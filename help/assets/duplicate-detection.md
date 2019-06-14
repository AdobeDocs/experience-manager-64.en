---
title: Enabling Duplicate Detection
seo-title: Enabling Duplicate Detection
description: Learn how to enable the detection of duplicate assets in AEM.
seo-description: Learn how to enable the detection of duplicate assets in AEM.
uuid: 7a71c508-14c4-4d15-98bd-cd00b07ef91e
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 3bba2c24-cae7-43e3-814f-0b703ca9d708
---

# Enabling Duplicate Detection {#enabling-duplicate-detection}

Learn how to enable the detection of duplicate assets in AEM.

If you attempt to upload an asset that already exists in Adobe Experience Manager (AEM) Assets, the Duplicate Detection feature identifies it as duplicate.

Duplicate Detection is disabled by default. To enable the feature, perform the following steps:

1. Open **Adobe Experience Manager Web Console Configuration**. You can access it at `https://&lt;server&gt;:&lt;port&gt;/system/console/configMgr`.
1. Edit the configuration for the servlet **Day CQ DAM Create Asset**.
1. Select the **detect duplicate** option, and click/tap **Save**. The detect duplicate feature is now enabled in AEM Assets.

   ![chlimage_1-377](assets/chlimage_1-377.png)