---
title: Publish collections to Brand Portal
description: Learn how to publish and unpublish collections to Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: c2c6759e-f763-405e-9e45-5a90b9d32df2
---
# Publish collections to Brand Portal {#publish-collections-to-brand-portal}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

As an Adobe Experience Manager Assets administrator, you can publish collections to the [!DNL Experience Manager Assets Brand Portal] instance for your organization. However, you must first integrate Assets with Brand Portal. For details, see [Configure Assets with Brand Portal](configure-aem-assets-with-brand-portal.md).

If you make subsequent modifications to the original collection in Assets, the changes are not reflected in Brand Portal until you publish the collection again. This characteristic ensures that work-in-progress changes are not available in Brand Portal. Only approved changes that are published by an administrator are available in Brand Portal.

>[!NOTE]
>
>Content fragments cannot be published to the Brand Portal. Therefore, if you select content fragment(s) on [!DNL Experience Manager] Author, then **[Publish to Brand Portal]** action is not available.
>
>If collections containing content fragments are published from [!DNL Experience Manager] Author to Brand Portal, then all the contents of the folder except content fragments get replicated to Brand Portal interface.

## Publish a collection to Brand Portal {#publish-a-collection-to-brand-portal}

1. In the Assets UI, tap/click the [!DNL Experience Manager] logo. Then, go to **[!UICONTROL Assets > Collections]** from the **[!UICONTROL Navigation]** page.
2. From the Collections console, select the collection you want to publish to Brand Portal.

   ![select_collection](assets/select_collection.png)

3. From the toolbar, tap/click **[!UICONTROL Publish to Brand Portal]**.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. In the confirmation dialog, tap/click **[!UICONTROL Publish]**.
5. Close the confirmation message. 
6. Log in to Brand Portal as an administrator. The published collection is available in the Collections console.

   ![published_collection](assets/published_collection.png)

## Unpublish collections {#unpublish-collections}

You can unpublish collections that you publish from Assets to Brand Portal. After you unpublish the original collection, its copy is no longer available to Brand Portal users.

1. From the Collections console of your [!DNL Assets] instance, and select the collection you want to unpublish.

   ![select_collection-1](assets/select_collection-1.png)

2. From the toolbar, tap/click the **[!UICONTROL Remove from Brand Portal]** icon.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. In the dialog, tap/click **[!UICONTROL Unpublish]**.
4. Close the confirmation message. The collection is removed from the Brand Portal interface.
