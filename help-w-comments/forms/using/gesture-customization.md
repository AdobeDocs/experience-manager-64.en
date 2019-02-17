---
title: Gesture customization
seo-title: Gesture customization
description: Customize the gestures on your AEM Forms app
seo-description: Customize the gestures on your AEM Forms app
uuid: 4ee2e237-e543-40fc-95b9-4cff8c5f3a13
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 21d558d7-4b26-4fb2-8b8c-7166c7098bee
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
