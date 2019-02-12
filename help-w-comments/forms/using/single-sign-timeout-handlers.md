---
title: Single Sign On and timeout handlers
seo-title: Single Sign On and timeout handlers
description: How-to set the session timeout value for AEM Forms workspace.
seo-description: How-to set the session timeout value for AEM Forms workspace.
uuid: 2966f066-a439-46ad-9fa4-924210f13938
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c34b9643-174a-4a71-b6e0-15e672c6705d
index: y
internal: n
snippet: y
---

# Single Sign On and timeout handlers{#single-sign-on-and-timeout-handlers}

AEM Forms workspace is SSO enabled. If a user has logged in to an AEM Forms application like Forms Manager or PDF Generator user interface and accesses AEM Forms workspace in the same browser session, then the user is logged in to AEM Forms workspace and vice versa.

## Handling server timeout in&nbsp;AEM Forms workspace {#handling-server-timeout-in-nbsp-aem-forms-workspace}

Session timeout for a user can be configured in the Administration Console.

To set the timeout, login to `http://[server]:[port]/adminui`, navigate to **Settings &gt; User Management &gt; Configuration &gt; Configure Advanced System Attributes**, and make the desired settings.

In AEM Forms workspace timeout is handled as:

* Session duration for a user is available in response of `initialize` call that initializes user session.
* A pop-up dialog notifies the user that session is about to expire, 15 seconds before the session expiry.

On this pop-up dialog:

* Click OK to end the user session.
* Click Cancel to reinitialize the user session.

>[!NOTE]
>
>If no action is taken, the user is automatically logged out of AEM Forms workspace three seconds before the session expiry.

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
