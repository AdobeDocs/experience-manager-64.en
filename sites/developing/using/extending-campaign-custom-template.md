---
title: Creating Custom AEM Page Template with Adobe Campaign Form Components
seo-title: Creating Custom AEM Page Template with Adobe Campaign Form Components
description: null
seo-description: Build a custom page template that uses Adobe Campaign Form components
uuid: cbc43e90-f384-4f82-a7d3-7cb995746d9a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 2a48ab5a-cd64-47c3-a7ea-00631f3e859e
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Creating Custom AEM Page Template with Adobe Campaign Form Components{#creating-custom-aem-page-template-with-adobe-campaign-form-components}

This page explains how to build a custom page template that uses [Adobe Campaign Form](../../authoring/using/adobe-campaign-components.md) components by examining how the Geometrixx-outdoors template ( `/apps/geometrixx-outdoors/components/page_campaign_profile`) is implemented, and points you to important information you may need when creating your own custom template.

>[!NOTE]
>
>[Email and form samples are only available in Geometrixx](../../developing/using/we-retail.md#weretail). Please download sample Geometrixx content from Package Share.

To create a custom AEM page template using Adobe Campaign Form components, make sure you have the following:

1. **Correct resourceSuperType**

   Make sure the page-component inherits from `mcm/campaign/components/profile`.

   This is required for the servlets to get and save info

    * `com.day.cq.mcm.campaign.servlets.TemplateListServlet`
    * `com.day.cq.mcm.campaign.servlets.SaveProfileServlet`

   ![](assets/chlimage_1-158.png)

1. **ClientContext Settings**

   When you look at the clientcontext settings ( `/etc/designs/geometrixx-outdoors/jcr:content/page_campaign_profile`) you see the following settings:

    * ClientContext points to `/etc/clientcontext/campaign`
    * There is also an extra *config* node.

   ![](assets/chlimage_1-159.png)

1. **head.jsp (/apps/geometrixx-outdoors/components/page_campaign_profile/head.jsp)**

   In **head.jsp**, you see the following lines that use the **clientcontext-config** and the **cloudservice-hook**:

   ```
   <cq:include path="config" resourceType="cq/personalization/components/clientcontext_optimized/config"/>
   <sling:include path="contexthub" resourceType="granite/contexthub/components/contexthub"/>
   <cq:include script="/libs/cq/cloudserviceconfigs/components/servicelibs/servicelibs.jsp"/>
   ```

1. **body.jsp (/apps/geometrixx-outdoors/components/page_campaign_profile/body.jsp)**

   In **body.jsp**, the cloud services are loaded at the bottom of the page:

   ```
   <cq:include path="cloudservices" resourceType="cq/cloudserviceconfigs/components/servicecomponents"/>
   ```

1. **Campaign page properties**

   To be able to select an Adobe Campaign template the page-properties are extended with the **Campaign** tab:

   `/apps/geometrixx-outdoors/components/page_campaign_profile/dialog/items/tabs/items/campaign`

   ![](assets/chlimage_1-160.png)

1. **Template settings**.

   In the template ( `/apps/geometrixx-outdoors/templates/campaign_profile/jcr:content`) you see the following default values:

   | **acMapping** |mapRecipient (for Adobe Campaign 6.1), profile (for Adobe Campaign Standard) |
   |---|---|
   | **acTemplateId** |mail |

   ![](assets/chlimage_1-161.png)
