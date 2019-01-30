---
title: Changing the font on the interface
seo-title: Changing the font on the interface
description: null
seo-description: How to change the fonts on the user interface selectively.
uuid: 3263a50d-765a-4fd5-b534-c8376d209f7a
acrolinxdate: 2016-05-31T06 47 57.469-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: green
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/changing_font_interface_admin_5e12de0b318c6865_2120_report.xml
acrolinxsentences: 26
acrolinxwords: 319
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 88a81ef3-9473-4032-8d88-95ad9e523542
firstpublishqadate: 2013-02-19T05 45 19.647-0500
isreadyforlocalization: false
lastpublishqadate: 2015-09-28T08 55 19.491-0400
publishqadate: 2015-09-28T08 55 19.491-0400
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/html-workspace/changing-font-interface.html
index: y
internal: n
snippet: y
---

# Changing the font on the interface{#changing-the-font-on-the-interface}

You can change the font displayed in AEM Forms workspace. Fonts used in a specific section of the user interface are defined in the corresponding section of the style sheet. You can change the fonts on the user interface selectively.

Follow the [Generic steps for AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md) and depending on your requirements, follow the steps for customizing CSS, HTML, or both.

1. Change or add the font-family in an existing style.  
1. Change or add the font-family inline for the HTML element.
1. Add a style and use it for the HTML element.

As an example, to change the font of the top navigation bar anchor text to Courier New, follow these steps:

1. Log in to CRXDE Lite by accessing `http://[server]:[port]/lc/crx/de/index.jsp`.
1. Do one of the following:

    1. To change the font-family in an existing style, add the following in the newStyle.css file at /apps/ws/css.

       ```css    
       #topnav a {
          font-family: "Courier New";
       }
       ```

    1. To add the font-family inline for the HTML element, copy the `/libs/ws/js/runtime/templates/appnavigation.html` file to `/apps/ws/js/runtime/templates/appnavigation.html`.

       Update the /apps/ws/js/runtime/templates/appnavigation.html file as follows:

       ```    
       <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
       <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.todo.name')%></a></li>
       <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
       <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
       ```    
    
       Open the /apps/ws/js/registry.js file for editing and replace `text!/lc/libs/ws/js/runtime/templates/appnavigation.html` with `text!/lc/apps/ws/js/runtime/templates/appnavigation.html`.
    
    1. To add a style defining the font-family, add the following in the newStyle.css file at /apps/ws/css.

       ```css    
       .myNewFontStyle a {
          font-family: "Courier New";
       }
       ```    
    
       To add the font-family inline for the HTML element, add the following in the appnavigation.html file at /apps/ws/js/runtime/templates.

       ```css    
       <div id="topnav" class="myNewFontStyle">
           <ul>
               <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
               <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>"><%= $.t('index.header.topnav.todo.name')%></a></li>
               <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
               <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
           </ul>
       </div>
       ```

1. Relaunch the workspace and clear the browser cache for the changes to be visible.

![](assets/change_font_before.png)  ![](assets/change_font_after.png)

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
