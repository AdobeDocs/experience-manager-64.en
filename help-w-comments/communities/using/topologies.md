---
title: Recommended Topologies for Communities
seo-title: Recommended Topologies for Communities
description: How to approach the handling of user-generated content (UGC)
seo-description: How to approach the handling of user-generated content (UGC)
uuid: 6c55704e-92f8-45e2-9078-f9505cb311b0
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: eef9ac57-5516-4577-9e5a-b15ed53ad92c
index: y
internal: n
snippet: y
---

# Recommended Topologies for Communities{#recommended-topologies-for-communities}

As of AEM Communities 6.1, a unique approach has been adopted for handling user generated content (UGC) submitted by site visitors (members) from the publish environment.

This approach is fundamentally different from the way the AEM platform handles site content that is generally managed from the author environment.

The AEM platform uses a node store that replicates site content from author to publish, while AEM Communities uses a single, common store for UGC that is never replicated.

For the common UGC store, it is necessary to choose a [storage resource provider (SRP)](../../communities/using/working-with-srp.md). The recommended choices are:

* [DSRP - Relational Database Storage Resource Provider](../../communities/using/dsrp.md)
* [MSRP - MongoDB Storage Resource Provider](../../communities/using/msrp.md)
* [ASRP - Adobe Storage Resource Provider](../../communities/using/asrp.md)

One other SRP option, [JSRP - JCR Storage Resource Provider](../../communities/using/jsrp.md), does not support a common UGC store for the author and publish environments to both access.

Requiring a common store results in the following recommended topologies.

>[!NOTE]
>
>For AEM Communities, [UGC is never replicated](../../communities/using/working-with-srp.md#ugcneverreplicated). 
>
>When the deployment does not include a [common store](../../communities/using/working-with-srp.md), UGC will be visible only on the AEM publish or author instance on which it was entered.

>[!NOTE]
>
>For more information on the AEM platform, see [Recommended Deployments](../../sites/deploying/using/recommended-deploys.md) and [Introduction to the AEM Platform](../../sites/deploying/using/data-store-config.md).

### For Production {#for-production}

Establishing a common store for UGC is essential, and thus the underlying deployment is contingent on its ability to support a common store.

Two examples :

1) If the expected volume of UGC is high and a local MongoDB instance is possible, then the choice would be [MSRP](../../communities/using/msrp.md).

2) For optimal performance for page content, the choice of a [publish farm](../../sites/deploying/using/recommended-deploys.md#tarmkfarm) and [ASRP](../../communities/using/asrp.md) would provide optimal scaling of UGC with relatively straightforward operations.

For both, the deployment may be based on any OAK microkernel.

To choose the appropriate common store, carefully consider the unique [characteristics](../../communities/using/working-with-srp.md#srpoptionscharacteristics) of each.

For more details on Oak microkernals, visit [Recommended Deployments](../../sites/deploying/using/recommended-deploys.md).

#### TarMK Publish Farm {#tarmk-publish-farm}

When the topology is a publish farm, relevant topics of importance are

* [User Synchronization](../../communities/using/sync.md)
* [Managing Users and User Groups](../../communities/using/users.md)

#### Recommended : DSRP, MSRP or ASRP {#recommended-dsrp-msrp-or-asrp}

<table border="1" cellpadding="2" cellspacing="2" width="100%"> 
 <tbody>
  <tr>
   <td style="text-align: center;">MicroKernel</td> 
   <td style="text-align: center;">SITE CONTENT<br /> REPOSITORY</td> 
   <td style="text-align: center;">USER GENERATED CONTENT<br /> REPOSITORY</td> 
   <td style="text-align: center;">STORAGE RESOURCE PROVIDER</td> 
   <td style="text-align: center;">COMMON STORE </td> 
  </tr>
  <tr>
   <td style="text-align: center;">any</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">MySQL</td> 
   <td style="text-align: center;">DSRP</td> 
   <td style="text-align: center;">Yes</td> 
  </tr>
  <tr>
   <td style="text-align: center;">any</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">MongoDB</td> 
   <td style="text-align: center;">MSRP</td> 
   <td style="text-align: center;">Yes</td> 
  </tr>
  <tr>
   <td style="text-align: center;">any</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">Adobe on-demand<br /> storage</td> 
   <td style="text-align: center;">ASRP</td> 
   <td style="text-align: center;">Yes</td> 
  </tr>
 </tbody>
</table>

#### JSRP {#jsrp}

<table border="1" cellpadding="2" cellspacing="2" width="100%"> 
 <tbody>
  <tr>
   <td style="text-align: center;">Deployment</td> 
   <td style="text-align: center;">SITE CONTENT<br /> REPOSITORY</td> 
   <td style="text-align: center;">USER GENERATED CONTENT<br /> REPOSITORY</td> 
   <td style="text-align: center;">STORAGE RESOURCE PROVIDER</td> 
   <td style="text-align: center;">COMMON STORE </td> 
  </tr>
  <tr>
   <td style="text-align: center;">TarMK Farm (default)</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">JSRP</td> 
   <td style="text-align: center;">No<br /> </td> 
  </tr>
  <tr>
   <td style="text-align: center;">Oak Cluster</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">JCR</td> 
   <td style="text-align: center;">JSRP</td> 
   <td style="text-align: center;">Yes<br /> for publish environment only</td> 
  </tr>
 </tbody>
</table>

### For Development {#for-development}

For non-production environments, [JSRP](../../communities/using/jsrp.md) provides simplicity in setting up a development environment with one author instance and one publish instance.

If choosing [ASRP](../../communities/using/asrp.md), [DSRP](../../communities/using/dsrp.md) or [MSRP](../../communities/using/msrp.md) for production, it is also possible to setup a similar development environment using Adobe on-demand storage or MongoDB. For an example, see [HowTo Setup MongoDB for Demo](../../communities/using/demo-mongo.md).

### References {#references}

* [User Synchronization](../../communities/using/sync.md)  
  Discusses scynchronization of user data among publish farm instances.

* [Managing Users and User Groups](../../communities/using/users.md)  
  Discusses the roles of users and user groups in the author and publish environments.

* UGC [common store](../../communities/using/working-with-srp.md)  
  Describes the storage of community content separate from site content

* [Node Stores and Data Stores](../../sites/deploying/using/data-store-config.md)  
  Basically, site content is stored in a node store. For Assets, a data store can be configured to store binary data. For Communities, a common store must be configured to select the SRP.

* [Storage Elements in AEM 6.3](../../sites/deploying/using/storage-elements-in-aem-6.md)  
  Describes the two node storage implementations : Tar and MongoDB.

