---
title: Storage Resource Provider Overview
seo-title: Storage Resource Provider Overview
description: Common storage for Communities
seo-description: Common storage for Communities
uuid: b409285f-5902-4716-be8a-9bae5afc3e81
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7ad7e2e3-3834-4a6d-b13f-9f5abd817109
index: y
internal: n
snippet: y
---

# Storage Resource Provider Overview{#storage-resource-provider-overview}

## Introduction {#introduction}

As of AEM Communities 6.1, community content, commonly referred to as user generated content (UGC), is stored in a single, common store provided by a [storage resource provider](../../communities/using/working-with-srp.md) (SRP).

There are several SRP options, all of which access UGC through a new AEM Communities interface, the [SocialResourceProvider API](../../communities/using/srp-and-ugc.md) (SRP API), which includes all create, read, update, and delete (CRUD) operations.

All SCF components are implemented using the SRP API, allowing code to be developed without knowledge of either the [underlying topology](../../communities/using/topologies.md) or location of UGC.

***The SocialResourceProvider API is available only to licensed customers of AEM Communities.***

>[!NOTE]
>
>**Custom Components** : For licensed customers of AEM Communities, the SRP API is available to developers of custom components for the purpose of accessing UGC without regard to the underlying topology. See [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md).

See also :

* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

## About the Repository {#about-the-repository}

To understand SRP, it is helpful to understand the role of the AEM repository (OAK) in an AEM community site.

**Java Content Repository (JCR)** 
This standard defines a data model and application programming interface ([JCR API](http://jackrabbit.apache.org/jcr/jcr-api.html)) for content repositories. It combines characteristics of conventional file systems with those of relational databases, and adds a number of additional features that content applications often need.

One implementation of JCR is the AEM repository, OAK.

**Apache Jackrabbit Oak (OAK)** 
[OAK](../../sites/deploying/using/platform.md) is an implementation of JCR 2.0 that is a data storage system specifically designed for content-centric applications. It is a type of hierarchical database designed for unstructured and semi-structured data. The repository stores not only the user-facing content but also all code, templates and internal data used by the application. The UI for accessing content is [CRXDE Lite](../../sites/developing/using/developing-with-crxde-lite.md).

Both JCR and OAK are typically used to refer to the AEM repository.

After developing site content in the private author environment, it must by copied to the public publish environment. This is often done through an operation called * [replication](../../communities/using/deploy-communities.md#replicationagentsonauthor)*. This happens under control of the author/developer/administrator.

For UGC, the content is entered by registered site visitors (community members) in the public publish environment. This happens randomly.

For purposes of management and reporting, it is useful to have access to UGC from the private author environment. With SRP, access to UGC from author is more consistent and performant as reverse replication from publish to author is not necessary.

## About SRP {#about-srp}

When UGC is saved to shared storage, there is a single instance of member content that may, in most deployments, be accessed from both the author and publish environments. Regardless of SRP choice (MSRP, ASRP, JSRP), all must be accessed programmatically with the SRP API.

>[!NOTE]
>
>See [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) for sample code and additional details.
>
>See [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) for best practices when coding.

### ASRP {#asrp}

In the case of ASRP, UGC is not stored in JCR, it is stored in a cloud service hosted and managed by Adobe. UGC stored in ASRP may neither be viewed with CRXDE Lite nor accessed using the JCR API.

See [ASRP - Adobe Storage Resource Provider](../../communities/using/asrp.md).

It is not possible for developers to access the UGC directly.

ASRP uses Adobe cloud for queries.

### MSRP {#msrp}

In the case of MSRP, UGC is not stored in JCR, it is stored in MongoDB. UGC stored in MSRP may neither be viewed with CRXDE Lite nor accessed using the JCR API.

See [MSRP - MongoDB Storage Resource Provider](../../communities/using/msrp.md).

While MSRP is comparable to ASRP, as all AEM server instances are accessing the same UGC, it is possible to use common tools to directly access the UGC stored in MongoDB.

MSRP uses Solr for queries.

### JSRP {#jsrp}

JSRP is the default provider for accessing all UGC on a single AEM instance. It provides the ability to quickly experience AEM Communities 6.1 without the need for setting up MSRP or ASRP.

See [JSRP - JCR Storage Resource Provider](../../communities/using/jsrp.md).

In the case of JSRP, while UGC is stored in JCR, and accessible via both CRXDE Lite and JCR API, it is strongly recommended that JCR API never be used to do so, else future changes may affect custom code.

Further, the repository for the author and publish environments is not shared. While a cluster of publish instances results in a shared publish repository, UGC entered on publish will not be visible on author, hence no ability to manage UGC from author. UGC is only persisted in the AEM repository (JCR) of the instance on which it was entered.

JSRP uses the Oak indices for queries.

## About Shadow Nodes in JCR {#about-shadow-nodes-in-jcr}

Shadow nodes, which mimic the path to UGC, exist in the local repository to serve two purposes :

1. [Access Control (ACLs](#foraccesscontrolacls))
1. [Non-Existing Resources (NERs)](#fornonexistingresourcesners)

Regardless of SRP implementation, the actual UGC will *not *be visible at the same location as the shadow node.

### For Access Control (ACLs) {#for-access-control-acls}

Some SRP implementations, such as ASRP and MSRP, store community content in databases which provide no ACL verification. Shadow nodes provide a location in the local repository to which ACLs can be applied.

Using the SRP API, all SRP options perform the same check of the shadow location prior to all CRUD operations.

The ACL check uses an utility method that returns a path suitable for checking the permissions applied to the resource's UGC.

See [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) for sample code.

### For Non-Existing Resources (NERs) {#for-non-existing-resources-ners}

Some Communities components are includable within a script and thus require a Sling addressable node to support Communities features. [Included components](../../communities/using/scf.md#addorincludeacommunitiescomponent) are referred to as non-existing resources (NERs).

Shadow nodes provide a Sling addressable location in the repository.

>[!CAUTION]
>
>As the shadow node has multiple uses, the presence of a shadow node does *not* imply that the component is a NER.

### Storage Location {#storage-location}

Following is an example of a shadow node, using the [Comments component](http://localhost:4502/content/community-components/en/comments.html) in the [Community Components Guide](../../communities/using/components-guide.md) :

* the component exists in the local repository at :  
  /content/community-components/en/comments/jcr:content/content/includable/comments
* 
* the corresponding shadow node exists in the local repository at :  
  /content/usergenerated/content/community-components/en/comments/jcr:content/content/includable/comments

No UGC will be found under the shadow node.

The default behavior is to set up shadow nodes on a publish instance whenever the relevant subtree is referenced for a read or write.

As an example, suppose the deployment is [MSRP](../../communities/using/msrp.md) with a TarMK publish farm.

When a [member](../../communities/using/users.md) posts UGC on pub1 (stored in MongoDB), shadow nodes are created in JCR on pub1.

The first time the UGC is read on pub2, if nothing is set up, the default behavior is to create the shadow nodes.

If other than the default behavior is desired, it must be set up on the author instance and rolled forward to all publish instances, which is typically a manual process.
