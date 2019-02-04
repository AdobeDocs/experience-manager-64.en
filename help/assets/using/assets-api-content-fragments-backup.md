---
title: DO NOT PUBLISH BACKUP Content Fragments REST API
seo-title: DO NOT PUBLISH BACKUP Content Fragments REST API
description: null
seo-description: null
page-status-flag: never-activated
uuid: cdc7c973-6d3d-440e-9571-1be29e5697be
discoiquuid: fdc0e9f2-9386-44c5-8cab-34f23441377e
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH BACKUP Content Fragments REST API{#do-not-publish-backup-content-fragments-rest-api}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-30T09:50:43.196-0500
<p>CHANGE URL?</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-13T02:04:55.953-0500
<p><a href="https://wiki.corp.adobe.com/pages/viewpage.action?pageId=1570187152">https://wiki.corp.adobe.com/pages/viewpage.action?pageId=1570187152</a></p>
<p><a href="https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BContent+Fragments%5D+REST+API">https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BContent+Fragments%5D+REST+API</a></p>
<p><a href="https://jira.corp.adobe.com/browse/KT-2234">https://jira.corp.adobe.com/browse/KT-2234</a></p>
<p><a href="https://jira.corp.adobe.com/browse/CQDOC-13574">https://jira.corp.adobe.com/browse/CQDOC-13574</a></p>
<p><a href="https://jira.corp.adobe.com/browse/CQ-4210627">https://jira.corp.adobe.com/browse/CQ-4210627</a></p>
<p><a href="https://jira.corp.adobe.com/browse/CQ-4255471">https://jira.corp.adobe.com/browse/CQ-4255471</a><br /> </p>
<p><a href="https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=~sgrimm&title=HTTP+API">https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=~sgrimm&title=HTTP+API</a></p>
<p><a href="https://wiki.corp.adobe.com/display/~msiegel/AEM+Content+Services+Framework">https://wiki.corp.adobe.com/display/~msiegel/AEM+Content+Services+Framework</a></p>
<p> </p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T07:35:55.032-0500
<p>This page is currently for the 6.4 prerelease FP.....</p>
<p>Need details of where/how to join the prerelease....or will MS (or CM) create a prerelease page (as Jonas did).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T04:13:16.711-0500
<p>Current Task (fmpov):</p>
<ul>
<li>provide an overview/introduction/easy-how-to-use page to introduce the CF Rest API package and Swagger docs</li>
<li>for the prerelease</li>
</ul>
<div>
Can be extended once the initial FP is delivered.....
</div>
<div>
</div>
<div>
So have short-term and long-term goals! And need to differentiate them.
<br />
</div>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:21:20.372-0500
<p>various terms being used in various places</p>
<ul>
<li>Assets HTTP API</li>
<li>Granite HTTP API Framework</li>
<li><strong>Assets REST API</strong></li>
<li><strong>Content Fragments REST API</strong></li>
</ul>
<div>
do they need to be clarified for a devler?
</div>
<div>
what exactly needs to be documented here?
</div>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:08:40.576-0500
<ul>
<li>Assets HTTP API == Assets REST API</li>
<li>Granite HTTP API Framework is the technical foundation of the Assets HTTP API (or Assets HTTP API is built for Granite HTTP API Framework)</li>
<li>IMHO there should be no such thing like Content Fragments REST API on this page - here it a part of Assets HTTP/REST API, as both are accessed through /api/assets)</li>
</ul>
<p>That said, I would use a "Note" that shortly introduces Assets HTTP API & its foundation (could simply be a link to avoid duplication) and explains the relationship.</p>
<p>Or drop the usage of Granite HTTP API Framework altogether (typically, for the user of the API this fact is not really necessary - might still be required due to screenshots, config, etc.).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T01:59:42.291-0500
<p>The Feature Name given in the KT Wiki is:</p>
<ul>
<li>Feature Name - Content Fragments REST API</li>
</ul>
<p>Surely that is what should be covered here?</p>
<p>Also, originally was asked to provide an overview/intro page for the swagger docs....</p>
<p>But what else do we need - would prefer a clear definition (so can assess what we can achieve for various deadlines).<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:16:12.587-0500
<p>I can just argue from a developer's perspective:</p>
<ul>
<li>Content Fragment API doesn't make sense, as it is part of Assets API (/api/assets)</li>
<li>Some aspects are rather general (like SIREN output, request patterns, etc.) -&gt; in that respect, the entirety of /api (AEM HTTP API?) would be the best approach.</li>
<li>But this might be too broad, for a first version at least, as we would need to identify all contexts (Assets, Screens, Sites probably) and find or create documentation for them.</li>
</ul>
<p>Therefore my suggestion is to use the "Assets API" scope for now, as we have all information, and address the other API entry points (/api/screens, etc.) later. Otherwise we will probably have to delay it substantially (as other teams would heavily be involved if additional ref doc has to be created or existing ref doc has to be redone for a consistent look).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T05:11:38.136-0500
<p>SG:</p>
<p>This page is (currently) based on an initial draft <a href="/cf#content-fragments-rest-api.html">from this helpx-page</a>.</p>
<p>What has yet to be defined:</p>
<ul>
<li>Scope: CF without (at least parts of) the remaining Assets API does not make too much sense (for example, folders are required for creating CFs); but from a documentation perspective, it would make most sense to create one "umbrella" page for <em>all</em> usages of HAF (e.g. <em>/api/screens</em> as well), but this effort would clearly be out-of-scope for the FluidXP team. → <em>Assuming "Assets REST API" scope for this page, as those make most sense short-term.</em></li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T02:28:09.463-0500
<p>Scope:</p>
<ul>
<li>SG's wiki page only mentions the Assets REST API (apart from the title)<br />
<ul>
<li>do we need/want to mention CF REST API at all?</li>
<li>how is the Assets HTTP API different from the Assets REST API?</li>
</ul> </li>
<li>The Assets HTTP API page doesn't mention REST as all:
<ul>
<li>https://chl-author.corp.adobe.com/cf#/content/help/en/experience-manager/6-4/assets/using/mac-api-assets.html</li>
</ul> </li>
<li>"for example, folders are required for creating CFs"<br />
<ul>
<li>what about the content on the Assets HTTP page? Can we cross-reference? eg Create a folder
<ul>
<li>https://chl-author.corp.adobe.com/cf#/content/help/en/experience-manager/6-4/assets/using/mac-api-assets.html#CreateaFolder<br /> </li>
</ul> </li>
</ul> </li>
<li>An umbrella page for all uses of HAF -&gt; would be a new page/CQDOC-issue</li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:20:54.160-0500
<p>To be clear: In my opinion this should be the umbrella page for whatever scope we choose.</p>
<p>(Most parts of) T(t)he existing Assets API page will be the reference doc for Assets API minus the CF-specific parts (that may in the long term be migrated to Swagger, which would be the correct/consistent tool), therefore this will become a sub-page of this page, just as the CFM API will. Given his comments, I don't think Mathias is aware of this.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T06:49:19.343-0500
<p>Content Fragments REST API or Assets REST API?</p>
<p>Do I need to change the Title and URL of the page?</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:22:50.402-0500
<p>IMHO Content Fragment REST API doesn't make sense, as explained above.</p>
<p>(I blindly copy/pasted the CF-related title from a mail from Mathias to the Wiki, as requested - that might have led to the confusion.)</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:37:54.626-0500
<p>MS:</p>
<p>Hi Stefan, seems I can’t edit the page. Can you make the title a bit more self explanatory, like “Content Fragments REST API - Technical Documentation Overview” ?</p>
<p>Presumably referring to the wiki page......</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:23:56.607-0500
<p>Yes. Copy/Pasted it without reviewing. As said, technically "CF API" doesn't make sense.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T02:06:09.337-0500
<p>Related issues were:</p>
<p>- [Auto-Clone] support for Content Fragments in Assets HTTP API create/update operations</p>
<p>- [Auto-Clone] Content Fragment raw JSON output over http api framework</p>
<p>Would either of these be a better title for the page?</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:24:51.074-0500
<p>NO!</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T10:35:29.798-0500
<p>how to connect to https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html ?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:27:47.354-0500
<p>"Overview"/"Current implementation" sections can be included here.</p>
<p>Rest: Sub-page of this page, as it is reference documentation (= same content as the CFM Swagger documentation, just different formatting).</p>
<p>As said before, I don't think Mathias is aware of this.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T02:32:32.795-0500
<ul>
<li>API package
<ul>
<li>when will the API package be ready
<ul>
<li>https://jira.corp.adobe.com/browse/CQ-4210627 -&gt; <strong>L18</strong><br /> </li>
</ul> </li>
<li>how will it be made available as a prerelease FP for 6.4? <br />
<ul>
<li>packageshare?</li>
<li>prerelease site?</li>
</ul> </li>
<li>where will the installation instructions be? <br /> </li>
</ul> </li>
<li>when will the swagger docu package be ready?<br /> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:30:35.111-0500
<p style="margin-left: 40px;"><em>when will the swagger docu package be ready?</em></p>
<p>V 1.0.0 should be released before the end of this week.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-20T00:14:20.232-0500
<p><a href="https://wiki.corp.adobe.com/display/DMSArchitecture/KT+-+Content+Fragments+REST+API">https://wiki.corp.adobe.com/display/DMSArchitecture/KT+-+Content+Fragments+REST+API</a></p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:50:39.750-0500
<p><a href="https://wiki.corp.adobe.com/pages/viewpage.action?pageId=1570187152">https://wiki.corp.adobe.com/pages/viewpage.action?pageId=1570187152</a></p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:36:32.894-0500
<table>
<tbody>
<tr>
<td><p><strong>KPIs</strong></p> </td>
<td colspan="5"><p>M3: ability to output content fragment in JSON format as HTTP API response</p> <p>M4: ability create, update and delete content fragments over HTTP API</p> </td>
</tr>
</tbody>
</table>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-20T08:37:59.361-0500
<p>need link to more resources about the Content Services Framework....KT page?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T06:52:05.713-0500
<p>About the original introduction....</p>
<p style="margin-left: 40px;">&lt;sgrimm: The above sound more like a management summary. Depending on the target group (any reader vs. developer) I would suggest to drop it - assuming that a developer would know that, and it is somewhat redundant (although written with a different perspective).&gt;</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-20T00:13:44.218-0500
<p>Not tagged yet....will be done when location confirmed</p>
-->

## Overview {#overview}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:28:00.519-0500
<p>MS</p>
<ul>
<li>What is Content Fragment REST API?
<ul>
<li>see Introduction<br /> </li>
</ul> </li>
<li>How does it relate to other AEM API’s, internal and external?</li>
<li>When and for what purpose would it be used?</li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:38:34.393-0500
<p>Content Fragments REST API == Assets REST API?</p>
<p>And the difference to the Assets HTTP API???</p>
<p>ie can we link to https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html ?</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:41:04.810-0500
<p style="margin-left: 40px;"><em>Content Fragment REST API == Assets REST API?</em></p>
<p>Not exactly. CF REST API is a part of Assets REST API. It introduces an additional data type (for a CF) and adds suitable actions for manipulating it. But in general it's the same.</p>
<p style="margin-left: 40px;"><em>And the difference to the Assets HTTP API???</em></p>
<p>See above.</p>
<p style="margin-left: 40px;"><em>ie can we link to https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html ?</em></p>
<p>See comment above: Will become a sub-page.</p>
-->

The Assets REST API allows developers to access content (stored in AEM) directly over the HTTP API, via CRUD operations (Create, Read, Update, Delete).

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-03T02:26:41.849-0500
<p>"The API can be used".....the assets or the HTTP API?</p>
-->

The API can be used to realize headless Content Management Services (CMS) by providing Content Services to a JavaScript front end application. Or any other application that can execute HTTP requests and handle JSON responses.

For example, Single Page Applications (SPA), framework-based or custom, require content provided over the HTTP API, often in JSON format.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:26:09.353-0500
<p>slight change from:</p>
<p style="margin-left: 40px;">SG <br /> "While AEM Core Components provide a very comprehensive, flexible and customizable API that can serve at least the "read" aspect of this purpose, they do require WCM know-how for implementation as they must be hosted in (API) pages that are based on dedicated AEM templates. Not every SPA development organization has access to such resources. This page-based approach may also be inconvenient or even inadequate for some use-cases."</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-02T03:19:52.357-0500
<p>WCM?</p>
<p>do we still use that in the docs? if so need to expand</p>
<p>and/or is it the best term for here, needs to be AEM specific<br /> </p>
-->

While AEM Core Components provide a very comprehensive, flexible and customizable API that can serve (at least) the Read operations for this purpose, they do require WCM know-how for implementation as they must be hosted in (API) pages that are based on dedicated AEM templates. Not every SPA development organization has access to such resources. This page-based approach may also be inconvenient or even inadequate for some use-cases.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:25:43.307-0500
<p>SG: "It allows to access assets (images or even content fragments)"</p>
<ul>
<li>only images and CFs?</li>
<li>any other assets types, eg videos, pdfs, etc, etc?</li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:42:38.906-0500
<p>All asset types. Images & CF are merely examples.</p>
-->

This is when the Assets REST API can be used. It allows developers to access assets (images and content fragments) directly, without need to embed them in a page. Contrary to the API provided through AEM Core Components, the Assets REST API also allows developers to change content - by creating new, updating, or deleting existing assets and folders.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T06:51:10.370-0500
<p><em>&lt;sgrimm: Maybe it would make sense to provide short explanations for SIREN concepts that are later referred to, e.g. "Entities" <img alt="(question)" src="https://wiki.corp.adobe.com/s/en_GB/7502/0b299669c4463ddac3ccf20d032b26c21ec203a2/_/images/icons/emoticons/help_16.png" />&gt;</em></p>
-->

The Assets REST API:

* follows the [HATEOAS principle](https://en.wikipedia.org/wiki/HATEOAS)   

* implements the [SIREN format](https://github.com/kevinswiber/siren)

## Prerequisites {#prerequisites}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:28:22.152-0500
<p>MS</p>
<ul>
<li><em>If any (prerequisites for user to use)</em></li>
</ul>
-->

The Assets REST API is available on each out-of-the-box install of a recent AEM version.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T02:55:05.906-0500
<p>This page is currently for the 6.4 prerelease FP.....</p>
<p>Need details of where/how to join the prerelease.</p>
-->

>[!NOTE]
>
>For AEM 6.4 you have to install a Prerelease Feature Pack to get full support for content fragments. For some use-cases you then have to perform some additional configuration; see the [Security](../../assets/using/assets-api-content-fragments-backup.md#security) section.

<!--
Comment Type: draft

<note type="note">
<p>For versions of AEM before 6.5, you have to install a Feature Pack to get full support for content fragments. For some use-cases you then have to perform some additional configuration; see the <a href="../../assets/using/assets-api-content-fragments-backup.md#security">Security</a> section.</p>
</note>
-->

## Key Concepts {#key-concepts}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T06:56:37.940-0500
<p><em>&lt;sgrimm: Could be considered "too basic" - feel free to remove&gt;</em></p>
<p>Basic is good (imho).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T08:04:36.790-0500
<p>How does this relate to:</p>
<p>- https://chl-author.corp.adobe.com/content/help/en/experience-manager/6-4/assets/using/mac-api-assets.html#Currentimplementation </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:46:44.543-0500
<p>It doesn't.</p>
<p>Contrary to <em>#Current Implementation</em>, <em>#Available Features</em> is somewhat similar to this section, but this here is on a more general level. I would leave <em>#Available Features</em> to the reference docs. Or move it to the part of this page where you are linking to the reference documentation.</p>
-->

The Assets REST API offers [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)-style access to assets stored within an AEM instance. It uses the `/api/assets` endpoint and requires the path of the asset to access it (without the leading `/content/dam`).

The HTTP method determines the operation to be executed:

* **GET** - to retrieve a JSON representation of an asset or a folder
* **POST** - to create new assets or folders
* **PUT** - to update the properties of an asset or folder
* **DELETE** - to delete an asset or folder

>[!NOTE]
>
>The request body and/or URL parameters can be used to configure some of these operations; for example, define that a folder or an asset should be created by a **POST** request.

The exact format of supported requests is defined in the reference section of this documentation.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T07:05:24.789-0500
<p>reference section:</p>
<ul>
<li>the reference material?</li>
<li>the API Reference section of this page?</li>
<li>the reference materials section of this page?<br /> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:48:10.265-0500
<p>The Swagger documentation + the reference parts of the existing Assets API documentation (the parts that could be converted to Swagger Doc).</p>
-->

### Transactional Behavior {#transactional-behavior}

All requests are atomic.

This means that subsequent ( `write`) requests cannot be combined into a single transaction that could succeed or fail as a single entity.

<!--
Comment Type: draft

<h3>Architecture and Usage of the AEM HTTP API Framework</h3>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:28:59.638-0500
<p>MS</p>
<ul>
<li><p><em>Brief description of HAF</em></p> </li>
<li><p><em>What of HAF does CF API use, how, and why? </em></p> </li>
<li><p><em>CF API request processing (description, diagram)</em></p> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:03:27.852-0500
<p><em style="color: rgb(255, 0, 0); font-family: Arial, sans-serif; font-size: 14px; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: rgb(255, 255, 255); text-decoration-style: initial; text-decoration-color: initial;">&lt;sgrimm: Too far-reaching for an asset-related documentation. But required for an "umbrella documentation". Input required from other teams. Could also check for existing Wiki pages. Some documentation available on GitHub (see "Additional Resources"). Leaving out for now.&gt;</em></p>
-->

### AEM (Assets) REST API versus AEM Components {#aem-assets-rest-api-versus-aem-components}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-26T09:16:57.641-0500
<p>AEM Components or AEM Core Components?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:51:41.760-0500
<p>Technically it's not limited to Core Components, but to components that leverage Sling Models.</p>
<p>So I would either keep <em>AEM components</em> or change it to <em>AEM components</em> using Swing Models (as Sling Models are mentioned in the table, it would probably be kind of a duplication).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T01:36:38.768-0500
<p>Does it really need the double "/" ?</p>
<p>/api/assets<strong>//</strong>we-retail/en/products/apparel/gloves/Classic Leather.jpg.json</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:52:10.605-0500
<p>Nope, copy/paste bug :-)</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T00:02:37.914-0500
<p>Uses the .model selector to create the JSON representation.</p>
<p>An example URL would look like:<br /> http://.../content/we-retail/language-masters/en/products/men/gloves/classic-leather-gloves/jcr:content/root/product/image.json</p>
<p>&gt;&gt;&gt; where's the <span class="code">.model </span>selector in that example URL?</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:02:12.407-0500
<p>It went missing in action in the clipboard ;-).</p>
<p>Correct is: <span class="code">.../product/image.model.json</span> (the other URL works as well, but creates a different JSON output).</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T23:56:44.789-0500
<p>Need a new colour :)</p>
<p>What can we use from MS' page:</p>
<p><a href="https://wiki.corp.adobe.com/display/~msiegel/AEM+Content+Services+Framework">https://wiki.corp.adobe.com/display/~msiegel/AEM+Content+Services+Framework</a></p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:29:23.091-0500
<p>MS</p>
<ul>
<li><p><em>Components =&gt; customizable API, e.g. customizable JSON output (via Sling Model Exporter), but requires WCM knowledge for implementation (templates, pages, components)</em></p> </li>
<li><p><em>REST API =&gt; direct content API, no WCM knowledge required, but not customizable (logic, processing, syntax)</em></p> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-02T03:27:07.931-0500
<p>use the term WCM or Sites?</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T01:54:56.337-0500
<p><em>&lt;sgrimm: Too far-reaching for an asset-related documentation. But required for an "umbrella documentation". Input required from other teams. Could also check for existing Wiki pages. Some documentation available on GitHub (see "Additional Resources"). Leaving out for now.&gt;</em></p>
-->

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Aspect</td> 
   <td>Assets REST API<br /> </td> 
   <td>AEM Component</td> 
  </tr> 
  <tr> 
   <td>Supported use-case(s)</td> 
   <td>General purpose.</td> 
   <td><p>Optimized for consumption in a Single Page Application (SPA), or any other (content consuming) context.</p> <p>Can also contain layout information.</p> </td> 
  </tr> 
  <tr> 
   <td>Supported operations</td> 
   <td><p>Create, Read, Update, Delete.</p> <p>With additional operations depending on the entity type.</p> </td> 
   <td>Read-only.</td> 
  </tr> 
  <tr> 
   <td>Access</td> 
   <td><p>Can be accessed directly.</p> <p>Uses the <span class="code">/api/assets </span>endpoint, mapped to <span class="code">/content/dam</span> (in the repository).</p> <p>For example, to access:<code class="code">
       /content/dam/we-retail/en/products/apparel/gloves/Classic Leather.jpg</code><br /> request:<br /> <span class="code">/api/assets//we-retail/en/products/apparel/gloves/Classic Leather.jpg.json</span></p> </td> 
   <td><p>Needs to be referenced through an AEM component on an AEM page.</p> <p>Uses the <span class="code">.model</span> selector to create the JSON representation.</p> <p>An example URL would look like:<br /> <span class="code">http://.../content/we-retail/language-masters/en/products/men/gloves/classic-leather-gloves/jcr:content/root/product/image.json</span></p> </td> 
  </tr> 
  <tr> 
   <td>Security</td> 
   <td><p>Multiple options are possible.</p> <p>OAuth is proposed; can be configured separately from standard setup.</p> </td> 
   <td>Uses AEM's standard setup.</td> 
  </tr> 
  <tr> 
   <td>Architectural remarks</td> 
   <td><p>Write access will typically address an author instance.</p> <p>Read may also be directed to a publish instance.</p> </td> 
   <td>As this approach is read-only, it will typically be used for publish instances.</td> 
  </tr> 
  <tr> 
   <td>Output</td> 
   <td>JSON-based SIREN output: verbose, but powerful. Allows for navigating within the content.</td> 
   <td>JSON-based proprietary output; configurable through Sling Models. Navigating the content structure is hard to implement (but not necessarily impossible).</td> 
  </tr> 
 </tbody> 
</table>

### Security {#security}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:30:36.674-0500
<p>MS</p>
<ul>
<li><em>Authentication</em></li>
<li><em>....<br /> </em></li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T01:54:28.357-0500
<p><em>&lt;sgrimm: Is CORS required as well <img alt="(question)" src="https://wiki.corp.adobe.com/s/en_GB/7502/0b299669c4463ddac3ccf20d032b26c21ec203a2/_/images/icons/emoticons/help_16.png" />&gt;</em></p>
<p><em>&lt;sgrimm: to be verified; will need input from other teams on this topic; question is: rely on existing documentation (the KB; can't use the GitHub stuff) and simply put links, or create something original, like step-by-step instructions <img alt="(question)" src="https://wiki.corp.adobe.com/s/en_GB/7502/0b299669c4463ddac3ccf20d032b26c21ec203a2/_/images/icons/emoticons/help_16.png" />&gt;</em></p>
<p><em>&lt;sgrimm: In the long term, it would be good if we could provide examples, as this part is extremely blurry. Would again need help on this.&gt;</em></p>
-->

If the Assets REST API is used within an environment without specific authentication requirements, AEM's CORS filter needs to be configured correctly.

>[!NOTE]
>
>For further information see:
>
>* [the README of this GitHub repository](https://git.corp.adobe.com/Granite/com.adobe.granite.cors)
>* [CORS/AEM explained](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-article-understand)
>* [Video](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/cors-security-technical-video-develop.html)
>

In environments with specific authentication requirements, OAuth is recommended. To configure please see this [Gem session](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem). Additional information is available under [OAuth scopes](/content/help/en/experience-manager/kt/platform-repository/using/oauth-code-sample-develop)

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T00:17:10.690-0500
<p>OAuth is still an open issue for the security docs - disparate info received so far.</p>
-->

## Available Features {#available-features}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:33:38.284-0500
<p>MS</p>
<ul>
<li><p><em>Create</em></p> </li>
<li><p><em>Read</em></p> </li>
<li><p><em>Update</em></p> </li>
<li><p><em>Delete</em></p> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T23:59:40.072-0500
<p>see MS' input (above Remark)</p>
<p>Do we need to cover CRUD? or link to the Assets HTTP API page?</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:03:23.194-0500
<p>We could move the "Available Features" section from the Assets HTTP API page to this section. Could also add a note to the moved section that "Content Fragments are assets with some specifics, please refer to the 'Entity Types' section." (Or move the "Entity Types" section further to the top.)</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:33:26.992-0500
<p>probably need an intro paragraph; fwir markdown governance won't allow 2 headings together.....</p>
-->

### Paging {#paging}

The Assets REST API supports paging (for GET requests) via the URL parameters:

* `offset` - the number of the first (child) entity to retrieve
* `limit` - the maximum number of entities returned

The response will contain paging information as part of the `properties` section of the SIREN output. This `srn:paging` property contains the total number of (child) entities ( `total`), the offset and the limit ( `offset`, `limit`) as specified in the request.

>[!NOTE]
>
>Paging is typically applied on container entities (i.e. folders or assets with renditions), as it relates to the children of the requested entity.

#### Example: Paging {#example-paging}

`GET /api/assets.json?offset=2&limit=3`

```
...
"properties": {
    ...
    "srn:paging": {
        "total": 7,
        "offset": 2,
        "limit": 3
    }
    ...
}
...
```

## Extensibility {#extensibility}

For further information see this [Overview of the Granite HTTP API Framework](https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html).

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T10:59:36.973-0500
<p>Unfortunately this link points to Adobe internal GitHub, so we can't include it into public facing documentation.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:32:35.055-0500
<p>MS</p>
<ul>
<li><em style="color: rgb(51, 51, 51); font-family: Arial, sans-serif; font-size: 14px; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: left; text-indent: 0px; text-transform: none; white-space: normal; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: rgb(255, 255, 255); text-decoration-style: initial; text-decoration-color: initial;">If any (custom actions?)</em></li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:05:14.768-0500
<p><em>&lt;sgrimm: Some documentation on extensibility is available on <a href="https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html">this GitHub page</a>. Note that this is a very extensive topic. Strongly recommended to create a documentation dedicated on this topic alone.&gt;</em></p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:11:26.492-0500
<p>SG:</p>
<p>- -can leave it out for the moment; is for assets and cfs</p>
-->

## Entity Types {#entity-types}

### Folders {#folders}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T03:05:57.124-0500
<p>link to https://chl-author.corp.adobe.com/cf#/content/help/en/experience-manager/6-4/assets/using/mac-api-assets.html#CreateaFolder ?</p>
<p>or should these non-CF-specific entities sub-sections be moved to that page?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:06:19.744-0500
<p>This section explains the entity types that are available for the Assets API.</p>
<p>It's for overview only, to allow for getting the entire picture. Thus I wouldn't link to anything concrete (like how to create a folder).</p>
-->

Folders act as containers for assets and other folders. They reflect the structure of the AEM content repository.

The Assets REST API exposes access to the properties of a folder; for example its name, title, etc. Assets are exposed as child entities of folders.

>[!NOTE]
>
>Depending on the asset type the list of child entities may already contain the full set of properties that defines the respective child entity. Alternatively, only a reduced set of properties may be exposed for an entity in this list of child entities.

### Assets {#assets}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T03:07:32.783-0500
<p>link to https://chl-author.corp.adobe.com/cf#/content/help/en/experience-manager/6-4/assets/using/mac-api-assets.html#CreateanAsset ?</p>
<p>or should these non-CF-specific entities sub-sections be moved to that page?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:10:09.495-0500
<p>See above.</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-28T03:06:56.505-0500
<p>Should the first two sentences be merged? Or is there additional info missing from the first line?</p>
<p>If an asset is requested, the response will return the </p>
<p>The binary data of an asset is exposed as a SIREN link of type (aka rel attribute) content.</p>
-->

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:09:26.574-0500
<p>The first sentence was unfinished, I added the missing information directly in this page (not on the Wiki).</p>
-->

<!--
Comment Type: draft

<p>If an asset is requested, the response will return its metadata - like title, name and other information as defined by the respective assets schema.</p>
-->

The binary data of an asset is exposed as a SIREN link of type `content` (also known as the `rel attribute`).

Assets can have multiple renditions. These are typically exposed as child entities, one exception being a thumbnail rendition, which is exposed as a link of type `thumbnail` ( `rel="thumbnail"`).

### Content Fragments {#content-fragments}

A [content fragment](../../assets/using/content-fragments.md) is a special type of asset. They can be used to access structured data, such as texts, numbers, dates, amongst others.

As there are several differences to *standard* assets (such as images or audio), some additional rules apply to handling them.

#### Representation {#representation}

Content fragments:

* Do not expose any binary data.   
* Are completely contained in the JSON output (within the `properties` property).   

* Are also considered atomic, i.e. the elements and variations are exposed as part of the fragment's properties vs. as links or child entities. This allows for efficient access to the payload of a fragment.

#### Content Models and Content Fragments {#content-models-and-content-fragments}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:29:47.421-0500
<p>MS</p>
<p><em>Description of CF API targets (fragment, elements, variations, properties, metadata, media assets), to introduce vocabulary, with links to existing CF documentation for more detail</em></p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:46:22.915-0500
<p><img alt="(question)" src="https://wiki.corp.adobe.com/s/en_GB/7502/0b299669c4463ddac3ccf20d032b26c21ec203a2/_/images/icons/emoticons/help_16.png" /> <em>&lt;sgrimm: needs to be double-checked when the implementation is ready&gt;</em></p>
-->

Currently the models that define the structure of a content fragment are not exposed through an HTTP API. Therefore the *consumer* needs to know about the model of a fragment (at least a minimum) - although most information can be inferred from the payload; as data types, etc. are part of the definition.

To create a new content fragment, the (internal repository) path has to be provided.

#### Associated Content {#associated-content}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:22:09.632-0500
<p><em>&lt;sgrimm: Other aspects may also be worth of being documented&gt;</em></p>
-->

Associated content is currently not exposed.

<!--
Comment Type: draft

<h2>Best Practices</h2>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:31:44.090-0500
<p>MS</p>
<ul>
<li><p><em>Performance</em></p> </li>
<li><p><em>Security</em></p> </li>
<li><p><em>Compatibility (upgradeability) </em></p> </li>
<li><p><em>Things not to do</em></p> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:12:18.745-0500
<p><em>&lt;sgrimm: to be defined ... help from other teams required.&gt;</em></p>
-->

## API Reference {#api-reference}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:19:13.525-0500
<p>SG: </p>
<p>Would use three sub pages for the API Reference and link it here (or link it from the respective "Entities" sub-chapters):</p>
<ul>
<li>Assets, folder CRUD (from <a href="https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html">https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html</a>)</li>
<li>Assets, assets, renditions CRUD (from <a href="https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html">https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html</a>)</li>
<li>Assets, content fragments CRUD (the Swagger documentation, see <a href="https://wiki.corp.adobe.com/download/attachments/1570187152/cq-dam-cfm-haf-doc-1.0.0-SNAPSHOT-haf-doc.zip?version=1&modificationDate=1542872441117&api=v2">attached package</a> for an example)</li>
</ul>
<p> </p>
-->

See:

* Assets REST API
* Content Fragments REST API

### API URLs {#api-urls}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:18:08.938-0500
<p>what sort of URLs - examples or links to the reference doc package?<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T07:27:27.944-0500
<p>MS</p>
<ul>
<li><p>Base (<em>https//: … )</em></p> </li>
<li><p>Selectors <em>( .json, .model.json (if applicable), selectors for navigating up/down in CF structure)</em></p> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:13:38.707-0500
<strong>Examples</strong>
<p><em>&lt;sgrimm: IMHO an example section would make sense - mainly how to handle a SIREN response, like getting from the top-level folder to a specific image&gt;</em></p>
-->

## Additional Resources {#additional-resources}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T02:16:17.058-0500
<ul>
<li><a href="https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem.html">AEM Gem session: OAuth</a> - AH - already referenced</li>
<li><a href="https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html">HAF Extensibility (GitHub)</a> - SG - note that this is somewhat incomplete and may be outdated</li>
<li><a href="https://helpx.adobe.com/experience-manager/6-4/assets/using/mac-api-assets.html">Existing Assets REST API docs</a> SG - (will be re-used for the reference part of this overview documentation)</li>
<li>...</li>
</ul>
-->

For further information see:

* [AEM Gem session: OAuth](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem)
* [HAF Extensibility (GitHub)](https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html)   

* [Existing Assets REST API docs](../../assets/using/mac-api-assets.md)

<!--
Comment Type: remark
Last Modified By: Stefan Grimm (sgrimm)
Last Modified Date: 2018-11-28T11:13:23.000-0500
<p>Same as above: "HAF Extensibility" is in a repo on the internal GitHub, so we can't link to it.</p>
-->

