---
title: Quick Guide to Authoring Pages
seo-title: Quick Guide to Authoring Pages
description: A quick, high-level guide to the key actions of authoring page content
seo-description: A quick, high-level guide to the key actions of authoring page content
uuid: e0bece6a-e78f-4ecf-9a43-fb2aa3ee028c
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: a15f4950-348b-4d4a-b03d-150c1fc91b2f
index: y
internal: n
snippet: y
---

# Quick Guide to Authoring Pages{#quick-guide-to-authoring-pages}

These procedures are intended as a quick guide (high-level) to the key actions of authoring page content in AEM.

They:

* Are not intended as comprehensive coverage.
* Provide links to the detailed documentation.

For full details about authoring with AEM see:

* [First Steps for Authors](../../../sites/authoring/using/first-steps.md)  

* [Working with the Author Environment](../../../sites/authoring/using/author-environment.md)
* [Authoring Pages](../../../sites/authoring/using/page-authoring.md)

### A Few Quick Hints {#a-few-quick-hints}

Before giving the overview of specifics, here is a small collection of general tips and hints that are worth bearing in mind, especially if you are used to the [classic UI authoring environment](../../../sites/classic-ui-authoring/using/classicui.md).

#### Sites Console {#sites-console}

* **Create**

    * This button is available in many consoles - the options presented are context sensitive so can vary according to the scenario.

* Re-ordering pages in a folder

    * This can be done in [List View](../../../sites/authoring/using/basic-handling.md#listview). The changes will be applied and be visible in other views.

* Changing your UI

    * This can be done from various locations. See [Selecting your UI](../../../sites/authoring/using/select-ui.md).

#### Page Authoring {#page-authoring}

* Navigating Links

    * ***Links are not available for navigation*** when you are in **Edit** mode. To navigate with links you need to [preview the page](../../../sites/authoring/using/editing-content.md#previewingpages) using either:

        * [Preview Mode](../../../sites/authoring/using/editing-content.md#previewmode)
        * [View as Published](../../../sites/authoring/using/editing-content.md#viewaspublished)

* Workflows and Versions are no longer started/created from the page editor; this is now done from [Timeline](../../../sites/authoring/using/basic-handling.md#timeline) (accessible from the console).

>[!NOTE]
>
>There are a number of keyboard shortcuts that can make the authoring experience easier.
>
>* [Keyboard Shortcuts When Editing Pages](../../../sites/authoring/using/page-authoring-keyboard-shortcuts.md)
>* [Keyboard Shortcuts for Consoles](../../../sites/authoring/using/keyboard-shortcuts.md)  
>

### Finding Your Page {#finding-your-page}

1. Open the **Sites** console (using the **Sites** option in the [Global Navigation](../../../sites/authoring/using/basic-handling.md#globalnavigation) - this is triggered (drop down) when you select the Adobe Experience Manager link (top left).  

1. Navigate down the tree by tapping/clicking on the appropriate page. How the page resources are represented depends on the view you are using - [Card, List, or Column](../../../sites/authoring/using/basic-handling.md#main-pars-title-14):

   ![](assets/screen_shot_2018-03-21at160214.png)

1. Navigate up the tree using [the breadcrumb in the header](../../../sites/authoring/using/basic-handling.md#theheaderwithbreadcrumbs), which allows you to return to the selected location:

   ![](assets/chlimage_1-132.png)

### Creating a New Page {#creating-a-new-page}

1. [Navigate to the location](#findingyourpage) where you want to create the new page.
1. Use the **Create** icon and then select **Page** from the list:

   ![](assets/screen_shot_2018-03-21at160324.png)

1. This opens the wizard that will guide you through collecting the information needed when [creating your new page](../../../sites/authoring/using/managing-pages.md#main-pars-title-0). Follow the on screen instructions.

### Selecting Your Page for Further Action {#selecting-your-page-for-further-action}

You can select a page so that you can take action on it. Selecting a page will automatically update the toolbar so that the actions relevant to that resource are shown.

How to select a page depends on which view you are using in the console:

1. Card View:

    * Enter selection mode by [selecting the required resource](../../../sites/authoring/using/basic-handling.md#viewingandselectingyourresources) with:

        * Mobile device: tap-and-hold
        * Desktop: the [quick action](../../../sites/authoring/using/basic-handling.md#quickactions) - tick icon:

   ![](assets/screen_shot_2018-03-21at160503.png)

    * The card will be overlaid with a tick to show that the page has been selected.

   >[!NOTE]
   >
   >Once in selection mode the **Select** icon (a tick) will change to the **Deselect** icon (a cross).

1. List View:

    * Tap/click on the thumbnail for the required resource - the thumbnail will be overlaid with a tick to show that it has been selected.

1. Column View:

    * Tap/click on the thumbnail for the required resource - the thumbnail will be overlaid with a tick to show that it has been selected.

### Quick Actions (Card View/Desktop Only) {#quick-actions-card-view-desktop-only}

1. [Navigate to the page](#findingyourpage) you want to take action on.
1. Hover your mouse pointer over the card that represents your required resource; the quick actions will be shown:

   ![](assets/screen_shot_2018-03-21at160503-1.png)

### Editing Your Page Content {#editing-your-page-content}

1. [Navigate to the page](#findingyourpage) you want to edit.
1. [Open your page for editing](../../../sites/authoring/using/managing-pages.md#main-pars-title-6) using the Edit (pencil) icon:

   ![](assets/screen_shot_2018-03-21at160607.png)

   This can be accessed from either:

    * [Quick Actions (Card View/Desktop Only)](#quickactionscardviewdesktoponly) for the approprate resource.
    * The toolbar when your [page has been selected](#selectiingyourpageforfurtheraction).

1. When the editor opens you can:

    * [Add a new compenent to your page](../../../sites/authoring/using/editing-content.md#main-pars-title-2) by:

        * opening the side panel
        * selecting the components tab (the [components browser](../../../sites/authoring/using/author-environment-tools.md#main-pars-title-17))
        * dragging the required component onto your page.

      The side panel can be opened (and closed) with:

   ![](assets/screen_shot_2018-03-21at160738.png)

    * [Edit the content of an existing component](../../../sites/authoring/using/editing-content.md#main-pars-title-32) on the page:

        * Open the component toolbar with either tap or click. Use the **Edit** (pencil) icon to open the dialog.
        * Open the in place editor for the component with either tap-and-hold or a double-slow-click. The available actions will be shown (for some components, this will be a limited selection).
        * To see all actions available enter full-screen mode using:

   ![](assets/screen_shot_2018-03-21at160706.png)

    * [Configure the properties of an existing component](../../../sites/authoring/using/editing-content.md#main-pars-title)

        * Open the component toolbar with either tap or click. Use the **Configure** (wrench) icon to open the dialog.

    * [Move a component](../../../sites/authoring/using/editing-content.md#main-pars-title-30) either:

        * Drag the required component to its new location.
        * Open the component toolbar with either tap or click. Use the **Cut** then **Paste** icons where required.

    * [Copy (and Paste)](../../../sites/authoring/using/editing-content.md#main-pars-title-32) a component:

        * Open the component toolbar with either tap or click. Use the **Copy** then **Paste** icons as required.

   >[!NOTE]
   >
   >You can **Paste** components to either the same page, or a different page. If pasting to a different page that was already open before the cut/copy operation, then that page will need a page refresh.

    * [Delete](../../../sites/authoring/using/editing-content.md#main-pars-title-32) a component:

        * Open the component toolbar with either tap or click, then use the **Delete** icon.

    * [Add annotations](../../../sites/authoring/using/annotations.md#main-pars-title-1) to the page:

        * Select the **Annotate** mode (speech bubble icon). Add annotations using the **Add annotation** (plus) icon. Exit annotation mode using the X at top right.

   ![](assets/screen_shot_2018-03-21at160813.png)

    * [Preview a page](../../../sites/authoring/using/editing-content.md#main-pars-title-196884421) (to see how it will appear in the publish environment)

        * Select **Preview** from the toolbar.

    * Return to edit mode (or select another mode) using the **Edit** drop down selector.

   >[!NOTE]
   >
   >To navigate using links in the content you must use [Preview mode](../../../sites/authoring/using/editing-content.md#main-pars-title-196884421).

### Editing the Page Properties {#editing-the-page-properties}

There are two (main) methods of [editing page properties](../../../sites/authoring/using/editing-page-properties.md):

* From the **Sites** console:

    1. [Navigate to the page](#findingyourpage) you want to publish.
    1. Select the **Properties** icon from either:

        * [Quick Actions (Card View/Desktop Only)](#quickactionscardviewdesktoponly) for the approprate resource.
        * The toolbar when your [page has been selected](#selectiingyourpageforfurtheraction).

  ![](assets/screen_shot_2018-03-21at160850.png)

  3. The page properties will be shown. You can make updates as required, then use Save to persist these

* When [editing your page](#editingyourpagecontent):

    1. Open the **Page Information** menu.
    1. Select **Open Properties** to open the dialog for editing the properties.

  ![](assets/screen_shot_2018-03-21at160920.png)

### Publishing Your Page (or Unpublishing) {#publishing-your-page-or-unpublishing}

There are two main methods of [publishing your page](../../../sites/authoring/using/publishing-pages.md) (and also of unpublishing):

* From the **Sites** console:

    1. [Navigate to the page](#findingyourpage) you want to publish.
    1. Select the **Quick Publish** icon from either:

        * [Quick Actions (Card View/Desktop Only)](#quickactionscardviewdesktoponly) for the approprate resource.
        * The toolbar when your [page has been selected](#selectiingyourpageforfurtheraction) (also gives access to [Publish Later](../../../sites/authoring/using/publishing-pages.md#main-pars-title-12)).

  ![](assets/screen_shot_2018-03-21at160957.png)

* When [editing your page](#editingyourpagecontent):

    1. Open the **Page Information** menu.
    1. Select **Publish Page**.

  ![](assets/screen_shot_2018-03-21at161026.png)

* Unpublishing a page from the console can only be done via the **Manage Publication** option, which is only available on the toolbar (not via the quick actions).

  The **Unpublish Page** option is still available via the **Page Information** menu in the editor.

  ![](assets/screen_shot_2018-03-21at161059.png)

  See [Publishing Pages](../../../sites/authoring/using/publishing-pages.md#main-pars-title-9d71) for more information.

### Move, Copy and Paste, or Delete Your Page {#move-copy-and-paste-or-delete-your-page}

1. [Navigate to the page](#findingyourpage) you want to move, copy and paste, or delete.
1. Select the copy (and then paste), move or delete icon as required using either:

    * [Quick Actions (Card View/Desktop Only)](#quickactionscardviewdesktoponly) for the required resource.
    * The toolbar when your [page has been selected](#selectingyourpageforfurtheraction).

    * Copy:

        * You will then need to navigate to the new location and paste.

    * Move:

        * The wizard will open to collect the information needed to move the page. Follow the on-screen instructions.

    * Delete:

        * You will be asked to confirm the action.

   >[!NOTE]
   >
   >Delete is not available as a Quick Action.

### Locking Your Page (then Unlocking) {#locking-your-page-then-unlocking}

[Locking a page](../../../sites/authoring/using/editing-content.md#main-pars-title-13) prevents other authors from working on it while you are. The Lock (and Unlock) icon/button can be found:

* The toolbar when your [page has been selected](#selectingyourpageforfurtheraction).
* The [Page Information drop down menu](#editingthepageproperties) when editing a page.
* The page toolbar when editing a page (when the page is locked)

For example, the lock icon looks like this:

![](assets/screen_shot_2018-03-21at161124.png) 

### Accessing Page References {#accessing-page-references}

[Quick access to references](../../../sites/authoring/using/author-environment-tools.md#main-pars-title-11) to/from a page are available in the References Rail.

1. Select **References** using the toolbar icon (either before or after [selecting your page](#selectingyourpageforfurtheraction)):

   ![](assets/screen_shot_2018-03-21at161210.png)

   A list of reference types is shown:

   ![](assets/screen_shot_2018-03-21at161315.png)

1. Tap/click on the required type of reference to show more details and (when appropriate) take further actions.

### Creating a Version of Your Page {#creating-a-version-of-your-page}

1. To open the Timeline rail, select ** [Timeline](../../../sites/authoring/using/basic-handling.md#main-pars-title-281465694)** using the toolbar icon (either before or after [selecting your page](#selectingyourpageforfurtheraction)):

   ![](assets/screen_shot_2018-03-21at161355.png)

1. Tap/click on the up-arrow at the bottom right of the Timeline column to reveal extra buttons, including **Save as Version**.

   ![](assets/screen_shot_2018-03-21at161507.png)

1. Select **Save as Version**, then **Create**.

### Restoring/Comparing a Version of Your Page {#restoring-comparing-a-version-of-your-page}

The same basic mechanism is used when restoring and/or comparing versions of your page:

1. Select ** [Timeline](../../../sites/authoring/using/basic-handling.md#main-pars-title-281465694)** using the toolbar icon (either before or after [selecting your page](#selectingyourpageforfurtheraction)):

   ![](assets/screen_shot_2018-03-21at161355-1.png)

   If a version of your page has already been saved, this will be listed in the Timeline. 

1. Tap/click on the version you want to restore - this will reveal additional action buttons:

    * **Revert to this Version**

        * The version will be restored.

    * **Show Differences**

        * The page will be opened with differences (between the two versions) highlighted.

