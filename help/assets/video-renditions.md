---
title: Video renditions
description: Video renditions
contentOwner: AG
feature: Video,Renditions
role: User
exl-id: 9fc93034-e83a-42b5-901d-7867b4a850a8
---
# Video renditions {#video-renditions}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets generates video renditions for video assets of various formats including OGG, FLV, and so on.

AEM Assets supports static and dynamic renditions (DM-encoded renditions) for media assets.

Static renditions are generated natively using FFMPEG (installed and available on the system path) and stored in the content repository.

The DM-encoded renditions are stored in the proxy server and served at runtime.

AEM assets provide playback support for these renditions on the client side.

To view the renditions of a particular video asset, open its asset page, and tap the Global Navigation icon. Then, choose **[!UICONTROL Renditions]** from the list.

![chlimage_1-478](assets/chlimage_1-478.png)

The list of video renditions are displayed in the **[!UICONTROL Renditions]** panel. 

![chlimage_1-479](assets/chlimage_1-479.png)

To configure the proxy server for DM-encoded renditions, [configure Dynamic Media Cloud services.](config-dynamic.md)

To generate video renditions with desired parameters, [create a corresponding video profile](video-profiles.md).

After you configure the proxy server and create video profiles, you can include this video preset in a processing profile and apply the processing profile to a folder.

>[!NOTE]
>
>Audio playback do not work for OGG and WAV files on Internet Explorer 11. An error "Invalid Source " shows up on the asset details page for assets with extension OGG or WAV.
>
>On MS Edge and iPad , OGG files do not play and raise an Unsupported format error.
