---
title: Communities User Synchronization
seo-title: Communities User Synchronization
description: null
seo-description: How user synchronization works
uuid: 3ee8d489-8b24-436b-b6d0-a3ed95be21d7
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 04692f4b-d0ce-47b5-b689-608bef08ece7
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Communities User Synchronization{#communities-user-synchronization}

## Introduction {#introduction}

In AEM Communities, from the publish environment (depending on permissions configured), *site visitors *may become *members*, create *user groups*, and edit their *member profile* .

*User data* is a term used to refer to *users*, *user profiles* and *user groups*.

*Members *is a term used to refer to *users *registered in the publish environment, as opposed to users registered in the author environment.

For more information regarding user data, visit [Managing Users and User Groups](../../communities/using/users.md).

## Synchronizing Users Across a Publish Farm {#synchronizing-users-across-a-publish-farm}

By design, user data created in the publish environment does not appear in the  author  environment.

Most user data created in the  author  environment is intended to remain in the  author  environment and is not synchronized nor replicated to publish instances.

When the [topology](../../communities/using/topologies.md) is a [publish farm](../../sites/deploying/using/recommended-deploys.md#tarmkfarm), registration  and  modifications made on one publish instance need to be synchronized with other publish instances. Members need to be able to log in and see their data on any publish node.

When user synchronization is enabled, user data is automatically synchronized across the publish instances in the farm.

### User Sync Setup Instructions {#user-sync-setup-instructions}

For detailed, step-by-step instructions, on how to enable synchronization across a publish farm, see

* [User Synchronization](../../sites/administering/using/sync.md)

## What Happens When ... {#what-happens-when}

### Publish Site from Communities Sites Console {#publish-site-from-communities-sites-console}

On author, when a community site is published from the [Communities Sites console](../../communities/using/sites-console.md), the effect is to [replicate](../../sites/deploying/using/configuring.md#replicationreversereplicationandreplicationagents) the associated pages, and Sling distribute the dynamically created community user groups, including their membership.

### User is Created or Edits Profile on Publish {#user-is-created-or-edits-profile-on-publish}

By design, users and profiles created in the publish environment (such as by self-registration, social-login, LDAP authentication) do not appear in the author environment.

When the topology is a [publish farm](../../communities/using/topologies.md) and user sync has been correctly configured, the *user *and *user profile* is synchronized across the publish farm using Sling distribution.

### New Community Group is created on Publish {#new-community-group-is-created-on-publish}

Although initiated from a publish instance, the community group creation, which results in new site pages and a new user group, actually occurs on the author instance.

As part of the process, the new site pages are replicated to all publish instances. The dynamically created community user group and its membership are Sling distributed to all publish instances.

### Users or User Groups are Created Using Security Console {#users-or-user-groups-are-created-using-security-console}

By design, user data created in the publish environment does not appear in the author environment and vice versa.

When the [User Administration and Security](../../sites/administering/using/security.md) console is used to add new users in the publish environment, user sync will synchronize the new users and their group membership to other publish instances, if necessary. User sync will also synchronize user groups created through the security console.

### User Posts Content on Publish {#user-posts-content-on-publish}

For user generated content (UGC), the data entered on a publish instance is accessed through the [configured SRP](../../communities/using/srp-config.md).

## Best practices {#bestpractices}

By default, user sync is **disabled**. Enabling user sync involves modifying *existing* OSGi configurations. No new configurations should be added as a result of enabling user sync.

User sync relies on the author environment to manage the user data distributions, even though the user data is not created on author.

Following configurations are necessary to enable user synchronization on AEM Communities. Ensure that these configurations are correct to prevent sling content distribution from failing.

**Prerequisites**

1. If users and user groups have already been created on one publisher, it is recommended to [manually sync](../../sites/administering/using/sync.md#manuallysyncingusersandusergroups) the user data to all publishers prior to configuring and enabling user sync.  
   Once user sync is enabled, only newly created users and groups are syncrhonized. 

1. Ensure the latest code has been installed:

    * [AEM platform updates](/content/help/en/experience-manager/kb/aem62-available-hotfixes)
    * [AEM Communities updates](../../communities/using/deploy-communities.md#latestfeaturepack)

The default values in the configuration are for a single publish instance. As user sync is useful to synchronize multiple publish instances, such as for a publish farm, additional publish instances need to be added to the configuration.

On AEM Author instance:

1. sign in with administrator privileges.
1. access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html).  
   For example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. locate **Apache Sling Distribution Agent - Sync Agents Factory**

    * select the existing configuration to open for edit (pencil icon)  
      verify name : **socialpubsync**
    
    * select the **Enabled **checkbox
    * select **Use Multiple queues**
    * specify **Exporter Endpoints** and **Importer Endpoints **(you can add more exporter and importer endpoints)  
      These endpoints define where you want to get the content from and where you want to push the content. Author fetches the content from the specified exporter endpoint, and pushes the content to the publishers (other than the publisher from which it fetched the content).

![]()

It enables author to identify the authorized user, as having permission to sync user data from author to publish.

The [authorized user created](../../sites/administering/using/sync.md#createauthuser) on all the publish instances helps the publishers to connect with author and configure Sling distribution on author. This authorized user has all requisite [ACLs](../../sites/administering/using/sync.md#howtoaddacl).

On AEM author instance:

* sign in with administrator privileges
* access the [Web Console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* locate **Adobe Granite Distribution - Encrypted Password Transport Secret Provider**
* select the existing configuration to open for edit (pencil icon)  
  Verify property name : **socialpubsync-publishUser**

* set the username and password to the [authorized user](../../sites/administering/using/sync.md#createauthorizeduser)

    * for example, usersync-admin

Whenever data is to be installed on or fetched from publishers, then author connects with the publishers using the credentials (user name and password) set in this configuration.

![]()

On AEM Publish instance:

* sign in with administrator privileges.
* access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html)

    * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

* locate **Apache Sling Distribution Agent - Queue Agents Factory**

    * select the existing configuration to open for edit (pencil icon)  
      Verify Name : socialpubsync-reverse.
    * select the **Enabled** checkbox and save.

* repeat** **for each publish instance.

It syncs group membership across publishers.

On each AEM Publish instance:

* sign in with administrator privileges.
* access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html)

    * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

* locate Adobe Granite Distribution - Diff Observer Factory

    * select the existing configuration to open for edit (pencil icon)  
      Verify agent name : socialpubsync-reverse.
    * select the Enabled checkbox and Save.

The author polls publishers every 30 seconds (default). If any packages are present at the folder /var/sling/distribution/packages/socialpubsync-vlt/shared, then it will fetch those packages and install them on other publishers.

**To alter polling interval**

On AEM author instance:

1. sign in with administrator privileges.
1. access the [Web Console](../../sites/deploying/using/configuring-osgi.md),  
   for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

1. Locate **Apache Sling Distribution Trigger - Scheduled Triggers Factory**

* select the existing configuration to open for edit (pencil icon)  
  Verify Name : **socialpubsync-scheduled-trigger**

* set the Interval in Seconds to the desired interval, and save.

For issues in Sling distribution where there is discrepency in subscriptions and follows, check whether the following properties in **AEM Communities User Sync Listener** configurations are set.

On each AEM Publish instance:

* sign in with administrator privileges.
* access the [Web Console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

* locate **AEM Communities User Sync Listener.**
* select the existing configuration to open for edit (pencil icon)  
  Verify Name : **socialpubsync-scheduled-trigger**

* set the following **NodeTypes**:  
  rep:User  
  nt:unstructured  
  nt:resource  
  rep:ACL  
  sling:Folder  
  sling:OrderedFolder  
  The node types specified in this property will synchronize, and the notifications info (blogs and configurations followed) are synced between different publishers.

* Add all the folders to synchronize in **DistributedFolders**. For example,  
  segments/scoring  
  social/relationships  
  activities

* Set the ignorablenodes to:  
  .tokens  
  system  
  rep:cache (since we use sticky sessions, we need not sync this node to different publishers)

![]()

If the Sling ID of a publish instance matches the Sling ID of any other publish instance, then:

1. Stop one of the publish instances that has a matching Sling ID.
1. In the crx-quickstart/launchpad/felix directory, search for and delete the file named *sling.id.file.  
   *for example, on a Linux system:* 
   rm -i $(find . -type f -name sling.id.file)  
   *for example, on a Windows system:  
   use windows explorer and search for *sling.id.file*

1. Start the publish instance. On startup it will be assigned a new Sling ID. 
1. Validate that the **Sling ID** is now unique.

Repeat these steps until all publish instances have an unique Sling ID.

For updates to sync properly, it is necessary to modify the vault package builder for user sync. In /home/users a &#42;/rep:cache node is created. It is a cache which is used to find that if we query on a princepal name of a node then this cache can be used directly.

On each AEM publish instance:

1. access the [Web Console](../../sites/deploying/using/configuring-osgi.md)  
   for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

1. locate the **Apache Sling Distribution Packaging - Vault Package Builder Factory  
   **Builder name: socialpubsync-vlt.
1. select the edit icon.
1. add two Package Filters:

    * /home/users|-.&#42;/.tokens
    * /home/users|**+**.&#42;/rep:cache

1. policy handling

    * to overwrite existing rep:policy nodes with new ones, add a third Package Filter:  
      /home/users|**+**.&#42;/rep:policy
    
    * to prevent policies from being distributed, set  
      Acl Handling: IGNORE

1. **Apache Sling Distribution Agent - Sync Agents Factory**

   This configuration fetches the content to be synced across the publishers.

   The default values in the configuration are for a single publish instance. As user sync is useful to synchronize multiple publish instances, such as for a publish farm, additional publish instances need to be added to the configuration.

   On AEM Author instance:

    1. sign in with administrator privileges.
    1. access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html).  
       For example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
    
    1. locate **Apache Sling Distribution Agent - Sync Agents Factory**

        * select the existing configuration to open for edit (pencil icon)  
          verify name : **socialpubsync**
        
        * select the **Enabled **checkbox
        * select **Use Multiple queues**
        * specify **Exporter Endpoints** and **Importer Endpoints **(you can add more exporter and importer endpoints)  
          These endpoints define where you want to get the content from and where you want to push the content. Author fetches the content from the specified exporter endpoint, and pushes the content to the publishers (other than the publisher from which it fetched the content).

1. **Apache Sling Distribution Agent - Queue Agents Factory**

   On AEM Publish instance:

    * sign in with administrator privileges.
    * access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html)

        * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

    * locate **Apache Sling Distribution Agent - Queue Agents Factory**

        * select the existing configuration to open for edit (pencil icon)  
          Verify Name : socialpubsync-reverse.
        * select the **Enabled** checkbox and save.

    * repeat** **for each publish instance.

   ![]()

1. **Adobe Granite Distribution - Diff Observer Factory**

   On each AEM Publish instance:

    * sign in with administrator privileges.
    * access the [Web Console](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html)

        * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

    * locate Adobe Granite Distribution - Diff Observer Factory

        * select the existing configuration to open for edit (pencil icon)  
          Verify agent name : socialpubsync-reverse.
        * select the Enabled checkbox and Save.

   ![]()

1. **Apache Sling Distribution Trigger - Scheduled Triggers Factory**

   The author polls publishers every 30 seconds (default). If any packages are present at the folder /var/sling/distribution/packages/socialpubsync-vlt/shared, then it will fetch those packages and install them on other publishers.  
   **To alter polling interval**

   On AEM author instance:

    1. sign in with administrator privileges.
    1. access the [Web Console](../../sites/deploying/using/configuring-osgi.md),  
       for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)
    
    1. Locate **Apache Sling Distribution Trigger - Scheduled Triggers Factory**

    * select the existing configuration to open for edit (pencil icon)  
      Verify Name : **socialpubsync-scheduled-trigger**
    
    * set the Interval in Seconds to the desired interval, and save.

1. **Apache Sling Distribution Agent - Sync Agents Factory**

   Specify the exporter and importer endpoints

1. **AEM Communities User Sync Listener**

   For issues in Sling distribution where there is discrepency in subscriptions and follows, check whether the following properties in **AEM Communities User Sync Listener** configurations are set.

   On each AEM Publish instance:

    * sign in with administrator privileges.
    * access the [Web Console](../../sites/deploying/using/configuring-osgi.md)

        * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).

    * locate **AEM Communities User Sync Listener.**
    * select the existing configuration to open for edit (pencil icon)  
      Verify Name : **socialpubsync-scheduled-trigger**
    
    * set the following **NodeTypes**:  
      rep:User  
      nt:unstructured  
      nt:resource  
      rep:ACL  
      sling:Folder  
      sling:OrderedFolder  
      The node types specified in this property will synchronize, and the notifications info (blogs and configurations followed) are synced between different publishers.
    
    * Add all the folders to synchronize in **DistributedFolders**. For example,  
      segments/scoring  
      social/relationships  
      activities
    
    * Set the ignorablenodes to:  
      .tokens  
      system  
      rep:cache (since we use sticky sessions, we need not sync this node to different publishers)

   ![]()

1. **Unique Sling ID**

   Make sure all the publishers in a publish farm have a unique Sling ID. If the Sling ID is the same for multiple publish instances in a publish farm, then user groups will not be synchronized.

   To validate that all Sling ID values differ, on each publish instance :

    1. browse to [http://*host:port*/system/console/status-slingsettings](http://localhost:4503/system/console/status-slingsettings)
    1. check the value of **Sling ID**

   ![]()

   If the Sling ID of a publish instance matches the Sling ID of any other publish instance, then:

    1. Stop one of the publish instances that has a matching Sling ID.
    1. In the `crx-quickstart/launchpad/felix` directory, search for and delete the file named *sling.id.file.  
       *for example, on a Linux system:* 
       rm -i $(find . -type f -name sling.id.file)  
       *for example, on a Windows system:  
       use windows explorer and search for *sling.id.file*
    
    1. Start the publish instance. On startup it will be assigned a new Sling ID. 
    1. Validate that the **Sling ID** is now unique.

   Repeat these steps until all publish instances have an unique Sling ID.

1. **Vault Package Builder Factory**

   For updates to sync properly, it is necessary to modify the vault package builder for user sync. In `/home/users` a `*/rep:cache` node is created. It is a cache which is used to find that if we query on a princepal name of a node then this cache can be used directly.

   On each AEM publish instance:

    1. access the [Web Console](../../sites/deploying/using/configuring-osgi.md)  
       for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr).
    
    1. locate the **Apache Sling Distribution Packaging - Vault Package Builder Factory  
       **Builder name: `socialpubsync-vlt`.
    
    1. select the edit icon.
    1. add two Package Filters:

        * /home/users|-.&#42;/.tokens
        * /home/users|**+**.&#42;/rep:cache

    1. policy handling

        * to overwrite existing rep:policy nodes with new ones, add a third Package Filter:  
          /home/users|**+**.&#42;/rep:policy
        
        * to prevent policies from being distributed, set  
          Acl Handling: IGNORE

## Troubleshoot Sling distribution in AEM Communities {#troubleshoot-sling-distribution-in-aem-communities}

If Sling distribution fails, try the following debugging steps:

1. **Check for improperly added configurations.** Additional configurations added
1. **Check configurations**. Ensure that all the [configurations](../../communities/using/sync.md#bestpractices)are appropriately set in your AEM Author instance.
1. **Check authorized user permissions**. If the packages are not installed properly, then check that the [authorized user](../../sites/administering/using/sync.md#createauthuser) created in the first Publish instance has the correct ACLs.

   To validate this, instead of the [created authorized user](../../sites/administering/using/sync.md#createauthuser) change the [Adobe Granite Distribution - Encrypted Password Transport Secret Provider](../../sites/administering/using/sync.md#adobegraniteencpasswrd) configuration on Author instance to use Admin user credentials. Now try installing the packages again. If the user sync works fine with administrator credentials, then it means that the created publish user did not have appropriate ACLs.

1. **Check Diff Observer Factory configuration**. If only specific nodes are not synced across the publish farm- for example, group members are not synchronized- then ensure that the [Adobe Granite Distribution - Diff Observer Factory](../../sites/administering/using/sync.md#diffobserver) configuration is enabled and **rep  :members ** are set in **looked properties names**.
1. **Check AEM Communities User Sync Listener configuration. **If the created users are synced but subscriptions and follows are not working, then ensure that AEM Communities User Sync Listener configuration has:

    * Node types- set to **rep:User,  nt :unstructured**, ** nt :resource**, **rep:ACL**, **sling:Folder**, and **sling:OrderedFolder**
    
    * Ignorable nodes- set to **.tokens**, **system**, and **rep  :cache **
    
    * Distributed Folders- set to the folders which you want to be distributed

1. **Check logs generated on user creation on Publish instance**. If the above configurations are appropriately set yet user sync is not working, then check the logs generated on user creation.

   Check whether the order of logs is the same, as follows:

   ```shell
   15.05.2016 18:33:01.523 *INFO* [sling-oak-observation-7422] com.adobe.cq.social.sync.impl.PublisherSyncServiceImpl Handing these paths to the distribution subsystem: [/home/users/C, /home/users/C/Cw-5avWqilmqsNn5hCvK]
   15.05.2016 18:33:01.523 *INFO* [sling-oak-observation-7422] org.apache.sling.distribution.agent.impl.SimpleDistributionAgent [agent][socialpubsync-reverse] REQUEST-START DSTRQ2: ADD paths=[/home/users/C, /home/users/C/Cw-5avWqilmqsNn5hCvK], user=communities-user-admin
   15.05.2016 18:33:01.523 *INFO* [sling-oak-observation-7431] com.adobe.cq.social.sync.impl.PublisherSyncServiceImpl Handing these paths to the distribution subsystem: [/home/users/C/Cw-5avWqilmqsNn5hCvK, /home/users/C/Cw-5avWqilmqsNn5hCvK/profile, /home/users/C/Cw-5avWqilmqsNn5hCvK/rep:policy]
   15.05.2016 18:33:01.523 *INFO* [sling-oak-observation-7431] org.apache.sling.distribution.agent.impl.SimpleDistributionAgent [agent][socialpubsync-reverse] REQUEST-START DSTRQ3: ADD paths=[/home/users/C/Cw-5avWqilmqsNn5hCvK, /home/users/C/Cw-5avWqilmqsNn5hCvK/profile, /home/users/C/Cw-5avWqilmqsNn5hCvK/rep:policy], user=communities-user-admin
   15.05.2016 18:33:01.757 *INFO* [sling-oak-observation-7431] org.apache.jackrabbit.vault.packaging.impl.JcrPackageDefinitionImpl unwrapping package sling/distribution:socialpubsync-vlt_1463337181554_ebb27ad9-a861-4405-9342-d64c916654e2:0.0.1
   15.05.2016 18:33:01.820 *INFO* [sling-oak-observation-7422] org.apache.jackrabbit.vault.packaging.impl.JcrPackageDefinitionImpl unwrapping package sling/distribution:socialpubsync-vlt_1463337181554_58811273-5861-48fe-95d2-4aff367b99c3:0.0.1
   15.05.2016 18:33:02.023 *INFO* [sling-oak-observation-7430] com.adobe.cq.social.sync.impl.PublisherSyncServiceImpl Handing these paths to the distribution subsystem: [/home/users/C/Cw-5avWqilmqsNn5hCvK/profile]
   15.05.2016 18:33:02.023 *INFO* [sling-oak-observation-7430] org.apache.sling.distribution.agent.impl.SimpleDistributionAgent [agent][socialpubsync-reverse] REQUEST-START DSTRQ4: ADD paths=[/home/users/C/Cw-5avWqilmqsNn5hCvK/profile], user=communities-user-admin
   15.05.2016 18:33:02.273 *INFO* [sling-oak-observation-7430] org.apache.jackrabbit.vault.packaging.impl.JcrPackageDefinitionImpl unwrapping package sling/distribution:socialpubsync-vlt_1463337182039_f34f4fa6-10b9-42eb-8740-4da9d4d38f99:0.0.1
   ```

   To debug:

    1. Disable the user synchronization:  
    1. On AEM Author instance, sign in with administrator privileges.  
       2. Access the [Web Console](../../sites/deploying/using/configuring-osgi.md). For example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).  
       3. Locate the configuration **Apache Sling Distribution Agent - Sync Agents Factory**.  
       4. Disable the **Enabled** checkbox.
    
    1. Go to the first publisher, and create a user on the publisher. As a result, events are created. 
    1. Check the order of logs, created on user creation.
    1. Check whether a ** vlt  **package is created on **/var/sling/distribution/packages/socialpubsync-vlt/data**.
    
    1.

