---
title: Use Apache Tika to detect MIME type of digital assets
description: Enable Apache Tika to help AEM Assets detect the MIME type of assets from the content stream during the upload operation instead of the file extension.
contentOwner: AG
feature: Metadata,Developer Tools,Asset Management
role: Administrator,Architect
exl-id: 6c9e53e9-5e54-4816-9431-41e796340d1e
---
# Use Apache Tika to detect MIME type of digital assets {#detecting-mime-type-of-assets-using-apache-tika}

Typically, Adobe Experience Manager (AEM) Assets detects the MIME type of assets that you upload from their file extension. If you use Apache Tika to upload assets, AEM Assets detects their MIME type from the content stream during the upload operation instead of the file extension.

This feature is disabled by default. To enable the feature, configure the **Day CQ DAM Mime Type** service from Configuration Manager.

>[!NOTE]
>
>MIME type detection using the Apache Tika library is a resource-intensive operation.

1. Go to `https://[AEM_server]:[port]/system/console/configMgr` to open the Configuration Manager web console.
1. From the list of services, locate **[!UICONTROL Day CQ DAM Mime Type Service]** and tap/click the **[!UICONTROL Edit]** icon beside it to open it in Edit mode.   

1. Select the **[!UICONTROL Detect MIME from content]** option to enable the parsing of uploaded assets to determine their MIME type while ignoring file extensions. By default, this option is unselected.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Click/tap **[!UICONTROL Save]** to save the changes.
