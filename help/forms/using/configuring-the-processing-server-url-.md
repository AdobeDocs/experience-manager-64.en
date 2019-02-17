---
title: Configuring AEM DS settings
seo-title: Configuring AEM DS settings
description: You need to specify the processing server URL before you submit a form.
seo-description: You need to specify the processing server URL before you submit a form.
uuid: ba15b3c8-7e1c-4842-806d-87153281e1d6
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 1dbede6f-eae1-46dd-82f7-20a5bd25a033
index: y
internal: n
snippet: y
---

# Configuring AEM DS settings{#configuring-aem-ds-settings}

This article describes how to configure **AEM DS Settings Service**. This setting can be used in multiple scenarios, for example:

* In Correspondence Management

    * For configuring AEM Forms Workflow
    * While using forms portal for remote save of draft/submission

* In Adaptive forms for cases when Adaptive form is submitted from publish instance

Following are the steps to configure the **[!UICONTROL AEM DS Settings]**:

1. Open the Configuration Manager on the publish instance using the URL:   
   *http://localhost:port/system/console/configMgr*.

   ![](assets/aem_web_configuration_console.png)

1. In the **[!UICONTROL Adobe Experience Manager Web Console Configuration]** window, locate and click the **[!UICONTROL AEM DS Settings]** option.

   ![](assets/ds_settings.png)

1. The **[!UICONTROL AEM DS Settings Service]** window displays the common configuration settings for AEM DS Components.

   ![](assets/ds_settings_1.png)

1. Add the following information in the respective fields:

   **[!UICONTROL **Processing Server UR**L]**: The Processing Server is the server where the Forms or AEM workflow needs to be triggered. This can be same as the URL of the AEM author instance or the other Server URL (that is, http://localhost:port/).

   ****[!UICONTROL Processing Server User Name]****: Workflow user's User Name [based on the server URL being used]

   ****[!UICONTROL Processing Server Password]****: Workflow user's Password

   >[!NOTE]
   >
   >
   >    
   >    
   >    * While using either Forms or AEM workflows, before you make any submission from the publish server, it is necessary to configure the DS settings service. Otherwise, the Form submission shall fail.
   >    
   >

