---
title: Adding Fonts for Graphic-Rendering
seo-title: Adding Fonts for Graphic-Rendering
description: null
seo-description: AEM allows you to generate graphics incorporating text dynamically taken from your content
uuid: 47a8891b-d9ae-4925-be3f-520389eb3f09
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 26b88723-7286-409d-9a20-07bf47b26d42
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Adding Fonts for Graphic-Rendering{#adding-fonts-for-graphic-rendering}

CQ allows you to generate graphics incorporating text dynamically taken from your content.

To do this you can also load and use your own fonts.

Currently all implementations of the Java Platform support [TrueType](http://en.wikipedia.org/wiki/Truetype) fonts.

1. Open CRXDE Lite and navigate to your project application folder:  
   `/apps/<*your-project*>/`  

1. Under `/apps/<*your-project*>/` create a new node:

    * **Name**: `fonts`
    
    * **Type**: `sling:Folder`

   Save all changes.

1. Copy the font files into this folder; for example, using WebDAV.

   >[!NOTE]
   >
   >Font files in the repository must have the suffix `*.ttf` or `*.TTF`.

1. Update the [OSGi configuration](../../../sites/deploying/using/configuring-osgi.md) of [Day Commons GFX Font Helper](../../../sites/deploying/using/osgi-configuration-settings.md#daycommonsgfxfonthelper). Add the path to your fonts folder; i.e. `/apps/<*your-project*>/fonts`.  

1. Return to CRXDE Lite. You should now see a `.fontlist` node in your folder containing the name of the imported fonts.

   These fonts are now ready to be used in the Java API.

For full details of how to use the fonts with the Java API, see the [documentation for the Font class of the Java API](http://download.oracle.com/javase/6/docs/api/java/awt/Font.html).  

