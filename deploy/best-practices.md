---
uuid: b1be849a-418c-4f72-b69a-3175aa774864
index: y
internal: n
snippet: y
translate: y
---

# Deploying Best Practices

Deploying best practices describe how to deploy or maintain AEM in the most efficient and most effective way possible. This growing list of topics includes a variety of areas in AEM.

The following areas have documentation available concerning deploying and maintaining best practices and recommendations:

* [OAK](#OAK)
* [Communities](#Communities)
* [UI](#UI)
* [Performance](#Performance)

For best practices on administering, developing, or authoring, see one of the following:

* [Administering best practices](/content/help/en/experience-manager/6-4/sites/administering/using/administer-best-practices)
* [Developing best practices](/content/help/en/experience-manager/6-4/sites/developing/using/best-practices)
* [Authoring best practices](/content/help/en/experience-manager/6-4/sites/authoring/using/best-practices)

Specific documents are described and linked to in the tables that follow.

---

## OAK
[Oak](platform.md) is a scalable and performant hierarchical content repository that is the foundation of AEM. 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><p>Scalability, Performance and Disaster Recovery</p> </td> 
   <td><a href="performance.md">Performance &amp; Scalability</a></td> 
   <td>Provides a white paper discussing the technical agility, high performance, and sound disaster recovery features</td> 
  </tr>
  <tr>
   <td>Recommended OAK deployments</td> 
   <td><a href="recommended-deploys.md">Recommended deployments</a></td> 
   <td>Describes deployment scenarios</td> 
  </tr>
  <tr>
   <td>Mongo topology</td> 
   <td><a href="recommended-deploys.md">Mongo topology best practices</a></td> 
   <td>Describes mongo topology - when to use which topology.</td> 
  </tr>
  <tr>
   <td>Datastore options</td> 
   <td><a href="data-store-config.md">Configuring node and data stores</a></td> 
   <td>This document explains best practices around storing binary data and content nodes. Includes informationon using Amazon S3 data store.</td> 
  </tr>
  <tr>
   <td>Search in OAK</td> 
   <td><a href="best-practices-for-queries-and-indexing.md">Best Practices for Queries and Indexing</a><br /> </td> 
   <td>Describes best practices on how to index content.</td> 
  </tr>
 </tbody>
</table>

---

## Communities
AEM Communities simplifies the creation and management of on-premise Communities. Best practices for AEM Communities are described here: 

| Community Content Persistence | [Community Content Store](/content/help/en/experience-manager/6-4/communities/using/working-with-srp) |Discusses the new shared storage feature for user generated content (UGC) and the considerations for choosing the underlying [topology](/content/help/en/experience-manager/6-4/communities/using/topologies). |
|---|---|---|
| Deployments for Communities | [Recommended deployments](recommended-deploys.md#ConsiderationsforAEMCommunities) |Describes the recommended deployments for Communities. |

---

## UI
Best practices around the user interface are described here: 

| Recommendations for UI selection | [User Interface Recommendations for Customers](ui-recommendations.md) |AEM currently has two UIs: classic and touch-optimized UI in the same release. Therefore customers have to make a decision about which to use during the project implementation. This document is intended to help with finding the right choice.. |
|---|---|---|

---

## Performance
Best practices around performance are listed here:

| Best Practices for Quality Assurance | [Best Practices for Quality Assurance](configuring-performance.md#BestPracticesforQualityAssurance) |A standardized overview of the issues involved with defining a Test Concept specifically for performance tests on your *publish* environment. This is primarily of interest to QA engineers, project managers and system administrators. |
|---|---|---|
| Using Dispatcher with a CDN | [Using Dispatcher with a CDN](/content/help/en/experience-manager/dispatcher/using/dispatcher#UsingDispatcherwithaCDN) |A content delivery network (CDN), such as Akamai Edge Delivery or Amazon Cloud Front, deliver content from a location close to the end user. |
| Performance Optimization | [Performance Optimization](configuring-performance.md) |A key issue is the time your website takes to respond to visitor requests. |
| Performance Testing | [Best Practices for Performance Testing](best-practices-for-performance-testing.md) |Describes best practices for running performance tests on an AEM deployment.  |

