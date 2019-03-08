---
title: Getting Task Variables in Summary URL
seo-title: Getting Task Variables in Summary URL
description: How-to reuse the information about a task and generate a Summary URL to summarize or describe a task.
seo-description: How-to reuse the information about a task and generate a Summary URL to summarize or describe a task.
uuid: 0d54ce46-9311-4d74-a0f3-1456e4c2d230
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 5ab6e4d8-d70d-408e-a751-9e6aafcd3c8e
index: y
internal: n
snippet: y
---

# Getting Task Variables in Summary URL{#getting-task-variables-in-summary-url}

The summary page displays task-related information. This article describes how you can reuse task-related information in the summary page.

In this sample orchestration, an employee submits a leave application form. The application form then goes to the employee's manager for approval.

1. Create a sample HTML renderer (html.esp) for resourseType **Employees/PtoApplication**.

   The renderer assumes the following properties to be set on the node:

    * ename
    * empid
    * reason
    * duration

   **Note**: This renderer is the summary page template.

   The following sample code for this renderer is contained in:

   `apps/Employees/PtoApplication/html.esp`

   ```
   <html>
     <body>
       <table style="background-color: #647B7B;color: WHITE;text-align: left;width: 100%;font-size: 24px;line-height: 40px;">
       <tbody>
       <tr>
           <td style="width:50%;">
               <h3>Employee Name: <%= currentNode.ename %></h3>
               <h3>Employee ID: <%= currentNode.eid %></h3>
               <h3>Leave duration: <%= currentNode.duration %> days</h3>
               <h3>Reason: <%= currentNode.reason %></h3>
           </td>
       </tr>
       </tbody>
       </table>
     </body>
   </html>
   ```

1. Modify the orchestration to extract the four properties from the submitted form data. After this create a node in CRX of type **Employees/PtoApplication**, with the properties populated.

    1. Create a process **create PTO summary** and use this as a subprocess before the **Assign Task** operation in your orchestration.
    1. Define **employeeName**, **employeeID**, **ptoReason**, **totalDays**, and **nodeName **as input variables in your new process. These variables will be passed as submitted form data.

       Also define an output variable **ptoNodePath **which will be used while setting the summary Url.
    
    1. In the **create PTO summary** process, use the **set value** component to set the input details in a **nodeProperty **(**nodeProps**) map.

       The keys in this map should be the same as the keys defined in your HTML renderer in the previous step.

       Also, add a **sling:resourceType** key with value **Employees/PtoApplication** in the map.
    
    1. Use the subprocess **storeContent** from the **ContentRepositoryConnector** service in the **create PTO summary** process. This subprocess creates a CRX node.

       It takes three input variables:

        * **Folder Path**: The path where the new CRX node is created. Set the path as **/content**.
        
        * **Node name**: Assign the input variable nodeName to this field. This is a unique node name string. 
        * **Node Type**: Define the type as **nt:unstructured**. The output of this process is nodePath. The nodePath is the CRX path of the newly created node. The ndoePath would be the final output of the **create PTO** summary process.

    1. Pass the submitted form data (**employeeName**, **employeeID**, **ptoReason**, and **totalDays**) as input to the new process **create PTO summary**. Take the output as **ptoSummaryNodePath**.

1. Define the summary Url as an XPath expression containing the server details along with **ptoSummaryNodePath**.

   XPath: `concat('http://[*server*]:[*port*]/lc',/process_data/@ptoSummaryNodePath,'.html')`.

In AEM Forms workspace, when you open a task, the summary Url accesses the CRX node, and the HTML renderer displays the summary.

The summary layout can be changed without modifying the process. The HTML renderer displays the summary appropriately.

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

