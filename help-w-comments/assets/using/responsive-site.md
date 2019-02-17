---
title: Delivering Optimized Images for a Responsive Site
seo-title: Delivering Optimized Images for a Responsive Site
description: How to use the responsive code feature to deliver optimized images
seo-description: How to use the responsive code feature to deliver optimized images
uuid: 69874b76-d41d-4b76-985c-d1f9b4080f69
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 85f21d01-177e-4c38-a628-71e20cba8470
index: y
internal: n
snippet: y
---

# Delivering Optimized Images for a Responsive Site{#delivering-optimized-images-for-a-responsive-site}

Use the Responsive code feature when you want to share the code for responsive serving with your web developer. You copy the responsive (RESS) code to the clipboard so you can share it with the web developer.

This feature makes sense to use if your website is on a third-party WCM. However, if your website is on AEM instead, an offsite image server renders the image and supplies it to the web page.

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2019-01-10T16:15:29.968-0500
to me, "directly through AEM" sounds as though AEM is rendering the responsive image an off-site image server is rendering the image and supplying it to the Web page RB: Fixed.
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-07T20:17:31.057-0400
General note: I checked that links worked but not the content of the links itself
-->

See also [Embedding the Video Viewer on a Web Page.](../../assets/using/embed-code.md)

See also [Linking URLs to your Web Application.](../../assets/using/linking-urls-to-yourwebapplication.md)

To deliver optimized images for a responsive site:

1. Navigate to the image you want supply responsive code for and in the drop-down menu, tap or click **Renditions**.

   ![](assets/chlimage_1-417.png)

1. Select a responsive image preset. The **URL** and **RESS** buttons appear.

   <!--
   Comment Type: annotation
   Last Modified By: rbrough
   Last Modified Date: 2019-01-10T16:21:42.738-0500
   The URL button was removed but it should be brought back for parity reasons RB: Is it being brought back? Check when writing next version.
   -->

   ![](assets/chlimage_1-418.png)

   >[!NOTE]
   >
   >The selected asset *and* the selected image preset or viewer preset must be published to make the **URL** or **RESS** buttons available.
   >
   >
   >(Note that Dynamic Media - Hybrid mode requires you to publish image presets; Dynamic Media - Scene7 mode automatically publishes image presets.

1. Tap or click **RESS**. The responsive code displays.

   <!--
   Comment Type: annotation
   Last Modified By: rbrough
   Last Modified Date: 2019-01-10T16:20:38.932-0500
   Maybe update the screen shot to include the break points that are mentioned in Step #5 below RB: Can be fixed at will.
   -->

   ![](assets/chlimage_1-419.png)

1. Select and copy the text and paste it in your web site to access the responsive asset.
1. Edit the default breakpoints in the embed code to match those of the responsive web site directly in the code. In addition, test the different image resolutions being served at different page breakpoints.

### Using HTTP/2 to delivery your Dynamic Media assets {#using-http-to-delivery-your-dynamic-media-assets}

HTTP/2 is the new, updated web protocol that improves the way browsers and servers communicate. It provides faster transfer of information and reduces the amount of processing power that is needed. Delivery of Dynamic Media assets is supported using HTTP/2 which provides better response and load times.

See [HTTP2 Delivery of Content](../../assets/using/http2.md) for complete details on getting started using HTTP/2 with your Dynamic Media account.

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2019-01-10T16:20:14.027-0500
change "can now be over" to "is supported using" RB: Fixed.
-->

