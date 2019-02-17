---
title: Working with Content Fragments
seo-title: Working with Content Fragments
description: Learn how Content Fragments allow you to design, create, curate and use page-independent content.
seo-description: Learn how Content Fragments allow you to design, create, curate and use page-independent content.
uuid: 86f0f3ff-edab-4fc3-a350-396b8b64eb3e
contentOwner: Alison Heimoz
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 25618c2b-4335-447d-bb01-00c6066a6a8f
index: y
internal: n
snippet: y
---

# Working with Content Fragments{#working-with-content-fragments}

>[!CAUTION]
>
>Some Content Fragment functionality requires the application of [AEM 6.4 Service Pack 2 (6.4.2.0) or later](../../release-notes/sp-release-notes.md).

Adobe Experience Manager (AEM) Content Fragments allow you to design, create, curate and [publish page-independent content](../../sites/authoring/using/content-fragments.md). They allow you to prepare content ready for use in multiple locations/over multiple channels.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-01-22T02:33:57.556-0500
<p>need links to</p>
<ul>
<li>the JSON exporter page in 6-4</li>
<li>appropriate core components page</li>
</ul>
<p>msiegel (last week)<br /> agreed, with a brief explanation though, that content fragments can be delivered in JSON format by using Sling Model (JSON) export capabilities of AEM core components, and then the link. Also that this form of delivery allows using the component to manage which elements of a fragment to delivery, and that it allows bulk-delivery by adding multiple content fragment core components on the page that is used for API delivery</p>
<p>AJH - intro below - will add links when available</p>
<p> </p>
-->

Content fragments can also be delivered in JSON format, using the Sling Model (JSON) export capabilities of AEM core components. This form of delivery:

* enables you to use the component to manage which elements of a fragment to deliver
* allows bulk-delivery, by adding multiple content fragment core components on the page being used for API delivery

This and the following pages cover the tasks for creating, configuring and maintaining your content fragments:

* [Managing Content Fragments](../../assets/using/content-fragments-managing.md) - create your content fragments; then edit, publish and reference  

* [Content Fragment Models](../../assets/using/content-fragments-models.md) - enabling, creating and defining your models  

* [Variations - Authoring Fragment Content](../../assets/using/content-fragments-variations.md) - author the fragment content and create variations of the Master  

* [Markdown](../../assets/using/content-fragments-markdown.md) - using markdown syntax for your fragment  

* [Using Associated Content](../../assets/using/content-fragments-assoc-content.md) - adding associated content  

* [Metadata - Fragment Properties](../../assets/using/content-fragments-metadata.md) - viewing and editing the fragment properties

>[!NOTE]
>
>These pages should be read in conjunction with [Page Authoring with Content Fragments](../../sites/authoring/using/content-fragments.md).

The number of communication channels is increasing annually. Typically channels refer to the delivery mechanism, either as the:

* Physical channel; e.g. desktop, mobile.
* Form of delivery in a physical channel; e.g. the "product detail page", "product category page" for desktop, or "mobile web", "mobile app" for mobile.

However, you (probably) do not want to use exactly the same content for all channels - you need to optimize your content according to the specific channel.

Content fragments allow you to:

* Consider how to reach target audiences efficiently across channels.
* Create and manage channel-neutral editorial content.
* Build content pools for a range of channels.
* Design content variations for specific channels.
* Add images to your text by inserting assets (mixed-media fragments).

These content fragments can then be assembled to provide experiences over a variety of channels.

### Content Fragments and Content Services {#content-fragments-and-content-services}

AEM Content Services are designed to generalize the description and delivery of content in/from AEM beyond a focus on web pages.

They provide the delivery of content to channels that are not traditional AEM web pages, using standardized methods that can be consumed by any client. These channels can include:

* Single Page Applications
* Native Mobile Applications 
* other channels and touch-points external to AEM

Delivery is made in JSON format.

AEM Content Fragments can be used to describe and manage structured content. Structured content is defined in models that can contain a variety of content types; including text, numerical data, boolean, date and time, and more.

Together with the JSON export capabilities of AEM core components, this structured content can then be used to deliver AEM content to channels other than AEM pages.

>[!NOTE]
>
>**Content Fragments** and ** [Experience Fragments](../../sites/authoring/using/experience-fragments.md)** are different features within AEM:
>
>* **Content Fragments** are editorial content, primarily text and related images. They are pure content, without design and layout.
>* **Experience Fragments** are fully laid out content; a fragment of a web page.  
>
>Experience Fragments can contain content in the form of Content Fragments, but not the other way around.
>
>For further information see also [Understanding Content Fragments and Experience Fragments in AEM](/content/help/en/experience-manager/kt/platform-repository/using/content-fragments-experience-fragments-article-understand).

>[!CAUTION]
>
>Content fragments are not available in the classic UI.
>
>The Content Fragment component can be seen in the classic UI sidekick, but further functionality is not available.

>[!NOTE]
>
>AEM also supports the translation of fragment content. See [Creating Translation Projects for Content Fragments](../../assets/using/creating-translation-projects-for-content-fragments.md) for further information.

## Types of Content Fragment {#types-of-content-fragment}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-01-22T02:38:50.445-0500
<p>msiegel (last week)<br /> nice, I like this definition -<br /> brief, to the point, and without introduction of new terms and names. </p>
-->

Content fragments can be either:

* Simple fragments  
  These have no predefined structure. They contain only text, and images.  
  These are based on the Simple Fragment template.

* Fragments that contain structured content  
  These are based on a [Content Fragment Model](../../assets/using/content-fragments-models.md), which predefines a structure for the resulting fragment.  
  These can also be used to realize Content Services using the JSON Exporter.

## Content Type {#content-type}

Content fragments are:

* Stored as **Assets**:

    * Content fragments (and their variations) can be created and maintained from the **Assets** console.
    * Authored and edited in the Content Fragment Editor.

* Used in the [page editor by means of the **Content Fragment** component](../../sites/authoring/using/content-fragments.md) (referencing component):

    * The **Content Fragment** component is available to page authors. It allows them to reference, and deliver, the required content fragment in either HTML or JSON format.

Content Fragments are a content structure that:

* Are without layout or design (some text formatting is possible in Rich Text mode).
* Contain one, or more, [constituent parts](#constituentpartsofacontentfragment).
* Can [contain, or be connected to, images](#fragmentswithvisualassets).
* Can use [in-between content](#inbetweencontentwhenpageauthoringwithcontentfragments) when referenced on a page.  

* Are independent from the delivery mechanism (i.e. page, channel).

### Fragments with Visual Assets {#fragments-with-visual-assets}

To give authors more control of their content, images can be added to and/or integrated with a content fragment.

Assets can be used with a content fragment in several ways; each with its own advantage(s):

* **Insert Asset** into a fragment (mixed-media fragments)

    * Are an integral part of the fragment (see [Constituent Parts of a Content Fragment](#constituentpartsofacontentfragment)).
    * Define the position of the asset.
    * See [Inserting Assets into your Fragment](../../assets/using/content-fragments-variations.md#insertingassetsintoyourfragment) in the Fragment Editor for more information.

  >[!NOTE]
  >
  >Visual assets inserted into the content fragment itself are attached to the preceding paragraph. When the fragment is added to a page these assets are moved in relation to that paragraph when in-between content is added.

*

    * Are connected to a fragment; but not a fixed part of the fragment (see [Constituent Parts of a Content Fragment](#constituentpartsofacontentfragment)).
    * Allows some flexibility for positioning.
    * Are easily available for use (as in-between content) when using the fragment on a page.
    * See [Associated Content](../../assets/using/content-fragments-assoc-content.md) for more information.

* Assets available from the **Assets browser** of the page editor

    * Allow full flexibility for selection of an asset.
    * Allows some flexibility for positioning.
    * Does not provide the concept of being approved for a specific fragment.
    * See [Assets Browser](../../sites/authoring/using/author-environment-tools.md#assetsbrowser) for more information.

### Constituent Parts of a Content Fragment {#constituent-parts-of-a-content-fragment}

The content fragment assets are made up of the following parts (either directly or indirectly):

*

    * Elements correlate to the data fields holding content.
    * For fragments with structured content, you use a content model to create the content fragment. The elements (fields) specified in the model define the structure of the fragment. These elements (fields) can be of a variety of data-types.
    * For simple fragments:

        * The content is held in one (or more) multi-line text field(s), or element(s).  
        * The elements are defined in the fragment template (cannot be defined when authoring the fragment, see [Content Fragment Templates](../../sites/developing/using/content-fragment-templates.md)).

*

    * Blocks of text, that are:

        * separated by vertical spaces (carriage return)   
        * in multi-line text elements; in either simple or structured fragments

    * In the [Rich Text](../../assets/using/content-fragments-variations.md#richtext) and [Markdown](../../assets/using/content-fragments-variations.md#markdown) modes, a paragraph can be formatted as a header, in which case it and the following paragraph belong together as one unit.
    
    * Enable content control during page authoring.

*

    * Assets (images) inserted into the actual fragment and used as the internal content of a fragment.   
    * Are embedded in the paragraph system of the fragment.
    * Can be formatted when the [fragment is used/referenced on a page](../../sites/authoring/using/content-fragments.md).
    * Can only be added to, deleted from, or moved within, a fragment using the fragment editor. These actions cannot be made in the page editor.
    * Can only be added to, deleted from, or moved within, a fragment using [Rich Text format in the fragment editor](../../assets/using/content-fragments-variations.md#insertingassetsintoyourfragment).
    * Can only be added to multi-line text elements (any fragment type).  
    * Are attached to the preceding text (paragraph).

  >[!CAUTION]
  >
  >Can be (inadvertently) removed from a fragment by switching to Plain Text format.

  >[!NOTE]
  >
  >Assets can also be added as [additional (in-between) content](../../sites/authoring/using/content-fragments.md#usingassociatedcontent) when using a fragment on a page; using either Associated Content or assets from the Assets browser.

*

    * This is content external to, but with editorial relevance for, a fragment. Typically images, videos or other fragments.
    * The individual assets within the collection are available to be used with the fragment in the page editor, when it is added to a page. This means that they are optional, depending on the requirements of the specific channel.
    * The assets are [associated to fragments via collections](../../assets/using/content-fragments-assoc-content.md); associated collections allow the author to decide which assets to use when they are authoring the page.

        * Collections can be associated to fragments via templates, as default content, or by authors during fragment authoring.
        * [Assets (DAM) Collections](../../assets/using/managing-collections-touch-ui.md) are the basis for the associated content of fragments.

    * Optionally you can also add the fragment itself to a collection to aid tracking.

*

    * Use the [Assets metadata schemas](../../assets/using/metadata.md).
    * Tags can be created when you:

        * Create and author the fragment
        * Or later:

            * By viewing/editing the fragment **Properties** from the console
            * By editing the **Metadata** when in the fragment editor

  >[!CAUTION]
  >
  >Metadata processing profiles do not apply to Content Fragments.

*

    * An integral part of the fragment

        * Every content fragment has one instance of Master.
        * Master cannot be deleted.

    * Master is accessible in the fragment editor under ** [Variations](../../assets/using/content-fragments-variations.md)**.
    * Master is not a variation as such, but is the basis of all variations.

*

    * Renditions of fragment text that are specific to editorial purpose; can be related to channel but is not compulsory, can also be for ad-hoc local modifications.
    * Are created as copies of **Master**, but can then be edited a required; there is usually content overlap between the variations themselves.
    * Can be defined during fragment authoring or pre-defined in fragment templates.
    * Stored in the fragment, to help avoid scattering of content copies.
    * Variations can be [synchronized](../../assets/using/content-fragments-variations.md#synchronizingwithmaster) with Master if the Master content has been updated.
    * Can be [Summarized](../../assets/using/content-fragments-variations.md#summarizingtext) to quickly truncate the text to a predefined length.
    * Available under the [Variations](../../assets/using/content-fragments-variations.md) tab of the fragment editor.

### In-Between Content when Page Authoring with Content Fragments {#in-between-content-when-page-authoring-with-content-fragments}

In-between content:

* Is available for use in the [Page Editor when working with Content Fragments](../../sites/authoring/using/content-fragments.md).
* Is [additional content added within the flow of a fragment](../../sites/authoring/using/content-fragments.md#addinginbetweencontent) once it has been used/referenced on a page.
* In-between content can be added to any fragment, where there is only one element visible.  
* Associated content can be used, as can assets and/or components from the appropriate browser.

>[!CAUTION]
>
>The in-between content is page content. It is not stored in the content fragment.

### Required by Fragments {#required-by-fragments}

To create, edit and use content fragments you also need:

*

    * Are [enabled and then created using Tools](../../assets/using/content-fragments-models.md).
    * Required to [create a structured fragment](../../assets/using/content-fragments-managing.md#creatingcontentfragments).
    * Defines the structure of a fragment (title, content elements, tag definitions).
    * Content models definitions require a title and one data element; everything else is optional. The model defines a minimal scope of the fragment and default content if applicable. Authors cannot change the defined structure when authoring fragment content.

*

    * Required to [create a simple fragment](../../assets/using/content-fragments-managing.md#creatingcontentfragments).
    * Usually [developed during project implementation](../../sites/developing/using/content-fragment-templates.md); cannot be created when authoring.  
    
    * Defines the basics properties of a simple fragment (title, number of text elements, tag definitions).
    * Template definitions require a title and one text element; everything else is optional. The template defines a minimal scope of the fragment and default content if applicable. Authors can later extend a fragment beyond what is defined in the template.

*

    * Instrumental to delivering the fragment in HTML and/or JSON format.
    * Required to [reference the fragment on a page](../../sites/authoring/using/content-fragments.md).
    * Responsible for layout and delivery of a fragment; i.e. channels. 
    * Fragments need one or more dedicated components to define layout and deliver some or all elements/variations and associated content.  
    * Dragging a fragment onto a page in authoring will automatically associate the required component.

## Example Usage {#example-usage}

A fragment, with its elements and variations, can be used to create coherent content for multiple channels. When designing your fragment you need to consider what will be used where.

### We.Retail Sample {#we-retail-sample}

A sample fragment can be seen at:

` [http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten](http://localhost:4502/assets.html/content/dam/we-retail/en/experiences/arctic-surfing-in-lofoten)`

>[!MORE_LIKE_THIS]
>
>* [kt](/content/help/en/experience-manager/kt)
>* [Assets](/content/help/en/experience-manager/kt/assets)
>* [Internal](/content/help/en/experience-manager/kt/assets/internal)
>* [AEM 6.3 Assets: Assets management, metadata, and Insights enhancements](/content/help/en/experience-manager/kt/assets/internal/beta-management-metadata-insights-enhancements)
>* [AEM 6.3 Assets: Smart tags, templates, and catalog enhancements](/content/help/en/experience-manager/kt/assets/internal/beta-tags-templates-catalogs-enhancements)
>* [AEM 6.3 What's New - What’s New in AEM Desktop App 1.3 and 1.4](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-smarttags)
>* [AEM 6.3 What's New - Smart Tags](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-desktopapp13and14)
>* [AEM 6.3 What's New - Related Assets and Multilingual Asset Enhancements](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-related-assets-and-multilingual-enhancements)
>* [AEM 6.3 What's New - Asset Templates and Catalog Enhancements](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-templates-catalog-enhancements)
>* [AEM 6.3 What's New - Asset Insights Overview and Enhancements](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-insights-overview)
>* [AEM 6.3 What's New - Assets Usability and Performance Improvements](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-usability-perf-improvements)
>* [AEM 6.3 What's New - General Asset Management Enhancements](/content/help/en/experience-manager/kt/assets/internal/whats-new-assets-general-asset-mgmt-enhance)
>* [AEM 6.3 Assets: Integration with Livefyre and other enhancements](/content/help/en/experience-manager/kt/assets/internal/livefyre-integration-user-experience-improvements)
>* [Sizing AEM Assets Deployments](/content/help/en/experience-manager/kt/assets/internal/deployment-sizing-calculator-tutorial-use)
>* [AEM Assets Brand Portal Enablement Sessions](/content/help/en/experience-manager/kt/assets/internal/enablement-sessions-brand-portal-video)
>* [KB](/content/help/en/experience-manager/kt/assets/kb)
>* [Using](/content/help/en/experience-manager/kt/assets/using)
>* [Using Annotations in AEM Assets](/content/help/en/experience-manager/kt/assets/using/annotations-feature-video-use)
>* [Using Desktop App with AEM Assets](/content/help/en/experience-manager/kt/assets/using/aem-desktop-app-sync-status-technical-video-use)
>* [Set up Asset Insights with AEM Assets](/content/help/en/experience-manager/kt/assets/using/asset-insights-tutorial-setup)
>* [Using Search in AEM Assets](/content/help/en/experience-manager/kt/assets/using/search-feature-video-use)
>* [Understanding Smart Tags in AEM Assets](/content/help/en/experience-manager/kt/assets/using/smart-tags-feature-video-understand)
>* [Using Smart Tags with AEM Assets](/content/help/en/experience-manager/kt/assets/using/smart-tags-feature-video-use)
>* [Set up Smart Tags with AEM Assets](/content/help/en/experience-manager/kt/assets/using/smart-tags-technical-video-setup)
>* [Using the Video Player in AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-video-player-feature-video-use)
>* [Using Interactive Video with AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-interactive-video-feature-video-use)
>* [Understanding the Asset Viewer with AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-viewer-feature-video-understand)
>* [Using Custom Video Thumbnail with AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-video-thumbnails-feature-video-use)
>* [Understand Search Boosting in AEM Assets](/content/help/en/experience-manager/kt/assets/using/search-boost-technical-video-understand)
>* [Set up Asset Templates with AEM Assets and InDesign Server](/content/help/en/experience-manager/kt/assets/using/asset-templates-technical-video-setup)
>* [Using Asset Templates with AEM Assets and InDesign Server](/content/help/en/experience-manager/kt/assets/using/asset-templates-feature-video-use)
>* [Understanding Color Management with AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-color-management-technical-video-setup)
>* [Using Review Task to compare assets in AEM Assets](/content/help/en/experience-manager/kt/assets/using/review-task-compare-feature-video-use)
>* [Set up Brand Portal with AEM Assets](/content/help/en/experience-manager/kt/assets/using/brand-portal-technical-video-setup)
>* [Using Brand Portal with AEM Assets](/content/help/en/experience-manager/kt/assets/using/brand-portal-feature-video-use)
>* [Understanding Brand Portal with AEM Assets](/content/help/en/experience-manager/kt/assets/using/brand-portal-article-understand)
>* [Using Source File Translation with AEM Assets](/content/help/en/experience-manager/kt/assets/using/source-file-translation-feature-video-use)
>* [Set up 3D with AEM Assets](/content/help/en/experience-manager/kt/assets/using/3d-assets-technical-video-setup)
>* [Using 3D with AEM Assets](/content/help/en/experience-manager/kt/assets/using/3d-assets-feature-video-use)
>* [Developing for Brand Portal with AEM Assets](/content/help/en/experience-manager/kt/assets/using/brand-portal-technical-video-develop)
>* [Understanding InDesign files and Asset Templates in AEM Assets](/content/help/en/experience-manager/kt/assets/using/asset-templates-tutorial-understand)
>* [Using Image Sharpening with AEM Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-image-sharpening-feature-video-use)
>* [Understanding Multitenancy and Concurrent Development](/content/help/en/experience-manager/kt/assets/using/multitenancy-concurrent-development)
>* [Understanding Asset Share Commons](/content/help/en/experience-manager/kt/assets/using/asset-share-commons-article-understand)
>* [Set up Asset Share Commons on local AEM](/content/help/en/experience-manager/kt/assets/using/asset-share-commons-article-understand/asset-share-commons-feature-video-setup)
>* [Understanding the User Experience of Asset Share Commons](/content/help/en/experience-manager/kt/assets/using/asset-share-commons-article-understand/asset-share-commons-user-experience-feature-video-understand)
>* [Introduction to Theming in Asset Share Commons](/content/help/en/experience-manager/kt/assets/using/asset-share-commons-article-understand/asset-share-commons-feature-video-theming)
>* [Using Cascading Metadata in AEM Assets](/content/help/en/experience-manager/kt/assets/using/cascade-metadata-feature-video-use)
>* [Using Brand Portal with AEM Assets](/content/help/en/experience-manager/kt/assets/using/brand-portal-improvements-feature-video-use)
>* [Set up Smart Translation Search with AEM Assets](/content/help/en/experience-manager/kt/assets/using/smart-translation-search-technical-video-setup)
>* [Using Smart Translation Search with AEM Assets](/content/help/en/experience-manager/kt/assets/using/smart-translation-search-feature-video-use)
>* [Using Metadata Import and Export in AEM Assets](/content/help/en/experience-manager/kt/assets/using/metadata-import-feature-video-use)
>* [Using Smart Crop with AEM Assets Dynamic Media](/content/help/en/experience-manager/kt/assets/using/smart-crop-feature-video-use)
>* [Using Experience Fragments with AEM Assets Dynamic Media](/content/help/en/experience-manager/kt/assets/using/dynamic-media-experience-fragments-feature-video-use)
>* [Using Reports in AEM Assets](/content/help/en/experience-manager/kt/assets/using/asset-reports-feature-video-use)
>* [Using Closed User Groups with AEM Assets](/content/help/en/experience-manager/kt/assets/using/closed-user-groups-feature-video-use)
>* [Using Enhanced Smart Tags with AEM Assets](/content/help/en/experience-manager/kt/assets/using/enhanced-smart-tags-feature-video-use)
>* [Using Adobe Asset Link Extension with AEM Assets](/content/help/en/experience-manager/kt/assets/using/adobe-asset-link-feature-video-use)
>* [Using Asset Catalog with AEM Commerce and InDesign Server](/content/help/en/experience-manager/kt/assets/using/asset-catalog-template-feature-video-use)
>* [Understanding Adobe Asset Link authentication with AEM Assets](/content/help/en/experience-manager/kt/assets/using/adobe-asset-link-authentication-article-understand)
>* [Setup Enhanced Smart Tags in AEM Assets](/content/help/en/experience-manager/kt/assets/using/enhanced-smart-tags-technical-video-setup)
>* [Understanding Enhanced Smart Tags with AEM Assets](/content/help/en/experience-manager/kt/assets/using/enhanced-smart-tags-article-understand)
>* [Using Panorama and Vertical Image Viewer with AEM Assets Dynamic Media](/content/help/en/experience-manager/kt/assets/using/panorama-vertical-image-viewer-feature-video-use)
>* [Using Adobe Stock assets with AEM Assets](/content/help/en/experience-manager/kt/assets/using/stock-assets-feature-video-use)
>* [Set up Adobe Stock with AEM Assets](/content/help/en/experience-manager/kt/assets/using/adobe-stock-aem-assets-technical-video-setup)
>* [Using Check-in/Check-out in AEM Assets](/content/help/en/experience-manager/kt/assets/using/checkin-checkout-feature-video-use)
>* [Understanding Check-in/Check-out in AEM Assets](/content/help/en/experience-manager/kt/assets/using/checkin-checkout-technical-video-understand)
>* [Set up Asset Insights with AEM Assets and Launch, By Adobe](/content/help/en/experience-manager/kt/assets/using/asset-insights-launch-tutorial-setup)
>* [Using Remote DAM with AEM Assets](/content/help/en/experience-manager/kt/assets/using/remote-dam-feature-video-use)
>* [Index](/content/help/en/experience-manager/kt/assets/index)
>* [AEM Assets 6.3 Videos](/content/help/en/experience-manager/kt/assets/index/aem-6-3-assets)
>* [AEM Assets 6.4 Videos](/content/help/en/experience-manager/kt/assets/index/aem-6-4-assets)
>* [AEM Assets 6.4 Videos](/content/help/en/experience-manager/kt/assets/index/aem-6-5-assets)
>* [Beta](/content/help/en/experience-manager/kt/assets/beta)
>* [AEM Assets Remote DAM](/content/help/en/experience-manager/kt/assets/beta/remote-dam-feature-video-understand)
>* [Commerce](/content/help/en/experience-manager/kt/commerce)
>* [Internal](/content/help/en/experience-manager/kt/commerce/internal)
>* [KB](/content/help/en/experience-manager/kt/commerce/kb)
>* [Using](/content/help/en/experience-manager/kt/commerce/using)
>* [Understanding Architecture of Demandware Integration in AEM](/content/help/en/experience-manager/kt/commerce/using/demandware-technical-video-understand)
>* [Understanding Demandware Integration in AEM](/content/help/en/experience-manager/kt/commerce/using/demandware-feature-video-understand)
>* [Index](/content/help/en/experience-manager/kt/commerce/index)
>* [Videos highlighting the new commerce features for the AEM 6.3 release.](/content/help/en/experience-manager/kt/commerce/index/aem-6-3-commerce)
>* [Communities](/content/help/en/experience-manager/kt/communities)
>* [Internal](/content/help/en/experience-manager/kt/communities/internal)
>* [AEM 6.3 Communities: What's New and Release Overview](/content/help/en/experience-manager/kt/communities/internal/beta-what-new-release-overview)
>* [AEM 6.3 Communities: Scoring, badging, and ideation](/content/help/en/experience-manager/kt/communities/internal/beta-scoring-badging-leaderboards-ideation)
>* [AEM 6.3 Communities: Enablement and learning use cases](/content/help/en/experience-manager/kt/communities/internal/beta-enablement-learning-usecases)
>* [AEM 6.3 Communities: Key features](/content/help/en/experience-manager/kt/communities/internal/beta-key-features)
>* [KB](/content/help/en/experience-manager/kt/communities/kb)
>* [Using](/content/help/en/experience-manager/kt/communities/using)
>* [New Features Overview](/content/help/en/experience-manager/kt/communities/using/whats-new-feature-video-understand)
>* [Understanding Groups](/content/help/en/experience-manager/kt/communities/using/groups-feature-video-understand)
>* [Creating a New Community Site](/content/help/en/experience-manager/kt/communities/using/create-new-community-site-feature-video-use)
>* [How AEM Communities Works](/content/help/en/experience-manager/kt/communities/using/overview-feature-video-understand)
>* [How to Access Learning Resources](/content/help/en/experience-manager/kt/communities/using/viewing-learning-resources-feature-video-use)
>* [Calendar Functionality Overview](/content/help/en/experience-manager/kt/communities/using/calendar-overview-feature-video-understand)
>* [Understanding Blogging Functionality](/content/help/en/experience-manager/kt/communities/using/blogs-feature-video-undertstand)
>* [Using Reports and Analytics](/content/help/en/experience-manager/kt/communities/using/reports-analytics-feature-video-use)
>* [Publish Learning Resources for Enablement](/content/help/en/experience-manager/kt/communities/using/publish-learning-resources-enablement-feature-video-use)
>* [Editing Pages](/content/help/en/experience-manager/kt/communities/using/edit-pages-feature-video-use)
>* [New Features Overview](/content/help/en/experience-manager/kt/communities/using/updates-feature-video-understand)
>* [Index](/content/help/en/experience-manager/kt/communities/index)
>* [AEM 6.3 Communities](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_1497782182/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_1497782182/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-3-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [AEM 6.4 Communities](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_915934575/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_1497782182/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards_1497782182/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/communities/index/aem-6-4-communities/jcr:content/main-pars/step_with_card_1372438351/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [Forms](/content/help/en/experience-manager/kt/forms)
>* [Internal](/content/help/en/experience-manager/kt/forms/internal)
>* [AEM 6.3 Forms: New features and enhancements](/content/help/en/experience-manager/kt/forms/internal/beta-what-new)
>* [AEM 6.3 Forms: Authoring enhancements (Part 1)](/content/help/en/experience-manager/kt/forms/internal/beta-authoring-enhancements-1)
>* [AEM 6.3 Forms: Authoring enhancements (Part 2)](/content/help/en/experience-manager/kt/forms/internal/beta-authoring-enhancements-2)
>* [AEM 6.3 Forms: Data Integration](/content/help/en/experience-manager/kt/forms/internal/beta-data-integration)
>* [AEM 6.3 Forms: Form Workflow on OSGi](/content/help/en/experience-manager/kt/forms/internal/beta-forms-workflow-osgi)
>* [AEM 6.3 What's New - Theme Editor Correspondence Management Improvements](/content/help/en/experience-manager/kt/forms/internal/whats-new-forms-theme-editor)
>* [AEM 6.3 What's New - Authoring Improvements Secure and Simplify Authoring](/content/help/en/experience-manager/kt/forms/internal/whats-new-forms-authoring-mprovements)
>* [AEM 6.3 What's New - Workflow Integration](/content/help/en/experience-manager/kt/forms/internal/whats-new-forms-workflow-intergration)
>* [AEM 6.3 Forms: AEM Workflow Forms Technical Review](/content/help/en/experience-manager/kt/forms/internal/aem-workflow-formstechnicalreview)
>* [KB](/content/help/en/experience-manager/kt/forms/kb)
>* [Using](/content/help/en/experience-manager/kt/forms/using)
>* [Set up Data Integration with AEM Forms](/content/help/en/experience-manager/kt/forms/using/data-integration-technical-video-setup)
>* [Using User Profile Data Integration with AEM Forms](/content/help/en/experience-manager/kt/forms/using/user-profile-data-integration-feature-video-use)
>* [Using JDBC-based Form Data Models with AEM Forms](/content/help/en/experience-manager/kt/forms/using/jdbc-data-model-technical-video-use)
>* [Using Association Data Models with AEM Forms](/content/help/en/experience-manager/kt/forms/using/association-data-model-technical-video-use)
>* [Using Service Data Models with AEM Forms](/content/help/en/experience-manager/kt/forms/using/service-data-model-technical-video-use)
>* [Using CAPTCHAs with AEM Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/forms-captcha-feature-video-use)
>* [Using Correspondence Manager API via POST invocation in AEM Forms](/content/help/en/experience-manager/kt/forms/using/correspondence-mamangement-api-article-setup)
>* [Using Automated Tests with AEM Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/calvin-sdk-test-adaptive-forms-article-use)
>* [Using Adobe Sign with AEM Forms](/content/help/en/experience-manager/kt/forms/using/adobe-sign-integration-feature-video)
>* [Developing with Service Users in AEM Forms](/content/help/en/experience-manager/kt/forms/using/service-user-tutorial-develop)
>* [Using API to generate Document of Record with AEM Forms](/content/help/en/experience-manager/kt/forms/using/document-of-record-api-tutorial-use)
>* [Using AEM Workflow routing with AEM Forms](/content/help/en/experience-manager/kt/forms/using/aem-workflow-integration-technical-video-use)
>* [Developing with Useful Utility Functions in AEM Forms](/content/help/en/experience-manager/kt/forms/using/useful-utility-functions-article-develop)
>* [Developing with Output and Forms Services in AEM Forms](/content/help/en/experience-manager/kt/forms/using/output-and-forms-services-article-develop)
>* [Using PDFG in AEM Forms](/content/help/en/experience-manager/kt/forms/using/using-pdfg-in-aem-forms)
>* [Using POST mechanism to launch AEM Forms Create Correspondence Management Inteface](/content/help/en/experience-manager/kt/forms/using/using-post-to-open-cm-ui)
>* [N/A](/content/help/en/experience-manager/kt/forms/using/using-post-to-open-cm-ui/jcr:content/main-pars/download_section/download-1/file.sftmp)
>* [Configure Adobe Sign for AEM](/content/help/en/experience-manager/kt/forms/using/adobe-sign-technical-video-setup)
>* [Using Correspondence Management in AEM Forms](/content/help/en/experience-manager/kt/forms/using/using-correspondence-management-in-aem-forms)
>* [Using Assembler Service in AEM Forms](/content/help/en/experience-manager/kt/forms/using/using-assembler-service-in-aem-forms)
>* [Restricting the Rule Editor to specific groups in AEM Forms](/content/help/en/experience-manager/kt/forms/using/restricting-rule-editor-aem-forms-technical-video-use)
>* [Theme Editor Improvements in AEM Forms](/content/help/en/experience-manager/kt/forms/using/theme-editor-improvements-feature-video-use)
>* [Form Editor Improvements in AEM Forms](/content/help/en/experience-manager/kt/forms/using/form-editor-improvements-feature-video-use)
>* [Storing Adaptive Form Data](/content/help/en/experience-manager/kt/forms/using/storing_adaptive_form_data_in_db)
>* [N/A](/content/help/en/experience-manager/kt/forms/using/storing_adaptive_form_data_in_db/jcr:content/main-pars/image_2073616316/file.sftmp)
>* [List CM Letters in AEM Page](/content/help/en/experience-manager/kt/forms/using/listing-letters-in-portal-aem-page)
>* [Rule Editor Improvements in AEM Forms](/content/help/en/experience-manager/kt/forms/using/rule-editor-improvements-feature-video-use)
>* [Understanding Automated Forms Testing with AEM Forms](/content/help/en/experience-manager/kt/forms/using/calvin-sdk-test-adaptive-forms-feature-video)
>* [Editing Improvements for Correspondence Management in AEM Forms](/content/help/en/experience-manager/kt/forms/using/editing-improvements-correspondence-mgmt-feature-video-use)
>* [AEM Forms Samples](/content/help/en/experience-manager/kt/forms/using/aem-forms-samples)
>* [Configuring Microsoft Dynamics for AEM Forms](/content/help/en/experience-manager/kt/forms/using/config-dynamics-for-aem-forms)
>* [Using Dynamic Tables in AEM Forms Correspondence Management](/content/help/en/experience-manager/kt/forms/using/Dynamic-Tables-AEM-FORMS-CM)
>* [Using Microsoft Dynamics with AEM Forms](/content/help/en/experience-manager/kt/forms/using/using-ms-dynamics-with-aem-forms)
>* [Using Table Component in AEM Forms Print Channel Document](/content/help/en/experience-manager/kt/forms/using/table-in-print-channel-documents-video-use)
>* [Creating your first interactive communication for web channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms)
>* [Creating Document Fragments to hold the recipient name and address](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/five)
>* [Creating Web Channel Document Template AEM Forms](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/four)
>* [Creating Form Data Model](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/three)
>* [Creating DataSource Configuration in AEM Forms](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/two)
>* [Install and Configure Tomcat](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/one)
>* [Create Interactive Communication for Web Channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/six)
>* [Adding text and image content to web channel document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/seven)
>* [Configuring line chart for your first interactive communication document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/eight)
>* [Adding table to account balance panel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/nine)
>* [Configuring Retirement Outlook Panel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/ten)
>* [Configuring Investment Mix Panel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/eleven)
>* [Setting up the delivery of web channel document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-web-channel-aem-forms/twelve)
>* [Creating Form Data Model](/content/help/en/experience-manager/kt/forms/using/creating-form-data-model-feature-video-use)
>* [Creating Document Fragments in AEM Forms](/content/help/en/experience-manager/kt/forms/using/creating-document-fragment-feature-video-use)
>* [Creating Web Channel Document Template AEM Forms](/content/help/en/experience-manager/kt/forms/using/creating-web-channel-document-template-feature-video-use)
>* [Creating DataSource Configuration in AEM Forms](/content/help/en/experience-manager/kt/forms/using/creating-datasource-feature-video-use)
>* [Using Charts In Print Channel Documents](/content/help/en/experience-manager/kt/forms/using/using-charts-in-print-channel-documents-aem-forms-video-use)
>* [Preparing DataSource For Form Data Model](/content/help/en/experience-manager/kt/forms/using/preparing-datasource-for-form-data-model-tutorial-use)
>* [Using Form Data Model To Post Binary Data](/content/help/en/experience-manager/kt/forms/using/form-data-model-to-post-binary-data-tutorial-use)
>* [Delivery of Interactive Communication Document - Web Channel AEM Forms](/content/help/en/experience-manager/kt/forms/using/delivery-of-web-channel-document-tutorial-use)
>* [Using Table in Interactive Communication Documents - Web Channel](/content/help/en/experience-manager/kt/forms/using/table-in-web-channel-document-video-use)
>* [Using JSON Xpath in AEM Forms Form Data Model](/content/help/en/experience-manager/kt/forms/using/json-xpath-in-form-data-model-tutorial-use)
>* [Using PieCharts in Interactive Communications Document - Web Channel](/content/help/en/experience-manager/kt/forms/using/pie-charts-aem-forms-web-channel-video-use)
>* [Simplified Steps for Installing AEM Forms on Windows](/content/help/en/experience-manager/kt/forms/using/installing-aem-form-on-windows-tutorial-use)
>* [Using Reducer Functions in AEM Forms - Charts](/content/help/en/experience-manager/kt/forms/using/reducer-functions-in-charts-aem-forms-video-use)
>* [Using setvalue in AEM Forms workflow](/content/help/en/experience-manager/kt/forms/using/SetValue-in-Aem-Forms-workflow-tutorial-use)
>* [Using setvalue in AEM Forms workflow](/content/help/en/experience-manager/kt/forms/using/SetValue-in-Aem-Forms-workflow-tutorial-use/SetValue-in-Aem-Forms-workflow-tutorial-use)
>* [Developing with Adobe Sign APIs in AEM Forms](/content/help/en/experience-manager/kt/forms/using/adobe-sign-api-with-aem-tutorial-use)
>* [Using Send Email Step of Forms Workflow](/content/help/en/experience-manager/kt/forms/using/email-step-aem-workflow-video-use)
>* [Using Form Data Model Service as Step in Workflow](/content/help/en/experience-manager/kt/forms/using/form-data-model-service-as-step-in-workflow-video-use)
>* [Creating Form Data Model Without Data Source](/content/help/en/experience-manager/kt/forms/using/form-data-model-without-data-source-feature-video-use)
>* [Generating Interactive Communications Document for print channel using watch folder mechanism](/content/help/en/experience-manager/kt/forms/using/generating-interactive-communications-print-document-using-api-tutorial-use)
>* [Getting Started With Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use)
>* [Creating Adaptive Form](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part1)
>* [Adding Child Panels to Root Panel](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part2)
>* [Adding components to People panel](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part3)
>* [Adding components to Income panel](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part4)
>* [Adding components to Assets section](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part5)
>* [Using functions and code editor](/content/help/en/experience-manager/kt/forms/using/adaptive-forms-getting-started-tutorial-use/part6)
>* [Listing Custom Assets Type in AEM Forms Portal](/content/help/en/experience-manager/kt/forms/using/listing-custom-asset-types-tutorial-use)
>* [Registering Custom Asset Types](/content/help/en/experience-manager/kt/forms/using/listing-custom-asset-types-tutorial-use/part1)
>* [Listing Custom Asset Types in AEM Forms](/content/help/en/experience-manager/kt/forms/using/listing-custom-asset-types-tutorial-use/part2)
>* [Using Watched Folders in AEM Forms](/content/help/en/experience-manager/kt/forms/using/watched-folders-document-services-article-use)
>* [Handling Adaptive Form Submission](/content/help/en/experience-manager/kt/forms/using/adaptive-form-submission-tutorial-use)
>* [Submitting Adaptive Form to AEM Workflow](/content/help/en/experience-manager/kt/forms/using/adaptive-form-submission-tutorial-use/invoking-aem-workflow-on-form-submission-article-use)
>* [Submitting Adaptive Form to External Server](/content/help/en/experience-manager/kt/forms/using/adaptive-form-submission-tutorial-use/submitting-adaptive-forms-to-external-server-article-use)
>* [Submitting To Thank You Page](/content/help/en/experience-manager/kt/forms/using/adaptive-form-submission-tutorial-use/submitting-adaptive-forms-thank-you-page-article-use)
>* [Sending Email on Adaptive Form Submission](/content/help/en/experience-manager/kt/forms/using/adaptive-form-submission-tutorial-use/sending-email-on-adaptive-form-submission)
>* [Using ldap with Aem Forms Workflow](/content/help/en/experience-manager/kt/forms/using/aem-forms-workflow-with-ldap-article-use)
>* [Using Document Services in AEM Forms](/content/help/en/experience-manager/kt/forms/using/documentservices-aem-forms-tutorial-use)
>* [Creating your first interactive communication for the print channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms)
>* [Install and Configure Tomcat](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part1)
>* [Creating DataSource Configuration in AEM Forms](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part2)
>* [Creating Form Data Model](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part3)
>* [Create Layout using Forms Designer](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part4)
>* [Create Interactive Communication For Print Channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part6)
>* [Creating Document Fragments to hold the recipient name and address](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part5)
>* [Adding text and image content to print channel document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part7)
>* [Adding table to contributions section](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part9)
>* [Configuring line chart for your first interactive communication document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part8)
>* [Generating Print Channel Documents Using Watched Folder](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part10)
>* [Opening Agent UI On POST Submission](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms/Part11)
>* [Getting Started With AEM Forms](/content/help/en/experience-manager/kt/forms/using/aem-forms-getting-started-tutorial-use)
>* [Prefill Service in Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/prefill-service-adaptive-forms-article-use)
>* [Acroform To AEM Forms](/content/help/en/experience-manager/kt/forms/using/acroforms-aem-forms-tutorial-use)
>* [Two Column Layout in AEM Forms Print Channel Document](/content/help/en/experience-manager/kt/forms/using/two-column-layout-aem-forms-article-use)
>* [Tagging and Storing AEM Forms DoR in DAM](/content/help/en/experience-manager/kt/forms/using/tagging-and-saving-document-of-record-in-dam-article-use)
>* [Using Transaction Reporting in AEM Forms](/content/help/en/experience-manager/kt/forms/using/transaction-reporting-aem-forms-article-use)
>* [Data based routing of Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/routing-adaptive-forms-based-on-data-aem-forms-article-use)
>* [Certifying Document in AEM Forms](/content/help/en/experience-manager/kt/forms/using/certifying-documents-aem-forms-tutorial)
>* [Capturing workflow comments in Adaptive Forms Workflow](/content/help/en/experience-manager/kt/forms/using/capturing-workflow-comments-aem-workflow-article)
>* [PrePopulate HTML5 Forms using data attribute](/content/help/en/experience-manager/kt/forms/using/prepopulating_html5_forms_in_aem_forms-article)
>* [Setting value of Json Data Element in AEM Forms Workflow](/content/help/en/experience-manager/kt/forms/using/setvalue-json-data-in-aem-forms-workflow-article-use)
>* [Configuring DataSource with Salesforce in AEM Forms 6.3 and 6.4](/content/help/en/experience-manager/kt/forms/using/using-adaptive-forms-with-sales-force-integration-tutorial)
>* [Creating your first interactive communication for the print channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial)
>* [Install and Configure Tomcat](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part1)
>* [Creating DataSource Configuration in AEM Forms](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part2)
>* [Creating Form Data Model](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part3)
>* [Create Layout using Forms Designer](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part4)
>* [Create Interactive Communication For Print Channel](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part6)
>* [Creating Document Fragments to hold the recipient name and address](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part5)
>* [Adding text and image content to print channel document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part7)
>* [Adding table to contributions section](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part9)
>* [Configuring line chart for your first interactive communication document](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part8)
>* [Generating Print Channel Documents Using Watched Folder](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part10)
>* [Opening Agent UI On POST Submission](/content/help/en/experience-manager/kt/forms/using/interactive-communication-print-channel-aem-forms-tutorial/Part11)
>* [Using Geolocation API's in Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/using-geolocation-api-in-aem-forms-article)
>* [Creating Computed Form Data Model Elements in AEM Forms](/content/help/en/experience-manager/kt/forms/using/computed-form-data-model-elements-aem-forms-feature-video)
>* [Getting Started with AEM Forms and Adobe Campaign Standard](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial)
>* [Generating JSON Web Token and Access Token](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial/Part1)
>* [Prefilling Adaptive Form using ACS Profile](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial/Part3)
>* [Creating Campaign Profile on Adaptive Form Submission](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial/Part2)
>* [Create Campaign Profile Using Form Data Model](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial/Part4)
>* [Create Form Data Model to fetch ACS profile information](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-campaign-standard-getting-started-tutorial/Part5)
>* [Merging Adaptive Form Data with Acroform](/content/help/en/experience-manager/kt/forms/using/merging-adaptive-form-data-with-acroform-article-use)
>* [Generate PDF from HTML5 Form Submission](/content/help/en/experience-manager/kt/forms/using/generating-pdf-on-mobile-form-submission-article-use)
>* [Translating Adaptive Form](/content/help/en/experience-manager/kt/forms/using/translating-adaptive-forms-tutorial-use)
>* [Integrate AEM Forms with Microsoft Dynamics 365](/content/help/en/experience-manager/kt/forms/using/Integrate-AEM-Forms-With-Dynamics-365)
>* [Implementing Custom AEM Process Step](/content/help/en/experience-manager/kt/forms/using/custom-process-step-aem-forms-tutorial)
>* [AEM Forms with JSON Schema and Data](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-json-schema-and-data-tutorial)
>* [Create Adaptive Form based on JSON Schema](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-json-schema-and-data-tutorial/part1)
>* [Storing Submitted Data in Database](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-json-schema-and-data-tutorial/part2)
>* [Storing JSON Schema in Database](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-json-schema-and-data-tutorial/part3)
>* [Querying Submitted Data](/content/help/en/experience-manager/kt/forms/using/aem-forms-with-json-schema-and-data-tutorial/part4)
>* [Writing a Custom Submit in AEM Forms](/content/help/en/experience-manager/kt/forms/using/custom-submit-aem-forms-article)
>* [Rendering XDP into PDF with Usage Rights](/content/help/en/experience-manager/kt/forms/using/rendering-and-reader-extending-xdp-templates-article)
>* [Ability to modify Data Source Configuration Settings](/content/help/en/experience-manager/kt/forms/using/modify-data-source-configuration-settings-article)
>* [Create Re-Usable AEM Forms Workflow Models](/content/help/en/experience-manager/kt/forms/using/re-usable-aem-forms-workflow-models-article)
>* [Ability to add web channel to an existing print channel](/content/help/en/experience-manager/kt/forms/using/add-web-channel-to-print-channel-document-article)
>* [Barcode Service With Adaptive Forms](/content/help/en/experience-manager/kt/forms/using/barcode-service-adaptive-forms-article)
>* [Generate PDF from HTM5 Form Submission](/content/help/en/experience-manager/kt/forms/using/generate-pdf-from-mobile-form-submission-article)
>* [Index](/content/help/en/experience-manager/kt/forms/index)
>* [AEM 6.3 Forms Tutorials and Videos](/content/help/en/experience-manager/kt/forms/index/aem-6-3-forms)
>* [AEM 6.4 Forms Tutorials and Videos](/content/help/en/experience-manager/kt/forms/index/aem-6-4-forms)
>* [AEM 6.5 Forms Tutorials and Videos](/content/help/en/experience-manager/kt/forms/index/aem-6-5-forms)
>* [Beta](/content/help/en/experience-manager/kt/forms/beta)
>* [Form Data Model Enhancements](/content/help/en/experience-manager/kt/forms/beta/form-data-model-enhancements-feature-video-understand)
>* [Interactive Communication Enhancements](/content/help/en/experience-manager/kt/forms/beta/interactive-communication-enhancements-feature-video-understand)
>* [Using Adobe Sign Cloud Signatures with Adaptive Forms](/content/help/en/experience-manager/kt/forms/beta/adobe-sign-cloud-signatures-adaptive-forms-feature-video-understand)
>* [Dynamically Populate Adaptive Form Controls](/content/help/en/experience-manager/kt/forms/beta/dynamic-population-adaptive-forms-controls-feature-video-understand)
>* [Workflow Enhancements](/content/help/en/experience-manager/kt/forms/beta/workflow-enhancements-feature-video-understand)
>* [Mobile](/content/help/en/experience-manager/kt/mobile)
>* [Internal](/content/help/en/experience-manager/kt/mobile/internal)
>* [KB](/content/help/en/experience-manager/kt/mobile/kb)
>* [Using](/content/help/en/experience-manager/kt/mobile/using)
>* [Index](/content/help/en/experience-manager/kt/mobile/index)
>* [AEM Foundation](/content/help/en/experience-manager/kt/platform-repository)
>* [Internal](/content/help/en/experience-manager/kt/platform-repository/internal)
>* [AEM 6.3 Platform: Online revision cleanup on TarMK](/content/help/en/experience-manager/kt/platform-repository/internal/beta-online-revision-cleanup-tarmk)
>* [AEM 6.3 Platform: Projects, workflows, and inbox](/content/help/en/experience-manager/kt/platform-repository/internal/beta-projects-workflows-inbox)
>* [AEM 6.3 What's New - We.Retail Reference Site](/content/help/en/experience-manager/kt/platform-repository/internal/whats-new-platform-weretailreferencesite)
>* [AEM 6.3 What's New - Integrations with Marketing Cloud Solutions](/content/help/en/experience-manager/kt/platform-repository/internal/whats-new-platform-integrationswithMCsolutions)
>* [AEM 6.3 What's New - MongoMK Cross-geo Deployment and Production Readiness](/content/help/en/experience-manager/kt/platform-repository/internal/whats-new-platform-mongomkcrossgeodeployment)
>* [AEM 6.3 What's New - HTL Enhancements](/content/help/en/experience-manager/kt/platform-repository/internal/whats-new-platform-htl-enhancements)
>* [AEM 6.3 What's New Videos](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards_505605962/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards_505605962/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_770649399/step-with-card-pars/tutorial_cards_505605962/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_1138826323/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_1138826323/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_1138826323/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_1138826323/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_1138826323/step-with-card-pars/tutorial_cards_769783197/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_35738720/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_35738720/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/internal/aem-6-3-whats-new-videos/jcr:content/main-pars/step_with_card_35738720/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [AEM 6.3 Platform: Upgrade](/content/help/en/experience-manager/kt/platform-repository/internal/beta-upgrade)
>* [AEM 6.3 Platform: Operations dashboard](/content/help/en/experience-manager/kt/platform-repository/internal/beta-operations-dashboard)
>* [AEM 6.3 What's New - UI Updates](/content/help/en/experience-manager/kt/platform-repository/internal/whats-new-platform-uiupdates)
>* [KB](/content/help/en/experience-manager/kt/platform-repository/kb)
>* [Using](/content/help/en/experience-manager/kt/platform-repository/using)
>* [Developing for the OSGi HTTP Whiteboard in AEM](/content/help/en/experience-manager/kt/platform-repository/using/osgi-http-whiteboard-code-sample-develop)
>* [Developing OAuth Scopes in AEM](/content/help/en/experience-manager/kt/platform-repository/using/oauth-code-sample-develop)
>* [Developing Sling Model Exporters in AEM](/content/help/en/experience-manager/kt/platform-repository/using/sling-model-exporter-tutorial-develop)
>* [Understanding Sling Model Exporters in AEM](/content/help/en/experience-manager/kt/platform-repository/using/sling-model-exporter-tutorial-understand)
>* [Using Calendar View with AEM Projects and Inbox](/content/help/en/experience-manager/kt/platform-repository/using/projects-and-inbox-calendar-view-feature-video-use)
>* [Using the Inbox in AEM](/content/help/en/experience-manager/kt/platform-repository/using/inbox-feature-video-use)
>* [Developing Projects in AEM - Part 1](/content/help/en/experience-manager/kt/platform-repository/using/projects-part1-tutorial-develop)
>* [Developing Projects in AEM - Part 2](/content/help/en/experience-manager/kt/platform-repository/using/projects-part2-tutorial-develop)
>* [Developing for Task Management in AEM](/content/help/en/experience-manager/kt/platform-repository/using/task-management-api-code-sample-develop)
>* [Using Online Revision Clean-up in AEM](/content/help/en/experience-manager/kt/platform-repository/using/revision-cleanup-technical-video-use)
>* [Set up AEM Dispatcher on macOS](/content/help/en/experience-manager/kt/platform-repository/using/dispatcher-macos-technical-video-setup)
>* [Set up Sling Dynamic Include in AEM](/content/help/en/experience-manager/kt/platform-repository/using/sling-dynamic-include-technical-video-setup)
>* [Understanding Content Fragments and Experience Fragments in AEM](/content/help/en/experience-manager/kt/platform-repository/using/content-fragments-experience-fragments-article-understand)
>* [Using Project Masters in AEM](/content/help/en/experience-manager/kt/platform-repository/using/projects-masters-feature-video-use)
>* [Using the SSL Wizard in AEM](/content/help/en/experience-manager/kt/platform-repository/using/ssl-wizard-technical-video-use)
>* [Developing for AEM 6.3](/content/help/en/experience-manager/kt/platform-repository/using/aem-6-3-article-develop)
>* [Developing for Cross-Origin Resource Sharing (CORS) with AEM](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-technical-video-develop)
>* [Understanding Cross-Origin Resource Sharing (CORS) with AEM](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-article-understand)
>* [Understanding Authentication support in AEM](/content/help/en/experience-manager/kt/platform-repository/using/authentication-support-article-understand)
>* [Developing a new project in AEM](/content/help/en/experience-manager/kt/platform-repository/using/new-aem-project-tutorial-develop)
>* [Set up an AEM Project using the AEM Maven Project Archetype](/content/help/en/experience-manager/kt/platform-repository/using/maven-archetype-technical-video-setup)
>* [User Experience Enhancements in AEM](/content/help/en/experience-manager/kt/platform-repository/using/enhancements-ux-feature-video-use)
>* [Using the System Overview Dashboard in AEM](/content/help/en/experience-manager/kt/platform-repository/using/system-overview-feature-video-use)
>* [Using oak-run.jar to Manage Indexes in AEM](/content/help/en/experience-manager/kt/platform-repository/using/oak-run-index-technical-video-use)
>* [Understanding Reasons to Upgrade AEM](/content/help/en/experience-manager/kt/platform-repository/using/upgrade-aem-article-understand)
>* [Understanding Reasons to Upgrade to AEM 6.3](/content/help/en/experience-manager/kt/platform-repository/using/upgrade-aem-article-understand/upgrade-aem-6-3-article-understand)
>* [Understanding Reasons to Upgrade to AEM 6.3](/content/help/en/experience-manager/kt/platform-repository/using/upgrade-aem-6-3-article-understand)
>* [Developing for AEM 6.4](/content/help/en/experience-manager/kt/platform-repository/using/aem-article-develop)
>* [Developing for AEM 6.3](/content/help/en/experience-manager/kt/platform-repository/using/aem-article-develop/aem-6-3-article-develop)
>* [Using the Workflow Editor in AEM](/content/help/en/experience-manager/kt/platform-repository/using/workflow-editor-feature-video-use)
>* [Using the CI/CD Pipeline in Cloud Manager for AEM](/content/help/en/experience-manager/kt/platform-repository/using/cloud-manager-cicd-pipeline-feature-video-use)
>* [AEM Security Notification (November 2018)](/content/help/en/experience-manager/kt/platform-repository/using/aem-security-notification-article)
>* [Understanding Java API preference in AEM](/content/help/en/experience-manager/kt/platform-repository/using/java-apis-article-understand)
>* [Set up a Local AEM Development Environment](/content/help/en/experience-manager/kt/platform-repository/using/local-aem-dev-environment-article-setup)
>* [Understanding Adobe IMS authentication with AEM on Adobe Managed Services](/content/help/en/experience-manager/kt/platform-repository/using/adobe-ims-authentication-technical-video-understand)
>* [Setup public and private keys for use with AEM and Adobe I/O](/content/help/en/experience-manager/kt/platform-repository/using/public-private-keys-tutorial-setup)
>* [Index](/content/help/en/experience-manager/kt/platform-repository/index)
>* [AEM 6.3 tutorials videos new platform foundation Adobe Experience Manager](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-platform)
>* [AEM 6.3 feature videos new projects Adobe Experience Manager](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-3-projects/jcr:content/main-pars/step_with_card_892877700/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [AEM 6.4 tutorial videos new platform foundation Adobe Experience Manager](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-foundation)
>* [AEM 6.3 feature videos new projects Adobe Experience Manager](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-2/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-3/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects/jcr:content/main-pars/step_with_card/step-with-card-pars/tutorial_cards/tutorial-card-4/file)
>* [N/A](/content/help/en/experience-manager/kt/platform-repository/index/aem-6-4-projects/jcr:content/main-pars/step_with_card_892877700/step-with-card-pars/tutorial_cards/tutorial-card-1/file)
>* [Sites](/content/help/en/experience-manager/kt/sites)
>* [Internal](/content/help/en/experience-manager/kt/sites/internal)
>* [AEM 6.3 Sites: Admin and page editor improvements](/content/help/en/experience-manager/kt/sites/internal/beta-site-admin-page-editor-improvements)
>* [AEM 6.3 Sites: Core components and template editor improvements](/content/help/en/experience-manager/kt/sites/internal/beta-core-components-template-editor-improvements)
>* [AEM 6.3 What's New - Core Components](/content/help/en/experience-manager/kt/sites/internal/whats-new-sites-core-components)
>* [AEM 6.3 What's New - Experience Fragments](/content/help/en/experience-manager/kt/sites/internal/whats-new-sites-experience-fragments)
>* [AEM 6.3 What's New - Content Fragments](/content/help/en/experience-manager/kt/sites/internal/whats-new-sites-content-fragments)
>* [AEM 6.3 What's New - Sites Admin and Page Authoring Improvements](/content/help/en/experience-manager/kt/sites/internal/whats-new-sites-admin-page-authoring)
>* [AEM 6.3 Sites: Content Fragments](/content/help/en/experience-manager/kt/sites/internal/beta-content-fragments)
>* [AEM 6.3 Sites: Experience Fragments](/content/help/en/experience-manager/kt/sites/internal/beta-experience-fragments)
>* [KB](/content/help/en/experience-manager/kt/sites/kb)
>* [Using](/content/help/en/experience-manager/kt/sites/using)
>* [Using Mixed-media with AEM Content Fragments](/content/help/en/experience-manager/kt/sites/using/content-fragments-mixed-media-feature-video-use)
>* [Using Content Fragments in AEM](/content/help/en/experience-manager/kt/sites/using/content-fragments-feature-video-use)
>* [Using Content Fragments in AEM 6.3](/content/help/en/experience-manager/kt/sites/using/content-fragments-feature-video-use/aem-63)
>* [Understanding AEM Content Fragments](/content/help/en/experience-manager/kt/sites/using/content-fragments-feature-video-understand)
>* [Using AEM Experience Fragments](/content/help/en/experience-manager/kt/sites/using/experience-fragments-feature-video-use)
>* [Using Translation with AEM Content Fragments](/content/help/en/experience-manager/kt/sites/using/content-fragments-translation-feature-video-use)
>* [Touch UI Authoring Improvements in AEM 6.3](/content/help/en/experience-manager/kt/sites/using/page-editor-feature-video-use)
>* [Introducing Multi Site Manager Touch UI Interfaces](/content/help/en/experience-manager/kt/sites/using/multi-site-manager-feature-video-use)
>* [Using Publication Management with AEM Sites](/content/help/en/experience-manager/kt/sites/using/publication-management-feature-video-use)
>* [Understanding AEM Content Fragment Delivery Considerations](/content/help/en/experience-manager/kt/sites/using/content-fragments-delivery-considerations-article-understand)
>* [Using Language Copy with AEM Sites](/content/help/en/experience-manager/kt/sites/using/language-copy-feature-video-use)
>* [Set up Social Posting with AEM Experience Fragments](/content/help/en/experience-manager/kt/sites/using/experience-fragments-social-technical-video-setup)
>* [Developing Component Icons in AEM Sites](/content/help/en/experience-manager/kt/sites/using/component-icons-technical-video-develop)
>* [Using the Components Console with AEM Sites](/content/help/en/experience-manager/kt/sites/using/components-console-feature-video-use)
>* [Set up Adobe Analytics Activity Map with AEM Sites](/content/help/en/experience-manager/kt/sites/using/activity-map-feature-video-setup)
>* [Using Adobe Analytics Activity Map with AEM Sites](/content/help/en/experience-manager/kt/sites/using/activity-map-feature-video-use)
>* [Troubleshooting Adobe Analytics Activity Map with AEM Sites](/content/help/en/experience-manager/kt/sites/using/activity-map-feature-video-troubleshoot)
>* [Using Timewarp with AEM Sites](/content/help/en/experience-manager/kt/sites/using/timewarp-feature-video-use)
>* [Template Editor Enhancements in AEM 6.3](/content/help/en/experience-manager/kt/sites/using/template-editor-feature-video-use)
>* [Using Page Difference with AEM Sites](/content/help/en/experience-manager/kt/sites/using/page-diff-feature-video-use)
>* [Simple search implementation guide](/content/help/en/experience-manager/kt/sites/using/search-tutorial-develop)
>* [Developing Resource Statuses in AEM Sites](/content/help/en/experience-manager/kt/sites/using/resource-status-tutorial-develop)
>* [Understanding Mixed-Media with AEM Content Fragments](/content/help/en/experience-manager/kt/sites/using/content-fragments-mixed-media-technical-video-understand)
>* [Setup Translation Rules in AEM](/content/help/en/experience-manager/kt/sites/using/translation-rules-editor-technical-video-setup)
>* [Understanding Publication Management with AEM Sites](/content/help/en/experience-manager/kt/sites/using/publication-management-feature-video-understand)
>* [Developing for Page Difference in AEM Sites](/content/help/en/experience-manager/kt/sites/using/page-diff-technical-video-develop)
>* [Using Social Media Sharing in AEM Sites](/content/help/en/experience-manager/kt/sites/using/social-media-sharing-feature-video-use)
>* [Understanding AEM Experience Fragments](/content/help/en/experience-manager/kt/sites/using/experience-fragments-feature-video-understand)
>* [Understanding Core Components](/content/help/en/experience-manager/kt/sites/using/core-components-feature-video-understand)
>* [Getting Started with AEM Sites - WKND Tutorial](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop)
>* [Getting Started with AEM Sites Chapter 1 - Project Setup](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part1)
>* [Getting Started with AEM Sites Chapter 2 - Creating a Base Page and Template](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part2)
>* [Getting Started with AEM Sites Chapter 3 - Client-Side Libraries and Responsive Grid](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part3)
>* [Getting Started with AEM Sites Chapter 4 - Developing with the Style System](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part4)
>* [Getting Started with AEM Sites Chapter 5 - Navigation](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part5)
>* [legacy](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy)
>* [Getting Started with AEM Sites Part 1 - Project Setup](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part1)
>* [Getting Started with AEM Sites Part 2 - Creating a Base Page and Template](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part2)
>* [Getting Started with AEM Sites Part 3 - Client-Side Libraries and Responsive Grid](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part3)
>* [Getting Started with AEM Sites Part 4 - Developing with the Style System](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part4)
>* [Getting Started with AEM Sites Part 5 - Navigation](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part5)
>* [Getting Started with AEM Sites Part 6 - Sling Models and Card Component](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part6)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/legacy/part6/jcr:content/main-pars/procedure_236510881/proc_par/step_174669634/step_par/download_section/download-1/file.sftmp)
>* [Getting Started with AEM Sites Chapter 6 - Creating a new AEM Component](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part6)
>* [Getting Started with AEM Sites Chapter 7 - Teaser and Carousel Components](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part7)
>* [Getting Started with AEM Sites Chapter 8 - Unit Testing](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part8)
>* [Extending Page Properties in AEM Sites](/content/help/en/experience-manager/kt/sites/using/page-properties-technical-video-develop)
>* [Extending Page Properties in AEM Sites](/content/help/en/experience-manager/kt/sites/using/page-properties-technical-video-develop/6-3-page-properties-technical-video-develop)
>* [Understanding Responsive Layout with AEM Sites](/content/help/en/experience-manager/kt/sites/using/responsive-layout-feature-video-understand)
>* [Using the Simple project with AEM](/content/help/en/experience-manager/kt/sites/using/simple-code-use)
>* [Using the Simple Plus PJAX project with AEM](/content/help/en/experience-manager/kt/sites/using/simple-code-use/simple-plus-pjax-code-use)
>* [Using the Simple Plus Bootstrap 3 project with AEM](/content/help/en/experience-manager/kt/sites/using/simple-code-use/simple-plus-bootstrap-3-code-use)
>* [Using Content Fragments and Content Services in AEM](/content/help/en/experience-manager/kt/sites/using/structured-fragments-content-services-feature-video-use)
>* [Set up Content Fragments and Content Services in AEM](/content/help/en/experience-manager/kt/sites/using/structured-content-fragments-content-services-article-setup)
>* [Using AEM Experience Fragments with Adobe Target](/content/help/en/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use)
>* [Getting Started with AEM Content Services](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use)
>* [Getting Started with AEM Content Services - Part 1 - AEM Content Services Set up](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part1)
>* [Getting Started with AEM Content Services - Part 2 - Defining FAQ Content Fragment Models](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part2)
>* [Getting Started with AEM Content Services - Part 3 - Authoring FAQ Content Fragments](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part3)
>* [Getting Started with AEM Content Services - Part 4 - Defining Content Services Templates](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part4)
>* [Getting Started with AEM Content Services - Part 5 - Authoring Content Services Pages](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part5)
>* [Getting Started with AEM Content Services - Part 6 - Exposing the Content on AEM Publish](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part6)
>* [Getting Started with AEM Content Services - Part 7 - Consuming AEM Content Services from a 3rd Party App](/content/help/en/experience-manager/kt/sites/using/content-services-tutorial-use/part7)
>* [Using the Style System with AEM Sites](/content/help/en/experience-manager/kt/sites/using/style-system-feature-video-use)
>* [Using the Style System with AEM 6.3 Sites](/content/help/en/experience-manager/kt/sites/using/style-system-feature-video-use/aem-63)
>* [Using Building Blocks with AEM Experience Fragments](/content/help/en/experience-manager/kt/sites/using/building-blocks-experience-fragment-feature-video-use)
>* [Translation Enhancements in AEM](/content/help/en/experience-manager/kt/sites/using/translation-enhancements-feature-video-use)
>* [Understanding how to code for the AEM Style System](/content/help/en/experience-manager/kt/sites/using/style-system-technical-video-understand)
>* [Understanding Content Fragments and Content Services in AEM](/content/help/en/experience-manager/kt/sites/using/content-fragments-content-services-feature-video-understand)
>* [Getting Started with Core Components and the AEM Style System](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop)
>* [Getting Started with Core Components and the AEM Style System - Part 1 - AEM Core Components](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part1)
>* [Getting Started with Core Components and the AEM Style System - Part 0 - Set up](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part0)
>* [Getting Started with Core Components and the AEM Style System - Part 2 - Preparing the Page Template](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part2)
>* [Getting Started with Core Components and the AEM Style System - Part 3 - Content-first Authoring](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part3)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part3/jcr:content/main-pars/procedure/proc_par/step_1319053040/step_par/image_365829580/file.sftmp)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part3/jcr:content/main-pars/procedure/proc_par/step_431396762/step_par/image/file.sftmp)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part3/jcr:content/main-pars/procedure/proc_par/step_126729473/step_par/image/file.sftmp)
>* [Getting Started with Core Components and the AEM Style System - Part 4 - Organizing Client Libraries, CSS & JavaScript](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part4)
>* [Getting Started with Core Components and the AEM Style System - Part 5 - Applying the Basic Dopetrope Style](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part5)
>* [Getting Started with Core Components and the AEM Style System - Part 6 - Applying the Teaser Component CSS-based Styles](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part6)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part6/jcr:content/main-pars/procedure/proc_par/step_0/step_par/image/file.sftmp)
>* [N/A](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part6/jcr:content/main-pars/procedure/proc_par/step_4/step_par/image/file.sftmp)
>* [Getting Started with Core Components and the AEM Style System - Part 7 - Applying the Teaser Component JavaScript-based Styles](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part7)
>* [Getting Started with Core Components and the AEM Style System - Part 8 - Exploration of How Other Components Were Styled](/content/help/en/experience-manager/kt/sites/using/style-system-core-components-tutorial-develop/part8)
>* [Using the SPA Editor framework with AEM Sites](/content/help/en/experience-manager/kt/sites/using/spa-editor-framework-feature-video-use)
>* [Overview of AEM Sites](/content/help/en/experience-manager/kt/sites/using/overview-feature-video-understand)
>* [Set Up Experience Fragments and Adobe Target Integration in AEM](/content/help/en/experience-manager/kt/sites/using/experience-fragment-target-feature-video-setup)
>* [Using AEM Experience Fragment Offers within Adobe Target](/content/help/en/experience-manager/kt/sites/using/experience-fragment-target-offer-feature-video-use)
>* [Overview of Single Page Applications (SPA)](/content/help/en/experience-manager/kt/sites/using/spa-overview-feature-video)
>* [Getting Started with the AEM SPA Editor - Hello World Tutorial](/content/help/en/experience-manager/kt/sites/using/spa-editor-helloworld-tutorial-use)
>* [Understanding SPA components in AEM SPA Editor](/content/help/en/experience-manager/kt/sites/using/spa-editor-components-technical-video-understand)
>* [Understanding style organization with the AEM Style System](/content/help/en/experience-manager/kt/sites/using/style-organization-style-system-understand-article)
>* [Set up ContextHub with AEM Sites](/content/help/en/experience-manager/kt/sites/using/context-hub-technical-video-setup)
>* [Getting Started with the AEM SPA Editor - WKND Events Tutorial](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop)
>* [Getting Started with React and AEM SPA Editor](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react)
>* [do not publish](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-0-project-setup)
>* [Template DO NOT PUBLISH](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/template)
>* [Getting Started with React and AEM SPA Editor - Chapter 1](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-1)
>* [Getting Started with React and AEM SPA Editor - Chapter 2](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-2)
>* [Getting Started with React and AEM SPA Editor - Chapter 0](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-0)
>* [Getting Started with React and AEM SPA Editor - Chapter 3](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-3)
>* [Getting Started with Angular and AEM SPA Editor](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 0](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-0)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 1](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-1)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 2](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-2)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 3](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-3)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 4](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-4)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 5](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-5)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 6](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-6)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 7](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-7)
>* [Getting Started with Angular and AEM SPA Editor - Chapter 8](/content/help/en/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/angular/chapter-8)
>* [Index](/content/help/en/experience-manager/kt/sites/index)
>* [AEM 6.3 Sites Tutorials and Videos](/content/help/en/experience-manager/kt/sites/index/aem-6-3-sites)
>* [Simple for AEM](/content/help/en/experience-manager/kt/sites/index/simple)
>* [AEM 6.4 Sites Tutorials and Videos](/content/help/en/experience-manager/kt/sites/index/aem-6-4-sites)
>* [AEM 6.5 Sites Tutorials and Videos](/content/help/en/experience-manager/kt/sites/index/aem-6-5-sites)
>* [Beta](/content/help/en/experience-manager/kt/sites/beta)
>* [Architecture of the AEM Style System](/content/help/en/experience-manager/kt/sites/beta/style-system-architecture-technical-video-understand)
>* [How to Customize Component Element Names in the AEM Style System](/content/help/en/experience-manager/kt/sites/beta/style-system-overview-feature-video-understand)
>* [Overview of Style System Authoring Workflow](/content/help/en/experience-manager/kt/sites/beta/style-system-workflow-feature-video-understand)
>* [Overview of the AEM Style System](/content/help/en/experience-manager/kt/sites/beta/style-system-customize-element-names-feature-video-understand)
>* [Using Core Components with the AEM Style System](/content/help/en/experience-manager/kt/sites/beta/style-system-component-requirements-technical-video-understand)
>* [Overview of Content Fragments and Content Services](/content/help/en/experience-manager/kt/sites/beta/content-fragments-content-services-overview-feature-video-understand)
>* [Summary of Content Fragments and Content Services Enhancements](/content/help/en/experience-manager/kt/sites/beta/content-fragments-content-services-enhancements-feature-video-understand)
>* [Authoring Experience Using Structured Content Fragments](/content/help/en/experience-manager/kt/sites/beta/content-fragments-authoring-feature-video-use)
>* [Creating Content Fragment Models](/content/help/en/experience-manager/kt/sites/beta/content-fragments-create-models-technical-video-use)
>* [Extracting Data Using Content Services](/content/help/en/experience-manager/kt/sites/beta/content-fragments-content-services-output-technical-video-use)
>* [Understand Content Services Data Output](/content/help/en/experience-manager/kt/sites/beta/content-fragments-output-scenarios-technical-video-understand)
>* [Content Fragment Enhancements](/content/help/en/experience-manager/kt/sites/beta/content-fragment-enhancements-feature-video-understand)
>* [Experience Fragment Enhancements](/content/help/en/experience-manager/kt/sites/beta/experience-fragments-enhancements-feature-video-understand)
>* [Translation Enhancements](/content/help/en/experience-manager/kt/sites/beta/translation-enhancements-feature-video-understand)
>* [Templates (Do Not Publish)](/content/help/en/experience-manager/kt/templates--do-not-publish-)
>* [Video Page](/content/help/en/experience-manager/kt/templates--do-not-publish-/video-page)
>* [Diagram Page](/content/help/en/experience-manager/kt/templates--do-not-publish-/diagram-page)
>* [Code Page](/content/help/en/experience-manager/kt/templates--do-not-publish-/code-page)
>* [Aggregate Page](/content/help/en/experience-manager/kt/templates--do-not-publish-/aggregrate-page)
>* [Helpx AEM Tech Marketing Standards](/content/help/en/experience-manager/kt/templates--do-not-publish-/standards)
>* [POC CCL Tutorial Page for AEM Technical Marketing](/content/help/en/experience-manager/kt/templates--do-not-publish-/poc-ccl-tutorial-page)
>* [Tutorial Page](/content/help/en/experience-manager/kt/templates--do-not-publish-/tutorial-page)
>* [Internal](/content/help/en/experience-manager/kt/livefyre/kb-internal)
>* [Using](/content/help/en/experience-manager/kt/livefyre/using)
>* [KB](/content/help/en/experience-manager/kt/livefyre/kb)
>* [Index](/content/help/en/experience-manager/kt/livefyre/index)
>* [Livefyre](/content/help/en/experience-manager/kt/livefyre)
>* [Internal](/content/help/en/experience-manager/kt/integration/kb-internal)
>* [Using](/content/help/en/experience-manager/kt/integration/using)
>* [Launch by Adobe Reference Architectures](/content/help/en/experience-manager/kt/integration/using/launch-reference-architecture-guides)
>* [Integrate Launch by Adobe with AEM Sites](/content/help/en/experience-manager/kt/integration/using/adobe-launch-integration-tutorial-understand)
>* [Understanding AEM Integration with DTM, Analytics and Target](/content/help/en/experience-manager/kt/integration/using/aem-dtm-integration-tutorial-understand)
>* [Understanding AEM Integration with Launch By Adobe, Analytics and Target](/content/help/en/experience-manager/kt/integration/using/aem-launch-integration-tutorial-understand)
>* [Using Launch by Adobe to Implement Analytics, Target, and Audience Manager in Single Page Applications (SPA)](/content/help/en/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement)
>* [Understanding Single Page Application Content Insights using Launch by Adobe](/content/help/en/experience-manager/kt/integration/using/aem-analytics-spa-tutorial-understand)
>* [KB](/content/help/en/experience-manager/kt/integration/kb)
>* [Index](/content/help/en/experience-manager/kt/integration/index)
>* [Integration](/content/help/en/experience-manager/kt/integration)
>* [Index](/content/help/en/experience-manager/kt/index)
>* [AEM 6.3 Tutorials and Videos](/content/help/en/experience-manager/kt/index/aem-6-3-videos)
>* [AEM 6.4 Tutorials and Videos](/content/help/en/experience-manager/kt/index/aem-6-4-videos)
>* [A collection of tutorials focused on using, developing and integrating AEM with other Adobe products.](/content/help/en/experience-manager/kt/index/aem-tutorials)
>* [AEM 6.5 Tutorials and Videos](/content/help/en/experience-manager/kt/index/aem-6-5-videos)
>* [eSeminars](/content/help/en/experience-manager/kt/eseminars)
>* [Adobe Experience Manager: Desktop App](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-desktop-app)
>* [Adobe Analytics: Data Feed Management Tips & Tricks](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-data-feeds-tips-and-tricks)
>* [Adobe Customer Care Office Hours](/content/help/en/experience-manager/kt/eseminars/ccoo-index)
>* [Adobe Customer Care Office Hours](/content/help/en/experience-manager/kt/eseminars/ccoo-index/ccoo-index-AEM)
>* [Adobe Customer Care Office Hours](/content/help/en/experience-manager/kt/eseminars/ccoo-index/ccoo-index-Camapign)
>* [Adobe Campaign: Success Mantra for Email Delivery in Adobe Campaign v6](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-email-delivery-campaignv6)
>* [Adobe Experience Manager: Desktop App Advanced Tips](/content/help/en/experience-manager/kt/eseminars/cc00-aem-desktop-app-advanced)
>* [Adobe Campaign: Success Mantra for Email Delivery in Adobe Campaign v6](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-registernow)
>* [AEM GEMS : Sites and Experience Fragments](/content/help/en/experience-manager/kt/eseminars/gem-template-page)
>* [Adobe Campaign: Success Mantra for Email Delivery in Adobe Campaign v6](/content/help/en/experience-manager/kt/eseminars/coco-template-registration)
>* [Adobe Campaign: Message Center - Real Time Messaging](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-june-register)
>* [Adobe Experience Manager: Indexing - Best Practices and Troubleshooting](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-june-register)
>* [Adobe Analytics: Visitor ID Service Overview Registration](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-june-register)
>* [Adobe Analytics: Marketing Cloud ID Recording](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-marketing-cloud-id)
>* [Adobe Campaign: Messaging Center Recording](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-message-center-recording)
>* [Adobe Experience Manager: Indexing](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-indexing-recording)
>* [Adobe Analytics: Marketing Cloud Administration Overview Registration](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-july-register)
>* [Adobe Experience Manager: Key Features of AEM 6.3 and Upgrade Best Practices Registration](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-july-register)
>* [Adobe Campaign: Making the best of Campaign Solution Registration](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-july-register)
>* [Adobe Analytics: Marketing Cloud Administration Overview](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-july-recording)
>* [Adobe Experience Manager: Key Features of AEM 6.3 and Upgrade Best Practices](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-july-recording)
>* [Adobe Campaign: Making the best of Campaign Solution](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-july-recording)
>* [GEMS](/content/help/en/experience-manager/kt/eseminars/gems)
>* [AEM SPA Editor](/content/help/en/experience-manager/kt/eseminars/gems/jcr:content/aem-spa-editor)
>* [AEM Indexing and JCR Query](/content/help/en/experience-manager/kt/eseminars/gems/aem-indexing-jcr-query)
>* [Troubleshooting AEM Replication](/content/help/en/experience-manager/kt/eseminars/gems/aem-troubleshooting-aem-replication)
>* [AEM GEMS](/content/help/en/experience-manager/kt/eseminars/gems/aem-index)
>* [N/A](/content/help/en/experience-manager/kt/eseminars/gems/aem-index/jcr:content/hero/file)
>* [Granite GEMS](/content/help/en/experience-manager/kt/eseminars/gems/granite-index)
>* [Building Health Checks for AEM](/content/help/en/experience-manager/kt/eseminars/gems/aem-building-health-checks-for-aem)
>* [Toughday2 - A new and improved stress testing and benchmarking tool](/content/help/en/experience-manager/kt/eseminars/gems/aem-toughday2-stress-testing-benchmarking-tool)
>* [AEM Sustenance - Best Practices for deploying AEM Maintenance Releases](/content/help/en/experience-manager/kt/eseminars/gems/aem-sustenance-best-practices-deploying-maintenance-releases)
>* [Search forms made easy with the AEM querybuilder](/content/help/en/experience-manager/kt/eseminars/gems/aem-search-forms-using-querybuilder)
>* [Into the tar pit: a TarMK deep dive](/content/help/en/experience-manager/kt/eseminars/gems/aem-tarmk-deepdive)
>* [Tools to use for testing Adobe Experience Manager applications](/content/help/en/experience-manager/kt/eseminars/gems/aem-testing-tools-for-aem-apps)
>* [Introduction to AEM Screens](/content/help/en/experience-manager/kt/eseminars/gems/aem-introduction-to-aem-screens)
>* [Configuring the DAM for Enterprise](/content/help/en/experience-manager/kt/eseminars/gems/aem-configuring-dam-for-enterprise)
>* [Managing your content with the template editor of Adobe Experience Manager](/content/help/en/experience-manager/kt/eseminars/gems/aem-managing-content-with-template-editor)
>* [Setup and Configure AEM Dynamic Media](/content/help/en/experience-manager/kt/eseminars/gems/aem-setup-and-configure-aem-dynamic-media)
>* [Utilizing SAML in Adobe Experience Manager deployments](/content/help/en/experience-manager/kt/eseminars/gems/aem-utilizing-saml-in-aem-deployments)
>* [AEM Web Performance](/content/help/en/experience-manager/kt/eseminars/gems/aem-web-performance)
>* [Technical Sneak Peek](/content/help/en/experience-manager/kt/eseminars/gems/aem-technical-sneak-peek)
>* [Running AEM on MongoDB](/content/help/en/experience-manager/kt/eseminars/gems/aem-running-aem-on-mongodb)
>* [Oak Lucene Indexes](/content/help/en/experience-manager/kt/eseminars/gems/aem-oak-lucene-indexes)
>* [Track quality metrics of your Javascript project](/content/help/en/experience-manager/kt/eseminars/gems/aem-track-quality-metrics-of-your-javascript-project)
>* [Deep dive into AEM upgrade process](/content/help/en/experience-manager/kt/eseminars/gems/aem-deep-dive-into-aem-upgrade-process)
>* [Customizing Dialog Fields in Touch UI](/content/help/en/experience-manager/kt/eseminars/gems/aem-customizing-dialog-fields-in-touch-ui)
>* [AEM 6.1 Translation Integration & Best Practices](/content/help/en/experience-manager/kt/eseminars/gems/aem-6_1-translation-integration-and-best-practices)
>* [IBM WebSphere Commerce Integration for AEM](/content/help/en/experience-manager/kt/eseminars/gems/aem-ibm-websphere-commerce-integration-for-aem)
>* [Inside ACS AEM Commons & Tools](/content/help/en/experience-manager/kt/eseminars/gems/aem-inside-acs-aem-commons-and-tools)
>* [Oak's External Login Module - Authenticating with LDAP and Beyond](/content/help/en/experience-manager/kt/eseminars/gems/aem-oak-external-login-module-authenticating-with-ldap-and-beyond)
>* [Creating online Communities with AEM 6.1](/content/help/en/experience-manager/kt/eseminars/gems/aem-creating-online-communities-with-aem-6_1)
>* [Tips and tricks for AEM Sites Touch UI](/content/help/en/experience-manager/kt/eseminars/gems/aem-tips-and-tricks-for-aem-sites-touch-ui)
>* [Sonar - A key element to improve product quality](/content/help/en/experience-manager/kt/eseminars/gems/aem-sonar-a-key-element-to-improve-product-quality)
>* [AEM Forms Feature Pack 1 introduction and technical samples](/content/help/en/experience-manager/kt/eseminars/gems/aem-forms-feature-pack-1-introduction-and-technical-samples)
>* [Dispatcher Caching - New Features and Optimizations](/content/help/en/experience-manager/kt/eseminars/gems/aem-dispatcher-caching-new-features-and-optimizations)
>* [AEM Tech Sneak Peek](/content/help/en/experience-manager/kt/eseminars/gems/aem-tech-sneak-peek)
>* [Machine Translation in AEM](/content/help/en/experience-manager/kt/eseminars/gems/aem-machine-translation-in-aem)
>* [AEM 6 Oak: MongoMK and Queries](/content/help/en/experience-manager/kt/eseminars/gems/aem-oak-mongomk-and-queries)
>* [How to deploy Adobe Analytics on a local AEM instance by using the Dynamic Tag Management cloud service](/content/help/en/experience-manager/kt/eseminars/gems/aem-adobe-analytics-dynamic-tag-management)
>* [AEM Developer Tools for Eclipse](/content/help/en/experience-manager/kt/eseminars/gems/aem-developer-tools-for-eclipse)
>* [Delivering Managed Content to your Native Apps](/content/help/en/experience-manager/kt/eseminars/gems/aem-delivering-managed-content-to-your-native-apps)
>* [OAuth Server functionality in AEM - Embrace Federation and unleash your REST APIs!](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem)
>* [Social Component Framework in AEM 6](/content/help/en/experience-manager/kt/eseminars/gems/aem-social-component-framework-in-aem-6)
>* [AEM 6.0 Developer Mode](/content/help/en/experience-manager/kt/eseminars/gems/aem-developer-mode)
>* [Efficiently Build Reusable Components](/content/help/en/experience-manager/kt/eseminars/gems/aem-efficiently-build-reusable-components)
>* [Introduction to HTL](/content/help/en/experience-manager/kt/eseminars/gems/aem-introduction-to-htl)
>* [Technical Deep Dive into the AEM 6 Platform](/content/help/en/experience-manager/kt/eseminars/gems/aem-technical-deep-dive-into-the-aem-6-platform)
>* [Technical Overview of the AEM 6 Platform](/content/help/en/experience-manager/kt/eseminars/gems/aem-technical-overview-of-the-aem-6-platform)
>* [User Interface Customization for AEM 6](/content/help/en/experience-manager/kt/eseminars/gems/aem-user-interface-customization-for-aem6)
>* [How to get the most out of your DAM Feature Pack](/content/help/en/experience-manager/kt/eseminars/gems/aem-dam-feature-pack)
>* [AEM Dynamic Media 6.3 Architecture](/content/help/en/experience-manager/kt/eseminars/gems/aem-dynamic-media-architecture)
>* [SharePoint Connector - Setup and Configuration](/content/help/en/experience-manager/kt/eseminars/gems/aem-sharepoint-connector-setup-and-configuration)
>* [Metadata Management in AEM DAM](/content/help/en/experience-manager/kt/eseminars/gems/aem-metadata-management-in-aem-dam)
>* [Streamlining multilingual content process](/content/help/en/experience-manager/kt/eseminars/gems/aem-streamlining-multilingual-content-process)
>* [CQ/AEM 5.6 Troubleshooting](/content/help/en/experience-manager/kt/eseminars/gems/aem-cq-aem-5-6-troubleshooting)
>* [Mobile-First Development with CQ Made Easy](/content/help/en/experience-manager/kt/eseminars/gems/aem-mobile-first-development-with-cq-made-easy)
>* [MSM and Translation: Best Practices](/content/help/en/experience-manager/kt/eseminars/gems/aem-msm-and-translation-best-practices)
>* [Introduction of Job Handling and Offloading in AEM 5.6.1.](/content/help/en/experience-manager/kt/eseminars/gems/aem-job-handling-and-offloading)
>* [Launches: concurrent preparation of multiple versions of a website (AEM 5.6)](/content/help/en/experience-manager/kt/eseminars/gems/aem-launches)
>* [AEM 5.6 upgrade mechanisms](/content/help/en/experience-manager/kt/eseminars/gems/aem-upgrade-mechanisms)
>* [hybris/AEM 5.6 eCommerce framework integration](/content/help/en/experience-manager/kt/eseminars/gems/aem-hybris-ecommerce-framework-integration)
>* [Architecture of the AEM 5.6 Platform](/content/help/en/experience-manager/kt/eseminars/gems/aem-architecture-of-the-aem-5-6-platform)
>* [AEM 5.6 Media Publisher Deep Dive](/content/help/en/experience-manager/kt/eseminars/gems/aem-media-publisher-deep-dive)
>* [eCommerce Integration Framework](/content/help/en/experience-manager/kt/eseminars/gems/aem-ecommerce-integration-framework)
>* [AEM Upgrade to major version - Backwards compatibility continued: Testing for BC compliance; Pattern detection](/content/help/en/experience-manager/kt/eseminars/gems/granite-upgrade-major-version-pattern-detector-testing)
>* [Developing OSGi Bundles and Services for AEM](/content/help/en/experience-manager/kt/eseminars/gems/aem-developing-osgi-bundles-services-for-aem)
>* [AEM Upgrade to major version - Backwards compatibility](/content/help/en/experience-manager/kt/eseminars/gems/granite-upgrade-to-major-version-backwards-compatibility)
>* [Assuming the worst - AEM Customer orientation and long-term CritSit reduction](/content/help/en/experience-manager/kt/eseminars/gems/granite-assuming-the-worst-aem-customer-orientation-and-long-term-critsit-reduction)
>* [Evergreen Sprouts - Make it green from the start](/content/help/en/experience-manager/kt/eseminars/gems/granite-evergreen-sprouts-make-it-green-from-the-start)
>* [Content Package Validation Improvements](/content/help/en/experience-manager/kt/eseminars/gems/granite-content-package-validation-improvements)
>* [AEM Cumulative Fix Pack process](/content/help/en/experience-manager/kt/eseminars/gems/granite-cumulative-fix-pack-process)
>* [HTTP API Framework](/content/help/en/experience-manager/kt/eseminars/gems/granite-http-api-framework)
>* [Project evergreen and how to un-ring a bell - a required process change coming with AEM 6.3 M3 (load 9)](/content/help/en/experience-manager/kt/eseminars/gems/granite-project-evergreen)
>* [AEM Forms and Mobile Apps](/content/help/en/experience-manager/kt/eseminars/gems/granite-aem-forms-and-mobile-apps)
>* [AEM 2016/2017 program and operation](/content/help/en/experience-manager/kt/eseminars/gems/granite-program-and-operation)
>* [Snapshotting and Restoring AEM using Docker and CRIU](/content/help/en/experience-manager/kt/eseminars/gems/granite-snapshotting-and-restoring-aem)
>* [AEM Integrations - a solid foundation goes a long way](/content/help/en/experience-manager/kt/eseminars/gems/aem-integrations)
>* [AEM 6.3 Ready for the World - Translation Integration & Best Practices](/content/help/en/experience-manager/kt/eseminars/gems/aem-translation-integration)
>* [Managing AEM DataStore](/content/help/en/experience-manager/kt/eseminars/gems/aem-managing-aem-datastore)
>* [AEM Fluid Experiences for headless usecases](/content/help/en/experience-manager/kt/eseminars/gems/aem-headless-usecases)
>* [AEM 6.3 Ready for the World - Translation Integration & Best Practices](/content/help/en/experience-manager/kt/eseminars/gems/aem-translation-best-practices)
>* [Major Brand Portal Release and new reference implementation for Asset Share](/content/help/en/experience-manager/kt/eseminars/gems/aem-brand-portal)
>* [N/A](/content/help/en/experience-manager/kt/eseminars/gems/aem-brand-portal/jcr:content/main-pars/download_section/download-1/file.sftmp)
>* [Dispatcher - New features and best practices](/content/help/en/experience-manager/kt/eseminars/gems/aem-dispatcher)
>* [Troubleshooting Sling Content Distribution](/content/help/en/experience-manager/kt/eseminars/gems/aem-troubleshooting-sling)
>* [The Digital Asset Explosion & AEM Assets](/content/help/en/experience-manager/kt/eseminars/gems/aem-asset-explosion)
>* [Experiments in AEM Author Scalability](/content/help/en/experience-manager/kt/eseminars/gems/aem-author-scalability)
>* [The Digital Asset Explosion & AEM Assets](/content/help/en/experience-manager/kt/eseminars/gems/aem-digital-asset-explosion)
>* [Experiments in AEM Author Scalability](/content/help/en/experience-manager/kt/eseminars/gems/aem-author-scalability1)
>* [Deep Dive into Adobe Experience Manager 6.4](/content/help/en/experience-manager/kt/eseminars/gems/Deep-Dive-into-Adobe-Experience-Manager-6-4)
>* [Deep Dive into Adobe Experience Manager 6.4](/content/help/en/experience-manager/kt/eseminars/gems/aem-deep-dive-6-4)
>* [The Digital Asset Explosion & AEM Assets](/content/help/en/experience-manager/kt/eseminars/gems/Deep-Dive-into-Adobe-Experience-Manager-6-41)
>* [AEM Managed Services IMS Integration: Architecture and Operation](/content/help/en/experience-manager/kt/eseminars/gems/granite-ams-ms-ims-integration-1)
>* [Deep Dive into Adobe Experience Manager 6.4](/content/help/en/experience-manager/kt/eseminars/gems/aem-6_4_technical_sneak_peek)
>* [Mapping AEM - automatic analysis of AEM and its usage - a possible help in your daily decision-making](/content/help/en/experience-manager/kt/eseminars/gems/granite-mapping-aem)
>* [Cognifide's Zen Garden: What? Why? When?](/content/help/en/experience-manager/kt/eseminars/gems/granite-cognifide-zen-garden)
>* [New Release Model for AEM 2018](/content/help/en/experience-manager/kt/eseminars/gems/granite-new-release-model)
>* [How to improve your patent submission](/content/help/en/experience-manager/kt/eseminars/gems/granite-patent-submission)
>* [Machine Learning in AEM: Enhanced Smart Tags, Smart Layout and more](/content/help/en/experience-manager/kt/eseminars/gems/Machine-Learning-in-AEM-Enhanced-Smart-Tags-Smart-Layout-and-more)
>* [Machine Learning in AEM: Enhanced Smart Tags, Smart Layout and more](/content/help/en/experience-manager/kt/eseminars/gems/aem-machine-learning)
>* [AEM Managed Services IMS Integration - End to End Demo](/content/help/en/experience-manager/kt/eseminars/gems/granite-ims-demo)
>* [Real-time and lightweight: build event-driven integrations with AEM using I/O Events](/content/help/en/experience-manager/kt/eseminars/gems/event-driven-integrations-with-aem-using-IO-Events)
>* [Principles of the new AEM Engineering Operations Framework](/content/help/en/experience-manager/kt/eseminars/gems/granite-aem-engineering-framework)
>* [Configuring AEM deployments for Adobe Asset Link (fka Project Europa)](/content/help/en/experience-manager/kt/eseminars/gems/granite-asset-link)
>* [Real-time and lightweight: build event-driven integrations with AEM using I/O Events](/content/help/en/experience-manager/kt/eseminars/gems/aem-adobe-io)
>* [Solr as an Oak index for AEM](/content/help/en/experience-manager/kt/eseminars/gems/Solr-as-an-Oak-index-for-AEM)
>* [Adobe I/O Events - Analytics Triggers](/content/help/en/experience-manager/kt/eseminars/gems/aem-analytics-triggers)
>* [Solr as an Oak index for AEM](/content/help/en/experience-manager/kt/eseminars/gems/Solr-as-an-Oak-index-for-AEM1)
>* [Machine Learning in AEM: Enhanced Smart Tags, Smart Layout and more](/content/help/en/experience-manager/kt/eseminars/gems/Adobe-Cloud-Platform---The-Heart-of-Experience-Cloud)
>* [AEM Query and Index Troubleshooting](/content/help/en/experience-manager/kt/eseminars/gems/AEM-Query-and-Index-Troubleshooting2)
>* [Adobe Cloud Platform - The Heart of Experience Cloud](/content/help/en/experience-manager/kt/eseminars/gems/aem-acp)
>* [AEM Query and Index troubleshooting](/content/help/en/experience-manager/kt/eseminars/gems/AEM-Query-and-Index-Troubleshooting)
>* [AEM Query and Index Troubleshooting](/content/help/en/experience-manager/kt/eseminars/gems/A-Blank-registration-template)
>* [Best Practices for Test Automation with Selenium](/content/help/en/experience-manager/kt/eseminars/gems/granite-selenium)
>* [Maintaining Open Source While Maintaining Your Sanity](/content/help/en/experience-manager/kt/eseminars/gems/Maintaining-Open-Source-While-Maintaining-Your-Sanity)
>* [Metrics reporter in AEM](/content/help/en/experience-manager/kt/eseminars/gems/granite-metrics-reporter)
>* [Maintaining Open Source While Maintaining Your Sanity](/content/help/en/experience-manager/kt/eseminars/gems/aem-maintaining-open-source)
>* [Introduction to ContextHub in AEM 6.4](/content/help/en/experience-manager/kt/eseminars/gems/aem-intro-to-contexthub)
>* [Using OSGi R7 in AEM](/content/help/en/experience-manager/kt/eseminars/gems/Using-OSGi-R7-in-AEM)
>* [AEM SPA Editor](/content/help/en/experience-manager/kt/eseminars/gems/aem-spa-editor)
>* [AEM SPA Editor](/content/help/en/experience-manager/kt/eseminars/gems/AEM-SPA-Editor)
>* [SPA Editor SDK Deep Dive - Part 1 - React](/content/help/en/experience-manager/kt/eseminars/gems/SPA-Editor-SDK-Deep-Dive-React)
>* [SPA Editor SDK Deep Dive - Part 2 - Angular](/content/help/en/experience-manager/kt/eseminars/gems/SPA-Editor-SDK-Deep-Dive-Angular)
>* [AEM Core Components](/content/help/en/experience-manager/kt/eseminars/gems/AEM-Core-Components)
>* [AskTheExpert](/content/help/en/experience-manager/kt/eseminars/ask-the-expert)
>* [AEM Ask the AEM Community Expert](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/atace-index)
>* [AEM Dispatcher](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-develop-with-dispatcher-in-mind)
>* [AEM Assets and Dynamic Media](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-assets-and-dynamic-media)
>* [Using Lazybones and Editable template in AEM projects](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-using-lazybones-and-editable-template-in-aem-projects)
>* [Building responsive layouts using Bootstrap and Angular JS in Experience Manager](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-building-responsive-layouts-using-bootstrap-and-angular-js-in-aem)
>* [Getting the most out of digital interactions with AEM and Analytics](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-getting-the-most-out-of-digital-interactions-with-aem-and-analytics)
>* [Best Practices for using Experience Manager and Adobe Campaign](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-best-practices-for-using-experience-manager-and-adobe-campaign)
>* [Integrating Test and Target with Adobe Experience Manager for Personalization use cases](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-integrating-test-and-target-with-aem-for-personalization-use-cases)
>* [Comparative Architecture Analysis of large scale Experience Manager Installations](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-comparative-architecture-analysis-of-large-scale-experience-manager-installations)
>* [Best Practices for Experience Manager and AEM Assets](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-best-practices-for-experience-manager-and-aem-assets)
>* [Working with Experience Manager and eCommerce](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-working-with-experience-manager-and-ecommerce)
>* [Preparing for Adobe Experience Manager Developer Exam](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-preparing-for-adobe-experience-manager-developer-exam)
>* [AEM Forms dive into Document Services](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-forms-dive-into-document-services)
>* [Deep Dive into AEM Communities](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-deep-dive-into-aem-communities)
>* [Working with AEM Forms](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-working-with-aem-forms)
>* [Deep Dive into developing AEM components using HTL](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-deep-dive-into-developing-aem-components-using-htl)
>* [Developing AEM Sling Components using Brackets](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-developing-aem-sling-components-using-brackets)
>* [Deep Dive into AEM and translations](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-deep-dive-into-aem-and-translations)
>* [AEM Apps Deep Dive](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-apps-deep-dive)
>* [AEM & integration with other Digital Marketing products](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-integration-with-other-digital-marketing-products)
>* [Personalization & segmentation with AEM & Adobe Campaign](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-personalization-and-segmentation-with-aem-and-adobe-campaign)
>* [Adobe Experience Manager Technical Documentation](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-technical-documentation)
>* [Adobe Experience Manager & Sling](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-adobe-experience-manager-and-sling)
>* [AEM & Dispatcher](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-dispatcher)
>* [Advanced AEM component development](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-advanced-aem-component-development)
>* [Touch UI components](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-touch-ui-components)
>* [AEM Workflows](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-workflows)
>* [Building login-based sites in AEM](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-building-login-based-sites-in-aem)
>* [Replication](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-replication)
>* [Getting Started with AEM Apps](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-getting-started-with-aem-apps)
>* [Testing AEM Applications with ease](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-testing-aem-applications-with-ease)
>* [Developing custom services to customize AEM](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-developing-custom-services-to-customize-aem)
>* [Working with Experience Manager Core Components](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-working-with-experience-manager-core-components1)
>* [Creating custom components using HTL](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-custom-components-HTL)
>* [Working with Experience Manager Core Components](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-contexthub)
>* [AEM Component Development Strategies](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-component-development-strategies)
>* [Understanding AEM Communities](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-understanding-communities)
>* [AEM Sites - Multi-Site Management](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-multi-site-management)
>* [AEM Component Development Strategies](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-multi-site-management1)
>* [Working with AEM Workflows and Workflow API's](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-workflows-apis)
>* [Working with AEM Workflows and Workflow API's](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-workflows1)
>* [AEM Content Services: What, Why, and How?](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-content-services)
>* [Easy Access to Critical Information: Content Reports in Adobe Experience Manager](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-content-reports)
>* [Adobe Experience Manager and Audience Manager](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-audience-manager1)
>* [Adobe Experience Manager and Creative Cloud](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-creative-cloud)
>* [Developing AEM component using Vue.js](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-components-vue)
>* [Explore AEM Assets and Tags by their APIs](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-assets-tags)
>* [Adobe Experience Manager and Adobe Sensei](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-sensei)
>* [Developing AEM component using Vue.js](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-vue)
>* [Enterprise Search Solution for AEM using Apache Solr](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-apache-solr)
>* [Creating a site structure to support your global business](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-site-structure)
>* [Working with Single Page applications for Experience Manager](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-single-page-application)
>* [Enterprise Search Solution for AEM using Apache Solr](/content/help/en/experience-manager/kt/eseminars/ask-the-expert/aem-single-page-application1)
>* [Adobe Analytics: First Party Cookies & Using Adobe Managed Certificates](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-Aug-register)
>* [Adobe Campaign: Tips and Tricks to a healthy Campaign Server and Delivery Monitoring](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-Aug-register)
>* [Adobe Experience Manager: AEM 6.x Maintenance Tasks](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-Aug-register)
>* [Adobe Analytics: Marketing Channels - Common Pitfalls](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-sept-register)
>* [Adobe Experience Manager: Integrating SAML & LDAP with AEM 6.x](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-sept-register)
>* [Adobe Analytics: First Party Cookies & Using Adobe Managed Certificates](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-aug-recording)
>* [Adobe Campaign: Tips and Tricks to a healthy Campaign Server and Delivery Monitoring](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-Aug-recording)
>* [Adobe Experience Manager: AEM 6.x Maintenance Tasks](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-Aug-recording)
>* [Adobe Experience Manager: Integrating SAML and LDAP with AEM 6.x](/content/help/en/experience-manager/kt/eseminars/ccoo-AEM-Sept-recording)
>* [Adobe Analytics: Marketing Channels - Common Pitfalls](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-sept-recording)
>* [Adobe Analytics: Classifications - Get the most out of your Analytics Data](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-oct-register)
>* [Adobe Experience Manager: AEM Assets - Implementation Guidelines & Best Practices](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-oct-register)
>* [Adobe Campaign: Delivery Architecture and Performance](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-oct-register)
>* [Adobe Campaign: Getting the most from your Campaign solution](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign1-sept-recording)
>* [Adobe Analytics: Classifications - Get the most out of your Analytics Data](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-oct-recording)
>* [Adobe Experience Manager: AEM Assets - Implementation Guidelines & Best Practices](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-oct-recording)
>* [Adobe Campaign: Delivery Architecture and Performance](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-oct-recording)
>* [Adobe Analytics: Data Availability & Latency](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-Nov-register)
>* [Adobe Campaign Standard: Technical Workflows, Branding , Notification, Monitoring and Reports](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-Nov-register)
>* [Adobe Experience Manager: AEM 6.x Performance Tuning and Best Practices](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-Nov-register)
>* [Adobe Target: Visual Experience Composer](/content/help/en/experience-manager/kt/eseminars/ccoo-target-Nov-register)
>* [Adobe Primetime: TVE Dashboard User Interface](/content/help/en/experience-manager/kt/eseminars/ccoo-primetime-Nov-register)
>* [Adobe Analytics: Data Processing & Latency](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-nov-recording)
>* [Adobe Campaign Standard: Technical Workflows, Branding , Notification, Monitoring and Reports](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-Nov-recording)
>* [Adobe Experience Manager: AEM 6.x Performance Tuning and Best Practices](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-nov-recording)
>* [Adobe Primetime: TVE Dashboard User Interface](/content/help/en/experience-manager/kt/eseminars/ccoo-primetime-nov-recording)
>* [Adobe Target: Visual Experience Composer](/content/help/en/experience-manager/kt/eseminars/ccoo-target-nov-recording)
>* [Adobe Experience Manager: Adaptive Forms - Authoring and Processing](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-jan-register)
>* [Adobe Analytics: Using Raw Data](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-jan-register)
>* [Adobe Target: Analytics/Target-A4T](/content/help/en/experience-manager/kt/eseminars/ccoo-target-jan18-register)
>* [Adobe Campaign: Mobile delivery channels in Campaign](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-jan18-register)
>* [Experience Insider](/content/help/en/experience-manager/kt/eseminars/experience-insider)
>* [Experience Insider](/content/help/en/experience-manager/kt/eseminars/experience-insider/experience-insider-index)
>* [N/A](/content/help/en/experience-manager/kt/eseminars/experience-insider/experience-insider-index/jcr:content/hero/file)
>* [Experience Insider News](/content/help/en/experience-manager/kt/eseminars/experience-insider/experience-insider-news)
>* [What’s New in AEM6.4](/content/help/en/experience-manager/kt/eseminars/experience-insider/whats-new-aem-6_4)
>* [Experience Insider](/content/help/en/experience-manager/kt/eseminars/experience-insider/experience-insider-oss-index)
>* [N/A](/content/help/en/experience-manager/kt/eseminars/experience-insider/experience-insider-oss-index/jcr:content/hero/file)
>* [Need for Speed - Accelerate time to value with new Cloud Manager](/content/help/en/experience-manager/kt/eseminars/experience-insider/aem-cloud-manager)
>* [AEM Assets Part 1: Dynamic Media Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-dynamic-media)
>* [AEM Sites: Best Practices for Organizational Readiness](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-sites)
>* [Mobile Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-mobile-best-practices)
>* [AEM Assets Part 2: DAM Implementation Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-dam-best-practices)
>* [AEM Sites 6.3 What’s New and Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-sites-6-3)
>* [AEM Assets 6.3 What’s New and Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-assets-6-3)
>* [AEM Assets 6.3 Dynamic Media: What’s New and Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-dynamic-media-6-3)
>* [AEM Forms 6.3: What’s New and Best Practices](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-forms-6-3)
>* [AEM 6.3 What’s New for Integrations](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-aem-integrations-6-3)
>* [Need for Speed - Accelerate time to value with new Cloud Manager](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-cloud-manager)
>* [Insider tips to empower your omnichannel business](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-sites-64)
>* [Unlocking More Powerful Asset Analytics With AEM 6.4](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-asset-analytics)
>* [Unlocking More Powerful Asset Analytics With AEM 6.4](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-asset-analytics-64)
>* [GDPR - An opportunity to provide outstanding customer experiences](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-gdpr-customer-experience)
>* [Optimizing Creative Operations with AEM Assets](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-creative-ops-assets1)
>* [Harness the Power of Touch UI To Deliver Amazing Experiences at Scale](/content/help/en/experience-manager/kt/eseminars/experience-insider/exp-touch-ui)
>* [Adobe Campaign: Mobile Delivery Channels](/content/help/en/experience-manager/kt/eseminars/ccoo-campaign-Jan-recording)
>* [Adobe Target: Visual Experience Composer](/content/help/en/experience-manager/kt/eseminars/ccoo-target-Jan-recording)
>* [Adobe Experience Manager: Adaptive Forms - Authoring and Processing](/content/help/en/experience-manager/kt/eseminars/ccoo-aem-Jan-recording)
>* [Adobe Analytics: Using RAW data](/content/help/en/experience-manager/kt/eseminars/ccoo-analytics-Jan-recording)
>* [Marketing](/content/help/en/experience-manager/kt/marketing)
>* [dm-test](/content/help/en/experience-manager/kt/marketing/dm-test)
>* [AEM Assets 6.3 Videos](/content/help/en/experience-manager/kt/marketing/sampleindex)
>* [Sample Article](/content/help/en/experience-manager/kt/marketing/samplearticle)
>* [Playground](/content/help/en/experience-manager/kt/playground)
>* [test](/content/help/en/experience-manager/kt/playground/test)
>* [test](/content/help/en/experience-manager/kt/playground/foo)
>* [footwo](/content/help/en/experience-manager/kt/playground/footwo)
>* [foothree](/content/help/en/experience-manager/kt/playground/foothree)
>* [fourfive](/content/help/en/experience-manager/kt/playground/fourfive)
>* [AEM 6.3 Feature Videos](/content/help/en/experience-manager/kt/playground/max-foo-videos)
>* [Experience Business on Adobe Cloud Platform](/content/help/en/experience-manager/kt/playground/experience-business-acp-presentation-learn)
>* [WWSC 2019 Pre-conference Enablement](/content/help/en/experience-manager/kt/playground/wwsc-preconference-enablement)
>* [SC Content Three](/content/help/en/experience-manager/kt/playground/wwsc-sc-3)
>* [SC Content Two](/content/help/en/experience-manager/kt/playground/wwsc-sc-2)
>* [SC Content One](/content/help/en/experience-manager/kt/playground/wwsc-sc-1)
>* [CSM Content One](/content/help/en/experience-manager/kt/playground/wwsc-csm-1)
>* [CSM Content One](/content/help/en/experience-manager/kt/playground/wwsc-csm-2)
>* [CSM Content Three](/content/help/en/experience-manager/kt/playground/wwsc-csm-3)
>* [Description text SEO title](/content/help/en/experience-manager/kt/playground/foo-feature-video-use)
>* [Description text SEO title](/content/help/en/experience-manager/kt/playground/foo-feature2-video-use)
>* [Screens](/content/help/en/experience-manager/kt/screens)
>* [Internal](/content/help/en/experience-manager/kt/screens/internal)
>* [KB](/content/help/en/experience-manager/kt/screens/kb)
>* [Using](/content/help/en/experience-manager/kt/screens/using)
>* [REDIRECT Understanding AEM Screens](/content/help/en/experience-manager/kt/screens/using/screens-concepts-feature-video-understand)
>* [REDIRECT Extending an AEM Screens Component](/content/help/en/experience-manager/kt/screens/using/extending-component-tutorial-develop)
>* [REDIRECT Developing a Custom Component for AEM Screens](/content/help/en/experience-manager/kt/screens/using/developing-custom-component-tutorial-develop)
>* [Index](/content/help/en/experience-manager/kt/screens/index)
>* [AEM 6.4 Screens Videos](/content/help/en/experience-manager/kt/screens/index/aem-6-4-screens)
