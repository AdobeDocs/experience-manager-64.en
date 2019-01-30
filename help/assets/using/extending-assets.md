---
title: Customizing and Extending Assets
seo-title: Customizing and Extending Assets
description: null
seo-description: Learn ways by which you can customize and extend Asset Share and Asset Editor, which presents users with a specifically tailored interface and set of functionality.
uuid: 64807785-712e-4a1e-b22b-ed43e5069b1a
acrolinxdate: 2019-01-12T17 28 46.923-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/extending_assets_krs_workflow_f3c2f2ccebf6138e_133_report.xml
acrolinxsentences: 17
acrolinxwords: 266
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: extending-assets
content-type: reference
discoiquuid: f585c7d7-f03d-480f-88d5-36ea0153fb6d
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Customizing and Extending Assets{#customizing-and-extending-assets}

The Asset Editor is the primary point of access that users of a Adobe Enterprise Manager (AEM) website will use to find, view, and manipulate the digital assets in your repository.

As an AEM developer, you can customize and extend the Asset Editor in a number of ways, presenting users with a specifically tailored interface and set of functionality.

The following aspects of the functionality can be customized or enhanced:

* [Extending Asset Editor](../../assets/using/asseteditorx.md)
* [Extending Assets Search](../../assets/using/searchx.md)
* [Processing Assets Using Media Handlers and Workflows](../../assets/using/media-handlers.md)
* [Integrating Assets with Activity Stream](../../assets/using/extending-activity-stream.md)
* [Assets Proxy Development](../../assets/using/proxy.md)
* [Best Practices for Configuring ImageMagick](../../assets/using/best-practices-for-imagemagick.md)

## Customizing the Look and Feel {#customizing-the-look-and-feel}

The following aspects of the look and feel of the Asset Editor are customizable:

* Logo: You can add your own organization's logo to the interface.
* Colors and Fonts: You can change the colors and fonts used in the interface.
* HTML Code: For more thorough customization you can change the underlying HTML code that defines the interfaces.

## Customizing Renditions {#customizing-renditions}

In AEM Assets terminology a rendition is the form in which an asset is presented. In general, a particular asset may have multiple renditions. For example, full-color image may have one rendition in its original size, another at a scaled-down size and another that is both scaled down and converted to grayscale.

The renditions that a particular asset is available in can be customized and new renditions created.
