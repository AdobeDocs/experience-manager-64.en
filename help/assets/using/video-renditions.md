---
title: Video renditions
seo-title: Video renditions
description: null
seo-description: null
uuid: ed268386-33b5-4617-b939-25c715591964
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: f148da7e-8851-4b60-96ed-938e64f01fd5
index: y
internal: n
snippet: y
---

# Video renditions{#video-renditions}

Adobe Experience Manager (AEM) Assets generates video renditions for video assets of various formats including OGG, FLV, and so on.

AEM Assets supports static and dynamic renditions (DM-encoded renditions) for media assets.

Static renditions are generated natively using FFMPEG (installed and available on the system path) and stored in the content repository.

The DM-encoded renditions are stored in the proxy server and served at runtime.

AEM assets provide playback support for these renditions on the client side.

To view the renditions of a particular video asset, open its asset page, and click/tap the GlobalNav icon. Then, choose **Renditions** from the list.

![](assets/chlimage_1-479.png)

The list of video renditions are displayed in the** Renditions** panel. 

![](assets/chlimage_1-480.png)

To configure the proxy server for DM-encoded renditions, [configure Dynamic Media Cloud services.](../../assets/using/config-dynamic.md)

To generate video renditions with desired parameters, [create a corresponding video profile](../../assets/using/video-profiles.md).

After you configure the proxy server and create video profiles, you can include this video preset in a processing profile and apply the processing profile to a folder.

>[!NOTE]
>
>Audio playback do not work for OGG and WAV files on Internet Explorer 11. An error "Invalid Source " shows up on the asset details page for assets with extension OGG or WAV.
>
>On MS Edge and iPad , OGG files do not play and raise an Unsupported format error.

