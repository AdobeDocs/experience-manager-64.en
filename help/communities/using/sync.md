---
title: Communities User Synchronization
seo-title: Communities User Synchronization
description: How user synchronization works
seo-description: How user synchronization works
uuid: 024f0fa8-9ff0-48f7-b394-e5f8133b97c3
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 41acf7bb-1125-4283-a4ed-8f98c440eed1
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

User sync relies on the  author  environment to manage the user data distributions, even though the user data is not created on  author .

**Prerequisites**

1. If users and user groups have already been created on one publisher, it is recommended to [manually sync](../../sites/administering/using/sync.md#manuallysyncingusersandusergroups) the user data to all publishers prior to configuring and enabling user sync.  
   Once user sync is enabled, only newly created users and groups are  syncrhonized . 

1. Ensure the latest code has been installed:

    * [AEM platform updates](https://helpx.adobe.com/experience-manager/kb/aem62-available-hotfixes.html)
    * [AEM Communities updates](../../communities/using/deploy-communities.md#latestfeaturepack)

Following configurations are necessary to enable user synchronization on AEM Communities. Ensure that these configurations are correct to prevent sling content distribution from failing.

### Apache Sling Distribution Agent - Sync Agents Factory {#apache-sling-distribution-agent-sync-agents-factory}

This configuration fetches the content to be synced across the publishers. The configuration is on Author instance.

The default values in the configuration are for a single publish instance. As user sync is useful to synchronize multiple publish instances, such as for a publish farm, additional publish instances need to be added to the configuration.

<details> 
 <summary>Item Title</summary> 
 <p>On AEM Author instance:</p> 
 <ol> 
  <li>sign in with administrator privileges.</li> 
  <li>Access the <a href="https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html">Web Console</a>.<br /> For example, <a href="http://localhost:4502/system/console/configMgr">http://localhost:4502/system/console/configMgr</a>.</li> 
  <li>Locate <strong>Apache Sling Distribution Agent - Sync Agents Factory.</strong> 
   <ul> 
    <li>Select the existing configuration to open for edit (pencil icon).<br /> Verify name: <strong> 
      <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_disable_anim_appear ContextualSpelling" data-gr-id="18" id="18">
        socialpubsync 
      </g>.</strong></li> 
    <li>Select the <strong>Enabled </strong>checkbox.</li> 
    <li>Select <strong>Use Multiple queues.</strong></li> 
    <li>Specify <strong>Exporter Endpoints</strong> and <strong>Importer Endpoints </strong>(you can add more exporter and importer endpoints).<br /> These endpoints define where you want to get the content from and where you want to push the content. Author fetches the content from the specified exporter endpoint and pushes the content to the publishers (other than the publisher from which it fetched the content).</li> 
   </ul> </li> 
 </ol> 
 <img imageRotate="0" src="assets/sync-agent-fact.png" /> 
</details>

### Adobe Granite Distribution - Encrypted Password Transport Secret Provider {#adobe-granite-distribution-encrypted-password-transport-secret-provider}

It enables the author to identify the authorized user, as having permission to sync user data from  author  to publish.

The [authorized user created](../../sites/administering/using/sync.md#createauthuser) on all the publish instances helps the publishers to connect with  author  and configure Sling distribution on the author. This authorized user has all the requisite [ACLs](../../sites/administering/using/sync.md#howtoaddacl).

Whenever data is to be installed on or fetched from publishers, then the author connects with the publishers using the credentials (user name and password) set in this configuration.

<details> 
 <summary>Item Title</summary> 
 <p>On AEM author instance:</p> 
 <ol> 
  <li>Sign in with administrator privileges.</li> 
  <li>Access the <a href="../../sites/deploying/using/configuring-osgi.md">Web Console</a>.<br /> For example, <a href="http://localhost:4502/system/console/configMgr">http://localhost:4502/system/console/configMgr</a>.</li> 
  <li>Locate <strong>Adobe Granite Distribution - Encrypted Password Transport Secret Provider.</strong></li> 
  <li>Select the existing configuration to open for edit (pencil icon).<br /> Verify property 
   <g class="gr_ gr_122 gr-alert gr_gramm gr_inline_cards gr_run_anim Style multiReplace" data-gr-id="122" id="122">
     name : 
   </g> <strong> 
    <g class="gr_ gr_15 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="15" id="15">
      socialpubsync 
    </g>- 
    <g class="gr_ gr_13 gr-alert gr_spell gr_inline_cards gr_disable_anim_appear ContextualSpelling ins-del multiReplace" data-gr-id="13" id="13">
      publishUser 
    </g>.</strong></li> 
  <li>Set the username and password to the <a href="../../sites/administering/using/sync.md#createauthorizeduser">authorized user</a>.<br /> For example, <strong> 
    <g class="gr_ gr_163 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="163" id="163">
      usersync 
    </g>-admin</strong></li> 
 </ol> 
 <img imageRotate="0" src="assets/granite-paswrd-trans.png" /> 
</details>

### Apache Sling Distribution Agent - Queue Agents Factory {#apache-sling-distribution-agent-queue-agents-factory}

This configuration is used to configure the data you want to sync across publishers. When data is created/ updated in paths specified in **Allowed Roots**, "var/community/distribution/diff" gets activated and the created replicator fetches the data from a publisher and installs it on other publishers.

<details> 
 <summary>Item Title</summary> 
 <p>On AEM Publish instance:</p> 
 <ol> 
  <li>Sign in with administrator privileges.</li> 
  <li>Access the <a href="https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html">Web Console</a>.<br /> For example, <a href="http://localhost:4503/system/console/configMgr">http://localhost:4503/system/console/configMgr</a>.</li> 
  <li>Locate <strong>Apache Sling Distribution Agent - Queue Agents Factory.</strong></li> 
  <li>Select the existing configuration to open for edit (pencil icon).<br /> Verify Name: 
   <g class="gr_ gr_22 gr-alert gr_spell gr_inline_cards gr_disable_anim_appear ContextualSpelling" data-gr-id="22" id="22" style="font-size: 12px;">
     socialpubsync 
   </g>-reverse.</li> 
  <li>Select the <strong>Enabled</strong> checkbox and save.</li> 
  <li> Specify the node paths that are to be replicated in <strong>Allowed roots</strong>.</li> 
  <li>Repeat<strong> </strong>for each publish instance.</li> 
 </ol> 
 <img imageRotate="0" src="assets/queue-agents-fact.png" /> 
</details>

### Adobe Granite Distribution - Diff Observer Factory {#adobe-granite-distribution-diff-observer-factory}

This configuration syncs group membership across publishers.   
If changing the membership of a group in one publisher does not update its membership on other publishers, then ensure that **ref  :members ** is  added to **looked properties names**.

<details> 
 <summary>Item Title</summary> 
 <p>On each AEM Publish instance:</p> 
 <ol> 
  <li>Sign in with administrator privileges.</li> 
  <li>Access the <a href="https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html">Web Console</a>.<br /> For example, <a href="http://localhost:4503/system/console/configMgr">http://localhost:4503/system/console/configMgr</a>.</li> 
  <li>Locate <strong>Adobe Granite Distribution - Diff Observer Factory.</strong></li> 
  <li>Select the existing configuration to open for edit (pencil icon).<br /> Verify <strong>agent name: 
    <g class="gr_ gr_11 gr-alert gr_spell gr_inline_cards gr_disable_anim_appear ContextualSpelling" data-gr-id="11" id="11">
      socialpubsync 
    </g>-reverse</strong>.</li> 
  <li>Select the <strong>Enabled </strong>checkbox.</li> 
  <li>Specify <strong>rep 
    <g class="gr_ gr_58 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="58" id="58">
      :members 
    </g> </strong>as 
   <g class="gr_ gr_23 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar only-ins doubleReplace replaceWithoutSep" data-gr-id="23" id="23">
     description 
   </g> for propertyName in <strong>looked properties names</strong>, and Save.</li> 
 </ol> 
 <img imageRotate="0" src="assets/diff-obs.png" /> 
</details>

### Apache Sling Distribution Trigger - Scheduled Triggers Factory {#apache-sling-distribution-trigger-scheduled-triggers-factory}

The author polls publishers every 30 seconds (default). If any packages are present at the folder /var/sling/distribution/packages/  socialpubsync -  vlt /shared, then it will fetch those packages and install them on other publishers.

<details> 
 <summary>To alter polling interval</summary> 
 <p>On AEM author instance:</p> 
 <ol> 
  <li>sign in with administrator privileges.</li> 
  <li>access the <a href="../../sites/deploying/using/configuring-osgi.md">Web Console</a>,<br /> for example, <a href="http://localhost:4502/system/console/configMgr">http://localhost:4502/system/console/configMgr</a></li> 
  <li>Locate <strong>Apache Sling Distribution Trigger - Scheduled Triggers Factory</strong></li> 
 </ol> 
 <ul> 
  <li>select the existing configuration to open for edit (pencil icon)<br /> Verify 
   <g class="gr_ gr_13 gr-alert gr_gramm gr_inline_cards gr_run_anim Style multiReplace" data-gr-id="13" id="13">
     Name : 
   </g> <strong> 
    <g class="gr_ gr_12 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="12" id="12">
      socialpubsync 
    </g>-scheduled-trigger</strong></li> 
  <li>set the Interval in Seconds to the desired interval, and save.</li> 
 </ul> 
 <img /> 
</details>

### Apache Sling Distribution Agent - Sync Agents Factory {#apache-sling-distribution-agent-sync-agents-factory-1}

Specify the exporter and importer endpoints.

This configuration fetches the content to be synced across the publishers.

The default values in the configuration are for a single publish instance. As user sync is useful to synchronize multiple publish instances, such as for a publish farm, additional publish instances need to be added to the configuration.

<details> 
 <summary>Item Title</summary> 
 <p>On AEM Author instance:</p> 
 <ol> 
  <li>sign in with administrator privileges.</li> 
  <li>access the <a href="https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-osgi.html">Web Console</a>.<br /> For example, <a href="http://localhost:4502/system/console/configMgr">http://localhost:4502/system/console/configMgr</a>.</li> 
  <li>locate <strong>Apache Sling Distribution Agent - Sync Agents Factory</strong> 
   <ul> 
    <li>select the existing configuration to open for edit (pencil icon)<br /> verify name: <strong> 
      <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="18" id="18">
        socialpubsync 
      </g></strong></li> 
    <li>select the <strong>Enabled </strong>checkbox.</li> 
    <li>select <strong>Use Multiple queues.</strong></li> 
    <li>specify <strong>Exporter Endpoints</strong> and <strong>Importer Endpoints </strong>(you can add more exporter and importer endpoints).<br /> These endpoints define where you want to get the content from and where you want to push the content. Author fetches the content from the specified exporter endpoint and pushes the content to the publishers (other than the publisher from which it fetched the content).</li> 
   </ul> </li> 
 </ol> 
 <img /> 
</details>

### AEM Communities User Sync Listener {#aem-communities-user-sync-listener}

For issues in Sling distribution where there is a discrepancy in subscriptions and follows, check whether the following properties in **AEM Communities User Sync Listener** configurations are set.

<details> 
 <summary>Item Title</summary> 
 <p>On each AEM Publish instance:</p> 
 <ol> 
  <li>sign in with administrator privileges.</li> 
  <li>access the <a href="../../sites/deploying/using/configuring-osgi.md">Web Console.<br /> </a>For example, <a href="http://localhost:4503/system/console/configMgr">http://localhost:4503/system/console/configMgr</a>.</li> 
  <li>locate <strong>AEM Communities User Sync Listener.</strong></li> 
  <li>select the existing configuration to open for edit (pencil icon)<br /> Verify Name: <strong> 
    <g class="gr_ gr_31 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="31" id="31">
      socialpubsync 
    </g>-scheduled-trigger</strong></li> 
  <li>set the following <strong> 
    <g class="gr_ gr_28 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="28" id="28">
      NodeTypes 
    </g></strong>:<br /> rep 
   <g class="gr_ gr_35 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="35" id="35">
     :User 
   </g><br /> 
   <g class="gr_ gr_29 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="29" id="29">
     nt 
   </g>:unstructured<br /> 
   <g class="gr_ gr_30 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="30" id="30">
     nt 
   </g> 
   <g class="gr_ gr_36 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="36" id="36">
     :resource 
   </g><br /> rep 
   <g class="gr_ gr_37 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="37" id="37">
     :ACL 
   </g><br /> sling 
   <g class="gr_ gr_38 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="38" id="38">
     :Folder 
   </g><br /> sling 
   <g class="gr_ gr_39 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="39" id="39">
     :OrderedFolder 
   </g><br /> The node types specified in this property will synchronize, and the notifications info (blogs and configurations followed) are synced between different publishers.</li> 
  <li>Add all the folders to synchronize in <strong>DistributedFolders</strong>. For example,<br /> segments/scoring<br /> social/relationships<br /> activities</li> 
  <li>Set the<strong> 
    <g class="gr_ gr_27 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="27" id="27">
      ignorablenodes 
    </g></strong> to:<br /> .tokens<br /> system<br /> rep 
   <g class="gr_ gr_61 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="61" id="61">
     :cache 
   </g> (since we use sticky sessions, we need not sync this node to different publishers)</li> 
 </ol> 
 <img /> 
</details>

### Unique Sling ID {#unique-sling-id}

Make sure all the publishers in a publish farm have a unique Sling ID. If the Sling ID is the same for multiple publish instances in a publish farm, then user groups will not be synchronized.

<details> 
 <summary>Item Title</summary> 
 <p>Make sure all the publishers in a publish farm have a unique Sling ID. If the Sling ID is the same for multiple publish instances in a publish farm, then user groups will not be synchronized.</p> 
 <p>To validate that all Sling ID values differ, on each publish instance :</p> 
 <ol> 
  <li>browse to <a href="http://localhost:4503/system/console/status-slingsettings">http://<em>host:port</em>/system/console/status-slingsettings</a></li> 
  <li>check the value of <strong>Sling ID</strong></li> 
 </ol> 
 <img /> 
 <p>If the Sling ID of a publish instance matches the Sling ID of any other publish instance, then:</p> 
 <ol> 
  <li>Stop one of the publish instances that has a matching Sling ID.</li> 
  <li>In the <span class="code">crx-quickstart/launchpad/felix</span> directory, search for and delete the file named <em>sling.id.file.<br /> </em>for example, on a Linux system:<em><br /> rm -i $(find . -type f -name sling.id.file)<br /> </em>for example, on a Windows system:<br /> use windows explorer and search for <em>sling.id.file</em></li> 
  <li>Start the publish instance. On startup it will be assigned a new Sling ID. </li> 
  <li>Validate that the <strong>Sling ID</strong> is now unique.</li> 
 </ol> 
 <p>Repeat these steps until all publish instances have an unique Sling ID.</p> 
</details>

### Vault Package Builder Factory {#vault-package-builder-factory}

For updates to sync properly, it is necessary to modify the vault package builder for user sync.  
In **/home/users** a **&#42;/rep:cache **node is created. It is a cache which is used to find that if we query on the  principal  name of a node then this cache can be used directly.

<details> 
 <summary>Item Title</summary> 
 <p>On each AEM publish instance:</p> 
 <ol> 
  <li>access the <a href="../../sites/deploying/using/configuring-osgi.md">Web Console</a><br /> for example, <a href="http://localhost:4503/system/console/configMgr">http://localhost:4503/system/console/configMgr</a>.</li> 
  <li>locate the <strong>Apache Sling Distribution Packaging - Vault Package Builder Factory<br /> </strong>Builder name: socialpubsync-vlt.</li> 
  <li>select the edit icon.</li> 
  <li>add two Package Filters: 
   <ul> 
    <li>/home/users|-.*/.tokens</li> 
    <li>/home/users|<strong>+</strong>.*/rep:cache</li> 
   </ul> </li> 
  <li>policy handling 
   <ul> 
    <li>to overwrite existing rep:policy nodes with new ones, add a third Package Filter:<br /> /home/users|<strong>+</strong>.*/rep:policy</li> 
    <li>to prevent policies from being distributed, set<br /> Acl Handling: IGNORE</li> 
   </ul> </li> 
 </ol> 
</details>

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

