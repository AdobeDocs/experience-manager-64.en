---
title: Integrating Landing Pages with Adobe Analytics
seo-title: Integrating Landing Pages with Adobe Analytics
description: Learn how to integrate landing pages with Adobe Analytics.
seo-description: Learn how to integrate landing pages with Adobe Analytics.
uuid: 6a8b0e81-ee45-44b8-a904-5df14e7f7667
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 6ded8a85-19fd-42f5-a7d8-86daed49824b
index: y
internal: n
snippet: y
---

# Integrating Landing Pages with Adobe Analytics{#integrating-landing-pages-with-adobe-analytics}

AEM has integrated the landing pages solution with [Adobe Analytics](http://www.omniture.com/en/products/analytics/sitecatalyst) by using the following call-to-action (CTA) components:

1. Click Through Component
1. Graphical Link Component

These components expose certain attributes that can be mapped via Adobe Analytics variables (Traffic, conversion variables) and success events to send information to Adobe Analytics.

## Prerequisites {#prerequisites}

Adobe recommends that you go through the [existing AEM-Adobe Analytics integration](../../../sites/administering/using/adobeanalytics.md) to understand how this integration works.

## Components available for mapping {#components-available-for-mapping}

In AEM, the **Call to Action** components - **ClickThroughLink** and **GraphicalLink** - displayed here in the sidekick, can be mapped to Adobe Analytics variables.

![](assets/chlimage_1-21.jpeg)

### Mapping Landing Page components to Adobe Analytics {#mapping-landing-page-components-to-adobe-analytics}

To map landing page components to Adobe Analytics:

1. After creating the Adobe Analytics configuration and creating a new framework, select the appropriate reporting suite from the drop-down menu. This results in fetching the Adobe Analytics variables and showing them in the content finder.
1. Drag and drop Call to Action (CTA) components from the sidekick into the mapping area in the middle of the page, as appropriate.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Component Name</strong></td> 
   <td><strong>Attributes Exposed</strong></td> 
   <td><strong>Meaning of Attribute</strong></td> 
  </tr>
  <tr>
   <td><strong>CTA Click Through Link</strong></td> 
   <td><i>eventdata.clickthroughLinkLabel</i> <br /> </td> 
   <td>The label on the link or the text of the link </td> 
  </tr>
  <tr>
   <td><br type="_moz" /> </td> 
   <td><i>eventdata.clickthroughLinkTarget</i> <br /> </td> 
   <td>The destination where you are taken when you click on the link </td> 
  </tr>
  <tr>
   <td><br type="_moz" /> </td> 
   <td><i>eventdata.events.clickthroughLinkClick</i> <br /> </td> 
   <td>The click event </td> 
  </tr>
  <tr>
   <td><strong>CTA Graphical Link</strong></td> 
   <td><i>eventdata.clicktroughImageLabel</i> <br /> </td> 
   <td>The title of the CTA image </td> 
  </tr>
  <tr>
   <td><br type="_moz" /> </td> 
   <td><i>eventdata.clicktroughImageTarget</i> <br /> </td> 
   <td>The destination where you are taken when you click on the image which contains a link</td> 
  </tr>
  <tr>
   <td><br type="_moz" /> </td> 
   <td><i>eventdata.clicktroughImageAsset</i> <br /> </td> 
   <td>The path to the image asset in the repository </td> 
  </tr>
  <tr>
   <td><br type="_moz" /> </td> 
   <td><i>eventdata.events.clicktroughImageClick</i> <br /> </td> 
   <td>The click event</td> 
  </tr>
 </tbody>
</table>

1. Map these exposed attributes with any Adobe Analytics variables from the content finder. The framework is now ready to use. 
1. You can now create a new landing page or open an existing landing page with existing CTA components and click **Cloud Services** tab in **Page Properties** from the sidekick (in the touch-optimized UI, select **Open Properties **and** **click** Cloud Services**) and configure the framework to use with landing page. Select the framework from the drop-down list.

   ![](assets/chlimage_1-25.png)

1. After configuring the framework with the landing page, you can now use the instrumented components and any clicks on CTA are recorded in Adobe Analytics.

