---
title: Granite Operations - User and Group Administration
seo-title: Granite Operations - User and Group Administration
description: null
seo-description: Learn about Granite user and group administration.
uuid: d33786ef-c855-415b-ae13-6898f54c6f14
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 1f3e78f2-b70d-40ab-a4e5-419791d86344
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Granite Operations - User and Group Administration{#granite-operations-user-and-group-administration}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:26.723-0500
<p>How to highlight difference between Granite user admin and CQ user admin...and how they interact.</p>
-->

As Granite incorporates the CRX Repository implementation of the JCR API Specification it has its own user and group administration.

These accounts are the underlying basis of the [AEM accounts](../../administering/using/security.md) and any account changes made with the Granite administration will be reflected if/when the accounts are accessed from the [AEM Users console](../../administering/using/security.md#accessinguseradministrationwiththesecurityconsole) (e.g. `http://localhost:4502/useradmin`). From the AEM Users console you can also manage the privileges and other AEM specifics.

Granite user and group administration consoles are both available from the ** [Tools](../../administering/using/tools-consoles.md)** console of the touch-optimized UI:

![](assets/chlimage_1-79.png)

Choosing either **Users** or **Groups** from the Tools console will open the appropriate console. In both you can take action either by using the clickbox and then actions from the toolbar, or by opening the account details via the link under **Name**.

* [User Administration](#useradministration)

  ![](assets/chlimage_1-80.png)

  The **Users** console lists:

    * the user name
    * the user login name (account name)  
    * any title that the account has been given

* [Group Administration](#groupadministration)

  ![](assets/chlimage_1-81.png)

  The **Groups** console lists:

    * the group name
    * the group description
    * the number of users/groups in the group

## User Administration {#user-administration}

### Adding a New User {#adding-a-new-user}

1. Use the **Add User** icon:

   ![](assets/chlimage_1-82.png)

1. The **Create User** form will open:

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2017-11-30T05:00:27.132-0500
   <p>Always seems to show admin when first opened, even when logged in as another account.<br /> </p>
   -->

   ![](assets/chlimage_1-83.png)

   Here you can enter the user details for the account (most are standard and self-explanatory):

    * **ID** 
      This is the unique identification for the user account. It is mandatory and cannot contain spaces.  
    
    * **Email Address**
    * **Password** 
      A password is mandatory.
    
    * **Retype Password** 
      This is mandatory as it is required for confirmation of the password.
    
    * **First Name**
    * **Last Name**
    * **Phone Number**
    * **Job Title**
    * **Street**
    * **Mobile**
    * **City**
    * **Postal Code**
    * **Country**
    * **State**
    * **Title**
    * **Gender**
    * **About**
    * **Account Settings**

        * **Status** 
          You can flag the account as either **active** or **inactive**.

    * **Photo** 
      Here you can upload a photo to use as an avatar.  
      Accepted file types: `.jpg .png .tif .gif`  
      Preferred size: `240x240px`
    
    * **Add User to Groups** 
      Use the selection drop-down to select groups that the user should be a member of. Once selected, use the **X** by the name to deselect before saving.  
    
    * **Groups** 
      A list of group(s) that the user is currently a member of. Use the **X** by the name to deselect before saving.

1. When you have defined the user account use:

    * **Cancel** to abort the registration.
    * **Save** to complete the registration. Creation of the user account will be confirmed with a message.

### Editing an Existing User {#editing-an-existing-user}

1. Access the user details from the link under the user name in the Users console.  

1. You can now edit the details as in [Adding a New User](#addinganewuser).

1. Access the user details from the link under the user name in the Users console.  

1. You can now edit the details as in [Adding a New User](#addinganewuser).

### Changing the Password for an Existing User {#changing-the-password-for-an-existing-user}

1. Access the user details from the link under the user name in the Users console.  

1. You can now edit the details as in [Adding a New User](#addinganewuser). Under **Account Settings** there is a link for **Change Password**.

   ![](assets/chlimage_1-84.png)

1. The **Change Password** dialog will open. Enter and retype the new password, together with your password. Use **OK** to confirm the changes.

   ![](assets/chlimage_1-85.png)

   An message will confirm that the password has been changed.

### Quick Group Assignment {#quick-group-assignment}

1. Use the clickbox to flag one or more users.
1. Use the **Groups** icon:

   ![](assets/chlimage_1-86.png)

   To open the group selection drop down:

   ![](assets/chlimage_1-87.png)

1. In the selection box you can select or deselect groups to which the user account should belong.  

1. When you have assigned, or unassigned, the groups as required use:

    * **Cancel** to abort the changes  
    
    * **Save** to confirm the changes

### Deleting Existing User Details {#deleting-existing-user-details}

1. Use the clickbox to flag one or more users.
1. Use the **Delete** icon to delete the user details:

   ![](assets/chlimage_1-88.png)

1. You will be asked to confirm the deletion, then a message will confirm that the actual deletion has taken place.

## Group Administration {#group-administration}

### Adding a New Group {#adding-a-new-group}

1. Use the Add Group icon:

   ![](assets/chlimage_1-89.png)

1. The **Create Group** form will open:

   ![](assets/chlimage_1-90.png)

   Here you can enter the group details:

    * **ID** 
      This is a unique identifier for the group. This is mandatory and cannot contain spaces.  
    
    * **Name** 
      A name for the group; it will be shown in the Groups console.  
    
    * **Description** 
      A description of the group.  
    
    * **Add Members to Group** 
      Use the selection drop-down to select user(s) to add to the group. Once selected, use the **X** by the name to deselect before saving.  
    
    * **Group Members** 
      A list of user(s) in the group. Use the **X** by the name to deselect before saving.

1. When you have defined the group, use:

    * **Cancel** to abort the registration.
    * **Save** to complete the registration. Creation of the group will be confirmed with a message.

### Editing an Existing Group {#editing-an-existing-group}

1. Access the group details from the link under the group name in the Groups console.  

1. You can now edit and save the details as in [Adding a New Group](#addinganewgroup).

### Copying an Existing Group {#copying-an-existing-group}

1. Use the clickbox to flag a group.
1. Use the **Copy** icon to copy the group details:

   ![](assets/chlimage_1-91.png)

1. The **Edit Group Settings** form will be opened.

   The group ID will be the same as the original, but prefixed with `Copy of`. You must edit this as the ID cannot contain spaces. All other details will be the same as the original.

   You can now edit and save the details as in [Adding a New Group](#addinganewgroup).

### Deleting an Existing Group {#deleting-an-existing-group}

1. Use the clickbox to flag one or more groups.
1. Use the **Delete** icon to delete the group details:

   ![](assets/chlimage_1-92.png)

1. You will be asked to confirm the deletion, then a message will confirm that the actual deletion has taken place.

