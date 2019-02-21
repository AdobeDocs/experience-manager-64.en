---
title: Enabling Duplicate Detection
seo-title: Enabling Duplicate Detection
description: Learn how to enable the detection of duplicate assets in AEM.
seo-description: Learn how to enable the detection of duplicate assets in AEM.
uuid: 4e3e61b2-4f46-4155-9400-b00c545d0234
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: c1ec5962-358a-46c3-9467-a98cf1bc29e5
index: y
internal: n
snippet: y
---

# Enabling Duplicate Detection{#enabling-duplicate-detection}

Learn how to enable the detection of duplicate assets in AEM.

If you attempt to upload an asset that already exists in Adobe Experience Manager (AEM) Assets, the Duplicate Detection feature identifies it as duplicate.

Duplicate Detection is disabled by default. To enable the feature, perform the following steps:

1. Go to the **Adobe Experience Manager Web Console Configuration** page at the following URL:
1. Edit the configuration for the servlet **Day CQ DAM Create Asset**.
1. Select the d**etect duplicate** option, and click/tap **Save**. The Detect Duplicate feature is now enabled in AEM Assets.

   ![](assets/chlimage_1-383.png)

