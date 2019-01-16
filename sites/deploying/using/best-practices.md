---
title: Deploying Best Practices
seo-title: Deploying Best Practices
description: null
seo-description: Deploying and maintaining best practices.
uuid: 2683fb70-9f79-452f-959a-e22c6cbf0c66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 66dfe54d-064e-4b3c-aa78-4b87136d0e13
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Deploying Best Practices{#deploying-best-practices}

Deploying best practices describe how to deploy or maintain AEM in the most efficient and most effective way possible. This growing list of topics includes a variety of areas in AEM.

The following areas have documentation available concerning deploying and maintaining best practices and recommendations:

* [OAK](#oak)
* [Communities](#communities)
* [UI](#ui)
* [Performance](#performance)

For best practices on administering, developing, or authoring, see one of the following:

* [Administering best practices](../../administering/using/administer-best-practices.md)
* [Developing best practices](../../developing/using/best-practices.md)
* [Authoring best practices](../../authoring/using/best-practices.md)

Specific documents are described and linked to in the tables that follow.

## OAK {#oak}

[Oak](../../deploying/using/platform.md) is a scalable and performant hierarchical content repository that is the foundation of AEM. 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><p>Scalability, Performance and Disaster Recovery</p> </td> 
   <td><a href="../../deploying/using/performance.md">Performance &amp; Scalability</a></td> 
   <td>Provides a white paper discussing the technical agility, high performance, and sound disaster recovery features</td> 
  </tr>
  <tr>
   <td>Recommended OAK deployments</td> 
   <td><a href="../../deploying/using/recommended-deploys.md">Recommended deployments</a></td> 
   <td>Describes deployment scenarios</td> 
  </tr>
  <tr>
   <td>Mongo topology</td> 
   <td><a href="../../deploying/using/recommended-deploys.md">Mongo topology best practices</a></td> 
   <td>Describes mongo topology - when to use which topology.</td> 
  </tr>
  <tr>
   <td>Datastore options</td> 
   <td><a href="../../deploying/using/data-store-config.md">Configuring node and data stores</a></td> 
   <td>This document explains best practices around storing binary data and content nodes. Includes informationon using Amazon S3 data store.</td> 
  </tr>
  <tr>
   <td>Search in OAK</td> 
   <td><a href="../../deploying/using/best-practices-for-queries-and-indexing.md">Best Practices for Queries and Indexing</a><br /> </td> 
   <td>Describes best practices on how to index content.</td> 
  </tr>
 </tbody>
</table>

## Communities {#communities}

AEM Communities simplifies the creation and management of on-premise Communities. Best practices for AEM Communities are described here:

| Community Content Persistence | [Community Content Store](/content/help/en/experience-manager/6-4/communities/using/working-with-srp) |Discusses the new shared storage feature for user generated content (UGC) and the considerations for choosing the underlying [topology](/content/help/en/experience-manager/6-4/communities/using/topologies). |
|---|---|---|
| Deployments for Communities | [Recommended deployments](../../deploying/using/recommended-deploys.md#considerationsforaemcommunities) |Describes the recommended deployments for Communities. |

## UI {#ui}

Best practices around the user interface are described here:

| Recommendations for UI selection | [User Interface Recommendations for Customers](../../deploying/using/ui-recommendations.md) |AEM currently has two UIs: classic and touch-optimized UI in the same release. Therefore customers have to make a decision about which to use during the project implementation. This document is intended to help with finding the right choice.. |
|---|---|---|

## Performance {#performance}

Best practices around performance are listed here:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Best Practices for Quality Assurance</td> 
   <td><a href="../../deploying/using/configuring-performance.md#bestpracticesforqualityassurance">Best Practices for Quality Assurance</a></td> 
   <td>A standardized overview of the issues involved with defining a Test Concept specifically for performance tests on your <em>publish</em> environment. This is primarily of interest to QA engineers, project managers and system administrators.</td> 
  </tr>
  <tr>
   <td>Using Dispatcher with a CDN</td> 
   <td><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher#UsingDispatcherwithaCDN">Using Dispatcher with a CDN</a></td> 
   <td>A content delivery network (CDN), such as Akamai Edge Delivery or Amazon Cloud Front, deliver content from a location close to the end user.</td> 
  </tr>
  <tr>
   <td>Performance Optimization</td> 
   <td><a href="../../deploying/using/configuring-performance.md">Performance Optimization</a></td> 
   <td>A key issue is the time your website takes to respond to visitor requests.</td> 
  </tr>
  <tr>
   <td>Performance Testing</td> 
   <td><a href="../../deploying/using/best-practices-for-performance-testing.md">Best Practices for Performance Testing</a></td> 
   <td>Describes best practices for running performance tests on an AEM deployment.<br /> </td> 
  </tr>
 </tbody>
</table>

