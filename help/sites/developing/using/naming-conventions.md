---
title: Naming Conventions
seo-title: Naming Conventions
description: null
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository
uuid: 1c4dbd0d-ba84-4c64-9562-bed20a20f4e8
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: c69f9ab7-4641-4517-aab7-55dc97e6af96
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Naming Conventions{#naming-conventions}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:25:10.680-0500
<p>do we need info for assets - and if so is this the appropriate location (and if not, where is)?</p>
-->

Nodes in the repository are subject to naming conventions of the [Java Content Repository](../../../sites/developing/using/the-basics.md#javacontentrepository). However AEM imposes further conventions for the name of page nodes.

## Naming Conventions for Pages {#naming-conventions-for-pages}

These naming conventions are implemented at various levels:

* JcrUtil: the AEM implementation of the [JCR utilities](#jcrutilities).
* PageManager: the [Page Manager](#pagemanager) provides methods for page level operations.
* According to the UI being used:

    * [Standard, touch-enabled UI](#standardui)  
    
    * [Classic UI](#classicui)

### JCR Utilities {#jcr-utilities}

[JcrUtil](/sites/developing/using/reference-materials/javadoc/index.html?com/day/cq/commons/jcr/JcrUtil) is the AEM implementation of the JCR utilities. Of particular interest to validating names are the character mappings that it controls and the following validations:

* `isValidName`

    * Checks if the name is not empty and contains only valid chars.
    * Can be used to check whether a proposed name is valid.

* `createValidName`

    * This creates a valid label out of an arbitrary string.  
    * It can be used to create a name from a title.

### Page Manager {#page-manager}

[PageManager](/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager) provides methods for page level operations, based on [JCRUtil](#jcrutilities).

### Standard UI {#standard-ui}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:25:10.808-0500
<p>Rofe&gt;&gt;&gt; I would really _not_ mention the ampersand here, because the UI will run havoc if it is being used. Imho allowing this character (of all other special characters) is a bug that needs to be fixed rather than documented.</p>
<p>"The touch-optimized UI allows the use of ampersand ( & ) in a node name. However pages with ampersand in the name cannot be edited (in neither touch-optimized nor classic)."</p>
-->

The standard, touch-enabled UI:

* Validates the name according to the restrictions imposed by PageManager when either:

    * a page title is provided for conversion into the node name
    * an explicit node name is provided

### Classic UI {#classic-ui}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:25:10.849-0500
<p>just to check what is meant by "dash/minus":</p>
<ul>
<li>all dashes and hyphen characters</li>
<li>dash and the hyphen-minus char</li>
<li>or just the hyphen-minus char (instead of dash-minus)</li>
<li>http://www.fileformat.info/info/unicode/char/2d/index.htm</li>
<li>http://www.fileformat.info/info/unicode/char/search.htm?q=dash&preview=entity</li>
<li>http://www.fileformat.info/info/unicode/char/search.htm?q=minus&preview=entity</li>
</ul>
-->

The classic UI imposes tighter restrictions:

* Validates the name when an explicit node name when either:

    * a page title is provided for conversion into the node name
    * an explicit node name is provided

* Valid characters (only these characters are actually valid when a page is created from within the classic UI, even though `PageManagerImpl` would allow additional characters):

    * 'a' to 'z'
    * 'A' to 'Z'
    * '0' to '9'
    * _ (underscore)
    * - (dash/minus)

<!--
Comment Type: draft

<h3>Naming Conventions for Assets</h3>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:25:10.891-0500
<p>apparently the rules are much more open for assets - need confirmation of what - or a link</p>
<p>Rofe&gt;&gt;&gt; Asset names allow all sorts of special characters, except characters forbidden by JCR name standard</p>
-->

