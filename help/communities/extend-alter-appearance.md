---
title: Alter the Appearance (HBS)
seo-title: Alter the Appearance
description: Modify the HBS scripts
seo-description: Modify the HBS scripts
uuid: 6e1030af-f170-4a60-9d3f-439afd05de57
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 70be208d-185b-4b27-8e01-74e62f656344
exl-id: 358b70b8-8122-4eda-baa7-d9a58d6901f9
---
# Alter the Appearance (HBS) {#alter-the-appearance-hbs}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Now that the components for the custom comment system in the application directory (/apps) are in place, with a resourceSuperType referencing the default comment system and the custom Model/View registered, it is possible to modify the implementation.

For a simple demonstration, a visual feature, the avatar shown of the signed-in user who posts a comment, is removed.

>[!NOTE]
>
>To make use of the extension, the instance of the comment system in a website to be affected (/content) must set its resourceType to be the custom comment system.

## Modify the HBS Scripts {#modify-the-hbs-scripts}

Using [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Open [/apps/custom/components/comments/comment/comment.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment/comment.hbs)

    * Comment out the tag which includes the avatar for a comment post (~ line 21):

      ``` 
      <!--
       <<img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
       -->
      ```

* Open [/apps/custom/components/comments/comments.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comments.hbs)

    * Comment out the tag which includes the avatar for the next comment entry (~ line 44):

      ``` 
      <!--
       <img class="scf-composer-avatar" src="{{loggedInUser.avatarUrl}}"></img>
       -->
      ```

* Select **Save All**

## Replicate Custom App {#replicate-custom-app}

After the application has been modified, it is necessary to re-replicate the custom component.

One way to do so is

* From the main menu

    * Select **[!UICONTROL Tools > Operations > Replication]**
    * Select `Activate Tree`
    * Set `Start Path`: to `/apps/custom`
    * Uncheck `Only Modified`
    * Select `Activate` button

## View Modified Comment on Published Sample Page {#view-modified-comment-on-published-sample-page}

[Continuing the experience](extend-sample-page.md#publish-sample-page) on the publish instance, still signed in as the same user, it is now possible to refresh the page in the publish environment to view the modification to remove the avatar:

![chlimage_1-81](assets/chlimage_1-81.png) 

## Sample Comment Extension Package {#sample-comment-extension-package}

Attached is a package of the custom comments application created in this tutorial.

[Get File](assets/sample-comment-extension-6-1-fp3.zip)
