---
title: Trying out Content Fragments in We.Retail
seo-title: Trying out Content Fragments in We.Retail
description: null
seo-description: null
uuid: 66daddfe-8e98-47b6-8499-db055887ac17
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: d1326737-f378-46d0-9916-61ead4d31639
---

# Trying out Content Fragments in We.Retail{#trying-out-content-fragments-in-we-retail}

Content Fragments allow you to create channel-neutral content, together with (possibly channel-specific) variations. **We.Retail** (as available in an out-of-the-box instance of AEM) provides the fragment **Arctic Surfing in Lofoten** as a basic sample. This illustrates that:

* Adobe Experience Manager (AEM) content fragments are [created and managed as page-independent assets](../../../assets/using/content-fragments.md). They allow you to create channel-neutral content, together with (possibly channel-specific) variations.

    * See [Where to Find Content Fragment assets in We.Retail](#where-to-find-content-fragments-in-we-retail)

* You can then [use these fragments, and their variations, when authoring](../../../sites/authoring/using/content-fragments.md) your content pages.

    * See [Where Content Fragments are Used in We.Retail](#where-content-fragments-are-used-in-we-retail)

For the full documentation on creating, managing, using and developing content fragments:

* See [Further Information](#further-information)

>[!NOTE]
>
>**Content Fragments** and ** [Experience Fragments](../../../sites/authoring/using/experience-fragments.md)** are different features within AEM:
>
>* **Content Fragments** are editorial content, primarily text and related images. They are pure content, without design and layout.
>* **Experience Fragments** are fully laid out content; a fragment of a web page.  
>
>Experience Fragments can contain content in the form of Content Fragments, but not the other way around. [](../../../sites/authoring/using/experience-fragments.md)

## Where to Find Content Fragments in We.Retail {#where-to-find-content-fragments-in-we-retail}

There are several sample content fragments in We.Retail; navigate via **Assets**, **Files**, **We.Retail**, **English**, **Experiences**.

These include **Arctic Surfing in Lofoten**, a fragment together with related visual assets:

* Navigate via **Assets**, **Files**, **We.Retail**, **English**, **Experiences**, **Artic Surfing in Lofoten**:

    * [http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten](http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten)

![](assets/cf-44.png)

You can select and edit the **Arctic Surfing in Lofoten** fragment:

* [http://localhost:4502/editor.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten/arctic-surfing-in-lofoten](http://localhost:4502/editor.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten/arctic-surfing-in-lofoten)

Here you can [edit and manage](../../../assets/using/content-fragments.md) your fragment using the tabs (left side panel):

![](do-not-localize/cf-45-aa.png) ![](do-not-localize/cf-45-a.png)

* ** [Variations](../../../assets/using/content-fragments-variations.md)** including [Markdown](../../../assets/using/content-fragments-markdown.md)   

* ** [Associated Content](../../../assets/using/content-fragments-assoc-content.md)**
* ** [Metadata](../../../assets/using/content-fragments-metadata.md)**

![](assets/cf-46.png) 

## Where Content Fragments are Used in We.Retail {#where-content-fragments-are-used-in-we-retail}

To illustrate [page authoring with a content fragment](../../../sites/authoring/using/content-fragments.md) there are several example pages provided under, for example:

* [http://localhost:4502/sites.html/content/we-retail/language-masters/en/experience](http://localhost:4502/sites.html/content/we-retail/language-masters/en/experience)

For example, the **Arctic Surfing in Lofoten** content fragment is referenced in the Sites page:

* Navigate via **Sites**, **We.Retail**, **Language Masters**, **English**, **Experience**. Then open **Arctic Surfing in Lofoten** for editing:

    * [http://localhost:4502/editor.html/content/we-retail/language-masters/en/experience/arctic-surfing-in-lofoten.html](http://localhost:4502/editor.html/content/we-retail/language-masters/en/experience/arctic-surfing-in-lofoten.html)

![](assets/cf-53.png) 

## Further Information {#further-information}

For more details see:

* [Working with Content Fragments](../../../assets/using/content-fragments.md)

    * Learn how to create, edit and manage your Content Fragment assets.

* [Page Authoring with Content Fragments](../../../sites/authoring/using/content-fragments.md)

    * Use your Content Fragment when authoring a page.

* [Developing AEM - Components for Content Fragments](../../../sites/developing/using/components-content-fragments.md)

    * An overview of the components for Content Fragments.

* [Developing and Extending Content Fragments](../../../sites/developing/using/customizing-content-fragments.md)

    * Information to help you develop and extend Content Fragments.

