---
title: APIs used in AEM Forms workspace
seo-title: APIs used in AEM Forms workspace
description: Public Java and JavaScript APIs and methods of LiveCycle AEM Forms workspace, exposed for customization and automation.
seo-description: Public Java and JavaScript APIs and methods of LiveCycle AEM Forms workspace, exposed for customization and automation.
uuid: 61212491-3eca-499b-80ba-5783050ef298
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 60e64e82-898d-40bf-9614-3901ff9c8f92
index: y
internal: n
snippet: y
---

# APIs used in AEM Forms workspace{#apis-used-in-aem-forms-workspace}

The following APIs are used in AEM Forms workspace.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody style="font-size: 75%;">
  <tr>
   <td width="20%"><strong>Javascript Method</strong></td> 
   <td width="25%"><strong>Service Name</strong></td> 
   <td width="20"><strong>API Name</strong></td> 
   <td width="20"><strong>Comments</strong></td> 
  </tr>
  <tr>
   <td width="20%">getGroups</td> 
   <td width="25%">ProcessManagementUserProxyService</td> 
   <td width="20">getGroups</td> 
   <td width="20">Searches groups. it returns a list of all the groups if nothing specified, else returns groups with the specified name.</td> 
  </tr>
  <tr>
   <td width="20%">getUsersAndGroups</td> 
   <td width="25%">ProcessManagementUserProxyService</td> 
   <td width="20">getUsersAndGroups</td> 
   <td width="20">Searches users and groups. It returns a list of all the users and groups if nothing specified, else returns users and groups with specified name.</td> 
  </tr>
  <tr>
   <td width="20%">prepareForSubmit</td> 
   <td width="25%">ProcessManagementDocumentHandlingService</td> 
   <td width="20">prepareForSubmit</td> 
   <td width="20">It is called before submitting form via DocumentSubmitServlet. It sets the task ID in a session variable (along with expiry time) which is retrieved during actual submit.</td> 
  </tr>
  <tr>
   <td width="20%">submitTask</td> 
   <td width="25%">ProcessManagementDocumentHandlingService</td> 
   <td width="20">submit</td> 
   <td width="20">It submits the document object associated with a task (and submit process in turn).</td> 
  </tr>
  <tr>
   <td width="20%">getRootEndpointCategories</td> 
   <td width="25%">ProcessManagementStartpointService</td> 
   <td width="20">getRootEndpointCategories</td> 
   <td width="20">It fetches all root categories present on server.</td> 
  </tr>
  <tr>
   <td width="20%">getDirectChildCategories</td> 
   <td width="25%">ProcessManagementStartpointService</td> 
   <td width="20">getDirectChildCategories2</td> 
   <td width="20">It fetches all direct children for a category.</td> 
  </tr>
  <tr>
   <td width="20%">getAllStartpoints</td> 
   <td width="25%">ProcessManagementStartpointService</td> 
   <td width="20">getAllStartpoints</td> 
   <td width="20">It fetches all startpoints present on the server under all categories.</td> 
  </tr>
  <tr>
   <td width="20%">invokeStartpoint</td> 
   <td width="25%">ProcessManagementStartpointService</td> 
   <td width="20">invokeStartpoint</td> 
   <td width="20">This invokes a Startpoint and creates a new task corresponding to a starpoint</td> 
  </tr>
  <tr>
   <td width="20%">getAllTasks</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">getAllActionableTasks</td> 
   <td width="20">It fetches all tasks which are created and forwarded or consulted, saved, assigned, assigned and saved for logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getTask</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">getTask</td> 
   <td width="20">It fetches a specific task.</td> 
  </tr>
  <tr>
   <td width="20%">renderTask</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">render</td> 
   <td width="20">It renders a task and returns information needed to render form like form url, form type, data url if needed etc.</td> 
  </tr>
  <tr>
   <td width="20%">submitWithPriorData</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">submitWithPriorData</td> 
   <td width="20">It returns result of TaskManager’s submit API using the result key.</td> 
  </tr>
  <tr>
   <td width="20%">submitWithData</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">submitWithData</td> 
   <td width="20">It submits the form data (passed as string) associated with task usingTaskManager’s submit API. It is used for flex forms which do not callTaskManager’s submit API.</td> 
  </tr>
  <tr>
   <td width="20%">save</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">save</td> 
   <td width="20">It saves a task on server.</td> 
  </tr>
  <tr>
   <td width="20%">complete</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">complete</td> 
   <td width="20">It completes a task and task is passed to next step as per process design.</td> 
  </tr>
  <tr>
   <td width="20%">getAttachment</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">getAttachment</td> 
   <td width="20">It returns url of a attachment where attachment is available.</td> 
  </tr>
  <tr>
   <td width="20%">getAllAttachments</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">getAllActionableAttachments</td> 
   <td width="20">It fetches all attachments and notes for a task.</td> 
  </tr>
  <tr>
   <td width="20%">share</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">share</td> 
   <td width="20">It shares a task with another user. Another user can claim the task and becomes owner of the task.</td> 
  </tr>
  <tr>
   <td width="20%">forward</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">forward</td> 
   <td width="20">It forwards a task to another user.</td> 
  </tr>
  <tr>
   <td width="20%">consult</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">consult</td> 
   <td width="20">It consults a task with another user.</td> 
  </tr>
  <tr>
   <td width="20%">claim</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">claim</td> 
   <td width="20">It claims a task available in shared queue.</td> 
  </tr>
  <tr>
   <td width="20%">unlock</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">unlock</td> 
   <td width="20">It unlocks a task.</td> 
  </tr>
  <tr>
   <td width="20%">lock</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">lock</td> 
   <td width="20">It locks a task and task can not be claimed by another user if shared.</td> 
  </tr>
  <tr>
   <td width="20%">reject</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">reject</td> 
   <td width="20">It returns task to previous owner of task.</td> 
  </tr>
  <tr>
   <td width="20%">abandon</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">abandon</td> 
   <td width="20">It deletes a task.</td> 
  </tr>
  <tr>
   <td width="20%">setVisibility</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">setVisibility</td> 
   <td width="20">It sets visibility of a task. If visibility is set to false then task will not be visible to user afterwards.</td> 
  </tr>
  <tr>
   <td width="20%">getUsers</td> 
   <td width="25%">ProcessManagementUserProxyService</td> 
   <td width="20">getUsers</td> 
   <td width="20">It is used for searching users. It returns all users if no name is specified else returns users with specified name.</td> 
  </tr>
  <tr>
   <td width="20%">getUsersInGroup</td> 
   <td width="25%">ProcessManagementUserProxyService</td> 
   <td width="20">getUsersInGroupByName</td> 
   <td width="20">It returns all users in a group.</td> 
  </tr>
  <tr>
   <td width="20%">grantQueueAccess</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">grantQueueAccess</td> 
   <td width="20">It grants access of logged in user's queue to specified user. It is basically sharing own queue with another user.</td> 
  </tr>
  <tr>
   <td width="20%">requestQueueAccess</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">requestQueueAccess</td> 
   <td width="20">It makes access request of queue of specified user for logged in user. If user approves the request then user's queue is shared with logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getGrantedUsers</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">getGrantedUsers</td> 
   <td width="20">It returns all users who have access to queue of logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getUsersForAccessibleQueues</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">getUsersForAccessibleQueues</td> 
   <td width="20">It returns all users whose queue is accessible to a user.</td> 
  </tr>
  <tr>
   <td width="20%">revokeQueueAccess</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">revokeQueueAccess</td> 
   <td width="20">It removes a user from the list of users who have access to queue of logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">removeQueueAccess</td> 
   <td width="25%">ProcessManagementQueueService</td> 
   <td width="20">removeQueueAccess</td> 
   <td width="20">It removes a user from the list of users whose queue is accessible to logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getAllQueues<br /> </td> 
   <td width="25%">ProcessManagementQueueService<br /> </td> 
   <td width="20">getAllQueues<br /> </td> 
   <td width="20">It gets all queues (own, shared and group queues) accessible to logged in user.<br /> </td> 
  </tr>
  <tr>
   <td width="20%">getOutOfOfficeSettings</td> 
   <td width="25%">ProcessManagementOutOfOfficeService</td> 
   <td width="20">getOutOfOfficeSettings</td> 
   <td width="20">It gets out of office settings of a user.</td> 
  </tr>
  <tr>
   <td width="20%">saveOutOfOfficeSettingsJson</td> 
   <td width="25%">ProcessManagementOutOfOfficeService</td> 
   <td width="20">saveOutOfOfficeSettingsJson</td> 
   <td width="20">It saves out of office settings of a user.</td> 
  </tr>
  <tr>
   <td width="20%">getAllProcesses</td> 
   <td width="25%">ProcessManagementProcessService</td> 
   <td width="20">getAllProcesses</td> 
   <td width="20">It returns list of all processes.</td> 
  </tr>
  <tr>
   <td width="20%">getParticipatedProcesses</td> 
   <td width="25%">ProcessManagementProcessService</td> 
   <td width="20">getParticipatedProcesses</td> 
   <td width="20">It retuns list of all process names participated by logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getProcessInstance<br /> </td> 
   <td width="25%">ProcessManagementProcessService<br /> </td> 
   <td width="20">getProcessInstance<br /> </td> 
   <td width="20">It fetches details of a process instance.<br /> </td> 
  </tr>
  <tr>
   <td width="20%">getProcessInstances</td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">getProcessInstances</td> 
   <td width="20">It fetches all process instances for a process.</td> 
  </tr>
  <tr>
   <td width="20%">getPendingTasksForProcessInstance</td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">getPendingTasksForProcessInstance</td> 
   <td width="20">It gets pending tasks for a process instance.</td> 
  </tr>
  <tr>
   <td width="20%">getTasksForProcessInstance</td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">getTasksForProcessInstance</td> 
   <td width="20">It gets all tasks for a process instance.</td> 
  </tr>
  <tr>
   <td width="20%">getAllSearchTemplates</td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">getAllSearchTemplates</td> 
   <td width="20">It returns list of all search templates.</td> 
  </tr>
  <tr>
   <td width="20%">getTemplate</td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">getTemplate</td> 
   <td width="20">It returns content for a search template.</td> 
  </tr>
  <tr>
   <td width="20%">findTasksJson<br /> </td> 
   <td width="25%">ProcessManagementQueryService</td> 
   <td width="20">findTasksJson</td> 
   <td width="20">It searches and returns all tasks satisfying all condition of a search template.</td> 
  </tr>
  <tr>
   <td width="20%">getAssignmentsForTask</td> 
   <td width="25%">ProcessManagementTaskService</td> 
   <td width="20">getAssignmentsForTask</td> 
   <td width="20">It gets all assignments for a task. For e.g :- If user forwards or consults a task with another user then it is an assignment for a task.</td> 
  </tr>
  <tr>
   <td width="20%">deleteAttachment </td> 
   <td width="25%">TaskManagerService</td> 
   <td width="20">deleteAttachment</td> 
   <td width="20">It deletes an attachment.</td> 
  </tr>
  <tr>
   <td width="20%">initialize</td> 
   <td width="25%">ProcessManagementClientSessionService</td> 
   <td width="20">initialize</td> 
   <td width="20">It renews assertion if necessary. Authenticates user. Sets session parameters for server / client information. Returns user information and polling interval.</td> 
  </tr>
  <tr>
   <td width="20%">getTasksForDirectReports</td> 
   <td width="25%">ProcessManagementTeamTasksService</td> 
   <td width="20">getTasksForDirectReports</td> 
   <td width="20">It returns all tasks of direct reports of logged in manager.</td> 
  </tr>
  <tr>
   <td width="20%">getTaskOfDirectReport<br /> </td> 
   <td width="25%">ProcessManagementTeamTasksService</td> 
   <td width="20">getDirectReportTask</td> 
   <td width="20">It returns task of specified direct report of logged in manager.</td> 
  </tr>
  <tr>
   <td width="20%">forwardTaskOfDirectReport</td> 
   <td width="25%">ProcessManagementTeamTasksService</td> 
   <td width="20">forwardTaskOfDirectReport</td> 
   <td width="20">It forwards a task of a direct report to another user.</td> 
  </tr>
  <tr>
   <td width="20%">rejectTaskOfDirectReport</td> 
   <td width="25%">ProcessManagementTeamTasksService</td> 
   <td width="20">rejectTaskOfDirectReport</td> 
   <td width="20">It returns a task of a direct report to previous user.</td> 
  </tr>
  <tr>
   <td width="20%">getProperty</td> 
   <td width="25%">WorkspacePropertyService</td> 
   <td width="20">getProperty</td> 
   <td width="20">It gets a Workspace property for a user.</td> 
  </tr>
  <tr>
   <td width="20%">removeProperty</td> 
   <td width="25%">WorkspacePropertyService</td> 
   <td width="20">delete</td> 
   <td width="20">It removes a Workspace property for a user.</td> 
  </tr>
  <tr>
   <td width="20%">getProperties</td> 
   <td width="25%">WorkspacePropertyService</td> 
   <td width="20">getPropertiesAsMap</td> 
   <td width="20">It returns all Workspace properties for a user.</td> 
  </tr>
  <tr>
   <td width="20%">setProperty</td> 
   <td width="25%">WorkspacePropertyService</td> 
   <td width="20">setProperty</td> 
   <td width="20">It sets a Workspace property for a user.</td> 
  </tr>
  <tr>
   <td width="20%">getCurrentUserImageUrl</td> 
   <td width="25%">ProcessManagementClientSessionService</td> 
   <td width="20">getCurrentUserImageUrl</td> 
   <td width="20">It gets user's image url for logged in user.</td> 
  </tr>
  <tr>
   <td width="20%">getUserImageUrl</td> 
   <td width="25%">ProcessManagementClientSessionService</td> 
   <td width="20">getUserImageUrl</td> 
   <td width="20">It gets user's image url for specified user.</td> 
  </tr>
  <tr>
   <td width="20%">uploadNote</td> 
   <td width="25%">ProcessManagementDocumentHandlingService</td> 
   <td width="20">uploadNote</td> 
   <td width="20">It uploads a note on server for a task.</td> 
  </tr>
  <tr>
   <td width="20%">uploadRMAToServer (It's also called directly from html template)<br /> </td> 
   <td width="25%">ProcessManagementDocumentHandlingService</td> 
   <td width="20">uploadAttachment</td> 
   <td width="20">It uploads an attachment on server for a task.</td> 
  </tr>
  <tr>
   <td width="20%">getImageURL (It's also called directly from html template)</td> 
   <td width="25%">ProcessManagementDocumentHandlingService</td> 
   <td width="20">getImage</td> 
   <td width="20">It gets image for a process.</td> 
  </tr>
 </tbody>
</table>

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
