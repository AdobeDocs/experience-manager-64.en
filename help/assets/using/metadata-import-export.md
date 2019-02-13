---
title: Bulk Metadata Import and Export
seo-title: Bulk Metadata Import and Export
description: This article describes how to import and export metadata in bulk.
seo-description: This article describes how to import and export metadata in bulk.
uuid: d4edbc65-3c47-4a12-83cb-8cbc31bd9e28
contentOwner: cmajumda
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
discoiquuid: 1b2da8d0-11b3-468c-ba54-83b8b84c44d9
index: y
internal: n
snippet: y
---

# Bulk Metadata Import and Export{#bulk-metadata-import-and-export}

This article describes how to import and export metadata in bulk.

AEM 6.4 Assets lets you import asset metadata in bulk using a CSV file for newly uploaded assets. In addition, you can also update the metadata for assets in bulk for existing assets by importing a CSV file. You can also ingest asset metadata in bulk from third-party system in CSV format.

## Import metadata {#import-metadata}

In other words, you can use a single CSV file to simultaneously update the metadata for multiple assets simultaneously. The operation is asynchronous. and, therefore, does not impede your system performance.

>[!NOTE]
>
>To be able to import metadata on custom namespaces, first register them.

1. Navigate to the Assets UI, and tap/click **Create** from the toolbar.
1. From the menu, select **Metadata**.
1. In the **Metadata Import** page, tap/click the **Select File** button to select the CSV file with metadata values to be imported.
1. Specify the following configuration parameters:

<table border="1" cellpadding="0" cellspacing="0"> 
 <tbody>
  <tr>
   <td style="font-weight: normal" valign="top" width="295"><p>Batch Size</p> </td> 
   <td style="font-weight: normal" valign="top" width="295"><p>Number of assets in a batch for which metadata is to be imported. Default value is 50. Maximum value is 100.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="295"><p>Field Separator</p> </td> 
   <td valign="top" width="295"><p>Default value is Comma. You can specify any other character.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="295"><p>Multi value Delimiter</p> </td> 
   <td valign="top" width="295"><p>Separator for metadata values. Default value is |.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="295"><p>Launch Workflows</p> </td> 
   <td valign="top" width="295"><p>False by default. When set to <em>true</em> and default Launcher settings are in effect for the DAM Metadata WriteBack Workflow (that writes metadata to the binary XMP data). Enabling launch workflows slows the system down. </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="295"><p>Asset Path Column Name</p> </td> 
   <td valign="top" width="295"><p>Defines the column name for the CSV file with assets.</p> </td> 
  </tr>
 </tbody>
</table>

1. Tap/click **Import** from the toolbar. After the metadata is imported a notification is sent to your Notification inbox. Navigate to asset property page and verify whether the metadata values are correctly imported for assets.

## Export Metadata {#export-metadata}

AEM 6.4 Assets lets you export metada for multiple assets in CSV format and reimport the metadata in a third-party system. You can also share asset metadata within project team.

The metadata is exported asynchronously and, therefore, does not impact the performance of your system. When you export metadata, AEM traverses through properties of the asset node *jcr:content/metadata* and its child nodes and exports metadata properties in a CSV file.

1. Select the asset folder for which you want to export metadata. 

   ![](assets/select_folder.png)

1. From the toolbar, select** Export metadata**.

   ![](assets/export_metadata.png)

1. In the Metadata Export field, specify a name for the CSV file. To export metadata for assets in subfolders, select **Include assets in sub-folders**.

   ![](assets/export_metadata_page.png)

1. Select whether you want to export now or at a later date.
1. In the **Properties to be exported** field, specify whether you want to export all or specific properties.  

1. From the toolbar, tap/click **Export**. A message confirms that the metadata is exported. Close the message.
1. Open the inbox nofification for the export job. To download the CSV file with the metadata, tap/click the **CSV Download** icon from the toolbar.

   ![](assets/csv_download.png)

