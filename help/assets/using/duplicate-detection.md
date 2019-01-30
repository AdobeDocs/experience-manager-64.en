---
title: Enabling Duplicate Detection
seo-title: Enabling Duplicate Detection
description: Learn how to enable the detection of duplicate assets in AEM.
seo-description: Learn how to enable the detection of duplicate assets in AEM.
uuid: abe41065-6a89-47a1-9611-34f2227a3aa1
acrolinxdate: 2019-01-12T17 28 31.819-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: green
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/duplicate_detection_krs_workflow_f3c2f2ccebf6138e_127_report.xml
acrolinxsentences: 12
acrolinxwords: 116
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: ef49f16e-c4f7-4aea-8088-6ded11a2678d
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Enabling Duplicate Detection{#enabling-duplicate-detection}

Learn how to enable the detection of duplicate assets in AEM.

If you attempt to upload an asset that already exists in Adobe Experience Manager (AEM) Assets, the Duplicate Detection feature identifies it as duplicate.

Duplicate Detection is disabled by default. To enable the feature, perform the following steps:

1. Go to the **Adobe Experience Manager Web Console Configuration** page at the following URL:

   *http://&lt;server&gt;:&lt;port&gt;/system/console/configMgr* 

1. Edit the configuration for the servlet **Day CQ DAM Create Asset**.
1. Select the d**etect duplicate** option, and click/tap **Save**. The Detect Duplicate feature is now enabled in AEM Assets.

   ![](assets/chlimage_1-333.png)

