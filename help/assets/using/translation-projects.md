---
title: Creating Translation Projects
seo-title: Creating Translation Projects
description: Learn how to create translation projects in AEM.
seo-description: Learn how to create translation projects in AEM.
uuid: 5dc7f506-6a2e-4b3f-875e-b51e7d44539b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 00560fd9-f1a3-4194-bb0d-48f3834808f5
---

# Creating Translation Projects{#creating-translation-projects}

To create a language copy, trigger one of the following language copy workflows available under the References rail in the Assets UI:

**Create and translate**

In this workflow, assets to be translated are copied to the language root of the language to which you want to translate. In addition, depending upon the options you choose, a translation project is created for the assets in the Projects console. Depending on the settings, the translation project can be started manually or allowed to run automatically as soon as the translation project is created.

**Update language copies**

You run this workflow to translate an additional group of assets and include it in a language copy for a particular locale. In this case, the translated assets are added to the target folder that already contains previously-translated assets.

>[!NOTE]
>
>Asset binaries are translated only if the translation service provider supports the translation of binaries.

>[!NOTE]
>
>If you launch a translation workflow for complex assets, such as PDFs and InDesign files, their subassets or renditions (if any) are not submitted for translation.

## Create and translate workflow {#create-and-translate-workflow}

You use the Create and translate workflow to generate language copies for a particular language for the first time. The workflow provides the following options:

* Create structure only 
* Create a new translation project
* Add to existing translation project

### Create structure only {#create-structure-only}

Use the **Create structure only** option to create a target folder hierarchy within the target language root to match the hierarchy of the source folder within the source language root. In this case, source assets are copied to the destination folder. However, no translation project is generated.

1. In the Assets UI, select the source folder for which you want to create a structure in the target language root.
1. Open the **References **pane and click/tap **Language Copies **under **Copies**.

   ![](assets/chlimage_1-62.png)

1. Click/tap **Create & Translate** at the bottom.

   ![](assets/chlimage_1-63.png)

1. From the **Target Languages** list, select the language for which you want to create a folder structure.

   ![](assets/chlimage_1-64.png)

1. From the** Project** list, choose **Create structure only**. 

   ![](assets/chlimage_1-65.png)

1. Click/tap** Create**. The new structure for the target language is listed under **Language Copies**. 

   ![](assets/chlimage_1-66.png)

1. Click/tap the structure from the list, and then click/tap **Reveal in Assets** to navigate to the folder structure within the target language.

   ![](assets/chlimage_1-67.png)

### Create a new translation project {#create-a-new-translation-project}

If you use this option, assets to be translated are copied to the language root of the language to which you want to translate. Depending upon the options you choose, a translation project is created for the assets in the Projects console. Depending on the settings, the translation project can be started manually or runs automatically as soon as the translation project is created.

1. In the Assets UI, select the source folder for which you want to create a Language copy.
1. Open the **References **pane and click/tap **Language Copies **under **Copies**.

   ![](assets/chlimage_1-68.png)

1. Click/tap **Create & Translate** at the bottom.

   ![](assets/chlimage_1-69.png)

1. From the **Target Languages **list, select the language(s) for which you want to create a folder structure.

   ![](assets/chlimage_1-70.png)

1. From the **Project **list, select **Create a new translation project**.

   ![](assets/chlimage_1-71.png)

1. In the **Project Title **field, enter a title for the project.

   ![](assets/chlimage_1-72.png)

1. Click/tap on **Create**. Assets from the source folder are copied to the target folders for the locales you selected in step 4.

   ![](assets/chlimage_1-73.png)

1. To navigate to the folder, select the language copy, and click **Reveal in Assets**.

   ![](assets/chlimage_1-74.png)

1. Navigate to the Projects console. The translation folder is copied to the Projects console.

   ![](assets/chlimage_1-75.png)

1. Open the folder to view the translation project.

   ![](assets/chlimage_1-76.png)

1. Click/tap the project to open the details page.

   ![](assets/chlimage_1-77.png)

1. To view the status of the translation job, click the ellipsis at the bottom of the **Translation Job **tile.

   ![](assets/chlimage_1-78.png)

   For more details around job statuses, see [Monitoring the Status of a Translation Job](../../sites/administering/using/tc-manage.md#monitoring-the-status-of-a-translation-job).

1. Navigate to the Assets UI, and open the Properties page for each of the translated assets to view the translated metadata.

   ![](assets/chlimage_1-79.png)

   >[!NOTE]
   >
   >This feature is available both for assets and folders. When an asset is selected instead of a folder, the entire hierarchy of folders upto the language root is copied to create a language copy for the asset.

### Add to existing translation project {#add-to-existing-translation-project}

If you use this option, the translation workflow runs for assets that you add to the source folder after running a previous translation workflow. Only the newly-added assets are copied to the target folder that contains previously-translated assets. No new translation project is created in this case.

1. In the Assets UI, navigate to the source folder that contains untranslated assets.
1. Select an asset you want to translate, and open the **Reference pane**. The **Language Copies** section displays the number of translation copies that are currently available.
1. Click/tap **Language Copies** under **Copies**. A list of available translation copies is displayed.
1. Click/tap **Create & Translate** at the bottom.

   ![](assets/chlimage_1-80.png)

1. From the **Target Languages **list, select the language(s) for which you want to create a folder structure.

   ![](assets/chlimage_1-81.png)

1. From the **Project **list, select **Add to existing translation project **to run the translation workflow on the folder.

   ![](assets/chlimage_1-82.png)

   >[!NOTE]
   >
   >If you choose the **Add to existing translation project** option, your translation project is added to a pre-existing project only if your project settings exactly match the settings of the pre-existing project. Otherwise, a new project is created.

1. From the **Existing translation project **list, select a project to add the asset for translation.

   ![](assets/chlimage_1-83.png)

1. Click/tap **Create**. The assets to be translated are added to the target folder. The updated folder is listed under the **Language Copies **section.

   ![](assets/chlimage_1-84.png)

1. Navigate to the Projects console, and open the existing translation project you added to.
1. Click/tap the translation project view the project details page.

   ![](assets/chlimage_1-85.png)

1. Click/tap the ellipsis at the bottom of the **Translation Job** tile to view the assets in the translation workflow. The translation job list also displays entries for asset metadata and tags. These entries indicate that the metadata and tags for the assets are also translated.

   >[!NOTE]
   >
   >If you delete the entry for tags or metadata, no tags or metadata are translated for any of the assets.

   >[!NOTE]
   >
   >If you use Machine Translation, asset binaries aren't translated.

   >[!NOTE]
   >
   >If the asset you add to the translation job includes subassets, select the subassets and remove them for the translation to proceed without any glitches.

1. To start the translation for the assets, click/tap the arrow on the **Translation Job** tile and select **Start** from the list.

   ![](assets/chlimage_1-86.png)

   A message notifies the commencement of the translation job.

   ![](assets/chlimage_1-87.png)

1. To view the status of the translation job, click/tap the ellipsis at the bottom of the **Translation Job** tile.

   ![](assets/chlimage_1-88.png)

   For more details, see [Monitoring the Status of a Translation Job](../../sites/administering/using/tc-manage.md#monitoring-the-status-of-a-translation-job).

1. After the translation completes, the status changes to Ready to Review. Navigate to the Assets UI, and open the Properties page for each of the translated assets to view the translated metadata.

## Update language copies {#update-language-copies}

Run this workflow to translate any additional set of assets and include it in a lanugage copy for a particular locale. In this case, the translated assets are added to the target folder that already contains previously-translated assets. Depending upon the choice of options, a translation project is created or an existing translation project is updated for the new assets. The Update language copies workflow includes the following options:

* Create a new translation project
* Add to existing translation project

### Create a new translation project {#create-a-new-translation-project-1}

If you use this option, a translation project is created for the set of assets for which you want to update a language copy.

1. From the Assets UI, select the source folder where you added an asset.
1. Open the **References** pane, and click/tap **Language Copies** under **Copies** to display the list of language copies. 
1. Select the check box before **Language Copies**, and then select the target folder corresponding to the appropriate locale.

   ![](assets/chlimage_1-89.png)

1. Click/tap **Update language copies** at the bottom.

   ![](assets/chlimage_1-90.png)

1. From the **Project** list, choose **Create a new translation project**.

   ![](assets/chlimage_1-91.png)

1. In the **Project Title **field, enter a title for the project. 

   ![](assets/chlimage_1-92.png)

1. Click/tap **Start**.
1. Navigate to the Projects console. The translation folder is copied to the Projects console.

   ![](assets/chlimage_1-93.png)

1. Open the folder to view the translation project.

   ![](assets/chlimage_1-94.png)

1. Click/tap the project to open the details page.

   ![](assets/chlimage_1-95.png)

1. To start the translation for the assets, click the arrow on the **Translation Job **tile and select **Start **from the list.

   ![](assets/chlimage_1-96.png)

   A message notifies the commencement of the translation job.

   ![](assets/chlimage_1-97.png)

1. To view the status of the translation job, click/tap the ellipsis at the bottom of the **Translation Job **tile.

   ![](assets/chlimage_1-98.png)

   For more details around job statuses, see [Monitoring the Status of a Translation Job](../../sites/administering/using/tc-manage.md#monitoring-the-status-of-a-translation-job).

1. Navigate to the Assets UI, and open the Properties page for each of the translated assets to view the translated metadata.

### Add to existing translation project {#add-to-existing-translation-project-1}

If you use this option, the set of assets are added to an existing translation project to update the language copy for the locale you choose.

1. From the Assets UI, select the source folder where you added an asset folder.
1. Open the References pane, and click/tap **Language Copies** under **Copies** to display the list of language copies.

   ![](assets/chlimage_1-99.png)

1. Select the check box before **Language Copies**, which selects all language copies. Unselect other copies except the language copy (copies) corresponding to the locale(s) to which you want to translate.

   ![](assets/chlimage_1-100.png)

1. Click/tap **Update language copies** at the bottom.

   ![](assets/chlimage_1-101.png)

1. From the **Project** list, choose **Add to existing translation project**.

   ![](assets/chlimage_1-102.png)

1. From the **Existing translation project **list, select a project to add the asset for translation.

   ![](assets/chlimage_1-103.png)

1. Click/tap **Start**.
1. See steps 9-14 of [Add to existing translation project](../../assets/using/translation-projects.md#add-to-existing-translation-project) to complete the rest of the procedure.

## Creating temporary language copies {#creating-temporary-language-copies}

When you run a translation workflow to update a language copy with edited versions of original assets, the existing language copy is preserved until you approve the translated asset(s). AEM Assets stores the newly-translated asset(s) at a temporary location and updates the existing language copy after you explicitly approve the asset(s). If you reject the asset(s), the language copy remains unchanged.

1. Click/tap the source root folder under **Language Copies** for which you already created a languag copy, and then click/tap **Reveal in Assets** to open the folder in AEM Assets.

   ![](assets/chlimage_1-104.png)

1. From the Assets UI, select an asset you already translated and click/tap the **Edit** icon from the toolbar to open the asset in edit mode.

   ![](assets/chlimage_1-105.png)

1. Edit the asset and then save the changes.
1. Perform steps 2-14 of the [Add to existing translation project](#main-pars-title-0) procedure to update the language copy.
1. Click/tap the ellipsis at the bottom of the **Translation Job** tile. From the list of assets in the **Translation Job** page, you can clearly view the temporary location where the translated version of the asset is stored.

   ![](assets/chlimage_1-106.png)

1. Select the checkbox next to **Title**.
1. From the toolbar, click/tap **Accept Translation** and then click/tap **Accept** in the dialog to overwrite the translated asset in the target folder with the translated version of the edited asset.

   ![](assets/chlimage_1-107.png)

   >[!NOTE]
   >
   >To enable the translation workflow to update the destination asset(s), accept both the asset and metadata.

   Click/tap **Reject Translation** to retain the originally translated version of the asset in the target locale root and reject the edited version.

   ![](assets/chlimage_1-108.png)

1. Navigate to the Assets console, and open the Properties page for each of the translated assets to view the translated metadata.

For tips on translating metadata for assets efficiently, see [5 Steps for Efficiently Translating Metadata](http://blogs.adobe.com/experiencedelivers/experience-management/translate_aemassets_metadata/).
