---
title: Adding Scene7 Features to your Page
seo-title: Adding Scene7 Features to your Page
description: Learn how to add Scene7 features and components to your AEM page.
seo-description: Learn how to add Scene7 features and components to your AEM page.
uuid: 91218a65-02c0-4737-a187-fa10cd0014ba
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: managing-assets
discoiquuid: dfdb9d49-f018-458e-a0a0-703fdcd72819
---

# Adding Scene7 Features to your Page{#adding-scene-features-to-your-page}

[Adobe Scene7](http://help.adobe.com/en_US/scene7/using/WS26AB0D9A-F51C-464e-88C8-580A5A82F810.html) is a hosted solution for managing, enhancing, publishing, and delivering rich media assets to Web, mobile, email, and Internet-connected displays and print.

You can view AEM assets published in Scene7 in various viewers:

* Zoom
* Flyout
* Video
* Image Template
* Image

You can publish digital assets directly from AEM to Scene7 and you can publish digital assets from Scene7 to AEM.  

This document describes how to publish digital assets from AEM to Scene7 and vice versa. Viewers are also described in detail. For information on configuring AEM for Scene7, see [Integrating Scene7 with AEM](../../sites/administering/using/scene7.md).  

See also [Adding Image Maps](../../assets/using/image-maps.md).  

For more information on using video components with AEM, see the following:

* [Video](../../assets/using/video.md)

>[!NOTE]
>
>If Scene7 assets do not display properly, please make sure that Dynamic media is [disabled](../../assets/using/config-dynamic.md#disablingdynamicmedia) and then refresh the page.

## Manually Publishing to Scene7 from Assets {#manually-publishing-to-scene-from-assets}

You can publish digital assets to Scene7 as follows:

* [In the classic user interface from the Assets console](../../sites/classic-ui-authoring/using/manage-assets-classic-s7.md#publishingfromtheassetsconsole)
* [In the classic user interface from an asset](../../sites/classic-ui-authoring/using/manage-assets-classic-s7.md#publishingfromanasset)
* [In the classic user interface from outside the the CQ Target folder](../../sites/classic-ui-authoring/using/manage-assets-classic-s7.md#publishingassetsfromoutsidethecqtargetfolder)

>[!NOTE]
>
>AEM publishes to Scene7 asynchronously. After you click **Publish**, it may take several seconds for your asset to publish to Scene7.
>

## Scene7 Components {#scene-components}

The following Scene7 components are available in AEM:

* Zoom
* Flyout (Zoom)
* Image Template
* Image
* Video

>[!NOTE]
>
>These components are not available by default and need to be selected in Design mode before using.

After they are made available in Design mode, you can add the components to your page like any other AEM component. Assets that have not yet been published to Scene7 are published to Scene7 if in a synchronized folder or on a page or with a Scene7 cloud configuration.

>[!NOTE]
>
>If you are creating and developing custom S7 viewers and using the Content Finder, you need to explicity add the **allowfullscreen** parameter.

### Flash Viewers End-of-Life Notice {#flash-viewers-end-of-life-notice}

Effective January 31, 2017, Adobe Scene7 will officially end-of-life support for the Flash viewer platform.

For more information about this important change, see [Flash Viewer End-of-Life FAQs](https://docs.adobe.com/content/docs/en/aem/6-1/administer/integration/marketing-cloud/scene7/flash-eol.html).

### Adding a Scene7 Component to a Page {#adding-a-scene-component-to-a-page}

Adding a Scene7 component to a page is the same as adding a component to any page. Scene7 components are described in detail in the following sections.

To add a Scene7 component/viewer to a page in the touch-optimized UI:

1. In AEM, open the page where you want to add the Scene7 component.  

1. If no Scene7 components are available, click **Design** mode, tap/click any component with a blue border, click the Parent icon, and then the Configuration icon. In **Parsys (Design)**, select all the **Scene7** components to make them available and click **OK**.

   ![](assets/chlimage_1-229.png)

1. Click **Edit** to return to Edit mode.  

1. Drag a component from the **Scene7** group in the sidekick onto the page in the desired location.  

1. Click the **Configuration** icon to open the component.  

1. Edit the component as necessary and click **OK** to save changes.
1. Drag your image or video from the content browser onto the Scene7 component you added to the page.

   >[!NOTE]
   >
   >In touch UI only, you must drag and drop the image or video onto the Scene7 component you placed on the page. Selecting and editing the Scene7 component and then choosing the asset is not supported.

### Adding interactive viewing experiences to a responsive website {#adding-interactive-viewing-experiences-to-a-responsive-website}

Responsive design for your assets means that your assets adapts depending on where it is displayed. With responsive design, the same assets can be effectively displayed on multiple devices.

See also [Responsive Design for Web Pages](../../sites/developing/using/responsive.md).

To add an interactive viewing experience to a responsive site in the touch-optimized UI:

1. Log in to AEM, and ensure that you have [configured Adobe Scene7 Cloud Services](../../sites/administering/using/scene7.md#configuringscene7integration) and that Scene7 components are available.

   >[!NOTE]
   >
   >If Scene7 WCM components are not available, be sure [to enable them via Design mode](../../sites/authoring/using/author-environment-tools.md#designmodeclassicui). [](../../sites/authoring/using/default-components-designmode.md)

1. In a website with the Scene7 components enabled, drag an **Image** component to the page.
1. Select the component and tap or click the configuration icon.
1. In the **Scene7 Settings** tab, adjust the breakpoints.

   ![](assets/chlimage_1-230.png)

1. Confirm that the viewers are responsively resizing and that all interactions are optimized for desktop, tablet, and mobile.

### Settings common to all Scene7 components {#settings-common-to-all-scene-components}

Although configuration options vary, the following are common to all Scene7 components:

* **File Reference **- Browse to a file that you want to reference. File reference shows the asset URL and not necessarily the full Scene7 URL including the URL commands and parameters. You cannot add Scene7 URL commands and parameters in this field. They have to be added through the corresponding functionality in the component.
* **Width** - Lets you set the width.
* **Height** - Lets you set the height.

You set these configuration options by opening (double-clicking) a Scene7 component, for example, when you open a **Zoom** component:

![](assets/chlimage_1-231.png) 

### Zoom {#zoom}

The HTML5 Zoom component displays a larger image when you press the + button.

The asset has zoom tools at the bottom. Click **+** to enlarge. Click **-** to reduce. Clicking the **x** or the reset zoom arrow brings the image back to the original size it was imported as. Click the diagonal arrows to make it full screen. Click **Edit** to configure the component. With this component, you can configure [settings common to all Scene7 components](#settingscommontoallscene7components).

![](assets/chlimage_1-232.png) 

### Flyout {#flyout}

In the HTML5 Flyout component, the asset is shown as split screen; left the asset in the specified size; right the zoom portion is displayed. Click **Edit** to configure the component. With this component, you can configure [settings common to all Scene7 components](../../sites/administering/using/scene7.md#settingscommontoallscene7components).

>[!NOTE]
>
>If your Flyout component uses a custom size, then that custom size is used and responsive setup of the component is disabled.
>
>If your Flyout component uses the default size, as set in the Design view, then the default size is used and the component stretches to accomodate the page layout size with responsive setup of the component enabled. Be aware, however, that there is a limitation on responsive setup of the component. When the you use the Flyout component with responsive setup, you should not use it with full page stretch. Otherwise, the Flyout may extend beyond the page's right border.

![](assets/chlimage_1-233.png) 

### Image {#image}

The Scene7 Image component lets you add Scene7 functionality to your images, such as Scene7 modifiers, image or viewer presets, and sharpening. The Scene7 image component is similar to other image components in AEM with special Scene7 functionality. In this example, the image has the Scene7 URL modifier, **&op_invert=1** applied.

![](assets/chlimage_1-234.png)

**Title, Alt Text** In the Advanced tab, add a title to the image and alt text for those users who have graphics turned off.

**URL, Open in** You can set an asset from to open a link. Set the URL and in Open in indicate whether you want it to open in the same window or a new window.

![](assets/chlimage_1-235.png)

**Viewer preset** Select an existing viewer preset from the drop-down menu. If the viewer preset you are looking for is not visible, you may need to make it visible. See Managing Viewer Presets. You cannot select a viewer preset if you are using an image preset and vice versa.

**Scene7 Configuration** Select the Scene7 configuration you want to use to fetch active image presets from the SPS.

**Image preset** Select an existing image preset from the drop-down menu. If the image preset you are looking for is not visible, you may need to make it visible. See Managing Image Presets. You cannot select a viewer preset if you are using an image preset and vice versa.

**Output Format** Select the output format of the image, for example jpeg. Depending on the output format you select, you may have additional configuration options. See Image Preset best practices.

**Sharpening** Select how you want to sharpen the image. Sharpening is explained in detail in Image Preset best practices and Sharpening best practices.

**URL Modifiers** You can change image effects by supplying additional S7 image commands. These are described in Image Presets and the Command reference.

**Breakpoints** If your website is responsive, you want to adjust the breakpoints. Breakpoints must be separated by commas (,).

### Image Template {#image-template}

[Scene7 Image Templates](http://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) are layered Photoshop content that was imported to Scene7, where content and properties were parameterized for variability. The** Image template** component lets you import images and change the text dynamically in AEM. In addition, you can configure the **Image template** component to use values from client context, so that each user experiences the image in a personalized way.

Click **Edit** to configure the component. You can configure [settings common to all Scene7 components](../../sites/administering/using/scene7.md#settingscommontoallscene7components) as well as other settings described in this section.

![](assets/chlimage_1-236.png)

**File Reference, Width, Height** See settings common to all Scene7 components.

>[!NOTE]
>
>Scene7 URL commands and parameters cannot be added to the File Reference URL directly. They can only be defined in the component UI in the **Parameter** panel.

**Title, Alt Text** In the Scene7 Image Template tab, add a title to the image and alt text for those users who have graphics turned off.

**URL, Open in** You can set an asset from to open a link. Set the URL and in Open in indicate whether you want it to open in the same window or a new window.

![](assets/chlimage_1-237.png)

**Parameter Panel** When importing an image, the parameters are pre-populated with information from the image. If there is no content that can be dynamically changed, this window is empty.

![](assets/chlimage_1-238.png) 

#### Changing text dynamically {#changing-text-dynamically}

To change the text dynamically, enter new text in the fields and click **OK**. In this example, the **Price** is now $50 and shipping is 99 cents.

![](assets/chlimage_1-239.png)

The text in the image changes. You can reset the text back to the original value by clicking **Reset** next to the field.

![](assets/chlimage_1-240.png) 

#### Changing text to reflect the value of a client context value {#changing-text-to-reflect-the-value-of-a-client-context-value}

To link a field to a client context value, click **Select** to open the client-context menu, select the client context, and click **OK**. In this example, the name changes based on linking the Name with the formatted name in the profile.

![](assets/chlimage_1-241.png)

The text reflects the name of the currently logged in user. You can reset the text back to the original value by clicking **Reset **next to the field.

![](assets/chlimage_1-242.png) 

#### Making the Scene7 image template a link {#making-the-scene-image-template-a-link}

To make the Scene7 image template component a clickable link:

1. On the page with the Scene7 image template component, click **Edit**.
1. In the **URL** field, enter the URL that users go to when the image is clicked. In the **Open in** field, select whether you want the target to open (a new window or same window). 

   ![](assets/chlimage_1-243.png)

1. Click **OK**.

### Video component {#video-component}

The Scene7 **Video** component (available from the Scene7 section of the sidekick) uses device and bandwidth detection to serve the right video to each screen. This component is an HTML5 video player; it is a single viewer that can be used cross channel.

It can be used for adaptive video sets, a single MP4 video, or a single F4V video.

See [Video](../../assets/using/s7-video.md) for more information on how videos work with Scene7 integration. In addition, see how [the **Scene7 video **component compares to the foundation **video** component](../../assets/using/s7-video.md). 

![](assets/chlimage_1-244.png) 

### Known limitations for the video component {#known-limitations-for-the-video-component}

Adobe DAM and WCM shows if a master video is uploaded. They do not show these proxy assets:

* Scene7 encoded renditions
* Scene7 adaptive video sets

When using an adaptive video set with the Scene7 video component, the component will need to resized to fit he dimensions of the video.

### Excluding master videos from adaptive video sets {#excluding-master-videos-from-adaptive-video-sets}

See [Excluding master videos from adaptive video sets](../../sites/administering/using/scene7.md#excludingmastervideosfromadaptivevideosets).

## Scene7 Content Browser {#scene-content-browser}

The Scene7 content browser lets you view content from Scene7 directly in AEM. To access the content browser, in the Content Finder, select **Scene7** in the touch-optimized user interface or the **S7** icon in the classic user interface. Functionality is identical between both user interfaces.

If you have multiple configurations, AEM by default displays the [default configuration](../../sites/administering/using/scene7.md#configuringadefaultconfiguration). You can select different configurations directly in the Scene7 content browser in the drop-down menu.

>[!NOTE]
>
>* Assets located in the ad-hoc folder will not appear in the Scene7 content browser.
>* When [Secure Preview is enabled](../../sites/administering/using/scene7.md#configuringthestatepublishedunpublishedofassetspushedtoscene7), both published and unpublished assets on Scene7 do appear in the Scene7 content browser.
>* If you do not see **Scene7 **or the** S7 **icon as an option in the content browser, you need to [configure Scene7 to work with AEM](../../sites/administering/using/scene7.md).
>
>* For video, the Scene7 content browser supports: >
>    * Adaptive Video Sets: container of all video renditions needed for seamless playback across multiple screens
>    * Single MP4 video 
>    * Single F4V video 
>

### Browsing content in the Touch-optimized UI {#browsing-content-in-the-touch-optimized-ui}

You can access the content browser either in the touch-optimized or classic UI. Currently the touch-optimized has the following limitation:

* FXG and Flash assets from Scene7 are not supported.

Browse Scene7 assets by selecting **Scene7** from the third drop-down menu. Scene7 does not appear in the list if you have not configured Scene7/AEM integration.

>[!NOTE]
>
>* The Scene7 content browser loads about 100 assets and sorts them by name. 
>* If you have a secure preview server set, the browser will use that preview server to render thumbnails and assets.
>

![](assets/chlimage_1-245.png)

In addition, you can browse resolution information, size, days since modification, and file name by hovering over the asset in the browser.

![](assets/chlimage_1-246.png)

* For Adaptive Video Sets and Templates, no size information is generated for thumbnails.
* For Adaptive Video Sets, no resolution is generated for thumbnails.

### Searching for Scene7 assets with the content browser {#searching-for-scene-assets-with-the-content-browser}

Searching for Scene7 assets is similar to searching AEM assets except that when you search you are actually seeing a remote view of the assets in the Scene7 system, rather than importing them directly into AEM.

You can use either the classic UI or the touch-optimized UI to both view and search for assets. Depending on the interface, how you search is slightly different.

When searching in either UI, you can filter by the following criteria (shown here in the touch-optimized UI):

**Enter keywords** You can search assets by name. When searching the keywords you enter is what the file name starts with. For example, typing the word "swimming" would look for any asset file names that start with those letters in that order. Be sure to click enter after you type the term to find the asset.

![](assets/chlimage_1-247.png)

**Folder/path** The name of the folder that appears is based on the configuration you have selected. You can drill down to lower levels by clicking the folder icon and selecting a sub-folder, then clicking the checkmark to select it.

If you enter a keyword and select a folder, AEM searches that folder and any sub-folders. However, if you do not enter any keywords when searching, selecting the folder will only show the assets in that folder and will not include any subfolders.

By default, AEM searches the folder selected and all sub-folders.

![](assets/chlimage_1-248.png)

**Type of Asset** Select Scene7 to browse Scene7 content. This option is only available if Scene7 has been configured.

![](assets/chlimage_1-249.png)

**Configuration** If you have more than one Scene7 configuration defined in Cloud Services, you can select it here. As a result the folder will change based on the configuration you have chosen.

![](assets/chlimage_1-250.png)

**Asset type** Within the Scene7 browser, you can filter results to include any of the following: images, templates, videos, and adaptive video sets. If you do not select any asset type, AEM by default searches all asset types.

![](assets/chlimage_1-251.png)

>[!NOTE]
>
>* In the classic UI, you can also search for **Flash** and **FXG**. Filtering for these in the touch-optimized UI is currently not supported.
>
>* When searching video, you are searching a single rendition. Results return the original rendition (only &#42;.mp4) and the encoded rendition.
>* When searching an adaptive video set, you are searching the the folder and all sub-folders but only if you have added a keyword to the search. If you have not added a keyword, AEM does not search the sub-folders.
>

**Publish Status** You can filter for assets based on publication status: Unpublished or Published. If you do not select any Publish Status, AEM by default searches all publish statuses.

![](assets/chlimage_1-252.png)

