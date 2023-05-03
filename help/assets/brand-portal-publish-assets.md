---
title: Publish folders to Brand Portal
description: Learn how to publish and unpublish assets to Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: 6b78124d-4022-452f-8d0f-b667de337bf4
---
# Publish assets to Brand Portal {#publish-assets-to-brand-portal}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

As an Adobe Experience Manager Assets administrator, you can publish assets to the [!DNL Experience Manager Assets Brand Portal] instance (or schedule the publish workflow to a later date/time) for your organization. However, you must first configured [!DNL Assets] with [!DNL Brand Portal]. For details, see [Configure [!DNL Assets] with [!DNL Brand Portal]](configure-aem-assets-with-brand-portal.md).

After you publish an asset, it is available to users in Brand Portal.

If you make subsequent modifications to the original asset in [!DNL Assets], the changes are not reflected in Brand Portal until you republish the asset. This feature ensures that work-in-progress changes are not available in Brand Portal. Only approved changes that are published by an administrator are available in Brand Portal.

After replication succeeds, you can publish assets, folders, and collections to [!DNL Brand Portal]. To publish assets to Brand Portal, follow these steps:

>[!NOTE]
>
>Adobe recommends staggered publishing, preferably during non-peak hours, so that the [!DNL Experience Manager] author does not occupy excess resources.

1. From the Assets console, hover over the desired assets and select **[!UICONTROL Publish]** option from the quick actions.

   Alternatively, select the assets you want to publish to Brand Portal.

   ![publish2bp-2](assets/publish2bp-2.png)

2. To publish the assets to Brand Portal, following two options are available:
    * [Publish assets immediately](#publish-now)
    * [Publish assets later](#publish-later)

## Publish assets now {#publish-now}

 To publish the selected assets to Brand Portal, do either of the following:

* From the toolbar, select **[!UICONTROL Quick Publish]**. Then from the menu, select **[!UICONTROL Publish to Brand Portal]**.

* From the toolbar, select **[!UICONTROL Manage Publication]**.

    1. Then from the **[!UICONTROL Action]** select **[!UICONTROL Publish to Brand Portal]**, and from **[!UICONTROL Scheduling]** select **[!UICONTROL Now]**. Tap/ click **[!UICONTROL Next].**

    2. Within **[!UICONTROL Scope]**, confirm your selection and tap/ click **[!UICONTROL Publish to Brand Portal]**.

A message appears stating that the assets have been queued up for publishing to Brand Portal. Log in to the Brand Portal interface to see the published assets.

## Publish assets later {#publish-later}

To schedule publishing the assets to Brand Portal to a later date or time:

1. Once you have selected assets/ folders to publish, select **[!UICONTROL Manage Publication]** from the tool bar at the top.
2. On **[!UICONTROL Manage Publication]** page, select **[!UICONTROL Publish to Brand Portal]** from **[!UICONTROL Action]** and select **[!UICONTROL Later]** from **[!UICONTROL Scheduling]**.

    ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Select an **[!UICONTROL Activation date]** and specify time. Tap/ click **[!UICONTROL Next]**.
4. Select an **[!UICONTROL Activation date]** and specify time. Tap/ click **[!UICONTROL Next]**.
5. Specify a Workflow title under **[!UICONTROL Workflows]**. Tap/ click **[!UICONTROL Publish Later]**.

    ![publishworkflow](assets/publishworkflow.png)

Now, log in to Brand Portal to see whether the published assets are available on Brand  Portal interface.

   ![bp_631_landing_page](assets/bp_landing_page.png)
