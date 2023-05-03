---
title: Enabling Duplicate Detection
description: Learn how to enable the detection of duplicate assets in AEM.
contentOwner: AG
feature: Asset Management,Asset Reports
role: User,Admin
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
---
# Enabling Duplicate Detection {#enabling-duplicate-detection}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

If you attempt to upload an asset that exists in Adobe Experience Manager Assets, the duplicate detection feature identifies it as duplicate. Duplicate detection is disabled by default. To enable the feature, do the following steps:

1. Open the **[!UICONTROL Adobe Experience Manager Web Console Configuration]** page at `https://[server]:[port]/system/console/configMgr`.
1. Edit the configuration for the servlet **[!UICONTROL Day CQ DAM Create Asset]**.
1. Select the **[!UICONTROL detect duplicate]** option, and click/tap **[!UICONTROL Save]**.

   ![Select detect duplicate option in the servlet](assets/chlimage_1-377.png)

The detect duplicate feature is now enabled in [!DNL Experience Manager] Assets. When a user attempts to upload an asset that exists in AEM, the system checks for conflict and indicates it. The assets are identified using SHA-1 hash stored at `jcr:content/metadata/dam:sha1`, which means duplicate assets are detected irrespective of the filenames.

>[!MORELIKETHIS]
>
>* [Duplicate assets in existing repository (a tutorial from community member)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)
