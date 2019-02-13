---
title: Customizing and Extending Assets
seo-title: Customizing and Extending Assets
description: Learn ways by which you can customize and extend Asset Share and Asset Editor, which presents users with a specifically tailored interface and set of functionality.
seo-description: Learn ways by which you can customize and extend Asset Share and Asset Editor, which presents users with a specifically tailored interface and set of functionality.
uuid: c4ec7d0a-0153-4e56-a145-e126ce0367ee
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: extending-assets
content-type: reference
discoiquuid: 9ebece23-729d-4d45-89c4-df364f0b3fd9
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
