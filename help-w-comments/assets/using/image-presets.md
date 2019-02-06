---
title: Applying Image Presets
seo-title: Applying Image Presets
description: Learn how to apply image presets in dynamic media
seo-description: Learn how to apply image presets in dynamic media
uuid: bff19a31-0099-4640-be51-1638602c4bcb
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 4e0d12b1-d9f2-4dd5-abf5-d6d0526a2d01
index: y
internal: n
snippet: y
---

# Applying Image Presets{#applying-image-presets}

Image Presets enable assets to dynamically deliver images at different sizes, in different formats, or with other image properties there are generated dynamically. You can choose a preset when you export images, which also reformats images to the specifications that your administrator has specified.

In addition, you can choose an image preset that is responsive (designated by the **RESS** button after you select it).

This section describes how to use image presets. [Administrators can create and configure image presets](../../assets/using/managing-image-presets.md).

>[!NOTE]
>
>Smart imaging works with your existing image presets and uses intelligence at the last millisecond of delivery to further reduce image file size based on browser or network connection speed. See [Smart Imaging](../../assets/using/imaging-faq.md) for more information.

You can apply an image preset to an image anytime you preview it. To apply an image preset:

1. Open the asset and in the left rail, click or tap the drop-down menu and click or tap **Renditions**.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Static renditions appear in the top half of the the pane. Dynamic renditions appear in the lower half. With dynamic renditions only, you can use the URL to display the image. The **URL** button only appears if you select a dynamic rendition. The **RESS** button only appears if you select a responsive image preset.
   >    
   >    * The system shows numerous renditions when you select **Renditions** in an asset's Detail view. You can increase the number of presets seen. See [Increasing the number of image presets that display](../../assets/using/managing-image-presets.md#increasingthenumberofimagepresetsthatdisplay).
   >    
   >    
   >

   ![](assets/chlimage_1-161.png)

1. Do any of the following:

    * Select a dynamic rendition to preview the image preset.
    * Click **URL**, **Embed**, or **RESS** to display the pop-up.

   <!--
   Comment Type: annotation
   Last Modified By: rbrough
   Last Modified Date: 2018-12-10T16:30:35.303-0500
   This is hard to read. Maybe instead say something like: Click on a dynamic rendition to preview the image preset. Click on the URL, Embed, or RESS buttons to display the pop-up. RB: Fixed.
   -->

   >[!NOTE]
   >
   >If the asset *and* the image preset have not yet been published, the **URL** button (or **URL** and **RESS** buttons, if applicable) are not available.
   >
   >
   >Note also that image presets are automatically published on a Dynamic Media S7 server.

