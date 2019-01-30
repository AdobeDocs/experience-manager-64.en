---
title: DO NOT PUBLISH, BUT DO NOT DELETE Experience Fragments
seo-title: DO NOT PUBLISH, BUT DO NOT DELETE Experience Fragments
description: null
seo-description: null
page-status-flag: never-activated
uuid: 5085df06-0ebe-4bf6-81af-b43594cffe1a
contentOwner: aheimoz
discoiquuid: b54429f5-0698-4046-91b7-62361400d5b6
preview: true
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH, BUT DO NOT DELETE Experience Fragments{#do-not-publish-but-do-not-delete-experience-fragments}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-19T08:35:14.751-0500
<p>6.5 CONTENT</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-19T08:41:05.157-0500
<p>https://jira.corp.adobe.com/browse/CQDOC-11638</p>
<p>conventions to be respected when developing social variations - and the components to be used:</p>
<p>Hardcoded node properties:<br /> <strong>fileReference</strong>, <strong>fileName</strong> - for extracting image<br /> <strong>text</strong> - for extracting text</p>
<p>Components which do NOT use this convention will not be taken into consideration.</p>
<p> </p>
<p>The ideea under it is that after you create a master variation, you can also create social variations (trim some text, remove some images, etc.)</p>
<p>Related to the last issue, to give a but more context:</p>
<p>· Social variants can be posted on social media (text and image).</p>
<p>· The social variants in AEM can contain any components (text components, image components, etc.)</p>
<p>· In order to poste the correct text and image to the social media network, some conventions need to be respected if custom components are built by customers.</p>
<p>- For text components the text must be saved as a property called `<strong>text</strong> ` on the component.</p>
<p>- For image components the image must be saved as a `<strong>fileReference</strong>` or `<strong>fileName</strong>` on the component.</p>
<p> </p>
-->

