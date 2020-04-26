---
title: Manage metadata of your digital assets
description: Learn about the types of metadata an how Adobe Experience Manager Assets helps manage metadata for assets to allow easier categorization and organization of assets. With the ability to keep and manage arbitrary metadata with your assets Adobe Experience Manager Assets makes it possible to automatically organize and process assets based on their metadata.
contentOwner: AG
---

# Manage metadata of your digital assets {#managing-metadata-for-digital-assets}

Adobe Experience Manager Assets keeps metadata for every asset. This allows easier categorization and organization of assets and it helps people who are looking for a specific asset. With the ability to extract metadata from files uploaded to Experience Manager Assets, metadata management integrates with the creative workflow. With the Experience Manager capability to keep and manage metadata with your assets, you can automatically organize and process assets based on the metadata.

* [XMP metadata](xmp.md)
* [How to edit or add metadata](meta-edit.md)
* [Metadata schemata reference](meta-ref.md)

## Why we need metadata {#why-we-need-metadata}

Metadata means data about data. In this regard, data refers to your digital asset, say an image. Metadata is critical for efficient asset management.

Metadata is the collection of all the data available for an asset but that is not necessarily contained in that image. Some examples of metadata are:

* Name of the asset.
* Time and date of last modification.
* Size of the asset as it was stored in the repository.
* Name of the folder it is contained in.
* Related assets or applied tags.

These are the basic metadata properties that Experience Manager can manage for assets, which allows users to see all assets, for example, ordered by their last modification date - useful when trying to discover what assets have recently been added to the repository.

You can add more high-level data to digital assets, for example:

* Type of asset (is it an image, a video, an audio clip or a document?).
* Owner of the asset.
* Title of the asset.
* Description of the asset.
* Tags assigned to an asset.

More metadata helps you further categorize assets and is helpful as the amount of digital information grows. It is possible to manage a few hundred files based on just the filenames. However, this approach is not scalable and quickly falls short when the number of people involved and the number of assets managed increases.

As metadata is added to assets, the value of the asset grows, because the asset becomes,

* more accessible - people can find it much easier.
* easier to manage - you can find assets with the same set of properties easier and apply changes to them.
* more complex - the more metadata you have added to an asset, the more important managing metadata becomes.

For these reasons, Experience Manager Assets provides you with the right means of creating, managing, and exchanging metadata for your digital assets.

## Types of metadata {#types-of-metadata}

The two basic types of metadata are technical metadata and descriptive metadata.

Technical metadata is useful for software applications that are dealing with digital assets and should not be maintained manually. Experience Manager Assets and other software automatically determines technical metadata and the metadata may change when the asset is modified. The available technical metadata of an asset depends largely on the file type of the asset. Some examples of technical metadata are:

* Size of a file
* Dimensions (height and width) of an image
* Bit rate of an audio or video file
* Resolution (level of detail) of an image

Descriptive metadata is metadata concerned with the application domain, for example, the business that an asset is coming from. Descriptive metadata cannot be determined automatically. It is created manually or semi-automatically. For example, a GPS-enabled camera can automatically track the latitude and longitude and add geotag the image.

Because of the high cost of the manual effort required to create descriptive metadata information, standards have been established to ease the exchange of metadata across software systems and organizations.

Experience Manager Assets supports all relevant standards for metadata management.

Because of the importance of metadata and the high manual involvement required to create metadata, standards have been established that make it easier to exchange.

## Encoding standards {#encoding-standards}

There are various ways to embed metadata in files. A selection of encoding standards are supported:

* XMP: used by Experience Manager Assets to store the extracted metadata within the repository.
* ID3: for audio and video files.
* Exif: for image files.
* Other/Legacy: from Microsoft Word, PowerPoint, Excel, and so on.

### XMP {#xmp}

Extensible Metadata Platform (XMP) is an open standard that is used by Experience Manager Assets for all metadata management. The standard offers universal metadata encoding that can be embedded into all file formats. Adobe and other companies support XMP standard as it provides a rich content model. Users of XMP standard and of Experience Manager Assets have a powerful platform to build upon. For more information, see [XMP](https://www.adobe.com/products/xmp.html).

### ID3 {#id}

Data stored in these ID3 tags is displayed when you play back a digital audio file on either your computer or a portable MP3 player.

ID3 tags are designed for the MP3 file format. Additional information on formats:

* ID3 tags work in MP3 and mp3PRO files.
* WAV has no tags.
* WMA has proprietary tags that do not allow open-source implementation.
* Ogg Vorbis uses Xiph Comments embedded in the Ogg container.
* AAC uses a proprietary tagging format.

### Exif {#exif}

Exchangeable image file format (Exif) is the most popular metadata format used in digital photography. It provides a way of embedding a fixed vocabulary of metadata properties in many file formats, such as JPEG, TIFF, RIFF, and WAV. Exif stores metadata as pairs of a metadata name and a metadata value. These metadata name-value-pairs are also called tags, not to be confused with the tagging in Experience Manager. As Exif is automatically created by modern digital cameras and supported through modern graphics software, it can be seen as the lowest common denominator for metadata management.

A major limitation of Exif is that a few popular image file formats such as BMP, GIF, or PNG do not support it.

Metadata fields usually defined by Exif are technical in nature and are of limited use for descriptive metadata management. For this reason, Experience Manager Assets offers mapping of Exif properties into [common metadata schemata](metadata-schemas.md) and into [XMP](xmp-writeback.md).

### Other metadata {#other-metadata}

Other metadata that can be embedded from files include Microsoft Word, PowerPoint, Excel, and so on.

## Metadata schemata {#metadata-schemata}

Metadata schemas are predefined sets of metadata property definitions that can be used in various applications. Properties are always associated with an asset, meaning that the properties are “about” the resource.

You can also design your own metadata schemata if none exists that meet your needs. Do not duplicate existing information. Within an organization, separating schemata makes it easier to share metadata. Experience Manager provides you with a default list of the most popular metadata schemata. The list helps you to jumpstart your metadata strategy and quickly pick the metadata properties that you need.

The supported metadata schemata supported are listed below.

### Standard metadata {#standard-metadata}

* dc - Dublin Core - the most important and widely used set of metadata.
* DICOM - Digital Imaging and Communications in Medicine.
* Iptc4xmpCore & iptc4xmpExt - International Press Communications Standard - lots of subject-specific metadata.
* rdf - Resource Description Framework - for generic semantic web metadata.
* xmp - Extensible Metadata Platform.
* xmpBJ - Basic Job Ticketing.

### Application-specific metadata {#application-specific-metadata}

The application-specific metadata includes technical and descriptive metadata. If you use these, other applications may not be able to use the metadata. For example, if you have an asset with Adobe Photoshop metadata and another image-rendering application tries to access the metadata, it may not be able to access the metadata. If you find that you have much application-specific metadata in your assets, you can create a workflow step that changes an application-specific property to a standard property.

* acdsee - metadata managed by the ACDSee program [www.acdsee.com/](https://www.acdsee.com/).
* album - Adobe Photoshop Album.
* cq - used by Experience Manager Assets.
* dam - used by Experience Manager Assets.
* dex - Optima SC Description Explorer.
* crs - Adobe Photoshop Camera Raw.
* lr - Adobe Lightroom.
* mediapro - IView MediaPro.
* MicrosoftPhoto & MP - Microsoft Photo.
* pdf & pdfx
* photoshop & psAux - Adobe Photoshop

### Digital Rights Management metadata {#digital-rights-management-metadata}

* cc - creative commons
* xmpRights
* plus - Picture Licensing Universal System - https://www.useplus.com/
* prism - https://www.idealliance.org/prism-metadata Publishing Requirements for Industry Standard Metadata
* prl - Prism Rights Language
* pur - Prism Usage Rights
* xmpPlus - integration of PLUS with XMP

### Photography-specific metadata {#photography-specific-metadata}

* exif - lots of technical information from camera, including GPS position
* crs - photoshop camera raw
* Iptc4xmpCore and iptc4xmpExt
* TIFF - image metadata (not only for TIFF images)

### Print-specific metadata {#print-specific-metadata}

* pdf and pdfx - Adobe PDF and third-party applications
* prism - [www.prismstandard.org](https://www.prismstandard.org) Publishing Requirements for Industry Standard Metadata
* xmp
* xmpPG - xmp for paged text

### Multimedia-specific metadata {#multimedia-specific-metadata}

* xmpDM - Dynamic Media
* xmpMM - Media Management

## Metadata-driven workflows {#metadata-driven-workflows}

Creating metadata-driven workflows helps you automate some processes, which improves efficiency. In a metadata-driven workflow, the workflow management system reads the workflow and as a result performs some pre-defined action. For example, some of the ways you could use metadata-driven workflows:

* The workflow can check whether an image has a title. If it does not, the system notifies a particular user to add a title.
* The workflow can check whether a copyright notice on an asset allows for distribution. If it does, the system sends the asset to one server. If it does not, the system sends the asset to another server.
* A workflow can check for assets without pre-defined, mandatory metadata or with *invalid* metadata.
