---
title: Text Overlay
seo-title: Text Overlay
description: Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image. Follow this page to learn more.
seo-description: Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image. Follow this page to learn more.
uuid: a39d33b2-a04b-46cd-bd3d-a4466ccf453a
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 4447b2fd-7ed5-4953-bff1-4215790b3fab
noindex: true
index: y
internal: n
snippet: y
---

# Text Overlay{#text-overlay}

This section covers the following topics:

* ** [Overview](../../screens/using/text-overlay.md#overview)**
* ** [Using Text Overlay](../../screens/using/text-overlay.md#usingtextoverlay)  
  **

    * ** [Prerequisites](../../screens/using/text-overlay.md#prerequisites)**
    * ** [Understanding Text Overlay Properties](../../screens/using/text-overlay.md#understandingtextoverlayproperties)  
      **

>[!CAUTION]
>
>The **Text Overlay** feature is only available, if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3.

## Overview {#overview}

Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image.

To learn how to create your own custom component, please refer to [**Extending an AEM Screens Component**](../../screens/using/extending-component-tutorial-develop.md) for more information.

This section only showcases how to use and leverage the poster component in an AEM Screens project and use it as text overlay in one of your sequence channels.

## Using Text Overlay {#using-text-overlay}

The following section describes the use of text overlay in an AEM Screens project.

### Prerequisites {#prerequisites}

Before you start implementing this functionality, please make sure you have set up a project as a prerequisite to start implementing text overlay. For example,

* Create an AEM Screens project (in this example, **TextOverlayDemo**)  

* Create a channel as **TextSample** under **Channels** folder

* Add content to your **TextSample** Channel

The following image shows the **TextOverlayDemo** project with **TextSample** channel in **Channels** folder.

![](assets/screen_shot_2018-12-16at75908pm.png)

1. Navigate to **TextOverlayDemo** --&gt; **Channels** --&gt; **TextSample** and click **Edit** from the action bar to open the editor.

   ![](assets/screen_shot_2018-12-16at80017pm.png)

1. Select the image and click **Configure** (wrench icon) to open the properties dialog box.

   ![](assets/screen_shot_2018-12-16at80221pm.png)

1. Select the **Text Overlay** option from the navigation bar of the dialog box, as shown in the figure below.

   ![](assets/screen_shot_2018-12-16at80424pm.png)

### Understanding Text Overlay Properties {#understanding-text-overlay-properties}

Using the Text Overlay properties, you can add text to any of the component in your Screens project. The following section provides an overview of the properties that are available in Text Overlay:

![](assets/text.gif)

You can add a text to the text box and add typographical emphasis such as bold, italics, underline, and so on.

**Color Variant** This option allows the text to be either Dark (text in black color) or Light (text in white color).

**Sizing & positioning** This option allows the user to align the text horizontally or vertically or additionally use fine-grained tools for text alignment.

>[!NOTE]
>
>To properly use fine-grained tools, be sure to identify the correct position in pixels using (px) as a suffix, for example 200px. The result of this expression will be 200 pixels from start point.

