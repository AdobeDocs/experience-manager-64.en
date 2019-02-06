---
title: Setup Website Structure
seo-title: Setup Website Structure
description: Set up directories
seo-description: Set up directories
uuid: 3c0e5ba7-c5f8-4ad0-b178-6912535dbc8c
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: e55616ef-0813-43c3-bc80-3b818b458923
index: y
internal: n
snippet: y
---

# Setup Website Structure{#setup-website-structure}

| [**⇐ Create An SCF Sandbox**](../../communities/using/an-scf-sandbox.md) |** [Initial Sandbox Application ⇒](../../communities/using/initial-app.md)** |
|---|---|

To setup your website, the instructions below describe the folders to create in the following locations :

* **/apps**/an-scf-sandbox  
  this is where custom applications and templates reside

* **/etc/designs**/an-scf-sandbox  
  this is where downloadable design elements reside

* **/content**/an-scf-sandbox  
  this is where the downloadable web pages reside

The code in this tutorial will rely on the main folder name being the same for the application, design, and content. If you choose some other name for your website, then always replace **an-scf-sandbox **with the name you have chosen.

>[!NOTE]
>
>About names :
>
>* the names seen in CRXDE are node names which form the path to addressable content
>* node names may contain spaces, but when used in an URI, the space must be encoded either as '%20' or '+'
>* node names may contain hyphens and underscores, but they must be encoded when referenced as a package name within a Java file. Both hyphens and underscores are escaped with underscore followed by their unicode value : >
>    * hypen becomes '_002d'  
>    * underscore becomes '_005f'
>

### Setup the Application Directory (/apps) {#setup-the-application-directory-apps}

The /apps directory in the repository contains the code with implements the behavior and rendering of the pages served from the /content directory.

The /apps directory is protected and not publicly accessible as are the /content and /etc/designs directories.

1. Create** /apps/an-scf-sandbox **folder.

   Using **CRXDE Lite**, in the explorer pane

    1. select the **`/apps`** folder   
    
    1. right-click **Create**... or pull down the **Create...** menu
    
    1. select **Create** **Folder...** .
    
    1. in the **Create Folder **dialog, enter **an-scf-sandbox**
    
    1. click **OK**

1. Create **components **subfolder.

    1. select the **/apps/an-scf-sandbox** folder
    1. click **Create** &gt; **Create Folder**
    
    1. in the **Create Folder** dialog, enter **components**
    
    1. click **OK**

1. Create **templates **subfolder.

    1. select the **/apps/an-scf-sandbox **folder
    1. click **Create** &gt; **Create Folder**
    
    1. in the **Create Folder** dialog, enter **templates**
    
    1. ****click **OK**

1.

    1. re-select /apps/**an-scf-sandbox**
    1. select **Save All**

   As with any editing process, save often. If you run into problems with entering data, it may be either because your login has timed out or you need to save previous edits.

1. The structure in the explorer pane of CRXDE Lite should now look something like this:

   ![](assets/chlimage_1-43.png)

### Setup the Design Directory (/etc/designs) {#setup-the-design-directory-etc-designs}

The /etc/designs directory contains the images, scripts, and stylesheets to be downloaded along with the page content.

1. To use the Deisgner tool in the Classic UI, browse to [http://<server>:<port>/miscadmin](http://localhost:4502/miscadmin).

   Note : If you use CRXDE Lite to create a Node of type `cq:Page`, the Access Control and Replication would not be set to default settings for a page.

1. In the explorer pane, select the **Designs **folder and then click **New &gt; New Page**.

   Enter:

    * Title :** An SCF Sandbox**
    * Name : **an-scf-sandbox**
    * select **Design Page Template**

   Click **Create**

   ![](assets/chlimage_1-44.png)

1. Refresh the explorer pane if "An SCF Sandbox" folder does not appear.  

1. Return to CRXDE Lite (http://localhost:4502/crx/de) and expand /etc/designs to see the node named "an-scf-sandbox".

   In the right, lower pane of CRXDE, you can view the Properties tab, Access Control tab and Replication tab to see what was defined using the Design Page Template.

   ![](assets/chlimage_1-45.png)

### Setup the Content Directory (/content) {#setup-the-content-directory-content}

The /content directory in the respository is where the website content resides. The paths under /content comprise the paths of the URL for browser requests.

*After *the [page template](../../communities/using/initial-app.md#createthepagetemplate) is created as part of the initial application, the initial page content can be created based on the template.... [**⇒**](../../communities/using/initial-app.md)

| [**⇐ Create An SCF Sandbox**](../../communities/using/an-scf-sandbox.md) |** [Initial Sandbox Application ⇒](../../communities/using/initial-app.md)** |
|---|---|

