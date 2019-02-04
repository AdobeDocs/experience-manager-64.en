---
title: Known patterns and styles
seo-title: Known patterns and styles
description: null
seo-description: null
page-status-flag: never-activated
uuid: 3bbdade0-1ea0-437b-a151-1e0916fbc1a3
discoiquuid: 3de2b061-d8bb-4235-8ca5-59cf1a1a120b
index: y
internal: n
snippet: y
---

# Known patterns and styles{#known-patterns-and-styles}

AEM Forms Automated Conversion service converts a PDF form to an adaptive form. The service uses artificial intelligence and machine learning algorithms to understand the layout and fields of the source form. Every machine learning service continuously learns from source data and produces an improved output with every churn. These services learn from the experience like humans.

Automated Forms Conversion service is trained on a large set of forms. It easily identifies fields in a source form and produces adaptive forms. However, there are some fields and styles in PDF forms which are easily visible to the human eye but difficult to understand for the service. The service can assign different than applicable field types or panels to some fields or styles. All such field and style patterns are listed below.

The service would start identifying and assigning correct fields or panels to these patterns as it keeps learning from the source data. For the time being, you can use [Review and Correct](../../../forms/using/wip/review-correct-ui-edited.md) editor to fix such issues. Before start fixing the issues or reading further, familiarize yourself with [adaptive form components](../../../forms/using/introduction-forms-authoring.md).

## Style and layout {#style-and-layout}

<details>
 <summary>Service may not convert or partially convert PDF forms with a dotted outline, colored fields, or filled forms to adaptive forms. </summary>
 <img captionBottom="Scanned PDF Forms, PDF Forms with the dynamic layout, dotted outline, and filled or colored fields are not supported. " imageRotate="0" src="assets/Colored-dotted-filled-form.PNG" />
</details>

<details>
 <summary>Service does not support scanned forms or PDF forms with content in the form of an image.</summary>
 <img imageRotate="0" src="assets/scanned-forms.jpeg" />
</details>

<details>
 <summary>Service can leave some texts with very small fonts or very less width in between lines unidentified. To identify such texts, add space between the lines and increase the font size of such texts and re-convert the forms. </summary>
 <img imageRotate="0" src="assets/dense-forms-2.png" />
</details>

## Choice Group {#choice-group}

<details>
 <summary>Service may not or partially recognize nested choice groups</summary>
</details>

<details>
 <summary>Choice groups with only box or circular shapes are supported. Choice groups with any other shape are not converted to corresponding adaptive form components </summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

## Fields and widgets {#fields-and-widgets}

<details>
 <summary>Service can leave some form fields without borders unidentified</summary>
 <img imageRotate="0" src="assets/border-less-fields-1.PNG" />
</details>

<details>
 <summary>Service can leave some form fields with captions at the bottom or right unidentified</summary>
 <img imageRotate="0" src="assets/caption-at-bottom-fields.PNG" />
</details>

<details>
 <summary>Service does not support hidden fields</summary>
 <video imageRotate="0" status="changing" videoLocalizationType="subtitle" videoSrcUrl="/content/dam/help/en/experience-manager/6-4/forms/using/wip/styles-and-pattern--considerations-and-best-practices-/jcr_content/main-pars/image/hidden-fields.mp4"></video>
</details>

<details>
 <summary>Service can merge the form fields which are very near to each other or assign a wrong type to such fields</summary>
</details>

<details>
 <summary>Service may not recognize fields without explicit labels</summary>
 <img imageRotate="0" />
</details>

<details>
 <summary>Service may not recognize fields with far away captions</summary>
</details>

## Image {#image}

<details>
 <summary>Service does not identify images. Manually add images to converted forms</summary>
</details>

<details>
 <summary>Service does not extract text present within an image. </summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

## List {#list}

<details>
 <summary>Lists containing form fields are not supported</summary>
 <img imageRotate="0" src="assets/list-with-fields-patterns.png" />
</details>

<details>
 <summary>Service can leave a few nested lists unidentified </summary>
</details>

<details>
 <summary>Service can merge some closely spaced list items with each other</summary>
</details>

<details>
 <summary>Service can merge lists containing choice groups with each other</summary>
 <img imageRotate="0" src="assets/lists-with-choice-group.png" />
</details>

<details>
 <summary>Item Title</summary>
</details>

## Table {#table}

<details>
 <summary>Some borderless tables are not converted to adaptive form tables</summary>
 <img imageRotate="0" src="assets/border-less.PNG" />
</details>

<details>
 <summary>Service does not convert nested tables to adaptive form tables</summary>
</details>

<details>
 <summary>Service may not convert some colored tables, large-empty table, and merged tables to adaptive form tables. Service easily converts simple tables, with empty fields, proper headers, and clear boundaries and borders to adaptive form tables.</summary>
 <img imageRotate="0" src="assets/tables.gif" />
</details>

<details>
 <summary>Tables with placeholder values are not converted to adaptive form tables</summary>
</details>

<!--
Comment Type: draft

<h2>Text</h2>
-->

<details>
 <summary>Very small fonts with densely packaged content are not recognized</summary>
 <img imageRotate="0" src="assets/dense-forms-2.png" />
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

<details>
 <summary>Item Title</summary>
</details>

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

