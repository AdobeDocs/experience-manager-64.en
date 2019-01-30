---
title: Known patterns and styles
seo-title: Known patterns and styles
description: null
seo-description: null
page-status-flag: never-activated
uuid: 0775ae5d-3884-4694-af9c-51ddcd1fd62e
discoiquuid: 538f094c-7292-4d6a-952d-c5bfe38c83c5
lastpublishinternaldate: 2018-11-29T08 40 12.895-0500
index: y
internal: n
snippet: y
---

# Known patterns and styles{#known-patterns-and-styles}

AEM Forms Automated Conversion service converts a PDF form to an adaptive form. The service uses artificial intelligence and machine learning algorithms to understand the layout and fields of the source form. Every machine learning service continuously learns from source data and produces an improved output with every churn. These services learn from the experience like humans.

Automated Forms Conversion service is trained on a large set of forms. It easily identifies fields in a source form and produces adaptive forms. However, there are some fields and styles in PDF forms which are easily visible to the human eye but difficult to understand for the service. The service can assign different than applicable field types or panels to some fields or styles. All such field and style patterns are listed below.

The service would start identifying and assigning correct fields or panels to these patterns as it keeps learning from the source data. For the time being, you can use [Review and Correct](../../../forms/using/wip/review-correct-ui-edited.md) editor to fix such issues. Before start fixing the issues or reading further, familiarize yourself with [adaptive form components](../../../forms/using/introduction-forms-authoring.md).

## Style and layout {#style-and-layout}

![](assets/Colored-dotted-filled-form.PNG) ![](assets/scanned-forms.jpeg) ![](assets/dense-forms-2.png)

## Choice Group {#choice-group}

## Fields and widgets {#fields-and-widgets}

![](assets/border-less-fields-1.PNG) ![](assets/caption-at-bottom-fields.PNG)

>[!VIDEO](/content/dam/help/en/experience-manager/6-4/forms/using/wip/styles-and-pattern--considerations-and-best-practices-/jcr_content/main-pars/image/hidden-fields.mp4)

![]()

## Image {#image}

## List {#list}

![](assets/list-with-fields-patterns.png) ![](assets/lists-with-choice-group.png)

## Table {#table}

![](assets/border-less.PNG) ![](assets/tables.gif)

<!--
Comment Type: draft

<h2>Text</h2>
-->

![](assets/dense-forms-2.png)

<!--
Comment Type: draft

<h4>Scanned PDF Forms, PDF Forms with the dynamic layout, dotted outline, and filled or colored fields are not supported.</h4>
-->

<!--
Comment Type: draft

<ul>
<li>Scanned PDF Forms, PDF Forms with the dynamic layout, dotted outline, and filled or colored fields are not supported.<br /> </li>
</ul>
-->

<!--
Comment Type: draft

<ul>
<li>Forms with very small fonts or content with very less width in between lines are not converted properly. Add spacing between the lines and increase the size of forms before starting the conversion.</li>
</ul>
-->

<!--
Comment Type: draft

<ul>
<li>Forms with very small fonts or content with very less width in between lines are not converted properly. Add spacing between the lines and increase the size of forms before starting the conversion.</li>
<li>Images and text inside the images are not identified. Manually add images to converted forms.<br /> </li>
<li>Complex tables like borderless tables, nested tables, table with colored rows, and tables with placeholder values are not converted to adaptive form tables. Only simple table, with empty fields, proper headers, and clear boundaries and borders are supported. You can use <a href="https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/wip/review-correct-ui-edited.html#main-pars_header_1182718738">adaptive form editor</a> to add or modify complex tables, after the conversion.</li>
</ul>
-->

<!--
Comment Type: draft

<h2>Field-level patterns and styles</h2>
-->

<!--
Comment Type: draft

<h3>Lists</h3>
-->

<!--
Comment Type: draft

<table border="1" cellpadding="1" cellspacing="0" width="100%">
<tbody>
<tr>
<td valign="top" width="204"><p>Pattern</p> </td>
<td>Resolution</td>
<td>Example</td>
</tr>
<tr>
<td>Closely spaced list items are merged.</td>
<td>Ensure there is proper spacing in the list items.</td>
<td><img src="assets/Closely-spaced-list-items.png" /></td>
</tr>
<tr>
<td>Lists with fields are not supported</td>
<td>Use Review and Correct editor to identify such fields</td>
<td><img src="assets/list-with-fields.png" /> </td>
</tr>
<tr>
<td> </td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>
-->

<!--
Comment Type: draft

<h3>Tables</h3>
-->

<!--
Comment Type: draft

<h3>Choice groups</h3>
-->

<!--
Comment Type: draft

<ul>
<li>Lists with form fields, nested lists, and nested choice groups are not supported.</li>
<li>Form fields with captions at bottom or right are not supported.</li>
<li>Form fiields without bordes are not supported.</li>
<li>Hidden form fields are not supported.</li>
<li>Button in PDF forms are not converted to adaptive form buttons.<br /> </li>
<li>Tables with clear explicit boundaries and borders are supported.</li>
<li>Fields with far away captions are not supported.<br /> </li>
<li>Choice groups with only box or circle shaped selectors are supported. </li>
</ul>
-->

