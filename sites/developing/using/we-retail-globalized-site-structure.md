---
title: Trying out the Globalized Site Structure in We.Retail
seo-title: Trying out the Globalized Site Structure in We.Retail
description: null
seo-description: null
uuid: 9856c72c-5b4b-4f43-81b1-377931c63216
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 52e5d206-911b-48c3-820e-7e839ef3e310
disttype: dist5
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
modalsize: 426x240
index: y
internal: n
snippet: y
---

# Trying out the Globalized Site Structure in We.Retail{#trying-out-the-globalized-site-structure-in-we-retail}

We.Retail has been built with a globalized site structure offering a language masters that can be live-copied to country-specific web sites. Everything is set up out-of-the-box to allow you to experiment with this structure and the built-in translation capabilities.

## Trying it out {#trying-it-out}

1. Open the sites console from **Global Navigation -&gt; Sites**.
1. Switch to column view (if not already active) and select We.Retail. Note the example country structure with Switzerland, the United States, France, etc., along side the Language Masters.

   ![](assets/chlimage_1-106.png)

1. Select Switzerland and see the language roots for the languages of that country. Note that there is not yet any content below these roots.

   ![](assets/chlimage_1-107.png)

1. Switch to the list view and see that the language copies for the countries are all live copies.

   ![](assets/chlimage_1-108.png)

1. Return to column view and click on the Language Master and see the language master roots with content. Note that only English has content.

   We.Retail does not come with any translated content, but the structure and configuration is in place to allow you to demonstrate the translation services.

   ![](assets/chlimage_1-109.png)

1. With the English Language Master selected, open the **References** rail in the sites console and select **Language Copies**.

   ![](assets/chlimage_1-110.png)

1. Tick the checkbox next to the **Language Copies** label to select all language copies. In the **Update language copies** section of the rail, select the option to **Create a new translation project**. Provide a name for the project and click **Update**.

   ![](assets/chlimage_1-111.png)

1. A project is created for each language translation. View them under **Navigation -&gt; Projects**.

   ![](assets/chlimage_1-112.png)

1. Click on German to see the details of the translation project. Note that the status is in **Draft**. To start the translation with Microsoft's translation service, click the chevron next to the **Translation Job** heading and select **Start**.

   ![](assets/chlimage_1-113.png)

1. The translation project starts. Click on the ellipsis at the bottom of the card labeled Translation Job to see the details. Pages with the state **Ready for review** have already been translated by the translation service.

   ![](assets/chlimage_1-114.png)

1. Selecting one of the pages in the list and then **Preview in Sites** in the toolbar opens the translated page in the page editor.

   ![](assets/chlimage_1-115.png)

>[!NOTE]
>
>This procedure demonstrated the built-in integration with Microsoft machine translation. Using the [AEM Translation Integration Framework](../../administering/using/translation.md), you can integrate with many standard translation services to orchestrate the translation of AEM.

## Further Information {#further-information}

For further information, refer to the authoring document [Translating Content for Multilingual Sites](../../administering/using/translation.md) for complete technical details.
