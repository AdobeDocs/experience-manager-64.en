---
title: About the use of stages in AEM 3D
seo-title: About the use of stages in AEM 3D
description: Stages are light-weight 3D scene files that provide the basic viewing environment (lights, backgrounds, ground planes or other fixed geometry), optional pre-defined cameras, and render settings for third-party renderers.
seo-description: Stages are light-weight 3D scene files that provide the basic viewing environment (lights, backgrounds, ground planes or other fixed geometry), optional pre-defined cameras, and render settings for third-party renderers.
uuid: 889d014f-66fe-45cc-b279-a72cb0992066
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 9bc896e3-b36e-45d8-ba4a-967b3037cae5
index: y
internal: n
snippet: y
---

# About the use of stages in AEM 3D{#about-the-use-of-stages-in-aem-d}

Stages are light-weight 3D scene files that provide the basic viewing environment (lights, backgrounds, ground planes or other fixed geometry), optional pre-defined cameras, and render settings for third-party renderers.

>[!NOTE]
>
>The OBJ 3D format does not support lights. Therefore, it cannot be used to provide stages to AEM 3D.

The file format of the stage determines which renderer you can use with that stage. For example, if Autodesk® Maya® is used for high-quality rendering, the stage must be in `.ma` or `.mb` format. If you intend to only use the default Rapid Refine™ renderer, any supported stage file format is acceptable.

All render settings in AEM 3D, except the output image type and size must be pre-configured and saved into the stage file prior to uploading to AEM.

