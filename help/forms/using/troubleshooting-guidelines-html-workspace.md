---
title: Troubleshooting guidelines for AEM Forms workspace
seo-title: Troubleshooting guidelines for AEM Forms workspace
description: Enable logs and use debugger in browser to troubleshoot AEM Forms workspace.
seo-description: Enable logs and use debugger in browser to troubleshoot AEM Forms workspace.
uuid: cb62b8fe-b297-4068-849e-6d866afc017b
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: f94a72eb-7d38-430c-81ac-1e516ee7925f
index: y
internal: n
snippet: y
---

# Troubleshooting guidelines for AEM Forms workspace{#troubleshooting-guidelines-for-aem-forms-workspace}

This article discusses how to debug AEM Forms workspace by enabling logging and by using debugger in a browser. It also explains some common issues that you can encounter when using AEM Forms workspace and their workarounds.

## Unable to install AEM Forms workspace package {#unable-to-install-aem-forms-workspace-package}

Ater installing the patch, open the AEM Forms workspace. If you encounter the No Resource Found error, open the CRX Package Manager, and reinstalling the `adobe-lc-workspace-pkg-<version>.zip` package.

While installling the package, if you encounter an error `javax.jcr.nodetype.ConstraintViolationException: OakConstraint0025: Authorizable property rep:authorizableId may not be removed`, perform the following steps:

1. Log in to CRX DE lite. The default url is `http://[localhost]:[port]/lc/crx/de/index.jsp`
1. Delete the following node: 
1. Go to the Package Manager. The default URL is `http://[localhost]:[port]/lc/crx/packmgr/index.jsp.`
1. Search and install the `adobe-lc-workspace-pkg-[version].zip` package.
1. Restart the application server.

## AEM Forms workspace&nbsp;logging {#aem-forms-workspace-nbsp-logging}

You can generate logs at various levels to enable optimal troubleshooting of errors. For example, in a complex application, logging at the component level helps in debugging and troubleshooting specific components.

In AEM Forms workspace:

* To get the logging information about a specific component file, append `/log/<ComponentFile>/<LogLevel>` in the URL, and press `Enter`. All logging information for the component file at the specified log level is printed on the console.

* To get logging information of all component files, append `/log/all/trace` in the URL, and press `Enter`.

* Log format: `<Component file> <Date>:<Time>: <Log Level> : <Log Message>`

>[!NOTE]
>
>By default log level of all components is set to INFO.

* The log level set by user is maintained only for that browser session. When the user refreshes the page, the log level is set to its initial value for all components.

### List of component files in&nbsp;AEM Forms workspace {#list-of-component-files-in-nbsp-aem-forms-workspace}

<table border="1" cellpadding="3" cellspacing="0"> 
 <tbody> 
  <tr> 
   <td valign="top" width="213"><p>allcategoryModel</p> </td> 
   <td valign="top" width="213"><p>processinstanceModel</p> </td> 
   <td valign="top" width="213"><p>tasklistModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>appnavigationModel</p> </td> 
   <td valign="top" width="213"><p>processInstanceView</p> </td> 
   <td valign="top" width="213"><p>tasklistView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>appnavigationView</p> </td> 
   <td valign="top" width="213"><p>processnamelistModel</p> </td> 
   <td valign="top" width="213"><p>taskModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>categorylistModel</p> </td> 
   <td valign="top" width="213"><p>processnamelistView</p> </td> 
   <td valign="top" width="213"><p>taskView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>categorylistView</p> </td> 
   <td valign="top" width="213"><p>processnameModel</p> </td> 
   <td valign="top" width="213"><p>teamqueuesView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>categoryModel</p> </td> 
   <td valign="top" width="213"><p>processnameView</p> </td> 
   <td valign="top" width="213"><p>todoView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>categoryView</p> </td> 
   <td valign="top" width="213"><p>searchtemplatedetailsView</p> </td> 
   <td valign="top" width="213"><p>trackingView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>favoritecategoryModel</p> </td> 
   <td valign="top" width="213"><p>sharequeueModel</p> </td> 
   <td valign="top" width="213"><p>uisettingsModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>filterlistView</p> </td> 
   <td valign="top" width="213"><p>sharequeueView</p> </td> 
   <td valign="top" width="213"><p>uisettingsView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>filterView</p> </td> 
   <td valign="top" width="213"><p>startpointlistModel</p> </td> 
   <td valign="top" width="213"><p>userinfoModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>outofofficeModel</p> </td> 
   <td valign="top" width="213"><p>startpointlistView</p> </td> 
   <td valign="top" width="213"><p>userinfoView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>outofofficeView</p> </td> 
   <td valign="top" width="213"><p>startpointModel</p> </td> 
   <td valign="top" width="213"><p>usersearchModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>preferencesView</p> </td> 
   <td valign="top" width="213"><p>startpointView</p> </td> 
   <td valign="top" width="213"><p>usersearchView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>processinstancehistoryView</p> </td> 
   <td valign="top" width="213"><p>startProcessView</p> </td> 
   <td valign="top" width="213"><p>wserrorModel</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>processinstancelistModel</p> </td> 
   <td valign="top" width="213"><p>startprocessView</p> </td> 
   <td valign="top" width="213"><p>wserrorView</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="213"><p>processinstancelistView</p> </td> 
   <td valign="top" width="213"><p>taskdetailsView</p> </td> 
   <td valign="top" width="213"><p>wsmessageView</p> </td> 
  </tr> 
 </tbody> 
</table>

### Log levels available in&nbsp;AEM Forms workspace {#log-levels-available-in-nbsp-aem-forms-workspace}

* FATAL
* ERROR
* WARN
* INFO
* DEBUG
* TRACE
* OFF

## Debugging information for browsers {#debugging-information-for-browsers}

Scripts and styles can be debugged in different browsers.

* **Debugging in IE**: To debug AEM Forms workspace in IE, see: [http://msdn.microsoft.com/en-us/library/hh772704(v=vs.85).aspx](http://msdn.microsoft.com/en-us/library/hh772704(v=vs.85).aspx).

* **Debugging in Chrome**: To open debugger in Chrome, use the shortcut: Ctrl+Shift+I. For more information, see: [http://developer.chrome.com/extensions/tut_debugging.html](http://developer.chrome.com/extensions/tut_debugging.html).

* **Debugging in Firefox**: Several Add-ons are available to debug scripts and styles in Firefox. For example, Firebug is one such debugging utility ([http://getfirebug.com](http://getfirebug.com)).

## FAQs {#faqs}

1. PDF form is not getting rendered or submitted in Google Chrome.

    1. Install the Adobe® Reader® plug-in.
    1. In Chrome, open chrome://plugins, to view available plug-ins. 
    1. Disable the Chrome PDF Viewer plug-in, and enable the Adobe Reader plug-in.

1. SWF form or Guide is not rendering in Google Chrome.

    1. In Chrome, open chrome://plugins, to view available plug-ins.
    1. See details for Adobe Flash® Player plug-in.
    1. Disable PepperFlash under Adobe Flash Player plug-in.

1. I have customized AEM Forms workspace but I am unable to see the changes.

   Clear your browser's cache, and then access AEM Forms workspace.

1. What needs to be done by the user to enable the form to be rendered in HTML when opened in desktop?

   Select the HTML radio button for default profile in the assign task step while using Workbench.

1. Attachment does not show up when clicked.

   To view attachments, enable popups in your browser.

1. A user is logged in to a forms application. If the user tries to log in to workspace, it may not load, if the user does not have workspace permissions.

   Logout from the other forms application, and then log in to workspace.

1. HTML forms, using Process Properties in their design, when rendered in AEM Forms workspace, display Submit button inside the form.

   When designing forms, when you use Process Properties, it adds a Submit button inside the form. When rendered as a PDF in AEM Forms workspace, the Submit button is not visible to the end user. However, when rendering as an HTML form in AEM Forms workspace, the Submit button is visible to the end user. Clicking on this Submit button inside the form does not initiate any action. Clicking on the Submit button at the bottom of the AEM Forms workspace, outside the form, completes the task.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
