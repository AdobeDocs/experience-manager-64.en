---
title: Camera Raw support
description: Learn how to enable Camera Raw support in Adobe Experience Manager (AEM) Assets.
contentOwner: AG
---

# Camera Raw support {#camera-raw-support}

The Camera Raw package enables support for various raw file formats, such as .CR2, .NEF, .RAF, and so on. The Camera Raw functionality is supported in Adobe Experience Manager (AEM) Assets to render your assets in JPEG format. The supported pacakge is available at [https://blogs.adobe.com/lightroomjournal/2017/03/acr-9-9-now-available.html](https://blogs.adobe.com/lightroomjournal/2017/03/acr-9-9-now-available.html).

To enable Camera Raw support in Assets, follow these steps:

1. Based on the AEM version and the operating system, download the appropriate Camera Raw package and install it:

 | Supported Platforms | Package Share Link | Supported AEM Versions |
|---|---|---|
| Windows 64 Bit, Mac OS, RHEL 7.x | 1.3.16 | 6.3, 6.4 |
| Windows 64 Bit, Mac OS, RHEL 7.x | 1.2.8 | 6.2 |
| Windows 64 Bit, Mac OS, RHEL 7.x | 1.1.22 | 6.1 |

1. Access `https://[AEM server]:[Port]/workflow`. Open the **[!UICONTROL DAM Update Asset]** workflow.

1. Open the **[!UICONTROL Process Thumbnails]** step.  

1. Provide the following configuration in the **[!UICONTROL Thumbnails]** tab:

    * Thumbnails: `140:100:false, 48:48:false, 319:319:false`
    * Skip Mime Types: `skip:image/dng, skip:image/x-raw-(.*)`

   ![chlimage_1-334](assets/chlimage_1-334.png)

1. In the **[!UICONTROL Web Enabled Image]** tab, specify the following:

    * Skip List: `audio/mpeg, video/(.*), image/dng, image/x-raw-(.*)`

   ![chlimage_1-335](assets/chlimage_1-335.png)

1. From SideKick, add the **[!UICONTROL Camera Raw/DNG Handler]** step below the **[!UICONTROL Thumbnail creation]** step.
1. In the **[!UICONTROL Camera Raw/DNG Handler]** step, provide the following configuration in the **[!UICONTROL Arguments]** tab:

   Mime Types: `image/dng, image/x-raw-(.*)`

   Command:

    * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.web.1280.1280.jpeg 1280 1280`
    * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.319.319.jpeg 319 319`
    * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.140.100.jpeg 140 100`
    * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.48.48.jpeg 48 48`

   ![chlimage_1-336](assets/chlimage_1-336.png)

1. Click **[!UICONTROL Save]**.

   You can now import camera raw files into AEM Assets. After you install the Camera RAW package and configure the required workflow, **[!UICONTROL Image Adjust]** option appears in the list of panes.

   ![chlimage_1-337](assets/chlimage_1-337.png)

   Click **[!UICONTROL Image Adjust]** from the list and use the options in the **[!UICONTROL Image Adjust]** pane to make lightweight edits to your image.

   ![chlimage_1-338](assets/chlimage_1-338.png)

After saving the edits to a Camera Raw image, a new rendition `AdjustedPreview.jpg` is generated for the image. For other image types except Camera Raw, the changes are reflected in all the renditions.

## Best practices, known issues, and limitations {#best-practices}

The functionality has the following limitations:

* The functionality supports only JPEG renditions. It is supported on Windows 64 Bit, Mac OS, and RHEL 7.x.
* Metadata writeback is not supported for RAW and DNG formats.
* The Camera Raw library has limitations around the total pixels it can process at a time. Currently, it can process a maximum of 1073741824 (1024 x 1024 x 1024) pixels.
