---
title: Initial Sandbox Content
seo-title: Initial Sandbox Content
description: Create content
seo-description: Create content
uuid: e8452289-cdc0-4dcd-aae0-213249e65bd6
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d9326700-d4e7-407e-8802-a3cb0fc577ac
index: y
internal: n
snippet: y
---

# Initial Sandbox Content{#initial-sandbox-content}

| ** [⇐ Initial Sandbox Application](../../communities/using/initial-app.md)** |** [Develop Sandbox Application ⇒](../../communities/using/develop-app.md)** |
|---|---|

In this section, you create the following pages which all use the [page template](../../communities/using/initial-app.md#createthepagetemplate):

* SCF Sandbox Site, which will redirect to the English version of the main page

    * SCF Sandbox - the main page for the English version of the site

        * SCF Play - child of the main page on which to play

Although this tutorial does not delve into [language copies](../../sites/administering/using/tc-prep.md), it is designed so the root page may implement detection of the preferred language for the user through the HTML header, and redirect to the appropriate main page for the language. The convention is to use the two-letter country code for the node name of the page, e.g., "en" for English, "fr" for French, and so on.

### Create First Pages {#create-first-pages}

Now that there is a [page template](../../communities/using/initial-app.md#createthepagetemplate), we can establish the root page of the website in the /content directory.

1. The standard UI currently provides blueprints for creating sites. As this tutorial is creating a simple site, the classic UI is useful.

   To switch to the classic UI, select global navigation and hover over the right side of the Projects icon. Select the "Switch to Classic UI" icon which appears:

   ![](assets/chlimage_1-36.png)

   The ability to switch to the classic UI must be [enabled by an administrator](../../sites/administering/using/enable-classic-ui.md).

1. From the [classic UI Welcome page](http://localhost:4502/welcome.html), select **Websites**.

   ![](assets/chlimage_1-37.png)

   Alternatively, access the classic UI for Websites directly by browsing to [/siteadmin.](http://localhost:4502/siteadmin)

1. In the explorer pane, select **Websites **and then in the toolbar select **New &gt; New Page**.

   In the** Create Page** dialog, enter the following:

    * Title: **SCF Sandbox Site**
    * Name: **an-scf-sandbox**
    * select **An SCF Sandbox Play Template**
    * click **Create**

   ![](assets/chlimage_1-38.png)

1. In the explorer pane, select the page you just created, **/Websites/SCF Sandbox Site**, and click **New** &gt;** New Page :**

    * Title: **SCF Sandbox**
    * Name: **en**
    * select **An SCF Sandbox Play Template**
    * click **Create**

1. In the explorer pane, select the page you just created, **/Websites/SCF Sandbox Site/SCF Sandbox**, and click **New** &gt;** New Page :**

    * Title: **SCF Play**
    * Name: **play**
    * select **An SCF Sandbox Play Template**
    * click **Create**

1. This is how the website now appears in the Websites console. Notice that child pages of the item selected in the explorer pane are displayed in the right pane where they can be managed.

   ![](assets/chlimage_1-39.png)

   This is the repository view of what was created using the Website tool and the template:

   ![](assets/chlimage_1-40.png)

### Add the Design Path {#add-the-design-path}

When ` [/etc/designs/an-scf-sandbox](../../communities/using/setup-website.md#setupthedesigntreeetcdesigns)` was created using the designs section of the Tools console, the property ``

* `cq:template="/libs/wcm/core/templates/designpage"`

was defined, which provides the optional ability to reference design assets in a script using `currentDesign.getPath()`. For example

* &lt;% String favIcon = currentDesign.getPath() + "/favicon.ico"; %&gt;

1. 
1.

    * Name: **cq:designPath**
    * Type: **String **
    * Value: **/etc/designs/an-scf-sandbox**

1. Click the green **[+] Add**

The respository should appear as follows:  

![](assets/chlimage_1-41.png)

* click** Save All**

[ Trouble saving? Re-login! ]

>[!NOTE]
>
>The use of cq:designPath is optional and is unrelated to the [use of clientlibs](../../communities/using/develop-app.md#includeclientlibsintemplate), which are essentially required as the SCF components use [clientlibs](../../communities/using/client-customize.md#clientlibsforscf) to manage their JS and CSS.

| ** [⇐ Initial Sandbox Application](../../communities/using/initial-app.md)** |** [Develop Sandbox Application ⇒](../../communities/using/develop-app.md)** |
|---|---|

