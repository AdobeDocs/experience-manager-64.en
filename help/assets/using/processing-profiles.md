---
title: Profiles for Processing Metadata, Images, and Videos
seo-title: Profiles for Processing Metadata, Images, and Videos
description: null
seo-description: A profile a set of rules around the options to be applied to assets uploaded to a folder. Specify what metadata profile and video encoding profile to apply to video assets that you upload. For image assets, you can also specify what imaging profile to apply to image assets to have them properly cropped.
uuid: 04e1f923-bc81-4661-ae2f-24089d3ae9fb
acrolinxdate: 2019-01-12T17 34 24.995-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: green
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/processing_profiles_krs_workflow_f3c2f2ccebf6138e_185_report.xml
acrolinxsentences: 17
acrolinxwords: 298
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: f45c830b-d6fa-4881-ab5f-4ca62ca70495
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Profiles for Processing Metadata, Images, and Videos{#profiles-for-processing-metadata-images-and-videos}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-77F410094CD97C4F0A746C1B@AdobeID)
Last Modified Date: 2017-11-30T11:33:27.959-0500
<p>Page inheritance canceled</p>
-->

A profile is a recipe for what options to apply to assets that get uploaded to a folder. For example, you can specify what metadata profile and video encoding profile to apply to video assets that you upload. Or, what imaging profile to apply to image assets to have them properly cropped.

Those rules can include adding metadata, smart cropping of images, or establishing video encoding profiles. In AEM, you can create three types of profiles, which are covered in detail at the following links:

* [Metadata profiles](../../assets/using/metadata-profiles.md)
* [Image profiles](../../assets/using/image-profiles.md)
* [Video profiles](../../assets/using/video-profiles.md)

You must have Administrator rights to create, edit, and delete metadata, image, or video profiles.

After you create your metadata, image, or video profile, you assign it to one or more folders that you use as the destination for newly uploaded assets.

See also [Best Practices for Organizing your Digital Assets for using Processing Profiles](../../assets/using/best-practices-for-file-management.md).

>[!NOTE]
>
>Assets that you move from one folder to another do not get reprocessed. For example, suppose you have Folder 1 that has profile A assigned to it and Folder 2 that has profile B assigned to it. If you move assets from Folder 1 to Folder 2, the moved assets retain their original processing from Folder 1.
>
>The same is true even when you move assets between two folders that have the same profile assigned to it.

