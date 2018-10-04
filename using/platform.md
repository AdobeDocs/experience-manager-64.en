---
title: Introduction to the AEM Platform
seo-title: Introduction to the AEM Platform
description: null
seo-description: This article provides a general overview of the AEM platform and its most important components.
uuid: 7c40f27a-3274-4262-8e98-a3570fb90e0d
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/platform
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 22.537-0400
cq-lastmodifiedby: msm-service
cq-lastreplicated: 2018-04-03T08 43 02.426-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: c904ec67-f18e-406f-9d2c-fb11a2317760
firstPublishExternalDate: 2017-10-31T16:17:47.896-0400
isreadyforlocalization: false
jcr-created: 2018-01-05T19 01 42.436-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:01.428-0400
legacypath: /content/docs/en/aem/6-0/deploy/upgrade/introduction-to-oak
lochandoffdate: 2018-04-30T03 27 22.536-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Introduction to the AEM Platform
publishexternaldate: 2018-04-03T08 43 01.428-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/platform.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/platform
sha1: dc2e3e72829b12fd70374225802762c312ca81fb
topicBrowsingSortDate: 2018-04-03T08:43:01.428-0400
index: y
internal: n
snippet: y
translate: y
---

# Introduction to the AEM Platform

The AEM platform in AEM 6 is based on Apache Jackrabbit Oak.

Apache Jackrabbit Oak is an effort to implement a scalable and performant hierarchical content repository for use as the foundation of modern world-class web sites and other demanding content applications.

It is the successor to Jackrabbit 2 and is used by AEM 6 as the default backend for its content repository, CRX.

## Design principles and goals
Oak implements the [JSR-283](http://www.day.com/day/en/products/jcr/jsr-283.html) (JCR 2.0) spec. Its principal design objectives are:

* Better support for big repositories
* Multiple distributed cluster nodes for high availability
* Better performance
* Support for many child nodes and Access Control Levels

## Architecture Concept
![](assets/chlimage_1.png)

#### Storage
The purpose of the Storage layer is to:

* Implement a tree model
* Make storage pluggable
* Provide a clustering mechanism

#### Oak Core
The Oak Core adds several layers to the storage layer:

* Access Level Controls
* Search and Indexing
* Observation

#### Oak JCR
The main objective of the Oak JCR is to transform JCR semantics into tree operations. It is also responsible for:

* Implementing the JCR API
* Containing commit hooks that implement JCR constraints

In addition, non-Java implementations are now possible and part of the Oak JCR concept.

## Storage overview
The Oak storage layer provides an abstraction layer for the actual storage of the content.

Currently, there are two storage implementations available in AEM6: **Tar Storage** and **MongoDB Storage**.

#### Tar Storage
The Tar storage uses tar files. It stores the content as various types of records within larger segments. Journals are used to track the latest state of the repository.

There are several key design principles it was build around:

* **Immutable Segments**

The content is stored in segments that can be up to 256KiB in size. They are immutable, which makes it easy to cache frequently accessed segments and reduce system errors that may corrupt the repository.

Each segment is identified by a unique identifier (UUID) and contains a continuous subset of the content tree. In addition, segments can reference other content. Each segment keeps a list of UUIDs of other referenced segments.

* **Locality**

Related records like a node and its immediate children are usually stored in the same segment. This makes searching the repository very fast and avoids most cache misses for typical clients that access more than one related node per session.

* **Compactness**

The formatting of records is optimized for size to reduce IO costs and to fit as much content in caches as possible.

#### Mongo Storage
The MongoDB storage leverages MongoDB for sharding and clustering. The repository tree is kept in one MongoDB database where each node is a separate document.

It has several particularities:

* Revisions

For each update (commit) of the content, a new revision is created. A revision is basically a string that consists of three elements:

1. A timestamp derived from the system time of the machine it was generated on
1. A counter to distinguish revisions created with the same timestamp
1. The cluster node id where the revision was created

* Branches

Branches are supported, which allows client to stage multiple changes and make them visible with a single merge call.

* Previous documents

MongoDB storage adds data to a document with every modification. However, it only deletes data if a cleanup is explicitly triggered. Old data is moved when a certain threshold is met. Previous documents only contain immutable data, which means they only contain committed and merged revisions.

* Cluster node metadata

Data about active and inactive cluster nodes is kept in the database in order to facilitate cluster operations.

A typical AEM cluster setup with MongoDB storage:

![](assets/chlimage_1.png)

## What is different from Jackrabbit 2?
Because Oak is designed to be backwards compatible with the JCR 1.0 standard, there will be almost no changes on the user level. However, there are some noticeable differences that you need to take into account when setting up an Oak based AEM installation:

* Oak does not create indexes automatically. Because of this, custom indexes will need to be created when necessary.  

* Unlike Jackrabbit 2 where sessions always reflect the latest state of the repository, with Oak a session reflects a stable view of the repository from the time the session was acquired. This is due to the MVCC model on which Oak is based on.
* Same name siblings (SNS) are not supported in Oak.

## Other Platform Related Documentation
For more information regarding the AEM platform, also check the articles below:

* [Configuring Node Stores and Data Stores in AEM 6](data-store-config.md)
* [Oak Queries and Indexing](queries-and-indexing.md)
* [Storage Elements in AEM 6](storage-elements-in-aem-6.md)
* [AEM with MongoDB](aem-with-mongodb.md)

