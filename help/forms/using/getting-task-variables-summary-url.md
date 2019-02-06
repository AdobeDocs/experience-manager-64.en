---
title: Getting Task Variables in Summary URL
seo-title: Getting Task Variables in Summary URL
description: How-to reuse the information about a task and generate a Summary URL to summarize or describe a task.
seo-description: How-to reuse the information about a task and generate a Summary URL to summarize or describe a task.
uuid: c97a548a-e390-45ce-b201-903fdab1498e
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ba12daf6-d5cb-4879-b19f-f528822aff62
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
