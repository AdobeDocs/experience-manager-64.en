---
title: Check-in and check-out your digital assets for editing
description: Learn how to check-out assets for editing and check them back in after the changes are complete.
contentOwner: AG
feature: Asset Management
role: User
exl-id: 0c79ed42-0acd-426e-8e14-412bb4117585
---
# Check-in and check-out files in Assets {#check-in-and-check-out-files-in-assets}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets lets you check-out assets for editing and check them back in after you complete making the changes. After you check-out an asset, only you can edit, annotate, publish, move, or delete the asset. Checking out an asset locks the asset. Other users cannot perform any of these operations on the asset until you check the asset back in to [!DNL Experience Manager] Assets. However, they can still change the metadata for the locked asset.

To be able to check-out or check-in assets, you require Write access on them.

This feature helps prevent other users from overriding the changes made by an author where multiple users collaborate on editing workflows across teams.

## Check-out assets {#checking-out-assets}

1. From the Assets UI, select the asset you want to check-out. You can also select multiple assets to check-out.

   ![chlimage_1-468](assets/chlimage_1-468.png)

1. From the toolbar, click/tap the **[!UICONTROL Checkout]** icon.

   ![chlimage_1-469](assets/chlimage_1-469.png)

   Observe that the **[!UICONTROL Checkout]** icon toggles to the **[!UICONTROL Checkin]** icon with the lock open.

   ![chlimage_1-470](assets/chlimage_1-470.png)

   To verify whether other users can edit the asset you checked out, log in as a different user. A lock icon appears on the thumbnail of the asset that you checked out.

   ![chlimage_1-471](assets/chlimage_1-471.png)

   Select the asset. Notice that the toolbar does not display any options that let you edit, annotate, publish, or delete the asset.

   ![chlimage_1-472](assets/chlimage_1-472.png)

   You can, however, click/tap the **[!UICONTROL View Properties]** icon to edit the metadata for the locked asset.

1. Click/tap the Edit icon to open the asset in edit mode.

   ![chlimage_1-473](assets/chlimage_1-473.png)

1. Edit the asset and save the changes. For example, crop the image and save. 

   ![chlimage_1-474](assets/chlimage_1-474.png)

   You can also choose to annotate or publish the asset.

1. Select the edited asset from the Assets UI, and click/tap the **[!UICONTROL Checkin]** icon from the toolbar.

   ![chlimage_1-475](assets/chlimage_1-475.png)

   The modified asset is checked in to [!DNL Assets] and is available to other users for editing.

## Forced check-in {#forced-check-in}

Administrators can check-in assets that are checked out by other users.

1. Log in to [!DNL Assets] as an administrator.
1. From the Assets UI select one or more assets that have been checked out by other users.

   ![chlimage_1-476](assets/chlimage_1-476.png)

1. From the toolbar, click/tap the **[!UICONTROL Release Lock]** icon. The asset is checked back in and available for edit to other users.

   ![chlimage_1-477](assets/chlimage_1-477.png)
