---
title: Minification of the JavaScript files
seo-title: Minification of the JavaScript files
description: Instructions to generate minified code after AEM Forms workspace customizations to optimize the JS files for the web.
seo-description: Instructions to generate minified code after AEM Forms workspace customizations to optimize the JS files for the web.
uuid: 5b4b44d4-038e-49eb-9214-44704d7b33c3
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: f6a5967f-f9f8-4918-a849-c210a2f63f68
index: y
internal: n
snippet: y
---

# Minification of the JavaScript files{#minification-of-the-javascript-files}

Minification removes from the source code the redundant characters, such as white space, new line, and comments. This improves the performance by reducing the size of the code. While minification does not impact the functionality, it reduces the readability of the code.

To generate minified code for semantic changes follow these steps.

1. Copy `client-html/src/main/webapp/js` from src-package on filesystem.

   >[!NOTE]
   >
   >See [Introduction to Customizing AEM Forms workspace](../../forms/using/introduction-customizing-html-workspace.md) for more details about the packages.

1. Update paths in `main.js` located under client-html/src/main/webapp/js, for added/updated models/views.

   For example, addition of a new Sharequeue model, say mySharequeue, change:

   ```
   sharequeuemodel : pathprefix + 'runtime/models/sharequeue',
   
   To
   
   sharequeuemodel : pathprefix + 'runtime/myModels/mySharequeue',
   ```

1. Update `registry-config.xml, located at client-html/src/main/webapp/js/resource_generator,` in case there is change/addition of alias in `main.js`.

   For example, addition of a new Sharequeue model, say mySharequeue, change:

   ```xml
   <sharequeue
               name="sharequeue"
               path="runtime/models/sharequeue.js"
               service="service"/>
   
   To
   
   <sharequeue
               name="sharequeue"
               path="runtime/myModels/mySharequeue.js"
               service="service"/>
   ```

1. At client-html/src/main/webapp/js/minifier, run command:

   ```shell
   mvn clean install
   ```

   It generates a folder minified-files, under client-html/src/main/webapp/js with minified main.js and registry.js.

>[!NOTE]
>
>Minification will only work on 64-bit JVM.

>[!NOTE]
>
>If you minify, upgrade is impacted.

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
