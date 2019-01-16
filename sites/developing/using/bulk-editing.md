---
title: Configuring your Page for Bulk Editing of Page Properties
seo-title: Configuring your Page for Bulk Editing of Page Properties
description: null
seo-description: Bulk editing of page properties allows you to edit the properties of multiple pages at once
uuid: 278f05d1-e55a-4492-83b5-edad53724711
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: d3b5dfae-ba83-4195-af17-24950745ec26
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring your Page for Bulk Editing of Page Properties{#configuring-your-page-for-bulk-editing-of-page-properties}

[Bulk editing of page properties](../../authoring/using/editing-page-properties.md#fromthesitesconsolemultiplepages) allows you to edit the properties of multiple pages at once.

Due to the possibility of different values, page properties are not enabled for bulk editing as default. They must be explicitily whitelisted (enabled). When defining the page properties to be available for bulk editing you need to consider certain implications, such as:

* Certain fields are usually unique; for example a page title. You must decide whether it is meaningful to enable such fields for bulk editing, when one value will be applied.  
* Certain fields might have multiple values - this needs meaningful representation when rendering.  
  For example, a check-box indicating "Ready for Publication". This might have several values before bulk-editing (e.g. ready, in-review, in-progress).

>[!CAUTION]
>
>Bulk editing of page properties is:
>
>* Not available in the classic UI.
>* Not available for pages within a live copy.
>* Only available for pages with the same resource type. 
>

>[!NOTE]
>
>Bulk editing is also available for Assets. It is very similar, but differs in a few points. See [Editing Properties of Multiple Assets](/content/help/en/experience-manager/6-4/assets/using/managing-multiple-assets) for full information. You can customize the fields in the Bulk Metadata editor for Assets using the [Schema editor](/content/help/en/experience-manager/6-4/assets/using/metadata-schemas).

### Enabling a Field {#enabling-a-field}

>[!NOTE]
>
>Certain fields might have multiple values - this needs meaningful representation when rendering. For this reason you should only enable the following field types: 
>
>* `/libs/granite/ui/components/foundation/form/textfield`
>* `/libs/granite/ui/components/foundation/form/textarea`
>* `/libs/granite/ui/components/foundation/form/tagspicker`
>* `/libs/granite/ui/components/foundation/form/datepicker`
>* `/libs/granite/ui/components/foundation/form/pathbrowser`
>* `/libs/granite/ui/components/foundation/form/checkbox`
>

Fields are enabled on the page component (*not* on the template):

1. Using CRXDE Lite (or an equivalent method) open your page component.

   For example: `/apps/core/wcm/components/page/v1/page`

   >[!NOTE]
   >
   >This example assumes that the Core Components have been installed on the instance, which is the case if the instance is running with We.Retail sample content. See the [Core Components documentation](/content/help/en/experience-manager/core-components/user-guide) for more information.

1. Navigate to the required field within the `cq:dialog` definition.
1. Define the following property on the field node:

    * **Name**: `allowBulkEdit`  
    
    * **Type**: `Boolean`  
    
    * **Value**: `true`

   For example, for the standard page [foundation component](../../authoring/using/default-components-foundation.md):

   `/libs/foundation/components/page`

   The property would be defined on:

   `cq:dialog/content/items/tabs/items/basic/items/column/items/onofftime/items/ondate`

   >[!CAUTION]
   >
   >You ***must*** not change anything in the `/libs` path.
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

1. Select **Save All** to persist your updates.

<!-- 

Comment Type: draft

<h3>Defining an Indicator for Mixed Values</h3>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-01-18T11:18:11.556-0500

<p>CM:<br /> After some consideration, I'd keep this page straightforward and probably remove this section as it could be confusing (and is incomplete: providing an indicator for mixed values is not sufficient; there's also some more work that needs to be done so that the fields works nice with the bulk editing, see my previous comment on that page). So I'd only keep the part that explain how to add a field to bulk editing using the allowBulkEdit flag. Adding a *custom* field to bulk editing is more advanced; and we anyway don't have documentation explaining how to develop *custom* fields at the moment..<br /> <br /> tldr; Remove the "defining an indicator for mixed values" section; wait until we have some documentation that explains how to create custom fields and a nice github example for it.<br /> <br /> AH: But if we remove that section is it safe to leave the enabling a field section? How do we warn them not to enable a field that hasn't been correctly configured?</p>

 -->

<!-- 

Comment Type: draft

<p>When there is a common property that has, or can have, different values across selected pages, then this must be represented in some way for editing.</p> 
<p>Out-of-the-box, text fields with multiple values are represented with the text:</p> 
<p style="margin-left: 40px;"><strong>&lt;Mixed Entries&gt;</strong></p> 
<p>For example:<br /> </p>

 -->

<!-- 

Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-212.png" />

 -->

<!-- 

Comment Type: draft

<p>When you add fields to bulk editing then you must consider the representations required for the possible variations in content and, where necessary, provide your own representation.<br /> </p>

 -->

<!-- 

Comment Type: draft

<note type="note"> 
 <p>If you do not provide a representation, then the field will appear blank when editing, even though the individual pages do have values.</p> 
</note>

 -->

<!-- 

Comment Type: draft

<p>To provide a representation when rendering you need to change your <span class="code">jsp</span>/<span class="code">sightly</span> script to:</p>

 -->

<!-- 

Comment Type: draft

<ul> 
 <li><p>Detect whether the field has mixed values.</p> 
  <ul> 
   <li>Make use of the Granite Field API to detect whether the field is mixed or not. Depending on the result you need to render the value or an appropriate indicator.</li> 
  </ul> <p>For example:<br /> </p> 
  <codeblock gutter="true" class="syntax js">
    &nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(isMixed)&nbsp;{!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;attrs.addClass("foundation-field-mixed");!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;attrs.add("placeholder",&nbsp;i18n.get("<Mixed&nbsp;Entries>"));!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;else&nbsp;{!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;attrs.add("value",&nbsp;vm.get("value",&nbsp;String.class));!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;}!!discoiqbr!!!!discoiqbr!! 
  </codeblock> 
  <note type="caution"> 
   <p>Consideration should be given before providing fields with mixed values as they must be used with care (to avoid inadvertent data loss).<br /> </p> 
  </note> 
  <draft-comment color="yellow" lastModifiedBy="aheimoz" lastModifiedDate="2018-01-18T11:18:11.984-0500" prevFirstName="Alison" prevLastName="Heimoz" type="remark"> 
   <p>6.1 - do we need links to:</p> 
   <p>http://docs.adobe.com/docs/en/aem/6-0/develop/ref/granite-ui/api/jcr_root/libs/granite/ui/components/foundation/form/field/index.html ?</p> 
   <p>CM&gt;&gt;&gt; This links refers to the field UI component, we should actually refer the Field Java API (unfortunately, I didn't find it in the doc). The relevant method is Field#isMixed(Config cfg, Value value)</p> 
  </draft-comment> 
  <draft-comment color="yellow" lastModifiedBy="aheimoz" lastModifiedDate="2018-01-18T11:18:12.019-0500" prevFirstName="Alison" prevLastName="Heimoz" type="remark"> 
   <p>Christian Meyer - 2015/04/27</p> 
   <p>See https://jira.corp.adobe.com/browse/DOC-5452 for more complicated cases:<br /> <br /> Mixed fields shouldn't be "blindly" submitted (could lead to data loss)<br /> =&gt; foundation-field-mixed class + field.adaptTo(foundation-field-mixed).setMixed() API to properly set the class on the field<br /> =&gt; to prevent their submission, the field should provide an implementation for the field.adaptTo(foundation-field).setDisabled() API<br /> <br /> But this would be maybe too advanced/complicated to explain with words here. We should maybe provide a some code on Github like we did for the Extension points of the Page Authoring</p> 
   <p>++++++++++++++++++++</p> 
   <p>Have added a caution and....</p> 
   <p>Agree that code samples would be preferable - see:<br /> </p> 
   <ul> 
    <li><a href="https://jira.corp.adobe.com/browse/DOC-5459">https://jira.corp.adobe.com/browse/DOC-5459</a></li> 
   </ul> 
  </draft-comment><p>As an example, you can refer to:</p> <p style="margin-left: 40px;"><span class="code">/libs/granite/ui/components/foundation/form/textfield/render.jsp</span></p> 
  <note type="caution"> 
   <p>You <i><strong>must</strong></i> not change anything in the <span class="code">/libs</span> path.</p> 
   <p>This is because the content of <span class="code">/libs</span> is overwritten the next time you upgrade your instance (and may well be overwritten when you apply either a hotfix or feature pack).</p> 
   <p>The recommended method for configuration and other changes is:</p> 
   <ol> 
    <li>Recreate the required item (i.e. as it exists in <span class="code">/libs</span>) under <span class="code">/apps</span><br /> </li> 
    <li>Make any changes within <span class="code">/apps</span></li> 
   </ol> 
  </note></li> 
</ul>

 -->

