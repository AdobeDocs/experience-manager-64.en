---
title: Creating Translation Projects for Content Fragments
seo-title: Creating Translation Projects for Content Fragments
description: Learn how to translate content fragments.
seo-description: Learn how to translate content fragments.
uuid: 594115fe-a7a0-4bd0-9f13-c8136a63abf7
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 70679b51-5724-45bf-b668-52e37b5fe407
index: y
internal: n
snippet: y
---

# Creating Translation Projects for Content Fragments{#creating-translation-projects-for-content-fragments}

In addition to assets, Adobe Experience Manager (AEM) Assets supports language copy workflows for [content fragments](../../assets/using/content-fragments.md) (including variations). No additional optimization is required to run language copy workflows on content fragments. In each workflow, the entire content fragment is sent for translation.

The types of workflows that you can run on content fragments is exactly similar to the workflow types you run for assets. Also, the options available within each workflow type match the options available under the corresponding workflows types for assets.

You can run the following types of language copy workflows on content fragments:

**Create and translate**

In this workflow, content fragments to be translated are copied to the language root of the language to which you want to translate. In addition, depending upon the options you choose, a translation project is created for the content fragments in the Projects console. Depending on the settings, the translation project can be started manually or allowed to run automatically as soon as the translation project is created.

**Update language copies**

When the source content fragment is updated or modified, the corresponding locale/language specific content fragment requires retranslation. The update language copies workflow translates an additional group of content fragments and includes it in a lanugage copy for a particular locale. In this case, the translated content fragments are added to the target folder that already contains previously-translated content fragments.

## Create and translate workflow {#create-and-translate-workflow}

The Create and translate workflow includes the following options. The procedural steps associated with each option are similar to those associated with the corresponding option for assets.

* Create structure only: For procedure steps, see [Create structure only for assets](../../assets/using/translation-projects.md#main-pars-title-525074238). 
* Create a new translation project: For procedure steps, see [Create a new translation project for assets](../../assets/using/translation-projects.md#main-pars-title-688302526). 
* Add to existing translation project: For procedure steps, see [Add to existing translation project for assets](../../assets/using/translation-projects.md#main-pars-title-0).

## Update language copies workflow {#update-language-copies-workflow}

The Update language copies workflow includes the following options. The procedural steps associated with each option are similar to those associated with the corresponding option for assets.

* Create a new translation project: For procedure steps, see [Create a new translation project for assets](../../assets/using/translation-projects.md#main-pars-title-1131803059) (update workflow). 
* Add to existing translation project: For procedure steps, see [Add to existing translation project for assets](../../assets/using/translation-projects.md#main-pars-title-514496090) (update workflow).

You can also create temporary language copies for fragments similar to the way you create temporary copies for assets. For details, see [Creating temporary language copies for assets](../../assets/using/translation-projects.md#main-pars-title-20911192).

## Translating mixed media fragments {#translating-mixed-media-fragments}

AEM lets you translate content fragments that include various types of media assets and collections. If you translate a content fragment that includes inline assets, the translated copies of these assets are stored under the target language root.

If the content fragment includes a collection, the assets within the collection are translated along with the content fragment. The translated copies of the assets are stored within the appropriate target language root at a location that matches the physical location of the source assets under the source language root.

To be able to translate content fragments that include mixed media, first edit the default translation framework to enable the translation of inline assets and collections associated with content fragments.

1. Click/tap the AEM logo, and navigate to **Tools** &gt; **Deployment** &gt; **Cloud Services**.
1. Locate **Translation Integration** under **Adobe Marketing Cloud**, and click/tap **Show Configurations**. 

   ![](assets/chlimage_1-459.png)

1. From the list of available configurations, click/tap **Default configuration (Translation Integration configuration)** to open the **Default configuration** page.

   ![](assets/chlimage_1-460.png)

1. Click **Edit** from the toolbar to display the **Translation Config** dialog.

   ![](assets/chlimage_1-461.png)

1. Navigate to the **Assets** tab, and choose **Inline Media Assets and Associated Collections** from the **Translate Content Fragment Assets** list. Click/tap **OK** to save the changes.

   ![](assets/chlimage_1-462.png)

1. From within the English root folder, open a content fragment.

   ![](assets/chlimage_1-463.png)

1. Click/tap the **Insert Asset** icon.

   ![](assets/chlimage_1-464.png)

1. Insert an asset into the content fragment.

   ![](assets/chlimage_1-465.png)

1. Click/tap the **Associate Content** icon.

   ![](assets/chlimage_1-466.png)

1. Click/tap **Associate Content**.

   ![](assets/chlimage_1-467.png)

1. Select a collection and include it into the content fragment. Click/tap **Save**.

   ![](assets/chlimage_1-468.png)

1. Select the content fragment, and click/tap the **GlobalNav** icon.
1. Select **References** from the menu to display the **References** pane.

   ![](assets/chlimage_1-469.png)

1. Click/tap **Language Copies** under **Copies** to display the language copies.

   ![](assets/chlimage_1-470.png)

1. Click/tap **Create & Translate** from at the bottom of the panel to display the **Create & Translate** dialog.

   ![](assets/chlimage_1-471.png)

1. Select the target language from the **Target Languages** list.

   ![](assets/chlimage_1-472.png)

1. Select the translation project type from the **Project** list.

   ![](assets/chlimage_1-473.png)

1. Specify the title of the project in the **Project Title** box and then click/tap **Create**.

   ![](assets/chlimage_1-474.png)

1. Navigate to the **Projects** console, and open the project folder for the translation project you created.

   ![](assets/chlimage_1-475.png)

1. Click/tap the project tile to open the project details page. 

   ![](assets/chlimage_1-476.png)

1. From the Translation Job tile, verify the number of assets to be translated.
1. From the **Translation Job** tile, start the translation job.

   ![](assets/chlimage_1-477.png)

1. Click the ellipses at the bottom of the Translation Job tile to display the status of the translation job.

   ![](assets/chlimage_1-478.png)

1. Click/tap the content fragment to check the path of the translated associated assets.

   ![](assets/chlimage_1-479.png)

1. Review the language copy for the collection in the Collections console.

   ![](assets/chlimage_1-480.png)

   Notice that only the content of the collection are translated. The collection itself is not translated.

1. Navigate to the path of the translated associated asset. Observe that the translated asset is stored under the target language root.

   ![](assets/chlimage_1-481.png)

1. Navigate to the assets within the collection that are translated along with the content fragment. Observe that the translated copies of the assets are stored at the appropriate target language root.

   ![](assets/chlimage_1-482.png)

   >[!NOTE]
   >
   >The procedures for adding a content fragment to an existing project or to perform update workflows are similar to the corresponding procedures for assets. For guidance on these procedures, refer to the procedures described for assets.

