---
title: Configuring AEM DS settings
seo-title: Configuring AEM DS settings
description: You need to specify the processing server URL before you submit a form.
seo-description: You need to specify the processing server URL before you submit a form.
uuid: 5a7f075d-4fbd-44d7-ab5c-b5b752d7e62f
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 115fe296-845c-40e9-bbb0-9a5651a1c87c
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

   ![](assets/AEM_web_configuration_console.PNG)

1. In the **[!UICONTROL Adobe Experience Manager Web Console Configuration]** window, locate and click the **[!UICONTROL AEM DS Settings]** option.

   ![](assets/DS_settings.PNG)

1. The **[!UICONTROL AEM DS Settings Service]** window displays the common configuration settings for AEM DS Components.

   ![](assets/DS_settings_1.PNG)

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

