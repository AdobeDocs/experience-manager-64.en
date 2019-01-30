---
title: Gesture customization
seo-title: Gesture customization
description: null
seo-description: Customize the gestures on your AEM Forms app
uuid: dc54c6da-f8ee-424c-9607-dfb970ba1f05
acrolinxdate: 2016-05-31T06 50 05.608-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/gesture_customization_admin_5e12de0b318c6865_2156_report.xml
acrolinxsentences: 27
acrolinxwords: 318
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 71ae26fc-c893-49d3-8fc3-742b266b47ff
firstpublishqadate: 2013-02-20T08 59 15.288-0500
isreadyforlocalization: false
lastpublishqadate: 2015-11-20T08 18 52.526-0500
locpublishdate: 09/06/13
locpublishoption: later
publishqadate: 2015-11-20T08 18 52.526-0500
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/mobile-workspace/gesture-customization.html
index: y
internal: n
snippet: y
---

# Gesture customization{#gesture-customization}

You can customize the gestures of AEM Forms app to provide a distinct method of interacting with the app. For example, you can add new gestures to open or close a task or Startpoint.

### To customize gestures in AEM Forms app {#to-customize-gestures-in-aem-forms-app}

In the AEM Forms app, the left swipe opens up a new task or Startpoint while right swipe does nothing. The following example provides steps to open up a new task or Startpoint on performing the right-swipe gestures in the AEM Forms app.

1. Open your project.

    * For iOS, open `Capture.xcodeproj` in Xcode
    * For Android, open the Android project in Eclipse. 
    * For Windows, open `MWSWindows.sln` in Visual Studio.

1. Navigate to the views folder and open the `task.js` file for editing.

    * In Xcode, navigate to the **Capture &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; views **folder.
    * In Eclipse, navigate to the** assets &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; views** folder.
    * In Visual Studio, navigate to the **MWSWindows &gt; www &gt; wsmobile &gt; js &gt; runtime &gt; views** folder.

   >[!NOTE]
   >
   >The task.js file contains the backbone view associated with each task or Startpoint listed in the task or Startpoint lists.

   <!--
   Comment Type: remark
   Last Modified By: Peter G.A. Barraud (barraud)
   Last Modified Date: 2017-11-30T06:09:51.366-0500
   <p>SP1 UPDATE</p>
   <p>Is the task.js used for both tasks and Startpoints</p>
   -->

1. In the `task.js` file, search for the events property of the view.

   The events property is a map with each entry in the format:   
   `"EventName Selector": "Function"`

   When you trigger a Javascript event named `EventName`on an HTML element specified by `Selector`, the `Function`is called. 

1. Find

    * "tap .taskContentArea" : "onTaskClick",  
      "tap .taskOpenArea" : "onTaskClick",  
      "tap .task-content" : "onTaskClick",  
      "tap .last_empty_div" : "onTaskClick",

   and replace with

    * "swipe .taskContentArea" : "onTaskClick",  
      "swipe .taskOpenArea" : "onTaskClick",  
      "swipe .task-content" : "onTaskClick",  
      "swipe .last_empty_div" : "onTaskClick",

1. Save and close the `task.js` file.
1. Build and run the AEM Forms app. Now you can open a using with left-swipe and right-swipe.

Similarly, you can make changes in other views for various combinations of gestures, HTML elements, and functions.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
