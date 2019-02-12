---
title: Best Practices for Organizing Your Digital Assets for Using Profiles
seo-title: Best Practices for Organizing Your Digital Assets for Using Profiles
description: Tips and best-practices for naming, organizing, managing metadata for digital asset files.
seo-description: Tips and best-practices for naming, organizing, managing metadata for digital asset files.
uuid: 59536c03-7e15-4ce0-81a6-4dbcf6b1a082
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 5378dcb3-9c2f-4cff-87c4-6ff6f9093d84
index: y
internal: n
snippet: y
---

# Best Practices for Organizing Your Digital Assets for Using Profiles{#best-practices-for-organizing-your-digital-assets-for-using-profiles}

An important concept regarding the use of profiles in AEM Assets is that they are assigned to folders. Within a profile are settings in the form of metadata profiles, along with video profiles or image profiles. These settings process the contents of a folder along with any of its sub-folders. Therefore, how you name files and folders, how you arrange sub-folders, and how you handle the files within these folders has a significant impact on how those assets are processed by a profile.

By using consistent and appropriate file and folder naming strategies, along with good metadata practice, you can make the most of your digital asset collection and ensure that the right files are processed by the right profile.

See [Profiles for Processing Video, Metadata, and Images](../../assets/using/processing-profiles.md).

The following are best-practice tips for organizing your digital asset files.

* Organize your files based on the metadata that you add to them instead of on the folders in which they reside. You can accomplish this by adding metadata profiles.  
  See [Metadata Profiles.](../../assets/using/metadata-profiles.md)  
  See [Metadata for Digital Asset Management](../../assets/using/metadata.md).  

* In most cases, your collection of digital assets are always growing. Therefore, it is important, earlier on, to formalize metadata use, folder structure, and file naming among all your uploaded assets. Standardizing on these things ensures that as your pool of digital assets grows, you can apply processing profiles to folders with greater precision and consistency.
* Use folders only to impose a consisistent storage structure for your digital assets. For example, folder structures that can help you refine what profiles to assign may include the following:

    * Development folders - contains digital assets that you are currently working on.
    * Client folders - contains digital assets based on clients or project names.  
    * Master folders - contains original, source digital assets.  
    * Rendition folders - contains renditions and copies of the original, source digital assets.  
    * File Size folders - contains digital assets based on small, medium, or large file sizes.  
    * Staging folders - contains digital assets that are ready to publish live on your website.
    * Mime type folders - contains digital assets that are specific to mime types such as images, documents, and multimedia.
    * Archive folders - contains retired digital assets.
    * Date-based folders - contains digital assets based on a creation date or a last modified date.

* Create a directory of folders that are not likely to change so that any assigned profiles do not break.
* If an asset is already published, then you use AEM to move the asset to another folder, and re-publish from its new location, the original published asset location is still available, along with the newly re-published asset. The original published asset, however, is "lost" to AEM and cannot be unpublished. Therefore, as a best practice, unpublish assets first before you move them to a different folder.

