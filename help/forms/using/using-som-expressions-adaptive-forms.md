---
title: Using SOM expressions in adaptive forms
seo-title: Using SOM expressions in adaptive forms
description: null
seo-description: Learn how to extract SOM expressions of a panel of an adaptive form.
uuid: 2d6b9aed-2e49-44a9-a310-54bf20b1ea1a
acrolinxdate: 2016-05-31T06 44 01.484-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/using_som_expressions_adaptive_forms_admin_5e12de0b318c6865_2072_report.xml
acrolinxsentences: 25
acrolinxwords: 378
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: f9910001-b424-40ea-a7d1-e5e144f60625
isreadyforlocalization: false
lastpublishqadate: 2015-06-17T05 43 23.192-0400
index: y
internal: n
snippet: y
---

# Using SOM expressions in adaptive forms{#using-som-expressions-in-adaptive-forms}

Adaptive forms are modeled as AEM Page which is represented as JCR content structure in AEM repository. The key element of the content structure is guideContainer node. Below guideContainer, there is rootPanel which may contain nested panel and fields.

You can use a scripting object model (SOM) to reference values, properties, and methods within a particular document object model (DOM). A DOM organizes the memory objects and properties in a tree hierarchy. A SOM expression references Fields/Draw elements and panels.

The following image depicts a node structure that an adaptive form translates to when you add components to a form. For example, you can add a panel to the root panel and a radio button in the panel that is transformed to DOM at runtime. The SOM Expression for the radio-button field in adaptive form is specified as `guide[0].guide1[0].guideRootPanel[0].panel1[0].radiobutton[0]`.

![DOM tree](assets/Hierarchy.png)

A SOM expression for any element in an adaptive form is prefixed by `guide[0].guide1[0]`. The position of a component in the node structure hierarchy is used to derive its SOM expression.

![DOM tree with two radio buttons](assets/Hierarchy_Radio_Button.png)

The SOM expression changes when you change the position of the radio-buttons in the adaptive form. In the authoring mode, you can view the SOM expression of a field or element within AEM Forms using the View SOM Expression option. The option appears on the panel and when you right-click the field or element. 

![Extracting SOM Expressions in an Adaptive form](assets/som-expressions.png)

Within panels, you can access the feature from the panel toolbar. The feature facilitates scripting by adaptive form authors.

![Extracting SOM Expressions using panel toolbar](assets/som-expression.png)

Some APIs listed in [GuideBridge]( http://helpx.adobe.com/aem-forms/6/javascript-api/GuideBridge) use the SOM expression of an element. For example, to bring focus to a particular field in an adaptive form, pass the corresponding SOM expression to the `getFocus`API in `guideBridge`.

>[!MORE_LIKE_THIS]
>
>* [Introduction to authoring adaptive forms](../../forms/using/introduction-forms-authoring.md)
