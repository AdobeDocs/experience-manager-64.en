---
title: Customizing Views of Page Properties
seo-title: Customizing Views of Page Properties
description: Every page has a set of properties that you can edit as required
seo-description: Every page has a set of properties that you can edit as required
uuid: 74545468-7e20-47fa-b677-30b020114f54
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 645b90d5-2e4d-43a0-b691-c515db83a9ce
index: y
internal: n
snippet: y
---

# Customizing Views of Page Properties{#customizing-views-of-page-properties}

Every page has a set of [properties](../../../sites/authoring/using/editing-page-properties.md) that can be viewed and edited by users; some are required when creating the page (create view), others can be viewed and edited (edit view) at a later stage. These page properties are defined and made available by the dialog ( `cq:dialog`) of the appropriate page component.

>[!CAUTION]
>
>Customizing view of page properties is not available in the classic UI.

The default state for every page property is:

* hidden in the create view (e.g. **Create Page** wizard)  

* available in the edit view (e.g. **View Properties**)

Fields must be specifically configured if any change is required. This is done using the appropriate node properties:

* Page property to be available in the create view (e.g. **Create Page** wizard):

    * Name: `cq:showOnCreate`
    * Type: `Boolean`

* Page property to be available in the edit view (e.g. **View**/**Edit**) **Properties** option):

    * Name: `cq:hideOnEdit`
    * Type: `Boolean`

For example, see the settings for fields grouped under the **More Titles and Description** on the **Basic** tab for the foundation Page component. These are visible in the **Create Page** wizard as `cq:showOnCreate` has been set to `true`:

```xml
/libs/foundation/components/page/cq:dialog/content/items/tabs/items/basic/items/column/items/moretitles   
```

### Configuring your Page Properties {#configuring-your-page-properties}

You can also configure the fields available by configuring the dialog of your page component and applying the appropriate node properties.

For example, by default the [**Create Page** wizard](../../../sites/authoring/using/managing-pages.md#creatinganewpagetouchoptimizedui) shows the fields grouped under **More Titles and Description**. To hide these you configure:

1. Create your page component under `/apps`.
1. Create an override (using *dialog diff* provided by the [Sling Resource Merger](../../../sites/developing/using/sling-resource-merger.md)) for the `basic` section of your page component; for example:

   ```xml
   <your-page-component>/cq:dialog/content/items/tabs/items/basic
   ```

   >[!NOTE]
   >
   >As reference, see:  

   >
   >
   >
   >
   >```   >
   >/libs/wcm/foundation/components/basicpage/v1/basicpage/cq:dialog
   >
   >```   >
   >

   >
   >
   >However, you ***must*** not change anything in the `/libs` path.
   >
   >
   >This is because the content of `/libs` is overwritten the next time you upgrade your instance (and may well be overwritten when you apply either a hotfix or feature pack).
   >
   >
   >The recommended method for configuration and other changes is:
   >
   >    
   >    
   >    1. Recreate the required item (i.e. as it exists in `/libs`) under `/apps`  
   >    
   >    1. Make any changes within `/apps`
   >    
   >

1. Set the `path` property on `basic` to point to the override of the basic tab (see the next step as well). For example:

   ```xml
   /apps/demos/components/page/tabs/basic
   ```

1. Create an override of the `basic` - `moretitles` section at the corresponding path; for example:

   ```xml
   /apps/demos/components/page/tabs/basic/items/column/items/moretitles
   ```

1. Apply the appropriate node property:

    * **Name**: `cq:showOnCreate`
    
    * **Type**: `Boolean`
    
    * **Value**: `false`

   The **More Titles and Description** section will no longer be shown in the **Create Page** wizard.

>[!NOTE]
>
>When configuring page properties for use with live copies see [Configuring MSM Locks on Page Properties](../../../sites/developing/using/extending-msm.md#configuringmsmlocksonpagepropertiestouchoptimizedui) for more details.

### Sample Configuration of Page Properties {#sample-configuration-of-page-properties}

This sample demonstrates the dialog diff technique of the [Sling Resource Merger](../../../sites/developing/using/sling-resource-merger.md); including use of ` [sling:orderBefore](../../../sites/developing/using/sling-resource-merger.md#properties)`. It also illustrates use of both `cq:showOnCreate` and `cq:hideOnEdit`.

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-authoring-extension-page-dialog project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-authoring-extension-page-dialog)

<!--
Comment Type: draft

<p>CODE ON GITHUB</p>
<p>You can find the code of this page on GitHub</p>
<ul>
<li><a href="https://github.com/Adobe-Marketing-Cloud/aem-authoring-extension-page-dialog">Open aem-authoring-extension-page-dialog project on GitHub</a></li>
<li>Download the project as <a href="https://github.com/Adobe-Marketing-Cloud/aem-authoring-extension-page-dialog/archive/master.zip">a ZIP file</a></li>
</ul>
-->

