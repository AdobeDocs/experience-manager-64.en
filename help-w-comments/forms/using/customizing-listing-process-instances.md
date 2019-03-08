---
title: Customizing the listing of process instances
seo-title: Customizing the listing of process instances
description: How-to customize the properties displayed in process instance in AEM Forms workspace.
seo-description: How-to customize the properties displayed in process instance in AEM Forms workspace.
uuid: c5134933-55ae-4c43-bbc5-3284f9b803b0
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 101c7f24-e390-4292-9f84-dc1d25e55d47
index: y
internal: n
snippet: y
---

# Customizing the listing of process instances{#customizing-the-listing-of-process-instances}

The process instance list is displayed in the Tracking tab of AEM Forms workspace.

In the process instance list, for each process instance, AEM Forms workspace shows some properties of that instance. The following properties are available for each process instance. These properties are stored as attributes in the process instance component model and are available for use in its view and template.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td style="text-align: center;"><strong>Property</strong></td> 
   <td style="text-align: center;"><strong>Comments</strong></td> 
  </tr> 
  <tr> 
   <td>description</td> 
   <td>Description of the process instance.</td> 
  </tr> 
  <tr> 
   <td>initiator</td> 
   <td>Name of initiator of the process instance.</td> 
  </tr> 
  <tr> 
   <td>initiatorId</td> 
   <td>ID of the initiator of the process instance.</td> 
  </tr> 
  <tr> 
   <td>processCompleteTime</td> 
   <td>Time stamp when the process completed.</td> 
  </tr> 
  <tr> 
   <td>processInstanceId</td> 
   <td>ID of the process instance.</td> 
  </tr> 
  <tr> 
   <td>processInstanceStatus</td> 
   <td>0 = Initiated<br /> 1 = Running<br /> 2 = Complete<br /> 3 = Completing<br /> 4 = Terminated<br /> 5 = Terminating<br /> 6 = Suspended<br /> 7 = Suspending<br /> 8 = Unsuspending</td> 
  </tr> 
  <tr> 
   <td>processName</td> 
   <td>Name of the process.</td> 
  </tr> 
  <tr> 
   <td>processStartTime</td> 
   <td>Time stamp when the process started.</td> 
  </tr> 
  <tr> 
   <td>processVariables</td> 
   <td>Array of objects of process variables. Each process variable object contains <strong>name</strong> (the name of process variable), <strong>value</strong> (value of the process variable), and<strong> type</strong> (the type of process variable).</td> 
  </tr> 
 </tbody> 
</table>

**Example:**

To display the `description` property of the process instance in the process instance card, perform the following steps.

1. Follow the [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md).
1. Do the following:

    1. Copy /libs/ws/js/runtime/templates/processinstance.html to/apps/ws/js/runtime/templates/, if it does not exist. Click **Save All**.
    1. Add process description div with class = 'processDescription' inprocessinstance.html.

   ```
   <div class="processDescription" title="<%= description%>"><%= description%></div>
   ```

1. Do the following:

    1. Open /apps/ws/js/registry.js for editing.
    1. Search and replace `text!/lc/libs/ws/js/runtime/templates/processinstance.html`with `text!/lc/`**apps**/ws/js/runtime/templates/processinstance.html.

1. The above changes may require an update to the CSS file by adding an entry in the style sheet /apps/ws/css/newStyle.css in the following way:

   ```css
   .processinstance .processDescription {
    <!--Dummy values, need to be configured by user as per requirement as well as user can add or delete any property depending upon requirement-->
       width : 250px;
       font-size : 11pt;
       padding : 2px;
   }
   ```

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

