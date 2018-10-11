---
title: Performing an In-Place Upgrade
seo-title: Performing an In-Place Upgrade
description: null
seo-description: Learn how to perform an in-place upgrade.
uuid: 693c4f56-b091-4f2c-bd79-9376dac1af5f
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/in-place-upgrade
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-06-20T09 11 45.896-0400
cq-lastmodifiedby: sarchiz
cq-lastreplicated: 2018-05-03T10 53 36.286-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
cq-template: /apps/help/templates/article-3
discoiquuid: 0baaa3aa-50a9-432e-8a3e-c95b786c4927
firstPublishExternalDate: 2017-11-29T07:08:47.203-0500
isreadyforlocalization: false
jcr-created: 2018-02-10T08 01 13.002-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-05-03T10:53:36.176-0400
lochandoffdate: 2018-04-30T03 27 47.077-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
publishexternaldate: 2018-05-03T10 53 36.176-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/in-place-upgrade.html
sha1: 44ca1ad42468bd14ffdf0c33dd8d5afc3d9e2265
topicBrowsingSortDate: 2018-05-03T10:53:36.176-0400
index: y
internal: n
snippet: y
---

# Performing an In-Place Upgrade

>[!NOTE]
>
>This page outlines the upgrade procedure for AEM 6.4. If you have an installation that is deployed to an application server, see [Upgrade Steps for Application Server Installations](app-server-upgrade.md).

## Pre-Upgrade Steps
Before executing your upgrade, there are several steps that must be completed. See [Upgrading Code and Customizations](upgrading-code-and-customizations.md) and [Pre-Upgrade Maintenance Tasks](pre-upgrade-maintenance-tasks.md) for more information. Additionally, make sure that your system meets the requirements for the new version of AEM. See how Pattern Detector can help you estimate the complexity of your upgarde and also see the Upgrade Scope and Requirements section of [Planning Your Upgrade](upgrade-planning.md) for more information.

## Migration Prerequisites

* **Minimum Required Java version:** The migration tool only works with Java versions 7 and up. Note that for AEM 6.3 and up, Oracle's JRE 8 and IBM's JRE 7 & 8 are the only supported versions.

* **Upgraded Instance:** If you are upgrading from a version **older than 5.6**, make sure that you have performed an in-place upgrade to AEM 6.0 by following the procedure described in the 6.0 version of the Upgrade documentation.

## Preparation of the AEM Quickstart jar file

1. Stop the instance if it is running.  

1. Download the new AEM jar file and use it to replace the old one outside the `crx-quickstart` folder.  

1. Unpack the new quickstart jar by running:

   ```shell
   java -Xmx4096m -jar aem-quickstart.jar -unpack
   ```

## Content Repository Migration
This migration is not required if you are upgrading from AEM 6.3. For versions older than 6.3, Adobe provides a tool that can be used to migrate the repository to the new version of the Oak Segment Tar present in AEM 6.3. It is provided as part of the quickstart package and is mandatory for any upgrades that will be using TarMK. Upgrades for environments that are using MongoMK do not require repository migration. For more information on what the benefits of the new Segment Tar format are, see the [Migrating to Oak Segment Tar FAQ](revision-cleanup.md#OnlineRevisionCleanupFrequentlyAskedQuestions).

The actual migration is performed using the standard AEM quickstart jar file, executed with a new `-x crx2oak` option which executes the crx2oak tool in order to simplify the upgrade and make it more robust.

>[!NOTE]
>
>If you are performing TarMK repository content migration using the CRX2Oak Quickstart extension, you might remove the **samplecontent** runmode by adding the following to the migration command line:
>
>* `--promote-runmode nosamplecontent`
>

To determine the command that you should run, use the following command:

```shell
java -Xmx4096m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile <<YOUR_PROFILE>> <<ADDITIONAL_FLAGS>>
```

Where `<<YOUR_PROFILE>>` and `<<ADDITIONAL_FLAGS>>` are replaced with the profile and flags listed in the following table:

| **Source Repository** |**Target Repository** |**Profile** |**Additional Flags** 
|
|---|---|---|---|
| crx2 or TarMK with `FileDataStore` |TarMK |segment-fds |See Troubleshooting section below |
| crx2 |MongoMK |mongo-from-crx2  | `-T mongo-uri=mongo://mongo-host:mongo-port -T mongo-db=mongo-database-name` |
| `TarMK or crx2 with `S3DataStore`` |TarMK |segment-custom-ds |See Troubleshooting section below |
| TarMK with no datastore |TarMK |segment-no-ds |  |
| MongoMK |MongoMK |No migration is needed |  |

**Where:**

* `mongo-host` is the MongoDB server IP (for example, 127.0.0.1)  

* `mongo-port` is the MongoDB server port (for example: 27017)  

* `mongo-database-name` represents the name of the database (for example: aem-author)

**You may also require additional switches for the following scenarios:**

* If you are performing the upgrade on a Windows system where Java memory mapping is not handled correctly, please add the `--disable-mmap` parameter to the command.  

* If you are using Java 7, add the `-XX:MaxPermSize=2048m` parameter just after the `-Xmx` parameter.

For additional instructions on using the crx2oak tool, see Using the [CRX2Oak Migration Tool](using-crx2oak.md). The crx2oak helper JAR can be manually upgraded if needed, by manually replacing it with newer versions after unpacking the quickstart. Its location in the AEM installation folder is: `<aem-install>/crx-quickstart/opt/extensions/crx2oak.jar`. The newest version of the CRX2Oak migration tool is available for download from the Adobe Repository at: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/crx2oak/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/crx2oak/)

If the migration has completed successfully, the tool will exit with an exit code of zero. Additionally, check for WARN and ERROR messages in the `upgrade.log` file, located under `crx-quickstart/logs` in the AEM installation directory, as these could indicate non-fatal errors that occurred during the migration.

Check the configuration files beneath `crx-quickstart/install` folder. If a migration was necessary these will be updated to reflect the target repository.

**A note on datastores:**

While `FileDataStore` is the new default for AEM 6.3 installations, using an external datastore is not required. While using an external datastore is recommended as a best practice for production deployments, it is not a prerequisite to upgrade. Due to the complexity already present in upgrading AEM, we recommend performing the upgrade without doing a datastore migration. If desired, a datastore migration can be executed afterwards as a separate effort.

## Troubleshooting Migration Issues
Please skip this section if you are upgrading from 6.3. While the provided crx2oak profiles should meet the needs of most customers, there are times when additional parameters will be necessary. If you run into an error during your migration, it is possible that there are aspects of your environment that require additional configuration options to be provided. If so, you will likely encounter the following error:

**Checkpoints won't be copied, because no external datastore has been specified. This will result in the full repository reindexing on the first start. Use --skip-checkpoints to force the migration or see https://jackrabbit.apache.org/oak/docs/migration.html#Checkpoints_migration for more info.**

For some reason, the migration process needs access to binaries in the datastore and is unable to find it. In order to specify your datastore configuration, include the following flags in the `<<ADDITIONAL_FLAGS>>` portion of your migration command:

**For S3 datastores:**

```shell
--src-s3config=/path/to/SharedS3DataStore.config --src-s3datastore=/path/to/datastore
```

Where `/path/to/SharedS3DataStore.config` represents the path to your S3 datastore config file and `/path/to/datastore` represents the path to your S3 datastore.

**For File datastores:**

```shell
--src-datastore=/path/to/datastore
```

Where `/path/to/datastore` represents the path to your File Datastore.

## Performing The Upgrade
**If using S3:**

1. Remove any jars beneath `crx-quickstart/install` associated with an earlier version of the S3 connector.  

1. Download the latest release of the 1.6.x S3 connector from [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)  

1. Extract the package to a temporary folder and copy the contents of `jcr_root/libs/system/install` to the `crx-quickstart/install` folder.

### Determining the correct upgrade start command
To execute the upgrade, it is important to start AEM using the jar file to bring up the instance. For upgrading to 6.4, please also see other content restructuring and migration options in [Lazy Content Migration](lazy-content-migration.md) that you can choose with the upgrade command.

Note that starting AEM from the start script will not start the upgrade. Most customers start AEM using the start script and have customized this start script to include switches for environment configurations such as memory settings, security certificates, etc. For this reason, we recommend following this procedure to determine the proper upgrade command:

1. On a running AEM instance, execute the following from the command line:

   ```shell
   ps -ef | grep java
   ```

1. Look for the AEM process. It will look something like:

   ```shell
   /usr/bin/java -server -Xmx1024m -XX:MaxPermSize=256M -Djava.awt.headless=true -Dsling.run.modes=author,crx3,crx3tar -jar crx-quickstart/app/cq-quickstart-6.2.0-standalone-quickstart.jar start -c crx-quickstart -i launchpad -p 4502 -Dsling.properties=conf/sling.properties
   ```

1. Modify the command by replacing the path to the existing jar ( `crx-quickstart/app/aem-quickstart*.jar` in this case) with the new jar that is a sibling of the `crx-quickstart` folder. Using our previous command as an example, our command would be:

   ```shell
   /usr/bin/java -server -Xmx1024m -XX:MaxPermSize=256M -Djava.awt.headless=true -Dsling.run.modes=author,crx3,crx3tar -jar cq-quickstart-6.3.0.jar start -c crx-quickstart -i launchpad -p 4502 -Dsling.properties=conf/sling.properties
   ```

   This will ensure that all proper memory settings, custom runmodes, and other environmental parameters are applied for the upgrade. After the upgrade has completed, the instance may be started from the start script on future startups.

## Deploy Upgraded Codebase
Once the in-place upgrade process has been completed, the updated code base should be deployed. Steps for updating the code base to work in the target version of AEM can be found in [Upgrade Code and Customizations page](upgrading-code-and-customizations.md).

## Perform Post-Upgrade Checks and Troubleshooting
See [Post Upgrade Checks and Troubleshooting](post-upgrade-checks-and-troubleshooting.md).
