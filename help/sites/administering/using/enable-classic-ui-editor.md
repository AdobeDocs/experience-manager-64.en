---
title: Editor
seo-title: Editor
description: Learn how to switch back to the Classic UI Editor.
seo-description: Learn how to switch back to the Classic UI Editor.
uuid: 5d26358c-ceb0-4adf-bfb2-25ae177ef9d6
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: def35545-7ca9-448c-b4d1-38403cd090d8
---

# Editor{#editor}

By default, the ability to switch to the classic UI from the editor has been disabled.

![](assets/chlimage_1-9.png)

To re-enable the option **Open in Classic UI** in the **Page Information** menu, follow these steps.

1. Using CRXDE Lite, find the following node:

   `/libs/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

   For example

   ` [http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui](http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui)`

1. Using the **Overlay Node** option, create an overlay under `/apps` as follows:

   `/apps/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

1. Add the following multi-value text property to the overlaid node:

   `sling:hideProperties = ["granite:hidden"]`

1. The **Open in Classic UI** option is again available in the **Page Information** menu when editing pages.

   ![](assets/chlimage_1-10.png)

