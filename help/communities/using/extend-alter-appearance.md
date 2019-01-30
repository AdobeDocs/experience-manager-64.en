---
title: Alter the Appearance (HBS)
seo-title: Alter the Appearance
description: null
seo-description: Modify the HBS scripts
uuid: 5776b8c8-0d18-4ef5-9eb7-ddf88b4916b2
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 0a3c0749-4f1f-4109-baba-4c6bc72c41c0
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Alter the Appearance (HBS){#alter-the-appearance-hbs}

| ** [⇐ Add Comment to Sample Page](../../communities/using/extend-sample-page.md)** |  |
|---|---|

Now that the components for the custom comment system in the application directory (/apps) are in place, with a resourceSuperType referencing the default comment system and the custom Model/View registered, it is possible to modify the implementation.

For a simple demonstration, a visual feature, the avatar shown of the signed-in user who posts a comment, is removed.

>[!NOTE]
>
>To make use of the extension, the instance of the comment system in a website to be affected (/content) must set its resourceType to be the custom comment system.

### Modify the HBS Scripts {#modify-the-hbs-scripts}

Using [CRXDE Lite](../../sites/developing/using/developing-with-crxde-lite.md) :

* open [/apps/custom/components/comments/comment/**comment.hbs**](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment/comment.hbs)

    * comment out the tag which includes the avatar for a comment post (~ line 21) :  
      `&lt;!--  
      &lt;&lt;img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"&gt;&lt;/img&gt;  
      -->`

* open [/apps/custom/components/comments/**comments.hbs**](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comments.hbs)

    * comment out the tag which includes the avatar for the next comment entry (~ line 44) :  
      `&lt;!--  
      &lt;img class="scf-composer-avatar" src="{{loggedInUser.avatarUrl}}"&gt;&lt;/img&gt;  
      -->`

* select **Save All**

### Replicate Custom App {#replicate-custom-app}

After the application has been modified, it is necessary to re-replicate the custom component.

One way to do so is

* from the main menu

    * select **Tools &gt; Operations &gt; Replication**
    * select `Activate Tree`
    * set `Start Path`: to `/apps/custom`
    
    * uncheck `Only Modified`
    * select `Activate`button

### View Modified Comment on Published Sample Page {#view-modified-comment-on-published-sample-page}

[Continuing the experience](../../communities/using/extend-sample-page.md#publishsamplepage) on the publish instance, still signed in as the same user, it is now possible to refresh the page in the publish environment to view the modification to remove the avatar :

![](assets/chlimage_1-87.png) 

### Sample Comment Extension Package {#sample-comment-extension-package}

Attached is a package of the custom comments application created in this tutorial.

[](assets/sample-comment-extension-6-1-fp3.zip)

| ** [⇐ Add Comment to Sample Page](../../communities/using/extend-sample-page.md)** |  |
|---|---|

