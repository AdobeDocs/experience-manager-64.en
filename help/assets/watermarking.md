---
title: Watermark your images
description: Use the watermarking feature to add a digital watermark to your PNG AND JPEG images.
contentOwner: AG
---

# Watermark your assets {#watermarking}

Adobe Experience Manager (AEM) Assets lets you add a digital watermark to images that helps users verify the authenticity and copyright ownership of the assets. AEM Assets supports text to be used as a watermark on PNG and JPEG files.

To be able to apply watermark on assets, add the [!UICONTROL Watermark] step in the [!UICONTROL DAM Update Asset] workflow.

1. Tap the AEM logo, and go to **[!UICONTROL Tools]** &gt; **[!UICONTROL Workflow]** &gt; **[!UICONTROL Models]**.
1. From the Workflow Models page, select the **[!UICONTROL DAM Update Asset]** workflow and click **[!UICONTROL Edit]**.  

1. From the side panel, drag the **[!UICONTROL Add Watermark]** step and add it to the [!UICONTROL DAM Update Asset] workflow.

   ![Darg add watermark step in the DAM update asset workflow](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Place the [!UICONTROL Add Watermark] step anywhere before the [!UICONTROL Process Thumbnail] step.

1. Open the **[!UICONTROL Add Watermark]** step to display its properties.
1. In the **[!UICONTROL Arguments]** tab, specify valid values in the various fields, including text, font type, size, color, position, orientation, and so on. To confirm the changes, tap/click the Done icon.

   ![Provide the arguments in the add watermark step in Assets](assets/arguments_add_watermark_aem_assets.png)

1. Save the **[!UICONTROL DAM Update Asset]** workflow with the [!UICONTROL Watermark] step.
1. From the AEM user interface, upload a sample asset. The watermark appears with the font size, color and so on, at the position that you configured in the above steps.
