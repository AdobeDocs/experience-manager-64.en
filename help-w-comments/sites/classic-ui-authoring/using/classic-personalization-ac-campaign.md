---
title: Working with Adobe Campaign 6.1 and Adobe Campaign Standard
seo-title: Working with Adobe Campaign 6.1 and Adobe Campaign Standard
description: You can create email content in AEM and process it in Adobe Campaign emails.
seo-description: You can create email content in AEM and process it in Adobe Campaign emails.
uuid: 5fd27802-c2c6-4661-afdb-593663d9f97c
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: ee5a80cd-4759-4f2a-bd11-5010023a21c4
index: y
internal: n
snippet: y
---

# Working with Adobe Campaign 6.1 and Adobe Campaign Standard{#working-with-adobe-campaign-and-adobe-campaign-standard}

You can create email content in AEM and process it in Adobe Campaign emails. To do that, you must:

1. Create a new newsletter in AEM from an Adobe Campaign-specific template.  
1. Select [an Adobe Campaign service](#selectingtheadobecampaigncloudservice) before editing the content to access all the functionality.
1. Edit the content.
1. Validate the content.

Content can then be synched with a delivery in Adobe Campaign. Detailed instructions are described in this document.

See also [Creating Adobe Campaign Forms in AEM](../../../sites/classic-ui-authoring/using/classic-personalization-ac-forms.md).

>[!NOTE]
>
>Before you can use this functionality, you must configure AEM to integrate with either [Adobe Campaign](../../../sites/administering/using/campaignonpremise.md) or [Adobe Campaign Standard](../../../sites/administering/using/campaignstandard.md).

## Sending Email Content via Adobe Campaign {#sending-email-content-via-adobe-campaign}

After you configure AEM and Adobe Campaign, you can create email delivery content directly in AEM and then process it in Adobe Campaign.

When you create Adobe Campaign content in AEM, you must link to an Adobe Campaign service before editing the content to access all the functionality.

There are two possible cases:

* Content can be synched with a delivery from Adobe Campaign. This allows you to use AEM content in a delivery.
* (Adobe Campaign on premise only) The content can be sent directly to Adobe Campaign, which automatically generates a new email delivery. This mode has limitations.

Detailed instructions are described in this document.

### Creating new email content {#creating-new-email-content}

>[!NOTE]
>
>When adding email templates, be sure to add them under **/content/campaigns** to make them available. 
>

1. In AEM, select the **Websites** folder then browse your explorer to find where your email campaigns are managed. In the following example, the node concerned is **Websites** &gt; **Campaigns** &gt; **Geometrixx Outdoors** &gt; **Email Campaigns**.

   >[!NOTE]
   >
   >[Email samples are only available in Geometrixx](../../../sites/developing/using/we-retail.md#weretail). Please download sample Geometrixx content from Package Share.

   ![](assets/chlimage_1-197.png)

1. Select **New** &gt; **New Page** to create new email content.
1. Select one of the available templates specific to Adobe Campaign, then fill the general properties of the page. Three templates are available by default:

    * **Adobe Campaign Email (AC 6.1)**: lets you add content to a predefined template before sending it to Adobe Campaign 6.1 for delivery. 
    * **Adobe Campaign Email (ACS)**: lets you add content to a predefined template before sending it to Adobe Campaign Standard for delivery.

   ![](assets/chlimage_1-198.png)

1. Click **Create **to create your email or newsletter.

### Selecting the Adobe Campaign cloud service and template {#selecting-the-adobe-campaign-cloud-service-and-template}

To integrate with Adobe Campaign, you need to add an Adobe Campaign cloud service to the page. Doing so provides you with access to personalization and other Adobe Campaign information.

In addition you may also need to select the Adobe Campaign template and change the subject and add plain text content for those users who will not view the email in HTML.

1. Select the **Page** tab in the sidekick, then select **Page properties.**
1. In the **Cloud services** tab in the pop-up window, select **Add Service** to add the Adobe Campaign service and click **OK**.

   ![](assets/chlimage_1-199.png)

1. Select the configuration that matches your Adobe Campaign instance from the drop-down list, then click **OK**.

   >[!NOTE]
   >
   >Be sure to tap/click **OK** or **Apply** after adding the cloud service. This enables the **Adobe Campaign** tab to work properly.

1. If you would like to apply a specific email delivery template (from Adobe Campaign), other than the default **mail** template, select **Page properties** again. In the **Adobe Campaign** tab, enter the email delivery template's internal name in the related Adobe Campaign instance.

   In Adobe Campaign Standard, the template is **Delivery with AEM Content**. In Adobe Campaign 6.1, the template is **Email delivery with AEM content**.

   <!--
   Comment Type: remark
   Last Modified By: unknown unknown (ims-author-50BC48A24CE15F640A04B84F@AdobeID)
   Last Modified Date: 2017-11-30T05:06:41.917-0500
   <p>Actually you should choose the "AEM e-Mail" template here (don't know the exact name and don't have the time to look it up, sorry).</p>
   <p>In a standard use-case, this has already the correct External Account and Content Mode, so this does not have to be done by the user.</p>
   <p>Unfortunately we didn't change the default setting. Will open a JIRA for it.</p>
   -->

   <!--
   Comment Type: remark
   Last Modified By: unknown unknown (ims-author-7A535D734CFE87FA0A04B88B@AdobeID)
   Last Modified Date: 2017-11-30T05:06:41.933-0500
   <p>It's the "Delivery with AEM content" template.</p>
   -->

   When you select the template, AEM automatically enables the **Adobe Campaign Newsletter** components.

   <!--
   Comment Type: remark
   Last Modified By: unknown unknown (ims-author-77F410094CD97C4F0A746C1B@AdobeID)
   Last Modified Date: 2017-11-30T05:06:41.963-0500
   <p>From on prem docs, just for reference:</p>
   <p>There are both Adobe Campaign and Adobe Campaign newsletter components.</p>
   <p>[damien] the Adobe Campaign components are the ones used for the forms.</p>
   -->

### Editing email content {#editing-email-content}

You can edit email content in either the classic user interface or the touch-optimized user interface.

1. Enter the subject and the text version of the email by selecting **Page properties** &gt; **Email** from the toolbox. 

   ![](assets/chlimage_1-200.png)

1. Edit email content by adding the elements you would like from those available in the sidekick. To do this, drag and drop them. Then double click the element you want to edit.

   For example, you can add text containing personalization fields.

   ![](assets/chlimage_1-201.png)

   See [Adobe Campaign Components](../../../sites/classic-ui-authoring/using/classic-personalization-ac-components.md) for a description of components available for Adobe Campaign newsletters/email campaigns.

   ![](assets/chlimage_1-202.png)

### Inserting personalization {#inserting-personalization}

When editing your content, you can insert:

* Adobe Campaign context fields. These are are fields that you can insert within your text that will adapt according to the recipient’s data (for example first name, last name, or any data of the target dimension).
* Adobe Campaign personalization blocks. These are blocks of predefined content that are not related to the recipient’s data, such as a brand logo, or link to a mirror page.

See [Adobe Campaign Components](../../../sites/classic-ui-authoring/using/classic-personalization-ac-components.md) for a full description of the Campaign components.

>[!NOTE]
>
>* Only the fields of the Adobe Campaign **Profiles** targeting dimension are taken into account.
>* When viewing Properties from **Sites**, you do not have access to the Adobe Campaign context fields. You can access those directly from the email while editing.
>

1. Insert a new **Newsletter** &gt; **Text & Personalization (Campaign)** component.
1. Open the component by double-clicking it. The **Edit** window has a functionality that lets you insert the personalization elements.

   >[!NOTE]
   >
   >The available context fields correspond to the **Profiles** targeting dimension in Adobe Campaign.
   >
   >
   >See [Linking an AEM page to an Adobe Campaign email](/sites/classic-ui-authoring/using/classic-personalization-ac-campaign.html?cq_ck=1450290357185#LinkinganAEMpagetoanAdobeCampaignemail).

   ![](assets/chlimage_1-203.png)

1. Select **Client Context** in the sidekick to test the personalization fields using the data in the persona profiles.

   ![](assets/chlimage_1-204.png)

1. A window appears and lets you select the persona you like. The personalization fields are automatically replaced by data from the selected profile.

   ![](assets/chlimage_1-205.png)

### Previewing a newsletter {#previewing-a-newsletter}

You can preview how the newsletter will look as well as preview the personalization.

1. Open the newsletter you want to preview and click Preview (magnifying glass) to shrink the sidekick. 
1. Click one of the email client icons to see what your newsletter looks like in each email client.

   ![](assets/chlimage_1-206.png)

1. Expand the sidekick to begin editing again.

### Approving content in AEM {#approving-content-in-aem}

After the content is finished, you can start the approval process. Go to the **Workflow** tab of the toolbox and select the **Approve for Adobe Campaign** workflow.

This out-of-the-box workflow has two steps: revision then approval, or revision then rejection. Nevertheless, this workflow can be extended and adapted to a more complex process.

![](assets/chlimage_1-207.png)

To approve content for Adobe Campaign, apply the workflow by selecting **Workflow** in the sidekick and selecting** Approve for Adobe Campaign** and click** Start Workflow. **Go through the steps and approve the content. You can also reject the contents by selecting **Reject** instead of **Approve** in the last workflow step.

![](assets/chlimage_1-208.png)

After content is approved, it appears as approved in Adobe Campaign. The email can then be sent.

In Adobe Campaign Standard:

![](assets/chlimage_1-209.png)

In Adobe Campaign 6.1:

![](assets/chlimage_1-210.png)

>[!NOTE]
>
>Unapproved content can be synched with a delivery in Adobe Campaign but the delivery cannot be executed. Only approved content can be sent via Campaign deliveries.

## Linking AEM with Adobe Campaign Standard and Adobe Campaign 6.1 {#linking-aem-with-adobe-campaign-standard-and-adobe-campaign}

>[!NOTE]
>
>See [Linking AEM with Adobe Campaign Standard and Adobe Campaign 6.1](../../../sites/authoring/using/campaign.md#main-pars-title-1767901358) under [Working with Adobe Campaign 6.1 and Adobe Campaign Standard](../../../sites/authoring/using/campaign.md) in the standard authoring docurmentation for details.

