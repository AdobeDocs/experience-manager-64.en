---
title: Translation Enhancements
seo-title: Translation Enhancements
description: Translation enhancements in AEM.
seo-description: Translation enhancements in AEM.
uuid: 34331fa2-c959-4852-9c50-67911da408e5
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 20fb2269-435a-4dc6-bfd0-e0a528a4d739
---

# Translation Enhancements{#translation-enhancements}

This page presents incremental enhancements and refinements to AEM translation management capabilities.

## Translation Project automation {#translation-project-automation}

Options to improve productivity working with translation projects have been added, such as automatically promoting and deleting translation launches, and scheduling the recurring execution of a translation project.

1. In your translation project, click or tap the ellipsis at the bottom of the **Translation Summary** tile.

   ![](assets/screen_shot_2018-04-19at222622.jpg)

1. Switch to the **Advanced** tab. At the bottom, you can select **Automatically Promote Translation Launches**.

   ![](assets/screen_shot_2018-04-19at223430.jpg)

1. Optionally, you can select if after receiving translated content, translation launches should be automatically promoted and deleted.

   ![](assets/screen_shot_2018-04-19at224033.jpg)

1. To select the recurring execution of a translation project, select the frequency with the dropdown under **Repeat Translation**. Recurring project execution will automatically create and execute translation jobs in the specified intervals. 

   ![](assets/screen_shot_2018-04-19at223820.jpg)

## Multilingual Translation Projects {#multilingual-translation-projects}

It is possible to configure multiple target languages in a translation project, to reduce the total number of translation projects created.

1. In your translation project, click or tap the dots at the bottom of the **Translation Summary** tile.

   ![](assets/screen_shot_2018-04-19at222622.jpg)

1. Switch to the **Advanced** tab. You can add multiple languages under **Target Language**. 

   ![](assets/screen_shot_2018-04-22at212601.jpg)

1. Alternatively, if you are initiating translation via the references rail in Sites, add you languages and select **Create Multiple-language Translation Project**.

   ![](assets/screen_shot_2018-04-22at212941.jpg)

1. Translation jobs will be created in the project for every target language. They can be started either one by one within the project, or all at once by executing the project globally in Projects Admin. 

   ![](assets/screen_shot_2018-04-22at213854.jpg)

## Translation Memory Updates {#translation-memory-updates}

Manual edits of translated content can be synchronized back to the Translation Management System (TMS) to train its Translation Memory.

1. From the Sites console, after updating text content in a translated page, select **Update Translation Memory**.

   ![](assets/screen_shot_2018-04-22at234430.jpg)

1. A list view shows a side-by-side comparison of the source and the translation for every text component that was edited. Select which translation updates should be synchronized to Translation Memory, and select **Update Memory**.

   ![](assets/screen_shot_2018-04-22at235024.jpg)

   >[!NOTE]
   >
   >AEM will send the selected strings back to the Translation Management System.

## Language Copies on Multiple Levels {#language-copies-on-multiple-levels}

Language roots can now be grouped under nodes, for example by region, while still being recognized as roots of language copies. 

![](assets/screen_shot_2018-04-23at144012.jpg)

>[!CAUTION]
>
>Only one level is allowed. For example, the following will not allow the "es" page to resolve to a language copy:
>
>* `/content/we-retail/language-masters/en`
>* `/content/we-retail/language-masters/americas/central-america/es`
>
>This `es` language copy will not be detected as it is 2 levels (americas/central-america) away from the `en` node.

>[!NOTE]
>
>Language roots can have any page name, rather than just the ISO-code of the language. AEM will always check the path and name first, but if the page name does not identify a language, AEM will check cq:language property of the page for the language identification.

## Translation Status Reporting {#translation-status-reporting}

A property can now be selected in the Sites list view that shows if a page has been translated, is in translation, or has not yet been translated. To display it:

1. In Sites, switch to **List View.**

   ![](assets/screen_shot_2018-04-23at130646.jpg)

1. Click or tap **View Settings**.

   ![](assets/screen_shot_2018-04-23at130844.jpg)

1. Check **Translated** checkbox under **Translation** and tap/click **Update**.

   ![](assets/screen_shot_2018-04-23at130955.jpg)

You can now see a **Translated** column which shows the translation status of the pages.

![](assets/screen_shot_2018-04-23at133821.jpg)

