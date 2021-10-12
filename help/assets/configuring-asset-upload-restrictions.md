---
title: Configure asset upload restrictions
description: Learn how to configure Adobe Experience Manager Assets to restrict the type of assets (files) that users can upload.
contentOwner: AG
feature: Upload,Asset Ingestion,Asset Management
role: Admin,Architect
exl-id: 0d817cfa-ae06-442a-ad89-5fe619bb2eff
---
# Configure asset upload restrictions {#configuring-asset-upload-restrictions}

You can configure Adobe Experience Manager Assets to restrict the type of assets (files) that users can upload. This feature helps you eliminate the possibility of users uploading assets in an undesired format or uploading any malicious files. The `Day CQ DAM Asset Upload Restriction` service enables you to control the type of files that users can upload. By default, [!DNL Experience Manager] Assets allows users to upload assets of all MIME types. However, you can configure the service to restrict users to upload files of specific MIME types only.

1. To open the Configuration Manager web console, access `https://[AEM_server]:[port]/system/console/configMgr`.
1. Open the **[!UICONTROL Day CQ DAM Asset Upload Restriction]** service in Edit mode. By default, the **Allow all MIME** option is selected, which allows users to upload files of all MIME types.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. To restrict users to upload files of certain MIME types only, unselect the **[!UICONTROL llow all MIME]** option and specify allowed MIME types in the **[!UICONTROL Allowed Asset MIMEs (regex)]** fields using regular expressions.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Click/tap **[!UICONTROL Save]** to save the changes. If you specify MIME-strings for allowed MIME types, the upload operation fails for any asset with MIME type that doesn’t match the configured MIME strings in these fields.
