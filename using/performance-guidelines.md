---
title: Performance Guidelines
seo-title: Performance Guidelines
description: null
seo-description: This article provides general guidelines on how to optimize the performance of your AEM deployment.
uuid: 85bcba1f-f97a-43a5-a698-1c5e98d87204
content-encoding: UTF-8
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/performance-guidelines
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-05-16T10 19 08.403-0400
cq-lastmodifiedby: raiman
cq-lastreplicated: 2018-05-16T10 19 08.574-0400
cq-lastreplicatedby: raiman
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: configuring
cq-template: /apps/help/templates/article-3
discoiquuid: 5a16b350-236e-46a0-bf7d-16690cb43220
firstPublishExternalDate: 2017-11-16T10:33:49.531-0500
isreadyforlocalization: false
jcr-created: 2018-01-24T19 01 55.157-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-05-16T10:19:08.362-0400
lochandoffdate: 2018-04-30T03 27 44.327-0400
lr-lastreplicatedby: raiman@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-05-16T10 19 08.362-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/performance-guidelines.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/performance_draft
sha1: 78e81e2b6ca37c2e2a2a9240e6fe4224d1e63ea5
topicBrowsingSortDate: 2018-05-16T10:19:08.362-0400
index: y
internal: n
snippet: y
translate: y
---

# Performance Guidelines

This page provides general guidelines on how to optimize the performance of your AEM deployment. If you are new to AEM, please go over the following pages before you start reading the performance guidelines:

* [AEM Basic Concepts](deploy.md#BasicConcepts)
* [Overview of Storage in AEM 6.3](storage-elements-in-aem-6.md#OverviewofStorageinAEM6)
* [Recommended Deployments](recommended-deploys.md)
* [Technical Requirements](technical-requirements.md)

Illustrated below are the deployment options available for AEM (scroll to view all the options):

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td height="13" width="104"><p><strong>AEM</strong></p> <p><strong>Product</strong></p> </td> 
   <td width="106"><p><strong>Topology</strong></p> </td> 
   <td width="82"><p><strong>Operating System</strong></p> </td> 
   <td width="87"><p><strong>Application Server</strong></p> </td> 
   <td width="56"><p><strong>JRE</strong></p> </td> 
   <td width="64"><p><strong>Security</strong></p> </td> 
   <td width="106"><p><strong>Micro Kernel</strong></p> </td> 
   <td width="73"><p><strong>Datastore</strong></p> </td> 
   <td width="65"><p><strong>Indexing</strong></p> </td> 
   <td width="65"><p><strong>Web Server</strong></p> </td> 
   <td width="69"><p><strong>Browser</strong></p> </td> 
   <td width="82"><p><strong>Marketing Cloud</strong></p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Sites</p> </td> 
   <td width="106"><p>Non-HA</p> </td> 
   <td width="82"><p>Windows</p> </td> 
   <td width="87"><p>CQSE</p> </td> 
   <td width="56"><p>Oracle</p> </td> 
   <td width="64"><p>LDAP</p> </td> 
   <td width="106"><p>Tar</p> </td> 
   <td width="73"><p>Segment</p> </td> 
   <td width="65"><p>Property</p> </td> 
   <td width="65"><p>Apache</p> </td> 
   <td width="69"><p>Edge</p> </td> 
   <td width="82"><p>Target</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Assets</p> </td> 
   <td width="106"><p>Publish-HA</p> </td> 
   <td width="82"><p>Solaris</p> </td> 
   <td width="87"><p>WebLogic</p> </td> 
   <td width="56"><p>IBM</p> </td> 
   <td width="64"><p>SAML</p> </td> 
   <td width="106"><p>MongoDB</p> </td> 
   <td width="73"><p>File</p> </td> 
   <td width="65"><p>Lucene</p> </td> 
   <td width="65"><p>IIS</p> </td> 
   <td width="69"><p>IE</p> </td> 
   <td width="82"><p>Analytics</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Communities</p> </td> 
   <td width="106"><p>Author-CS</p> </td> 
   <td width="82"><p>Red Hat</p> </td> 
   <td width="87"><p>WebSphere</p> </td> 
   <td width="56"><p>HP</p> </td> 
   <td width="64"><p>Oauth</p> </td> 
   <td width="106"><p>RDB/Oracle</p> </td> 
   <td width="73"><p>S3/Azure</p> </td> 
   <td width="65"><p>Solr</p> </td> 
   <td width="65"><p>iPlanet</p> </td> 
   <td width="69"><p>FireFox</p> </td> 
   <td width="82"><p>Campaign</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Forms</p> </td> 
   <td width="106"><p>Author-Offload</p> </td> 
   <td width="82"><p>HP-UX</p> </td> 
   <td width="87"><p>Tomcat</p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p>RDB/DB2</p> </td> 
   <td width="73"><p>MongoDB</p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p>Chrome</p> </td> 
   <td width="82"><p>Social</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Mobile</p> </td> 
   <td width="106"><p>Author-Cluster</p> </td> 
   <td width="82"><p>IBM AIX</p> </td> 
   <td width="87"><p>JBoss</p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p>RDB/MySQL</p> </td> 
   <td width="73"><p>RDBMS</p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p>Safari</p> </td> 
   <td width="82"><p>Audience</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Multi-site</p> </td> 
   <td width="106"><p>ASRP</p> </td> 
   <td width="82"><p>SUSE</p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p>RDB/SQLServer</p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p>Assets</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Commerce</p> </td> 
   <td width="106"><p>MSRP</p> </td> 
   <td width="82"><p>Apple OS</p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p>Activation</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Dynamic Media</p> </td> 
   <td width="106"><p>JSRP</p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p>Mobile</p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Brand Portal</p> </td> 
   <td width="106"><p>J2E</p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>AoD</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>LiveFyre</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Screens</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Doc Security</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Process Mgt</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
  <tr> 
   <td width="104"><p>Desktop App</p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
   <td width="87"><p> </p> </td> 
   <td width="56"><p> </p> </td> 
   <td width="64"><p> </p> </td> 
   <td width="106"><p> </p> </td> 
   <td width="73"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="65"><p> </p> </td> 
   <td width="69"><p> </p> </td> 
   <td width="82"><p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
><p>The performance guidelines apply mainly to AEM Sites.</p>

---

## When to Use the Performance Guidelines

You should use the performance guidelines in the following situations:

* **First time deployment**: When planning to deploy AEM Sites or Assets for the first time, it is important to understand the options available when configuring the Micro Kernel, Node Store, and Data Store (compared to the default settings). For example, changing the default settings of the Data Store for TarMK to File Data Store.
* **Upgrading to a new version**: When upgrading to a new version, it is important to understand the performance differences compared to the running environment. For example, upgrading from AEM 6.1 to 6.2, or from AEM 6.0 CRX2 to 6.2 OAK.
* **Response time is slow**: When the selected Nodestore architecture is not meeting your requirements, it is important to understand the performance differences compared to other topology options. For example, deploying TarMK instead of MongoMK, or using a File Data Sore instead of an Amazon S3 or Microsoft Azure Data Store.
* **Adding more authors**: When the recommended TarMK topology is not meeting the performance requirements and upsizing the Author node has reached the maximum capacity available, it is important to understand the performance differences compared to using MongoMK with three or more Author nodes. For example, deploying MongoMK instead of TarMK.
* **Adding more content**: When the recommended Data Store architecture is not meeting your requirements, it’s important to understand the performance differences compared to other Data Store options. Example: using the Amazon S3 or Microsoft Azure Data Store instead of a File Data Store.

---

## Introduction

This chapter gives a general overview of the AEM architecture and its most important components. It also provides development guidelines and describes the testing scenarios used in the TarMK and MongoMK benchmark tests.

### The AEM Platform

The AEM platform consists of the following components:
![](assets/chlimage_1.png) 

For more information on the AEM platform, see [What is AEM](deploy.md#WhatisAEM).

### The AEM Architecture

There are three important building blocks to an AEM deployment. The **Author Instance** which is used by content authors, editors, and approvers to create and review content. When the content is approved, it is published to a second instance type named the **Publish Instance** from where it is accessed by the end users. The third building block is the **Dispatcher** which is a module that handles caching and URL filtering and is installed on the webserver. For additional information about the AEM architecture, see [Typical Deployment Scenarios](deploy.md#TypicalDeploymentScenarios).
![](assets/chlimage_1.png) 

### Micro Kernels

Micro Kernels act as persistence managers in AEM. There are three types of Micro Kernels used with AEM: TarMK, MongoDB, and Relational Database (under restricted support). Choosing one to fit your needs depends on the purpose of your instance and the deployment type you are considering. For additional information about Micro Kernels, see the [Recommended Deployments](recommended-deploys.md) page.
![](assets/chlimage_1.png) 

### Nodestore

In AEM, binary data can be stored independently from content nodes. The location where the binary data is stored is referred to as the **Data Store**, while the location of the content nodes and properties is called the **Node Store**.

>[!NOTE]
>
><p>Adobe recommends TarMK to be the default persistence technology used by customers for both the AEM Author and the Publish instances.</p> 

>[!CAUTION]
>
><p>The Relational Database Micro Kernel is under restricted support. Contact <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html">Adobe Customer Care</a> before using this type of Micro Kernel.</p> 
![](assets/chlimage_1.png) 

### Data Store

When dealing with large number of binaries, it is recommended that an external data store be used instead of the default node stores in order to maximize performance. For example, if your project requires a large number of media assets, storing them under the File or Azure/S3 Data Store will make accessing them faster than storing them directly inside a MongoDB.

For further details on the available configuration options, see [Configuring Node and Data Stores](data-store-config.md).

>[!NOTE]
>
><p>Adobe recommends to choose the option of deploying AEM on Azure or Amazon Web Services (AWS) using Adobe Managed Services, where customers will benefit from a team who has the experience and the skills of deploying and operating AEM in these cloud computing environments. Please see our&nbsp;<a href="http://www.adobe.com/marketing-cloud/enterprise-content-management/managed-services-cloud-platform.html?aemClk=t">additional documentation on Adobe Managed Services</a>.</p> <p>For recommendations on how to deploy AEM on Azure or AWS, outside of Adobe Managed Services, we strongly recommend working directly with the cloud provider or one of our partners supporting the deployment of AEM in the cloud environment of your choice. The selected cloud provider or partner is responsible for the sizing specifications, design and implementation of the architecture they will support to meet your specific performance, load, scalability, and security requirements.</p> <p>For additional details also see the&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/deploying/using/technical-requirements.html#SupportedPlatforms">technical requirements</a>&nbsp;page.</p> 
![](assets/chlimage_1.png) 

### Search

Listed in this section are the custom index providers used with AEM. To know more about indexing, see [Oak Queries and Indexing](queries-and-indexing.md).

>[!NOTE]
>
><p>For most deployments, Adobe recommends using the Lucene Index. You should use Solr only for scalability in specialized and complex deployments.</p> 
![](assets/chlimage_1.png) 

### Development Guidelines

You should develop for AEM aiming for **performance and scalability**. Presented below are a number of best practices that you can follow:

****

* Apply separation of presentation, logic, and content
* Use existing AEM APIs (ex: Sling) and tooling (ex: Replication)
* Develop in the context of actual content
* Develop for optimum cacheability
* Minimize number of saves (ex: by using transient workflows)
* Make sure all HTTP end points are RESTful
* Restrict the scope of JCR observation
* Be mindful of asynchronous thread

****

* Don’t use JCR APIs directly, if you can
* Don’t change /libs, but rather use overlays
* Don’t use queries wherever possible
* Don’t use Sling Bindings to get OSGi services in Java code, but rather use:

    * @Reference in a DS component    
    * @Inject in a Sling Model    
    * sling.getService() in a Sightly Use Class    
    * sling.getService() in a JSP    
    * a ServiceTracker    
    * direct access to the OSGi service registry

For further details about developing on AEM, read [Developing - The Basics](/content/help/en/experience-manager/6-4/sites/developing/using/the-basics). For additional best practices, see [Development Best Practices](/content/help/en/experience-manager/6-4/sites/developing/using/best-practices).

### Benchmark Scenarios

>[!NOTE]
>
><p>All the benchmark tests displayed on this page have been performed in a laboratory setting.</p>

The testing scenarios detailed below are used for the benchmark sections of the TarMK, MongoMk and TarMK vs MongoMk chapters. To see which scenario was used for a particular benchmark test, read the Scenario field from the [Technical Specifications](performance-guidelines.md#TarMKPerformanceBenchmark) table.

**Single Product Scenario**

:

* User interactions: Browse Assets / Search Assets / Download Asset / Read Asset Metadata / Update Asset Metadata / Upload Asset / Run Upload Asset Workflow
* Execution mode: concurrent users, single interaction per user

**Mix Products Scenario**

:

* Sites user interactions: Read Article Page / Read Page / Create Paragraph / Edit Paragraph / Create Content Page / Activate Content Page / Author Search
* Assets user interactions: Browse Assets / Search Assets / Download Asset / Read Asset Metadata / Update Asset Metadata / Upload Asset / Run Upload Asset Workflow
* Execution mode: concurrent users, mixed interactions per user

**Vertical Use Case Scenario**

* Read Article Page (27.4%), Read Page (10.9%), Create Session (2.6%), Activate Content Page (1.7%), Create Content Page (0.4%), Create Paragraph (4.3%), Edit Paragraph (0.9%), Image Component (0.9%), Browse Assets (20%), Read Asset Metadata (8.5%), Download Asset (4.2%), Search Asset (0.2%), Update Asset Metadata (2.4%), Upload Asset (1.2%), Browse Project (4.9%), Read Project (6.6%), Project Add Asset (1.2%), Project Add Site (1.2%), Create Project (0.1%), Author Search (0.4%)
* Execution mode: concurrent users, mixed interactions per user

---

## TarMK

This chapter gives general performance guidelines for TarMK specifying the minimum architecture requirements and the settings configuration. Benchmark tests are also provided for further clarification.

Adobe recommends TarMK to be the default persistence technology used by customers in all deployment scenarios, for both the AEM Author and Publish instances.

For more information about TarMK, see [Deployment Scenarios](recommended-deploys.md#Deploymentscenarios) and [Tar Storage](storage-elements-in-aem-6.md#TarStorage).

### TarMK Minimum Architecture Guidelines

>[!NOTE]
>
><p>The minimum architecture guidelines presented below are for production enviroments and high traffic sites. These are <b>not </b>the <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/technical-requirements.html#Prerequisites" >minimum specifications</a><b>&nbsp;</b>needed to run AEM.&nbsp;</p>

To establish good performance when using TarMK, you should start from the following architecture:

* One Author instance
* Two Publish instances
* Two Dispatchers

Illustrated below are the architecture guidelines for AEM sites and AEM Assets.

>[!NOTE]
>
><p>Binary-less replication should be turned <b>ON</b> if the File Datastore is shared.</p>

**Tar Architecture Guidelines for AEM Sites**
![](assets/chlimage_1.png) 

**Tar Architecture Guidelines for AEM Assets**
![](assets/chlimage_1.png) 

### TarMK Settings Guideline

For good performance, you should follow the settings guidelines presented below. For instructions on how to change the settings, [see this page](/content/help/en/experience-manager/kb/performance-tuning-tips).

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Setting</strong></td> 
   <td><strong>Parameter</strong></td> 
   <td><strong>Value</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>Sling Job Queues</td> 
   <td><span class="code">queue.maxparallel</span></td> 
   <td>Set value to half of the number of CPU cores. </td> 
   <td>By default the number of concurrent threads per job queue is equal to the number of CPU cores.</td> 
  </tr> 
  <tr> 
   <td>Granite Transient Workflow Queue</td> 
   <td><span class="code">Max Parallel</span></td> 
   <td>Set value to half of the number of CPU cores</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>JVM parameters</td> 
   <td><p><span class="code">Doak.queryLimitInMemory</span></p> <p><span class="code">Doak.queryLimitReads</span></p> <p><span class="code">Dupdate.limit</span></p> <p><span class="code">Doak.fastQuerySize</span></p> </td> 
   <td><p>500000</p> <p>100000</p> <p>250000</p> <p>True</p> </td> 
   <td>Add these JVM parameters in the AEM start script to prevent expansive queries from overloading the systems.</td> 
  </tr> 
  <tr> 
   <td>Lucene index configuration</td> 
   <td><p><span class="code">CopyOnRead</span></p> <p><span class="code">CopyOnWrite</span></p> <p><span class="code">Prefetch Index Files</span></p> </td> 
   <td><p>Enabled</p> <p>Enabled</p> <p>Enabled</p> </td> 
   <td>For more details on the available parameters, see <a href="http://jackrabbit.apache.org/oak/docs/query/lucene.html">this page</a>.</td> 
  </tr> 
  <tr> 
   <td>Data Store = S3 Datastore</td> 
   <td><p><span class="code">maxCachedBinarySize</span></p> <p><span class="code">cacheSizeInMB</span></p> </td> 
   <td><p>1048576 (1MB) or smaller</p> <p>2-10% of max heap size</p> </td> 
   <td>See also <a href="data-store-config.md#DataStoreConfigurations">Data Store Configurations</a>.</td> 
  </tr> 
  <tr> 
   <td>DAM Update Asset workflow</td> 
   <td><span class="code">Transient Workflow</span></td> 
   <td>checked</td> 
   <td>This workflow manages the update of assets.</td> 
  </tr> 
  <tr> 
   <td>DAM MetaData Writeback</td> 
   <td><span class="code">Transient Workflow</span></td> 
   <td>checked</td> 
   <td>This workflow manages XMP write-back to the original binary and sets the last modified date in JCR.</td> 
  </tr> 
 </tbody> 
</table>

### TarMK Performance Benchmark

#### Technical Specifications

The benchmark tests were performed on the following specifications:

| ** ** |**Author Node** |
|---|---|
| Server |Bare metal hardware (HP) |
| Operating System |RedHat Linux |
| CPU / Cores |Intel(R) Xeon(R) CPU E5-2407 @2.40GHz, 8 cores  |
| RAM |32GB |
| Disk |Magnetic |
| Java |Oracle JRE Version 8 |
| JVM Heap |16GB |
| Product  |AEM 6.2 |
| Nodestore |TarMK |
| Datastore |File DS  |
| Scenario |Single Product: Assets / 30 concurrent threads |

#### Performance Bechmark Results

>[!NOTE]
>
><p>The numbers presented below have been normalized to 1 as the baseline and are not the actual throughput numbers.</p> 
![](assets/chlimage_1.png)  ![](assets/chlimage_1.png) 

---

## MongoMK

The primary reason for choosing the MongoMK persistence backend over TarMK is to scale the instances horizontally. This means having two or more active author instances running at all times and using MongoDB as the persistence storage system. The need to run more than one author instance results generally from the fact that the CPU and memory capacity of a single server, supporting all concurrent authoring activities, is no longer sustainable.

For more information about TarMK, see [Deployment Scenarios](recommended-deploys.md#Deploymentscenarios) and [Mongo Storage](storage-elements-in-aem-6.md#MongoStorage).

### MongoMK Minimum Architecture Guidelines

To establish good performance when using MongoMK, you should start from the following architecture:

* Three Author instances
* Two Publish instances
* Three MongoDB instances
* Two Dispatchers

>[!NOTE]
>
><p>In production environments, MongoDB will always be used as a replica set with a primary and two secondaries. Reads and writes go to the primary and reads can go to the secondaries. If storage is not available, one of the secondaries can be replaced with an arbiter, but MongoDB replica sets must always be composed of an odd number of instances.</p> 

>[!NOTE]
>
><p>Binary-less replication should be turned&nbsp;<b>ON</b>&nbsp;if the File Datastore is shared.</p> 
![](assets/chlimage_1.png) 

### MongoMK Settings Guidelines

For good performance, you should follow the settings guidelines presented below. For instructions on how to change the settings, [see this page](/content/help/en/experience-manager/kb/performance-tuning-tips).

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Setting</strong></td> 
   <td><strong>Parameter</strong></td> 
   <td><strong>Value (default)</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>Sling Job Queues</td> 
   <td><span class="code">queue.maxparallel</span></td> 
   <td>Set value to half of the number of CPU cores. </td> 
   <td>By default the number of concurrent threads per job queue is equal to the number of CPU cores.</td> 
  </tr> 
  <tr> 
   <td>Granite Transient Workflow Queue</td> 
   <td><span class="code">Max Parallel</span></td> 
   <td>Set value to half of the number of CPU cores.</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>JVM parameters</td> 
   <td><p><span class="code">Doak.queryLimitInMemory</span></p> <p><span class="code">Doak.queryLimitReads</span></p> <p><span class="code">Dupdate.limit</span></p> <p><span class="code">Doak.fastQuerySize</span></p> <p><span class="code">Doak.mongo.maxQueryTimeMS</span></p> </td> 
   <td><p>500000</p> <p>100000</p> <p>250000</p> <p>True</p> <p>60000</p> </td> 
   <td>Add these JVM parameters in the AEM start script to prevent expansive queries from overloading the systems.</td> 
  </tr> 
  <tr> 
   <td>Lucene index configuration</td> 
   <td><p><span class="code">CopyOnRead</span></p> <p><span class="code">CopyOnWrite</span></p> <p><span class="code">Prefetch Index Files</span></p> </td> 
   <td><p>Enabled</p> <p>Enabled</p> <p>Enabled</p> </td> 
   <td>For more details on available parameters, see <a href="http://jackrabbit.apache.org/oak/docs/query/lucene.html">this page</a>.</td> 
  </tr> 
  <tr> 
   <td>Data Store = S3 Datastore</td> 
   <td><p><span class="code">maxCachedBinarySize</span></p> <p><span class="code">cacheSizeInMB</span></p> </td> 
   <td><p>1048576 (1MB) or smaller</p> <p>2-10% of max heap size</p> </td> 
   <td>See also <a href="data-store-config.md#DataStoreConfigurations">Data Store Configurations</a>.</td> 
  </tr> 
  <tr> 
   <td>DocumentNodeStoreService</td> 
   <td><p><span class="code">cache</span></p> <p><span class="code">nodeCachePercentage</span></p> <p><span class="code">childrenCachePercentage</span></p> <p><span class="code">diffCachePercentage</span></p> <p><span class="code">docChildrenCachePercentage</span></p> <p><span class="code">prevDocCachePercentage</span></p> <p><span class="code">persistentCache</span></p> </td> 
   <td><p>2048</p> <p>35 (25)</p> <p>20 (10)</p> <p>30 (5)</p> <p>10 (3)</p> <p>4 (4)</p> <p>./cache,size=2048,binary=0,-compact,-compress</p> </td> 
   <td><p>The default size of the cache is set to 256 MB.</p> <p>Has impact on the time it takes to perform cache invalidation.</p> </td> 
  </tr> 
  <tr> 
   <td>oak-observation</td> 
   <td><p><span class="code">thread pool</span></p> <p><span class="code">length</span></p> </td> 
   <td><p>min &amp; max = 20</p> <p>50000</p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

### MongoMK Performance Benchmark

### Technical Specifications

The benchmark tests were performed on the following specifications:

| ** ** |**Author node** |**MongoDB node** |
|---|---|---|
| Server |Bare metal hardware (HP) |Bare metal hardware (HP) |
| Operating System |RedHat Linux |RedHat Linux |
| CPU / Cores |Intel(R) Xeon(R) CPU E5-2407 @2.40GHz, 8 cores |Intel(R) Xeon(R) CPU E5-2407 @2.40GHz, 8 cores  |
| RAM |32GB |32GB |
| Disk |Magnetic - >1k IOPS |Magnetic - >1k IOPS |
| Java |Oracle JRE Version 8 |N/A |
| JVM Heap |16GB |N/A |
| Product  |AEM 6.2 |MongoDB 3.2 WiredTiger |
| Nodestore |MongoMK |N/A |
| Datastore |File DS  |N/A |
| Scenario |Single Product: Assets / 30 concurrent threads |Single Product: Assets / 30 concurrent threads |

### Performance Benchmark Results

>[!NOTE]
>
><p>The numbers presented below have been normalized to 1 as the baseline and are not the actual throughput numbers.</p> 
![](assets/chlimage_1.png)  ![](assets/chlimage_1.png) 

---

## TarMK vs MongoMK

The basic rule that needs to be taken into account when choosing between the two is that TarMK is designed for performance, while MongoMK is used for scalability. Adobe recommends TarMK to be the default persistence technology used by customers in all deployment scenarios, for both the AEM Author and Publish instances.

The primary reason for choosing the MongoMK persistence backend over TarMK is to scale the instances horizontally. This means having two or more active author instances running at all times and using MongoDB as the persistence storage system. The need to run more than one author instance generally results from the fact that the CPU and memory capacity of a single server, supporting all concurrent authoring activities, is no longer sustainable.

For further details on TarMK vs MongoMK, see [Recommended Deployments](recommended-deploys.md#Microkernelswhichonetouse).

### TarMK vs MongoMk Guidelines

**Benefits of TarMK**

* Purpose-built for content management applications
* Files are always consistent and can be backed up using any file-based backup tool
* Provides a failover mechanism - see [Cold Standby](tarmk-cold-standby.md) for more details
* Provides high performance and reliable data storage with minimal operational overhead
* Lower TCO (total cost of ownership)

**Criteria for choosing MongoMK**

* Number of named users connected in a day: in the thousands or more
* Number of concurrent users: in the hundreds or more
* Volume of asset ingestions per day: in hundreds of thousands or more
* Volume of page edits per day: in hundreds of thousands or more
* Volume of searches per day: in tens of thousands or more

### TarMK vs MongoMK Benchmarks

>[!NOTE]
>
><p>The numbers presented below have been normalized to 1 as the baseline and are not actual throughput numbers.</p>

### Scenario 1 Technical Specifications

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong> </strong></td> 
   <td><strong>Author OAK Node</strong></td> 
   <td><strong>MongoDB Node</strong></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Server</td> 
   <td>Bare metal hardware (HP)</td> 
   <td>Bare metal hardware (HP)</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Operating System</td> 
   <td>RedHat Linux</td> 
   <td>RedHat Linux</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CPU / Cores</td> 
   <td>Intel(R) Xeon(R) CPU E5-2407 @2.40GHz, 8 cores</td> 
   <td>Intel(R) Xeon(R) CPU E5-2407 @2.40GHz, 8 cores</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>RAM</td> 
   <td>32GB</td> 
   <td>32GB</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Disk</td> 
   <td>Magnetic - &gt;1k IOPS</td> 
   <td>Magnetic - &gt;1k IOPS</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Java</td> 
   <td>Oracle JRE Version 8</td> 
   <td>N/A</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>JVM Heap16GB</td> 
   <td>16GB</td> 
   <td>N/A</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Product </td> 
   <td>AEM 6.2</td> 
   <td>MongoDB 3.2 WiredTiger</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Nodestore</td> 
   <td>TarMK or MongoMK</td> 
   <td>N/A</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Datastore</td> 
   <td>File DS </td> 
   <td>N/A</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Scenario</td> 
   <td colspan="2" width="462"><p><br /> Single Product: Assets / 30 concurrent threads per run</p> </td> 
   <td width="462"> </td> 
  </tr> 
 </tbody> 
</table>

### Scenario 1 Performance Benchmark Results
![](assets/chlimage_1.png) 

### Scenario 2 Technical Specifications

>[!NOTE]
>
><p>To enable the same number of Authors with MongoDB as with one TarMK system you need a cluster with two AEM nodes. A four node MongoDB cluster can handle 1.8 times the number of Authors than one TarMK instance. An eight node MongoDB cluster can handle 2.3 times the number of Authors than one TarMK instance.</p> 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong> </strong></td> 
   <td><strong>Author TarMK Node</strong></td> 
   <td><strong>Author MongoMK Node</strong></td> 
   <td><strong>MongoDB Node</strong></td> 
  </tr> 
  <tr> 
   <td>Server</td> 
   <td>AWS c3.8xlarge</td> 
   <td>AWS c3.8xlarge</td> 
   <td>AWS c3.8xlarge</td> 
  </tr> 
  <tr> 
   <td>Operating System</td> 
   <td>RedHat Linux</td> 
   <td>RedHat Linux</td> 
   <td>RedHat Linux</td> 
  </tr> 
  <tr> 
   <td>CPU / Cores</td> 
   <td>32</td> 
   <td>32</td> 
   <td>32</td> 
  </tr> 
  <tr> 
   <td>RAM</td> 
   <td>60GB</td> 
   <td>60GB</td> 
   <td>60GB</td> 
  </tr> 
  <tr> 
   <td>Disk</td> 
   <td>SSD - 10k IOPS</td> 
   <td>SSD - 10k IOPS</td> 
   <td>SSD - 10k IOPS</td> 
  </tr> 
  <tr> 
   <td>Java</td> 
   <td>Oracle JRE Version 8</td> 
   <td><br /> Oracle JRE Version 8</td> 
   <td>N/A</td> 
  </tr> 
  <tr> 
   <td>JVM Heap16GB</td> 
   <td>30GB</td> 
   <td>30GB</td> 
   <td>N/A</td> 
  </tr> 
  <tr> 
   <td>Product </td> 
   <td>AEM 6.2</td> 
   <td>AEM 6.2</td> 
   <td><br /> MongoDB 3.2 WiredTiger</td> 
  </tr> 
  <tr> 
   <td>Nodestore</td> 
   <td>TarMK </td> 
   <td>MongoMK</td> 
   <td><br /> N/A</td> 
  </tr> 
  <tr> 
   <td>Datastore</td> 
   <td>File DS </td> 
   <td><br /> File DS</td> 
   <td><br /> N/A</td> 
  </tr> 
  <tr> 
   <td>Scenario</td> 
   <td colspan="2" width="462"><p><br /> <br /> Vertical use case: Media / 2000 concurrent threads</p> </td> 
  </tr> 
 </tbody> 
</table>

### Scenario 2 Performance Benchmark Results
![](assets/chlimage_1.png) 

### Architecture Scalability Guidelines For AEM Sites and Assets
![](assets/chlimage_1.png) 

---

## Summary of Performance Guidelines

The guidelines presented on this page can be summarized as follows:

* **TarMK with File Datastore** is the recommended architecture for most customers:

    * Minimum topology: one Author instance, two Publish instances, two Dispatchers    
    * Binary-less replication turned on if the File Datastore is shared

* **MongoMK with File Datastore** is the recommended architecture for horizontal scalability of the Author tier:

    * Minimum topology: three Author instances, three MongoDB instances, two Publish instances, two Dispatchers    
    * Binary-less replication turned on if the File Datastore is shared

* **Nodestore** should be stored on the local disk, not a network attached storage (NAS)
* When using** Amazon S3:**

    * The Amazon S3 datastore is shared between the Author and Publish tier    
    * Binary-less replication must be turned on    
    * Datastore Garbage Collection requires a first run on all Author and Publish nodes, then a second run on Author

* **Custom index should be created in addition to the out of the box index** based on most common searches

    * Lucene indexes should be used for the custom indexes

* **Customizing workflow can substantially improve the performance**, for example, removing the video step in the “Update Asset” workflow, disabling listeners which are not used, etc.

For more details, also read the [Recommended Deployments](recommended-deploys.md) page.
