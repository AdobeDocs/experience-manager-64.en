---
title: Naming conventions for assets
seo-title: Naming conventions for assets
description: Learn about the naming conventions for assets.
seo-description: Learn about the naming conventions for assets.
uuid: fa5f48d0-9cff-4495-9a86-4b55cc910d0e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
discoiquuid: 1bd0470e-0bf8-4416-aa85-10a99f7fb6c8
index: y
internal: n
snippet: y
---

# Naming conventions for assets{#naming-conventions-for-assets}

Nodes in the repository are subject to naming conventions of the [Java Content Repository](../../sites/developing/using/the-basics.md#javacontentrepository). However, Adobe Experience Manager imposes further conventions for the name of asset nodes.

### TOUCH-OPTIMIZED UI {#touch-optimized-ui}

The touch-optimized UI:

* Validates the name according to the restrictions:

    * an asset title is provided for conversion into the node name
    * an explicit node name is provided

AEM Assets does not let you specify "subassets" as the name of an asset folder. It is a keyword reserved for naming all CRXDe nodes that include subassets for compound assets. 
