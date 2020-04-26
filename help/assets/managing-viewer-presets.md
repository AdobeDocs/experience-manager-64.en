---
title: Managing Dynamic Media viewer presets
seo-title: Managing Dynamic Media viewer presets
description: How to create and manage Dynamic Media viewer presets
seo-description: How to create and manage Dynamic Media viewer presets
uuid: 31ef7a4e-2053-43b5-ac6c-cdc4b30c3914
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e78bb08a-a923-4399-b3f7-13aa4b7994d5
legacypath: /content/docs/en/aem/6-0/administer/integration/dynamic-media/viewer-presets
---

# Managing Dynamic Media viewer presets {#managing-viewer-presets}

A Dynamic Media viewer preset is a collection of settings that determine how users view rich-media assets on their computer screens and mobile devices. If you are an administrator, you can create Viewer Presets. Settings are available for an array of viewer configuration options. For example, you can change the viewer display size or zoom behavior.

For instructions on creating and customizing your own HTML5 viewer presets, see the *Adobe Scene7 HTML5 Viewer SDK*. The SDK is available on the IS publish server embedded in the SDK itself. Each library version has its own SDK documentation included.

Path: `<scene7_domain>/s7sdk/<library_version>/docs/jsdocs/index.html`.  
For example, 3.5 SDK: [https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html](https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html)

See also the [Adobe Viewers Reference Guide](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/).

This section describes how to create, edit, and manage viewer presets. You can apply a viewer preset to an asset anytime you preview it. See [Applying Viewer Presets](viewer-presets.md).

>[!NOTE]
>
>Be aware that editing any *predefined, out-of-the-box viewer presets* is not a supported scenario. If you attempt to edit an out-of-the-box viewer preset, you are prompted to save the viewer preset using a new name.

## Keyboard accessibility for viewers {#keyboard-accessibility-for-viewers}

All out-of-the-box viewers support keyboard accessibility.

See also [Keyboard accessiblity and navigation](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_keyboard_accessibility.html).

## Managing Dynamic Media viewer presets {#managing-presets}

You can add, edit, delete, publish, unpublish, and preview viewer presets in AEM by tapping **[!UICONTROL Tools > Assets > Viewer Presets]**.

![tools-assets](assets/tools-assets.png)

>[!NOTE]
>
>By default, the system shows 15 viewer presets when you select Viewers in an asset's detail view. You can increase this limit. See [Increasing the number of viewer presets that display](#increasing-the-number-of-viewer-presets-that-display).

## Viewer support for responsive designed web pages {#viewer-support-for-responsive-designed-web-pages}

Different web pages have different needs. For example, sometimes you want a web page that provides a link that opens the HTML5 Viewer in a separate browser window. In other cases, it may be necessary to embed the HTML5 Viewer directly on the hosting page. In the latter case, the web page may have a static layout. Or, it may be *responsive* and display differently on different devices or for different browser window sizes. To accommodate these needs, all the pre-defined, out-of-the-box HTML5 Viewers that come with Dynamic Media support both static web pages and responsive designed web pages.

See [Responsive Image library](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/c_about_responsive_static_image_library.html) in the *Scene7 Image Serving API Help* for more information on how to embed responsive viewers onto your web pages.

>[!NOTE]
>
>Please note that you must publish all out-of-the-box viewers before you first use them.  
>See [Publishing Viewer Presets.](#publishing-viewer-presets)

## Viewer preset system compatibility  {#viewer-preset-system-compatibility}

All out-of-the-box Viewer Presets that come with Dynamic Media are fully compatible with the following systems:

* Desktops
* Apple iPhone
* Apple iPad
* Android Smartphone
* Android Tablet
* For video, additional support for MP4 playback is provided for [Blackberry](https://developer.blackberry.com/devzone/develop/supported_media/bb_media_support_at_a_glance.html#kba1328730952678) and [Windows Phone](https://msdn.microsoft.com/library/windows/apps/ff462087%28v=vs.105%29.aspx).

### Rich media types for viewer presets {#rich-media-types-for-viewer-presets}

Administrators can add and customize the following rich media types when creating new viewer presets.

| Rich media types | Description |
|:---|:---|
| **Carousel Set** | Hotspots, or image maps, or both are added to a series of two or more images. A customer can pan the images left or right and then click a hotspot on an image for additional details or for purchasing directly from a website's category, home, or landing pages. |
| **Flyout Zoom** | Displays a second image of the zoomed area next to the original image. There are no controls to use - users move the selection over the area they want to view. |
| | When determining the complete bandwidth usage for this viewer, consider that both the main image and the flyout image are served in the viewer. The main image size (Stage Width and Height) and the Zoom Factor determine the flyout image size. To keep the flyout file size from becoming too large, balance these two values: if you have a large main image size, lower the Zoom Factor value. (The Flyout Width and Flyout Height determine the size of the flyout window, but not the size of the flyout image that is served into the viewer.) |
| | For example, if your main image size is 350 by 350 pixels, with a Zoom Factor of 3, the resulting flyout image is 1050 by 1050 pixels. If your main image size is 300 by 300 pixels, with a Zoom Factor of 4, the flyout image is 1200 by 1200 pixels. Depending on the JPEG quality setting (recommended settings are between 80-90), you can decrease the file size significantly. Recommended zoom factors are 2.5 to 4, depending on the size of your main image. |
| **Inline Zoom** | Displays an image of the zoomed area within the original viewer. There are no controls to use. That is, users move the selection over the area they want to view. |
| **Image Set** | In the Image Set viewer, users can see different views or color variations of an item by clicking a thumbnail image. This viewer also offers zooming tools for examining images closely. |
| **Interactive Image** | Hotspots are added to portions of an image that a customer can then click for additional details or for purchasing directly from a website's category, home, or landing pages. |
| **Interactive Video** | Thumbnails are added to timeline segments in a video that a customer can then click for additional details or for purchasing directly from a website's category, home, or landing pages. |
| **Mixed Media** | Displays different types of media in one viewer. You can include spin sets, image set, images, and videos. |
| **Panoramic Image** | The Panoramic Image and PanoramicVR viewers render spherical panoramic images to immerse users in a 360° viewing experience of a room, property, location, or landscape. |
| | For an uploaded image to qualify as a spherical panorama, it must have either one or both of the following: <ul><li>An aspect ratio of 2:1.</li><li>Tagged with the keywords equirectangular, or spherical and panorama, or spherical and panoramic. See [Using Tags](../sites-authoring/tags.md).</li></ul> |
| | Both the aspect ratio and keyword criteria apply to panoramic assets for the asset details page and the "Panoramic Media" WCM component. |
| | Important: This viewer is only available in Dynamic Media - Scene7 mode. |
| **Spin Set** | Provides multiple views of an image so users can turn the object to examine the different sides and angles. |
| **Video** | Plays video using progressive or adaptive bitrate streaming. Adaptive bitrate streaming automatically performs device and bandwidth detection to serve the right quality video in the right format. |
| **Vertical Zoom** | The Vertical Zoom viewer lets you maximize a product imagery viewing experience to give your users the best representation of a product. The vertical location of swatches does the following: <ul><li>Ensures swatches are above the fold. With horizontal swatches, depending on the users desktop screen size, swatches were not be visible until the user scrolled down the page. By placing the swatches vertically in the viewer, it ensures that they are visible no matter the user's screen size.</li><li>Maximizes main image size. With horizontal swatches, it is necessary to reserve space on the page to ensure that they are visible. This positioning decreased the size of the main image. With a vertical swatch layout, however, you do not need to allocate this space. As such, you can maximize the main image size.</li></ul> |
| **Zoom** | Lets users zoom into the area by clicking it. Users can click controls to zoom in, zoom out, and reset the image to its default size. |

## List of out-of-the-box viewer presets {#list-of-out-of-the-box-viewer-presets}

The following table identifies all pre-defined, out-of-box viewer presets that come with Dynamic Media.

See also [Viewers Reference Library Examples](https://marketing.adobe.com/resources/help/en_US/s7/vlist/vlist.html) and [Live Demos](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/live-demos.html).

For information about supported web browser and operating system versions for Viewers, you can review the Viewers Release Notes.

See *Viewers release notes* in the table of contents of the [Viewers Reference Guide](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/).

>[!NOTE]
>
>All out-of-the-box viewer presets in Dynamic Media come already activated (on), but you must publish them.  
>See [Publishing Viewer Presets](#publishing-viewer-presets).
>
>Any new viewer presets that you create and add must be both activated *and* published.  
>See [Activating or Deactivating Viewer Presets](#activating-or-deactivating-viewer-presets) and [Publishing Viewer Presets](#publishing-viewer-presets).

| Viewer preset title | Type | CSS file name |
|:---|:---|:---|
| Carousel_Dotted_dark | Carousel_Set | html5_carouselviewer_dotted_dark.css |
| Carousel_Dotted_light | Carousel_Set | html5_carouselviewer_dotted_light.css |
| Carousel_Numeric_dark | Carousel_Set | html5_carouselviewer_numeric_dark.css |
| Carousel_Numeric_light | Carousel_Set | html5_carouselviewer_numeric_light.css |
| Flyout | Flyout_Zoom | html5_flyoutviewer.css |
| ImageSet_dark | Image Set | html5_zoomviewer_dark.css |
| ImageSet_light | Image Set | html5_zoomviewer_light.css |
| InlineMixedMedia_dark | Mixed_Media | html5_inlinemixedmediaviewer_dark.css |
| InlineMixedMedia_light | Mixed_Media | html5_inlinemixedmediaviewer_light.css |
| InlineZoom | Flyout_Zoom | html5_inlinezoomviewer.css |
| MixedMedia_dark | Mixed_Media | html5_mixedmediaviewer_dark.css |
| MixedMedia_light | Mixed_Media | html5_mixedmediaviewer_light.css |
| PanoramicImage | Panoramic_Image | html5_panoramicimage.css |
| PanoramicImageVR | Panoramic_Image | html5_panoramicimage.css |
| Shoppable_Banner | Interactive_Image | html5_interactiveimage.css |
| Shoppable_Video_dark | Interactive_Video | html5_interactivevideoviewer_dark.css |
| Shoppable_Video_light | Interactive_Video | html5_interactivevideovewer_light.css |
| SpinSet_dark | Spin_Set | html5_spinviewer_dark.css |
| SpinSet_light | Spin_Set | html5_spinviewer_light.css |
| Video (Includes support for closed captioning) | Video | html5_videoviewer.css |
| Video_social (Includes support for closed captioning and social media) | Video | html5_videoviewersocial.css |
| Zoom_dark | Zoom | html5_basiczoomviewer_dark.css |
| Zoom_light | Zoom | html5_basiczoomviewer_light.css |
| ZoomVertical_dark | Vertical_Zoom | html5_zoomverticalviewer_dark.css |
| ZoomVertical_light | Vertical_Zoom | html5_zoomverticalviewer_light.css |

### Supported mobile viewers gestures matrix {#supported-mobile-viewers-gestures-matrix}

The following table identifies the mobile viewer gestures that are supported on iOS, Android 2.x, and Android 3.x devices.

| Gesture | Flyout Zoom | Zoom | Spin |
|---|---|---|---|
| **Drag** | Pans | Pans | Pans |
| **Tap** | Shows flyout window | Shows or hides the user interface | Shows or hides the user interface |
| **Double-tap** | Does not apply | Zooms in or resets | Zooms in or resets |
| **Pinch open** | Does not apply | Zooms in (iOS and Android 3x only) | Zooms in (iOS and Android 3x only) |
| **Pinch close** | Does not apply | Zooms out (iOS and Android 3x only) | Zooms out (iOS and Android 3x only) |
| **Swipe** | Scrolls swatch bar | Scrolls images | Spins |
| **Flick** | Scrolls swatch bar | Scrolls images | Spins |

## Increasing the number of Dynamic Media viewer presets that display {#increasing-the-number-of-viewer-presets-that-display}

AEM shows a wide variety viewer presets when viewing an assets from **[!UICONTROL Detail View > Viewers]**. You can increase or decrease the number of viewers that display.

**To increase the number of Dynamic Media viewer presets that display**:

1. Navigate to **[!UICONTROL CRXDE Lite]** ([http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Navigate to the viewer preset listing node at `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist`

   ![chlimage_1-221](assets/chlimage_1-221.png)

1. In the **[!UICONTROL limit]** property, change the **[!UICONTROL Value]**, which is set to 15 by default, to the desired number.
1. Navigate to the viewer preset datasource at `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist/datasource`

   ![chlimage_1-222](assets/chlimage_1-222.png)

1. In the **[!UICONTROL limit]** property, change the number to the desired number, for example `{empty requestPathInfo.selectors[1] ? "20" : requestPathInfo.selectors[1]}`
1. Tap **[!UICONTROL Save All]**.

## Creating a new Dynamic Media viewer preset {#creating-a-new-viewer-preset}

Creating viewer presets lets you apply various settings to view and interact with assets. However, you do not need to create new viewer presets. If you prefer, you can use the default, out-of-the-box viewer presets that already come with AEM Assets.

If you choose to create a new viewer preset, after you save it, the viewer's state is automatically activated (set to **On**) in the **[!UICONTROL Viewer Presets]** page. This state means that it is visible in the **[!UICONTROL Dynamic Media]** component and the **[!UICONTROL Interactive Media]** component and whenever you preview an image or video.

Some viewer presets have exclusive settings that can affect the use and overall behavior of the viewer. Depending on the viewer preset you are creating, you may want to be aware of these special considerations.

See [Special considerations for creating an Interactive Viewer preset](#special-considerations-for-creating-an-interactive-viewer-preset).

See [Special considerations for creating a Carousel Banner Viewer preset](#special-considerations-for-creating-a-carousel-banner-viewer-preset).

**To create a new Dynamic Media viewer preset**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.

   ![viewerpresets](assets/viewerpresets.png)

1. On the **[!UICONTROL Viewer Presets]** page, on the toolbar, tap **[!UICONTROL Create]**.
1. In the **[!UICONTROL New Viewer Preset]** dialog box, in the **[!UICONTROL Preset Name]** field, enter the name of the new preset. Choose a name carefully--they are not editable after you tap **[!UICONTROL Create]**.

   When you save the preset later in these steps, the name appears on the Viewer Presets page under the **[!UICONTROL Preset Title]** column header.

1. On the **[!UICONTROL Rich Media Type]** drop-down menu, select the type of viewer preset you want to create, then in the upper-right corner of the page, tap **[!UICONTROL Create]**.

   See [Rich Media Types for Viewer Presets](#rich-media-types-for-viewer-presets).

1. On the **Edit Viewer Preset** page, tap the **[!UICONTROL Appearance]** tab.
1. Do one of the following:

    * In the **[!UICONTROL Selected Type]** pull-down menu, select a component whose visual design you want to customize. Alternatively, you can tap any visual element in the viewer to select it for configuration.  
  
      The visual editor lets you see what effect a certain property has on a style. Just set or adjust any property to instantly see what effect it has on the viewer using the sample to the left of the editor.
  
      The CSS styling properties for each type of viewer preset are described in the any "Customizing *&lt;viewer_name&gt;* Viewer" Help topic in the [Viewers Reference Guide](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/).
  
      For example, if you are creating a viewer preset of the type `Mixed_Media`, see [Customizing Mixed Media Viewer](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_mixedmedia_viewer_customizingviewer.html) for a list and description of each property. 

    * If you have defined style settings in a separate CSS file, you can upload the CSS file to AEM Assets. Tap **[!UICONTROL Import CSS]** below the **[!UICONTROL Selected Type]** pull-down menu (you may need to scroll the visual editor up to see it) to find the uploaded CSS file and associate it with the viewer preset.  
  
      When you import a CSS file, the visual editor checks to see if the CSS uses the correct viewer markers. For example, if you are creating a Zoom viewer, all the CSS rules you import must be defined using its viewer class name `.s7mixedmediaviewer` defined on a parent viewer element.  
  
      You can import arbitrary, handmade CSS as long as it properly defines the CSS markers for a given viewer. (CSS markers are described in any "Customzing *&lt;viewer name&gt;* Viewer" Help topic in the [Viewers Reference Guide](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/). For example, if you want to read about CSS markers for the Zoom Viewer, see [Customizing Zoom Viewer](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_20_zoom_viewer_customizingviewer.html).) It is possible, however, that the visual editor may not understand some CSS values. In such cases, the visual editor attempts to override the errors so that the CSS can still work.

   >[!NOTE]
   >
   >If you prefer to edit the CSS directly in its raw form, tap **[!UICONTROL Show/Hide CSS]** below the **[!UICONTROL Selected Type]** pull-down menu (you may need to scroll the visual editor up to see it).
   >
   >Like the visual editor, when you make a change to a property directly in the CSS, you can instantly see what effect it has on the viewer sample. And, that same property is automatically updated at the same time in the visual editor. As such, you can use the raw CSS editor, or the visual editor, or use both interchangeably.

   >[!NOTE]
   >
   >For button artwork, choose the 2x image and upload high resolution art work. When working with interactive images and shoppable banners, you can also select from a variety of out-of-the-box hotspot buttons.

1. (Optional) Near the top of the **[!UICONTROL Edit Viewer Preset]** page, tap **[!UICONTROL Desktop]**, **[!UICONTROL Tablet]**, or **[!UICONTROL Phone]** to uniquely define visual styles for different device and screen types.
1. On the **[!UICONTROL Edit Viewer Preset]** page, tap the **Behavior** tab. Alternatively, you can tap or click any visual element in the viewer to select it for configuration.
1. From the **[!UICONTROL Selected Type]** pull-down menu, select a component whose behaviors you want to change.

   Many components in the visual editor have a detailed description associated with it. These descriptions appear within blue boxes when you expand a component to reveal its associated parameters.

   Some Viewer types have components that let you specify Image Serving commands in an **IS Command** text field. For a list of commands you can use, see the [Image Serving API Reference](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/image_serving_api_ref.html).

   >[!NOTE]
   >
   >**If you are using a touch device, such as a phone or tablet...**
   >
   >After you type a value in the text field, tap elsewhere in the user interface to submit the change and close the virtual keyboard. If you tap **[!UICONTROL Enter]**, no action occurs.

1. Near the upper-right corner of the page, tap **[!UICONTROL Save]**.
1. Publish your new viewer preset. You must publish the preset before you can use it on your website.

   See [Publishing Viewer Presets](#publishing-viewer-presets).

## Special considerations for creating an Interactive Viewer preset {#special-considerations-for-creating-an-interactive-viewer-preset}

**About Display Modes for image thumbnails in the panel**

When you create or edit an Interactive Video viewer preset, you have the choice of which **[!UICONTROL Display Mode]** setting to use when you select `InteractiveSwatches` from the **[!UICONTROL Selected Component]** pull-down menu under the **[!UICONTROL Behavior]** tab. The display mode you choose affects how and when thumbnails appear while the video is playing. You can choose either a `segment`display mode (default) or a `continuous`display mode.

| Display Mode | Description |
|---|---|
| [!UICONTROL Segment] | [!UICONTROL Segment] is the default display mode for the out-of-box Interactive Video Viewer presets Shoppable_Video_light and Shoppable_Video_dark and any Interactive Video Viewer presets that you create yourself. |
| | In this mode, when there are fewer thumbnails assigned to a video segment than the number of visible spots in the display panel, thumbnails from the next or previous sub-segments are not pulled in to fill any empty spots in the panel. That is, it preserves the display of swatches that were assigned to the particular video segment. |
| [!UICONTROL Continuous] | In [!UICONTROL Continuous] display mode, if the number of thumbnails in a segment is less than the number that are visible in the panel, the viewer automatically includes the display of thumbnails from the next segment, or the previous segment, in cases where the last thumbnail is displayed. |

**About Auto Scrolling Behavior in the Interactive Video Viewer**

The auto scroll behavior of thumbnails in the Interactive Video viewer functions independently of the display mode that you chose.

When you create or edit an interactive video viewer preset, you access **[!UICONTROL Auto Scroll]** from the **[!UICONTROL Behavior]** tab. In the Behavior tab, from the **[!UICONTROL Selected Components]** drop-down menu, tap **[!UICONTROL InteractiveSwatches]**. The **[!UICONTROL Auto Scroll]** check box is listed below the IS Command text field.

If you disable **[!UICONTROL Auto Scroll]** (clear the check box) in the viewer preset, during video playback by the user, the panel only displays the first thumbnail image for the entire length of the video. However, a user can manually scroll through the thumbnails using the up and down arrow icons, if desired.

When you enable (select) **[!UICONTROL Auto Scroll]** in the viewer preset, during video playback, thumbnail images assigned to a video segment scroll into view at the start of a segment. There are instances, however, where certain thumbnails within a segment display twice as long as other thumbnails before or after it. This behavior occurs because the number of thumbnails in a segment is greater than the number that are visible in the panel, and are not evenly divisible.

To illustrate, suppose you have one 30 second video segment. And, there are a total of nine thumbnails to display over the 30 seconds. Your browser is sized in such a way that there are four visible thumbnail positions in the display panel. The 30 second video time segment is divided into three sub-segments. The following table shows the breakdown of which thumbnails are displayed for a given time sub-segment:

| **Video sub-segment** |**Sub-segment time in seconds** |**Thumbnails that are visible in the panel** |
|---|---|---|
| 1 |0-10 |1, 2, 3, 4 |
| 2 |10-20 |4, 5, 6, 7 |
| 3 |20-30 |6, 7, 8, 9 |

Video sub-segment 3 does not extend beyond the thumbnails that are assigned to it. Notice also that thumbnails 4, 6, and 7 are visible in the panel twice as long as the other thumbnails.

The logic that the viewer uses for how many thumbnails are displayed in the panel based on the number of available positions is as follows:

* Number of sub-segments = round up to next sub-segment (number of thumbnails / number of visible slots in the thumbnail panel, based on browser window size).  

  Using the example in the table above, 9 thumbnails / 4 slots = 2.25; the viewer logic rounds it up to 3 sub-segments.

* Number of thumbnails = round up to next thumbnail (number of thumbnails / number of video sub-segments).  

  Using the example in the table above, 9 thumbnails / 3 video sub-segments = 3 thumbnails.

* Duration of sub-segment = total video duration / number of video sub-segments.  

  Using the example in the table above, 30 seconds / 3 video sub-segments = 10 second display of each video sub-segment.

### Special considerations for creating a Carousel Banner viewer preset {#special-considerations-for-creating-a-carousel-banner-viewer-preset}

When creating Carousel Banner viewer presets, changing the style of hotspots can be accessed as follows:

| |**Description** |**Actions** |
|---|---|---|
| **Hotspot Icon** |Change the icon used for hotspot |To change the hotspot icon image, in the **[!UICONTROL Appearance]** tab, in **[!UICONTROL Selected Component]**, tap **[!UICONTROL ImageMapEffect]**. Under **[!UICONTROL Icon]**, select **[!UICONTROL Background]** and in the **[!UICONTROL Image]** field navigate to the background image you want. |

## Activating or deactivating Dynamic Media viewer presets {#activating-or-deactivating-viewer-presets}

The Viewer Presets that are available in the user interface depends on which ones are active in Author mode. By default, a viewer preset is *On* after you create it. If you toggle the preset off, you will not see it in Author mode. If the preset is published. it will always be published regardless of whether it is toggled on or off. You may want to deactivate viwer presets if the list becomes too unwieldy or you do not want a viewer preset made available to use.

**To activate or deactivate Dynamic Media viewer presets**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. On the **[!UICONTROL Viewer Preset]** page, under the **[!UICONTROL State]** column header, tap the toggle to activate or deactivate a viewer preset.

   Viewer presets that are activated have the toggle appear on the right, inside a blue box; deactivated viewer presets have the toggle appear on the left, inside a light grey box.

## Publishing Dynamic Media viewer presets {#publishing-viewer-presets}

Activating (or turning *On*) the state of a viewer preset means that it is visible in the Dynamic Media component, the Interactive Media component, and whenever you view an asset.

However, to deliver an asset with a viewer preset, the viewer preset must be published as well. All viewer presets must be activated *and* published to obtain URL or embed code for an asset. You must activate and publish all out-of-the-box viewer presets that come with Dynamic Media. Custom viewer presets that you create and add are auto-activated, but must also be published.

See [Activating or Deactivating Viewer Presets](#activating-or-deactivating-viewer-presets).

See also [Previewing Assets](previewing-assets.md).

**To publish Dynamic Media viewer presets**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Select one or more viewer presets that you want to publish.
1. On the toolbar, tap the **[!UICONTROL Publish]** icon.

## Sorting Dynamic Media viewer presets {#sorting-viewer-presets}

**To sort Dynamic Media viewer presets**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **Tools** (hammer icon) **[!UICONTROL > Assets > Viewer Presets]**.
1. Click **[!UICONTROL Preset Title]**, **[!UICONTROL Type]**, **[!UICONTROL Published]**, or **[!UICONTROL State]** to sort by that column heading. For example, click **[!UICONTROL Type]** to sort the viewer preset types in alphabetical or reverse-alphabetical order.

## Editing Dynamic Media viewer presets {#editing-viewer-presets}

Be aware that editing any *predefined, out-of-the-box viewer presets* is not a supported scenario. If you edit an out-of-the-box viewer preset, you are prompted to save it with a new name.

**To edit Dynamic Media viewer presets**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Select a preset by checking the box to the left of the viewer preset title.
1. On the toolbar, tap **[!UICONTROL Edit]**.
1. On the **[!UICONTROL Edit Viewer Preset]** page make the changes you want to the viewer preset.
1. Do one of the following:

    * Tap **[!UICONTROL Save]** to save your changes and return to the **[!UICONTROL Viewer Preset]** page.
    * Tap **[!UICONTROL Cancel]** to void any changes you made and return to the **[!UICONTROL Viewer Preset]** page.

## Deleting custom Dynamic Media viewer presets {#deleting-custom-viewer-presets}

You can delete Viewer Presets that you have created and added to Dynamic Media.

**To delete custom Dynamic Media viewer presets**:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. On the **[!UICONTROL Viewer Presets]** page, check a **[!UICONTROL Preset Title]**, and then tap the **[!UICONTROL Trash]** icon.
1. Tap **[!UICONTROL Delete]**.

## Applying a Dynamic Media viewer preset to an asset {#applying-a-viewer-preset-to-an-asset}

If you have already published both the asset and the selected viewer, the **[!UICONTROL URL]** and **[!UICONTROL Embed]** buttons appear after you select a viewer preset.

**To apply a Dynamic Media viewer preset to an asset**:

1. Open the asset and near the upper-left corner of the page, tap the drop-down menu, then select **[!UICONTROL Viewers]**.

   >[!NOTE]
   >
   >If you have already published both the asset and the selected viewer, the **[!UICONTROL URL]** and **[!UICONTROL Embed]** buttons appear after you select a viewer preset.

1. Select a viewer preset from the left pane to apply it to the asset.

   You can [copy the URL to share](linking-urls-to-yourwebapplication.md) with other users.

## Delivering assets with Dynamic Media viewer presets {#delivering-assets-with-viewer-presets}

To get the URLs for Viewer Presets, see [Linking URLs to your Web application](linking-urls-to-yourwebapplication.md). See also [Embedding the Video Viewer on a Web Page](embed-code.md).

If you are using AEM as your WCM, you can add assets using the viewer presets directly on the page. See [Adding Dynamic Media Assets to Pages](adding-dynamic-media-assets-to-pages.md).
