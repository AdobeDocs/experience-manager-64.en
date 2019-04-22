---
title: Track Content Changes Using Task Management
seo-title: Track Content Changes Using Task Management
description: Learn how to track content changes using Task Management.
seo-description: Learn how to track content changes using Task Management.
page-status-flag: de-activated
uuid: 38297f36-19f9-4db9-978b-d317f63b80b3
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 849e79b4-1408-40cc-9325-6ec9d4c4c0d8
---

# Track Content Changes Using Task Management{#track-content-changes-using-task-management}

Task Management enables you to create Projects and Tasks to help manage content change and log change events:

* Create projects that contain related tasks.
* Create tasks to represent work to be performed on content.
* Assign tasks to users or groups who perform the work.

For information about completing tasks that are assigned to you, see [Working with Tasks](/help/sites/authoring/using/task-content.md).

## Creating Projects {#creating-projects}

Create a project to organize a set of related tasks. Projects appear below the Task Projects folder in the left-hand frame of the Projects tab. Projects are automatically assigned to the user who creates the project.

After you create a project, you can populate it with tasks.

![](assets/tmprojects.png)

>[!NOTE]
>
>Members of the Task Administrator Group can see and modify all projects and tasks. If you are not a member of this group you can see and modify only the projects and tasks that you create.

1. Open the Task Management administration page ([http://localhost:4502/libs/cq/taskmanagement/content/taskmanager.html](http://localhost:4502/libs/cq/taskmanagement/content/taskmanager.html)).
1. In the left-hand frame, select the parent folder for the project and click New &gt; New Project.

   >[!NOTE]
   >
   >For a top-level project, select Task Projects as the parent. You can also use other projects as parents.

1. Type a name and description and click OK.

## Creating and Assigning Tasks {#creating-and-assigning-tasks}

Create a task to track the work performed on a content item (page) in the repository. After creating the task, users can open the associated content from the WCM Inbox. (See [Working With Tasks](/help/sites/authoring/using/task-content.md).)

**Task assignment**

Assign a task to the user that should perform the work. When assigned a task, the task appears in the user's Workflow inbox. You can also assign a task to a group. The task appears in the inbox of each user in the group so that any group member can perform the work.

**Scheduling**

Specify the priority of the task and the deadline for completing the task.

**Task lifecycle**

Tasks can have a status of Created or Completed:

* Created: The task is created and appears in the user's inbox. With this status, all content changes are logged. 
* Completed: The user has performed the work on the content. The user sets this status manually upon completing the work. With this status, content changes are no longer logged.

**Subtasks**

Create a heirarchy of tasks to represent task dependencies. Add a task as the child of another task to indicate that the parent depends on the child. The task tree provides a visual representation of task dependency. Dependencies are not enforced, so that parent tasks can be completed before child tasks are completed.

**Note:** If you are archiving tasks, do not complete parent tasks until all subtasks are complete. See [Archiving Tasks](#archiving-tasks).

Select the parent folder of the task to see the details in the right-hand panel.

### Manually Creating Tasks {#manually-creating-tasks}

Use the Task Management console to create tasks for a project.

>[!NOTE]
>
>Members of the Task Administrator Group can see and modify all projects and tasks. If you are not a member of this group you can see and modify only the projects and tasks that you create.

1. In the project tree, select a project or another task and click New &gt; New Task.
1. Specify values for the task properties:

    * Name: The name of the task to appear in the Workflow inbox.
    * Assign To: The name of the user or group who is to work on the task. When assigned to a group, the task appears in each group member's inbox.
    * Content Path: The path of the resource that the task is associated with. Multiple tasks can be associated with the same path.
    * Description: Information about the task, such as instructions to users.
    * Task Priority: The relative priority of the task. The priority is useful for sorting tasks on the Task Management page.
    * Due Date: The date and time by which the user must complete the task.

1. Click OK.

### Automatically Creating Tasks Using Workflows {#automatically-creating-tasks-using-workflows}

Use the Create Task step in a workflow to automatically create a task. The following workflow-specific properties can be configured for the task:

* The task content can either be the workflow payload or a content item that you specify. 
* You can specify one or more actions that the user selects upon completing the task. The action can then be used to determines the workflow route to follow.
* You can provide a script that runs before the task is created. For example, you can manipulate the task content according to logic and runtime data.

For more information, see [Create Task](/help/sites/developing/using/workflows-step-ref.md).

### Modifying Tasks {#modifying-tasks}

When a task is in the Created state, you can change all but the Name property. When a task is completed, you cannot change property values. In either state, you cannot delete a task.

1. Double-click the task.
1. To change task details, edit the form fields to change property values and click Save.
1. To change the status to Complete, click Complete Task.

## Archiving Tasks {#archiving-tasks}

Automatically archive tasks when they are no longer immediately useful. Archived tasks are moved to a location in the repository so that data is persisted for auditing and the tasks do not appear on the Task Management page. Archiving can also improve the responsiveness of the Task Management page when retrieving task data. Responsiveness depends on the number of task nodes that need to be iterated, and the available resources of your server.

Archiving is not peformed by default. When you activate archiving, a cron expression determines when archiving occurs. Only tasks that have been in the completed state for a specified length of time are archived. Furthermore, only top-level tasks (first children of projects) are evaluated for archival. If a top-level task is ready for archival, it and any child tasks are archived.

By default, tasks are stored below the `/etc/taskmanagement/archivedtasks` node in the repository. You can configure the TaskManagement JCR Storage Implementation service to change the storage location.

>[!NOTE]
>
>You can also specify the location to store in-use tasks.

The following procedures assume that you have an application folder below `/apps`.

>[!NOTE]
>
>When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](/help/sites/deploying/using/configuring-osgi.md) for full details.

**Configure task archival:**

Using the appropriate method configure the OSGi service:

* TaskManagement Archiving Service (com.adobe.granite.taskmanagement.impl.jcr.TaskArchiveService)

Configure the following properties to override default values, according to the following table:

<table> 
 <tbody> 
  <tr> 
   <th><p>Name</p> </th> 
   <th><p>Type</p> </th> 
   <th><p>Value</p> </th> 
  </tr> 
  <tr> 
   <td><p>archiving.enabled</p> </td> 
   <td><p>Boolean</p> </td> 
   <td><p>true enables archiving. false disables archiving. The default value is false.</p> </td> 
  </tr> 
  <tr> 
   <td><p>scheduler.expression</p> </td> 
   <td><p>String</p> </td> 
   <td><p>A cron expression that schedules archiving. The default value is 30 0 * * * ? (daily archival at 12:30 AM). <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>archive.since.days.completed</p> </td> 
   <td><p>Long</p> </td> 
   <td><p>The number of days after the task is completed when the task is eligible for archiving. The default value is 365.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Configure task storage locations:**

Using the appropriate method configure the OSGi service:

* TaskManagement JCR Storage Implementation (com.adobe.granite.taskmanagement.impl.jcr.TaskStorageProvider)

Configure the following properties to override default values, according to the following table:

<table> 
 <tbody> 
  <tr> 
   <th>Name</th> 
   <th>Type</th> 
   <th>Value</th> 
  </tr> 
  <tr> 
   <td>taskstorage.historyrootpath</td> 
   <td>String</td> 
   <td>The path of the root folder in the repository where tasks are archived. The default value is /etc/taskmanagement/archivedtasks.</td> 
  </tr> 
  <tr> 
   <td>taskstorage.rootpath</td> 
   <td>String</td> 
   <td>The path of the root folder where tasks are stored. The default value is<br /> /etc/taskmanagement/tasks.</td> 
  </tr> 
  <tr> 
   <td>taskstorage.jcrFilterImplementation</td> 
   <td>Boolean</td> 
   <td>Set to true to use the jcr query filter implementation, false to use the legacy filter. The default value is<br /> true.</td> 
  </tr> 
 </tbody> 
</table>

## Changing the Task Administrator Group {#changing-the-task-administrator-group}

>[!NOTE]
>
>When working with AEM there are several methods of managing the configuration settings for OSGi services; see [Configuring OSGi](/help/sites/deploying/using/configuring-osgi.md) for more details and the recommended practices.

The user group that is set as the Task Administrator Group can see and change all Task Management projects and tasks. The administrators group is the default Task Administrator Group.The Task Administrator Group property of the Task Manager Adapter Factory service stores the name of the group.

To use a `sling:OsgiConfig` node to configure the service, use the following node properties:

* **Node name:** `com.adobe.granite.taskmanagement.impl.service.TaskManagerAdapterFactory`

* **Node property:**

    * Name: `taskmanager.admingroups`  
    
    * Type: `String`
    * Value: The group name.

For information about using `sling:OsgiConfig` nodes, see [Configuring OSGi](/help/sites/deploying/using/configuring-osgi.md).

Use the following procedure to use the Web Console to configure the service:

1. Open the Web Console page and click the Configuration tab. ([http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr))
1. Click Task Manager Adapter Factory.
1. In the Task Administrator Group box, type the name of the user group and then click Save.

