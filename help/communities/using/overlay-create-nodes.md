---
title: Create Nodes
seo-title: Create Nodes
description: Overlay the comments system 
seo-description: Overlay the comments system 
uuid: 6b811184-f496-4b3e-8027-1539d927bdac
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ed3fe9fe-d5ed-4d97-a144-e9e7d88f406d
index: y
internal: n
snippet: y
---

# Create Nodes{#create-nodes}

| ** [⇐ Create Comments Page](../../communities/using/overlay-create-comments-page.md)** |** [Alter the Appearance⇒](../../communities/using/overlay-alter-appearance.md)** |
|---|---|

Overlay the comment system with a custom version by copying the minimal number of files necessary from /libs into /apps and modifying them in /apps.

>[!CAUTION]
>
>The contents of the /libs folder are never edited because any re-install or upgrade may delete or replace the /libs folder while the contents of the /apps folder is left untouched.

Using [CRXDE Lite](../../sites/developing/using/developing-with-crxde-lite.md)** **on an author instance, begin by creating a path in the /apps folder which is idential to the path to the overlaid components in the /libs folder.

The path being duplicated is

* /libs/social/commons/components/hbs/comments/comment

Some nodes in the path are folders and some are components.

1. browse to [http://localhost:4502/crx/de/index.jsp](http://localhost:4502/crx/de/index.jsp)
1. create `/apps/social` (if it does not already exist)

    * select `/apps` node
    * **Create &gt; Folder ...**

        * enter Name : `social`

1. `select social`node

    * **Create &gt; Folder...**

        * enter Name : `commons`

1. select `commons`node

    * **Create &gt; Folder...**

        * enter Name : `components`

1. select `components` node

    * **Create &gt; Folder..**.

        * enter Name : `hbs`

1. select `hbs`node

    * **Create &gt; Create Component...**

        * enter Label : `comments`
        * enter Title : `Comments`
        * enter Description : `List of comments without showing avatars`
        * Super Type : `social/commons/components/comments`
        * enter Group : `Communities`
        * click **Next** until **OK**

1. select `comments`node

    * **Create &gt; Create Component...**

        * enter Label : `comment`
        * enter Title : `Comment`
        * enter Description : `A comment instance without avatars`
        * Super Type : `social/commons/components/comments/comment`
        * enter Group : `.hidden`
        * click **Next** until **OK**

* select **Save All**

1. delete the default `comments.jsp`

    * select node `/apps/social/commons/components/hbs/comments/comments.jsp`
    * select **Delete**

1. delete the default comment.jsp

    * select node `/apps/social/commons/components/hbs/comments/comment/comment.jsp`
    * select **Delete**

* select **Save All**

>[!NOTE]
>
>In order to preserve the inheritance chain, the `Super Type` (property `sling:resourceSuperType`) of the overlay components are set to the same value as the `Super Type` of the components being overlaid, in this case
>
>* `social/commons/components/comments`
>* `social/commons/components/comments/comment`
>

The overlay's own `Type`(property `sling:resourceType`) must be a relative self-reference so that any content not found in /apps is then looked for in /libs.

1. 
1.

    * Name: `sling:resourceType`
    * Type: `String`
    * Value: `social/commons/components/hbs/comments`

1. select the green **[+] Add**
1. 
1.

    * Name: `sling:resourceType`
    * Type: `String`
    * Value: `social/commons/components/hbs/comments/comment`

1. select the green **[+] Add**

* select **Save All**

![](assets/chlimage_1-4.png) 

| ** [⇐ Create Comments Page](../../communities/using/overlay-create-comments-page.md)** |** [Alter the Appearance⇒](../../communities/using/overlay-alter-appearance.md)** |
|---|---|

