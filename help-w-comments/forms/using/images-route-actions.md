---
title: Customize images used in route actions
seo-title: Customize images used in route actions
description: How-to customize the images used in route actions in LiveCycle AEM Forms workspace.
seo-description: How-to customize the images used in route actions in LiveCycle AEM Forms workspace.
uuid: 9ddc98c6-7c5c-4afa-98df-a36f0d1f9862
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 951e31b4-9db9-4b25-a6c4-465eb52ebde2
index: y
internal: n
snippet: y
---

# Customize images used in route actions{#customize-images-used-in-route-actions}

To customize the images used in route actions, perform the steps described in [Generic Steps of customization](../../forms/using/generic-steps-html-workspace-customization.md) followed by the steps described in this article.

## Images for route actions {#images-for-route-actions}

1. Add the styles defining images in the CSS at the following location for the new route actions:

   `/apps/ws/css/newStyle.css`

   For example: Add a new style called `myStyle1`as shown below and upload the image file `myStyleIcon1.png` to the `/apps/ws/image`s folder using a WebDAV client.

   >[!NOTE]
   >
   >For more information about WebDAV access, see [http://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](http://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

   >[!NOTE]
   >
   >Prefer to use the style name to be same as the route action name.

   ```css
   .myStyle1{
   
           background-image: url('../images/myStyleIcon1.png');
   
       }
   
   ```

## Task List task action popup {#task-list-task-action-popup}

1. Create a task list action popup, see [Building AEM Forms workspace code](../../forms/using/introduction-customizing-html-workspace.md#main-pars-heading-3). It requires to use the dev package.

2. Copy `/libs/ws/js/runtime/templates/task.html` to `/apps/ws/js/runtime/templates/task.html`.

3. If the name of the CSS style is same as the route action name coming from the server, modify the following code in `/apps/ws/js/runtime/templates/task.html`:

```
<%if(routeList == null){%>
            <li>
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
            <li>
                <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
            </li>
            <%}%>
            <%}%>
 
To
 
<%if(routeList == null){%>
            <li class="<%= availableCommands.directCommands[0]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0]+'.value')%>">
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
            <li class="<%= availableCommands.directCommands[i]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
            </li>
            <%}%>
            <%}%>
```

4. If the name of the CSS style is different from the route action name coming from the server, modify the following code in `/apps/ws/js/runtime/templates/task.html`. It adds a stack of the `if-else` servlet conditions to map the style with the route action name.

```
<%if(routeList == null){%>
            <li>
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
            <li>
                <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
            </li>
            <%}%>
            <%}%>
 
To
 
<%if(routeList == null){%>
            <li class="<%= availableCommands.directCommands[0]%>" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0]+'.value')%>">
                <a href="javascript:void(0);" title="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%>" value="<%= availableCommands.directCommands[0]%>" data-action="route"><%= $.t('taskaction.directcommand.'+availableCommands.directCommands[0])%></a>
            </li>
            <%}else{%>
            <%for(var i = 0; i<availableCommands.directCommands.length; i++){%>
                <%if(availableCommands.directCommands[i].equals("myAction1")){%>
                     <li class="myStyle1" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                         <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                     </li>
                <%}else if(availableCommands.directCommands[i].equals("myAction2")){%>
                     <li class="myStyle2" alt="<%= $.t('taskaction.directcommand.'+availableCommands.directCommands[i]+'.value')%>">
                         <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                     </li>
                <%}%>
            <%}%>
            <%}%>
```

## Task Details task action popup {#task-details-task-action-popup}

1. Copy `/libs/ws/js/runtime/templates/taskdetails.html` to `/apps/ws/js/runtime/templates/taskdetails.html`.

2. If the name of the CSS style is same as the route action name coming from the server, modify the following code in `/apps/ws/js/runtime/templates/taskdetails.html`:

```

<%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                        <li class="routeAction">
                            <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                        </li>
                    <%}%>
 
To
 
<%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                        <li class="routeAction">
                            <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                            </a>
                        </li>
                    <%}%>
```

3. If the name of the CSS style is different from the route action name coming from the server, modify the following code in `/apps/ws/js/runtime/templates/taskdetails.html`. It adds a stack of `if-else` servlet conditions to map the style with the route action name.

```

<%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                        <li class="routeAction">
                            <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route"><%= availableCommands.directCommands[i]%></a>
                        </li>
                    <%}%>
 
To
 
<%for (var i = 0; i < availableCommands.directCommands.length; i++) {%>
                <%if(availableCommands.directCommands[i].equals("myAction1")){%>
                     <li class="routeAction">
                            <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="myStyle1" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                            </a>
                        </li>
                <%}else if(availableCommands.directCommands[i].equals("myAction2")){%>
                     <li class="routeAction">
                            <a href="javascript:void(0);" title="<%= availableCommands.directCommands[i]%>" value="<%= availableCommands.directCommands[i]%>" data-action="route">
                               <i class="myStyle2" value="<%= availableCommands.directCommands[i]%>" data-action="route"/>
                            </a>
                        </li>
                <%}%>
            <%}%>
```

4. Open `/apps/ws/js/registry.js` for editing and look for the following text :  
`"text!/lc/libs/ws/js/runtime/templates/taskdetails.html"`

5. Replace the text with the following:  
`"text!/lc/apps/ws/js/runtime/templates/taskdetails.html"`

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

