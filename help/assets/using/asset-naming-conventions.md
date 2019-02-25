---
title: Naming conventions for assets
seo-title: Naming conventions for assets
description: Learn about the naming conventions for assets.
seo-description: Learn about the naming conventions for assets.
uuid: fc084f1d-df1a-4d9e-88c0-bd9544dd7a38
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
discoiquuid: 83975e4c-11c8-49dd-9a37-6aca76cd8dcf
---

# Naming conventions for assets{#naming-conventions-for-assets}

Nodes in the repository are subject to naming conventions of the [Java Content Repository](../../sites/developing/using/the-basics.md#javacontentrepository). However, Adobe Experience Manager imposes further conventions for the name of asset nodes.

## TOUCH-OPTIMIZED UI {#touch-optimized-ui}

The touch-optimized UI:

* Validates the name according to the restrictions:

  * an asset title is provided for conversion into the node name
  * an explicit node name is provided

AEM Assets does not let you specify "subassets" as the name of an asset folder. It is a keyword reserved for naming all CRXDe nodes that include subassets for compound assets. 
