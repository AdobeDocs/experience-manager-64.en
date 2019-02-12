---
title: AEM to Creative Cloud Folder Sharing Best Practices
seo-title: AEM to Creative Cloud Folder Sharing Best Practices
description: Configure Adobe Experience Manager (AEM) to allow users in AEM Assets to exchange folders with Adobe Creative Cloud (CC) users.
seo-description: Configure Adobe Experience Manager (AEM) to allow users in AEM Assets to exchange folders with Adobe Creative Cloud (CC) users.
uuid: f71fa9a6-5709-44b6-88dc-be949bf17f08
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 2c00f8d3-2ca6-4f0e-8048-83cbc637a305
index: y
internal: n
snippet: y
---

# AEM to Creative Cloud Folder Sharing Best Practices{#aem-to-creative-cloud-folder-sharing-best-practices}

Adobe Experience Manager (AEM) can be configured to allow users in AEM Assets to share folders with Creative Cloud (CC) users, so they are available as shared folders in the Creative Cloud Assets service. The feature can be used to exchange files between creative teams and AEM Assets users, especially when the creative users do not have access to the AEM Assets instance (they are not on the enterprise network).

This type of integration can be used in both the use cases, especially when working with users who do not have direct access to AEM Assets:

* Sharing a set of specific Assets from AEM Assets with Creative Cloud Files users (for example, a creative brief and set of approved assets for design work for a new marketing activity)
* Receiving new files from CC users.

>[!NOTE]
>
>Before reading this document, you can review the overall [AEM and Creative Cloud integration best practices](../../assets/using/aem-cc-integration-best-practices.md) for a higher-level overview of the topic.

## Overview {#overview}

AEM to CC folder sharing relies on the server-side sharing of folders and files between AEM Assets and Creative Cloud accounts. Creative professionals, who use the Creative Cloud Desktop app on their desktops, can additionally make the shared folders available directly on their disks using Adobe CreativeSync technology.

The following diagram provides an overview of the integration.

![](assets/chlimage_1-366.png)

The integration includes the following elements:

* **AEM Assets server** deployed in the enterprise network (managed services or on-premise): Folder sharing is initiated here.
* **Adobe Marketing Cloud Assets core service**: Acts as an intermediary between AEM and Creative Cloud storage services. Admin of the company using the integration needs to established trust relationship between the Marketing Cloud organization and the AEM Assets instance. They also [define a list of approved CC collaborators](https://marketing.adobe.com/resources/help/en_US/mcloud/t_admin_add_cc_user.html), that AEM Assets users can share folders too for additional security.

* **Creative Cloud Assets web services** (storage and CC Files web UI): This is where specific CC users, with whom an AEM Assets folder was shared, would be able to accept the invitation and see the folder in their CC account storage.
* **Creative Cloud Desktop App**: (Optional) Allows for direct access to shared folder/files from creative user’s desktop via sync with CC Assets storage.

## Characteristics and limitations {#characteristics-and-limitations}

* **One-way propagation of changes:** File changes are propagated in one direction only - from the system (AEM or CC Assets), where the asset was originally created (uploaded). The integration does not provide a fully automated, two-way synchronization between the two systems.
* **Versioning:**

    * AEM only creates versions of an asset on updates if the file originated in AEM and is updated there.
    * CC Assets provides its own [versioning feature](https://helpx.adobe.com/creative-cloud/help/versioning-faq.html) that is targeted at Work in Progress updates (basically, stores updates for up to 10 days)

* **Space limitations:** Sizes and volumes of files exchanged is limited by the specific [CC Assets quota](https://helpx.adobe.com/creative-cloud/kb/file-storage-quota.html) for creative users (depends on subscription level) and a limitation of 5GB maximum file size. Space is additionally limited by the asset quota that the organization has in Adobe Marketing Cloud Assets core service.

* **Space requirements:** The files in shared folders also need to be physically stored in AEM and then in CC account, with a cached copy in Marketing Cloud Assets core service.
* **Networking and bandwidth:** The files in shared folders and all the updates need to be transported over the network between the systems. You should ensure that only relevant files and updates are shared.
* **Folder type**: Sharing an Assets folder of the type `sling:OrderedFolder`, is not supported. If you want to share a folder, when creating it in AEM Assets, do not select the Ordered option.

## Best practices {#best-practices}

Best practices for leveraging the AEM to CC folder sharing include:

* **Volume considerations:** AEM/CC Folder Sharing should be used to share smaller number of files, for example, relevant to a specific campaign or activity. To share larger sets of assets, like all approved assets in the organization, use other distribution methods (for example, AEM Assets Brand Portal) or AEM Desktop App.

* **Avoid sharing deep hierarchies:** The sharing works recursively and does not allow for selective unsharing. Typically, only folders without subfolders, or with a very shallow hierarchy, like 1 subfolder level, should be considered for sharing.
* **Separate folders for one-way sharing:** Separate folders should be used for sharing final assets from AEM Assets to Creative Cloud files, and for sharing creative-ready assets back from Creative Cloud files to AEM Assets. Together with a good naming convention for these folders, it creates an easier-to-understand working environment for AEM Assets and CC users alike.
* **Avoid WIP in the shared folder:** Shared folder should not be used for Work in Progress - use a separate folder in CC Files to carry out work that requires frequent changes to the file.
* **Start new work outside of shared folder:** New designs (creative files) should be started in the separate WIP folder in CC Files, and when they are ready to be shared with AEM Assets users, they should be moved or saved to the shared folder.
* **Simplify sharing structure:** For a more manageable operating set up, think about simplifying the sharing structure. Instead of sharing with all creative users, AEM Assets folders should be shared with team representative(s) only, like a creative director or team manager. The manager on the creative side would receive final assets, decide on work assignments, and then let designers work in their own CC accounts on WIP assets. They can use CC collaboration features to coordinate the work, and finally select and put assets that are ready to share back to AEM Assets into their creative-ready shared folder.

The following diagram illustrates an example configuration for creating new designs based on existing final assets from AEM Assets.

![](assets/chlimage_1-367.png)

