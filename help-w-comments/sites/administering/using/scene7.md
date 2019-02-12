---
title: Integrating with Dynamic Media Classic (Scene7)
seo-title: Integrating with Dynamic Media Classic (Scene7)
description: Learn how to integrate AEM with Scene7.
seo-description: Learn how to integrate AEM with Scene7.
uuid: 4cb8d384-b966-401e-9c87-75970715d2d1
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: ab01602a-822a-4005-96f0-72787bce8f77
index: y
internal: n
snippet: y
---

# Integrating with Dynamic Media Classic (Scene7){#integrating-with-dynamic-media-classic-scene}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-77F410094CD97C4F0A746C1B@AdobeID)
Last Modified Date: 2018-03-15T23:52:06.705-0400
<p>Most of the procedures are still only in classic UI (cloud services), but added procedure for enabling config in wcm in touch ui. Update was made in October.</p>
-->

[Adobe Scene7](http://help.adobe.com/en_US/scene7/using/WS26AB0D9A-F51C-464e-88C8-580A5A82F810.html) is a hosted solution for managing, enhancing, publishing, and delivering rich media assets to Web, mobile, email, and Internet-connected displays and print.

To use Scene7, you need to configure the cloud configuration so that Scene7 and AEM Assets can interact with one another. This document describes how to configure AEM and Scene7.

For information on using all the Scene7 components on a page and working with video, see [Using Scene7.](../../../assets/using/scene7.md)

>[!NOTE]
>
>* Scene7's DHTML viewer platform officially reached end-of-life on January 31, 2014. For more information see the [DHTML viewer end-of-life FAQ](../../../sites/administering/using/dhtml-viewer-endoflifefaqs.md).
>* Before configuring Scene7 to work with AEM, see [Best Practices](#bestpracticesforintegratingscene7withaem) for integrating Scene7 with AEM.
>* If you are using Scene7 with a custom proxy configuration, you need to configure both HTTP Client proxy configurations as some functionalities of AEM are using the 3.x APIs and some others the 4.x APIs. 3.x is configured with [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient) and 4.x is configured with [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator).
>

## AEM/Scene7 integration versus Dynamic Media {#aem-scene-integration-versus-dynamic-media}

AEM users have a choice between two solutions to work with dynamic media: Either integrating their instance of AEM with Scene7 or using the Dynamic Media solution that is integrated into AEM.

Use the following criteria to determine which solution to choose:

* If you are an **existing** Scene7 customer whose rich media assets reside in S7 for publishing and delivery, but you want to integrate those assets with Sites (WCM) authoring and/or AEM Assets for management, then use the [AEM/Scene7 point-to-point integration](#aemscene7pointtopointintegration) described in this document.

* If you are a **new** AEM customer who has rich media delivery needs, select the [Dynamic Media option](#aemdynamicmedia). This option makes the most sense if you do not have an existing S7 account and many assets stored in that system.

* In certain cases, you may want to use both solutions. The [dual-use scenario](../../../sites/administering/using/scene7.md#dualusescenario) describes that scenario.

### AEM/Scene7 point-to-point integration {#aem-scene-point-to-point-integration}

When you work with assets in this solution, you do one of the following:

* Upload assets directly to Scene7 and then access via the **Scene7** content browser for page authoring or
* Upload to AEM Assets and then enable automatic publishing to S7; you access via **Assets** content browser for page authoring

The components you use for this integration are found in the **Scene7** component area in [Design mode.](../../../sites/authoring/using/author-environment-tools.md#designmodeclassicui)  

### AEM Dynamic Media {#aem-dynamic-media}

AEM Dynamic Media is the unification of S7 features directly within the AEM platform.

When you work with assets in this solution, you follow this workflow:

1. Upload single image and video assets directly to AEM.
1. Encode videos directly within AEM.
1. Build image-based sets directly within AEM.
1. If applicable, add interactivity to images or videos.

The components you use for Dynamic Media are found in the **Dynamic Media** component area in [Design mode](../../../sites/authoring/using/author-environment-tools.md#designmodeclassicui). They include the following:

* **Dynamic Media** - The **Dynamic Media** component is smart - depending on whether you add an image or a video, you have various options. The component supports image presets, image-based viewers such as image sets, spin sets, mixed media sets, and video. In addition, the viewer is responsive - the size of the screen changes automatically based on screen size. All viewers are HTML5 viewers.

* **Interactive Media** - The **Interactive Media** component is for those assets, such as carousel banners, interactive images, and interactive video, that have interactivity on them such hotspots or image maps. This component is smart - depending on whether you add an image or a video, you have various options. In addition, the viewer is responsive - the size of the screen changes automatically based on screen size. All viewers are HTML5 viewers.

### Dual-Use Scenario {#dual-use-scenario}

Out of the box, you can use both Dynamic Media and Scene7 integration features of AEM simultaneously. The [Use cases](#usecases) table that follows describes when you turn certain areas on and off.

To use Dynamic Media and Scene7 simultaneously:

1. Configure [Scene7](#creatingacloudconfigurationforscene7) in cloud services.
1. Follow the specific instructions particular to your use case:

<table border="2" cellpadding="2" cellspacing="2" width="100%"> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> </td> 
   <td colspan="2"><strong>Dynamic Media</strong></td> 
   <td colspan="2"><strong>Scene7 Integration</strong></td> 
  </tr> 
  <tr> 
   <td><strong>If you are ...</strong></td> 
   <td><strong>Use Case Workflow</strong></td> 
   <td><strong>Imaging/Video</strong></td> 
   <td><strong>Dynamic Media Component</strong></td> 
   <td><strong>S7 Content Browser and Components</strong></td> 
   <td><strong>Automatic Upload from Assets to S7</strong></td> 
  </tr> 
  <tr> 
   <td>New to Sites and Dynamic Media</td> 
   <td>Upload assets to AEM and use AEM Dynamic Media component to author assets on Sites pages</td> 
   <td><p>On</p> <p>(See step 3)</p> </td> 
   <td><a href="../../../assets/using/adding-dynamic-media-assets-to-pages.md">On</a></td> 
   <td>Off</td> 
   <td>Off</td> 
  </tr> 
  <tr> 
   <td>In retail and are new to Sites and Dynamic Media</td> 
   <td>Upload NON-product assets to AEM for management and delivery. Upload PRODUCT assets to Scene7 and use Scene7 content browser in AEM and component to author Product Detail Pages on Sites.</td> 
   <td><p>On</p> <p>(See step 3)</p> </td> 
   <td><a href="../../../assets/using/adding-dynamic-media-assets-to-pages.md">On</a></td> 
   <td><a href="../../../assets/using/scene7.md#scene7contentbrowser">On</a></td> 
   <td>Off</td> 
  </tr> 
  <tr> 
   <td>New to Assets and Dynamic Media</td> 
   <td>Upload assets to AEM Assets and use published URL/embed code from Dynamic Media</td> 
   <td><p>On</p> <p>(See step 3)</p> </td> 
   <td>Off</td> 
   <td>Off</td> 
   <td>Off</td> 
  </tr> 
  <tr> 
   <td>New to Dynamic Media and Templating</td> 
   <td>Use Dynamic Media for imaging and video. Author image templates in Scene7 and use Scene7 content finder to include templates in Sites pages.</td> 
   <td><p>On</p> <p>(See step 3)</p> </td> 
   <td><a href="../../../assets/using/adding-dynamic-media-assets-to-pages.md">On</a></td> 
   <td><a href="../../../assets/using/scene7.md#scene7contentbrowser">On</a></td> 
   <td>Off</td> 
  </tr> 
  <tr> 
   <td>An existing Scene7 customer and are new to Sites</td> 
   <td>Upload assets to Scene7 and use AEM Scene7 content browser to search and author assets on Sites pages</td> 
   <td>Off</td> 
   <td>Off</td> 
   <td><a href="../../../assets/using/scene7.md#scene7contentbrowser">On</a></td> 
   <td>Off</td> 
  </tr> 
  <tr> 
   <td>An existing Scene7 customer and are new to Sites and Assets</td> 
   <td>Upload assets to DAM and automatically publish to Scene7 for delivery. Use AEM Scene7 content browser to search and author assets on Sites pages.</td> 
   <td>Off</td> 
   <td>Off</td> 
   <td><a href="../../../assets/using/scene7.md#scene7contentbrowser">On</a></td> 
   <td><p><a href="#configuringautouploadingfromaemassets">On</a></p> <p>(See step 4)</p> </td> 
  </tr> 
  <tr> 
   <td>Existing Scene7 customer and new to Assets</td> 
   <td><p>Upload assets to AEM and use Dynamic Media to generate renditions for download/share. Automatically publish AEM assets to Scene7 for delivery.</p> <p><strong>Important:</strong> Incurs duplicate processing and renditions generated in AEM will not be synchronized to Scene7</p> </td> 
   <td><p>On</p> <p>(See step 3)</p> </td> 
   <td>Off</td> 
   <td>Off</td> 
   <td><p><a href="#configuringautouploadingfromaemassets">On</a></p> <p>(See step 4)</p> </td> 
  </tr> 
 </tbody> 
</table>

1. Optional (please see use case table) - Set up the [Dynamic Media cloud configuration](../../../assets/using/config-dynamic.md) and [enable the Dynamic Media server](../../../assets/using/config-dynamic.md).
1. Optional (please see use case table) -- If you choose to enable Automatic Upload from Assets to Scene7, then you need to add the following:

    1. Set up automatic upload to Scene7.
    1. Add the **Scene7 upload** step after all the Dynamic Media workflow steps *at the end of* **Dam Update Asset** workflow ( `http://<server>:<host>/cf#/etc/workflow/models/dam/update_asset.html)`
    
    1. (Optional) Restrict Scene7 asset upload by MIME type in [http://&lt;server&gt;:&lt;port&gt;/system/console/configMgr/com.day.cq.dam.scene7.impl.Scene7AssetMimeTypeServiceImpl](http://localhost:4502/system/console/configMgr/com.day.cq.dam.scene7.impl.Scene7AssetMimeTypeServiceImpl). Asset MIME types not in this list will not be uploaded to Scene7 server.
    1. (Optional) Set up video in Scene7 configuration. You can enable video encoding for either or both Dynamic Media and Scene7 simultaneously. Dynamic renditions are used for preview and playback locally in AEM instance, whereas Scene7 video renditions are generated and stored on Scene7 servers. When setting up video encoding services for both Dynamic Media and Scene7, apply a [video processing profile](../../../assets/using/video-profiles.md) to the Scene7 asset folder.
    1. (Optional) [Configure Secure preview in Scene7](../../../sites/administering/using/scene7.md#configuringthestatepublishedunpublishedofassetspushedtoscene7).

#### Limitations {#limitations}

When you have both Scene7 and Dynamic Media enabled, there are the following limitations:

* Manually uploading to Scene7 by selecting an asset and dragging it to a Scene7 component on an AEM page does not work.
* Even though AEM-Scene7 synced assets are updated to Scene7 automatically when the asset is edited in Assets, a rollback action does not trigger a new upload, hence Scene7 would not get the latest version immediately after a rollback. The workaround is to edit again once rollback is complete.
* If you need to use Dynamic Media for one use case and Scene7 integration for another use case, so that the Dynamic Media assets do not interact with the Scene7 system, then do not to apply the Scene7 configuration to the Dynamic Media folder, or the Dynamic Media configuration (processing profile) to a Scene7 folder.

## Best Practices for Integrating Scene7 with AEM {#best-practices-for-integrating-scene-with-aem}

When integrating Scene7 with AEM, there are some important best practices that need to be observed in the following areas:

* Test-driving your integration
* Uploading assets directly from Scene7 recommended for certain scenarios

In addition, please see [known limitations](#knownlimitationsanddesignimplications).

### Test-driving your integration {#test-driving-your-integration}

Adobe recommends that you **test-drive your integration** by having your root folder pointing to a subfolder only rather than an entire company.

>[!CAUTION]
>
>Importing assets from an existing Scene7 company account may take a long time to show in AEM. Ensure that you designate a folder in Scene7 that does not have too many assets (for example, the root folder will often have too many assets and may crash your system).

### Uploading assets from AEM Assets versus from Scene7 {#uploading-assets-from-aem-assets-versus-from-scene}

You can upload assets either by using the Assets (digital asset management) functionality or by accessing Scene7 directly in AEM via the S7 content browser. Which one you choose depends on the following factors:

* S7 asset types that AEM Assets does not yet support have to be added to an AEM website from Scene7 directly, via the S7 content browser, for example, image templates.
* For asset types that are supported by both AEM Assets and Scene7, deciding how to upload them depends on the following:

    * Where the assets are today AND
    * How important managing them in a common repository is

If the assets are already in Scene7 and managing them in a common repository is not as important, then exporting them to AEM Assets only to sync them back to Scene7 for delivery would be an unnecessary roundtrip. Otherwise, keeping assets in a single repository and syncing to Scene7 only for delivery may be preferable.

## Configuring Scene7 integration {#configuring-scene-integration}

You can configure AEM to upload assets to Scene7. Assets from a CQ target folder can be uploaded (automatically or manually) from AEM to a Scene7 company account.

>[!NOTE]
>
>Adobe recommends that you use only the designated target folder for importing Scene7 assets. Digital assets that reside outside of the target folder can [only be used in Scene7 components on pages where the Scene7 configuration has been enabled](#publishingassetsfromoutsidethecqtargetfolder). In addition, they are placed in an ad hoc folder in Scene7. The adhoc folder is not synchronized with AEM (but assets are discoverable in the Scene7 content browser).

To configure Scene7 to integrate with AEM, you need to complete the following steps:

1. [Define a cloud configuration](#creatingacloudconfigurationforscene7), which defines the mapping between a Scene7 folder and an Assets folder. You need to complete this step even if you only want one-way (AEM Assets to Scene7) synchronization.
1. [Enable the **Adobe CQ s7dam Dam Listener**](#enablingtheadobecqscene7damlistener) in the OSGi console.
1. If you want AEM assets to [automatically upload to Scene7](#configuringautouploadingfromadobedam), you need to turn that option on and add Scene7 to the DAM update asset workflow. You can also manually upload assets.
1. [Adding Scene7 components to the sidekick](#addingascene7componenttoapage). This allows the users to use Scene7 components on their AEM pages.
1. [Map the configuration to the page in AEM](#enablingscene7forwcm). This step is required to view any video presets that you have created in Scene7. It is also required if you need to perform a [publish an asset from outside the CQ target folder to Scene7.](#publishingassetsfromoutsidethecqtargetfolder)

This section covers how to perform all of these steps and lists important limitations.

### How synchronization between Scene7 and AEM Assets works {#how-synchronization-between-scene-and-aem-assets-works}

When setting up AEM Assets and Scene7 synchronization, it is important to understand the following:

#### Uploading to Scene7 from AEM Assets {#uploading-to-scene-from-aem-assets}

* There is a designated synchronization folder in AEM for Scene7 uploads. 
* Uploads to Scene7 can be automated if the digital assets are placed in the designated synchronization folder.
* The folder and subfolder structure in AEM is replicated in Scene7.

>[!NOTE]
>
>AEM embeds all the metadata as XMP before uploading it to Scene7, so all properties on the metadata node are available in Scene7 as XMP.

#### Known limitations and design implications {#known-limitations-and-design-implications}

With the synchronization between AEM Assets and Scene7, there are currently the following limitations/design implications:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Limitation/design implication</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>1 designated synchronization (target) folder</td> 
   <td>You can only have one designated folder per company in AEM for Scene7 uploads. You can create multiple configurations if you need to have access to more than one company account in Scene7.</td> 
  </tr> 
  <tr> 
   <td>Folder structure</td> 
   <td>If you delete a synced folder with assets, all Scene7 remote assets are deleted but the folder remains.</td> 
  </tr> 
  <tr> 
   <td>Ad-hoc folder</td> 
   <td>Assets that reside outside the target folder that are manually uploaded to Scene7 in WCM are automatically placed in a separate ad-hoc folder on Scene7. You configure this in the cloud configuration in AEM.</td> 
  </tr> 
  <tr> 
   <td>Mixed media</td> 
   <td>Mixed media sets appear in AEM although they are not supported in AEM.</td> 
  </tr> 
  <tr> 
   <td>PDFs</td> 
   <td>Generated PDFs from eCatalogs in Scene7 will get imported into the CQ target folder.</td> 
  </tr> 
  <tr> 
   <td>UI refreshing</td> 
   <td>When synchronizing between AEM and Scene7, be sure to refresh the user interface to view changes. </td> 
  </tr> 
  <tr> 
   <td>Video thumbnails</td> 
   <td>If uploading a video to AEM Assets for encoding via Scene7, the video thumbnails and encoded videos may take some time to be available in AEM Assets, depending on video processing time.</td> 
  </tr> 
  <tr> 
   <td>Target subfolders</td> 
   <td><p>If you are using subfolders within the target folder, ensure that you either use unique names for each asset (regardless of location) or you configure Scene7 (in the Setup area) to not overwrite assets regardless of location.</p> <p>Otherwise, assets with the same name that are uploaded to a Scene7 target subfolder are uploaded, but the same-named asset in the target folder is deleted. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Configuring Scene7 servers {#configuring-scene-servers}

If you run AEM behind a proxy or have special firewall settings, you may need to explicitly enable the hosts of the different regions. Servers are managed in content in `/etc/cloudservices/scene7/endpoints` and can be customized as required. Click a URL and then edit to change the URL, if necessary. In previous versions of AEM, these values were hard-coded.

If you navigate to **/etc/cloudservices/scene7/endpoints.html**, you see the servers listed (and can edit them by clicking on the URL):

![](assets/chlimage_1-334.png) 

### Creating a cloud configuration for Scene7 {#creating-a-cloud-configuration-for-scene}

A cloud configuration defines the mapping between a Scene7 folder and an AEM Assets folder. It needs to be configured to synchronize AEM Assets with Scene7. See [How Synchronization Works](#howsynchronizationbetweenscene7andadobedamworks) for more information.

>[!CAUTION]
>
>Importing assets from an existing Scene7 company account may take a long time to show in AEM. Ensure that you designate a folder in Scene7 that does not have too many assets (for example, the root folder will often have too many assets).
>
>If you would like to test drive the integration, you may want to have the root folder point to a subfolder only, instead of the entire company.

>[!NOTE]
>
>You can have multiple configurations: one cloud configuration represents one user at a Scene7 company. If you want to access other Scene7 companies or users, you need to create multiple configurations.

To configure AEM to be able to publish assets to Scene7, perform the following steps:

1. Tap or click the AEM icon and navigate to **Deployment** &gt; **Cloud Services** to access Adobe Scene7.  

1. Click **Configure Now**.

   ![](assets/chlimage_1-335.png)

1. In the **Title** field, and optionally in the **Name** field, enter the appropriate information. Click **Create**.

   >[!NOTE]
   >
   >When creating additional configurations, the **parent configuration** field displays. 
   >
   >
   >Do **not** change the parent configuration. Changing the parent configuration can break the integration.

1. Enter the email address, password, and region of your Scene7 account and click **Connect to Scene7**. You are connected to the Scene7 server and the dialog expands with more options.  

1. Enter the **Company** name and **Root Path** (this is the published server name together with any path you want to specify; if you do not know the published server name, in Scene7, go to **Setup**, then **Application Setup**.)

   >[!NOTE]
   >
   >The Scene7 root path is the Scene7 folder AEM connects to. It can be narrowed down to a specific folder.

   >[!CAUTION]
   >
   >Depending on the size of the Scene7 folder, importing a root folder can take a long time. In addition, Scene7 data could exceed the AEM storage. Ensure you are importing the correct folder. Importing too much data can stop your system.

   ![](assets/chlimage_1-336.png)

1. Click **OK**. AEM saves your configuration.

>[!NOTE]
>
>If you are reconnecting:
>
>* When reconnecting to Scene7 on publish, you may need to reset the password on publish or reconnecting will not work. This is not an issue on the author instance.
>* If you modify values such as your region, company name, you must reconnect to Scene7. If configuration options have been modified but not saved, AEM erroneously still indicates that the configuration is valid. Be sure to reconnect.
>

### Enabling the Adobe CQ Scene7 Dam Listener {#enabling-the-adobe-cq-scene-dam-listener}

You must enable the Adobe CQ Scene7 Dam Listener, which is disabled by default.

To enable it:

1. Tap or click the Tools icon, then navigate to **Operations** &gt; **Web Console**. The Web console opens.
1. Navigate to **Adobe CQ Scene7 Dam Listener** and select the **Enabled** check box. 

   ![](assets/chlimage_1-337.png)

1. Tap or click **Save**.

### Adding configurable timeout to Scene7 Upload workflow {#adding-configurable-timeout-to-scene-upload-workflow}

When an AEM instance is configured to handle video encoding through Dynamic Media Classic (Scene7), by default, there is a 35-minute timeout on any upload job. To accommodate potentailly longer-running video encoding jobs, you can configure this setting:

1. Navigate to **http://localhost:4502/system/console/configMgr/com.day.cq.dam.scene7.impl.Scene7UploadServiceImpl**.

   ![](assets/chlimage_1-338.png)

1. Change the number as desired in the **Active job timeout** field. Any non-negative number is accepted with the unit of measure in seconds. By default, this is set to 2100.

   >[!NOTE]
   >
   >Best practice: Most assets are ingested within minutes at most (for example, images). But in certain instances - larger videos for example - the timeout value should be increased to 7200 seconds (2 hours) to accommodate long processing time. Otherwise, this Scene7 upload job is marked as **UploadFailed** in the JCR metadata.

1. Tap or click **Save**.

### Autouploading from AEM Assets {#autouploading-from-aem-assets}

Beginning with AEM 6.3.2, AEM Assets is now configured for you so that any digital assets that you upload to the digital asset manager are automatically updated to Scene7 if the assets are in a CQ target folder.

When an asset is added into AEM Assets, it is automatically uploaded and published to Scene7.

>[!NOTE]
>
>The maximum file size for automatic uploading from AEM Assets to Scene7 is 500 MB.

To configure autouploading from AEM Assets:

1. Tap or click the AEM icon and navigate to **Deployment** &gt; **Cloud Services** then, under the Dynamic Media heading, under Available Configurations, tap or click **dms7 (Dynamic Media**)
1. Click the **Advanced** tab and select the **Enable Automatic Upload** check box and click **OK**. You now need to configure the DAM Asset workflow to include uploading to Scene7.

   >[!NOTE]
   >
   >See [Configuring the state (published/unpublished) of assets pushed to Scene7](#configuringthestatepublishedunpublishedofassetspushedtoscene7) for information on pushing assets to Scene7 in an unpublished state.

   ![](assets/screen_shot_2018-03-15at52501pm.jpg)

1. Navigate back to the AEM welcome page and click **Workflows**. Double-click the** DAM Update Asset** workflow to open it.
1. In the sidekick, navigate to the **Workflow** components, and select **Scene7**. Drag **Scene7** to the workflow and click **Save**. Assets added to AEM Assets in the target folder will automatically be uploaded to Scene7.

   ![](assets/chlimage_1-339.png)

   >[!NOTE]
   >
   >
   >    
   >    
   >    * When adding assets after automating, if they are not placed in the CQ target folder, they are not uploaded to Scene7.
   >    * AEM embeds all the metadata as XMP before uploading it to Scene7, so all properties on the metadata node are available in Scene7 as XMP.
   >    
   >

### Configuring the state (published/unpublished) of assets pushed to Scene7 {#configuring-the-state-published-unpublished-of-assets-pushed-to-scene}

If you are pushing assets from AEM Assets to Scene7, you can either publish them automatically (default behavior) or push them to Scene7 in an unpublished state.

You may not want to publish assets immediately on Scene7 if you want to test them in a staging environment before going live. You can use AEM with Scene7's Secure Test environment to push assets directly from Assets into Scene7 in an unpublished state.

S7 assets remain available via secure preview. Only when assets are published within AEM do the S7 assets also go live in production.

If you want to publish assets immediately when pushing them to Scene7, you do not need to configure any options. This is the default behavior.

However, if you do not want assets pushed to Scene7 to publish automatically, this section describes how to configure AEM and Scene7 to do this.

#### Prerequisites to push assets to Scene7 unpublished {#prerequisites-to-push-assets-to-scene-unpublished}

Before you can push assets to Scene7 without publishing them, you must set up the following:

1. Contact Scene7 Customer Care (s7support@adobe.com) to enable secure preview for your Scene7 account. 
1. Follow directions to [setup secure preview for your Scene7 account.](http://help.adobe.com/en_US/scene7/using/WSd968ca97bf00cf72-5eeee3a113268dc80f5-8000.html)

These are the same steps you would follow to create any secure test setup in Scene7.

>[!NOTE]
>
>If your installation environment is a Unix 64-bit operating system, see [http://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html](http://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html) regarding additional configuration options you need to set.

#### Known Limitations for pushing assets in unpublished state  {#known-limitations-for-pushing-assets-in-unpublished-state}

If you use this feature, please note the following limitations:

* There is no support for version control.
* If an asset is already published in AEM and a subsequent version is created, that new version will be immediately published live to production. Publish upon activation only works with the initial publish of an asset.

>[!NOTE]
>
>If you want to publish assets instantly, best practice is to keep **Enable Secure Preview** set to **Immediately** and use the **Enable Automatic Upload** feature.

### Setting the state of assets pushed to Scene7 as unpublished {#setting-the-state-of-assets-pushed-to-scene-as-unpublished}

>[!NOTE]
>
>If a user publishes the asset in AEM, it automatically triggers the S7 asset to the production/live asset (the asset will no longer be in secure preview/unpublished).

To set the state of assets pushed to Scene7 as unpublished:

1. Tap or click the AEM icon and navigate to **Deployment** &gt; **Cloud Services**, click **Scene7**, and select your configuration in Scene7.
1. Click the **Advanced** tab. In the **Enable Secure View** drop-down menu, select **Upon AEM Publish Activation** to push assets to Scene7 without publishing. (By default, this value is set to **Immediately**, where Scene7 assets are published immediately.)

   See [Scene7 documentation](http://help.adobe.com/en_US/scene7/using/WSd968ca97bf00cf72-5eeee3a113268dc80f5-8000.html) for more information on testing assets before making them public.

   ![](assets/chlimage_1-340.png)

1. Click **OK**.

Enabling Secure View means that your assets are pushed to the secure preview server unpublished.

You can check this by navigating to a Scene7 component on a page in AEM and clicking **Edit**. The asset will have the secure preview server listed in the URL. After publishing in AEM, the server domain in the file reference gets updated from the preview URL to the production URL.

### Enabling Scene7 for WCM {#enabling-scene-for-wcm}

Enabling Scene7 for WCM is required for two reasons:

* To enable the drop-down list of universal video profiles for page authoring. Without this, the **Universal Video Preset** drop-down is empty and cannot be set.
* If a digital asset is not in the target folder, you can upload the asset to Scene7 if you enable Scene7 for that page in the page properties and drag and drop the asset on a Scene7 component. Normal inheritance rules apply (meaning that child pages will inherit the configuration from the parent page).

When enabling Scene7 for the WCM, note that as with other configurations, inheritance rules apply. You can enable Scene7 for WCM in either the touch-optimized or classic user interface.

#### Enabling Scene7 for WCM in the Touch-Optimized User Interface {#enabling-scene-for-wcm-in-the-touch-optimized-user-interface}

To enable Scene7 for WCM in the touch-optimized UI:

1. Tap or click the AEM icon and navigate to **Sites** and then the root page of your web site (not language specific).  

1. In the toolbar, select the settings icon and tap or click** Open Properties**.   

1. Tap or click **Cloud Services** and tap or click **Add Configuration **and select **Scene7**.
1. In the **Adobe Scene7** drop-down list, select the desired configuration and click **OK**.

   ![](assets/chlimage_1-341.png)

   Video presets from that configuration of Scene7 are available for use in AEM with the Scene7 video component on that page and child pages.

#### Enabling Scene7 for WCM in the Classic User Interface {#enabling-scene-for-wcm-in-the-classic-user-interface}

To enable Scene7 for WCM in the classic UI:

1. In AEM, click **Websites** and navigate to the root page of your web site (not language specific).  

1. In the sidekick, click the **Page** icon and click **Page Properties**.  

1. Click **Cloud Services** and click **Add services **and select **Scene7**.
1. In the **Adobe Scene7** drop-down list, select the desired configuration and click **OK**.

   Video presets from that configuration of Scene7 are available for use in AEM with the Scene7 video component on that page and child pages.

### Configuring a default configuration {#configuring-a-default-configuration}

If you have multiple Scene7 configurations, you can specify one of them as the default for the Scene7 content browser.

Only one Scene7 configuration can be marked as default at a given moment. The default configuration is the company assets that display by default in the Scene7 Content Browser.

To configure the default configuration:

1. Tap or click the AEM icon and navigate to** Deployment &gt; Cloud Services**, tap or click **Scene7**, and select your configuration in Scene7.
1. Click **Edit** to open the configuration.  

1. In the **General** tab, select the **Default Configuration **check box to make this the default company and root path that appears in the **Scene7 Content Browser**.

   ![](assets/chlimage_1-342.png)

   >[!NOTE]
   >
   >If there is only one configuration, selecting the **Default Configuration** check box has no effect.

### Configuring the Ad-hoc folder {#configuring-the-ad-hoc-folder}

You can configure the folder that assets are uploaded to in Scene7 when the asset is not located in the CQ target folder. See [Publishing assets from outside the CQ target folder.](#publishingassetsfromoutsidethecqtargetfolder)

To configure the adhoc folder:

1. Tap or click the AEM icon and navigate to **Deployment** &gt; **Cloud Services**, tap or click **Scene7**, and select your configuration in Scene7.
1. Tap or click **Edit** to open the configuration.  

1. Tap or click the **Advanced** tab. In the** Ad-hoc Folder **field, you can modify the **Ad-hoc** folder. By default, it is the **name_of_the_company/CQ5_adhoc**.

   ![](assets/chlimage_1-343.png)

### Configuring universal presets {#configuring-universal-presets}

To configure Universal Presets for the video component, see [Video](../../../assets/using/s7-video.md).

## Enabling MIME type-based Assets/Scene7 upload job parameter support {#enabling-mime-type-based-assets-scene-upload-job-parameter-support}

You can enable configurable Scene7 upload jobs parameters that are triggered by the synchronization of Digital Asset Manager/Scene7 assets.

Specifically, you configure the accepted file format by MIME type in the OSGi (Open Service Gateway initiative) area of the AEM Web Console Configuration panel. Then, you can customize the individual upload job parameters that are used for each MIME type in the JCR (Java Content Repository).

**To enable MIME type-based assets:**

1. Tap or click the AEM icon and navigate to **Tools** &gt; **Operations** &gt; **Web Console**.
1. In the Adobe Experience Manager Web Console Configuration panel, on the **OSGi** menu, tap **Configuration**.
1. Under the Name column, find and tap **Adobe CQ Scene7 Asset MIME type Service** to edit the configuration.
1. In the Mime Type Mapping area, tap any plus sign (+) to add a MIME type.

   See [Supported MIME types](../../../assets/using/assets-formats.md#supportedmimetypes).

1. In the text field, type the new MIME type name.

   For example, you would type a `<file_extension>=<mime_type>` as in `EPS=application/postscript` OR `PSD=image/vnd.adobe.photoshop`.

1. In the lower-right corner of the configuration window, tap **Save**.
1. Return to AEM and in the left rail, tap CRXDE Lite.
1. On the CRXDE Lite page, in the left rail, navigate to `/etc/cloudservices/scene7/<environment>` (substitute `<environment>` for the actual name).
1. Expand `<environment>` (substitute `<environment>` for the actual name) to reveal the `mimeTypes` node.
1. Tap the mimeType that you just added.

   For example, `mimeTypes > application_postscript` OR `mimeTypes > image_vnd.adobe.photoshop`.

1. On the right side of the CRXDE Lite page, tap the **Properties** tab.
1. Specify a Scene7 upload job parameter in the **jobParam** value field.

   For example, `psprocess="rasterize"&psresolution=120` .

   See the [Adobe Scene7 Image Production System API](https://marketing.adobe.com/resources/help/en_US/s7/ips_api/) for additional upload job parameters you can use.

   >[!NOTE]
   >
   >If you are uploading PSD files, process them as templates with layer extractions. To do so, enter the following in the **jobParam** value field:  

   >
   >
   >`process=MaintainLayers&createTemplate=true`
   >
   >
   >Be sure that your PSD file has “layers”. If it is strictly one image or an image with mask, it will only be processed as an image because there are no layers to process.

1. In the upper-left corner of the CRXDE Lite page, tap **Save All**.

## Troubleshooting Scene7 and AEM integration {#troubleshooting-scene-and-aem-integration}

If you are having trouble integrating AEM with Scene7, see the following scenarios for solutions.

**If your digital asset publishing to Scene7 fails:**

* Check that the the asset you are trying to upload is in the **CQ target** folder (you specify this folder in the Scene7 cloud configuration). 
* If it is not, you need to configure the cloud configuration in **Page Properties** for that page to allow uploading to the **CQ adhoc** folder.

* Check the logs for any information.

**If your video presets do not appear:**

* Ensure that you have configured the cloud configuration of that page through **Page Properties**. Video presets are avaialble in the Scene7 video component.

**If your video assets do not play in AEM:**

* Ensure that you used the correct video component. Scene7 video component is different than the foundation Video component. See [Foundation Video Component versus Scene7 Video Component](../../../assets/using/s7-video.md).

**If new or modified assets in AEM do not automatically upload to Scene7:**

* Ensure that the assets are in the CQ target folder. Only assets that are in the CQ target folder are automatically updated (provided you configured AEM Assets to automatically upload assets).
* Ensure that you have configured the Cloud Services configuration to Enable Automatic Uploading and that you have updated and saved the DAM Asset workflow to include Scene7 uploading.
* When uploading an image into a subfolder of the Scene7 target folder, ensure you do one of the following:

    * Make sure that the names of all assets regardless of location are unique. Otherwise the asset in the main target folder is deleted and only the asset in the subfolder remains.
    * Change how Scene7 overwrites assets in the Setup area of the Scene7 account. Do not set Scene7 to overwrite assets regardless of location if you use assets with the same name in subfolders.

**If your deleted assets or folders are not synchronized between Scene7 and AEM:**

* Assets and folders deleted in AEM Assets still show up in the synchronized folder in Scene7. You must delete them manually.

**If video upload fails**

* If your video upload fails and you are using AEM to encode video through the Scene7 integration, see [Adding configurable timeout to Scene7 Upload workflow](#addingconfigurabletimeouttoscene7uploadworkflow).

>[!CAUTION]
>
>Importing assets from an existing Scene7 company account may take a long time to show in AEM. Ensure that you designate a folder in Scene7 that does not have too many assets (for example, the root folder will often have too many assets).
>
>If you would like to test drive the integration, you may want to have the root folder point to a subfolder only, instead of the entire company.

