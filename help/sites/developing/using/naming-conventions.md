---
title: Naming Conventions
seo-title: Naming Conventions
description: Nodes in the repository are subject to naming conventions of the Java Content Repository
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository
uuid: 3fd92245-e3e0-4ac4-8fcb-3f625cee957b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 0902f4e5-98ec-47cb-96b7-8ad8c2a93242
index: y
internal: n
snippet: y
---

# Naming Conventions{#naming-conventions}

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

The standard, touch-enabled UI:

* Validates the name according to the restrictions imposed by PageManager when either:

    * a page title is provided for conversion into the node name
    * an explicit node name is provided

### Classic UI {#classic-ui}

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

