---
title: Pre-Upgrade Maintenance Tasks
seo-title: Pre-Upgrade Maintenance Tasks
description: null
seo-description: Learn about the pre-upgrade tasks in AEM.
uuid: ad602ac2-e596-467e-a8a8-bc608d3fa942
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/pre-upgrade-maintenance-tasks
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 53.306-0400
cq-lastmodifiedby: taneja
cq-lastreplicated: 2018-04-04T10 21 55.413-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
cq-template: /apps/help/templates/article-3
discoiquuid: 357204cd-80ad-4b14-a83f-15ef572060b7
firstPublishExternalDate: 2017-11-29T07:08:31.365-0500
isreadyforlocalization: false
jcr-created: 2017-12-16T19 01 29.310-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-04T10:21:53.846-0400
lochandoffdate: 2018-04-30T03 27 53.306-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
publishexternaldate: 2018-04-04T10 21 53.846-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/pre-upgrade-maintenance-tasks.html
sha1: 0ffd4ed45047651030b18db8f8dc58cd9ced7c4b
topicBrowsingSortDate: 2018-04-04T10:21:53.846-0400
index: y
internal: n
snippet: y
translate: y
---

# Pre-Upgrade Maintenance Tasks

Before beginning your upgrade, it is important to follow these maintenance tasks to ensure that the system is ready and can be rolled back should issues occur:

* [Ensure Sufficient Disk Space](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#ensure-sufficient-disk-space)
* [Fully Back Up AEM](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#fully-back-up-aem)
* [Back Up Changes to /etc](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#backup-changes-etc)
* [Generate The quickstart.properties File](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#generate-quickstart-properties)
* [Configure Workflow and Audit Log Purging](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#configure-wf-audit-purging)
* [Install, Configure, and Run The Pre-Upgrade Tasks](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#install-configure-run-pre-upgrade-tasks)
* [Disable Custom Login Modules](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#disable-custom-login-modules)
* [Remove Updates From The /install Directory](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#remove-updates-install-directory)
* [Stop Any Cold Standby Instances](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#stop-tarmk-coldstandby-instance)
* [Disable Custom Scheduled Jobs](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#disable-custom-scheduled-jobs)
* [Execute Offline Revision Cleanup](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#execute-offline-revision-cleanup)
* [Execute Datastore Garbage Collection](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#execute-datastore-garbage-collection)
* [Rotate Log Files](/pre-upgrade-maintenance-tasks.html?wcmmode=disabled#rotate-log-files)

## Ensure Sufficient Disk Space
When executing the upgrade, in addition to the content and code upgrade activities, a repository migration will need to be performed. The migration will create a copy of the repository in the new Segment Tar format. As a result, you will need enough disk space to retain a second, potentially larger, version of your repository.

## Fully Back Up AEM
AEM should be fully backed up before beginning the upgrade. Make sure to back up your repository, application installation, datastore, and Mongo instances if applicable. For more information on backing up and restoring an AEM instance, see [Backup and Restore](/content/help/en/experience-manager/6-4/sites/administering/using/backup-and-restore).

## Back Up Changes to /etc
The upgrade process does a good job of maintaining and merging existing content and configurations from under the `/apps` and `/libs` paths in the repository. For changes made to the `/etc` path, including Context Hub configurations, it is often necessary to re-apply these changes after the upgrade. While the upgrade will make a backup copy of any changes that it cannot merge under `/var`, we recommend backing up these changes manually before beginning the upgrade.

## Generate The quickstart.properties File
When starting AEM from the jar file, a `quickstart.properties` file will be generated under `crx-quickstart/conf`. If AEM has only been started with the start script in the past, this file will not be present and the upgrade will fail. Make sure to check for the existence of this file and restart AEM from the jar file if it is not present.

## Configure Workflow and Audit Log Purging
The `WorkflowPurgeTask` and `com.day.cq.audit.impl.AuditLogMaintenanceTask` tasks require separate OSGi configurations and will not work without them. If they fail during pre-upgrade task execution, missing configurations is the most likely reason. Therefore, make sure to add OSGi configurations for these tasks or remove them altogether from the pre-upgrade optimization tasks list if you do not wish to run them. Documentation for configuring workflow purging tasks can be found at [Administering Workflow Instances](/content/help/en/experience-manager/6-2/sites/administering/using/wf-administering#Regular Purging of Workflow Instances) and audit log maintenance task configuration can be found at [Audit Log Maintenance in AEM 6](/content/help/en/experience-manager/6-4/sites/administering/using/operations-audit-log).

For workflow and audit log purging on CQ 5.6 as well as audit log purging on AEM 6.0, see [Purge workflow and audit nodes](/content/help/en/experience-manager/kb/howtopurgewf).

## Install, Configure, and Run The Pre-Upgrade Tasks
Because of the level of customization AEM allows, environments usually do not adhere to a uniform way of performing upgrades. This makes creating a standardized procedure for upgrades a difficult process.

In previous versions, it was also difficult for AEM upgrades that were stopped or that have failed to be safely resumed. This led to situations where restarting the full upgrade procedure was necessary or where defective upgrades were carried out without triggering any warnings.

In order to address these issues, Adobe has added several enhancements to the upgrade process, making it more resilient and user friendly. Pre-upgrade maintenance tasks that before had to be performed manually are being optimized and automated. Also, post-upgrade reports have been added so that the process can be fully scrutinized in the hope that any issues are found more easily.

Pre-upgrade maintenance tasks are currently spread over various interfaces which are partially or completely performed manually. The pre-upgrade maintenance optimization introduced in AEM 6.3 enables a unified way to trigger these tasks and be able to inspect their result on demand.

All tasks included in the pre-upgrade optimization step are compatible with all versions from AEM 6.0 onwards.

### How to Set It Up
In AEM 6.3 and later, the pre-upgrade maintenance optimization tasks come included in the quickstart jar. If you are upgrading from an older version of AEM 6, they are made available through separate packages that you can download from the Package Manager.

You can find the packages at these locations:

* [For upgrading from AEM 6.0](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq600/product/pre-upgrade-tasks-content-cq60)

* [For upgrading from AEM 6.1](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq610/product/pre-upgrade-tasks-content-cq61)

* [For upgrading from AEM 6.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/product/pre-upgrade-tasks-content-cq62)

### How to Use It
The `PreUpgradeTasksMBean` OSGI component comes preconfigured with a list of pre-upgrade maintenance tasks that can be run all at once. You can configure the tasks by following the below procedure:

1. Go to the Web Console by browsing to *http://serveraddress:serverport/system/console/configMgr* 

1. Search for "**preupgradetasks**", then click on the first matching component. The full name of the component is `com.adobe.aem.upgrade.prechecks.mbean.impl.PreUpgradeTasksMBeanImpl`  

1. Modify the list of maintenance tasks that need to run as shown below:

   ![](assets/1487758925984.png)

The task list differs depending on the run mode that is being used to start the instance. Below is a description of the run mode each maintenance task is designed for.

| **Task** |**Run Mode** |**Notes** |
|---|---|---|
| `TarIndexMergeTask` |crx2 |  |
| `DataStoreGarbageCollectionTask` |crx2 |Will run mark and sweep. For shared datastores, remove this step and run  
manually or properly prepare instances before executing. |
| `ConsistencyCheckTask` |crx2 |  |
| `WorkflowPurgeTask` |crx2/crx3 |Must configure the Adobe Granite Workflow Purge Configuration OSGi before running. |
| `GenerateBundlesListFileTask` |crx2/crx3 |  |
| `RevisionCleanupTask` |crx3 |For TarMK instances on AEM 6.0 to 6.2, manually run Offline Revision Cleanup instead. |
| `com.day.cq.audit.impl.AuditLogMaintenanceTask` |crx3 |Must configure the Audit Log Purge Scheduler OSGi configuration before running. |

>[!CAUTION]
>
>`DataStoreGarbageCollectionTask` is calling a Datastore Garbage Collection operation with the mark and sweep phase if used. For deployments that use a shared datastore make sure to either reconfigure it or properly or prepare the instance to avoid deletion of items referenced by another instance. This might require running the mark phase manually on all instances before triggering this pre-upgrade task.

### Default Configuration of the Pre-Upgrade Health Checks
The `PreUpgradeTasksMBeanImpl` OSGI component comes pre-configured with a list of pre-upgrade health check tags to execute when the `runAllPreUpgradeHealthChecks` method is called:

* **system** - the tag used by the granite maintenance health checks  

* **pre-upgrade** - this is a custom tag that could be added to all the health checks that you can set to run before an upgrade

The list is editable. You can use the plus **(+)** and minus **(-)** buttons besides the tags to add more custom tags, or remove the default ones.

**MBean Methods**

The managed bean functionality can be accessed using the [JMX Console](/content/help/en/experience-manager/6-4/sites/administering/using/jmx-console).

You can access the MBeans by:

1. Going to the JMX Console at *http://serveraddress:serverport/system/console/jmx*
1. Search for **PreUpgradeTasks** and click the result  

1. Select any method from the **Operations** section and select **Invoke** in the following window.

Below is a list of all the available methods that the `PreUpgradeTasksMBeanImpl` exposes:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Method Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td><span class="code">getAvailablePreUpgradeTasksNames()</span></td> 
   <td>INFO</td> 
   <td>Displays the list of available pre-upgrade maintenance tasks names.</td> 
  </tr> 
  <tr> 
   <td><span class="code">getAvailablePreUpgradeHealthChecksTagNames()</span></td> 
   <td>INFO</td> 
   <td>Displays the list of pre-upgrade health checks tag names.</td> 
  </tr> 
  <tr> 
   <td><span class="code">runAllPreUpgradeTasks()</span></td> 
   <td>ACTION</td> 
   <td>Runs all the pre-upgrade maintenance tasks in the list.</td> 
  </tr> 
  <tr> 
   <td><span class="code">runPreUpgradeTask(preUpgradeTaskName)</span></td> 
   <td>ACTION</td> 
   <td>Runs the pre-upgrade maintenance task with the name given as the parameter.</td> 
  </tr> 
  <tr> 
   <td><span class="code">isRunAllPreUpgradeTaskRunning()</span></td> 
   <td>ACTION_INFO</td> 
   <td>Checks if the <span class="code">runAllPreUpgradeTasksmaintenance</span> task is currently running.</td> 
  </tr> 
  <tr> 
   <td><span class="code">getAnyPreUpgradeTaskRunning()</span></td> 
   <td>ACTION_INFO</td> 
   <td>Checks if any pre-upgrade maintenance task is currently running and<br /> returns an array containing the names of currently running tasks.</td> 
  </tr> 
  <tr> 
   <td><span class="code">getPreUpgradeTaskLastRunTime(preUpgradeTaskName)</span></td> 
   <td>ACTION</td> 
   <td>Displays the exact running time of the pre-upgrade maintenance task with the name given as the parameter.</td> 
  </tr> 
  <tr> 
   <td><span class="code">getPreUpgradeTaskLastRunState(preUpgradeTaskName)</span></td> 
   <td>ACTION</td> 
   <td>Displays the last running state of the pre-upgrade maintenance task with the name given as the parameter.</td> 
  </tr> 
  <tr> 
   <td><span class="code">runAllPreUpgradeHealthChecks(shutDownOnSuccess)</span></td> 
   <td>ACTION</td> 
   <td><p>Runs all the pre-upgrade health checks and saves their status in a file named <span class="code">preUpgradeHCStatus.properties</span> that is located in the sling home path. If the <span class="code">shutDownOnSuccess</span> parameter is set to <span class="code">true</span>, the AEM instance will be shut down, but only if all the pre-upgrade health checks have an OK status.</p> <p>The properties file will be used as a precondition for any future upgrade<br /> and the upgrade process will be stopped if the pre-upgrade health check<br /> execution failed. If you want to ignore the result of the pre-upgrade<br /> health checks and launch the upgrade anyway, you can delete the file.</p> </td> 
  </tr> 
  <tr> 
   <td><span class="code">detectUsageOfUnavailableAPI(aemVersion)</span></td> 
   <td>ACTION</td> 
   <td>Lists all the imported packages that will no longer be satisfied when<br /> upgrading to the specified AEM version. The target AEM version must be<br /> given as parameter.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The MBean methods can be invoked via:
>
>* The JMX Console  
>* Any external application that connects to JMX  
>* cURL
>

## Disable Custom Login Modules

>[!NOTE]
>
>This step is only required if you are upgrading from an AEM 5 version. It can be skipped entirely for upgrades from older AEM 6 versions.

The way custom `LoginModules` are configured for authentication at the repository level has fundamentally changed in Apache Oak.

In AEM versions that used CRX2 configuration was placed in the `repository.xml` file, while from AEM 6 onwards it is done in the Apache Felix JAAS Configuration Factory service via the Web Console.

Therefore, any existing configurations will have to be disabled and re-created for Apache Oak after the upgrade.

To disable the custom modules defined in the JAAS configuration of `repository.xml`, you need to modify the configuration to make use of default `LoginModule`, as in this example:

```xml
<Security >
             ....
          <!--
                 Use LoginModule authenticating against repository itself
                 -->
                 <LoginModule class = "com.day.crx.core.CRXLoginModule" >
                     <param name = "anonymousId" value = "anonymous" />
                     <param name = "adminId" value ="admin" />
                     <param name = "disableNTLMAuth" value = "true" />
                     <param name = "tokenExpiration" value = "43200000" />
                     <!-- param name="trust_credentials_attribute" value="d5b9167e95dad6e7d3b5d6fa8df48af8"/
                -->
                 </LoginModule >
         </ Security>
```

>[!NOTE]
>
>For more information, see [Authentication with the External Login Module](https://jackrabbit.apache.org/oak/docs/security/authentication/externalloginmodule.html).
>
>For an example of `LoginModule` configuration in AEM 6, see [Configuring LDAP with AEM 6](/content/help/en/experience-manager/6-4/sites/administering/using/ldap-config).

## Remove Updates From The /install Directory

>[!NOTE]
>
>Only remove packages from the crx-quickstart/install directory AFTER shutting down the AEM instance. This will be one of the last steps before starting the in-place upgrade procedure.

Remove any service packs, feature packs or hotfixes that have been deployed through the `crx-quickstart/install` directory on the local file system. This will prevent the inadvertent installation of old hotfixes and service packs on top of the new AEM version after the update has completed.

## Stop Any Cold Standby Instances
If using TarMK cold standby, stop any cold standby instances. These will guarantee an efficient way to come back online in case of issues in the upgrade. After the upgrade has completed successfully, the cold standby instances will need to be rebuilt from the upgraded primary instances.

## Disable Custom Scheduled Jobs
Disable any OSGi scheduled jobs that are included in your application code.

## Execute Offline Revision Cleanup

>[!NOTE]
>
>This step is only necessary for TarMK installations

If using TarMK, you should execute Offline Revision Cleanup before upgrading. This will make the repository migration step and subsequent upgrade tasks execute much faster and will help to ensure that Online Revision Cleanup can execute successfully after the upgrade has completed. For information on running Offline Revision Cleanup, see [Performing Offline Revision Cleanup](/content/help/en/experience-manager/6-2/sites/deploying/using/storage-elements-in-aem-6#PerformingOfflineRevisionCleanup).

## Execute Datastore Garbage Collection

>[!NOTE]
>
>This step is only necessary for instances running crx3

After running revision cleanup on CRX3 instances, you should run Datastore Garbage Collection to remove any unreferenced blobs in the data store. For instructions, see the documentation on [Data Store Garbage Collection](/content/help/en/experience-manager/6-4/sites/administering/using/data-store-garbage-collection).

## Rotate Log Files
We recommend archiving your current log files before beginning your upgrade. This will make it easier to monitor and scan your log files during and after the upgrade to identify and resolve any issues that may occur.
