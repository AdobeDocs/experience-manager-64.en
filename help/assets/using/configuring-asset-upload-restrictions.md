---
title: Configuring Asset Upload Restrictions
seo-title: Configuring Asset Upload Restrictions
description: null
seo-description: Learn how to configure Adobe Experience Manager (AEM) Assets to restrict the type of assets (files) that users can upload.
uuid: 03357282-b2a9-4e01-984a-974a7b0303e0
acrolinxdate: 2019-01-12T17 27 44.166-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/configuring_asset_upload_restrictions_krs_workflow_f3c2f2ccebf6138e_114_report.xml
acrolinxsentences: 14
acrolinxwords: 227
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: e7e9dc18-4ced-45e9-8135-5f6c6a8c6a95
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring Asset Upload Restrictions{#configuring-asset-upload-restrictions}

You can configure Adobe Experience Manager (AEM) Assets to restrict the type of assets (files) that users can upload. This feature helps you eliminate the possibility of users uploading assets in an undesired format or uploading any malicious files. The `Day CQ DAM Asset Upload Restriction` service enables you to control the type of files that users can upload. By default, AEM Assets allows users to upload assets of all MIME types. However, you can configure the service to restrict users to upload files of specific MIME types only.

1. Go to *http://&lt;server&gt;:&lt;port&gt;/system/console/configMgr* to open the Configuration Manager web console.
1. Open the **Day CQ DAM Asset Upload Restriction** service in Edit mode. By default, the **Allow all MIME** option is selected, which allows users to upload files of all MIME types.

   ![](assets/chlimage_1-334.png)

1. To restrict users to upload files of certain MIME types only, unselect the **Allow all MIME** option and specify allowed MIME types in the **Allowed Asset MIMEs (regex)** fields using regular expressions.

   ![](assets/chlimage_1-335.png)

1. Click/tap **Save** to save the changes. If you specify MIME-strings for allowed MIME types, the upload operation fails for any asset with MIME type that doesn’t match the configured MIME strings in these fields.

