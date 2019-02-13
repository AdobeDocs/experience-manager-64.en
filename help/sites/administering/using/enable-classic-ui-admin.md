---
title: Admin Consoles
seo-title: Admin Consoles
description: Lear how to use the Admin Consoles available in AEM.
seo-description: Lear how to use the Admin Consoles available in AEM.
uuid: 1529aade-4142-4068-ac54-1f5c3e48c886
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: a2861546-587a-4797-abc0-c62a5bbf1f45
index: y
internal: n
snippet: y
---

# Admin Consoles{#admin-consoles}

By default, the ability to switch to the classic UI via the admin consoles has been disabled. Therefore the pop-up icons that was seen when mousing over certain console icons, allowing access to classic UI, are no longer displayed.

![](assets/screen_shot_2018-03-23at111956.png)

Every console that has a Classic UI version in `/libs/cq/core/content/nav` can be re-enabled individually so that the **Classic UI** option once again pops up over the console icon when it is moused over.

In this example, we are re-enabling the Classic UI for the Sites console.

1. Using CRXDE Lite, find the node corresponding the the admin console for which you want to re-enable Classic UI. They are found under:

   For example

1. Select the node corresponding to the console for which you want to re-enable Classic UI. For our example, we will re-enable classic UI for the Sites console.
1. Using the **Overlay Node** option, create an overlay for the selected node under `/apps` as follows:
1. Add the following boolean property to the overlaid node:
1. The **Classic UI** option is again available as a popover option in the admin console.

   ![](assets/screen_shot_2018-03-23at111924.png)

Repeat these steps for every console for which you wish to re-enable access to the Classic UI version.
