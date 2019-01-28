---
title: Naming conventions for assets testing
seo-title: Naming conventions for assets
description: null
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository. However, Adobe Experience Manager imposes further conventions for the name of asset nodes.
uuid: c5e6dcda-41a0-4221-8c30-36b178d28e70
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 8e6e3391-230e-4419-a428-dc2a6b3d204e
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Naming conventions for assets testing{#naming-conventions-for-assets-testing}

Nodes in the repository are subject to naming conventions of the [Java Content Repository](../../developing/using/the-basics.md#javacontentrepository). However, Adobe Experience Manager imposes further conventions for the name of asset nodes.

### CLASSIC UI {#classic-ui}

The classic UI imposes tighter restrictions:

* Validates the asset name when an explicit node name when either:

    * an asset title is provided for conversion into the node name
    * an explicit node name is provided

* Valid characters (only these characters are actually valid when an asset is created from within the classic UI):

    * 'a' to 'z'
    * 'A' to 'Z'
    * '0' to '9'
    * _ (underscore)
    * - (dash/minus)

