---
title: Changing the color scheme of the interface
seo-title: Changing the color scheme of the interface
description: How to modify the color scheme of AEM Forms workspace user interface portions selectively.
seo-description: How to modify the color scheme of AEM Forms workspace user interface portions selectively.
uuid: 218647f2-56db-4747-9902-0dbadb83cf04
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 725c1d0a-014b-4005-b2e8-400ca5e448da
index: y
internal: n
snippet: y
---

# Changing the color scheme of the interface{#changing-the-color-scheme-of-the-interface}

You can modify the color scheme of AEM Forms workspace user interface portions to suit your requirements. Following are some examples of representative color scheme customizations. In addition to the steps discussed in this article, see [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md).

## Top navigation bar {#top-navigation-bar}

### Using background image {#using-background-image}

To update the navigation bar at the top of AEM Forms workspace.

1. Create a background image to update the color. Name the file as newBackground.jpg.
1. Upload the background image file in /apps/ws/images folder using a WebDAV client.

   >[!NOTE]
   >
   >For more information about WebDAV access, see [http://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](http://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

1. Reference the new background image in /apps/ws/css/newStyle.css by adding following style.

   ```css
   #header {
       background:#292929 url(../images/newBackground.jpg) repeat-x;
   }
   ```

<!--
Comment Type: remark
Last Modified By: (upgoyal)
Last Modified Date: 2018-01-18T11:26:01.662-0500
<p>1. Generic steps of customization are already mentioned in the beginning of this article.</p>
<p>2. I think link to CSS cutomization document should also present.</p>
<p><br type="_moz" /> </p>
-->

### Using color property in CSS {#using-color-property-in-css}

1. Add the following style in newStyle.css at /apps/ws/css

   ```css
   #header {
   background : none;
   background-color: gray;
   }
   ```

## Category component {#category-component}

Category component displays the various categories of your tasks in the left panel. To change its color, define the background color in `.category` element of the CSS file.

## Task component {#task-component}

Tasks are displayed in the middle panel called the TaskList Component. To change its color, modify the style associated with .task selector in the style sheet.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

<!--
<related-links>
<a href="../../forms/using/introduction-customizing-html-workspace.md">Introduction to Customizing AEM Forms workspace</a>
<a href="../../forms/using/generic-steps-html-workspace-customization.md">Generic steps for AEM Forms workspace customization</a>
<a href="../../forms/using/tasks-organizational-hierarchy-using-manager.md">Managing tasks in an organizational hierarchy using Manager View</a>
<a href="../../forms/using/integrating-correspondence-management-html-workspace.md">Integrating Correspondence Management in AEM Forms workspace</a>
<a href="../../forms/using/single-sign-timeout-handlers.md">Single Sign On and timeout handlers</a>
<a href="../../forms/using/displaying-user-avatar.md">Displaying the user avatar</a>
<a href="../../forms/using/displaying-information-task-summary-pane.md">Displaying information in the Task Summary pane</a>
<a href="../../forms/using/changing-organization-logo-branding.md">Changing the organization logo</a>
<a href="../../forms/using/changing-color-scheme-interface.md">Changing the color scheme of the interface</a>
<a href="../../forms/using/changing-font-interface.md">Changing the font on the interface</a>
<a href="../../forms/using/changing-locale-user-interface.md">Changing the locale of the user interface</a>
<a href="../../forms/using/customizing-error-dialogs.md">Customizing error dialogs</a>
<a href="../../forms/using/customizing-tabs-task.md">Customizing tabs for a task</a>
<a href="../../forms/using/customizing-task-actions.md">Customizing Task Actions</a>
<a href="../../forms/using/customizing-listing-process-instances.md">Customizing the listing of process instances</a>
<a href="../../forms/using/customizing-task-details-page.md">Customizing the task Details page</a>
<a href="../../forms/using/display-additional-data-in-todo-list.md">Displaying additional data in ToDo list</a>
<a href="../../forms/using/getting-task-variables-summary-url.md">Getting Task Variables in Summary URL</a>
<a href="../../forms/using/images-route-actions.md">Images for Route Actions</a>
<a href="../../forms/using/creating-new-login-screen.md">Creating a new login screen</a>
<a href="../../forms/using/minification-javascript-files.md">Minification of the JavaScript files</a>
<a href="../../forms/using/sorting-tracking-tables-add-columns.md">Sorting of Tracking tables and adding more columns</a>
<a href="../../forms/using/updating-link-help-documentation.md">Updating the link to the documentation</a>
<a href="../../forms/using/two-html-workspace-instances-one.md">Hosting two AEM Forms workspace instances on one server</a>
</related-links>
-->

