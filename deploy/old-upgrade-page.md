---
uuid: 15598324-4c37-4571-b3c9-43eac1f80938
index: y
internal: n
snippet: y
translate: y
---

# Upgrading to AEM 6.3

>[!NOTE]
>
><p>AEM 6.2 introduces the next generation Java Content Repository that the documentation&nbsp;refers to as Apache Jackrabbit Oak or CRX3. It comes with many significant improvements, mainly with regards to scalability, performance and optimizations for AEM capabilities. For more info, please see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/platform.html" >Introduction to the AEM Platform</a>.</p> <p>Adobe removes the CRX2 compatibility option since the 6.1 release of Adobe Experience Manager. The upgrade process of AEM 6.2 contains the requirement to switch to the Oak-based repository during the update, that can be used for customers that want to update from AEM 5.x or AEM 6.0 using the compatibility option.</p> <p>Learn more about the available persistence options of Oak. Current info for AEM 6.2 is available on <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/recommended-deploys.html" >Recommended Deployments</a>.</p>

In this section we cover upgrading an AEM installation to AEM 6.3:

* [Upgrade Planning](upgrade.md#UpgradePlanning)
* [Upgrading Steps for JAR Based Installations ](upgrade.md#main-pars_title_1963308877)
* [Upgrading Steps for Application Server Installations ](upgrade.md#UpgradingStepsforApplicationServerInstallations)
* [Analyzing Issues with the Upgrade](upgrade.md#main-pars_title_1690331669)

For easier reference to the AEM instances involved in the procedures, the following terms are used throughout this article:

* The *source* instance is the AEM instance that you are upgrading from.
* The *target* instance is the one that you are upgrading to.

>[!NOTE]
>
><p>After you perform the upgrade, you need to <a href="/content/help/en/experience-manager/6-4/sites/administering/using/contexthub-config.html#main-pars_title_1835611820">recover your ContextHub configurations</a>.</p>

---

## Upgrade Planning

Upgrading AEM is an extensive task. Depending on the size of your deployment, planning needs to be undertaken in order to ensure the success of the upgrade. For more information, see [Planning Your Upgrade](/planning).

---

## Upgrading Steps for JAR Based Installations

>[!NOTE]
>
><p>Before starting the preparation steps, make sure you run the <b>source</b> instance first by executing it with the j<span class="code">ava -jar aem-quickstart.jar</span> command. This is required in order to make sure that the <span class="code">quickstart.properties</span> file is generated properly. If it is missing, the upgrade will not work.</p> <p>Alternatively, you can check whether the file is present by looking under <span class="code">crx-quickstart/conf</span> in the installation folder of the source instance.<br> </p>

### Pre-Upgrade Maintenance Optimization

Because of the level of customization AEM allows, environments usually do not adhere to a uniform way of performing upgrades. This makes creating a standardized procedure for upgrades a difficult process.

In previous versions, it was also difficult for AEM upgrades that were stopped or that have failed to be safely resumed. This led to situations where restarting the full upgrade procedure was necessary or where defective upgrades were carried out without triggering any warnings.

In order to address these issues, Adobe has added several enhancements to the upgrade process, making it more resilient and user friendly. Pre-upgrade maintenance tasks that before had to be performed manually are being optimized and automated. Also, post-upgrade reports have been added so that the process can be fully scrutinized in the hope that any issues are found more easily.

Pre-upgrade maintenance tasks are currently spread over various interfaces which are partially or completely performed manually. The pre-upgrade maintenance optimization added to AEM 6.3 enables a unified way to trigger these tasks and be able to inspect their result on demand.

All tasks included in the pre-upgrade optimization step are compatible with all versions from AEM 6.0 onwards.

#### How to Set It Up

In AEM 6.3, the pre-upgrade maintenance optimization tasks come included in the quickstart. For older versions of AEM 6, they are made available through separate packages that you can download from the Package Manager.

You can find the packages at these locations:

* [For AEM 6.0](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq600/product/pre-upgrade-tasks-content-cq60)
* [For AEM 6.1](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq610/product/pre-upgrade-tasks-content-cq61)
* [For AEM 6.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/product/pre-upgrade-tasks-content-cq62)

#### How to Use It

The `PreUpgradeTasksMBean` OSGI component comes preconfigured with a list of pre-upgrade maintenance tasks that can be run all at once. You can configure the tasks by following the below procedure:

1. Go to the Web Console by browsing to *http://serveraddress:serverport/system/console/configMgr*
1. Search for "preupgradetasks", then click on the first matching component. The full name of the component is `com.adobe.aem.upgrade.prechecks.mbean.impl.PreUpgradeTasksMBeanImpl`
1. `Modify the list of maintenance tasks that need to run as shown below:`

![](assets/chlimage_1.png) 

The task list differs depending on the run mode that is being used to start the instance. Below is a description of the run mode each maintenance task is designed for.

| **Task** |**Run Mode** |**OSGi Configuration** |
|---|---|---|
| `TarIndexMergeTask` |crx2 |- |
| `DataStoreGarbageCollectionTask` |crx2 |- |
| `WorkflowPurgeTask` |crx2/crx3 |Adobe Granite Workflow Purge Configuration |
| `ConsistencyCheckTask` |crx2 |- |
| `RevisionCleanupTask` |crx3 |- |
| `com.day.cq.audit.impl.AuditLogMaintenanceTask` |crx3 |Audit Log Purge Scheduler |
| `GenerateBundlesListFileTask` |crx2/crx3  |- |

>[!CAUTION]
>
><p><span class="code">DataStoreGarbageCollectionTask</span> is calling a Datastore Garbage Collection operation with the mark and sweep phase if used. For deployments that use a shared datastore make sure to either reconfigure it or properly or prepare the instance to avoid deletion of items referenced by another instance. This might require running the mark phase manually on all instances before triggering this pre-upgrade task.</p>

The `WorkflowPurgeTask` and `com.day.cq.audit.impl.AuditLogMaintenanceTask` tasks require a configuration and will not work without one. If they fail, the missing configuration is most likely the reason.

Therefore, make sure to add OSGI configuration for these tasks or remove them altogether from the pre-upgrade optimization tasks list if you do not wish to run them.

#### Default Configuration of the Pre-Upgrade Health Checks

The `PreUpgradeTasksMBeanImpl` OSGI component comes pre-configured with a list of pre-upgrade health check tags to execute when the `runAllPreUpgradeHealthChecks` method is called:

* **system** - the tag used by the granite maintenance health checks
* **pre-upgrade** - this is a custom tag that could be added to all the health checks that you can set to run before an upgrade

The list is editable. You can use the plus (+) and minus (-) buttons besides the tags to add more custom tags, or remove the default ones.

****

The managed bean functionality can be accessed using the [JMX Console](/content/help/en/experience-manager/6-4/sites/administering/using/jmx-console).

You can access the MBeans by:

1. Going to the JMX Console at *http://serveraddress:serverport/system/console/jmx*
1. Search for PreUpgradeTasks and click the result.
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
   <td>Checks if the <span class="code">runAllPreUpgradeTasks</span> maintenance task is currently running.</td> 
  </tr> 
  <tr> 
   <td><span class="code">getAnyPreUpgradeTaskRunning()</span></td> 
   <td>ACTION_INFO</td> 
   <td>Checks if any pre-upgrade maintenance task is currently running and returns an array containing the names of currently running tasks.</td> 
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
   <td><p>Runs all the pre-upgrade health checks and saves their status in a file named <span class="code">preUpgradeHCStatus.properties</span> that is located in the sling home path. If the <span class="code">shutDownOnSuccess</span> parameter is set to true, the AEM instance will be shut down, but only if all the pre-upgrade health checks have an OK status.</p> <p><br /> The properties file will be used as a precondition for any future upgrade and the upgrade process will be stopped if the pre-upgrade health check execution failed. If you want to ignore the result of the pre-upgrade health checks and launch the upgrade anyway, you can delete the file.</p> </td> 
  </tr> 
  <tr> 
   <td><span class="code">detectUsageOfUnavailableAPI(aemVersion)</span></td> 
   <td>ACTION</td> 
   <td>Lists all the imported packages that will no longer be satisfied when upgrading to the specified AEM version. The target AEM version must be given as parameter.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
><p>The MBean methods can be invoked via:</p> <ul> <li>The JMX Console</li> <li>Any external application that connects to JMX</li> <li>cURL</li> </ul>

### Pre-Upgrade Compatibility Checks

The pre-upgrade compatibility checks allow checking existing AEM instances for their upgradability by detecting APIs in use that are not compatible with 6.3 and might potentially break after upgrade. This could serve as an assessment of the development effort that might be involved in moving to the next version.

In order to use this feature, you need to install the latest version of the **pre-upgrade-tasks-content** content package on the instance you are upgrading *from*.

You can download the packages for AEM 6 versions by accessing the links provided [in this section](upgrade.md#main-pars_title_1185294582).

The checks can be invoked using the above described `PreUpgradeTasksMBean` MBean. 
![](assets/chlimage_1.png) 

The method to be invoked for the Pre Upgrade Compatibility check is `detectUsageOfUnavailableAPI` with the version you want to check against passed as a parameter, as shown here:
![](assets/chlimage_1.png) 

The list of imported packages and bundles that use incompatible APIs and will be unavailable after the upgrade will be returned in the response as shown below. The results will also be added to upgrade.log.

### Other Preparation Steps

Even though the upgrade process has been designed to be as simple as possible with the automation of many pre-upgrade tasks in 6.3, any upgrade of a production environment is a significant task and still requires some preparation steps to be performed manually. More specifically, we recommend you perform the items in this checklist before proceeding with the update:

1. Create a full backup on the instance that is going to be upgraded. For info on how to do this, consult the [Backup and Restore](/content/help/en/experience-manager/6-4/sites/administering/using/backup-and-restore) documentation.

1. Check the list of [obsolete bundles](/content/help/en/experience-manager/6-2/sites/deploying/using/obsolete-bundles) that will be uninstalled during the upgrade. If your custom applications depend on any of these bundles, contact Adobe Support and ask for compatibility packages for the affected area.

1. Run a test suite that validates your instance, including any custom applications. After the instance and the test suite have been validated, you can reuse the test suite later on in the process to validate the upgrade.

1. Make sure that any hostname based mappings under /etc/map (or any other similar configurations) are compatible with the environment in which you will be testing the upgraded instance.

1. Disable any custom authentication mechanisms. See the section under [Disabling Custom Login Modules](upgrade.md#main-pars_title_1651670167) for guidance on how to achieve this.

1. Prepare any upgrade customizations that might be required for your custom applications.

   >[!NOTE]
   >
   ><p>In case you have customized Assets content, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/upgrade.html#PreparingAssetsCustomizationsforUpgrade" >Preparing Assets Customizations for Upgrade</a>.</p> 

1. Archive then delete the log files found under `crx-quickstart/logs` in order to get a clean set of logs for the upgrade.

#### Disabling Custom Login Modules

>[!NOTE]
>
><p>This step is only required if you are upgrading from an AEM 5 version. It can be skipped entirely for upgrades from older AEM 6 versions.</p>

The way custom `LoginModules` are configured for authentication at the repository level has fundamentally changed in Apache Oak.

In AEM versions that used CRX2 configuration was placed in the repository.xml file, while from AEM 6 onwards it is done in the Apache Felix JAAS Configuration Factory service via the Web Console.

Therefore, any existing configurations will have to be disabled and re-created for Apache Oak after the upgrade.

To disable the custom modules defined in the JAAS configuration of *repository.xml*, you need to modify the configuration to make use of default `LoginModule`, as in this example:

```xml
<Security>
            ....
         <!--
                Use LoginModule authenticating against repository itself
                -->
                <LoginModule class="com.day.crx.core.CRXLoginModule">
                    <param name="anonymousId" value="anonymous"/>
                    <param name="adminId" value="admin"/>
                    <param name="disableNTLMAuth" value="true"/>
                    <param name="tokenExpiration" value="43200000"/>
                    <!-- param name="trust_credentials_attribute" value="d5b9167e95dad6e7d3b5d6fa8df48af8"/ -->
                </LoginModule>
        </Security>
```

>[!NOTE]
>
><p>For more information, see <a href="http://jackrabbit.apache.org/oak/docs/security/authentication/externalloginmodule.html">Authentication with the External Login Module</a>.</p> <p>For an example of LoginModule configuration in AEM 6, see <a href="/content/help/en/experience-manager/6-4/sites/administering/using/ldap-config.html">Configuring LDAP with AEM 6</a>.</p>

### Preparation of the AEM Quickstart jar file

Download the new AEM jar file and use it to replace the old one in the crx-quistart folder.

Next, verify that your Java Virtual Machine (JVM) and its parameters are appropriate for this new quickstart jar. Depending on your requirements or the deployment type, you will need to run a different version of the JVM that you used for your old CQ or AEM version, or use different JVM parameters.

### Content Repository Migration and Upgrade

Adobe provides a tool that can be used to migrate the repository to the new version of the Oak Segment Tar present in AEM 6.3. It is provided as part of the quickstart package.

This step is mandatory if you are upgrading from an older version of TarMK or want to switch the new Segment Tar from another type of persistence. For more information on what the benefits of the new Segment Tar are, see the [Migrating to Oak Segment Tar FAQ](revision-cleanup.md#MigratingtoOakSegmentTar).

The actual migration is performed using the standard AEM 6.3 quickstart jar file, executed with a new -x `crx2oak` option which executes the crx2oak tool in order to simplify the upgrade and make it more robust.

There are some prerequisites that need to be satisfied before running the migration:

#### Migration Prerequistes

* **Minimum Required Java version:** The migration tool only works with
* **Upgraded Instance:** If you are upgrading from a version **older than 5.4**, make sure you have performed an in-place upgrade to AEM 6.0 by following the procedure described above. For more information, see the [6.0 version of the Upgrade documentation](https://docs.adobe.com/content/docs/en/aem/6-0/deploy/upgrade.html).

The migration also requires the following helper jar versions:

* **1.0.8 or later** for crx2oak-quickstart-extension.jar
* **1.0.32 or later** for crx2oak.jar

If, as a consequence, you need to manually update these jars please check the *crx2oak-quickstart-extension.jar and crx2oak.jar* versions section.

Once these conditions are met, the exact procedure you need to follow is:

1. First, stop the instance if it is running.

1. Delete the old quickstart jar file and replace it with the new 6.3 one.

1. Unpack the new quickstart jar by running:

   ```xml
   java -Xmx4096m -jar aem-quickstart.jar -unpack
   ```

1. Start the repository migration. The command you need to run depends on the migration path you are following. Below is a list of all migration combinations and their associated commands:

   >[!CAUTION]
   >
   ><p>If you are performing the upgrade on a Windows system where Java memory mapping is not handled correctly, please add the&nbsp;<b>--disable-mmap </b>paramater to the below commands.</p> 
   **From AEM 5.6.x to TarMK:**

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile segment-fds
   ```

   **From AEM 5.6.x to MongoMK:**

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile mongo-from-crx2 -T mongo-uri=mongodb://mongo-host:mongo-port -T mongo-db=mongo-database-name
   ```

   Where:

    * **mongo-host **is the MongoDB server IP (for example, *127.0.0.1*)    
    * **mongo-port **is the MongoDB server port (for example:** ***27017*)    
    * **mongo-database-name** represents the name of the database (for example: *aem-author*)

   **From AEM 6.x with TarMK with File Data Store:**

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile segment-fds
   ```

   **From AEM 6.x with TarMK with custom Data Store:**

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile segment-custom-ds
   ```

   **From AEM 6.x with TarMK without Data Store:**

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar -v -x crx2oak -xargs -- --load-profile segment-no-ds
   ```

   For migrating instances using an **Amazon S3 Data Store**, please consult [this article](data-store-config.md#MigratingfromCRX2toCRX3withS3Datastore).

1. Check that your migration finished correctly by inspecting WARN and ERROR messages in the upgrade.log file located under **crx-quickstart/logs **in the AEM installation directory.

   >[!NOTE]
   >
   ><p>Packages in the&nbsp;install&nbsp;folder in the repository will be reinstalled after the upgrade. &nbsp;</p> <p>Because of this, make sure to not make any changes to the instance that might overlap with packages in that folder before the upgrade.</p> 

1. Start AEM to bring up the instance for the inplace upgrade.

   ```shell
   java -Xmx4096m -XX:MaxPermSize=2048m -jar aem-quickstart.jar 
   ```

   >[!NOTE]
   >
   ><p>The upgrade process will automatically take over the correct runmodes (install options) according to your migration profile, while also retaining the older valid ones. Therefore, there is no need for chaining install options when starting the instance after an upgrade - custom runmodes still need to be passed like before.</p> 

1. Check that the inplace upgrade finished correctly by again inspecting WARN and ERROR messages in the upgrade.log file located under **crx-quickstart/logs **in the AEM installation directory.

### Manually updating the helper JAR

The crx2oak helper JAR can be manually upgraded if needed, by manually replacing it with newer versions after unpacking the quickstart. Its location in the AEM installation folder is:

* &lt;aem-install&gt;/crx-quickstart/opt/extensions/crx2oak.jar

The newest version of the CRX2Oak migration tool is available for download from the Adobe Repository at this location:

* [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/crx2oak/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/crx2oak/)

When run, the `crx2oak-quickstart-extension.jar` will display its version and the SHA-1 checksum, together with the same information for the `crx2oak.jar`. If you manually upgrade these JARs and want to report bugs related to repository migration please provide the versions and SHA-1 checksums of the files that you used to support.

### Post Upgrade Check Automation

In the past, inspecting the post upgrade state of your instance required careful inspection of various logfiles, parts of the repository and the launchpad. Generating a post upgrade report can help detect defective upgrades before going live.

The main purpose of this feature is to reduce the need for manual interpretation or complex parsing logic across multiple endpoints required to qualify the success of an upgrade. The solution aims to provide unambiguous information for external automation systems to react on the success or the indentified failure of an update.

More specifically, it ensures that:

* Upgrade failures detected by the upgrade framework can are centralized in a single upgrade report;
* The upgrade report includes indicators about necessary manual intervention.

To accomodate this, changes have been made in the way logs are generated in the **upgrade.log** file.

Here is a sample report that show no errors during upgrade:
![](assets/chlimage_1.png) 

Here is a sample report that shows a bundle that was not installed during the upgrade process:
![](assets/chlimage_1.png) 

---

## Upgrading Steps for Application Server Installations

This section describes the procedure that needs to be followed in order to update AEM for Application Server installations.

All the examples in this procedure use JBoss as the Application Server and imply that you have a working version of AEM already deployed. The procedure is meant to document upgrades performed from **AEM** **version 5.6 to 6.3**

1. First, start JBoss. In most situations, you can do this by running the `standalone.sh` startup script, by running this command from the terminal:

   ```shell
   jboss-install-folder/bin/standalone.sh
   ```

   >[!NOTE]
   >
   ><p>For more information on JBoss tasks, see the <a href="http://jbossas.jboss.org/docs" >documentation</a> page.<br> </p> 

1. If AEM 5.6 is already deployed, check that the bundles are functioning correctly by running:

   ```shell
   wget http://<serveraddress:port>/cq/system/console/bundles
   ```

1. Next, undeploy AEM 5.6:

   ```shell
   rm jboss-install-folder/standalone/deployments/cq.war
   ```

1. Stop JBoss.

1. Now, migrate the repository using the crx2oak migration tool:

   ```shell
   java -jar crx2oak.jar crx-quickstart/repository/ crx-quickstart/oak-repository
   ```

   >[!NOTE]
   >
   ><p>In this example, <span class="code">oak-repository</span> is the <i>temporary</i> directory where the newly converted repository will reside.</p> <p>Before perfroming this step, make sure you have the latest <span class="code">crx2oak.jar</span> version.<br> </p> 

1. Delete the necessary properties in the `sling.properties` file by doing the following:

    1. Open the file located at `crx-quickstart/launchpad/sling.properties;`    
    1. Remove the following properties and save the file:

   ```xml
   sling.installer.dir
   felix.cm.dir
   granite.product.version
   org.osgi.framework.system.packages
   osgi-core-packages
   osgi-compendium-services
   jre-*
   sling.run.mode.install.options
   ```

1. Remove the files and folders that are no longer necessary. The items you need to specifically remove are:

    * The **launchpad/startup** folder. You can delete it by running the following command in the terminal:

   ```shell
   rm -rf crx-quickstart/launchpad/startup
   ```

    * The **base.jar** file:

   ```shell
   find crx-quickstart/launchpad -type f -name "org.apache.sling.launchpad.base.jar*" -exec rm -f {} \;
   ```

   The **BootstrapCommandFile_timestamp.txt** file:

   ```shell
   rm -f crx-quickstart/launchpad/felix/bundle0/BootstrapCommandFile_timestamp.txt
   ```

1. Copy the newly migrated segmentstore to its proper location:

   ```shell
   mv crx-quickstart/oak-repository/segmentstore crx-quickstart/repository/segmentstore
   ```

1. Copy the datastore as well:

   ```shell
   mv crx-quickstart/repository/repository/datastore crx-quickstart/repository/datastore
   ```

1. Next, you need to create the folder that will contain the OSGi configurations that will be used with the new upgraded instance.

   More specifically, a folder named `install` needs to be created under `crx-quickstart`.

1. Now, create the node store and data store that will be used with AEM 6.3.

   You can do this by creating two files with the following names under `crx-quickstart\install`:

    * `org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.config`    
    * `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.config`

   These two files will set AEM to use a TarMK node store and a File data store. 

1. Edit the configuration files to make them ready for use. More specifically:

   Add the following line to org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.config:

   ```xml
   customBlobStore=B"true"
   ```

   Then add the following lines to org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.config:

   ```xml
   path="./crx-quickstart/repository/datastore"
   minRecordLength=I"4096"
   ```

1. Remove the crx2 runmode by running:

   ```shell
   find crx-quickstart/launchpad -type f -name "sling.options.file" -exec rm -rf {} \;
   ```

1. You now need to change the run modes in the AEM 6.3 war file. In order to do that, first create a temporary folder that will be housing the AEM 6.3 war. The name of the folder in this example will be `temp`.

   Once the war file has been copied over, extract its contents by running from inside the `temp` folder:

   ```shell
   jar xvf aem-quickstart-6.3.0.war
   ```

1. Once the contents have been extracted, go to the `WEB-INF` folder and edit the `web.xml` file to change the run modes.

   To find the location where they are set in the XML, look for the `sling.run.modes` string. Once you find it, change the run modes in the next line of code, which by default is set to `author`:

   ```xml
   <param-value>author</param-value>
   ```

   Change the above `author` value and set the run modes to:

   `author,crx3,crx3tar`

   The final block of code should look like this:

   ```xml
   <init-param>
   <param-name>sling.run.modes</param-name>
   <param-value>author,crx3,crx3tar</param-value>
   </init-param>
   <load-on-startup>100</load-on-startup>
   </servlet>
   ```

1. Recreate the jar with the modified contents:

   ```xml
   jar cvf aem62.war
   ```

1. Finally, deploy the new war file:

   ```xml
   cp temp/aem62.war jboss-install-folder/standalone/deployments/aem61.war
   ```

---

## Upgrading Assets

This section describes how to upgrade assets from an earlier version of AEM:

* If you are upgrading from a version earlier than AEM 6.2, you need to [prepare asset customizations for upgrade](#PreparingAssetCustomizationsforUpgrade).
* Existing assets need to have an asset ID. See [Generating Asset IDs for Existing Assets](#GeneratingAssetIDsforExistingAssets).

>[!NOTE]
>
><p>If you have made any InDesign Script customizations, they will <b>not</b> be preserved after upgrade.</p>

### Preparing Assets Customizations for Upgrade

>[!NOTE]
>
><p>This procedure is required only for upgrades from versions older than AEM 6.2.</p>

Instances that have customized Assets deployments need to be prepared for the upgrade. This is needed to ensure that all customized content is compatible with the new 6.3 node structure.

You can prepare the Assets content by doing the following:

1. On the instance that needs to be upgraded, open CRXDE Lite by going to `http://server:port/crx/de/index.jsp`

1. Go to the following node:

    * `/apps/dam/content`

1. Rename the `content` node to `content_backup`. You can do this by right clicking the explorer pane in the left hand side of the window and choosing **Rename**.

1. Once the node has been renamed, create a new node named content under `/apps/dam` named `content` and set its node type to `**sling:Folder**`.

1. Move all the children nodes of `content_backup` to the newly created `content` node. You can do this by right clicking each children node in the explorer pane and selecting **Move**.

1. Delete the ** `content_backup`** node.

### Generating Asset IDs for Existing Assets

To generate asset IDs for existing assets, upgrade the assets when you upgrade your AEM instance to run AEM 6.3. This is required to enable the [Assets Insights](/content/help/en/experience-manager/6-4/assets/using/touch-ui-asset-insights) feature. For more details, see [Adding Embed code](/content/help/en/experience-manager/6-4/assets/using/touch-ui-using-page-tracker#main-pars_title_1017167766).

To upgrade assets, configure the Associate Asset IDs package in the JMX console. Depending on the number of assets in the repository, `migrateAllAssets` may take a long time (roughly an hour for 125k assets on TarMK).
![](assets/chlimage_1.png) 

If you require asset IDs for a subset of your entire assets, use the `migrateAssetsAtPath` API.

For all other purposes, use the `migrateAllAsset`s() API.

---

## Upgrading AEM Communities

If the site being upgraded used the social communities capability, then visit [Upgrading to AEM Communities 6.2](/content/help/en/experience-manager/6-4/communities/using/upgrade) for additional upgrade information.

---

## Upgrading Custom Search Forms

Custom Search Facets require some manual adjustments after the upgrade in order to function properly. For more details, see [Upgrading Custom Search Forms](upgrading-custom-search-forms.md).

---

## Analyzing Issues With The Upgrade

This section contains some issue scenarios one might face along the upgrade procedure to AEM 6.3.

These scenarios should help to track down the root cause of issues related to ugprade and should help to identify project or product specific issues.

### Repository Migration Failing

The data migration from CRX2 to Oak should be feasible for any scenario starting with Source Instances based on CQ 5.4. Make sure that you exactly follow the upgrade instructions in this document which include the preparation of the `repository.xml`, making sure no custom custom authenticator is started via JAAS and the instance has been checked for inconsistencies before starting the migration.

If the migration still fails you can figure out what is the root cause by inspecting the `upgrade.log`. If the issue is not yet known, please report it to Customer Support.

### Packages and Bundles Fail to Update

In case packages fail to install during the upgrade, the bundles they contain will not be updated either.

This category of issues is usually caused by data store misconfiguration. They will also appear as **ERROR** and **WARN** messages in the `error.log`.

Since in most of these cases the default login may fail to work, you can use CRXDE directly in order to inspect and find the configuration problems.

### Some AEM Bundles are not switching to the active state

In case of bundles not starting up you should check for any unsatisfied dependencies.

In case this problem is present but it is based on a failed package installation which led to bundles not being upgrade they will be deemed incompatible for the new version. For more info on how to troubleshoot this, see [Packages and Bundles Fail to Update](upgrade.md#main-pars_title_1343403928) above.

It is also recommended to compare the bundle list of a fresh AEM 6.3 instance with the upgraded one to detect the bundles that where not upgraded. This will provide a closer scope of what to search for in the `error.log`.

### Custom Bundles not switching to the active state

In case your custom bundles are not switching to the active state it is most likely that there is code that is not importing change API. This will most often lead to unsatisfied dependencies.

API that was removed should be marked as deprecated in one of the pervious releases. You might find instructions about a direct migration of your code in this deprecation notice. Adobe aims for semantic versioning where possible so the versions can indicate breaking changes.

It is also best to check if the change that has caused the problem was absolutely necesarry necessary and revert it if it is not. Also check if the version increase of the package export was increased more than necessary, following strict semantic versioning.

>[!NOTE]
>
><p>The declaration of <span class="code">ConsumerType</span> versus <span class="code">ProviderType</span> does make a difference for the usage of the Maven Baseline Plugin. In case of <span class="code">ProviderType</span> API that was not declared properly, adding methods can lead to the missleading recommendation to bump the major version. Because of this, you can also look out for missing <span class="code">@ProviderType</span> annotations.</p>

### Malfunctioning Platform UI

In case of certain UI functionality that is not working properly after the upgrade, you should first check for custom overlays of the interface. Some structures might have changed and the overlay might need an update or is obsolete.

Next, check for any Javascript errors that can be tracked down to custom added extensions that are hooked to clientlibs. The same can apply for custom CSS that might be causing problems to the AEM layout.

Finally, check for misconfiguration that Javascript might not be able to deal with. This is usually the case with improperly deactivated extensions.

### Malfunctioning custom components, templates or UI extensions

In most cases, the root causes for these issues are the same as for bundles that are not started or packages not being installed with the only difference that the issues start occurng when first using the components.

The way to deal with erroneous custom code is to first perfom smoke tests in order to identify the cause. Once you find it, look at the recommendations in [this](upgrade.md#main-pars_title_1162686418) section of the article for ways of fixing them.

### Analyzing the error.log and upgrade.log

In most situations the logs need to be consulted for errors in order to find the cause of a problem. However, in case of upgrades it is also necessary to monitor dependency issues as old bundles might not be upgraded properly.

The best way to do this is to strip down the error.log by removing of all messages that are expected to be unrelated to the issue you are facing. You can do this via tool like grep, by using:

```xml
grep -v UnrelatedErrorString
```

Some error messages might not be immediately explicative. In this case, looking at the context in which they occur can also help understand where the error was created. You can separate the error using:

* `grep -B` for adding lines before the error;

or

* `grep -A` for adding lines after.

In a few cases errors can also be found WARN messages as there can be valid cases leading to this state and the application is not always able to decide if this is an actual error. Make sure you consult these messages as well.
