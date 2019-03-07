---
title: Customizing tabs for a task
seo-title: Customizing tabs for a task
description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
seo-description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
uuid: c807c8be-9c94-4701-9b16-6b62784283e3
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 83139a8e-6e93-4636-936d-34080e8d465c
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
