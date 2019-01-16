---
title: Trying out Content Fragments in We.Retail
seo-title: Trying out Content Fragments in We.Retail
description: null
seo-description: null
uuid: 38a05350-c08b-471c-b731-737e002344aa
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 62c30a1d-008d-4ba8-8011-fc8a0b008c22
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Trying out Content Fragments in We.Retail{#trying-out-content-fragments-in-we-retail}

Content Fragments allow you to create channel-neutral content, together with (possibly channel-specific) variations. **We.Retail** (as available in an out-of-the-box instance of AEM) provides the fragment **Arctic Surfing in Lofoten** as a basic sample. This illustrates that:

* Adobe Experience Manager (AEM) content fragments are [created and managed as page-independent assets](/content/help/en/experience-manager/6-4/assets/using/content-fragments). They allow you to create channel-neutral content, together with (possibly channel-specific) variations.

    * See [Where to Find Content Fragment assets in We.Retail](#wheretofindcontentfragmentsinweretail)

* You can then [use these fragments, and their variations, when authoring](../../authoring/using/content-fragments.md) your content pages.

    * See [Where Content Fragments are Used in We.Retail](#wherecontentfragmentsareusedinweretail)

For the full documentation on creating, managing, using and developing content fragments:

* See [Further Information](#furtherinformation)

>[!NOTE]
>
>**Content Fragments** and ** [Experience Fragments](../../authoring/using/experience-fragments.md)** are different features within AEM:
>
>* **Content Fragments** are editorial content, primarily text and related images. They are pure content, without design and layout.
>* **Experience Fragments** are fully laid out content; a fragment of a web page.  
>
>Experience Fragments can contain content in the form of Content Fragments, but not the other way around. [](../../authoring/using/experience-fragments.md)

### Where to Find Content Fragments in We.Retail {#where-to-find-content-fragments-in-we-retail}

There are several sample content fragments in We.Retail; navigate via **Assets**, **Files**, **We.Retail**, **English**, **Experiences**.

These include **Arctic Surfing in Lofoten**, a fragment together with related visual assets:

* Navigate via **Assets**, **Files**, **We.Retail**, **English**, **Experiences**, **Artic Surfing in Lofoten**:

    * [http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten](http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten)

![](assets/CF-44.png)

You can select and edit the **Arctic Surfing in Lofoten** fragment:

* [http://localhost:4502/editor.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten/arctic-surfing-in-lofoten](http://localhost:4502/editor.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten/arctic-surfing-in-lofoten)

Here you can [edit and manage](/content/help/en/experience-manager/6-4/assets/using/content-fragments) your fragment using the tabs (left side panel):

![](assets/CF-45-AA.png)  ![](assets/CF-45-A.png)

* ** [Variations](/content/help/en/experience-manager/6-4/assets/using/content-fragments-variations)** including [Markdown](/content/help/en/experience-manager/6-4/assets/using/content-fragments-markdown)   

* ** [Associated Content](/content/help/en/experience-manager/6-4/assets/using/content-fragments-assoc-content)**
* ** [Metadata](/content/help/en/experience-manager/6-4/assets/using/content-fragments-metadata)**

![](assets/CF-46.png) 

### Where Content Fragments are Used in We.Retail {#where-content-fragments-are-used-in-we-retail}

To illustrate [page authoring with a content fragment](../../authoring/using/content-fragments.md) there are several example pages provided under, for example:

* [http://localhost:4502/sites.html/content/we-retail/language-masters/en/experience](/sites.html/content/we-retail/language-masters/en/experience)

For example, the **Arctic Surfing in Lofoten** content fragment is referenced in the Sites page:

* Navigate via **Sites**, **We.Retail**, **Language Masters**, **English**, **Experience**. Then open **Arctic Surfing in Lofoten** for editing:

    * [http://localhost:4502/editor.html/content/we-retail/language-masters/en/experience/arctic-surfing-in-lofoten.html](http://localhost:4502/editor.html/content/we-retail/language-masters/en/experience/arctic-surfing-in-lofoten.html)

![](assets/CF-53.png) 

### Further Information {#further-information}

For more details see:

* [Working with Content Fragments](/content/help/en/experience-manager/6-4/assets/using/content-fragments)

    * Learn how to create, edit and manage your Content Fragment assets.

* [Page Authoring with Content Fragments](../../authoring/using/content-fragments.md)

    * Use your Content Fragment when authoring a page.

* [Developing AEM - Components for Content Fragments](../../developing/using/components-content-fragments.md)

    * An overview of the components for Content Fragments.

* [Developing and Extending Content Fragments](../../developing/using/customizing-content-fragments.md)

    * Information to help you develop and extend Content Fragments.

