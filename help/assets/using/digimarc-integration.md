---
title: Integrating digital non-visible watermarking (Digimarc) with Dynamic Media
seo-title: Integrating digital non-visible watermarking (Digimarc) with Dynamic Media
description: Learn how to integrate Digimarc digital watermarking to weave a unique, imperceptible, and traceable identifier into image assets.
seo-description: Learn how to integrate Digimarc digital watermarking to weave a unique, imperceptible, and traceable identifier into image assets.
page-status-flag: never-activated
uuid: 8f1df07d-361c-487f-a9cf-6b428a2a8cb2
contentOwner: rbrough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 0cf7d47e-645f-4f6c-b91e-f6be9344383f
index: y
internal: n
snippet: y
---

# Integrating digital non-visible watermarking (Digimarc) with Dynamic Media{#integrating-digital-non-visible-watermarking-digimarc-with-dynamic-media}

Dynamic Media supports Digimarc digital watermarking, which weaves a unique, imperceptible, and traceable identifier into images. The Digimarc tracking system monitors the Internet and specified URLs, locating digitally watermarked images and delivering reports to brand owners. This tracking system ensures that channel partners are acting in compliance with marketing guidelines for campaigns and new product roll-out. And, it allows legal departments to effectively communicate and enforce image copyrights.

To integrate Digimarc Barcode with image assets in Dynamic Media, you need your Digimarc license. Your license identifies your Digimarc user ID, PIN, and whether you are licensed as a Creator or a Distributor.

You can set the level for Digimarc durability. If you plan to alter images dynamically (through image adjustments or by displaying images at dramatically different sizes), set the durability to 4 (the strongest setting). This setting ensures that watermarks are recognized. The Digimarc ID is also enabled on the Dynamic Media Image Server. Any images that were created and saved from operations like Export are marked with the corresponding Digimarc identification.

**To integrate Digimarc with Dynamic Media:**

1. Create a support ticket and request that Digimarc be configured for your Dynamic Media. At the time the ticket is create you will need to include the following information that is provided by Digimarc:

    * Type: (Creator or Distributor, as licensed)
    * ID
    * PIN
    * Durability: 4 (Strongest)
    * Mode: Chroma

   Support will configure your Digimarc credentials with your account.

   >[!NOTE]
   >
   >Only users with Admininstrator rights to your Dynamic Media account can request this configuration from Adobe Support.

1. Step text
1. After the publish is complete, you can verify a watermark by requesting any Dynamic Media image asset. Do one of the following:

    * Save the image locally. Open the image in PhotoShop CS5 or above. On the Photoshop menu bar, tap **Filter** &gt; **Digimarc** &gt; **Read Watermark**.   
      If Digimarc is missing from the Filter menu, you may need to install the free Photoshop extension from [Adobe Exchange (www.adobeexchange.com) &gt; Creative Cloud &gt; Photoshop &gt; Digimarc Barcode for Digital Images](https://www.adobeexchange.com/creativecloud.details.12783.html). Digimarc is a subscription service.  
    
    * Download the following tool to verify the Digimarc within the browser: [https://www.digimarc.com/solutions/images/downloads.asp](https://www.digimarc.com/solutions/images/downloads.asp)

1. Step text

