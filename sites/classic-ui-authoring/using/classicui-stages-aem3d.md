---
title: About the use of stages in AEM 3D
seo-title: About the use of stages in AEM 3D
description: null
seo-description: Stages are light-weight 3D scene files that provide the basic viewing environment (lights, backgrounds, ground planes or other fixed geometry), optional pre-defined cameras, and render settings for third-party renderers.
uuid: 349270ec-ccbf-45b0-acdf-234c1279ac2d
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: f51fcb7b-137b-4d7c-b27a-3da19c6a52d4
isreadyforlocalization: false
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

