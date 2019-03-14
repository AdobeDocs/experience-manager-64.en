---
title: DO NOT PUBLISH | New features summary | AEM Assets
seo-title: DO NOT PUBLISH | New features summary | AEM Assets
description: Summary of new features and enhancements in AEM 6.4 Assets
seo-description: Summary of new features and enhancements in AEM 6.4 Assets
page-status-flag: de-activated
uuid: 08f84f24-9c31-4295-881a-e8ddbae5f4cb
contentOwner: cmajumda
discoiquuid: d5e8b969-ea92-4427-851b-e7b64e8334fd
---

# DO NOT PUBLISH | New features summary | AEM Assets{#do-not-publish-new-features-summary-aem-assets}

Summary of new features and enhancements in AEM 6.4 Assets

AEM 6.4 Assets includes several important features and enhancements around usability, metadata management, content intelligence, reporting, and search capabilities. The intuitive user interface provides an efficient browsing experience to users.

You can sign in to AEM 6.4 Assets using a unified sign-in account and seamlessly integrate your Creative Cloud apps with AEM.

The new features and enhancements can be broadly classified as follows:

* Usability enhancements
* Seamless integration with Creative Cloud
* Content intelligence
* Improved metadata management
* Reporting enhancements
* Enhanced search capabilities
* Brand Portal
* Dynamic media capabilities

## Usability enhancements {#usability-enhancements}

AEM 6.4 Assets includes several important enhancements to usability, UI performance, and UI productivity. Optimized lazy loading and scrolling experience, responsive back button in search results, and Content Tree view are some of the enhancements that significantly improve user experience. The Content Tree view allows you to quickly traverse the AEM Assets folder hierarchy and find assets faster.

## Seamless integration with Creative Cloud {#seamless-integration-with-creative-cloud}

You can now log in to Creative Cloud using a single sign-on account and integrate your creative apps with AEM Assets. Seamless integration with Creative Cloud fosters greater collaboration between creative users and marketers.

You can access assets from an AEM panel within your creative app. This way, you can search for, edit, and save changes to assets without leaving your creative app.

For example, you can use the AEM panel in Photoshop to access AEM Assets folders and update approved assets based on request from marketing. You can also use work-in-progress assets in Creative Cloud to create assets and save them to AEM Assets.

## Content intelligence {#content-intelligence}

AEM 6.4 Assets applies the power of Adobe Sensei to enhance the machine learning capabilities of smart tags (an image recognition service that applies suggested tags based on the image).

Adobe Sensei's AI framework uses the customer's tag structure and business taxonomy to train the image recognition algorithm. Content intelligence acquired through training enables the algorithm to suggest meaningful tags that are compatible with the customer's taxonomy. For, more information, see [Enhanced Smart Tags](../../assets/using/enhanced-smart-tags.md).

## Improved metadata management {#improved-metadata-management}

AEM 6.4 Assets supports cascading or contextual metadata. You can define metadata relationships based on business rules. In other words, you can create a dependency between a particular metadata field and one or more fields. You can use this dependency to display selective metadata based on a previous selection.

This feature is helpful when you want to display a relevant subset of tags from a large collection of tags in a complex taxonomy. For example, if you use the review status tag to classify assets, you can define related tags for various review stages, such as approved and rejected. This way, you can easily display approved assets from a large set of assets that have a review status tag.

AEM Assets also provides extended support for bulk metadata export and import. For more details, see [Cascading Metadata](../../assets/using/cascading-metadata.md).

## Enhanced reporting capabilities {#enhanced-reporting-capabilities}

With the new reporting engine in AEM 6.4 Assets, you can asynchronously generate reports much faster and efficiently.

You can generate more OOTB reports, including disk usage and link shares. Here is a list of reports that you can generate in AEM 6.4 Assets:

* Asset upload/downloads
* Asset expiration
* Asset modification
* Asset publish
* Brand Portal publish
* Disk usage
* File
* Link share

For more details, see [Asset Reports](../../assets/using/asset-reports.md).

## Enhanced search capabilities {#enhanced-search-capabilities}

AEM 6.4 Assets lets you search for specific types of images or documents. For example, you can search for images of a particular MIME type or format (vector or bitmap). Similarly, you can search for documents of a particular format, for example Word, PDF, PPT, and so on. AEM Assets includes OOTB search facets to support this search feature.

AEM Assets provides granular controls to search for assets based on modified date. You can also search for assets based on file size. You can include the unit of measure (MB, Mb, and so on) in size-based searches.

AEM Assets supports Smart Translation Search that lets you search for assets in various languages and fetch results even if the assets are not tagged in a particular language. For more information, see [Searching Assets](../../assets/using/search-assets.md) and [Search Facets](../../assets/using/search-facets.md).

## Brand Portal {#brand-portal}

Brand Portal is a turnkey solution for the secure distribution of assets. AEM 6.4 provides an updated user experience and better performance with Brand Portal. The latest Brand Portal offering also includes reporting, metadata, and search enhancements. You can rapidly publish assets from AEM Assets to Brand Portal. Branding improvements and in-app maintenance notifications are among the other enhancements/features that Brand Portal includes.

## Dynamic Media capabilities {#dynamic-media-capabilities}

AEM 6.4 Assets leverages machine learning and AI to identify focus points for assets and suggest appropriate cropping areas. This capability significantly increases the efficiency of cropping assets, especially when you crop assets in bulk.

To learn more about smart crop and smart swatch, see [Image Profiles](../../assets/using/image-profiles.md).
