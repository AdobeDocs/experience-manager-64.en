---
title: Customizing tabs for a task
seo-title: Customizing tabs for a task
description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
seo-description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
uuid: da1a277c-70fa-4f9d-8c3e-d97d21577bd5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c0e1e7f9-dc38-42d1-86ed-b6fa0420df08
index: y
internal: n
snippet: y
---

# Customizing tabs for a task{#customizing-tabs-for-a-task}

You can customize tab names for the `Start Process` component in the `Start Process` Uber view and the `Task Details` component in the `ToDo` Uber view.

1. Follow the [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md).
1. Change the value of `tabname`in the `translation.json` file.

   For example, change `/apps/ws/locales/en-US/translation.json` for English to the following.

    * For tasks initiated in the start process, use the following snippet from the `"startprocess" : {}` block.

   ```
   "tabname" : {
               "form" : "Application",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Helper Notes"
           }
   ```

    * For tasks in To-do, use the following snippet from the `"todo" : {}` block.

   ```
   "tabname" : {
               "summary" : "Bird's-eye view",
               "history" : "Past",
               "form" : "Form",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Notes"
   }
   ```

   >[!NOTE]
   >
   >Add corresponding key-value pair for all supported languages.

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

