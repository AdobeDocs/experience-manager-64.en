---
title: Image Profiles
seo-title: Image Profiles
description: Create image profiles that contain settings for unsharp mask, and smart crop, or smart swatch, or both, then apply the profile to a folder of image assets.
seo-description: Create image profiles that contain settings for unsharp mask, and smart crop, or smart swatch, or both, then apply the profile to a folder of image assets.
uuid: 8148c88b-60be-4a79-b108-8a07b9c1784a
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 2dd40cb7-47f4-4162-9823-786c58071f2e
index: y
internal: n
snippet: y
---

# Image Profiles{#image-profiles}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-77F410094CD97C4F0A746C1B@AdobeID)
Last Modified Date: 2017-11-30T05:29:14.643-0500
<p>Currently still says image processing profile</p>
-->

When uploading images, you can automatically crop the image upon upload by applying an Image Profile to the folder.

>[!NOTE]
>
>Smart Crop is available only in Dynamic Media - Scene7 mode.

### Crop Options {#crop-options}

You have two image cropping options to choose from and an option for automating the creation of color and image swatches.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Option</strong></td> 
   <td><strong>When to use</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>Pixel Crop</td> 
   <td>Bulk crop images based on dimensions only.</td> 
   <td><p>To use this option, select <strong>Pixel Crop</strong> from the Cropping Options drop-down list.</p> <p>To crop from the sides of an image, you enter the number of pixels to crop from any side or each side of the image. How much of the image is cropped depends on the ppi (pixels per inch) setting in the image file.</p> <p>An Image Profile pixel crop renders in the following manner:<br /> </p> 
    <ul> 
     <li>Values are Top, Bottom, Left, and Right.</li> 
     <li>Top left is considered 0,0 and the pixel crop is calculated from there.</li> 
     <li>Crop starting point: Left is X and Top is Y</li> 
     <li>Horizontal calculation: horizontal pixel dimension of original image minus Left and then minus Right.</li> 
     <li>Vertical calculation: vertical pixel height minus Top, and then minus Bottom.</li> 
    </ul> <p>For example, suppose you have a 4000 x 3000 pixel image. You use values: Top=250; Bottom=500; Left=300; Right=700.</p> <p>From Top Left (300,250) crop using the fill space of (4000-300-700, 3000-250-500, or 3000,2250).</p> </td> 
  </tr> 
  <tr> 
   <td>Smart Crop</td> 
   <td>Bulk crop images based on their visual focal point.</td> 
   <td><p>Smart Crop uses the power of artificial intelligence in Adobe Sensei to quickly automate the cropping of images in bulk. Smart Crop automatically detects and crops to the focal point in any image to capture the intended point of interest, regardless of screen size.</p> <p>To use Smart Crop, select <strong>Smart Crop</strong> from the Cropping Options drop-down list, then to the right of Responsive Image Crop, enable (turn on) the feature.</p> <p>The default breakpoint sizes of Large, Medium, and Small generally cover the full range of sizes that most images are used on mobile and tablet devices, desktops, and banners. If desired, you can edit the default names of Large, Medium, and Small.</p> <p>To add more breakpoints, click <strong>Add Crop</strong>; to delete a crop, click the Garbage Can icon.</p> </td> 
  </tr> 
  <tr> 
   <td>Color and Image Swatch</td> 
   <td>Bulk generate an image swatch for each image.</td> 
   <td><p><strong>Note</strong>: Smart Swatch is not supported in Dynamic Media Classic.</p> <p>Automatically locate and generate high-quality swatches from product images that show color or texture.</p> <p>To use Color and Image Swatch, select <strong>Smart Crop</strong> from the Cropping Options drop-down list, then to the right of Color and Image Swatch, enable (turn on) the feature. Enter a pixel value in the Width and Height text boxes.</p> <p>While all image crops are available from the Renditions rail, swatches are only used by way of the Copy URL feature. Note that you must use your own viewing component to render the swatch on your site. (The exception to this is carousel banners. Dynamic Media provides the viewing component for the swatch used in carousel banners.)</p> <p><strong>Using image swatches</strong></p> <p>The URL for image swatches is straightforward. That is:</p> <p><span class="code">/is/image/company/&lt;asset_name&gt;:Swatch</span></p> <p>where <span class="code">:Swatch</span> is appended to the asset request.</p> <p><strong>Using color swatches</strong></p> <p>To use color swatches, you make a <span class="code">req=userdata</span> request with the following:</p> <p><span class="code">/is/image/&lt;company_name&gt;/&lt;swatch_asset_name&gt;:Swatch?req=userdata</span></p> <p>For example, the following is a swatch asset in Dynamic Media Classic (Scene7):</p> <p><span class="code">http://my.company.com:8080/is/image/DemoCo/Sleek:Swatch</span></p> <p>and here is the swatch asset's corresponding <span class="code">req=userdata</span> URL:</p> <p><span class="code">http://my.company.com:8080/is/image/DemoCo/Sleek:Swatch?req=userdata</span></p> <p>The <span class="code">req=userdata</span> response is as follows:</p> <p><code class="code">SmartCropDef=Swatch
       SmartCropHeight=200.0
       SmartCropRect=0.421671,0.389815,0.0848564,0.0592593,200,200
       SmartCropType=Swatch
       SmartCropWidth=200.0
       SmartSwatchColor=0xA56DB2</code></p> <p>You can also request a <span class="code">req=userdata</span> response in either XML or JSON format, as in the following respective URL examples:</p> <p><span class="code">http://<span class="code">my.company.com</span>:8080/is/image/DemoCo/Sleek:Swatch?req=userdata,json</span><br /> <br /> <span class="code">http://my.company.com:8080/is/image/DemoCo/Sleek:Swatch?req=userdata,xml</span></p> <p><strong>Note</strong>: You must create your own WCM component to request a color swatch and parse the <span class="code">SmartSwatchColor</span> attribute, represented by a 24-bit RGB hexidecimal value.</p> <p>See also <a href="https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/http_ref/r_userdata.html" target="_blank">userdata in the Viewers Reference Guide</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-03-06T17:33:38.750-0500
"Crop Options" is new for 6.4. Select Pixel Crop from Cropping Options. RB: updated.
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-03-06T17:33:16.137-0500
To turn on: Select Smart crop from Cropping Options. RB: updated.
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-03-06T17:33:06.327-0500
Color swatch has been removed for this release; only Image swatch is available. RB: updated.
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-03-20T17:22:54.573-0400
As per CQDOC-12211
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-28T17:44:46.051-0500
This is incorrect. It isn't based on pixels per inch. They are straight pixel dimensions. You're subtracting the pixel amounts from all sides. Here is how Image Profiles pixel crop will render. Values are: Top, Bottom, Left, and Right Top left is considered 0,0 and crop is calculated from there. Crop starting point is: Left is X and Top is Y Horizontal is calculated like this: horizontal pixel dimension of original image minus Left and then minus Right. Vertical is calculated like this: vertical pixel height minus Top and then minus Bottom. For example, I have a 4000x3000 image. I use values: Top = 250, Bottom = 500, Left = 300, Right = 700 From top left (300,250) crop using the fill space of (4000-300-700, 3000-250-500 or 3000,2250) You can read how Image Serving handles crop here: https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/http_ref/r_crop.html This is crop= and not cropN= RB: updated description
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-28T15:06:31.295-0500
I'm not sure why the mention of asterisk is added here, since it applies to both pixel drop and smart crop RB: Mention of asterisk was removed.
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-27T17:02:56.997-0500
Delete the sentence starting with, "Entering a breakpoint in pixels..." The next paragraph covers this. RB: Fixed.
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-28T15:01:40.317-0500
It should be mentioned somewhere that Smart Crop is only available with Dynamic Media Scene7. RB: added Note above.
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T18:54:28.098-0400
remove ", for example"
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:20:17.357-0400
It needs to be mentioned that Smart Swatch is not supported with Classic Scene7 because the swatch example below could confuse people into thinking it'll work with the old system, which it won't
-->

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-28T14:58:02.541-0500
Internal server names should be changed to be generic in some way, or changed to live demo servers RB: switched from using s7saigon.macromedia.com to my.company.com
-->

### Unsharp Mask {#unsharp-mask}

You use** Unsharp mask** to fine-tune a sharpening filter effect on the final downsampled image. You can control intensity of effect, radius of the effect (measured in pixels), and a threshold of contrast that will be ignored. This effect uses the same options as Adobe Photoshop’s “Unsharp Mask” filter.

>[!NOTE]
>
>Unsharp mask is only applied to downscaled renditions within the PTIFF (pyramid tiff) that are downsampled more than 50%. That means that the largest-sized renditions within the ptiff are not affected by unsharp mask whereas smaller-sized renditions such as thumbnails are altered (and will show the unsharp mask).

In **Unsharp Mask**, you have the following filtering options:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Option</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>Amount</td> 
   <td>Controls the amount of contrast applied to edge pixels. The default is 1.75. For high-resolution images, you can increase it to as high as 5. Think of Amount as a measure of filter intensity. Range is 0-5.</td> 
  </tr> 
  <tr> 
   <td>Radius</td> 
   <td>Determines the number of pixels surrounding the edge pixels that affect the sharpening. For high-resolution images, enter from 1 through 2. A low value sharpens only the edge pixels; a high value sharpens a wider band of pixels. The correct value depends on the size of the image. The default value is 0.2. Range is 0-250.</td> 
  </tr> 
  <tr> 
   <td>Threshold</td> 
   <td><p>Determines the range of contrast to ignore when the unsharp mask filter is applied. In other words, this option determines how different the sharpened pixels must be from the surrounding area before they are considered edge pixels and are sharpened. To avoid introducing noise, experiment with values between 0-255.</p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-11-27T17:19:13.524-0500
Remove "Radius-" at the end rb: FIXED
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:14:58.273-0400
Threshold requires an integer. values of 0.02 and 0.2 are not allowed
-->

Sharpening is described in [Sharpening Images](https://marketing.adobe.com/resources/help/en_US/s7/sharpening/s7_sharpening_images.pdf).

## Creating image profiles {#creating-image-profiles}

To define advanced processing parameters for other asset types, see [Configuring Asset Processing](../../assets/using/config-dms7.md#configuringassetprocessing).

**To create image profiles**:

1. Tap or click the AEM logo and navigate to **Tools **&gt; **Assets **&gt; **Image Profiles.**
1. Tap or click **Create** to add a new image profile.
1. Enter a profile name, and values for unsharp mask, crop, or swatch, or both.

   You may find it helpful to use a profile name that is specific to its intended purpose. For example, if you want to create a profile that generates swatches only--that is, Smart Crop is disable (turned off) and Color and Image Swatch is enabled (turned on)--you could use the profile name "Smart Swatches".

   See also [Smart Crop and Smart Swatch Options](#smart-crop-and-smart-swatch-options) and [Unsharp Mask](#unsharp-mask).

   ![](assets/Crop.png)

1. Click **Save**. The newly created profile appears in the list of available profiles.

## Editing or deleting image profiles {#editing-or-deleting-image-profiles}

1. Tap or click the AEM logo and navigate to **Tools **&gt; **Assets **&gt; **Image Profiles.**
1. Select the image profile you want to edit or remove. To edit it, select **Edit Image Processing Profile**. To remove it, select **Delete Image Processing Profile**.

   ![](assets/chlimage_1-203.png)

1. If editing, save the changes. If deleting, confirm that you want to remove the profile.

## Applying an image profile to folders {#applying-an-image-profile-to-folders}

When you assign an image profile to a folder, any subfolders automatically inherit the profile from its parent folder. This means that you can assign only one image profile to a folder. As such, consider carefully the folder structure of where you upload, store, use, and archive assets.

If you assigned a different image profile to a folder, the new profile overrides the previous profile. The previously existing folder assets remain unchanged. The new profile is applied on the assets that are added to the folder later.

Folders that have a profile assigned to it are indicated in the user interface by the name of the profile appearing in the card.

When you add smart crop to an existing image profile, you need to re-trigger the [DAM Update Asset workflow](../../assets/using/assets-workflow.md) if you want to generate crops for existing assets in your asset repository.

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:27:12.315-0400
Maybe this should read more like, "When you add smart crop to an existing image profile," As it is written right now, it could be confused with adding an image profile to a new folder. Also, maybe add a link to a Timeline page that describes how to re-trigger a Workflow?
-->

You can apply image profiles to specific folders or globally to all assets.

### Applying image profiles to specific folders {#applying-image-profiles-to-specific-folders}

You can apply an image profile to a folder from within the **Tools** menu or if you are in the folder, from **Properties**. This section describes how to apply image profiles to folders both ways.

Folders that have a profile already assigned to it are indicated by the display of the profile's name directly below the folder name.

#### Applying image profiles to folders from Profiles user interface {#applying-image-profiles-to-folders-from-profiles-user-interface}

1. Tap or click the AEM logo and navigate to **Tools **&gt; **Assets **&gt; **Image Profiles.**
1. Select the image profile that you want to apply to a folder or multiple folders.

   ![](assets/chlimage_1-204.png)

1. Tap/click **Apply Processing Profile to Folder(s) **and select the folder or multiple folders you want use to receive the newly uploaded assets and tap/click **Apply**. Folders that have a profile already assigned to it are indicated by the display of the profile's name directly below the folder name.

#### Applying image profiles to folders from Properties {#applying-image-profiles-to-folders-from-properties}

1. Tap or click the AEM logo and navigate to **Assets **and then to the folder that you want to apply an image profile to.
1. On the folder, tap or click the check mark to select it and then tap or click **Properties**.
1. Tap the **Image Profiles** tab. From the Profile Name drop-down list, select the profile, then click **Save & Close**. Folders that have a profile already assigned to it are indicated by the display of the profile's name directly below the folder name.

   <!--
   Comment Type: annotation
   Last Modified By: wyamashi
   Last Modified Date: 2018-08-17T14:56:01.730-0400
   You won't be able to see this while in Properties
   -->

   ![](assets/chlimage_1-205.png)

### Applying an image profile globally {#applying-an-image-profile-globally}

In addition to applying a profile to a folder, you can also apply one globally so that any content uploaded into AEM assets in any folder has the selected profile applied.

To apply a profile globally, do one of the following:

* Navigate to **http://&lt;AEM server&gt;/mnt/overlay/dam/gui/content/assets/foldersharewizard.html/content/dam** and apply the appropriate profile and tap or click **Save**.

  ![](assets/chlimage_1-206.png)

* Navigate to CRXDE Lite to the following node: **/content/dam/jcr:content.**

  Add the property** imageProfile:/conf/global/settings/dam/adminui-extension/imageprofile/&lt;name of image profile&gt; **and tap **Save All**.

  <!--
  Comment Type: annotation
  Last Modified By: rbrough
  Last Modified Date: 2018-03-06T17:37:50.155-0500
  Are these CRXDE Lite paths still legitimate for 6.4? No, the location has changed: /conf/global/settings/dam/adminui-extension/imageprofile/
  <name image="" of="" profile="">
  RB: updated
  </name>
  -->

  <!--
  Comment Type: annotation
  Last Modified By: wyamashi
  Last Modified Date: 2018-08-16T19:39:31.872-0400
  Maybe split this up a bit, since that includes more than just the Property name
  -->

  ![](assets/configure_image_profiles.png)

## Editing the smart crop or smart swatch of a single image {#editing-the-smart-crop-or-smart-swatch-of-a-single-image}

<!--
Comment Type: annotation
Last Modified By: rbrough
Last Modified Date: 2018-03-06T16:09:47.896-0500
New to 6.4
-->

>[!NOTE]
>
>Smart Crop is only available in Dynamic Media - Scene7 mode.

You can manually realign or resize the smart crop window of an image to further refine its focal point.

After you edit a smart crop and save, the change is propagated everywhere you use the crop for the specific images.

You can re-run smart crop to generate the additional crops again, if required.

See also [Editing the smart crop or smart swatch of multiple images](#editingthesmartcroporsmartswatchofmultipleimages).

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:40:35.148-0400
change "clhange" to "change"
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:41:18.274-0400
I have not tested Smart Crop so my knowledge is very limited. I'll assume that the information presented here is correct
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:42:07.275-0400
This link just goes to the top of the page
-->

1. Tap or click the AEM logo and navigate to **Assets**, then to the folder that has a smart crop or smart swatch image profile applied to it.  

1. Tap or click the folder to open its contents.
1. Tap or click the image whose smart crop or smart swatch you want to adjust.
1. On the toolbar, tap or click **Smart Crop**.  

1. Do any of the following:

    * Near the upper-right corner of the page, drag the slider bar left or right to increase or decrease the image display, respectively.
    * On the image, drag a corner handle to adjust the size of the viewable area of the crop or swatch.
    * On the image, drag the box/swatch to a new location. You can only edit image swatches; color swatches are static.
    * Above the image, tap or click **Revert** to undo all your edits and restore the original crop or swatch.

   <!--
   Comment Type: annotation
   Last Modified By: robinv
   Last Modified Date: 2018-03-06T16:27:57.412-0500
   We have a bug with Smart crops. If you edit the smart crop and make the area smaller then the output image may show whitespace: https://jira.corp.adobe.com/browse/CQ-4233847
   -->

1. Near the upper-right corner of the page, tap or click **Save**, then tap or click **Close** to return to the folder of assets.

## Editing the smart crop or smart swatch of multiple images {#editing-the-smart-crop-or-smart-swatch-of-multiple-images}

After you apply an image profile--containing Smart Crop--to a folder, all images in that folder have a crop applied to them. If desired, you can manually realign or resize the smart crop window in multiple images to further refine their focal point.

After you edit a smart crop and save, the change is propagated everywhere you use the crop for the specific images.

You can re-run smart crop to generate the additional crops again, if required.

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:46:30.573-0400
The way this is written, it sounds like, if I apply an Image Profile that has Smart Crop to a Folder, all Image Assets in that Folder are reprocessed to include Smart Crop. Is that correct?
-->

<!--
Comment Type: annotation
Last Modified By: wyamashi
Last Modified Date: 2018-08-16T19:47:06.633-0400
change "clhange" to "change"
-->

1. Tap or click the AEM logo and navigate to **Assets**, then to a folder that has a smart crop or smart swatch image profile applied to it.
1. On the folder, tap or click the **More Actions** (...) icon, then tap or click **Smart Crop**.  

1. On the Edit Smart Crops page, do any of the following:

    * Adjust the viewing size of images on the Edit Smart Crops page.  
      To the right of the breakpoint name drop-down list, drag the slider bar left or right to change the size of the viewable image display.

   ![](assets/edit_smart_crops-sliderbar.png)

    * Filter the list of viewable images based on breakpoint names. In the example below, the images are filtered on the breakpoint name "Medium".  
      Near the upper-right corner of the page, from the drop-down list, select a breakpoint name to filter on what images you see. (See the image above.)

   ![](assets/edit_smart_crops-dropdownlist.png)

    * Resize the smart crop box. Do any one of the following:

        * If the image has a smart crop or a smart swatch only, on the image, drag the corner handle of the crop box to adjust the size of the viewable area of the crop.
        * If the image has both a smart crop and a smart swatch, on the image, drag the corner handle of the crop box to adjust the size of the viewable area of the crop. Or, tap or click the smart swatch below the image (color swatches are static), then drag the corner handle of the crop box to adjust the size of the viewable area of the swatch.

   ![Resizing the smart crop of an image.](assets/edit_smart_crops-resize.png)

    * Move the smart crop box. Do any one of the following:

        * If the image has a smart crop or a smart swatch only, on the image, drag the crop box to a new location.
        * If the image has both a smart crop and a smart swatch, on the image, drag the smart crop box to a new location. Or, tap or click the smart swatch below the image (color swatches are static), then drag the smart swatch crop box to a new location.

   ![](assets/edit_smart_crops-move.png)

    * Undo all your edits and restore the original smart crop or smart swatch (applies to the current editing session only).  
      Tap or click **Revert **above the image.

   ![](assets/edit_smart_crops-revert.png)

1. Near the upper-right corner of the page, tap or click **Save**. then tap or click **Close **to return to the folder of assets.

## Removing an image profile from folders {#removing-an-image-profile-from-folders}

When you remove an image profile from a folder, any subfolders automatically inherit the removal of the profile from its parent folder. However, any processing of files that has occurred within the folders remains intact.

You can remove an image profile from a folder from within the **Tools** menu or if you are in the folder, from **Properties**. This section describes how to remove image profiles from folders both ways.

#### Removing image profiles from folders via Profiles user interface {#removing-image-profiles-from-folders-via-profiles-user-interface}

1. Tap or click the AEM logo and navigate to **Tools **&gt; **Assets **&gt; **Image Profiles.**
1. Select the image profile that you want to remove from a folder or multiple folders.
1. Tap **Remove Processing Profile from Folder(s) **and select the folder or multiple folders you want use to remove the profile from and tap **Remove**.

   You can confirm that the image profile is no longer applied to a folder because the name no longer appears below the folder name.

   <!--
   Comment Type: annotation
   Last Modified By: wyamashi
   Last Modified Date: 2018-08-17T14:50:34.616-0400
   Change "Done" to "Remove"
   -->

#### Removing image profiles from folders via Properties {#removing-image-profiles-from-folders-via-properties}

1. Tap or click the AEM logo and navigate **Assets **and then to the folder that you want to remove an image profile from.
1. On the folder, tap or click the check mark to select it and then tap or click **Properties**.
1. Select the **Image Profiles** tab and select **None** from the **Profile Name **drop-down menu and click **Save & Close**. Folders that have a profile already assigned to it are indicated by the display of the profile's name directly below the folder name.

   <!--
   Comment Type: annotation
   Last Modified By: wyamashi
   Last Modified Date: 2018-08-16T19:53:14.407-0400
   Now "Save" is "Save & Close"
   -->

   <!--
   Comment Type: annotation
   Last Modified By: wyamashi
   Last Modified Date: 2018-08-17T15:08:17.151-0400
   You won't be able to see this while in Properties
   -->

