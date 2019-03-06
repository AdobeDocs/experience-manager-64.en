---
title: Displaying information in the Task Summary pane
seo-title: Displaying information in the Task Summary pane
description: In AEM Forms workspace, a Task Summary pane can be configured to summarize the task or display any other web page.
seo-description: In AEM Forms workspace, a Task Summary pane can be configured to summarize the task or display any other web page.
uuid: f52c3153-a945-48b7-9fc6-2c9ad389d235
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 3d9f6ae5-50a1-4557-895d-9c8a6e4aa1c0
index: y
internal: n
snippet: y
---

# Displaying information in the Task Summary pane{#displaying-information-in-the-task-summary-pane}

When you open a task in AEM Forms workspace, a Task Summary pane can display a summary of the task. This additional and relevant information for a task adds more value for the end-user of AEM Forms workspace.

AEM Forms workspace allows you to display a web page of your choice in the Task Summary pane. A process can be created to display a Task Summary pane using Workbench.

1. Create an Assign Task process in Workbench. For more details about Assign Task operation, see Service Reference topic in [Workbench Help](http://help.adobe.com/en_US/AEMForms/6.1/WorkbenchHelp/).

   >[!NOTE]
   >
   >If a TaskSummary URL exists, the Task Summary view opens by default instead of the Form view. In this case, even when a user enables ‘Open the form in maximized mode' option in Assign Task, the form does not open in maximized mode.

1. Configure the Task Summary URL field. You can specify a literal value, a template, a variable, or an XPath expression.
1. An example of displaying the information on Task Summary page is below.

    * Log in to CRXDE Lite environment at `http://[server]:[port]/lc/crx/de`.
    * `Create a node`**SampleSummary** ` under `/content` with type `nt:unstructured`. In the properties of this node, add `sling:resourceType` of type String and value `SampleSummary`. In the Access Control List of this node, add an entry for `PERM_WORKSPACE_USER` allowing `jcr:read` privileges.`
    
    * `Create a folder`**SampleSummary** under `/apps`. In the Access Control List of `/apps/SampleSummary`, add an entry for `PERM_WORKSPACE_USER` allowing `jcr:readprivileges`.
    
    * `Create a file `html.esp` at `/apps/SampleSummary`. For example, add the following lines in `html.esp`.`

   ```
   <html>
       <body>
           <h1>Sample Summary</h1>
           <br/>
           <p>Hello Sir!
               <br/>
               This is sample summary page for this task.
           </p>
       </body>
   </html>
   ```

    * Set the value of task summary url as `/lc/content/SampleSummary.html` in Assign Task step.
    * When the task associated with this Assign Task step is opened in AEM Forms workspace, the `html.esp` at `/apps/SampleSummary` is rendered in task summary pane.

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

