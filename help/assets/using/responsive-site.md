---
title: Delivering Optimized Images for a Responsive Site
seo-title: Delivering Optimized Images for a Responsive Site
description: How to use the responsive code feature to deliver optimized images
seo-description: How to use the responsive code feature to deliver optimized images
uuid: 7c6baef5-7513-4644-94ed-2383e8724c17
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 5edcc765-c374-4368-a0d9-e02a713a24f2
index: y
internal: n
snippet: y
---

# Delivering Optimized Images for a Responsive Site{#delivering-optimized-images-for-a-responsive-site}

Use the Responsive code feature when you want to share the code for responsive serving with your web developer. You copy the responsive (RESS) code to the clipboard so you can share it with the web developer.

This feature makes sense to use if your website is on a third-party WCM. However, if your website is on AEM instead, an offsite image server renders the image and supplies it to the web page.

See also [Embedding the Video Viewer on a Web Page.](../../assets/using/embed-code.md)

See also [Linking URLs to your Web Application.](../../assets/using/linking-urls-to-yourwebapplication.md)

To deliver optimized images for a responsive site:

1. Navigate to the image you want supply responsive code for and in the drop-down menu, tap or click **Renditions**.

   ![](assets/chlimage_1-408.png)

1. Select a responsive image preset. The **URL** and **RESS** buttons appear. 

   ![](assets/chlimage_1-409.png)

   >[!NOTE]
   >
   >The selected asset *and* the selected image preset or viewer preset must be published to make the **URL** or **RESS** buttons available.
   >
   >
   >(Note that Dynamic Media - Hybrid mode requires you to publish image presets; Dynamic Media - Scene7 mode automatically publishes image presets.

1. Tap or click **RESS**. The responsive code displays.

   ![](assets/chlimage_1-410.png)

1. Select and copy the text and paste it in your web site to access the responsive asset.
1. Edit the default breakpoints in the embed code to match those of the responsive web site directly in the code. In addition, test the different image resolutions being served at different page breakpoints.

### Using HTTP/2 to delivery your Dynamic Media assets {#using-http-to-delivery-your-dynamic-media-assets}

HTTP/2 is the new, updated web protocol that improves the way browsers and servers communicate. It provides faster transfer of information and reduces the amount of processing power that is needed. Delivery of Dynamic Media assets is supported using HTTP/2 which provides better response and load times.

See [HTTP2 Delivery of Content](../../assets/using/http2.md) for complete details on getting started using HTTP/2 with your Dynamic Media account.
