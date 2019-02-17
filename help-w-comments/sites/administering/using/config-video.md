---
title: Configure the Video component
seo-title: Configure the Video component
description: Learn how to configure the Video Component.
seo-description: Learn how to configure the Video Component.
uuid: 19adbdb8-59f9-4220-9c57-688ee2f5c45b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 6b6dfe30-670d-4bf6-9dc0-6414e0c520c5
index: y
internal: n
snippet: y
---

# Configure the Video component{#configure-the-video-component}

The [Video component](../../../sites/authoring/using/default-components-foundation.md#video) allows you to place a predefined, out-of-the-box video element on your page.

For proper transcoding to occur, your administrator must [Install FFmpeg](#installingffmpeg) separately. They can also [Configure your Video Profiles](#configuringvideoprofiles) for use with HTML5 elements.

## Configure video profiles {#configure-video-profiles}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T04:59:43.351-0500
<p>use case?</p>
-->

You may want to define video profiles to use for HTML5 elements. Those chosen here are used in order. To access, use [Design Mode](../../../sites/authoring/using/default-components-designmode.md) (Classic UI only) and select the **Profiles** tab:

![](assets/chlimage_1-385.png)

You can also configure the design of the video components and parameters for Playback, Flash, and Advanced.

## Install FFmpeg {#install-ffmpeg}

The Video Component relies on the third-party open-source product FFmpeg for proper transcoding of videos that can be downloaded from [http://ffmpeg.org/](http://ffmpeg.org/). After you install FFmpeg, you must configure AEM to use a specific audio codec and specific runtime options.

To install FFmpeg for your platform:

* **On Windows:**

    1. Download the compiled binary as `ffmpeg.zip`  
    
    1. Unzip to a folder.  
    1. Set the system environment variable `PATH` to `<*your-ffmpeg-locatio*n>\bin`  
    
    1. Restart AEM.

* **On Mac OS X:**

    1. Install Xcode ([http://developer.apple.com/technologies/tools/xcode.html](http://developer.apple.com/technologies/tools/xcode.html))
    1. Install XQuartz/X11.
    1. Install MacPorts ([http://www.macports.org/](http://www.macports.org/))
    1. In the console run the following command and follow the instructions:  
       `sudo port install ffmpeg`   
       `FFmpeg` must be in `PATH` so AEM can pick it up via command line.

* **Using the precompiled version for OS X 10.6:**

    1. Download the precompiled version.
    1. Extract it to the `/usr/local` directory.
    1. From terminal, execute:  
       `sudo ln -s /usr/local/Cellar/ffmpeg/0.6/bin/ffmpeg /usr/bin/ffmpeg`

To configure AEM, use the following steps:

1. Open CRXDE Lite in your web browser. ([http://localhost:4502/crx/de](http://localhost:4502/crx/de))
1. Select the `/libs/settings/dam/video/format_aac/jcr:content` node and ensure that the node properties are as follows:

    * audioCodec:     
    
      ```    
             aac
      ```    
    
    * customArgs:     
    
      ```    
             -flags +loop -me_method umh -g 250 -qcomp 0.6 -qmin 10 -qmax 51 -qdiff 4 -bf 16 -b_strategy 1 -i_qfactor 0.71 -cmp chroma -subq 8 -me_range 16 -coder 1 -sc_threshold 40 -b-pyramid normal -wpredp 2 -mixed-refs 1 -8x8dct 1 -fast-pskip 1 -keyint_min 25 -refs 4 -trellis 1 -direct-pred 3 -partitions i8x8,i4x4,p8x8,b8x8
      ```

1. To customize the configuration, create an overlay in `/apps/settings/` node and move the same structure under `/conf/global/settings/` node. It cannot be edited in `/libs` node. For example, to overlay path `/libs/settings/dam/video/fullhd-bp`, create it at `/conf/global/settings/dam/video/fullhd-bp`.

   >[!NOTE]
   >
   >Overlay and edit the entire profile-node and not just the property that needs modification. Such resources are not resolved via SlingResourceMerger.

1. If you changed either of the properties, click **Save All**.

>[!NOTE]
>
>Out-of-the-box (OOTB) workflow models are not preserved when you upgrade your AEM instance. Adobe recommends that you copy OOTB workflow models before modifying them. For example, copy the OOTB DAM Update Asset model before modifying the FFmpeg Transcoding step in the DAM Update Asset model to pick video-profile names that existed before the upgrade. Then, you can overlay the /apps node to let AEM retrieve the custom changes to the OOTB model.

