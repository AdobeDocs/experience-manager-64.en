---
title: About the use of stages in AEM 3D
seo-title: About the use of stages in AEM 3D
description: null
seo-description: Stages are light-weight 3D scene files that provide the basic viewing environment.
uuid: 080ccfff-d10f-413c-9562-86fb28602c3e
acrolinxdate: 2019-01-12T17 10 46.005-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/about_the_use_of_stages_in_aem_3d_krs_workflow_f3c2f2ccebf6138e_76_report.xml
acrolinxsentences: 12
acrolinxwords: 155
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 28f51ad8-4e4e-4f1e-91d8-37ac51e11740
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

##

