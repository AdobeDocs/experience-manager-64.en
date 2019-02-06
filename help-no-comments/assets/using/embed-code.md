---
title: Embedding the Video or Image Viewer on a Web Page
seo-title: Embedding the Video or Image Viewer on a Web Page
description: Learn how to embed dynamic media video or images on a web page
seo-description: Learn how to embed dynamic media video or images on a web page
uuid: dd5232ca-f270-4331-8c3d-3b46c82cf405
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: dae24d45-cb9c-4a28-9b45-2b9f8f2e205a
index: y
internal: n
snippet: y
---

# Embedding the Video or Image Viewer on a Web Page{#embedding-the-video-or-image-viewer-on-a-web-page}

Use the Embed Code feature when you want to play the video or view an asset embedded on a web page. You copy the embed code to the clipboard so you can paste it in your web pages. Editing of the code is not permitted in the Embed Code dialog box.

You embed URLs only if you are **not** using AEM as your WCM. If you are using AEM as your WCM, [you add the assets directly on your page.](../../assets/using/adding-dynamic-media-assets-to-pages.md)

See also [Linking URLs to your Web Application.](../../assets/using/linking-urls-to-yourwebapplication.md)

See also [Delivering Optimized Images for a Responsive Site.](../../assets/using/responsive-site.md)

>[!NOTE]
>
>The embed code is not available to copy until you have published the selected asset. In addition, you must also publish the viewer preset or image preset.
>
>See [Publishing Assets](../../assets/using/publishing-dynamicmedia-assets.md).
>
>See [Publishing Viewer Presets](../../assets/using/managing-viewer-presets.md#publishingviewerpresets).
>
>See [Publishing Image Presets](../../assets/using/managing-image-presets.md#publishingimagepresets).

To embed the video viewer or asset viewer on a web page:

1. Navigate to the *published *video or image asset whose embed code you want to copy.

   Remember that the embed code is only available to copy *after* you have first *published* the assets. In addition, the viewer preset or image preset must also be published.

   See [Publishing Assets.](../../assets/using/publishing-dynamicmedia-assets.md)

   See [Publishing Viewer Presets](../../assets/using/managing-viewer-presets.md#publishingviewerpresets).

   See [Publishing Image Presets](../../assets/using/managing-image-presets.md#publishingimagepresets).

1. In the left rail, select the drop-down menu and click or tap **Viewers**. 
1. In the left rail, click a viewer preset name. The viewer preset is applied to the asset.
1. Click **Embed**.
1. In the Embed Code dialog box, copy the entire code to the clipboard, and then click **Close**.
1. Paste the embed code into your web pages.

### Using HTTP/2 to deliver your Dynamic Media assets {#using-http-to-deliver-your-dynamic-media-assets}

HTTP/2 is the new, updated web protocol that improves the way browsers and servers communicate. It provides faster transfer of information and reduces the amount of processing power that is needed. Delivery of Dynamic Media assets can now be over HTTP/2 which provides better response and load times.

See [HTTP2 Delivery of Content](../../assets/using/http2.md) for complete details on getting started using HTTP/2 with your Dynamic Media account.
