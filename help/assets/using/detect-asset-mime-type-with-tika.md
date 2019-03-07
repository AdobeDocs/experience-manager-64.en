---
title: Detecting MIME Type of Assets Using Apache Tika
seo-title: Detecting MIME Type of Assets Using Apache Tika
description: Enable Apache Tika to help AEM Assets detect the MIME type of assets from the content stream during the upload operation instead of the file extension.
seo-description: Enable Apache Tika to help AEM Assets detect the MIME type of assets from the content stream during the upload operation instead of the file extension.
uuid: 28acb308-71da-4088-8572-cd704cfb15c2
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 41686817-cd0e-4156-89cd-8ee4d70d7209
index: y
internal: n
snippet: y
---

# Detecting MIME Type of Assets Using Apache Tika{#detecting-mime-type-of-assets-using-apache-tika}

Normally, Adobe Experience Manager (AEM) Assets detects the MIME type of assets that you upload from their file extension.

If you use Apache Tika to upload assets, AEM Assets detects their MIME type from the content stream during the upload operation instead of the file extension.

This feature is disabled by default. To enable the feature, configure the **Day CQ DAM Mime Type** service from Configuration Manager.

>[!NOTE]
>
>MIME type detection using the Apache Tika library is a resource-intensive operation.

1. Go to *http://&lt;server&gt;:&lt;port&gt;/system/console/configMgr* to open the Configuration Manager web console.
1. From the list of services, locate **Day CQ DAM Mime Type Service** and tap/click the **Edit** icon beside it to open it in Edit mode.   

1. Select the **Detect MIME from content** option to enable the parsing of uploaded assets to determine their MIME type while ignoring file extensions. By default, this option is unselected.

   ![](assets/chlimage_1-333.png)

1. Click/tap **Save** to save the changes.

