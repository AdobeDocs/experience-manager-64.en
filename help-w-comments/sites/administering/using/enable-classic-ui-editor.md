---
title: Editor
seo-title: Editor
description: Learn how to switch back to the Classic UI Editor.
seo-description: Learn how to switch back to the Classic UI Editor.
uuid: 6ff7bf98-42df-4d26-8493-a9637e795282
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 809ff403-4105-4f75-87f8-9214f1828670
index: y
internal: n
snippet: y
---

# Editor{#editor}

By default, the ability to switch to the classic UI from the editor has been disabled.

![](assets/chlimage_1-11.png)

To re-enable the option **Open in Classic UI** in the **Page Information** menu, follow these steps.

1. Using CRXDE Lite, find the following node:

   For example

1. Using the **Overlay Node** option, create an overlay under `/apps` as follows:
1. Add the following multi-value text property to the overlaid node:
1. The **Open in Classic UI** option is again available in the **Page Information** menu when editing pages.

   ![](assets/chlimage_1-12.png)

