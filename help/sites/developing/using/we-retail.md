---
title: We.Retail Reference Implementation
seo-title: We.Retail Reference Implementation
description: We.Retail is a technology preview of a reference implementation that illustrates the recommended way of setting up an online presence with AEM
seo-description: We.Retail is a technology preview of a reference implementation that illustrates the recommended way of setting up an online presence with AEM
uuid: d8833192-b592-4812-bf9b-bd882e8ee7f0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: f50150af-deff-4c29-bfe0-1cfc67b29d51
---

# We.Retail Reference Implementation{#we-retail-reference-implementation}

## Introduction {#introduction}

![](/content/help/en/experience-manager/6-4/sites/developing/using/we-retail/_jcr_content/main-pars/image.img.jpg/screencapture-localhost-4502-editor-html-content-we-retail-us-en-html-2018-08-17-14_33_32.png)

We.Retail is a reference implementation and sample content that illustrates the recommended way of setting up an online presence with Adobe Experience Manager.

We.Retail makes use of the latest AEM technologies such as HTL, responsive layouts, editable templates, core components, and much more.

While it illustrates a retail vertical, the way the site is setup can be applied to any vertical, and only the product catalog and cart features are retail-specific.

## Features {#features}

As AEM's standard reference implementation, We.Retail showcases some of the most powerful features of AEM.

| **Feature** |**Description** |**Interested?** |
|---|---|---|
| [Globalized site structure](../../../sites/administering/using/tc-bp.md) |We.Retail includes language masters which are live-copied into country-specific sites. | [Try it!](../../../sites/developing/using/we-retail-globalized-site-structure.md) |
| [Responsive layout](../../../sites/authoring/using/responsive-layout.md) |All pages feature responsive layout to adapt dynamically to screen and device size. | [Try it!](../../../sites/developing/using/we-retail-responsive-layout.md) |
| [Editable templates](../../../sites/developing/using/page-templates-editable.md) |All pages are based on editable templates, allowing non-developers to adapt and customize the templates. | [Try it!](../../../sites/developing/using/we-retail-editable-templates.md) |
| [HTML Template Language](https://helpx.adobe.com/experience-manager/htl/user-guide.html) |All components are based on HTL |  |
| [eCommerce capabilities](../../../sites/developing/using/ecommerce.md) |Features a product catalog |  |
| [Communities sites](../../../communities/using/overview.md) |Allowing visitors to join in community discussions, read blogs, and much more |  |
| [Core Components](https://helpx.adobe.com/experience-manager/core-components/user-guide.html) |All components are based on the new core components and are more usable and user-configurable out-of-the-box | [Try it!](../../../sites/developing/using/we-retail-core-components.md) |
| [Content Fragments](../../../assets/using/content-fragments.md) |The We.Retail Experiences section showcases the power of reusing content via content fragments. | [Try them!](../../../sites/developing/using/we-retail-content-fragments.md) |
| [Experience Fragments](../../../sites/authoring/using/experience-fragments.md) |An Experience Fragment is a group of one or more components including content and layout that can be referenced within pages. | [Try them!](../../../sites/developing/using/we-retail-experience-fragments.md) |

## Getting Started {#getting-started}

We.Retail is delivered as AEM's sample content. In order to use, simply [start AEM as you normally would](../../../sites/deploying/using/deploy.md#getting-started), making sure that sample content is not disabled.

>[!CAUTION]
>
>We.Retail should not be installed on production instances. Production instances should be started in `nosamplecontent` [runmode](../../../sites/deploying/using/configure-runmodes.md).

>[!CAUTION]
>
>We.Retail is based on the latest AEM technology and therefore does not support [classic UI authoring](/help/sites/classic-ui-authoring/using/home.md).

### Latest Version {#latest-version}

Although We.Retail is distributed with the AEM release, updates to the content and its features may be made after the release. Therefore it is possible to [download the latest release from GitHub](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases) and then [upload](../../../sites/administering/using/package-manager.md#uploading-packages-from-your-file-system) and [install](../../../sites/administering/using/package-manager.md#installing-packages) it as a package on your AEM instance.

### First Steps {#first-steps}

1. Once AEM is started (and/or We.Retail is installed), the site **We.Retail** is available in the [sites console](../../../sites/authoring/using/basic-handling.md#global-navigation).
1. For example the following page can be opened and it should look as displayed in the [appendix](#appendix) below:

   `https://<server name>:<port number>/editor.html/content/we-retail/language-masters/en.html`

## We.Retail & Geometrixx {#we-retail-geometrixx}

Geometrixx and its many incarnations served as sample content in earlier versions of AEM. Since version 6.3, We.Retail has been the sample content delivered with AEM and serves as the new standard reference implementation.

We.Retail is technically more robust and exploits the latest AEM technology to be more flexible and scalable, while also demonstrating the newest features of the product.

### Feature Comparison {#feature-comparison}

The following table gives an overview of major features that are available in We.Retail as compared to Geometrixx.

* **Available** means that examples of the feature are found in the sample content.
* **Not available** means that examples of the feature are not available in the sample content, but does not mean that the feature itself is not.

| **Feature** |**We.Retail** |**Geometrixx** |
|---|---|---|
| Globalized site structure |Language masters live-copied into country-specific sites |Not available |
| Content Fragments |Available |Not available |
| Experience Fragments |Available |Not available |
| Responsive Layout |For all pages |Only Geometrixx Media |
| Editable Templates |For all pages |Not available |
| HTL |All components |Limited |
| Targeting |For all pages |Only Geometrixx Outdoors |
| Screens |Available |Not available |
| Mobile |Not available |Available |
| Manuscripts |Not available |Available |
| Carousel, download, chart components |Not available |Available |
| Column control |Replaced by layout container |Available |
| Forms |Not available |Available |
| Campaign |No email samples |Available |

>[!NOTE]
>
>This list strives to be complete, but should not be considered exhaustive.

## Contribute {#contribute}

We.Retail has been released as an open-source project and the latest version of the source code can be downloaded from GitHub.

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-sample-we-retail project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/archive/master.zip)

The latest release can also be [downloaded directly](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases/latest) as an installable package.

If you encounter problems, please file [GitHub issues](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/issues).

Feel free to fork or to contribute with [pull requests](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/pulls).

## Appendix {#appendix}

Preview of the We.Retail welcome page:

![](assets/screencapture-localhost-4502-editor-html-content-we-retail-us-en-html-2018-08-17-14_33_32.png)

