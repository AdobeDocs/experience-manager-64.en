---
title: Working with Page Versions
seo-title: Working with Page Versions
description: null
seo-description: Create, compare, and restore versions of a page
uuid: d92adcd1-f3bb-41c4-8aa1-7c943939157f
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: b1e457c5-3109-42c1-934c-6f7e5fc29420
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Working with Page Versions{#working-with-page-versions}

Versioning creates a "snapshot" of a page at a specific point in time. With versioning, you can perform the following actions:

* Create a version of a page.
* Restore a page to a previous version in order to undo a change that you made to a page, for example.
* Compare the current version of a page with a previous version with differences in the text and images highlighted.

## Creating a New Version {#creating-a-new-version}

You can create a version of your resource from:

* the [Timeline rail](#creatinganewversiontimeline)
* the [Create](#creatinganewversioncreatewithaselectedresource) option (when a resource is selected)

### Creating a New Version - Timeline {#creating-a-new-version-timeline}

1. Navigate to show the page for which you want to create a version.
1. Select the page in [selection mode](../../authoring/using/basic-handling.md#main-pars-title-14).
1. Open the **Timeline** column.
1. Click/tap on the arrowhead by the comment field to reveal the options:

   ![](assets/screen_shot_2018-03-21at155035.png)

1. Select **Save as Version**.
1. Enter a **Label** and **Comment** if required.

   ![](assets/chlimage_1-81.png)

1. Confirm the new version with **Create**.

   The information in the timeline will be updated to indicate the new version.

### Creating a New Version - Create with a Selected Resource {#creating-a-new-version-create-with-a-selected-resource}

1. Navigate to show the page for which you want to create a version.
1. Select the page in [selection mode](../../authoring/using/basic-handling.md#main-pars-title-14).
1. Select the **Create** option from the toolbar.
1. The dialog will open. You can enter a **Label** and a **Comment** if required:

   ![](assets/screen_shot_2012-02-15at105050am.png)

1. Confirm the new version with **Create**.

   The timeline will be opened with the information updated to indicate the new version.

## Reverting to a Page Version {#reverting-to-a-page-version}

Once a version has been created you can revert to that version if needed.

>[!NOTE]
>
>When restoring a page, the version created will be part of a new branch.
>
>To illustrate:  

>
>* Create versions of any page.
>* The initial labels and version node names will be 1.0, 1.1, 1.2 and so forth.  
>* Restore the first version; i.e. 1.0.
>* Create new versions again.
>* The generated labels and node names will now be 1.0.0, 1.0.1, 1.0.2, etc.
>

To revert to a previous version:

1. Navigate to show the page you want to revert to a previous version.
1. Select the page in [selection mode](../../authoring/using/basic-handling.md#main-pars-title-14).
1. Open the **Timeline** column and select either **Show All** or **Versions**. The page versions for the selected page will be listed.
1. Select the version you want to revert to. The possible options will be shown:

   ![](assets/screen_shot_2018-03-21at155246.png)

1. Select **Revert to this Version**. The selected version will be restored and the information in timeline will be updated.

## Comparing a Version with Current Page {#comparing-a-version-with-current-page}

To compare a previous version with the current page:

1. Navigate to show the page you want to compare.
1. Select the page in [selection mode](../../authoring/using/basic-handling.md#main-pars-title-14).
1. Open the **Timeline** column and select either **Show All** or **Versions**.
1. The page versions will be listed. Select the version you want to compare:

   ![](assets/screen_shot_2018-03-21at155330.png)

1. Select **Compare to Current**. The [page diff](../../authoring/using/page-diff.md) will open and display the differences.

## Timewarp {#timewarp}

Timewarp is a feature designed to simulate the *published* state of a page at specific times in the past.

The purpose is to allow you to track the published website at the selected point in time. This uses the page versionss to determine the state of the publish environment.

To do this:

* The system looks for the page version that was active at the selected time.
* This means the version shown was created/activated *before* the point in time selected in Timewarp.
* When navigating to a page that has been deleted this will also be rendered - as long as the old versions of the page are still available in the repository.
* If no published version is found, then Timewarp will revert to the current state of the page on the author environment (this is to prevent an error/404 page, which would prevent browsing).

>[!NOTE]
>
>If versions are removed from the repository then Timewarp cannot show the correct view.
>
>If elements (such as code, css, assets/images, etc) for rendering the website have changed, the view will differ from what it originally was, as those items are not versioned in the repository.

### Using Timewarp {#using-timewarp}

Timewarp is a [mode](../../authoring/using/author-environment-tools.md#main-pars-title-20) of the page editor. To start it, simply switch it as you would any other mode.

1. Start the editor for the page where you wish to start Timewarp and then select **Timewarp** in the mode selection.

   ![](assets/screen_shot_2018-03-21at155416.png)

1. In the dialogue set a target date and time and click or tap **Set Date**. If you do not select a time, the current time will default.

   ![](assets/screen_shot_2018-03-21at155513.png)

1. The page is displayed based on the date set. Timewarp mode is indicated via the blue status bar at the top of the window. Use the links in the status bar to select a new target date or exit Timewarp mode.

   ![](assets/screen_shot_2018-03-21at155544.png)

>[!NOTE]
>
>Timewarp will only work fully if you have previously published the page. If not, timewarp will show the current page on the author environment.

>[!NOTE]
>
>If you navigate to a page that has been removed/deleted from the repository it will be rendered properly if old versions of the page are still available in the repository.

>[!NOTE]
>
>You cannot edit the old version of the page. It is only available for viewing. If you want to restore the older version you will have to do that manually using [restore](../../authoring/using/working-with-page-versions.md#main-pars-title-1).

