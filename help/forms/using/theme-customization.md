---
title: Theme Customization
seo-title: Theme Customization
description: null
seo-description: How to customize the theme of your AEM Forms app.
uuid: 8322aabd-65bd-43b6-9f79-6f9647d44c66
acrolinxdate: 2016-05-31T06 50 28.947-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/theme_customization_admin_5e12de0b318c6865_2165_report.xml
acrolinxsentences: 35
acrolinxwords: 275
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: bae95271-ba2a-4a13-95aa-a73fad4d78b2
firstpublishqadate: 2013-02-20T08 58 58.807-0500
isreadyforlocalization: false
lastpublishqadate: 2015-11-20T08 18 50.169-0500
locpublishdate: 09/06/13
locpublishoption: later
publishqadate: 2015-11-20T08 18 50.169-0500
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/mobile-workspace/theme-customization.html
index: y
internal: n
snippet: y
---

# Theme Customization{#theme-customization}

You can customize the HTML code and CSS file to provide a distinct organization-specific look and feel to AEM Forms app. For example, you can change the background color and height of tasks or Startpoints. The following example provides instructions to change:

* display instructions in place of the description  
* number of display routes  
* background gradient color

### Steps {#steps}

1. Open your project.

    * For iOS, open `Capture.xcodeproj` in Xcode
    * For Android, open the Android project in Eclipse. 
    * For Windows, open `MWSWindows.sln` in Visual Studio.

1. Navigate to the templates folder.

    * In Xcode, navigate to the **Capture &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; templates**folder.
    * In Eclipse, navigate to the** assets &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; templates**folder.
    * In Visual Studio, navigate to the **MWSWindows &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; templates** folder.

1. Open the `template.html` file for editing.
1. Locate the following string:

   ```
   <%if ( (task.description !== "") && (task.description !== null) && (typeof task.description !== null) && (typeof task.description !== 'undefined') ) {%>
                  <div class="description_details">
                    <%= task.description %>
                  </div>
                 <%} else 
   ```

   Replace it with `<%`.

1. Locate the following code in the `template.html` file:

   ```
   <ul id="task_menu_list">
                                   <li class="approve" title="<%= task.availableCommands.directCommands[0]%>" data-routename="<%= task.availableCommands.directCommands[0]%>">
                                       <%= task.availableCommands.directCommands[0]%>
                                   </li>
                                   <li class="reject last" title="<%= task.availableCommands.directCommands[1]%>" data-routename="<%= task.availableCommands.directCommands[1]%>">
                                       <%= task.availableCommands.directCommands[1]%>
                                   </li>
   ```

1. Comment the following line and save the file.

   ```
   task.availableCommands.directCommands[1]%>">
   <%= task.availableCommands.directCommands[1]%>
   </li>
   ```

1. Navigate to the css folder.

    * In Xcode, navigate to **Capture &gt; www &gt; wsmobile &gt; css**.  
    
    * In Eclipse, navigate to **assets &gt; www &gt; wsmobile &gt; css**.
    * In Visual Studio, navigate to **MWSWindows &gt; www &gt; wsmobile &gt; css**.

1. 
   Open the `_style.css` file for editing.  
1. For Background image, change `#323232` to `#fff`.
1. Save the changes and close `_style.css` file.
1. Open the AEM Forms app.

   The AEM Forms app now displays instructions instead of description.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
