---
title: Private folder sharing
seo-title: Private folder sharing
description: Learn how to create a private folder in the Adobe Experience Manager (AEM) Assets and share it with other users and the assign various privileges to them.
seo-description: Learn how to create a private folder in the Adobe Experience Manager (AEM) Assets and share it with other users and the assign various privileges to them.
uuid: ec8a76e2-6398-42a1-80be-12958022d17a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 4ddcd7d1-54ed-4dba-bdee-762c7d362998
index: y
internal: n
snippet: y
---

# Private folder sharing{#private-folder-sharing}

You can create a private folder in the Adobe Experience Manager (AEM) Assets user interface that is available exclusively to you. You can share this private folder to other users and the assign various privileges to them. Based on the privilege level you assign, users can perform various tasks on the folder, for example view assets within the folder or edit the assets.

1. In the Assets console, tap/click **Create** from the toolbar and then choose **Folder** from the menu.

   ![](assets/chlimage_1-417.png)

1. In the **Add Folder** dialog, enter a title and name (optional) for the folder, and select **Private**.

   ![](assets/chlimage_1-418.png)

1. Tap/click **Create**. A private folder is created in the UI.

   ![](assets/chlimage_1-419.png)

1. To share the folder with other users and the assign privileges to them, select the folder, and click/tap the **Properties** icon from the toolbar.

   ![](assets/chlimage_1-420.png)

   >[!NOTE]
   >
   >The folder is not visible to any other user until you share it.

1. In the Folder Prperties page, select a user from the **Add User** list, assign a role to the user on your private folder, and click **Add**.

   ![](assets/chlimage_1-421.png)

   >[!NOTE]
   >
   >You can assign various roles, such as Editor, Owner, or Viewer to the user with whom you share the folder. If you assign an Owner role to the user, the user has Editors privileges on the folder. In addition, the user can share the folder with others. If you assign an Editor role, the user can edit the assets in your private folder. If you assign a Viewer role, the user can only view the assets in your private folder.

1. Click **Save**. Depending on the role you assign, the user is assigned a set of privileges on your private folder when the user logs in to AEM Assets.
1. Click **Ok** to close the confirmation message.
1. The user with whom you share the folder receives a sharing notification. Log in to AEM Assets with the credentials of the user to view the notification.

   ![](assets/chlimage_1-422.png)

1. Tap/click the Notification icon to open the list of notifications.

   ![](assets/chlimage_1-423.png)

1. Click/tap the entry for the private folder shared by the administrator to open the folder.

>[!NOTE]
>
>To be able to create a private folder, you require Read and Edit ACL permissions on the parent folder under which you want to create a private folder. If you are not an administrator, these permissions are not enabled for you by default on */content/dam*. In this case, first obtain these permissions for your user ID/group before attempting to create private folders or view folder settings.

