---
title: Customizing and Extending Content Fragments
seo-title: Customizing and Extending Content Fragments
description: null
seo-description: A content fragment extends a standard asset.
uuid: 86496c09-b776-44bd-9649-10aa82ab4a59
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 6982e0cb-9c60-4109-9156-8894f71f4105
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Customizing and Extending Content Fragments{#customizing-and-extending-content-fragments}

>[!CAUTION]
>
>Some Content Fragment functionality requires the application of [AEM 6.4 Service Pack 2 (6.4.2.0)](/content/help/en/experience-manager/6-4/release-notes/sp-release-notes).

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-15T04:18:48.477-0400

<p>Links need to be checked have ones pointing to 6.4 and 6.3</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
Last Modified Date: 2018-01-18T11:19:30.027-0500

<p>https://docs-author.corp.adobe.com/content/docs/en/aem/6-2/administer/sites/translation/tc-manage.html</p>

 -->

A content fragment extends a standard asset; see:

* [Creating and Managing Content Fragments](/content/help/en/experience-manager/6-4/assets/using/content-fragments) and [Page Authoring with Content Fragments](../../authoring/using/content-fragments.md) for further information about content fragments.

* [Managing Assets](/content/help/en/experience-manager/6-4/assets/using/managing-assets-touch-ui) and [Customizing and Extending Assets](/content/help/en/experience-manager/6-4/assets/using/extending-assets) for further information about standard assets.

## Architecture {#architecture}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-20T05:36:43.036-0400

<p>some changes to this section since the last review - mainly models/templates</p>

 -->

The basic [constituent parts](/content/help/en/experience-manager/6-4/assets/using/content-fragments#ConstituentPartsofaContentFragment) of a content fragment are:

* A *Content Fragment,*
* consisting of one or more *Content Element*s,
* and which can have one or more *Content Variation*s.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-20T05:34:18.330-0400

<p>is the following still valid? for structured fragments where elements == fields (oder?)<br /> </p>

 -->

<!-- 

Comment Type: draft

<ul> 
 <li>Where: 
  <ul> 
   <li>Variations are managed globally; i.e. all elements have the same number of variations with the same name and description, but with (potentially) different content.</li> 
  </ul> </li> 
</ul>

 -->

Depending on the type of fragment, either models or templates are also used:

>[!CAUTION]
>
>[Content fragment models](/content/help/en/experience-manager/6-4/assets/using/content-fragments-models) are now recommended for creating all your fragments. 
>
>Content fragment models are used for all examples in We.Retail.

<!-- 

Comment Type: draft

<note type="caution"> 
 <p><a href="/content/help/en/experience-manager/6-4/assets/using/content-fragments-models">Content fragment models</a> are now recommended for creating all your fragments. See:</p> 
 <ul> 
  <li>Customizing Content Fragment Models</li> 
  <li>Customizing Data Types for Content Fragment Models</li> 
 </ul> 
 <p>Content fragment models are used for all examples in We.Retail.</p> 
</note>

 -->

* Content Fragment Models:

    * Used for defining content fragments that hold structured content.
    * Content fragment models define the structure of a content fragment when it is created.
    * A fragment references the model; so changes to the model may/will impact any dependent fragments.  
    * Models are built-up of data types.  
    * Functions to add new variations, etc., have to update the fragment accordingly.

  <!-- 

Comment Type: draft

<p>Content Fragment Models:</p> 
<ul> 
 <li>Used for defining content fragments that hold structured content.</li> 
 <li>Content fragment models define the structure of a content fragment when it is created.</li> 
 <li>A fragment references the model; so changes to the model may/will impact any dependent fragments.<br /> </li> 
 <li>Models are built-up of data types.<br /> </li> 
 <li>Functions to add new variations, etc., have to update the fragment accordingly.</li> 
</ul>

 -->

  >[!CAUTION]
  >
  >Any changes to an existing content fragment model can impact dependent fragments; this can lead to orphan properties in those fragments.

* Content Fragment Templates:

    * Used for defining simple content fragments.
    * Templates define the (basic, text-only) structure of a content fragment when it is created.
    * The template is copied to the fragment when it is created; so further changes to the template will not be reflected in existing fragments.
    * Functions to add new variations, etc., have to update the fragment accordingly.
    * [Content fragment templates](../../developing/using/content-fragment-templates.md) operate in a different manner to that of other templating mechanisms within the AEM ecosystem (e.g. page templates, etc.). Therefore they should be considered separately.
    * When based on a template the MIME type of the content is managed on the actual content; this means that each element and variation can have a different MIME type.

### Integration with Assets {#integration-with-assets}

Content Fragment Management (CFM) is part of AEM Assets as:

* Content fragments are assets.
* They use existing Assets functionality.
* They are fully integrated with Assets (admin consoles, etc.).

#### Mapping Structured Content Fragments to Assets {#mapping-structured-content-fragments-to-assets}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T09:18:41.678-0400

<p>new sub-section</p>

 -->

![](assets/fragment-to-assets-structured.png)

Content fragments with structured content (i.e. based on a content fragment model) are mapped to a single asset:

* All content is stored under the `jcr:content/data` node of the asset:

    * The element data is stored under the master sub-node:  
      `jcr:content/data/master`
    
    * Variations are stored under a sub-node that carries the name of the variation:  
      e.g. `jcr:content/data/myvariation`
    
    * The data of each element is stored in the respective sub-node as a property with the element name:  
      e.g. the content of element `text` is stored as property `text` on `jcr:content/data/master`

* Metadata and associated content is stored below `jcr:content/metadata`  
  Except for the title and description, which are not considered traditional metadata and stored on `jcr:content`

#### Mapping Simple Content Fragments to Assets {#mapping-simple-content-fragments-to-assets}

![](assets/chlimage_1-215.png)

Simple content fragments (based on a template) are mapped to a composite consisting of a main asset and (optional) sub-assets:

* All non-content information of a fragment (such as title, description, metadata, structure) is managed on the main asset exclusively.
* The content of the first element of a fragment is mapped to the original rendition of the main asset.

    * The variations (if there are any) of the first element are mapped to other renditions of the main asset.

* Additional elements (if existing) are mapped to sub-assets of the main asset.

    * The main content of these additional elements map to the original rendition of the respective sub-asset.
    * Other variations (if applicable) of any additional elements map to other renditions of the respective sub-asset.

#### Asset Location {#asset-location}

As with standard assets, a content fragment is held under:

`/content/dam`

#### Asset Permissions {#asset-permissions}

For further details see [Content Fragment - Delete Considerations](/content/help/en/experience-manager/6-4/assets/using/content-fragments-delete).

#### Feature Integration {#feature-integration}

* The Content Fragment Management (CFM) feature builds on the Assets core, but should be as independent of it as possible.
* CFM provides its own implementations for items in the card/column/list views; these plug into the existing Assets content rendering implementations.
* Several Assets components have been extended to cater for content fragments.

### Using Content Fragments in Pages {#using-content-fragments-in-pages}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T09:18:11.708-0400

<p>some changes since last review - mainly models/templates</p>

 -->

>[!CAUTION]
>
>The [Content Fragment Core Component](/content/help/en/experience-manager/core-components/using/content-fragment-component) is now recommended. See [Developing Core Components](/content/help/en/experience-manager/core-components/using/developing) for more details.

Content fragments can be referenced from AEM pages, just as any other asset type. AEM provides the [**Content Fragment** core component](/content/help/en/experience-manager/core-components/using/content-fragment-component) - a [component that allows you to include content fragments on your pages](../../authoring/using/content-fragments.md#addingacontentfragmenttoyourpage). You can also extend, this **Content Fragment** core component.

* The component uses the `fragmentPath` property to reference the actual content fragment. The `fragmentPath` property is handled in the same manner as similar properties of other asset types; for example, when the content fragment is moved to another location.

* The component allows you to select the variation to be displayed.
* Additionally, a range of paragraphs can be selected to restrict the output; for example, this can be used for multi-column output.
* The component allows [in-between content](../../developing/using/components-content-fragments.md#inbetweencontent):

    * Here the component allows you to place other assets (images, etc.) in between the paragraphs of the referenced fragment.
    * For in-between content you need to:

        * be aware of the possibility of unstable references; in-between content (added when authoring a page) has no fixed relationship to the paragraph it is positioned next to, inserting a new paragraph (in the content fragment editor) before the position of the in-between content can lose the relative position
        * consider the additional parameters (such as like variation and paragraph filters) to avoid false positives in search results

>[!NOTE]
>
>**Content Fragment Model:**
>
>When using a content fragment that has been based on a content fragment model on a page, the model is referenced. This means that if the model has not been published at the time you publish the page, this will be flagged and the model added to the resources to be published with the page.
>
>**Content Fragment Template:**
>
>When using a content fragment that has been based on a content fragment template on a page, there is no reference as the template was copied when creating the fragment.

#### Configuration using OSGi console {#configuration-using-osgi-console}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T09:18:52.112-0400

<p>new sub-section</p>

 -->

The backend implementation of content fragments is, for example, responsible for making instances of a fragment used on a page searchable, or for managing mixed media content. This implementation needs to know which components are used for rendering fragments and how the rendering is parameterized.

The parameters for this can be configured in the [Web Console](../../deploying/using/configuring-osgi.md#osgiconfigurationwiththewebconsole), for the OSGi bundle **DAM Content Fragments Configuration**.

* **Resource types** 
  A list of `sling:resourceTypes` can be provided to define components that are used for rendering content fragments and where the background processing should be applied to.

* **Reference Properties** 
  A list of properties can be configured to specify where the reference to the fragment is stored for the respective component.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-20T06:06:37.548-0400

<p>note below - which property in particular - or both?</p>

 -->

>[!NOTE]
>
>There is no direct mapping between property and component type. 
>
>AEM simply takes the first property that can be found on a paragraph. So you should choose the properties carefully.

![](assets/osgi-config.png) 

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-15T08:35:00.926-0400

<p style="margin-left: 40px;">if paragraphScope == range then the property paragraphRange defines the range of paragraphs to be rendered (format: see component documentation)</p> 
<p>needs a link</p>

 -->

There are still some guidelines you must follow to ensure your component is compatible with the content fragment background processing:

* The name of the property where the element(s) to be rendered is defined must be either `element` or `elementNames`.

* The name of the property where the variation to be rendered is defined must be either `variation` or `variationName`.

* If the output of multiple elements is supported (by using `elementNames` to specify multiple elements), the actual display mode is defined by property `displayMode`:

    * If the value is `singleText` (and there is only one element configured) then the element is rendered as a text with in-between content, layout support, etc. This is the default for fragments where only one single element is rendered.
    * Otherwise, a much more simple approach is used (could be called "form view"), where no in-between content is supported and the fragment content is rendered "as is".

* If the fragment is rendered for `displayMode` == `singleText` (implicitly or explicitly) the following additional properties come into play:

    * `paragraphScope` defines whether all paragraphs, or only a range of paragraphs, should be rendered (values: `all` vs. `range`)
    
    * if `paragraphScope` == `range` then the property `paragraphRange` defines the range of paragraphs to be rendered

### Integration with other Frameworks {#integration-with-other-frameworks}

Content fragments can be integrated with:

* 

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T04:36:25.169-0400

<p>"As the model (which also includes lanugage-specific texts such as title, description, etc.) is copied from the template, it can be included in the translation process as well."</p> 
<p>reword to something like?</p> 
<p>As the fragment (which also includes lanugage-specific texts such as title, description, etc.) is dependent on the underlying content fragment model, it can be included in the translation process as well.</p>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-13T12:46:28.572-0400

<p>I don't think this is true (unfortunately translations popped up rather late, and we were not able to fully integrate with the translation framework).</p> 
<p>AFAIK:</p> 
<ul> 
 <li>Models are not automatically included in translation packages.</li> 
 <li>Not sure if they can be translated separately (please ask Mathias, he should be aware)</li> 
 <li>There's also a known issue with the We.Retail component (which shouldn't have an impact on this docu though, as the customer is not supposed to base his own work on sample code/content.</li> 
</ul>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-14T06:26:13.548-0400

<p>following relates to templates/simple fragments (not models)<br /> </p>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-15T08:53:35.732-0400

<p>have removed the bullet point about models - is the rest generic about the fragments themselves?<br /> </p>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-20T03:28:56.119-0400

<p>response from Mathias:</p> 
<ol> 
 <li>&gt;&gt;&gt; cf models would generally not be translated, just like page templates. Both are stored in /conf. Translation workflows pick up content for translation only in /content.</li> 
 <li>&lt;&lt;&lt; think the worry might have been because of field labels, etc.<br /> &gt;&gt;&gt; Those could probably be translated with i18n/dictionary mechanism</li> 
</ol>

 -->

  **Translations**

  Content Fragments are fully integrated with the [AEM translation workflow](../../administering/using/tc-manage.md). On an architectural level, this means:

    * The individual translations of a content fragment are actually separate fragments; for example:

        * they are located under different language roots:  
          `/content/dam/<*path*/en/<*to*>/<*fragment*>`  
          vs.  
          `/content/dam/<*path*>/de/<*to*>/<*fragment*>`
        
        * but they share exactly the same relative path below the language root:  
          `/content/dam/<*path*>/en/<*to*>/<*fragment*>`  
          vs.  
          `/content/dam/<*path*>/de/<*to*>/<*fragment*>`

    * Besides the rule-based paths, there is no further connection between the different language versions of a content fragment; they are handled as two separate fragments, although the UI provides the means to navigate between the language variants.

  >[!NOTE]
  >
  >The AEM translation workflow works with `/content`:
  >
  >    
  >    
  >    * As the content fragment models reside in `/conf`, these are not included in such translations. You can [internationalize the UI strings](../../developing/using/i18n-dev.md).  
  >    
  >    * Templates are copied to create the fragment so this is implicit.  
  >    
  >

* **Metadata schemas**

    * Content fragments (re)use the [metadata schemas](/content/help/en/experience-manager/6-4/assets/using/metadata-schemas), that can be defined with standard assets.
    * CFM provides its own, specific schema:  
      `/libs/dam/content/schemaeditors/forms/contentfragment`  
      this can be extended if required.
    
    * The respective schema form is integrated with the fragment editor.

## The Content Fragment Management API - Server-Side {#the-content-fragment-management-api-server-side}

You can use the server-side API to access your content fragments; see:

` [com.adobe.cq.dam.cfm](/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/package-summary)`

>[!CAUTION]
>
>It is strongly recommended to use the server-side API instead of directly accessing the content structure.

### Key Interfaces {#key-interfaces}

The following three interfaces can serve as entry points:

* **Fragment Template** ( ` [FragmentTemplate](/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/FragmentTemplate)`)

  Use `FragmentTemplate.createFragment()` for creating a new fragment.

  ```
  Resource templateOrModelRsc = resourceResolver.getResource("...");
  FragmentTemplate tpl = templateOrModelRsc.adaptTo(FragmentTemplate.class);
  ContentFragment newFragment = tpl.createFragment(parentRsc, "A fragment name", "A fragment description.");
  
  ```

  <!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-13T13:07:46.428-0400

<p>In general this is still valid, but we used "data model" for template-based fragments already - which is somehow different from the "model" of structured fragments.</p> 
<p>Suggestion is to replace</p> 
<p style="margin-left: 40px;"><em>Get the model for a given element/variation</em></p> 
<p>with</p> 
<p style="margin-left: 40px;"><em>Get structural information for a given element/variation</em></p> 
<p>and mention that a FragmentTemplate is used to represent both template and model (naming may be confusing; but it is as it is due to historical reasons - no change to avoid compatibility issues). Same is true for ElementTemplate - despite the naming they reflect both element templates/fields.</p> 
<p>VariationTemplate is (more or less) unrelated to the notion of model vs. template (as it means the same for both types of fragments).</p>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T05:18:26.158-0400

<p>...and use of template was ambiguous as well.....joy</p>

 -->

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-20T03:37:27.071-0400

<p>changes made since first review</p>

 -->

  This interface represents:

    * either a content fragment model or content fragment template from which to create a content fragment,  
    * and (after the creation) the structural information of that fragment

  This information can include:

    * Access basic data (title, description)
    * Access templates/models for the elements of the fragment:

        * List element templates
        * Get structural information for a given element
        * Access the element template (see `ElementTemplate`)

    * Access templates for the variations of the fragment:

        * List variation templates
        * Get structural information for a given variation
        * Access the variation template (see `VariationTemplate`)

    * Get initial associated content

  Interfaces that represent important information:

    * `ElementTemplate`

        * Get basic data (name, title)
        * Get initial element content

    * `VariationTemplate`

        * Get basic data (name, title, description)

* **Content Fragment** ( ` [ContentFragment](/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/ContentFragment)`)

  This interface allows you to work with a content fragment in an abstract way.

  >[!CAUTION]
  >
  >It is strongly recommended to access a fragment through this interface. Changing the content structure directly should be avoided.

  The interface provides you with the means to:

    * Manage basic data (e.g. get name; get/set title/description)
    * Access meta data
    * Access elements:

        * List elements
        * Get elements by name
        * Create new elements (see [Caveats](#caveats))  
        
        * Access element data (see `ContentElement`)

    * List variations defined for the fragment
    * Create new variations globally
    * Manage associated content:

        * List collections
        * Add collections
        * Remove collections

    * Access the fragment's model or template

  Interfaces that represent the prime elements of a fragment are:

    * **Content Element** ( ` [ContentElement](/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/ContentElement)`)

        * Get basic data (name, title, description)
        * Get/Set content
        * Access variations of an element:

            * List variations
            * Get variations by name
            * Create new variations (see [Caveats](#caveats))
            * Remove variations (see [Caveats](#caveats))
            * Access variation data (see `ContentVariation`)

        * Shortcut for resolving variations (applying some additional, implementation-specific fallback logic if the specified variation is not available for an element)

    * **Content Variation** ( ` [ContentVariation](/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/ContentVariation)`)

        * Get basic data (name, title, description)
        * Get/Set content
        * Simple synchronization, based on last modified information

  All three interfaces ( `ContentFragment`, `ContentElement`, `ContentVariation`) extend the `Versionable` interface, which adds versioning capabilities, required for content fragments:

    * Create new version of the element
    * List versions of the element
    * Get the content of a specific version of the versioned element

### Adapting - Using adaptTo() {#adapting-using-adaptto}

The following can be adapted:

* `ContentFragment` can be adapted to:

    * `Resource` - the underlying Sling resource; note that updating the underlying `Resource` directly, requires rebuilding the `ContentFragment` object.
    
    * `Asset` - the DAM `Asset` abstraction that represents the content fragment; note that updating the `Asset` directly, requires rebuilding the `ContentFragment` object.

* `ContentElement` can be adapted to:

    * `ElementTemplate` - for accessing the element's structural information.

* 

  <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-14T06:38:55.441-0400

<p>add link to template and model pages</p>

 -->

  `FragmentTemplate` can be adapted to:

    * `Resource` - the `Resource` determining the referenced model or the original template that was copied;

        * changes made through the `Resource` are not automatically reflected in the `FragmentTemplate`.

* `Resource` can be adapted to:

    * `ContentFragment`
    * `FragmentTemplate`

### Caveats {#caveats}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-15T10:17:28.683-0400

<p>updates made since the first review</p>

 -->

It should be noted that:

* The API is implemented to provide functionality supported by the UI.
* The entire API is designed to **not** persist changes automatically (unless otherwise noted in the API JavaDoc). So you will always have to commit the resource resolver of the respective request (or the resolver you are actually using).
* Tasks that might require additional effort:

    * Creating/removing new elements will not update the data structure of simple fragments (based on a fragment template).
    * Creating new variations from `ContentElement` will not update the data structure (but creating them globally from `ContentFragment` will).
    
    * Removing existing variations will not update the data structure.

## The Content Fragment Management API - Client-Side {#the-content-fragment-management-api-client-side}

<!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-14T04:27:34.547-0400

<p>The entire clientside admin part has been marked "internal" (besides a single rendercondition), so there is no such thing anymore. So for 6.4, this entire chapter can be removed.</p> 
<p>Things that are not below /libs/dam/cfm/admin may be excluded from that rule, but I will add remarks at the respective content.</p> 
<p>I would still mention that the old API is still supported IF 6.4 is run in compat mode (with the compat package installed). And provide a link back to the 6.3 version of the documentation.</p>

 -->

>[!CAUTION]
>
>For AEM 6.4 the client-side API is internal.

<!-- 

Comment Type: draft

<note type="caution"> 
 <p>For AEM 6.4 the client-side API is internal.</p> 
 <p>If you are using AEM 6.4 in backwards compatibility mode you can refer to the AEM 6.3 documentation.<br /> </p> 
</note>

 -->

### Additional Information {#additional-information}

<!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-14T04:28:44.445-0400

<p>I would keep this, except for some areas. See my respective remarks.</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T05:19:59.383-0400

<p>would it make sense to relocate this....now that it's down to one point...but where does it best belong?</p>

 -->

See the following:

* `filter.xml`

  The `filter.xml` for content fragment management is configured so that it does not overlap with the Assets core content package.

## Edit Sessions {#edit-sessions}

<!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-14T04:33:38.438-0400

<p>Not sure about this section.</p> 
<p>I think it's worth keeping with some changes, as it provides some useful background information.</p> 
<p>Changes:</p> 
<ul> 
 <li>Remove reference to cfm:block</li> 
 <li>Entering a page/content change: In 6.4, the edit session is always started when the user enters a page. The system doesn't wait for the first edit. (There's a JIRA to get back to the previous behavior, but we didn't get that far for 6.4.)</li> 
</ul>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-03-16T05:23:45.784-0400

<ul> 
 <li>have removed the mention cfm:block (haven't replaced it with anything else)</li> 
 <li>have updated the paragraph about editing session, have left the original in draft for if/when it does revert<br /> </li> 
</ul>

 -->

An editing session is started when the user opens a content fragment in one of the editor pages. The editing session is finished when the user leaves the editor by selecting either **Save** or **Cancel**.

<!-- 

Comment Type: draft

<p>An editing session is started when the user opens a content fragment in one of the editor pages and starts editing; for example, by entering text or removing a variation. The editing session is finished when the user leaves the editor by selecting either <strong>Save</strong> or <strong>Cancel</strong>.</p>

 -->

#### Requirements {#requirements}

Requirements for controlling an editing session are:

* Editing a content fragment, which can span multiple views (= HTML pages), should be atomic.
* The editing should also be *transactional*; at the end of the edit session the changes must either be committed (saved) or rolled back (cancelled).
* Edge cases should be handled properly; these include situations such as when the user leaving the page by entering a URL manually or using global navigation.
* A periodic auto save (every x minutes) should be available to prevent data loss.
* If a content fragment is edited by two users concurrently, they should not overwrite each other's changes.

#### Processes {#processes}

The processes involved are:

* Starting a session

    * A new version of the content fragment is created.
    * Auto save is started.
    * Cookies are set; these define the currently edited fragment and that there is an edit session open.

* Finishing a session

    * Auto save is stopped.
    * Upon commit:

        * The last modified information is updated.
        * Cookies are removed.

    * Upon rollback:

        * The version of the content fragment that was created when the edit session was started is restored.
        * Cookies are removed.

* Editing

    * All changes (auto save included) are done on the active content fragment - not in a separated, protected area.
    * Therefore, those changes are reflected immediately on AEM pages that reference the respective content fragment

#### Actions {#actions}

The possible actions are:

* Entering a page

    * Check if an editing session is already present; by checking the respective cookie.

        * If one exists, verify that the editing session was started for the content fragment that is currently being edited

            * If the current fragment, reestablish the session.
            * If not, try to cancel editing for the previously edited content fragment and remove cookies (no editing session present afterwards).

        * If no edit session exists, wait for the first change made by the user (see below).

    * Check if the content fragment is already referenced on a page and display appropriate information if so.

* Content change

    * Whenever the user changes content and there is no edit session present, a new edit session is created (see [Starting a session](#processes)).

* Leaving a page

    * If an editing session is present and the changes have not been persisted, a modal confirmation dialog is shown to notify the user of potentially lost content and allow them to stay on the page.

## Examples {#examples}

### Example: Accessing an existing content fragment {#example-accessing-an-existing-content-fragment}

To achieve this you can adapt the resource that represents the API to:

`com.adobe.cq.dam.cfm.ContentFragment`

For example:

```java
// first, get the resource
Resource fragmentResource = resourceResolver.getResource("/content/dam/fragments/my-fragment");
// then adapt it
if (fragmentResource != null) {
    ContentFragment fragment = fragmentResource.adaptTo(ContentFragment.class);
    // the resource is now accessible through the API
} 
```

### Example: Creating a new content fragment {#example-creating-a-new-content-fragment}

To create a new content fragment programmatically, you need to use:

`com.adobe.cq.dam.cfm.ContentFragmentManager#create`

For example:

```java
Resource templateOrModelRsc = resourceResolver.getResource("...");
FragmentTemplate tpl = templateOrModelRsc.adaptTo(FragmentTemplate.class);
ContentFragment newFragment = tpl.createFragment(parentRsc, "A fragment name", "A fragment description.");

```

### Example: Specifying the auto-save interval {#example-specifying-the-auto-save-interval}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-02-15T06:39:47.749-0500

<p>need a link to confmgr docu</p> 
<p>see https://jira.corp.adobe.com/browse/DOC-6654</p> 
<p>now https://jira.corp.adobe.com/browse/CQDOC-6654</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-03-14T04:42:53.795-0400

<p>Technical documentation for confmgr is: https://git.corp.adobe.com/Granite/com.adobe.granite.confmgr (unfortunately private, so you can't link it).</p> 
<p>Unfortunately, there doesn't seem to be "regular" doc available (but I might have missed something - search on docs.adobe.com is not really useful for terms like "configuration manager" ...)</p>

 -->

The auto save interval (measured in seconds) can be defined using the configuration manager (ConfMgr):

* Node: `<*conf-root*>/settings/dam/cfm/jcr:content`
* Property Name: `autoSaveInterval`
* Type: `Long`  

* Default: `600` (10 minutes); this is defined on `/libs/settings/dam/cfm/jcr:content`

If you want to set an auto save interval of 5 minutes you need to define the property on your node; for example:

* Node: `/conf/global/settings/dam/cfm/jcr:content`
* Property Name: `autoSaveInterval`  

* Type: `Long`  

* Value: `300` (5 minutes equates to 300 seconds)

## Content Fragment Templates {#content-fragment-templates}

See [Content Fragment Templates](../../developing/using/content-fragment-templates.md) for full information.

<!-- 

Comment Type: draft

<h2>Content Fragment Models</h2>

 -->

<!-- 

Comment Type: draft

<p>For further information see:</p> 
<ul> 
 <li>Customizing Content Fragment Models<br /> </li> 
 <li>Customizing Data Types for Content Fragment Models </li> 
</ul>

 -->

## Components for Page Authoring {#components-for-page-authoring}

For further information see

* [Core Components - Content Fragment Component](/content/help/en/experience-manager/core-components/using/content-fragment-component) (recommended)
* [Content Fragment Components - Components for Page Authoring](../../developing/using/components-content-fragments.md#componentsforpageauthoring)

