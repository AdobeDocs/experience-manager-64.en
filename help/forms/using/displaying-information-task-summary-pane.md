---
title: Displaying information in the Task Summary pane
seo-title: Displaying information in the Task Summary pane
description: null
seo-description: In AEM Forms workspace, a Task Summary pane can be configured to summarize the task or display any other web page.
uuid: b4115a32-2f6a-4b2e-9820-60ad57efd61c
acrolinxdate: 2016-05-31T06 47 39.232-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/displaying_information_task_summary_pane_admin_5e12de0b318c6865_2115_report.xml
acrolinxsentences: 25
acrolinxwords: 345
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 405a7916-0735-4ef9-bfeb-e8ccb5e26514
firstpublishqadate: 2013-02-19T05 45 22.548-0500
isreadyforlocalization: false
lastpublishqadate: 2015-09-18T10 58 11.075-0400
publishqadate: 2015-09-18T10 58 11.075-0400
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/html-workspace/displaying-information-task-summary-pane.html
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

>[!MORE_LIKE_THIS]
>
>* [Introduction to Customizing AEM Forms workspace](../../forms/using/introduction-customizing-html-workspace.md)
>* [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md)
>* [Managing tasks in an organizational hierarchy using Manager View](../../forms/using/tasks-organizational-hierarchy-using-manager.md)
>* [Integrating Correspondence Management in AEM Forms workspace](../../forms/using/integrating-correspondence-management-html-workspace.md)
>* [Single Sign On and timeout handlers](../../forms/using/single-sign-timeout-handlers.md)
>* [Displaying the user avatar](../../forms/using/displaying-user-avatar.md)
>* [Displaying information in the Task Summary pane](../../forms/using/displaying-information-task-summary-pane.md)
>* [Changing the organization logo](../../forms/using/changing-organization-logo-branding.md)
>* [Changing the color scheme of the interface](../../forms/using/changing-color-scheme-interface.md)
>* [Changing the font on the interface](../../forms/using/changing-font-interface.md)
>* [Changing the locale of the user interface](../../forms/using/changing-locale-user-interface.md)
>* [Customizing error dialogs](../../forms/using/customizing-error-dialogs.md)
>* [Customizing tabs for a task](../../forms/using/customizing-tabs-task.md)
>* [Customizing Task Actions](../../forms/using/customizing-task-actions.md)
>* [Customizing the listing of process instances](../../forms/using/customizing-listing-process-instances.md)
>* [Customizing the task Details page](../../forms/using/customizing-task-details-page.md)
>* [Displaying additional data in ToDo list](../../forms/using/display-additional-data-in-todo-list.md)
>* [Getting Task Variables in Summary URL](../../forms/using/getting-task-variables-summary-url.md)
>* [Images for Route Actions](../../forms/using/images-route-actions.md)
>* [Creating a new login screen](../../forms/using/creating-new-login-screen.md)
>* [Minification of the JavaScript files](../../forms/using/minification-javascript-files.md)
>* [Sorting of Tracking tables and adding more columns](../../forms/using/sorting-tracking-tables-add-columns.md)
>* [Updating the link to the documentation](../../forms/using/updating-link-help-documentation.md)
>* [Hosting two AEM Forms workspace instances on one server](../../forms/using/two-html-workspace-instances-one.md)
