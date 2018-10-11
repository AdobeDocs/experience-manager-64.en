---
title: Storage Elements in AEM 6.4
seo-title: Storage Elements in AEM 6.4
description: null
seo-description: Learn about the node storage implementations available in AEM 6.4 and how to maintain the repository.
uuid: 9c42320f-cdfc-4c78-b34c-a4fef458b0bf
content-encoding: UTF-8
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/storage-elements-in-aem-6
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-10T08 18 35.707-0400
cq-lastmodifiedby: raiman
cq-lastreplicated: 2018-07-10T08 18 35.759-0400
cq-lastreplicatedby: raiman
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 3eb29f2f-a5db-41fa-a546-dd244a5c37a0
firstPublishExternalDate: 2017-10-31T16:17:34.574-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 03 25.429-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-07-10T08:18:35.696-0400
legacypath: /content/docs/en/aem/6-0/deploy/upgrade/microkernels-in-aem-6-0
lochandoffdate: 2018-04-30T03 29 10.055-0400
lr-lastreplicatedby: raiman@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Storage Elements in AEM 6.4
publishexternaldate: 2018-07-10T08 18 35.696-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/storage-elements-in-aem-6.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/platform/storage-elements-in-aem-6
sha1: 93f31fef681635196adfa4b48e6642156beaf9ba
topicBrowsingSortDate: 2018-07-10T08:18:35.696-0400
index: y
internal: n
snippet: y
translate: y
---

# Storage Elements in AEM 6.4

In this article, we will cover:

* [Overview of Storage in AEM 6](storage-elements-in-aem-6.md#main-pars_title)
* [Maintaining the Repository](storage-elements-in-aem-6.md#main-pars_title_4)

## Overview of Storage in AEM 6
One of the most important changes in AEM 6 are the innovations at the repository level.

Currently, there are two node storage implementations available in AEM6: Tar storage, and MongoDB storage.

### Tar Storage

#### Running a freshly installed AEM instance with Tar Storage

>[!CAUTION]
>
>The PID for the Segment node store has changed from org.apache.jackrabbit.oak.**plugins**.segment.SegmentNodeStoreService in previous versions of AEM 6 to org.apache.jackrabbit.oak.segment.SegmentNodeStoreService in AEM 6.3. Make sure you make the necessary configuration adjustments to reflect this change.

By default, AEM 6 uses the Tar storage to store nodes and binaries, using the default configuration options. To manually configured its storage settings, follow the below procedure:

1. Download the AEM 6 quickstart jar and place it in a new folder.
1. Unpack AEM by running:

   `java -jar cq-quickstart-6.jar -unpack`

1. Create a folder named `crx-quickstart\install` in the installation directory.  

1. Create a file called `org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.cfg` in the newly created folder.  

1. Edit the file and set the configuration options. The following options are available for Segment Node Store, which is the basis of AEM's Tar storage implementation:

    * `repository.home`: Path to repository home under which various repository related data is stored. By default segment files would be stored under the crx-quickstart/segmentstore directory.
    * `tarmk.size`: Maximum size of a segment in MB. The default is 256MB.

1. Start AEM.

### Mongo Storage

#### Running a freshly installed AEM instance with Mongo Storage
AEM 6 can be configured to run with MongoDB storage by following the below procedure:

1. Download the AEM 6 quickstart jar and place it into a new folder.
1. Unpack AEM by running the following command:

   `java -jar cq-quickstart-6.jar -unpack`

1. Make sure that MongoDB is installed and an instance of `mongod` is running. For more info, see [Installing MongoDB](http://docs.mongodb.org/manual/installation/).
1. Create a folder named `crx-quickstart\install` in the installation directory.
1. Configure the node store by creating a configuration file with the name of the configuration you want to use in the `crx-quickstart\install` directory.

   The Document Node Store (which is the basis for AEM's MongoDB storage implementation) uses a file called `org.apache.jackrabbit.oak.plugins.document.DocumentNodeStoreService.cfg`

1. Edit the file and set your configuration options. The following options are available:

    * `mongouri`: The [MongoURI](http://docs.mongodb.org/manual/reference/connection-string/) required to connect to Mongo Database. The default is `mongodb://localhost:27017`  
    
    * `db`: Name of the Mongo database. By default new AEM 6 installations use **aem-author** as the database name.  
    
    * `cache`: The cache size in MB. This is distributed among various caches used in DocumentNodeStore. The default is 256  
    
    * `changesSize`: Size in MB of capped collection used in Mongo for caching the diff output. The default is 256  
    
    * `customBlobStore`: Boolean value indicating that a custom data store will be used. The default is false.

1. Create a configuration file with the PID of the data store you wish to use and edit the file in order to set the configuration options. For more info, please see [Configuring Node Stores and Data Stores](data-store-config.md).  

1. Start the AEM 6 jar with a MongoDB storage backend by running:

   ```shell
   java -jar cq-quickstart-6.jar -r crx3,crx3mongo
   ```

   Where **`-r`** is the backend runmode. In this example, it will start with MongoDB support.

## Maintaining the Repository
Each update to the repository creates a new content revision. As a result, with each update the size of the repository grows. To avoid uncontrolled repository growth, old revisions need to be be cleaned up to free disk resources. This maintenance functionality is called Revision Cleanup. The Revision Cleanup mechanism will reclaim disk space by removing obsolete data from the repository. For further details about Revision Cleanup, read the [Revision Cleanup page](revision-cleanup.md).

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-0436B4A35714BFF67F000101@AdobeID)
Last Modified Date: 2017-11-30T05:42:41.816-0500

<p>All the offline revision cleanup content is now included in the new Revision Cleanup page (see the link above).</p>

 -->

As data is never overwritten in a tar file, the disk usage increases even when only updating existing data. To make up for the growing size of the repository, AEM employs a garbage collection mechanism called **Revision Cleanup**. The mechanism will reclaim disk space by removing obsolete data from the repository, and has three phases: **estimation**, **compaction**, **cleanup**. In the past the revision cleanup was often referenced as **compaction**.

The are two ways of performing revision cleanup:

1. [Offline Revision Cleanup](storage-elements-in-aem-6.md#PerformingOfflineRevisionCleanup)
1. [Online Revision Cleanup](storage-elements-in-aem-6.md#PerformingOnlineRevisionCleanup)

**Offline revision cleanup is the recommended and supported way of performing revision cleanup.**

### Choosing the Type of Revision Cleanup
**For AEM 6.2 Publish instances**

Offline revision cleanup is the recommended way of cleaning up revisions. This requires to shut down the instances in order to run offline revision cleanup during non business hours.

If downtimes are not possible, customers can contact Adobe Support to evaluate additional options:

1. If there is more than one publish instance, one can be taken down for offline revision cleanup while avoiding replication from author. After a successful revision cleanup, the instance can be taken back into production while a clone of the clean instance would replace other remaining production ones.
1. If the above is still not possible, online revision cleanup can be used under the terms and conditions of the program. This type of cleanup has **restricted** support in AEM 6.2.

**For AEM 6.2 Author instances**

Offline revision cleanup is the recommended way of cleanup for author instances as well. However, in rare cases where downtime is not possible either beacause maintenance windows were not foreseen and can have the same business impact as system outages, customers should contact Adobe Support to evaluate additional options. The additional options for performing cleanup on author instances are the same as the ones described above for publish instances.

>[!NOTE]
>
>For more information about the revision cleanup process, see the [Frequently Asked Questions](storage-elements-in-aem-6.md#RevisionCleanupFrequentlyAskedQuestions).

### Performing Offline Revision Cleanup

>[!CAUTION]
>
>Different versions of the Oak-run tool need to be used depending on the Oak version you use with your AEM installation. Please check the version requirements list below before using the tool:
>
>* For Oak versions **1.0.0 through 1.0.11 **or** 1.1.0 through 1.1.6**, use Oak-run version** 1.0.11**
>
>* For Oak versions **newer than the above**, use the version of Oak-run that matches the Oak core of your AEM installation.
>

Adobe provides a tool called **Oak-run** for performing revision cleanup. It can be downloaded at the following location:

[https://repo1.maven.org/maven2/org/apache/jackrabbit/oak-run/](https://repo1.maven.org/maven2/org/apache/jackrabbit/oak-run/)

The tool is a runnable jar that can be manually run to compact the repository. The process is called offline revision cleanup because the repository needs to be shut down in order to properly run the tool. Make sure to plan the cleanup in accordance with your maintenance window.

For tips on how to increase the performance of the cleanup process, see [Increasing the Performance of Offline Revision Cleanup](storage-elements-in-aem-6.md#PerformanceTuningandMaintenanceRecommendations1416769121).

>[!NOTE]
>
>You can also clear old checkpoints before the maintenance takes place (steps 2 and 3 in the procedure below). This is recommended only for instances that have more than 100 checkpoints.

The procedure to run the tool is:

1. Always make sure you have a recent backup of the AEM instance.

   Shut down AEM.

1. (Optional) Use the tool to find old checkpoints:

   ```xml
   java -jar oak-run.jar checkpoints install-folder/crx-quickstart/repository/segmentstore
   
   ```

1. (Optional) Then, delete the unreferenced checkpoints:

   ```java
   java -jar oak-run.jar checkpoints install-folder/crx-quickstart/repository/segmentstore rm-unreferenced
   ```

1. Run the compaction and wait for it to complete:

   ```java
   java -jar oak-run.jar compact install-folder/crx-quickstart/repository/segmentstore
   ```

### Increasing the Performance of Offline Revision Cleanup
Since version **1.0.22**, the oak-run tool introduces several features with an aim to increase the performance of the revision cleanup process and minimize the maintenance window as much as possible.

The list includes several command line parameters, as described below:

* `-Dtar.memoryMapped`. Use this to enable memory mapped operations for tar file to greatly increase performance. You can set this as `true` or `false`. It is highly recommended you enable this feature in order to speed up compaction.  

* `-Dupdate.limit`. Defines the threshold for the flush of a temporary transaction to disk. The default value is `5000000`.  

* `-Dcompress-interval`. Number of compaction map entries to keep until compressing the current map. The default is `1000000`. You should increase this value to an even higher number for faster throughput, if enough heap memory is available.

* `-Dcompaction-progress-log`. The number of compacted nodes that will be logged. The default value is `1500000`,** **which means that the first 1500000 compacted nodes will be logged during the operation. Use this in conjunction with the next parameter documented below.

* `-Dlogback.configurationFile`. Use a configuration file for logging. You can use the below configuration file to enable the logging of the nodes that are being compacted:

    * [logback.xml](logback.md)

* **`-Dtar.PersistCompactionMap.` **Set this parameter to `true` to use disk space instead of heap memory for compaction map persistance. Requires the oak-run tool **versions 1.4** and higher. For further details also see question 6 in the [FAQ section](storage-elements-in-aem-6.md#RevisionCleanupFrequentlyAskedQuestions).

>[!CAUTION]
>
>Memory mapped file operations do not work correctly on some versions of Windows. Make sure that you use the tool without the `-Dtar.memoryMapped` parameter on Windows platforms, otherwise the revision cleanup will fail.

An example of the parameters in use:

```shell
java -Dtar.memoryMapped=true -Dupdate.limit=5000000 -Dcompress-interval=10000000 -Dcompaction-progress-log=1500000 -Dlogback.configurationFile=logback.xml -Xmx8g -jar oak-run-*.jar checkpoints <repository>
```

>[!NOTE]
>
>Use as much heap memory as possible for faster I/O operations. It is recommended you use at least eight gigabytes for most common deployments.

### Performing Online Revision Cleanup

>[!CAUTION]
>
>Online Revision Cleanup is present in AEM 6.2 under **restricted** support. For more information on the conditions and terms of using the feature, please contact [Adobe Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html).

For situations where the AEM cannot be shut down for maintenance, revision cleanup can also be performed while the instance is running.

You can perform Online revision cleanup by doing the following:

1. Go to the folder where AEM is installed, then browse to `crx-quickstart\install` (create the folder if it does not exist).
1. Create or open the `org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.config` file.
1. Add the following line to the configuration file:

   ```xml
   pauseCompaction=B "false"
   ```

   A correct configuration file should look like this:

   ```xml
   repository.home=${repository.home}/segmentstore
   tarmk.size=256
   pauseCompaction=false
   ```

1. Restart AEM.
1. Go to the JMX console by pointing your browser to `http://server:port/system/console/jmx`
1. Search for **CompactionStrategy** and click the MBean that shows up in the search.
1. Next, verify that the value for **PausedCompaction** is set to `false`. This confirms that online revision cleanup is set to run:

   ![](assets/storage-elements-in-aem-6/chlimage_1.png)

   Online revision cleanup is now scheduled to run as part of the tasks performed in the Daily Maintenance Window. For more info, see [Automated Maintenance Tasks](/content/help/en/experience-manager/6-4/sites/administering/using/operations-dashboard#main-pars_title_15).

1. Next, verify if Online revision cleanup is running properly. You can do this by first going to the Operations Dashboard and checking what is the time interval configured for the **Daily Maintenance Window. **By default, it is scheduled to run between 2 and 5 AM.  

1. Now, inspect the **error.log** file for events logged during the time of the daily maintenance window to see if the online revision cleanup ran correctly.

   >[!NOTE]
   >
   >Before checking the logs, note that the revision cleanup will not be completed if the calculated disk space gain is less than 10 percent of the entire repository size.

   This is an example of the log entries that will be generated if the revision cleanup was not run because the gain is less than 10 percent:

   ```xml
   16.03.2015 02:00:13.736 *INFO* [TarMK compaction thread [/author/crx-quickstart/repository/segmentstore], active since Mon Mar 16 02:00:13 EDT 2015, previous max duration 58249ms] org.apache.jackrabbit.oak.plugins.segment.file.FileStore TarMK compaction started 16.03.2015 02:00:30.001 *INFO* [pool-9-thread-2] com.adobe.granite.taskmanagement.impl.jcr.TaskArchiveService archiving tasks at: 'Mon Mar 16 02:00:30 EDT 2015'
   16.03.2015 02:01:06.325 *INFO* [TarMK compaction thread [/author/crx-quickstart/repository/segmentstore], active since Mon Mar 16 02:00:13 EDT 2015, previous max duration 58249ms] org.apache.jackrabbit.oak.plugins.segment.file.FileStore Estimated compaction in 52.59 s, gain is 9% (1028524544/1137660928) or (1.0GB/1.1 GB), so skipping compaction for now
   ```

   This an example of the log entries that will be generated if the revision cleanup is going to be run because the gain is higher than 10 percent:

   ```xml
   19.03.2015 02:00:10.230 *INFO* [TarMK compaction thread [/author/crx-quickstart/repository/segmentstore], active since Thu Mar 19 02:00:10 EDT 2015, previous max duration 1369831ms] org.apache.jackrabbit.oak.plugins.segment.file.FileStore TarMK compaction started
   19.03.2015 02:00:30.441 *INFO* [pool-9-thread-2] com.adobe.granite.taskmanagement.impl.jcr.TaskArchiveService archiving tasks at: 'Thu Mar 19 02:00:30 EDT 2015'
   19.03.2015 02:01:01.699 *INFO* [TarMK compaction thread [/author/crx-quickstart/repository/segmentstore], active since Thu Mar 19 02:00:10 EDT 2015, previous max duration 1369831ms] org.apache.jackrabbit.oak.plugins.segment.file.FileStore Estimated compaction in 51.47 s, gain is 69% (1018859520/3343598080) or (1.0 GB/3.3 GB), so running compaction
   ```

   Lastly, these are the log entry generated when the revision cleanup has successfully completed:

   ```xml
   19.03.2015 02:22:52.638 *INFO* [TarMK compaction thread [/author/crx-quickstart/repository/segmentstore], active since Thu Mar 19 02:00:10 EDT 2015, previous max duration 1369831ms] org.apache.jackrabbit.oak.plugins.segment.file.FileStore TarMK compaction completed in 1310939ms
   ```

## Additional Methods of Triggering Revision Cleanup

### Triggering Revision Cleanup from the Operations Dashboard
The automatic revision cleanup can be triggered manually in the Operations Dashboard via a maintenance job called **Revision Clean Up**.

To start Revision Clean Up you need to:

1. Go to the AEM Welcome Screen.
1. In the main AEM window, go to **Tools - Operations - Dashboard - Maintenance** or directly browse to [http://localhost:4502/libs/granite/operations/content/maintenance.html](http://localhost:4502/libs/granite/operations/content/maintenance.html)
1. Click on **Daily Maintenance Window.**
1. Hover over the **Revision Clean Up** window and press the **Start **button.

![](assets/storage-elements-in-aem-6/chlimage_1-1.png)

The icon will turn orange to indicate that the Revision Clean Up job is running. You can stop it at any time by hovering the mouse over the icon and pressing the **Stop** button:

![](assets/storage-elements-in-aem-6/chlimage_1-2.png) 

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-0436B4A35714BFF67F000101@AdobeID)
Last Modified Date: 2017-11-30T05:42:42.921-0500

<p>As discussed with Peter Klassen we will hide all information about running Online Revision Cleanup in 6.2 and we will only keep the warning.</p>

 -->

### Invoking Revision Garbage Collection via the JMX Console

1. Open the JMX Console by going to [http://localhost:4502/system/console/jmx](http://localhost:4502/system/console/jmx)
1. Click the **RevisionGarbageCollection** MBean.
1. In the next window, click **startRevisionGC()** and then **Invoke** to start the Revision Garbage Collection job.

>[!NOTE]
>
>Due to the mechanics of the garbage collection, the first run will actually add 256 MB of disk space. Subsequent runs will work as expected and start shrinking the repository size.

## Performance Tuning and Maintenance Recommendations
Follow the below recommendations in order to maintain maximum efficiency while upkeeping the repository:

1. Make sure you run [Offline Revision Cleanup](storage-elements-in-aem-6.md#main-pars_title_42551947) whenever possible during scheduled maintenance hours;
1. If you are using an external data store, make sure you run [Data Store Garbage Collection](/content/help/en/experience-manager/6-4/sites/administering/using/data-store-garbage-collection) after revision cleanup has been completed.
1. Follow the recommendations in [this knowledgebase article](https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html) for tips on improving the performance of your AEM instance.

## Revision Cleanup Frequently Asked Questions
1. When to use Offline Revision Cleanup as opposed to Online Revision Cleanup?

* See [Choosing the Type of Revision Cleanup.](/content/docs/en/aem/6-3/deploy/platform/storage-elements-in-aem-6-2#Choosing%20the%20Type%20of%20Revision%20Cleanup)

2. How frequently should Offline Revision Cleanup be performed?

* It depends on the repository growth rate. As a general rule of thumb, for average content repositories, it is recommended that you perform revision cleanup every 2 weeks for an author instance, and once per quarter for a publish instance.

3. What are the factors that determine the duration of the Offline Revision Cleanup?

* The repository size and the amount of revisions that need to be cleaned up determines the duration of the cleanup.

4. What's the worst that can happen if you do not perform revision cleanup?

* The AEM instance will run out of disk space, which will cause outages in production. It is highly recommended that you follow the monitoring best practices as mentioned in the [Managing Projects - Best Practices](/content/help/en/experience-manager/6-4/managing/using/best-practices); see the [Managing Projects Best Practices Glossary for specific monitoring tasks](/content/help/en/experience-manager/6-4/managing/using/best-practices-glossary), with further details also available under [Monitoring and Maintaining your Instance](monitoring-and-maintaining.md).

5. What is the difference between a revision and a page version?

* **Oak revision:** Oak organizes all the content in a large tree hierarchy that consists of nodes and properties. Each snapshot or revision of this content tree is immutable, and changes to the tree are expressed as a sequence of new revisions. Typically, each content modification triggers a new revision. See also [http://jackrabbit.apache.org/dev/ngp.html](http://jackrabbit.apache.org/dev/ngp.html).

* **Page Version:** Versioning creates a "snapshot" of a page at a specific point in time. Typically, a new version is created when a page is activated. For more information, see [Working with Page Versions](/content/help/en/experience-manager/6-4/sites/authoring/using/working-with-page-versions).

6. How to speed up the Offline Revision Cleanup task if it does not complete within 8 hours ?

* If the revision task does not complete within 8 hours and the [thread dumps](/content/help/en/experience-manager/6-4/sites/administering/using/operations-dashboard#Diagnosistools) reveal that the main hotspot is `InMemoryCompactionMap.findEntry`, use the following parameter with the oak-run tool **versions 1.4 **or higher: -Dtar.PersistCompactionMap=true. See also [Performing Offline Revision Cleanup](storage-elements-in-aem-6.md#PerformingOfflineRevisionCleanup) and [Increasing the Performance of Offline Revision Cleanup](storage-elements-in-aem-6.md#IncreasingthePerformanceofOfflineRevisionCleanup).

