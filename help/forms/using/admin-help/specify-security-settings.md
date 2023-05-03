---
title: Specify security settings
seo-title: Specify security settings
description: Learn how to specify security settings.
seo-description: Learn how to specify security settings.
uuid: c86ba195-010d-40d6-9f9d-4cb4c364d104
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 3c017f9a-aa7f-4d12-ba8b-9fd92c029157
exl-id: 3cc39a24-dbdf-4a4c-9c96-4d39d8cff20d
---
# Specify security settings {#specify-security-settings}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Output enables you to control whether external entities in XML inputs are resolved. By default, they are resolved, but you can change this behavior to increase the security of your AEM forms system.

**Prevent the processing of XML data files that contain references to external entities**

1. In administration console, click Services &gt; output.
1. Clear the Resolve External Entities check box.
1. Click Save.
