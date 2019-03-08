---
title: Hosting two AEM Forms workspace instances on one server
seo-title: Hosting two AEM Forms workspace instances on one server
description: How LC administrators can customize HTML WS to host two instances on a single server accessible via different URLs.
seo-description: How LC administrators can customize HTML WS to host two instances on a single server accessible via different URLs.
uuid: 26aa8884-3d75-46bb-8519-0ebe936710ed
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 97b12823-7c7c-4881-b0e6-df43ac8740c9
index: y
internal: n
snippet: y
---

# Hosting two AEM Forms workspace instances on one server{#hosting-two-aem-forms-workspace-instances-on-one-server}

The default installation and settings of AEM Forms allow for only one AEM Forms workspace to be available on the server. However, you may need to host two different instances of AEM Forms workspace on a single AEM Forms server. The two instances are accessbile by different URLs.

AEM Forms administrators customize the workspace to create two different URLs and make two workspaces available on the same server. In this customization article, we assume the two workspaces are accessible at `http://[server]:[port]/lc/ws` and `http://[server]:[port]:/lc/ws2`.

Follow these steps to configure AEM Forms workspace.

1. Install the dev package of AEM Forms workspace on your server. See [dev package](../../forms/using/introduction-customizing-html-workspace.md#p-crx-package-p), for instructions to create it.
1. Login to CRXDE Lite as an administrator, by accessing `http://[server]:[port]/lc/crx/de/index.jsp`.
1. Copy node ws at /content and paste at /content. Rename node to ws2. Click **[!UICONTROL Save all]**. In properties of this node, change value of `sling:resourceType` to ws2. Click **[!UICONTROL Save all]**.  

1. Copy folder ws from /libs and paste at /apps. Rename the folder to ws2. Click **[!UICONTROL Save all]**.
1. In `GET.jsp` at `/apps/ws2`, make the following code changes. Replace the following

   ```
   <html lang="en">
   <head>
       <meta charset="utf-8">
       <title>Workspace Next</title>
       <meta http-equiv="refresh" content="0;URL='/lc/libs/ws/index.html'" /><html lang="en">
   <head>
       <meta charset="utf-8">
       <title>Workspace Next</title>
       <meta http-equiv="refresh" content="0;URL='/lc/libs/ws/index.html'" />
   ```

   with the following code

   ```
   <html lang="en">
   <head>
       <meta charset="utf-8">
       <title>Workspace Next</title>
       <meta http-equiv="refresh" content="0;URL='/lc/apps/ws2/index.html'" />
   ```

1. In `registry.js` at `/apps/ws2/js`, change path of templates to refer to templates at `/apps/ws2/js/runtime/templates`. Replace the following code

   ```css
   "tasklist" : {
   "name": "tasklist",
   "path": "tasklistview",
   "model": "tasklist",
   "template": "text!/lc/libs/ws/js/runtime/templates/tasklist.html",
   "utility": "utility",
   "view": "taskview",
   "errorModel": null
   }
   ```

   with the following code

   ```css
   "tasklist" : {
   "name": "tasklist",
   "path": "tasklistview",
   "model": "tasklist",
   "template": "text!/lc/apps/ws2/js/runtime/templates/tasklist.html",
   "utility": "utility",
   "view": "taskview",
   "errorModel": null
   }
   ```

1. In `userinfo.js` at `/apps/ws2/js/runtime/models` and `/apps/ws2/js/runtime/views`, change string `/lc/content/ws` to `lc/content/ws2`.  

1. In `/apps/ws2/js/runtime/services/service.js`, change the path in `getLocalizationData` function to point to `/lc/apps/ws2/Locale.html`.  

1. To refer to `pdf.html` of the new Workspace, change the path of `pdf.html` in `/apps/ws2/js/runtime/views/forms/pdftaskform.js`.  

1. To refer to `pdf.html` of the new Workspace, change paths of `pdf.html` and `WsNextAdapter.swf` in `startprocess.html`, `taskdetails.html`, and `processinstancehistory.html` at `/apps/ws2/js/runtime/templates`.  

1. Copy `/etc/map/ws` folder and paste at `/etc/map`. Rename the new folder to ws2. Click Save all.  

1. In properties of `ws2`, change value of `sling:redirect` to `content/ws2`.  

1. Change value of `sling:match` to `^[^/\||]/[^/\||]/ws2$`.

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

