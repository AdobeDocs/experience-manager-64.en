---
title: Create custom appearances in HTML5 forms
seo-title: Create custom appearances in HTML5 forms
description: null
seo-description: You can plug in custom widgets to a Mobile Forms. You can extend existing jQuery Widgets or develop your own custom widgets.
uuid: b80dba9a-1434-4f35-aa34-c7983c2cd622
acrolinxdate: 2016-05-31T06 46 49.045-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/custom_widgets_admin_5e12de0b318c6865_2095_report.xml
acrolinxsentences: 42
acrolinxwords: 660
contentOwner: robhagat
cq%3alastmodified: 2013-03-15T12 30 51.923-0400
cq%3alastmodifiedby: deepakk
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: b697dff3-0c95-427b-8e06-6aaf8896cad5
firstpublishqadate: 2013-02-20T08 58 39.917-0500
isreadyforlocalization: false
lastpublishqadate: 2015-11-03T03 22 30.810-0500
publishqadate: 2015-11-03T03 22 30.810-0500
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/html5-forms/custom-widgets.html
index: y
internal: n
snippet: y
---

# Create custom appearances in HTML5 forms{#create-custom-appearances-in-html-forms}

You can plug in custom widgets to a Mobile Forms. You can extend existing jQuery Widgets or develop your own custom widgets using appearances framework. XFA engine uses various widgets, see [Appearance framework for adaptive and HTML5 forms](../../forms/using/introduction-widgets.md) for detailed information.

![An example of default and custom widget](assets/custom-widgets.jpg) 

## Integrating custom widgets with HTML5 forms {#integrating-custom-widgets-with-html-forms}

### Create a profile&nbsp; {#create-a-profile-nbsp}

You can create a profile or choose an existing profile to add a custom widget. For more information on creating profiles, see [Creating custom Profile](../../forms/using/custom-profile.md).

### Create a widget {#create-a-widget}

HTML5 forms provide an implementation of the widget framework that can be extended to create new widgets. The implementation is a jQuery widget *abstractWidget* that can be extended to write a new widget. The new widget can be made functional only by extending/overriding the below mentioned functions.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Function/Class</td> 
   <td>Description</td> 
  </tr> 
  <tr> 
   <td>render</td> 
   <td>The render function returns the jQuery object for the default HTML element of the widget. The default HTML element should be of focusable type. For example, &lt;a&gt;, &lt;input&gt;, and &lt;li&gt;. The returned element is used as $userControl. If the $userControl specifies the above constraint, then functions of the AbstractWidget class work as expected, otherwise some of the common APIs (focus, click) require changes. </td> 
  </tr> 
  <tr> 
   <td>getEventMap</td> 
   <td>Returns a map to convert HTML events to XFA events. <br /> {<br /> blur: XFA_EXIT_EVENT,<br /> }<br /> This example shows that the blur is an HTML event and XFA_EXIT_EVENT is corresponding XFA event. </td> 
  </tr> 
  <tr> 
   <td>getOptionsMap</td> 
   <td>Returns a map which provides detail what action to perform on change of an option. The keys are the options that are provided to the widget and values are the functions that are called whenever a change in that option is detected. The widget provides handlers for all the common options (except value and displayValue)</td> 
  </tr> 
  <tr> 
   <td>getCommitValue</td> 
   <td>The Widget framework loads the function whenever the value of the widget is saved in the XFAModel (for example on exit event of a textField). The implementation should return the value that is saved in the widget. The handler is provided with the new value for the option.</td> 
  </tr> 
  <tr> 
   <td>showValue</td> 
   <td>By default, in XFA on enter event, the rawValue of the field is displayed. This function is called to show the rawValue to the user. </td> 
  </tr> 
  <tr> 
   <td>showDisplayValue</td> 
   <td>By default, in XFA on exit event, the formattedValue of the field is displayed. This function is called to show the formattedValue to the user. </td> 
  </tr> 
 </tbody> 
</table>

To create your own widget, in the profile created above, include references of the JavaScript file which contains overridden functions and newly added functions. For example, the *sliderNumericFieldWidget* is a widget for numeric Fields. To use the widget in your profile in the header section, include the following line:

```
window.formBridge.registerConfig("widgetConfig" , widgetConfigObject);
```

### Register custom widget with XFA Scripting Engine&nbsp; {#register-custom-widget-with-xfa-scripting-engine-nbsp}

When the custom widget code is ready, register the widget with the scripting engine by using `registerConfig`API for [Form Bridge](../../forms/using/form-bridge-apis.md). It takes widgetConfigObject as input.

```

window.formBridge.registerConfig("widgetConfig",
        {
        ".<field-identifier>":"<name-of-the-widget>"
        }
    );
```

#### widgetConfigObject {#widgetconfigobject}

The widget configuration is provided as a JSON object (a collection of key value pairs) where the key identifies the fields and value represents the widget to use with those fields. A sample configuration looks like:

*{*

*“identifier1” : “customwidgetname”,  
“identifier2” : “customwidgetname2”,  
..  
}*

where “identifier” is a jQuery CSS selector that represents a particular field, a set of fields of a particular type, or all fields. The following lists the value of the identifier in different cases:

| Type of identifier |Identifier  |Description |
|---|---|---|
| Particular field with name fieldname |Identifier:"div.fieldname" |All fields with the name ‘fieldname’ are rendered using the widget. |
| All fields of type ‘type’(where type is NumericField, DateField, and so on.): |Identifier: "div.type" |For Timefield and DateTimeField, the type is textfield as these fields are not supported. |
| All fields |Identifier: "div.field" |  |

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

>[!MORE_LIKE_THIS]
>
>* [Appearance framework for adaptive and HTML5 forms](../../forms/using/introduction-widgets.md)
>* [Creating custom profiles for HTML5 forms](../../forms/using/custom-profile.md)
>* [Custom Widgets for HTML5 forms](../../forms/using/custom-widgets.md)
>* [Form Bridge for HTML5 forms](../../forms/using/form-bridge-apis.md)
>* [Integrating form bridge with forms portal](../../forms/using/integrate-form-bridge-forms-portal.md)
>* [Changing default styles of HTML5 forms](../../forms/using/css-styles.md)
