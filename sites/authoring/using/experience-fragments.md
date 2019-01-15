---
title: Experience Fragments
seo-title: Experience Fragments
description: null
seo-description: null
uuid: 40376ef1-ee6e-4250-92bb-48d6a8f11385
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 672f8376-8473-4f0e-981f-033ad89f66ad
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

# Experience Fragments{#experience-fragments}

An Experience Fragment is a group of one or more components including content and layout that can be referenced within pages. They can contain any component.

An Experience Fragment:

* Is a part of an experience (page).
* Can be used across multiple pages.
* Is based on a template (editable only) to define structure and components.
* Is made up of one or more components, with layout, in a paragraph system.
* Can contain other experience fragments.
* Can be combined with other components (including other Experience Fragments) to form a complete page (experience).
* Can have different variations, which may share content and/or components.
* Can be broken down into building blocks that can be used across multiple variations of the fragment.

You can use Experience Fragments:

* If an author wants to re-use parts (a fragment of an experience) of a page, they need to copy and paste that fragment. Creating and maintaining these copy/paste experiences is time-consuming and prone to user errors. Experience Fragments eliminate the need for copy/paste.  
* To support the headless CMS use-case. Authors want to use AEM only for authoring but not for delivering to the customer. A third party system/touchpoint would consume that experience and then deliver to the end user.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-17T07:36:33.479-0500

<p>Add link when available.<br /> </p>

 -->

>[!NOTE]
>
>Write access for experience fragments requires the user account to be registered in the group:
>
>`experience-fragments-editors`
>
>Please contact your system administrator if you are experiencing any issues.

## When Should You Use Experience Fragments? {#when-should-you-use-experience-fragments}

Experience Fragments should be used:

* Whenever you want to reuse experiences.

    * Experiences that will be reused with same or similar content

* When you use AEM as a content delivery platform for third parties.

    * Any solution that wants to use AEM as the content delivery platform
    * Embedding content in third party touchpoints

* If you have an Experience with different variations or renditions.

    * Channel or context-specific variations
    * Experiences that make sense to group (for example a campaign with different experiences across channels)

* When you use Omnichannel Commerce.

    * Sharing commerce-related content on social media channels at scale
    * Making touchpoints transactional

## Creating an Experience Fragment {#creating-an-experience-fragment}

To create an Experience Fragment:

1. Select Experience Fragments from the Global Navigation.

   ![](assets/screen_shot_2018-04-05at92221am1.png)

1. Select **Create**. You can create **Folders** and/or **Experience Fragments**.

   Creating folders allows you to create a meaningful structure for your Experience Fragments.

   ![](assets/XF-Authoring-01.png)

1. From the required folder, select **Create** then **Experience Fragment** to open the **Create Experience Fragment** wizard.

   Select the required **Template**, then **Next**:

   ![](assets/XF-Authoring-02.png)

   >[!NOTE]
   >
   >You can use the [template editor](../../authoring/using/templates.md) to create your own template.
   >
   >
   >**Only** editable templates can be used; static templates are not fully compatible.

1. Enter the **Properties** for your **Experience Fragment**.

   A **Title** is mandatory. If the **Name** is left blank it will be derived from the **Title**.

   ![](assets/XF-Authoring-03.png)

1. Click **Create**.

   A message will be displayed. Select:

    * **Done** to return to the console   
    
    * **Open** to open the fragment editor

## Editing your Experience Fragment {#editing-your-experience-fragment}

The Experience Fragment Editor offers you similar capabilities to the normal page Editor. See [Editing Page Content](../../authoring/using/editing-content.md) for more information on how to use it.

The following example procedure illustrates how to create a teaser for a product:

1. Drag and drop a **Category Teaser** from the [Components Browser](../../authoring/using/author-environment-tools.md#componentsbrowser).

   ![](assets/XF-Authoring-04.png)

1. Select ** [Configure](../../authoring/using/editing-content.md#editconfigurecopycutdeletepaste)** from the component toolbar.
1. Add the **Asset** and define the **Properties** as required.
1. Confirm the definitions with **Done** (tick icon).
1. Add more components as required.

## Creating An Experience Fragment Variation {#creating-an-experience-fragment-variation}

You can create variations of your Experience Fragment, depending on your needs:

1. Open your fragment for [editing](/authoring/using/experience-fragments.html?cq_ck=1544783361584#EditingyourExperienceFragment).
1. Open the **Variations** tab.

   ![](assets/XF-Authoring-06.png)

1. **Create** allows you to create:

    * **Variation**
    * **Variation as live-copy**.

1. Define the required properties:

    * **Template**
    * **Title**
    * **Name**; if left blank it will be derived from the Title
    * **Description**
    * **Variation tags**

   ![](assets/XF-Authoring-07.png)

1. Confirm with **Done** (tick icon), the new variation will be shown in the panel:

   ![](assets/XF-Authoring-08.png)

## Using your Experience Fragment {#using-your-experience-fragment}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-07T00:33:58.138-0500

<p>cross-reference the integration with Target page as well....???</p>

 -->

You can now use your Experience Fragment when authoring your pages:

1. Open any page for editing.

   For example: [http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html](http://localhost:4502/editor.html/content/we-retail/language-masters/en/products/men.html)

1. Create an instance of the Experience Fragment component, by dragging the component from the Components browser to the page paragraph system:

   ![](assets/XF-Authoring-09.png)

1. Add the actual Experience Fragment to the component instance; either:

    * Drag the required fragment from the Assets Browser and drop onto the component  
    * Select **Configure** from the component toolbar and specify the fragment to use, confirm with **Done** (tick)

   ![](assets/XF-Authoring-10.png)

   >[!NOTE]
   >
   >Edit, in the component toolbar, operates as a shortcut to open the fragment in the fragment editor.

## Building Blocks {#building-blocks}

You can select one or more components to create a building block for recycling within your fragment:

#### Creating a Building Block {#creating-a-building-block}

To create a new Building Block:

1. In the Experience Fragment editor, select the components you want to re-use:

   ![](assets/XF-Authoring-12.png)

1. From the components toolbar, select **Convert to building block**:

   ![](assets/XF-Authoring-13-icon.png)

   For example:

   ![](assets/XF-Authoring-13.png)

1. Enter the name of the **Building Block**, and confirm with **Convert**:

   ![](assets/XF-Authoring-14.png)

1. The **Building Block** will be shown in the tab, and can be selected in the paragraph system:

   ![](assets/XF-Authoring-15.png)

#### Managing a Building Block {#managing-a-building-block}

Your building block is visible in the **Building Blocks** tab. For each block, the following actions are available:

* Go to master: open the master variation in a new tab  
* Rename   
* Delete

![](assets/XF-Authoring-16.png) 

#### Using a Building Block {#using-a-building-block}

You can drag your building block to the paragraph system of any fragment, as with any component.

## The Plain Rendition {#the-plain-rendition}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-07T00:32:54.042-0500

<p>provide a link to the developing docu page - when available</p>

 -->

Using the `.plain.` selector in the URL, you can access the plain HTML rendition.

This is available from the browser, but its primary purpose is to allow other applications (for example, third party web apps, custom mobile implementations) to access the content of the Experience Fragment directly, using only the URL.

The plain HTML rendition adds the protocol, host and context path to paths that are:

* of the type: `src`, `href`, or `action`

* or end with: `-src`, or `-href`

For example:

`.../brooklyn-coat/master.plain.html`

>[!NOTE]
>
>Links always reference the publish instance. They are intended to be consumed by third parties, so the link will always be called from the publish instance, not the author.

![](assets/XF-Authoring-17.png) 

## Exporting Experience Fragments {#exporting-experience-fragments}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-04T01:00:33.376-0500

<p>6.5 </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-04T01:04:06.780-0500

<p><a href="https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BExperience+Fragments%5D+Support+JSON+offers+for+Target">https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BExperience+Fragments%5D+Support+JSON+offers+for+Target</a></p> 
<h2>How to Document</h2> 
<p>Documentation should be added in, or below, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html">https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html</a></p> 
<ul> 
 <li>Title "Exporting Experience Fragments"</li> 
 <li>Explaining that: 
  <ul> 
   <li>by default, Experience Fragments are delivered in HTML format</li> 
   <li>for 3rd-party channels, export also happens in HTML format</li> 
   <li>for exporting to Adobe Target, i.e. creating offers that can be used in Target activities 
    <ul> 
     <li>Experience fragments can be exported in HTML format, JSON, or both, depending on if HTML or JSON offers are being created on Target side.</li> 
     <li>Media assets such as images are not being sent to Target, just their reference. The asset itself remains stored in AEM and is delivered from AEM publish, hence the need to publish experience fragments before export to Target.</li> 
     <li>Adobe Target must be connected with AEM, via Target Cloud Service in AEM, and respective cloud service attached to pages, either via configs or directly.</li> 
     <li>Explain the sequence of user interactions for exporting to Target, from admin and page editor.</li> 
    </ul> </li> 
  </ul> </li> 
</ul>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-04T02:52:02.140-0500

<p>as the page:</p> 
<p>- /content/help/en/experience-manager/6-4/sites/administering/using/experience-fragments-target.html</p> 
<p>already mentions exporting and publishing to Target, surely it makes more sense to have the detailed content there....oder?<br /> </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-04T02:58:08.164-0500

<p>Do we have to limit the discussion of JSON to the export to Target - can it be used by other solutions/3rd-parties?</p> 
<p>Or is it simply a matter of covering all the steps of exporting to Target as a specific case?<br /> </p>

 -->

By default, Experience Fragments are delivered in the HTML format. This can be used by both AEM and third party channels alike.

For export to Adobe Target, HTML is used. See [Target Integration with Experience Fragments](../../administering/using/experience-fragments-target.md) for full information.

<!-- 

Comment Type: draft

<p>By default, Experience Fragments are delivered in the HTML format. This can be used by both AEM and third party channels alike.</p> 
<p>For export to Adobe Target, JSON can also be used. See <a href="../../administering/using/experience-fragments-target.md">Target Integration with Experience Fragments</a> for full information.<br /> </p>

 -->

