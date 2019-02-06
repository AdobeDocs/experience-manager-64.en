---
title: AEM Assets Release Notes
seo-title: AEM Assets
description: Release notes specific to Adobe Experience Manager 6.4 Assets.
seo-description: Release notes specific to Adobe Experience Manager 6.4 Assets.
uuid: bc3a1e37-4733-4c4d-b393-d541695efaef
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 6c788cec-198a-4d1d-a4f1-a60548a826ed
index: y
internal: n
snippet: y
---

# AEM Assets Release Notes{#aem-assets-release-notes}

Release notes specific to Adobe Experience Manager 6.4 Assets.

Here are the key features and highlights of the AEM 6.4 Assets release.

## Adobe Asset Link {#adobe-asset-link}

Adobe Asset Link in Creative Cloud for enterprise streamlines collaboration between creatives and marketers in the content creation process. It is a new native capability in Creative Cloud for enterprise, providing a connection to AEM Assets directly from Photoshop, Illustrator, and InDesign—without leaving their tools of choice.  

To learn more about the capability, prerequisites, and how to access it, see the [Adobe Asset Link](https://www.adobe.com/creativecloud/business/enterprise/adobe-asset-link.html) page.  

## Enhanced Smart Tags (powered by Adobe Sensei) {#enhanced-smart-tags-powered-by-adobe-sensei}

AEM 6.4 introduces Artificial Intelligence based Enhanced Smart Tags capability in addition to Smart Tags which was launched in 6.3.

* Smart Content Service learns customer's business taxonomy and uses it to automatically tag digital assets with customer relevant tags in addition to generic tags. It improves asset discoverability significantly and reduces time to market. 
* Adobe Sensei powers the Smart Content Service, which enables you to train the image recognition algorithm on your business taxonomy. This content intelligence is then used to apply relevant tags on similar assets.

AEM Assets Enhanced Smart Tags requires the [latest service pack of AEM 6.4](/content/help/en/experience-manager/aem-releases-updates).

## Smart Translation Search (powered by Adobe Sensei) {#smart-translation-search-powered-by-adobe-sensei}

AEM 6.4 introduces Smart Translation Search capability to support multi lingual search scenarios. Customers with globally distributed teams across multiple locales now have access to search in different languages without having to go through costly and time-consuming translation workflows.

* Search query is translated without manual intervention
* Has support for Smart Tags, which are generated in English, but are machine translated to others language 
* Multi-lingual search is built using open source library Apache Joshua, which supports more than 50 languages.

## User Experience {#user-experience}

AEM 6.4 delivers significant user experience improvents in areas of browse, search, multi page assets and admin tools. Details below:

Browse Improvements

* New Content Tree rail to quickly navigate an asset hierarchy. In combination with the list view, this restores the Classic UI interaction model to browse asset hierarchies.
* New Keyboard Shortcuts such as (m) for Move operation, (p) for navigation to properties page, (ctrl+c) for copy operation and many more.
* Improved scrolling, lazy loading experience in card and list view for browsing large number of assets. 
* Improved Card View with support for different sized cards based on view setting.
* Improved asset detail experience with ability to view, navigate to “previous” or "next" asset along with number of assets, current asset.

Search Improvements

* New Search back button with ability to navigate to a search item and come back to same position in search results without running the search query again.
* New Search results count to display number of search results.
* Improved File Type Search Filter with ability to filter search results based on fine grained mime types such as .jpg, .png, and .psd compared to earlier Image, Document, Multimedia options.
* Improved search filters with accurate time stamps instead of previous time slider functionality.

Multi-Page Assets Improvements

* Improved multi page assets browsing experience with reduced number of clicks.
* Improved comments and annotations support with all of them collated at asset level rather than page level.

Admin Tools Improvements

* Improved Property picker in Admin tools for Metadata, Search and Reports with Type ahead and browsing capability to simplify admin experience.

Catalogs

* Improved user experience, alignement with Templates UI. For more information, see [Catalog Producer](../sites/administering/using/catalog-producer.md).

## Metadata {#metadata}

AEM 6.4 includes multiple advanced metadata management capabilities to manage metadata at scale and enforce metadata integrity through rules and validations. Here are the key capabilities:

* New Bulk Metadata Export capability to export (all, selective) metadata for large number of assets in CSV format for editing, sharing, and third-party integration.
* New Bulk Metadata Import capability to import CSV file for adding new metadata, updating existing metadata for multiple assets in one go. This operation is asynchronous, and does not hinder system performance. Once complete, user is notified via AEM's Notification system.
* New Cascading and Contextual Metadata using Metadata Schema Tool. It’s now possible to define chains of dependencies, and value mappings between fields. You can also define the context in which metadata form fields are displayed/hidden. This way, you can display only relevant fields at any moment depending on values in other fields.

## Reports {#reports}

AEM 6.4 delivers significant Asset Reporting enhancements:

* New enterprise-level, scalable (for large repositories) reports framework applying Sling jobs for asynchronously processing report requests. You can schedule report at a specific date and time. You can also add custom columns to a report.
* New OOTB reports most commonly asked by customers such as Disk Usage, Files, Link Shares, Publish to Brand Portal, Smart Tags Training.
* New Reports creation and management UI with fine grained options, ability to access archived reports, see report run status (success, failed, queued, and so on).

## Brand Portal {#brand-portal}

* **6.3 Platform Upgrade**: Brand Portal upgraded from AEM 6.0 to AEM 6.3, with new features and performance improvements.
* **Parallel Publish**: Up to replications can occur between AEM Assets and Brand Portal (previously 1), which significantly improves publishing performance
* **Schema & Search Facet Publish**: Ability to publish metadata schemas and custom search facets to Brand Portal, which eliminates effort duplication.
* **Bulk Tags Publish**: Ability to publish taxonomy (along with hierarchy) to Brand Portal, which eliminates effort duplication.
* **Self sign up/Request access**: Workflow for non-registered users to Brand Portal.
* **In-app (on screen) Maintenance Notification**: Notifications are displayed well in advance to avoid disruption in business.
* **Reporting improvements**: Three OOTB reports are available: downloads, publish and link-shares.
* **DRM-based restrictions**: After a licensed asset expires, it is no longer available for download from Brand Portal.

## AEM Desktop App {#aem-desktop-app}

AEM Desktop App has been updated to Version 1.8, which is compatible with AEM 6.4. The full list of changes for AEM Desktop App is provided in a dedicated [AEM Desktop App release notes](/content/help/en/experience-manager/desktop-app/release-notes) document.  
Here is a list of AEM Desktop App highlights added since AEM 6.3 was released:

* Ability to upload hierarchical folders in the background.
* UI to monitor asset uploads in the background.
* Caching improvements, including a UI to manage caching parameters.
* Broader support for AEM authentication configurations (SAML/SSO) and network proxy.
* Supportability: easy access to logs from a UI.
* Improved stability and fixes for customer issues.

For easier access to the documentation and best practices, the following documentation is available:

* [User Guide](/assets/using/aem-desktop-app), aimed at end users working with the application
* [Best Practices Guide](/assets/using/aem-desktop-app-best-practices), aimed at end users and administrators
* Configuration Guide, aimed at administrators setting up AEM and AEM Desktop App to work together

## Tiered Storage {#tiered-storage}

AEM 6.4 includes a set of features that support various tiered storage preferences and implement lifecycle rules. The storage options also support (but are not limited) public clouds - AWS or Azure.

* The ability for users to select and later change storage class at will, and define rules for storage of assets from one class to another or manage the lifecycle of their assets.
* The ability for users to lower their storage cost by selecting a different AWS or Azure.

For an overview of supported platforms, please refer to the [Technical Requirements Documentation](../sites/deploying/using/technical-requirements.md).

<!--
Comment Type: annotation
Last Modified By: arora
Last Modified Date: 2018-04-04T06:10:16.512-0400
Can we please check whether Azure & Google cloud are supported?
-->

## Closed User Group {#closed-user-group}

* In AEM 6.4, Closed User Group or CUG provides a way to restrict folder access on publish instance, it’s a touch UI option to add principals through folder properties page at the folder level and are applied to all folder and subfolders/assets inside. 
* In publish mode, if a CUG is configured and authorization enabled om a folder, users are redirected to a login page when they try to access the folder. Therefore, authorized users can access the folder and its assets only after successful login. Hence, CUG restricts read access to a given tree in the content repository for everyone except selected principals.

## Dynamic Media add-on {#dynamic-media-add-on}

Dynamic Media in 6.4 supports a new mode - where master asset is uploaded and managed with AEM Assets web UI, and dynamic renditions and other dynamic media features are handled in the background by the Dynamic Media cloud delivery service.

In this new mode (introduced first with the release of AEM 6.3 Feature Packs 14410 and 18912), users benefit from end-to-end asset management and dynamic media features using the modern AEM Assets web UI, and still leverage the delivery services that are backwards compatible with Dynamic Media Classic (Scene7)—including delivery URLs, which are unchanged.

In addition, AEM 6.4 introduces new features powered by Adobe Sensei, enhancements for emerging media like VR and 3D, Dynamic Media viewers, and support for Experience Fragments in Interactive Images and Carousel Banners.

#### Smart Crop (Powered by Adobe Sensei) {#smart-crop-powered-by-adobe-sensei}

* Smart Crop automatically provides non-destructive cropping of images to preserve the point of interest for responsive design. You can preview cropped suggestions and manually adjust them, if necessary.   
* This feature also enables automated swatch generation for product imagery. Automated swatch generation helps to add color swatches, pattern swatches, or both to product images automatically.

See [Image Profiles](../assets/using/image-profiles.md) documentation to learn more.

See also [Adding Dynamic Media Assets to Pages](../assets/using/adding-dynamic-media-assets-to-pages.md) documentation to learn more about using Smart Crop with the Dynamic Media component.

#### Smart Imaging {#smart-imaging}

* Smart imaging leverages each user's unique viewing characteristics to automatically serve images optimized for their experience, resulting in better pefromance and engagement.
* Images are automatically converted to different formats based on browser capabilities.
* Image quality settings are determined in the browser and applied respectively. This intelligence keeps image loading performance acceptable for limited bandwidth and slow connection speeds.

See [Smart Imaging](../assets/using/imaging-faq.md) documentation to learn more.

#### Emerging Media &amp; Viewer Enhancements {#emerging-media-amp-viewer-enhancements}

* New viewers are supported, providing better, immersive experiences for the user.
* Panoramic Viewer helps engage the user and provide ability to better experience room scenes, properites, locations, and landscapes. See [Panoramic Images](../assets/using/panoramic-images.md) documentation to learn.  

* VR Viewer provides immersive experience for properites, locations, and landscapes.
* Vertical Image Viewer optimized for product imagery.
* Keyboard accessibility improvements.

#### 3D and Integration with Dimension CC {#d-and-integration-with-dimension-cc}

Integration with [Dimension CC](https://www.adobe.com/products/dimension.html) for more seamless 3D workflow has been introducted.

See [Working with 3D assets](../assets/using/3d-assets.md) documentation to learn more.
