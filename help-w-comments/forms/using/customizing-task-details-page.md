---
title: Customizing the task details page
seo-title: Customizing the task details page
description: How-to customize the task details page in AEM Forms workspace to modify the default information displayed about a task.
seo-description: How-to customize the task details page in AEM Forms workspace to modify the default information displayed about a task.
uuid: 8ae58aae-9b12-4361-a10f-024c0dcc58eb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ebe3aa9d-81fa-44a2-80cb-1993cef2fabe
index: y
internal: n
snippet: y
---

# Customizing the task details page{#customizing-the-task-details-page}

The task details page contains information about a task and its processes. However, you can customize the task details page to add or delete information.

You can add the following information to the task details page:

* Information available in the JSON object of a task (Task section in [AEM Forms workspace JSON Object Description](../../forms/using/html-workspace-json-object-description.md))
* Information available in the JSON object of a process instance (Process instance section in [AEM Forms workspace JSON Object Description](../../forms/using/html-workspace-json-object-description.md))

To customize the task details page:

1. Follow [Generic steps for AEM Forms workspace customization.](../../forms/using/generic-steps-html-workspace-customization.md)
1. To show any additional information, add corresponding key-value pairs to the `translation.json` file at `todo`block > `details`block > `app`block > [ `required`block].

   The [ `required`block] refers to available blocks, such as the task block for task information, process block for process information, and currentpendingtask block for pending tasks information.

   For example, to add information about Route Selection Required in the task details page, you can add the following key-value pair in the task block:

   ```
   "todo" : {
       .
       .
       .
       "details" : {
           .
           .
           "task" : {
               .
               .
               "RouteSelectionRequired" : "Route Selection Required"
           }
       }
   }
   ```

   >[!NOTE]
   >
   >Add corresponding key-value pairs for all the supported languages.

1. Copy `/libs/ws/js/runtime/templates/taskdetails.html` to `/apps/ws/js/runtime/templates/taskdetails.html`.

   Add the new information to `/apps/ws/js/runtime/templates/taskdetails.html`. For example:

   ```css
   <div class="detailsContainer">
       .
       .
       <ul>
           .
           .
           <li>
               <label for="routeSelectionRequired" title="<%= $.t('todo.details.task.RouteSelectionRequired')%>"><%= $.t('todo.details.task.RouteSelectionRequired')%></label>
               <div>
                   <span id="routeSelectionRequired"><%= isRouteSelectionRequired != null ? isRouteSelectionRequired : ''%></span>
               </div>
           </li>
           .
           .
       </ul>
   </div>
   ```

1. Open /apps/ws/js/registry.js for editing.

   Search and replace `text!/lc/libs/ws/js/runtime/templates/taskdetails.html` with `text!/lc/apps/ws/js/runtime/templates/taskdetails.html`.

>[!NOTE]
>
>To customize the task details page with tasks created in the **Start Process **tab of AEM Forms workspace, add the new information to `/apps/ws/js/runtime/templates/startprocess.html`.
>
>To add new styles for the information added in the details page, modify the CSS file by using the *User interface changes* section in [Workspace Customization](../../forms/using/changing-locale-user-interface.md#main-pars-header-3).

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

