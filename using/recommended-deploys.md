---
title: Recommended Deployments
seo-title: Recommended Deployments
description: null
seo-description: This article describes the recommended topologies for AEM.
uuid: 3e9e037d-4db4-47c8-9dc8-4d4d8f71b369
content-encoding: UTF-8
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/recommended-deploys
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-06-22T05 17 44.657-0400
cq-lastmodifiedby: raiman
cq-lastreplicated: 2018-06-22T05 17 44.682-0400
cq-lastreplicatedby: raiman
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: deploying
cq-template: /apps/help/templates/article-3
discoiquuid: d2d526bd-8342-43fe-a681-4b4c9c5ee823
firstPublishExternalDate: 2017-10-31T16:17:40.963-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 49.135-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-06-22T05:17:44.654-0400
lochandoffdate: 2018-04-30T03 28 00.288-0400
lr-lastreplicatedby: raiman@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Recommended Deployments
publishexternaldate: 2018-06-22T05 17 44.654-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/recommended-deploys.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/recommended-deploys
sha1: 30ad02096227c512d78e60ac9533ffe20a4b6812
topicBrowsingSortDate: 2018-06-22T05:17:44.654-0400
index: y
internal: n
snippet: y
translate: y
---

# Recommended Deployments

>[!NOTE]
>
>This page refers to recommended topologies for AEM. For more information on clustering capabilities and how to configure them, see the [Apache Sling Discovery API documentation](https://sling.apache.org/documentation/bundles/discovery-api-and-impl.html).

MicroKernels act as persistence managers in AEM 6.2. Choosing one to fit your needs depends on the purpose of your instance and the deployment type you are considering.

The below examples are meant to be an indication of what are their recommended uses in the most common AEM setups.

## Deployment scenarios

### Single TarMK Instance
In this scenario, a single TarMK instance runs on a single server.

**This is the default deployment for author instances.**

![](assets/recommended-deploys/chlimage_1.png)

The advantages:

* Simple
* Easy maintenance
* Good performance

The disadvantages:

* Not scalable beyond the limits of server capacity
* No failover capacity

### TarMK Cold Standby
One TarMK instance acts as the primary instance. The repository from the primary is replicated to a standby failover system.

The cold standby mechanism can also be used as a backup because the complete repository is constantly replicated to the failover server. The failover server is running in cold standby mode, which means that only the HttpReceiver of the instance is running.

![](assets/recommended-deploys/chlimage_1-1.png)

The advantages:

* Simplicity
* Maintainability
* Performance
* Failover

The disadvantages:

* Not scalable beyond the limits of the server capacity
* One server is idle most of the time
* The failover is not automatic. It has to be detected externally before the failover system can start serving requests.

>[!NOTE]
>
>For more info on how to configure AEM with TarMK Cold Standby, see [this](tarmk-cold-standby.md) article.

>[!NOTE]
>
>The Cold Standby deployment in this TarMK example requires that both the primary and standby instances be licensed separately, as there is constant replication to the failover server. For more information about licensing, please consult the [Adobe General Licensing Terms](https://www.adobe.com/legal/terms/enterprise-licensing.html).

### TarMK Farm
Multiple Oak instances run each with one TarMK instance. The TarMK repositories are independent and need to be kept in sync.

Keeping the repositories in sync is provided with the fact that the author server is publishing the same content to each farm member. For more information, see [Replication](replication.md).

For AEM Communities, user generated content (UGC) is never replicated. For supporting UGC on a TarMK Farm, see [considerations for AEM Communities](#ConsiderationsforAEMCommunities).

**This is the default deployment for publish environments.**

![](assets/recommended-deploys/chlimage_1-2.png)

The advantages:

* Performance
* Scalability for read access
* Failover

### Oak Cluster with MongoMK Failover for High Availability in a Single Datacenter
This approach implies multiple Oak instances accessing a MongoDB replica set within a single data center, in effect creating an active-active cluster for the AEM author environment. Replica sets in MongoDB are used to provide high availability and redundancy in the event of a hardware or network failure.

![](assets/recommended-deploys/chlimage_1-3.png)

The advantages:

* Ability to scale horizontally with new AEM author instances
* High availability, redundancy, and automated failover of data layer

The disadvantages:

* Performance can be lower than with TarMK for some scenarios

### Oak Cluster with MongoMK Failover Across Multiple Datacenters
This approach implies multiple Oak instances accessing a MongoDB replica set across multiple data centers, in effect creating an active-active cluster for the AEM author environment. With multiple data centers, MongoDB replication provides the same high availability and redundancy but now includes the ability to handle a data center outage.

![](assets/recommended-deploys/chlimage_1-4.png)  ![](assets/oakclustermongofailover2datacenters.png)

The advantages:

* Ability to scale horizontally with new AEM author instances
* High availability, redundancy, and automated failover of data layer (including data center outages)

>[!NOTE]
>
>In the diagram above, AEM Server 3 and AEM Server 4 are presented with an inactive status assuming a network latency in between the AEM Servers in Data Center 2 and the MongoDB primary node in Data Center 1 that is higher than the requirement documented [here](aem-with-mongodb.md#Checklists). If the maximum latency is compatible with the requirements, for instance through the use of availability zones, then the AEM servers in Data Center 2 can be active as well, creating an active-active AEM cluster across multiple datacenters.

>[!NOTE]
>
>For additional information on the MongoDB architectural concepts described in this section, see [MongoDB Replication](http://docs.mongodb.org/manual/replication/).

>[!NOTE]
>
>In case the arbiter needs to be hosted on platforms like Amazon Web Services, it is recommended that it is configured to only take part in the voting process, and not contain any additional data.

### Distributed Oak Cluster with MongoDB Replication
Oak instances that are placed in multiple data centers access the primary MongoDB replica for writing, both primary and secondary MongoDB replica for reading.

![](assets/recommended-deploys/chlimage_1-5.png)

The advantages:

* Scalability for read and write access
* Failover with limited capacity
* Infrastructure is fully used
* If one datacenter fails, read access is still possible from the other datacenter without any switch being performed.
* The secondary can become primary if the original primary is down, thus allowing write access in case of a data center outage.

The disadvantages:

* Complex to operate
* Writes from the second datacenter perform worse than writes from the first

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (sarchiz@adobe.com)
Last Modified Date: 2017-11-30T05:42:26.341-0500

<p>jedelson:</p> 
<p>"Distributed Oak Cluster with MongoDB Replication<br /> According to @chetanm, reading from secondaries is not supported in Oak 1.0, so why are we documenting it? It may make it into SP1, but that hasn't been announced yet."</p>

 -->

### Oak Cluster with Sharded MongoDB
Multiple Oak instances access a sharded MongoDB deployment. MongoDB provides a built-in capability for scaling horizontally called Sharding. This is typically used for data sets that scale beyond the capacity of a single replica set. Sharded deployments of MongoDB are built to leverage the same high availability and redundancy characteristics provided by a replica set while also supporting linear scaling of reads and writes.

![](assets/recommended-deploys/chlimage_1-6.png)

The advantages:

* Ability to scale AEM instances
* Horizontal scalability of data layer
* Supports geographically distributed AEM deployments

>[!NOTE]
>
>The ability to read from MongoDB secondaries will only be available with AEM 6.0 SP1. In order to have this functionality, make sure you update your AEM instance accordingly.

#### CRX 2 Legacy Clustering
In case there are requirements that do not allow you to switch to the new Oak based repository architecture, CRX 2 clustering will still be supported in AEM 6.0. In order to enable it, you need to:

1. [Upgrade to AEM 6](https://docs.adobe.com/content/docs/en/aem/6-0/deploy/upgrade.html) without converting the repository to Oak.
1. [Configure clustering](https://docs.adobe.com/content/docs/en/aem/6-0/deploy/configuring/cluster.html) if necessary.

## Microkernels: which one to use
The basic rule that needs to be taken into account when choosing between the two available micro kernels is that TarMK is designed for performance, while MongoMK is used for scalability.

You can use these decision matrices in order to establish what is the best type of deployment suited to your requirements.

Adobe highly recommends TarMK to be the default persistence technology used by customers in all deployment scenarios, for both the AEM Author and Publish instances, except in the use cases outlined below.

### Exceptions for choosing AEM MongoMK over TarMK on Author Instances
The primary reason for choosing the MongoMK persistence backend over TarMK is to scale the instances horizontally. This means having two or more active author instances running at all times and using MongoDB as the persistence storage system. The need to run more than one author instance results generally from the fact that the CPU and memory capacity of a single server, supporting all concurrent authoring activities, is no longer sustainable.

It is almost impossible to predict what the exact concurrency model will be after a new site goes live. Therefore, Adobe recommends you consider the following criteria when evaluating whether to use MongoMK and two or more Author active nodes:

1. Number of named users connected in a day: in the thousands or more.
1. Number of concurrent users: in the hundreds or more.
1. Volume of asset ingestions per day: in hundreds of thousands or more.
1. Volume of page edits per day: in hundreds of thousands or more (including automated updates via Multi Site Manager or news feed ingestions for example).
1. Volume of searches per day: in tens of thousands or more.

>[!NOTE]
>
>Tough Day can be used to evaluate the performance of the customer’s application in the context of the hardware configuration deployed. More information about this tool is available [here](/content/help/en/experience-manager/6-4/sites/developing/using/tough-day).

A minimum deployment with MongoDB will typically involve the following topology:

* A MongoDB replica set consisting of one primary node, two secondary nodes with each of the MongoDB instances running in an availability zone with a latency under 15 milliseconds across each node;  
* A cluster of author instances with one leader node, one non-leader node and both active at all time, with each of the author instances running in each of the datacenters, where the MongoDB primary and secondary instances are running.

Additionally, it is highly recommended to configure the datastore on a shared file system or Amazon S3, such that the assets or binaries are not stored within MongoDB. This will ensure optimal performance within the deployment.

One of the additional benefits of deploying a MongoDB replica set with a cluster of two or more author instances is having an automated recovery scenario with minimal downtime in case of an author instances, MongoDB replica or a complete datacenter failure. Nonetheless, the choice of MongoMK over TarMK should not be solely driven by the recovery requirement, as TarMK can also provide a minimal downtime solution with a controlled failover mechanism.

If the above criteria are not expected to be met during the first eighteen months of deployment, it is encouraged to first deploy AEM using TarMK, then re-evaluate your configuration at a later date when the above criteria apply, and finally determine whether to remain on TarMK or migrate to MongoMK.

### Exceptions for choosing AEM MongoMK over TarMK on Publish Instances
It is not recommended to deploy MongoMK for publish instances. The publish tier of the deployment is almost always deployed as a farm of fully independent publish instances running TarMK, which are kept in sync by replicating content from the author instances. This "shared nothing" architecture, proper to the publish instances, allows the deployment of the publish tier to scale horizontally in a linear fashion. The farm topology also provides the benefit of applying any update or upgrade to publish instances on a rolling basis, such that any change to the publish tier will not require any downtime.

This does not apply to AEM Communities using MongoMK clusters on the publish tier whenever there's more than one publisher. If choosing JSRP (see [Community Content Storage](/content/help/en/experience-manager/6-4/communities/using/working-with-srp)), then a MongoMK cluster would be appropriate, as would any publish side cluster regardless of the MK chosen, such as MongoDB or RDB.

### Prerequisites and Recommendations when deploying AEM with MongoMK
A set of prerequisites and recommendations is available if you are considering a MongoMK deployment for AEM:

**Mandatory prerequisites for MongoDB deployments:**

1. MongoDB deployment architecture and sizing must be part of the project implementation with help from Adobe Consulting or MongoDB Architects who are familiar with AEM;
1. MongoDB expertise must be present within the partner or customer team in order to have confidence in being able to sustain and maintain an existing or new MongoDB environment;
1. You may choose to deploy the commercial or open source version of MongoDB (AEM supports both), but must purchase a MongoDB Maintenance and Support contract directly from MongoDB Inc;
1. Overall AEM and MongoDB architectures and infrastructures should be well defined and validated by an Adobe AEM Architect;
1. You must review the support model for AEM deployments that include MongoDB.

**Strong recommendations for MongoDB deployments:**

* Consult the MongoDB for Adobe Experience Manager [article](https://www.mongodb.com/lp/contact/mongodb-adobe-experience-manager);
* Review the MongoDB production [checklist](http://docs.mongodb.org/manual/administration/production-checklist/);
* Attend a certification class on MongoDB available online [here](https://university.mongodb.com/).

>[!NOTE]
>
>For all additional questions about these guidelines, prerequisites, and recommendations please contact [Adobe Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html).

### Considerations for AEM Communities
For sites which plan to deploy [AEM Communities](/content/help/en/experience-manager/6-4/communities/using/overview), it is recommended to [choose a deployment](/content/help/en/experience-manager/6-4/communities/using/working-with-srp#CharacteristicsofStorageOptions) optimized for handling UGC posted by community members from the publish environment.

By using a [common store](/content/help/en/experience-manager/6-4/communities/using/working-with-srp), UGC does not need to be replicated between author and other publish instances in order to obtain a consistent view of the UGC.

Below are a set of decisional matrices that can assist you in choosing the best type of persistence for your deployment:

#### Choosing the deployment type for author instances
![](assets/recommended-deploys/chlimage_1-7.png) 

#### Choosing the deployment type for publish instances
![](assets/recommended-deploys/chlimage_1-8.png) 

#### TarMK with Cloud Storage
Based on the Tar micro kernel for persistence management, it uses a separate cloud storage for all the user generated content.

**This deployment is recommended for sites with high volumes of user generated content (millions of posts per year).**

More information is available regarding the Adobe Social Common Store [here](/content/help/en/experience-manager/6-4/communities/using/working-with-srp).

![](assets/recommended-deploys/chlimage_1-9.png) 

#### MongoMK with Active/Active Cluster
Based on the Mongo micro kernel, all the user generated content is centrally stored inside a Mongo instance.

**This deployment is recommended for sites that have a high business impact and normal user generated content volumes. This generally includes enterprise community platforms and B2B websites.**

**Also note that this deployment is currently designed for Communities. Using it for other purposes needs upfront analysis.**

More information is available regarding the Mongo Common Store [here](/content/help/en/experience-manager/6-4/communities/using/working-with-srp).

![](assets/recommended-deploys/chlimage_1-10.png)

>[!NOTE]
>
>MongoDB is third-party software and is not included in the AEM licensing package. For more information see the [MongoDB licensing policy](http://www.mongodb.org/about/licensing/) page.
>
>In order to get the most of your AEM deployment, Adobe recommends licensing the MongoDB Enterprise version in order to benefit from professional support.
>
>The license includes a standard replica set, which is composed of one primary and two secondary instances that can be used for either the author or the publish deployments.
>
>In case you wish to run both author and publish on MongoDB, two separate licenses need to be purchased.
>
>For more information, see the [MongoDB for Adobe Experience Manager page](https://www.mongodb.com/lp/contact/mongodb-adobe-experience-manager).

