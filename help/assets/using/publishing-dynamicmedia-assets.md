---
title: Publishing Dynamic Media Assets
seo-title: Publishing Dynamic Media Assets
description: null
seo-description: How to publish dynamic media assets
uuid: aacfac0d-f75e-47de-a5eb-276c78a13a9a
acrolinxdate: 2019-01-12T17 34 20.228-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/publishing_dynamicmedia_assets_krs_workflow_f3c2f2ccebf6138e_183_report.xml
acrolinxsentences: 29
acrolinxwords: 406
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: ef2cf8af-9f11-4269-b1b4-7d96e4699e9a
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Publishing Dynamic Media Assets{#publishing-dynamic-media-assets}

You publish your dynamic media assets by selecting the assets and tapping **Publish**. After your dynamic media assets are published, they are available to you for including in a web page via URL or via embedding.

You can also instantly publish assets that you upload--without any user intervention. See [Configuring Dynamic Media - Scene7 mode](../../assets/using/config-dms7.md).

In the Card View, a small globe icon appears directly below an asset's name to indicate that it is published. In the List View, a **Published** column indicates which assets are published or which are not.

>[!NOTE]
>
>If an asset is already published, then you use AEM to move the asset to another folder, and re-publish from its new location, the original published asset location is still available, along with the newly re-published asset. The original published asset, however, is "lost" to AEM and cannot be unpublished. Therefore, as a best practice, unpublish assets first before you move them to a different folder.

If you intend to publish video assets immediately after encoding them, make sure encoding is completely done. When videos are still being encoded, the system lets you know that a video processing workflow is in progress. When video encoding is done, you should be able to preview the video renditions. At that point, it is safe for you to publish the videos without incurring any publishing errors.

See also [Linking URLs to your Web Application](../../assets/using/linking-urls-to-yourwebapplication.md).

See also [Embedding the Video Viewer on a Web Page.](../../assets/using/embed-code.md)

>[!NOTE]
>
>* Assets must be published in order to use the URL. If the assets are not published, copying and pasting the URL into a web browser will not work.
>* Image presets and viewer presets must be activated and published for live delivery.
>

For detailed information on publishing a set or asset, see [Publishing Assets.](../../assets/using/managing-assets-touch-ui.md)

### HTTP/2 delivery of Dynamic Media assets {#http-delivery-of-dynamic-media-assets}

AEM now supports the delivery of all Dynamic Media content (images and video) over HTTP/2. That is, a published URL or embed code for the image or video is available to be integrated with any application that accepts a hosted asset. That published asset is then delivered by way of HTTP/2 protocol. This method of delivery improves the way browsers and servers communicate, allowing for better response and load times of all your Dynamic Media assets.

See [HTTP/2 Delivery of Content Frequently Asked Questions](../../sites/administering/using/scene7-http2faq.md) to learn more.
