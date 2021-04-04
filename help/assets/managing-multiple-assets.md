---
title: Bulk edit metadata of multiple assets and collections
description: Learn how to edit the metadata of many assets and collections simultaneously to quickly propagate common metadata changes.
contentOwner: AG
feature: Asset Management,Metadata,Collections
role: Business Practitioner
exl-id: 3541b50a-f226-4a6a-9c2a-03a5f47f1c23
---
# Manage multiple assets and collections {#managing-multiple-assets-and-collections}

Learn how to edit the metadata of multiple assets and collections simultaneously to quickly propagate common metadata changes.

Adobe Enterprise Manager (AEM) Assets lets you edit the metadata of multiple assets simultaneously so you can quickly propagate common metadata changes to assets in bulk. You can also edit the metadata for multiple collections in bulk.

Use the properties page to perform metadata changes on multiple assets or collections:

* Change metadata properties to a common value
* Add or modify tags

To customize the metadata properties page, including adding, modifying, deleting metadata properties, use the Schema editor.

>[!NOTE]
>
>The bulk editing methods work for assets available in a folder or a collection. For the assets that are available across folders or match a common criteria, it is possible to update the metadata in bulk from asset search results.

## Edit metadata properties of multiple assets {#editing-metadata-properties-of-multiple-assets}

1. In the Assets user interface, navigate to the location of the assets you want to edit.
1. Select the assets for which you want to edit common properties.
1. From the toolbar, click **[!UICONTROL Properties]** to open the properties page for the selected assets.
1. Modify the metadata properties for selected assets under the various tabs.
1. To view the metadata of a specific asset, cancel the selection of the remaining assets in the list. If you cancel the selection of a few assets on the [!UICONTROL Properties] page, the metadata of such assets is not updated.
1. To select a different metadata schema for the assets, click **[!UICONTROL Settings]** from the toolbar, and select a schema. Click **[!UICONTROL Save & Close]**.
1. To append the new metadata with the existing metadata in fields that contain multiple values, select **[!UICONTROL Append mode]**. If you do not select this option, the new metadata replaces the existing metadata in the fields. Click **[!UICONTROL Submit]**.

![Metadata schema bulk apply to multiple assets](assets/metadata-schema-bulk-edit.gif)

   >[!CAUTION]
   >
   >For single-value fields, the new metadata is not appended to the existing value in the field even if you select **[!UICONTROL Append mode]**.

## Configure limit for bulk metadata update {#configure-limit-for-bulk-metadata-update}

To prevent DOS like situation, AEM limits the number of parameters supported in a Sling request. When updating metadata of many assets in one go, you may reach the limit and the metadata does not get updated for more assets. AEM generates the following warning in the logs:

`org.apache.sling.engine.impl.parameters.Util Too many name/value pairs, stopped processing after 10000 entries`

To change the limit, access **[!UICONTROL Tools > Operations > Web Console]** and change the value of [!UICONTROL Maximum POST Parameters] in [!UICONTROL Apache Sling Request Parameter Handling] OSGi configuration.

>[!MORELIKETHIS]
>
>* [Edit metadata of multiple collections in bulk](managing-collections-touch-ui.md#editing-collection-metadata-in-bulk)
