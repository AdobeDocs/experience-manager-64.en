---
title: Changing the organization logo for branding
seo-title: Changing the organization logo for branding
description: null
seo-description: To brand AEM Forms workspace provide the logo of your organization by customizing the default logo.
uuid: 1862b833-7ccb-490e-ab47-a5f064e429f2
acrolinxdate: 2016-05-31T06 47 58.685-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/changing_organization_logo_branding_admin_5e12de0b318c6865_2121_report.xml
acrolinxsentences: 9
acrolinxwords: 129
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 6f6b0409-b458-41e2-a262-120e4e85eae3
firstpublishqadate: 2013-02-19T05 45 17.569-0500
isreadyforlocalization: false
lastpublishqadate: 2015-09-28T07 37 24.136-0400
publishqadate: 2015-09-28T07 37 24.136-0400
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/html-workspace/changing-organization-logo-branding.html
index: y
internal: n
snippet: y
---

# Changing the organization logo for branding{#changing-the-organization-logo-for-branding}

The organization logo is displayed at the upper-left corner of AEM Forms workspace. To update the logo, follow the [Generic steps of AEM Forms workspace customization](../../forms/using/generic-steps-html-workspace-customization.md#generic-steps-for-html-workspace-customization) and then the following steps.

1. Create a logo and name the file as `NewWorkspace.png`. Place the image file in /apps/ws/images folder using a WebDAV client.

   >[!NOTE]
   >
   >The recommended size of the logo image is 218 px × 20 px.

   >[!NOTE]
   >
   >For more information about WebDAV access, see [http://dev.day.com/docs/en/crx/current/how_to/webdav_access.html](http://docs.adobe.com/docs/en/crx/current/how_to/webdav_access.html).

1. Reference the new logo image in style sheet at /apps/ws/css/newStyle.css by adding following style.

   ```css
   #logo {
   
          background: url(../images/NewWorkspace.png) no-repeat 14px 11px;
   
   }
   ```

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
