---
title: Storage Elements in AEM 6.4
seo-title: Storage Elements in AEM 6.4
description: Learn about the node storage implementations available in AEM 6.4 and how to maintain the repository.
seo-description: Learn about the node storage implementations available in AEM 6.4 and how to maintain the repository.
uuid: 56d1274f-aeeb-442a-95b3-695b8c72749a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 9914a41e-3351-4f76-afe9-004668c3c5ad
legacypath: /content/docs/en/aem/6-0/deploy/upgrade/microkernels-in-aem-6-0
index: y
internal: n
snippet: y
---

# Storage Elements in AEM 6.4{#storage-elements-in-aem}

In this article, we will cover:

* [Overview of Storage in AEM 6](../../../sites/deploying/using/storage-elements-in-aem-6.md#main-pars-title)
* [Maintaining the Repository](../../../sites/deploying/using/storage-elements-in-aem-6.md#main-pars-title-4)

## Overview of Storage in AEM 6 {#overview-of-storage-in-aem}

One of the most important changes in AEM 6 are the innovations at the repository level.

Currently, there are two node storage implementations available in AEM6: Tar storage, and MongoDB storage.

### Tar Storage {#tar-storage}

#### Running a freshly installed AEM instance with Tar Storage {#running-a-freshly-installed-aem-instance-with-tar-storage}

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

### Mongo Storage {#mongo-storage}

#### Running a freshly installed AEM instance with Mongo Storage {#running-a-freshly-installed-aem-instance-with-mongo-storage}

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

1. Create a configuration file with the PID of the data store you wish to use and edit the file in order to set the configuration options. For more info, please see [Configuring Node Stores and Data Stores](../../../sites/deploying/using/data-store-config.md).  

1. Start the AEM 6 jar with a MongoDB storage backend by running:

   ```shell
   java -jar cq-quickstart-6.jar -r crx3,crx3mongo
   ```

   Where **`-r`** is the backend runmode. In this example, it will start with MongoDB support.

#### Disabling Transparent Huge Pages {#disabling-transparent-huge-pages}

Red Hat Linux uses a memory management algorithm called Transparent Huge Pages (THP). While AEM performs fine-grained reads and writes, THP is optimized for large operations. Because of this, it is recommended that you disable THP both on Tar and Mongo storage. To disable the algorithm, follow these steps:

1. Open the `/etc/grub.conf` file in the text editor of your choice.
1. Add the following line to the **grub.conf** file:

   ```
   transparent_hugepage=never
   ```

1. Finally, check if the setting has taken effect by running:

   ```
   cat /sys/kernel/mm/redhat_transparent_hugepage/enabled
   ```

   If THP is disabled, the output of the above command should be:

   ```
   always madvise [never]
   ```

>[!NOTE]
>
>Addtionally, you can also consult the following resources:
>
>* For more information regarding Transparent Huge Pages on Red Hat Linux, see this [article](https://access.redhat.com/solutions/46111).
>* For Linux tuning tips, see this [article](https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html).
>

## Maintaining the Repository {#maintaining-the-repository}

Each update to the repository creates a new content revision. As a result, with each update the size of the repository grows. To avoid uncontrolled repository growth, old revisions need to be be cleaned up to free disk resources. This maintenance functionality is called Revision Cleanup. The Revision Cleanup mechanism will reclaim disk space by removing obsolete data from the repository. For further details about Revision Cleanup, read the [Revision Cleanup page](../../../sites/deploying/using/revision-cleanup.md).

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-0436B4A35714BFF67F000101@AdobeID)
Last Modified Date: 2017-11-30T05:42:41.816-0500
<p>All the offline revision cleanup content is now included in the new Revision Cleanup page (see the link above).</p>
-->

<!--
Comment Type: draft

<p>As data is never overwritten in a tar file, the disk usage increases even when only updating existing data. To make up for the growing size of the repository, AEM employs a garbage collection mechanism called <strong>Revision Cleanup</strong>. The mechanism will reclaim disk space by removing obsolete data from the repository, and has three phases: <strong>estimation</strong>, <strong>compaction</strong>, <strong>cleanup</strong>. In the past the revision cleanup was often referenced as <strong>compaction</strong>.</p>
<p>The are two ways of performing revision cleanup:</p>
<ol>
<li><a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#performingofflinerevisioncleanup">Offline Revision Cleanup</a></li>
<li><a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#performingonlinerevisioncleanup">Online Revision Cleanup</a></li>
</ol>
<p><strong>Offline revision cleanup is the recommended and supported way of performing revision cleanup.</strong> <br /> </p>
-->

<!--
Comment Type: draft

<h3>Choosing the Type of Revision Cleanup</h3>
-->

<!--
Comment Type: draft

<p><strong><u>For AEM 6.2 Publish instances</u></strong><br /> </p>
<p>Offline revision cleanup is the recommended way of cleaning up revisions. This requires to shut down the instances in order to run offline revision cleanup during non business hours.</p>
<p>If downtimes are not possible, customers can contact Adobe Support to evaluate additional options:</p>
<ol>
<li>If there is more than one publish instance, one can be taken down for offline revision cleanup while avoiding replication from author. After a successful revision cleanup, the instance can be taken back into production while a clone of the clean instance would replace other remaining production ones.</li>
<li>If the above is still not possible, online revision cleanup can be used under the terms and conditions of the program. This type of cleanup has <strong>restricted</strong> support in AEM 6.2.<br /> </li>
</ol>
<p><strong><u>For AEM 6.2 Author instances</u></strong></p>
<p>Offline revision cleanup is the recommended way of cleanup for author instances as well. However, in rare cases where downtime is not possible either beacause maintenance windows were not foreseen and can have the same business impact as system outages, customers should contact Adobe Support to evaluate additional options. The additional options for performing cleanup on author instances are the same as the ones described above for publish instances.<br /> </p>
-->

<!--
Comment Type: draft

<note type="note">
<p>For more information about the revision cleanup process, see the <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#revisioncleanupfrequentlyaskedquestions">Frequently Asked Questions</a>.</p>
</note>
-->

<!--
Comment Type: draft

<h3>Performing Offline Revision Cleanup</h3>
-->

<!--
Comment Type: draft

<note type="caution">
<p>Different versions of the Oak-run tool need to be used depending on the Oak version you use with your AEM installation. Please check the version requirements list below before using the tool:</p>
<ul>
<li>For Oak versions <strong>1.0.0 through 1.0.11 </strong>or<strong> 1.1.0 through 1.1.6</strong>, use Oak-run version<strong> 1.0.11</strong></li>
<li>For Oak versions <strong>newer than the above</strong>, use the version of Oak-run that matches the Oak core of your AEM installation.</li>
</ul>
</note>
-->

<!--
Comment Type: draft

<p>Adobe provides a tool called <strong>Oak-run</strong> for performing revision cleanup. It can be downloaded at the following location:</p>
<p><a href="https://repo1.maven.org/maven2/org/apache/jackrabbit/oak-run/">https://repo1.maven.org/maven2/org/apache/jackrabbit/oak-run/</a></p>
<p>The tool is a runnable jar that can be manually run to compact the repository. The process is called offline revision cleanup because the repository needs to be shut down in order to properly run the tool. Make sure to plan the cleanup in accordance with your maintenance window.</p>
<p>For tips on how to increase the performance of the cleanup process, see <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#performancetuningandmaintenancerecommendations1416769121">Increasing the Performance of Offline Revision Cleanup</a>.</p>
<p> </p>
-->

<!--
Comment Type: draft

<note type="note">
<p>You can also clear old checkpoints before the maintenance takes place (steps 2 and 3 in the procedure below). This is recommended only for instances that have more than 100 checkpoints. </p>
</note>
-->

<!--
Comment Type: draft

<p>The procedure to run the tool is:</p>
-->

<!--
Comment Type: draft

<ol>
<li><p>Always make sure you have a recent backup of the AEM instance.</p> <p>Shut down AEM.</p> </li>
<li><p>(Optional) Use the tool to find old checkpoints:</p>
<codeblock class="syntax xml">
java&nbsp;-jar&nbsp;oak-run.jar&nbsp;checkpoints&nbsp;install-folder/crx-quickstart/repository/segmentstore!!discoiqbr!!
</codeblock></li>
<li><p>(Optional) Then, delete the unreferenced checkpoints:</p>
<codeblock class="syntax java">
java&nbsp;-jar&nbsp;oak-run.jar&nbsp;checkpoints&nbsp;install-folder/crx-quickstart/repository/segmentstore&nbsp;rm-unreferenced
</codeblock></li>
<li><p>Run the compaction and wait for it to complete:</p>
<codeblock class="syntax java">
java&nbsp;-jar&nbsp;oak-run.jar&nbsp;compact&nbsp;install-folder/crx-quickstart/repository/segmentstore
</codeblock></li>
</ol>
-->

<!--
Comment Type: draft

<h3>Increasing the Performance of Offline Revision Cleanup</h3>
-->

<!--
Comment Type: draft

<p>Since version <strong>1.0.22</strong>, the oak-run tool introduces several features with an aim to increase the performance of the revision cleanup process and minimize the maintenance window as much as possible.</p>
<p>The list includes several command line parameters, as described below:</p>
<ul>
<li><span class="code">-Dtar.memoryMapped</span>. Use this to enable memory mapped operations for tar file to greatly increase performance. You can set this as <span class="code">true</span> or <span class="code">false</span>. It is highly recommended you enable this feature in order to speed up compaction.<br /> </li>
<li><span class="code">-Dupdate.limit</span>. Defines the threshold for the flush of a temporary transaction to disk. The default value is <span class="code">5000000</span>.<br /> </li>
<li><span class="code">-Dcompress-interval</span>. Number of compaction map entries to keep until compressing the current map. The default is <span class="code">1000000</span>. You should increase this value to an even higher number for faster throughput, if enough heap memory is available.</li>
<li><span class="code">-Dcompaction-progress-log</span>. The number of compacted nodes that will be logged. The default value is <span class="code">1500000</span>,<strong> </strong>which means that the first 1500000 compacted nodes will be logged during the operation. Use this in conjunction with the next parameter documented below.</li>
<li><span class="code">-Dlogback.configurationFile</span>. Use a configuration file for logging. You can use the below configuration file to enable the logging of the nodes that are being compacted:
<ul>
<li><a href="logback.md">logback.xml</a></li>
</ul> </li>
<li><strong><span class="code">-Dtar.PersistCompactionMap.</span> </strong>Set this parameter to <span class="code">true</span> to use disk space instead of heap memory for compaction map persistance. Requires the oak-run tool <strong>versions 1.4</strong> and higher. For further details also see question 6 in the <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#revisioncleanupfrequentlyaskedquestions">FAQ section</a>.</li>
</ul>
<p> </p>
-->

<!--
Comment Type: draft

<note type="caution">
<p>Memory mapped file operations do not work correctly on some versions of Windows. Make sure that you use the tool without the <span class="code">-Dtar.memoryMapped</span> parameter on Windows platforms, otherwise the revision cleanup will fail.</p>
</note>
-->

<!--
Comment Type: draft

<p>An example of the parameters in use:<br /> </p>
-->

<!--
Comment Type: draft

<codeblock gutter="true" class="syntax shell">
java&nbsp;-Dtar.memoryMapped=true&nbsp;-Dupdate.limit=5000000&nbsp;-Dcompress-interval=10000000&nbsp;-Dcompaction-progress-log=1500000&nbsp;-Dlogback.configurationFile=logback.xml&nbsp;-Xmx8g&nbsp;-jar&nbsp;oak-run-*.jar&nbsp;checkpoints&nbsp;<repository>
</codeblock>
-->

<!--
Comment Type: draft

<note type="note">
<p>Use as much heap memory as possible for faster I/O operations. It is recommended you use at least eight gigabytes for most common deployments.</p>
</note>
-->

<!--
Comment Type: draft

<h3>Performing Online Revision Cleanup</h3>
-->

<!--
Comment Type: draft

<note type="caution">
<p>Online Revision Cleanup is present in AEM 6.2 under <strong>restricted</strong> support. For more information on the conditions and terms of using the feature, please contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" target="_blank">Adobe Customer Care</a>.<br /> </p>
</note>
-->

<!--
Comment Type: draft

<p>For situations where the AEM cannot be shut down for maintenance, revision cleanup can also be performed while the instance is running. </p>
<p>You can perform Online revision cleanup by doing the following:</p>
-->

<!--
Comment Type: draft

<ol>
<li><p>Go to the folder where AEM is installed, then browse to <span class="code">crx-quickstart\install</span> (create the folder if it does not exist).</p> </li>
<li><p>Create or open the <span class="code">org.apache.jackrabbit.oak.segment.SegmentNodeStoreService.config</span> file.</p> </li>
<li><p>Add the following line to the configuration file:</p>
<codeblock gutter="true" class="syntax xml">
pauseCompaction=B&nbsp;"false"
</codeblock>
<draft-comment type="draft">
<p>A correct configuration file should look like this:</p>
</draft-comment>
<draft-comment type="draft">
<codeblock gutter="true" class="syntax xml">
repository.home=${repository.home}/segmentstore!!discoiqbr!!tarmk.size=256!!discoiqbr!!pauseCompaction=false
</codeblock>
</draft-comment></li>
<li><p>Restart AEM.</p> </li>
<li><p>Go to the JMX console by pointing your browser to <span class="code">http://server:port/system/console/jmx</span></p> </li>
<li><p>Search for <strong>CompactionStrategy</strong> and click the MBean that shows up in the search.</p> </li>
<li><p>Next, verify that the value for <strong>PausedCompaction</strong> is set to <span class="code">false</span>. This confirms that online revision cleanup is set to run:</p> <img imageRotate="0" src="assets/chlimage_1-123.png" /><p>Online revision cleanup is now scheduled to run as part of the tasks performed in the Daily Maintenance Window. For more info, see <a href="../../../sites/administering/using/operations-dashboard.md#main-pars-title-15">Automated Maintenance Tasks</a>.</p> </li>
<li><p>Next, verify if Online revision cleanup is running properly. You can do this by first going to the Operations Dashboard and checking what is the time interval configured for the <strong>Daily Maintenance Window. </strong>By default, it is scheduled to run between 2 and 5 AM.<br /> </p> </li>
<li><p>Now, inspect the <strong>error.log</strong> file for events logged during the time of the daily maintenance window to see if the online revision cleanup ran correctly. </p>
<note type="note">
<p>Before checking the logs, note that the revision cleanup will not be completed if the calculated disk space gain is less than 10 percent of the entire repository size.</p>
</note><p>This is an example of the log entries that will be generated if the revision cleanup was not run because the gain is less than 10 percent:</p>
<codeblock gutter="true" class="syntax xml">
16.03.2015&nbsp;02:00:13.736&nbsp;*INFO*&nbsp;[TarMK&nbsp;compaction&nbsp;thread&nbsp;[/author/crx-quickstart/repository/segmentstore],&nbsp;active&nbsp;since&nbsp;Mon&nbsp;Mar&nbsp;16&nbsp;02:00:13&nbsp;EDT&nbsp;2015,&nbsp;previous&nbsp;max&nbsp;duration&nbsp;58249ms]&nbsp;org.apache.jackrabbit.oak.plugins.segment.file.FileStore&nbsp;TarMK&nbsp;compaction&nbsp;started&nbsp;16.03.2015&nbsp;02:00:30.001&nbsp;*INFO*&nbsp;[pool-9-thread-2]&nbsp;com.adobe.granite.taskmanagement.impl.jcr.TaskArchiveService&nbsp;archiving&nbsp;tasks&nbsp;at:&nbsp;'Mon&nbsp;Mar&nbsp;16&nbsp;02:00:30&nbsp;EDT&nbsp;2015'!!discoiqbr!!16.03.2015&nbsp;02:01:06.325&nbsp;*INFO*&nbsp;[TarMK&nbsp;compaction&nbsp;thread&nbsp;[/author/crx-quickstart/repository/segmentstore],&nbsp;active&nbsp;since&nbsp;Mon&nbsp;Mar&nbsp;16&nbsp;02:00:13&nbsp;EDT&nbsp;2015,&nbsp;previous&nbsp;max&nbsp;duration&nbsp;58249ms]&nbsp;org.apache.jackrabbit.oak.plugins.segment.file.FileStore&nbsp;Estimated&nbsp;compaction&nbsp;in&nbsp;52.59&nbsp;s,&nbsp;gain&nbsp;is&nbsp;9%&nbsp;(1028524544/1137660928)&nbsp;or&nbsp;(1.0GB/1.1&nbsp;GB),&nbsp;so&nbsp;skipping&nbsp;compaction&nbsp;for&nbsp;now
</codeblock><p>This an example of the log entries that will be generated if the revision cleanup is going to be run because the gain is higher than 10 percent:<br /> </p>
<codeblock gutter="true" class="syntax xml">
19.03.2015&nbsp;02:00:10.230&nbsp;*INFO*&nbsp;[TarMK&nbsp;compaction&nbsp;thread&nbsp;[/author/crx-quickstart/repository/segmentstore],&nbsp;active&nbsp;since&nbsp;Thu&nbsp;Mar&nbsp;19&nbsp;02:00:10&nbsp;EDT&nbsp;2015,&nbsp;previous&nbsp;max&nbsp;duration&nbsp;1369831ms]&nbsp;org.apache.jackrabbit.oak.plugins.segment.file.FileStore&nbsp;TarMK&nbsp;compaction&nbsp;started!!discoiqbr!!19.03.2015&nbsp;02:00:30.441&nbsp;*INFO*&nbsp;[pool-9-thread-2]&nbsp;com.adobe.granite.taskmanagement.impl.jcr.TaskArchiveService&nbsp;archiving&nbsp;tasks&nbsp;at:&nbsp;'Thu&nbsp;Mar&nbsp;19&nbsp;02:00:30&nbsp;EDT&nbsp;2015'!!discoiqbr!!19.03.2015&nbsp;02:01:01.699&nbsp;*INFO*&nbsp;[TarMK&nbsp;compaction&nbsp;thread&nbsp;[/author/crx-quickstart/repository/segmentstore],&nbsp;active&nbsp;since&nbsp;Thu&nbsp;Mar&nbsp;19&nbsp;02:00:10&nbsp;EDT&nbsp;2015,&nbsp;previous&nbsp;max&nbsp;duration&nbsp;1369831ms]&nbsp;org.apache.jackrabbit.oak.plugins.segment.file.FileStore&nbsp;Estimated&nbsp;compaction&nbsp;in&nbsp;51.47&nbsp;s,&nbsp;gain&nbsp;is&nbsp;69%&nbsp;(1018859520/3343598080)&nbsp;or&nbsp;(1.0&nbsp;GB/3.3&nbsp;GB),&nbsp;so&nbsp;running&nbsp;compaction
</codeblock><p>Lastly, these are the log entry generated when the revision cleanup has successfully completed:</p>
<codeblock gutter="true" class="syntax xml">
19.03.2015&nbsp;02:22:52.638&nbsp;*INFO*&nbsp;[TarMK&nbsp;compaction&nbsp;thread&nbsp;[/author/crx-quickstart/repository/segmentstore],&nbsp;active&nbsp;since&nbsp;Thu&nbsp;Mar&nbsp;19&nbsp;02:00:10&nbsp;EDT&nbsp;2015,&nbsp;previous&nbsp;max&nbsp;duration&nbsp;1369831ms]&nbsp;org.apache.jackrabbit.oak.plugins.segment.file.FileStore&nbsp;TarMK&nbsp;compaction&nbsp;completed&nbsp;in&nbsp;1310939ms
</codeblock></li>
</ol>
-->

<!--
Comment Type: draft

<h2>Additional Methods of Triggering Revision Cleanup</h2>
-->

<!--
Comment Type: draft

<h3>Triggering Revision Cleanup from the Operations Dashboard</h3>
-->

<!--
Comment Type: draft

<p>The automatic revision cleanup can be triggered manually in the Operations Dashboard via a maintenance job called <strong>Revision Clean Up</strong>. </p>
<p>To start Revision Clean Up you need to:</p>
-->

<!--
Comment Type: draft

<ol>
<li><p>Go to the AEM Welcome Screen.</p> </li>
<li><p>In the main AEM window, go to <strong>Tools - Operations - Dashboard - Maintenance</strong> or directly browse to <a href="http://localhost:4502/libs/granite/operations/content/maintenance.html">http://localhost:4502/libs/granite/operations/content/maintenance.html</a></p> </li>
<li><p>Click on <strong>Daily Maintenance Window.</strong></p> </li>
<li><p>Hover over the <strong>Revision Clean Up</strong> window and press the <strong>Start </strong>button.<br /> </p> </li>
</ol>
-->

<!--
Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-124.png" />
-->

<!--
Comment Type: draft

<p>The icon will turn orange to indicate that the Revision Clean Up job is running. You can stop it at any time by hovering the mouse over the icon and pressing the <strong>Stop</strong> button:<br /> </p>
-->

<!--
Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-125.png" />
-->

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-0436B4A35714BFF67F000101@AdobeID)
Last Modified Date: 2017-11-30T05:42:42.921-0500
<p>As discussed with Peter Klassen we will hide all information about running Online Revision Cleanup in 6.2 and we will only keep the warning.</p>
-->

<!--
Comment Type: draft

<h3>Invoking Revision Garbage Collection via the JMX Console</h3>
-->

<!--
Comment Type: draft

<ol>
<li><p>Open the JMX Console by going to <a href="http://localhost:4502/system/console/jmx">http://localhost:4502/system/console/jmx</a></p> </li>
<li><p>Click the <strong>RevisionGarbageCollection</strong> MBean.</p> </li>
<li><p>In the next window, click <strong>startRevisionGC()</strong> and then <strong>Invoke</strong> to start the Revision Garbage Collection job.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<note type="note">
<p>Due to the mechanics of the garbage collection, the first run will actually add 256 MB of disk space. Subsequent runs will work as expected and start shrinking the repository size.</p>
</note>
-->

<!--
Comment Type: draft

<h2>Performance Tuning and Maintenance Recommendations</h2>
-->

<!--
Comment Type: draft

<p>Follow the below recommendations in order to maintain maximum efficiency while upkeeping the repository:</p>
<ol>
<li>Make sure you run <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#main-pars-title-42551947">Offline Revision Cleanup</a> whenever possible during scheduled maintenance hours;</li>
<li>If you are using an external data store, make sure you run <a href="../../../sites/administering/using/data-store-garbage-collection.md">Data Store Garbage Collection</a> after revision cleanup has been completed.</li>
<li>Follow the recommendations in <a href="https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html">this knowledgebase article</a> for tips on improving the performance of your AEM instance.</li>
</ol>
-->

<!--
Comment Type: draft

<h2>Revision Cleanup Frequently Asked Questions</h2>
-->

<!--
Comment Type: draft

<p> 1. When to use Offline Revision Cleanup as opposed to Online Revision Cleanup?</p>
<ul>
<li>See <a href="/content/docs/en/aem/6-3/deploy/platform/storage-elements-in-aem-6-2#Choosing%20the%20Type%20of%20Revision%20Cleanup">Choosing the Type of Revision Cleanup.</a></li>
</ul>
<p> 2. How frequently should Offline Revision Cleanup be performed?</p>
<ul>
<li>It depends on the repository growth rate. As a general rule of thumb, for average content repositories, it is recommended that you perform revision cleanup every 2 weeks for an author instance, and once per quarter for a publish instance.</li>
</ul>
<p> 3. What are the factors that determine the duration of the Offline Revision Cleanup?</p>
<ul>
<li>The repository size and the amount of revisions that need to be cleaned up determines the duration of the cleanup.</li>
</ul>
<p> 4. What's the worst that can happen if you do not perform revision cleanup?</p>
<ul>
<li>The AEM instance will run out of disk space, which will cause outages in production. It is highly recommended that you follow the monitoring best practices as mentioned in the <a href="../../../managing/using/best-practices.md">Managing Projects - Best Practices</a>; see the <a href="../../../managing/using/best-practices-glossary.md">Managing Projects Best Practices Glossary for specific monitoring tasks</a>, with further details also available under <a href="../../../sites/deploying/using/monitoring-and-maintaining.md">Monitoring and Maintaining your Instance</a>.</li>
</ul>
<p> 5. What is the difference between a revision and a page version?</p>
<ul>
<li><strong>Oak revision:</strong> Oak organizes all the content in a large tree hierarchy that consists of nodes and properties. Each snapshot or revision of this content tree is immutable, and changes to the tree are expressed as a sequence of new revisions. Typically, each content modification triggers a new revision. See also <a href="http://jackrabbit.apache.org/dev/ngp.html" title="Follow link">http://jackrabbit.apache.org/dev/ngp.html</a>.</li>
<li><strong>Page Version:</strong> Versioning creates a "snapshot" of a page at a specific point in time. Typically, a new version is created when a page is activated. For more information, see <a href="../../../sites/authoring/using/working-with-page-versions.md">Working with Page Versions</a>.</li>
</ul>
<p> 6. How to speed up the Offline Revision Cleanup task if it does not complete within 8 hours ?</p>
<ul>
<li>If the revision task does not complete within 8 hours and the <a href="../../../sites/administering/using/operations-dashboard.md#diagnosistools" target="_blank">thread dumps</a> reveal that the main hotspot is <span class="code">InMemoryCompactionMap.findEntry</span>, use the following parameter with the oak-run tool <strong>versions 1.4 </strong>or higher: -Dtar.PersistCompactionMap=true. See also <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#performingofflinerevisioncleanup">Performing Offline Revision Cleanup</a> and <a href="../../../sites/deploying/using/storage-elements-in-aem-6.md#increasingtheperformanceofofflinerevisioncleanup">Increasing the Performance of Offline Revision Cleanup</a>. </li>
</ul>
<p> </p>
-->

