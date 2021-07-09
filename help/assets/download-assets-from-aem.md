---
title: Download digital assets from [!DNL Adobe Experience Manager].
description: Learn how to download assets from [!DNL Adobe Experience Manager] and enable or disable the download functionality.
contentOwner: AG
feature: Asset Management,Asset Distribution
role: User
exl-id: bfe4d597-1080-4de5-a100-73a5175863d7
---
# Download assets from [!DNL Adobe Experience Manager] {#download-assets-from-aem}

You can download assets including static and dynamic renditions. Alternatively, you can send emails with links to assets directly from [!DNL Adobe Experience Manager Assets]. Downloaded assets are bundled in a ZIP file. The compressed ZIP file has a maximum file size of 1 GB for the export job. A maximum of 500 total assets per export job are allowed.

>[!NOTE]
>
>Recipients of emails must be members of the `dam-users` group to access the ZIP download link in the email message. To be able to download the assets, the members must have permissions to launch workflows that trigger downloading of assets.

The asset types Image Sets, Spin Sets, Mixed Media Sets, and Carousel Sets cannot be downloaded.

To download assets, follow these steps:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Navigation]**.
1. On the Navigation page, tap **[!UICONTROL Assets]** > **[!UICONTROL Files.]**
1. Navigate to a folder that contains assets you want to download.
1. Select the folder or select one or more assets within the folder.
1. On the toolbar, tap **[!UICONTROL Download.]**

   ![Available options when downloading assets from Experience Manager Assets](/help/assets/assets/asset_download_dialog.png)

   *Figure: Download dialog box options.*

1. In the Download dialog box, select the download options you want.

   | Export or download option | Description |
   |---|---|
   | **[!UICONTROL Create separate folder for each asset]** | Select this option to include each asset you download&ndash;including assets in child folders nested under the parent folder of the asset&ndash;into one folder on your local computer. When this option is not select, by default, the folder hierarchy is ignored and all assets are downloaded into one folder in your local computer. |
   | **[!UICONTROL Email]** | An email notification is sent to the user. Standard emails templates are available at the following locations:<ul><li>`/libs/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/libs/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul> Templates that you customize during deployment are available at the following locations: <ul><li>`/apps/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/apps/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul>You can store tenant-specific custom templates at the following locations:<ul><li>`/conf/<tenant_specific_config_root>/settings/dam/workflow/notification/email/downloadasset`.</li><li>`/conf/<tenant_specific_config_root>/settings/dam/workflow/notification/email/transientworkflowcompleted`.</li></ul> |
   | **[!UICONTROL Assets]** | Select this option to download the asset in its original form without any renditions.<br>The subassets option is available if the original asset has subassets. |
   | **[!UICONTROL Renditions]** | A rendition is the binary representation of an asset. Assets have a primary representation - that of the uploaded file. They can have any number of representations. <br> With this option, you can select the renditions you want downloaded. The renditions that are available depend on the asset you select. The option is available if the asset has any renditions. |
   | **[!UICONTROL Dynamic Renditions]** | Select this option to generate a series of alternate renditions in real time. When you select this option, you also select the renditions you want to create dynamically by selecting from the [Image Preset](image-presets.md) list. <br>In addition, you can select the size and unit of measurement, format, color space, resolution, and any optional image modifiers such as inverting the image. The option is only available if you have [!DNL Dynamic Media] enabled.|

1. In the dialog box, tap **[!UICONTROL Download.]**.

When you select a folder to download, the complete asset hierarchy under the folder is downloaded. To include each asset you download (including assets in child folders nested under the parent folder) in an individual folder, select **[!UICONTROL Create separate folder for each asset]**.

## Enable asset download servlet {#enable-asset-download-servlet}

The default servlet in [!DNL Experience Manager] allows authenticated users to issue arbitrarily large, concurrent download requests for creating ZIP files of assets visible to them that can overload the server and the network. To mitigate potential DoS risks caused by this feature, `AssetDownloadServlet` OSGi component is disabled by default for publish instances.

To allow downloading assets from your DAM, say when using something like Asset Share Commons or other portal-like implementation, manually enable the servlet via an OSGi configuration. Adobe recommends setting the permissible download size as low as possible without affecting the day-to-day download requirements. A high value may impact performance.

1. Create a folder with a naming convention that targets the publish runmode (`config.publish`): `/apps/<your-app-name>/config.publish`. To define configuration properties for a run mode, see [Run Modes](/help/sites-deploying/configure-runmodes.md#defining-configuration-properties-for-a-run-mode).
1. In the configuration folder, create a file of type `nt:file` named `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet.config`.
1. Populate `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet.config` with the following. Sets a maximum size (in bytes) for the download as value of `asset.download.prezip.maxcontentsize`. The below sample configures the maximum size of the ZIP download to not exceed 100 kB.

   ```conf
   enabled=B"true"
   asset.download.prezip.maxcontentsize=I"102400"
   ```

## Disable asset download servlet {#disable-asset-download-servlet}

The `Asset Download Servlet` can be disabled on an [!DNL Experience Manager] Publish instances by updating the dispatcher configuration to block any asset download requests. The servlet can also be manually disabled via the OSGi console directly.

1. To block asset download requests via a dispatcher configuration, edit the `dispatcher.any` configuration and add a rule to the [filter section](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#configuring-access-to-content-filter). `/0100 { /type "deny" /url "*.assetdownload.zip/assets.zip*" }`

1. To disable the OSGi component on a Publish instance, access the OSGi Console at `http://[aem_server]:[port]/system/console/components`. Locate `com.day.cq.dam.core.impl.servlet.AssetDownloadServlet` and click **[!UICONTROL Disable]**.

>[!MORELIKETHIS]
>
>* [Download DRM protected assets](drm.md).
>* [Download assets using Experience Manager desktop app on Win or Mac desktop](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html).
>* [Download assets using Adobe Assets Link from within the supported Adobe Creative Cloud apps](https://helpx.adobe.com/enterprise/using/manage-assets-using-adobe-asset-link.html).
