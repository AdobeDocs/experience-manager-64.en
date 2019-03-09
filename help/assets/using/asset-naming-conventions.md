---
title: Naming conventions for assets
seo-title: Naming conventions for assets
description: Learn about the naming conventions for assets.
seo-description: Learn about the naming conventions for assets.
uuid: 3c4def6e-7e5d-4594-b268-f08c94edb212
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
discoiquuid: 01cd1fbe-5cf2-44c3-bde9-f8c3553b211b
---

# Naming conventions for assets{#naming-conventions-for-assets}

Nodes in the repository are subject to naming conventions of the [Java Content Repository](../../sites/developing/using/the-basics.md#java-content-repository). However, Adobe Experience Manager imposes further conventions for the name of asset nodes.

### TOUCH-OPTIMIZED UI {#touch-optimized-ui}

The touch-optimized UI:

* Validates the name according to the restrictions:

    * an asset title is provided for conversion into the node name
    * an explicit node name is provided

AEM Assets does not let you specify "subassets" as the name of an asset folder. It is a keyword reserved for naming all CRXDe nodes that include subassets for compound assets. 
