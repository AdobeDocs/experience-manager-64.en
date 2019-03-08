---
title: Profiles for Processing Metadata, Images, and Videos
seo-title: Profiles for Processing Metadata, Images, and Videos
description: A profile a set of rules around the options to be applied to assets uploaded to a folder. Specify what metadata profile and video encoding profile to apply to video assets that you upload. For image assets, you can also specify what imaging profile to apply to image assets to have them properly cropped.
seo-description: A profile a set of rules around the options to be applied to assets uploaded to a folder. Specify what metadata profile and video encoding profile to apply to video assets that you upload. For image assets, you can also specify what imaging profile to apply to image assets to have them properly cropped.
uuid: f0d119d6-3af1-4269-a2ad-a1812adb7aa7
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 275bfa89-4585-45b1-966f-b0c31483cb55
index: y
internal: n
snippet: y
---

# Profiles for Processing Metadata, Images, and Videos{#profiles-for-processing-metadata-images-and-videos}

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

