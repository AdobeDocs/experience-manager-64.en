---
title: Managing Multiple Assets and Collections
seo-title: Managing Multiple Assets and Collections
description: Learn how to edit the metadata of multiple assets and collections simultaneously to quickly propagate common metadata changes.
seo-description: Learn how to edit the metadata of multiple assets and collections in bulk.
uuid: 469a3948-26ed-466b-b946-bc8a8d04417b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: authoring
discoiquuid: 5c6b45bf-8e99-45c6-95fd-f46f5888e9c3
index: y
internal: n
snippet: y
---

# Managing Multiple Assets and Collections{#managing-multiple-assets-and-collections}

Learn how to edit the metadata of multiple assets and collections simultaneously to quickly propagate common metadata changes.

Adobe Enterprise Manager (AEM) Assets lets you edit the metadata of multiple assets simultaneously so you can quickly propagate common metadata changes to assets in bulk. You can also edit the metadata for multiple collections in bulk.

Use the properties page to perform metadata changes on multiple assets or collections:

* Change metadata properties to a common value
* Add or modify tags

To customize the metadata properties page, including adding, modifying, deleting metadata properties, use the Schema editor.

## Editing metadata properties of multiple assets {#editing-metadata-properties-of-multiple-assets}

1. In the Assets user interface, navigate to the location of the assets you want to edit.
1. Select the assets for which you want to edit common properties.
1. From the toolbar, tap/click the **Properties** icon to open the properties page for the selected assets.

   >[!NOTE]
   >
   >When you select multiple assets, the lowest common parent form is selected for the assets. In other words, the properties page only displays metadata fields that are common across the properties pages of all the individual assets.

1. Modify the metadata properties for selected assets under the various tabs.
1. To view the metadata editor for a specific asset, deselect the remaining assets in the list. The metadata editor fields are populated with the metadata for the particular asset.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * In the properties page, you can remove assets from the asset list by deselecting them. The asset list has all the assets selected by default. The metadata for assets that you remove from the list is not updated.
   >    * At the top of assets list, select the check box near **Title** to toggle between selecting the assets and clearing the list.
   >    
   >

1. To select a different metadata schema for the assets, tap/click the **Settings** icon from the toolbar, and select the desired schema.
1. Save the changes.
1. To append the new metadata with the existing metadata in fields that contain multiple values, select **Append mode**. If you do not select this option, the new metadata replaces the existing metadata in the fields. Tap/click **Submit**.

   >[!NOTE]
   >
   >For single-value fields, the new metadata is not appended to the existing value in the field even if you select **Append mode**.

   ![](assets/chlimage_1-367.png)

## Editing metadata properties of multiple collections {#editing-metadata-properties-of-multiple-collections}

1. From the Collections console, select the collections you want to edit.
1. From the toolbar, tap/click the **Properties** icon to open the properties page for the selected collections.
1. Modify the metadata properties for selected collections under the various tabs.

   >[!NOTE]
   >
   >The metadata you add for the selected collections overwrites the previous metadata for these collections, except for tags. Any tags you add in the **Tags** field, are appended to the existing list of tags in the metadata.

1. To view the metadata properties for a specific collection, deselect the remaining collections in the collections list. The metadata editor fields are populated with the metadata for the particular collection.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * In the collection properties page, you can remove collections from the list of collections by deselecting them. The collections list has all the collections selected by default. The metadata for collections that you remove is not updated.
   >    * At the top of the list, select the check box near **Title** to toggle between selecting the collections and clearing the list.
   >    
   >

1. Save the changes.

