---
title: Video renditions
seo-title: Video renditions
description: null
seo-description: null
uuid: e8c4a8a8-8643-422e-ad0a-d4a2b1d02148
acrolinxdate: 2019-01-12T17 36 17.881-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/video_renditions_krs_workflow_f3c2f2ccebf6138e_200_report.xml
acrolinxsentences: 17
acrolinxwords: 219
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 8697c604-3ce9-4e92-918b-22c58fff6fee
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Video renditions{#video-renditions}

<!--
Comment Type: remark
Last Modified By: (alvawb)
Last Modified Date: 2017-11-30T05:30:59.326-0500
<p>Move to dynamic media and merge with DM</p>
<p>Static renditions is Assets. DM renditions is DM. </p>
<p> </p>
<p>Not sure if this topic makes sense - it doesn't seem to entirely fit in the Video Profiles topic either.</p>
<p> </p>
-->

Adobe Experience Manager (AEM) Assets generates video renditions for video assets of various formats including OGG, FLV, and so on.

AEM Assets supports static and dynamic renditions (DM-encoded renditions) for media assets.

Static renditions are generated natively using FFMPEG (installed and available on the system path) and stored in the content repository.

The DM-encoded renditions are stored in the proxy server and served at runtime.

AEM assets provide playback support for these renditions on the client side.

To view the renditions of a particular video asset, open its asset page, and click/tap the GlobalNav icon. Then, choose **Renditions** from the list.

![](assets/chlimage_1-491.png)

The list of video renditions are displayed in the** Renditions** panel. 

![](assets/chlimage_1-492.png)

To configure the proxy server for DM-encoded renditions, [configure Dynamic Media Cloud services.](../../assets/using/config-dynamic.md)

To generate video renditions with desired parameters, [create a corresponding video profile](../../assets/using/video-profiles.md).

After you configure the proxy server and create video profiles, you can include this video preset in a processing profile and apply the processing profile to a folder.

>[!NOTE]
>
>Audio playback do not work for OGG and WAV files on Internet Explorer 11. An error "Invalid Source " shows up on the asset details page for assets with extension OGG or WAV.
>
>On MS Edge and iPad , OGG files do not play and raise an Unsupported format error.

