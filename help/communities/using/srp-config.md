---
title: Storage Configuration
seo-title: Storage Configuration
description: null
seo-description: How to access the Storage Configuration Console
uuid: 49ae7ba4-180c-4e41-b299-b20e548b195f
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5624b913-96b7-400e-b5b7-643406accd4a
index: y
internal: n
snippet: y
---

# Storage Configuration{#storage-configuration}

Storage configuration is the means of identifying the storage chosen for community content, also known as user generated content (UGC).

This setting informs the AEM Communities code as to which implementation of the storage resource provider (SRP) is to be used when accessing UGC and must reflect the topology established when AEM was deployed.

For a discussion of storage options and deployment topologies, visit

* [Community Content Store](../../communities/using/working-with-srp.md)
* [Recommended Topologies](../../communities/using/topologies.md)

## Storage Configuration Console {#storage-configuration-console}

![](assets/chlimage_1-194.png)

In the author environment, to reach the storage configuration console

* from global navigation : **Tools, Communities, Storage Configuration**

To select a storage option other than the default JCR :

* select an option
* configure appropriately

    * see details for [selecting MSRP](../../communities/using/msrp.md#selectmsrp)
    * see details for [selecting DSRP](../../communities/using/dsrp.md#selectdsrp)
    * see details for [selecting ASRP](../../communities/using/asrp.md#selectasrp)

* select **Submit**

### About JCR Storage {#about-jcr-storage}

Be aware that if no selection is made, the default is the AEM repository, JCR.

JCR is *not *a common store shared by the author and publish environments. Community content will be visible only from the author or publish environment in which it was created.

Visit [JCR Store](../../communities/using/jsrp.md) for additional information.

>[!NOTE]
>
>The absence of the node `srpc`under `/etc/socialconfig` indicates the default [JCR store](../../communities/using/jsrp.md).

