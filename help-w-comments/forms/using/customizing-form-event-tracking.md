---
title: Customizing form event tracking
seo-title: Customizing form event tracking
description: If a user spends more than 60 seconds on a field, a fieldvisit event is triggered and the details of the field are sent to Adobe SiteCatalyst.
seo-description: If a user spends more than 60 seconds on a field, a fieldvisit event is triggered and the details of the field are sent to Adobe SiteCatalyst.
uuid: aac99d9e-3b0b-49e3-810d-062092cf5566
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: 85cfde42-5e2b-406c-a508-659b4f0f670f
index: y
internal: n
snippet: y
---

# Customizing form event tracking{#customizing-form-event-tracking}

Out of the box, the following events are tracked in an analytics enabled Adaptive Form:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>Event</th> 
   <th>Available variables</th> 
  </tr> 
  <tr> 
   <td>render</td> 
   <td>formName, formTitle, formInstance, source</td> 
  </tr> 
  <tr> 
   <td>abandon</td> 
   <td>formName, formTitle, formInstance, panelName, panelTitle</td> 
  </tr> 
  <tr> 
   <td>save</td> 
   <td>formName, formTitle, formInstance, panelName, source</td> 
  </tr> 
  <tr> 
   <td>submit</td> 
   <td>formName, formTitle, formInstance, source</td> 
  </tr> 
  <tr> 
   <td>error</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle</td> 
  </tr> 
  <tr> 
   <td>help</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle</td> 
  </tr> 
  <tr> 
   <td>fieldVisit</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle<br /> </td> 
  </tr> 
  <tr> 
   <td>panelVisit</td> 
   <td>formName, formTitle, panelName, panelTitle</td> 
  </tr> 
 </tbody> 
</table>

## Customizing the field visit event timeout {#customizing-the-field-visit-event-timeout}

On the default AEM form setup, if a user spends more than 60 seconds on a field, a `fieldvisit` event is triggered and the details of the field are sent to Adobe Analytics. You can customize the Field time tracking baseline under AEM Forms Analytics Configuration at AEM Configuration console (/system/console/configMgr) to increase or decrease the timeout limit.

## Customizing the tracking events {#customizing-the-tracking-events}

You can modify the `trackEvent`function available in `/libs/afanalytics/js/custom.js` file to customize the event tracking. Whenever an event that is being tracked occurs in an adaptive form, the `trackEvent`function is called. The `trackEvent` function accepts two parameters: `eventName`and `variableValueMap`.

<!--
Comment Type: annotation
Last Modified By: vishgupt
Last Modified Date: 2018-03-21T08:06:46.698-0400
Changed the location of trackEvent function as requested in https://jira.corp.adobe.com/browse/CQDOC-12021
-->

You can evaluate value of *eventName *and *variableValueMap* arguments to change the tracking behavior of events. For example, you can choose to send the information to analytics server after a certain number of error events occur. You can also choose to perform any of the following customizations:

* You can set a threshold time before sending the event.  
* You can maintain a state to decide action, for example, *fieldVisit* pushes a dummy event based on the timestamp of the last event.
* You can use the `pushEvent` function to send the event to analytics server *.*

* You can choose to not push the event to analytics server at all.

### Sample {#sample}

In the following example, state for the *error* event of each *fieldName *attribute is maintained*. *The event is sent to the analytics server only if an error occurs again.

```
case 'error':
        if(errorOccurred[variableValueMap.fieldName] == true) {
            pushEvent(eventName, variableValueMap)
        }
        errorOccurred[variableValueMap.fieldName] = true;
        break;
```

## Customizing the panelvisit event {#customizing-the-panelvisit-event}

On the default AEM Forms setup, after every 60 seconds, it is checked if the window containing the adaptive form is active. If the window is active, a `panelVisit`event is triggered to Adobe Analytics. It helps in ascertaining that the document or the form is active and calculating time spent on the corresponding form or document.

>[!NOTE]
>
>The event name used to acertain activity and calculating time spent is "panelVisit". This event is different from the panel visit event listed in the table listed above.

You can modify the scheduleHeartBeatCheck function available in the `/libs/afanalytics/js/custom.js` file to change or stop this event sent to Adobe Analytics at a regular interval.

<!--
<related-links>
<a href="../../forms/using/view-understand-aem-forms-analytics-reports.md">Viewing and understanding AEM Forms analytics reports</a>
</related-links>
-->

