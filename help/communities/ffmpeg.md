---
title: FFmpeg for Communities
seo-title: FFmpeg for Communities
description: How to install and configure FFmpeg for Communities
seo-description: How to install and configure FFmpeg for Communities
uuid: ef2f821c-70e9-4889-a8d7-a93b10a1d428
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 739ec991-552b-42cd-85cd-984d1c9fe8fd
role: Admin
exl-id: 9ed54ee3-3509-4a43-a710-90f4543ccaf3
---
# FFmpeg for Communities {#ffmpeg-for-communities}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

## Overview {#overview}

FFmpeg is a solution for converting and streaming audio and video and, when installed, is used for proper transcoding of [video assets](../../help/sites-authoring/default-components-foundation.md#video) as well as for AEM Communities' enablement feature.

FFmpeg is used in the author environment to obtain metadata for uploaded enablement resources as well as generate a thumbnail to display when listing the enablement resource.

## Installing FFmpeg {#installing-ffmpeg}

FFmpeg should be installed on the server(s) hosting the AEM *author* instance(s).

1. Go to [https://www.ffmpeg.org](https://www.ffmpeg.org/) 
1. Download the latest version of FFmpeg for your specific environment (Macintosh, Windows, or Linux)

    * it is important to keep FFmpeg up-to-date due to security vulnerabilities in older versions

1. Install FFmpeg following instructions for the OS.

1. Make sure the FFmpeg executable is set in your system path.  

   You should be able to run FFmpeg from any directory in your system.

    * for example, `ffmpeg -version`

## Configure FFmpeg Transcoding Service {#configure-ffmpeg-transcoding-service}

By default, when FFmpeg is installed, multiple renditions are configured (transcodings) as per the DAM Update Asset workflow definition.

As the transcodings are CPU intensive, it is recommended to modify the list of target renditions. In most cases, transcoding is not necessary.

To modify the DAM Update Asset workflow, and in this example, to turn off transcoding:

* Sign into the author instance with administrative privileges
* From global navigation: **[!UICONTROL Tools > Workflow > Models]**
* Locate **[!UICONTROL DAM Update Asset]**
* Double-click to open the workflow for edit in the Classic UI 

  Resulting location: [http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html](http://localhost:4502/cf#/etc/workflow/models/dam/update_asset.html)

* Double-click the **[!UICONTROL FFmpeg transcoding]** step to access the Step Properties dialog
* Under the **[!UICONTROL Process]** tab:

    * **[!UICONTROL Arugments]**: Clear all entries to disable transcoding Default values: `profile:firefoxhq,profile:hq,profile:flv,profile:iehq`

![chlimage_1-372](assets/chlimage_1-372.png)

* Select **[!UICONTROL OK]** to close the `Step Properties` dialog

* Select **[!UICONTROL Save]** to save the `DAM Update Asset` workflow  

  (upper left corner)
