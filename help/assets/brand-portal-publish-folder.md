---
title: Publish folders to Brand Portal
description: Learn how to publish and unpublish folders to Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: f41ab750-5780-42ae-a131-5bc748280215
---
# Publish folders to Brand Portal {#publish-folders-to-brand-portal}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

As an Adobe Experience Manager Assets administrator, you can publish assets and folders to the [!DNL Experience Manager Assets Brand Portal] instance (or schedule the publish workflow to a later date/time) for your organization. However, you must first integrate [!DNL Experience Manager Assets] with [!DNL Brand Portal]. For details, see [Configure [!DNL Experience Manager Assets] with Brand Portal](configure-aem-assets-with-brand-portal.md).

After you publish an asset or folder, it is available to users in Brand Portal.

If you make subsequent modifications to the original asset or folder in [!DNL Assets], the changes are not reflected in Brand Portal until you republish the asset or folder. This feature ensures that work-in-progress changes are not available in Brand Portal. Only approved changes that are published by an administrator are available in Brand Portal.

## Publish folders to Brand Portal {#publish-folders-to-brand-portal-1}

1. From the [!DNL Assets] interface, hover over the desired folder and select **[!UICONTROL Publish]** option from the quick actions.

   Alternatively, select the desired folder and follow the further steps.

   ![publish2bp](assets/publish2bp.png)

2. **Publish folders now**

   To publish the selected folders to Brand Portal, do either of the following:

    * From the toolbar, select **[!UICONTROL Quick Publish]**. Then from the menu, select **[!UICONTROL Publish to Brand Portal]**.
    * From the toolbar, select **[!UICONTROL Manage Publication]**.

3. Then from the **[!UICONTROL Action]** select **[!UICONTROL Publish to Brand Portal]**, and from **[!UICONTROL Scheduling]** select **[!UICONTROL Now]**. Tap **[!UICONTROL Next].**
4. Within **[!UICONTROL Scope]**, confirm your selection and tap **[!UICONTROL Publish to Brand Portal]**.

   A message appears stating that the folder has been queued up for publishing to Brand Portal. Log in to the Brand Portal interface to see the published folder.

   **Publish folders later**

   To schedule the publish to Brand Portal workflow of asset folders to a later date or time:

    1. Once you have selected assets/folders to publish, select **[!UICONTROL Manage Publication]** from the tool bar at the top.
    2. On **[!UICONTROL Manage Publication]** page, select **[!UICONTROL Publish to Brand Portal]** from **[!UICONTROL Action]** and select **[!UICONTROL Later]** from **[!UICONTROL Scheduling]**.

       ![publishlaterbp](assets/publishlaterbp.png)

    3. Select an **[!UICONTROL Activation date]** and specify time. Tap **[!UICONTROL Next]**.
    4. Confirm your selection in **[!UICONTROL Scope]**. Tap **[!UICONTROL Next]**.
    5. Specify a Workflow title under **[!UICONTROL Workflows]**. Tap **[!UICONTROL Publish Later]**.

       ![manageschedulepub](assets/manageschedulepub.png)

## Unpublish folders from Brand Portal {#unpublish-folders-from-brand-portal}

You can remove any asset folder published to Brand Portal by unpublishing it from [!DNL Experience Manager] Author instance. After you unpublish the original folder, its copy is no longer available to Brand Portal users.

You have the option to unpublish folders from Brand Portal quickly or schedule it for a later date and time. To unpublish asset folders from Brand Portal:

1. From the [!DNL Assets] interface in [!DNL Experience Manager]  Author instance, select the folder you want to unpublish.

   ![publish2bp-1](assets/publish2bp-1.png)

2. From the toolbar, tap/click **[!UICONTROL Manage Publication]**.  

3. **Unpublish from Brand Portal now**

   To quickly unpublish the desired folder from Brand Portal:

    1. On **[!UICONTROL Manage Publication]** page, from **[!UICONTROL Action]** select **[!UICONTROL Unpublish from Brand Portal]** and from **[!UICONTROL Scheduling]** select **[!UICONTROL Now]**.
    2. Tap/ click **[!UICONTROL Next].**
    3. Within **[!UICONTROL Scope]**, confirm your selection and tap **[!UICONTROL Unpublish from Brand Portal]**.

   ![confirm-unpublish](assets/confirm-unpublish.png)

   **Unpublish from Brand Portal later**

   To schedule the publishing of a folder from Brand Portal to a later date and time:

    1. On **[!UICONTROL Manage Publication]** page, from **[!UICONTROL Action]** select **[!UICONTROL Unpublish from Brand Portal]** and from **[!UICONTROL Scheduling]** select **[!UICONTROL Later].**
    2. Select an **[!UICONTROL Activation date]** and specify the time. Tap **[!UICONTROL Next]**.
    3. Within **[!UICONTROL Scope]**, confirm your selection and tap **[!UICONTROL Next]**.
    4. Specify a **[!UICONTROL Workflow title]** under **[!UICONTROL Workflows]**. Tap **[!UICONTROL Unpublish Later].**

       ![unpublishworkflows](assets/unpublishworkflows.png)

>[!NOTE]
>
>The procedure to publish/unpublish an asset to/from Brand Portal is similar to the corresponsing procedure for a folder.
