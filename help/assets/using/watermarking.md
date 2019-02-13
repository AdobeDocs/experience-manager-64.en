---
title: Watermarking
seo-title: Watermarking
description: Learn how to use the Watermarking feature to add a digital watermark to assets.
seo-description: Use the Watermarking feature to add a digital watermark to assets, which helps users verify your authenticity and ownership of copyright of the assets.
uuid: 30c96366-eb56-443f-bfea-6ebcdbb23a78
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: ea570e2d-24e0-4448-88ce-adeb15b0ef8f
index: y
internal: n
snippet: y
---

# Watermarking{#watermarking}

Learn how to use the Watermarking feature to add a digital watermark to assets.

The Watermarking feature in Adobe Experience Manager (AEM) Assets lets you add a digital watermark to assets, which helps users verify the authenticity and copyright ownership of the assets. AEM Assets supports text to be used as a watermark to watermark the web-renderable image formats, such as GIF, PNG, JPEG, and BMP.

To be able to apply watermark on assets, add the Watermark step in the DAM Update Asset workflow.

1. Tap/click the AEM logo, and go to **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. From the Workflow Models page, select the **[!UICONTROL DAM Update Asset]** workflow and click **[!UICONTROL Edit]**.  

1. From the Side Panel, drag the **[!UICONTROL Add Watermark]** step to the DAM Update Asset workflow.

   ![Darg add watermark step in the DAM update asset workflow](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Place the Add Watermark step anywhere before the Process Thumbnail step.

1. Open the **[!UICONTROL Add Watermark]** step to display its properties.
1. In the **[!UICONTROL Arguments]** tab, specify valid values in the various fields, including text, font type, size, color, position, orientation, and so on. To confirm the changes, tap/click the Done icon.

   ![Provide the arguments in the add watermark step in Assets](assets/arguments_add_watermark_aem_assets.png)

1. Save the **[!UICONTROL DAM Update Asset]** workflow with the Watermark step.
1. From the Assets user interface, upload a sample asset. The watermark appears with the font size, color and so on, at the position you configured in the above steps.

