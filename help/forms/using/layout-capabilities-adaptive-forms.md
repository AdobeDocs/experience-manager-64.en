---
title: Layout capabilities of adaptive forms
seo-title: Layout capabilities of adaptive forms
description: null
seo-description: Layout and appearances of adaptive forms on various devices are governed by the layout settings. Understand the various layouts and how to apply them.
uuid: 61d9f7bf-5988-4fe5-84f8-f95a70e2a137
acrolinxdate: 2016-05-31T06 41 15.796-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/layout_capabilities_adaptive_forms_admin_5e12de0b318c6865_2037_report.xml
acrolinxsentences: 61
acrolinxwords: 1333
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 81fc2e87-5366-4afb-9fe4-3caecc8cf553
isreadyforlocalization: false
lastpublishqadate: 2015-06-12T04 26 45.011-0400
index: y
internal: n
snippet: y
---

# Layout capabilities of adaptive forms{#layout-capabilities-of-adaptive-forms}

<!--
Comment Type: remark
Last Modified By: (asgupta)
Last Modified Date: 2017-11-30T06:07:53.968-0500
<p>Create links to these articles, when they are available:</p>
<ul>
<li>Creating custom toolbar layout: /content/help/en/aem-forms/6/creating-custom-toolbar-layout.html</li>
<li>Creating custom layout components for adaptive forms: /content/help/en/aem-forms/6/custom-layout-components-forms.html</li>
<li>Creating custom adaptive forms templates: /content/help/en/aem-forms/6/custom-adaptive-forms-templates.html</li>
</ul>
-->

Adobe Experience Manager (AEM) lets you create easy-to-use adaptive forms that offer dynamic experiences to end users. The form layout controls how items or components are displayed in an adaptive form.

## Prerequisite knowledge {#prerequisite-knowledge}

Before learning about the different layout capabilities of adaptive forms, read the following articles to know more about adaptive forms.

[Introduction to AEM Forms](../../forms/using/introduction-aem-forms.md)

[Introduction to authoring forms](../../forms/using/introduction-forms-authoring.md)

## Types of layouts {#types-of-layouts}

An adaptive form provides you with the following types of layouts:

**Panel Layout** Controls how items or components inside a panel are displayed on a device.

**Mobile Layout** Controls the navigation of a form on a mobile device. If the device width is 768 pixels or more, the layout is considered a mobile layout and optimized for a mobile device.

**Toolbar Layout** Controls the placement of Action buttons in the toolbar or panel toolbar in a form.

All these panel layouts are defined in the following location:

`/libs/fd/af/layouts`.

>[!NOTE]
>
>To change the layout of an adaptive form, use the Authoring Mode in AEM.

![Location of layouts in CRX repository](assets/layouts_location_in_crx.png) 

## Panel layout {#panel-layout}

A form author can associate a layout with each panel of an adaptive form, including the root panel.

The Panel layouts are available at `/libs/fd/af/layouts/panel` location.

![List of panel layouts for root panel of an adaptive form](assets/layouts.png) 

### Responsive - everything on one page without navigation <br> {#responsive-everything-on-one-page-without-navigation-br}

Use this panel layout to create a responsive layout that adjusts to the screen size of your device without any need for specialized navigation.

Using this layout, you can place multiple **[!UICONTROL Panel adaptive form]**components one after another inside the panel. 

![A form using responsive layout as seen on a small screen](assets/responsive_layout_seen_on_small_screen.png)  ![A form using responsive layout as seen on a large screen](assets/responsive_layout_seen_on_large_screen.png) 

### Wizard - a multi-step form showing one step at a time {#wizard-a-multi-step-form-showing-one-step-at-a-time}

Use this panel layout to provide guided navigation inside a form. For example, use this layout when you want to capture mandatory information in a form while guiding users step by step.

Use the `Panel adaptive form` component to provide step-by-step navigation inside a panel. When you use this layout, a user moves to the next step only after the current step is complete

```
window.guideBridge.validate([], this.panel.navigationContext.currentItem.somExpression)
```

![Step completion expression in Wizard layout for a multi-step form](assets/layout-sidebar.png)  ![A form using wizard layout](assets/wizard-layout.png) 

### Layout for accordion design {#layout-for-accordion-design}

Using this layout, you can place the `Panel adaptive form` component in a panel with accordion style navigation. Using this layout, you can also create repeatable panels. Repeatable panels enable you to dynamically add or remove panels as needed. You can define the minimum and the maximum number of times a panel repeats. Also, the title of the panel can be determined dynamically, based on the information provided in the panel items.

Summary expression can be used to show the values provided by the end user in the title of the minimized panel.

![Repeatable panels using Accordion layout in adaptive forms](assets/repeatable_panels_using_accordion_layout.png) 

### Tabbed layout - tabs appear on the left {#tabbed-layout-tabs-appear-on-the-left}

Using this layout, you can place the `Panel adaptive form` component in a panel with tab navigation. The tabs are placed on the left of the panel content.

![In the Tabbed layout, the tabs appear on the left](assets/tabbed_layout_left.png) 

### Tabbed layout - tabs appear on the top {#tabbed-layout-tabs-appear-on-the-top}

Using this layout, you can place the `Panel adaptive form` Component in a panel with tab navigation. The tabs are placed on top of the panel content.

![Tabbed layout in adaptive forms with tabs on the top](assets/tabbed_layout_top.png) 

## Mobile layouts {#mobile-layouts}

Mobile layouts allow for user-friendly navigation on the mobile devices with relatively smaller screens. Mobile layouts use either tabbed or wizard styles for form navigation. Applying a Mobile Layout provides a single layout for the entire form.

This layout controls navigation using a navigation bar and a navigation menu. The navigation bar shows **&lt;** and **&gt;** icon to indicate **next** and **previous** navigation steps in the form.

The Mobile Layouts are available at `/libs/fd/af/layouts/mobile/` location. The following mobile layouts are available in adaptive forms, by default.

![List of Mobile Layouts in adaptive forms](assets/mobile-navigation.png)

When using a mobile layout, the form menu, to access various form panels, is available by tapping  ![](assets/aem6forms_form_menu.png){width="21"}

icon.

### Layout with panel titles in the form header {#layout-with-panel-titles-in-the-form-header}

This layout, as the name suggests, shows panel titles along with the navigation menu and navigation bar. This layout also provides Next and Previous icons for navigation.

![Mobile layouts with panel titles in the form headers](assets/mobile_layout_with.png) 

### Layout without panel titles in the form header {#layout-without-panel-titles-in-the-form-header}

This layout, as the name suggests, shows only the navigation menu and navigation bar without panel titles. This layout also provides Next and Previous icons for navigation.

![Mobile layouts without panel titles in the form headers](assets/mobile_layout_without.png) 

## Toolbar layouts {#toolbar-layouts}

A Toolbar Layout controls positioning and display of any action buttons that you add to your adaptive forms. The layout can be added at a form level or at a panel level.

![A list of Toolbar Layouts in adaptive forms to control layout of buttons](assets/toolbar-layouts.png)

Toolbar layouts are available at `/libs/fd/af/layouts/toolbar` location. adaptive forms provide the following Toolbar Layouts, by default.

### Default layout for toolbar {#default-layout-for-toolbar}

This layout is selected as the default layout when you add any action buttons in an adaptive form. Selecting this layout displays the same layout for both, desktop and mobile devices.

Also, you can add multiple toolbars containing action buttons configured with this layout. An action button is associated with a form control. You can configure the toolbars to be before or after a panel.

![Default view for toolbar](assets/toolbar_layout_default.png) 

### Mobile fixed layout for toolbar {#mobile-fixed-layout-for-toolbar}

Select this layout to provide alternate layouts for desktop and mobile devices.

For the desktop layout, you can add Action buttons using some specific labels. Only one toolbar can be configured with this layout. If more than one toolbar are configured with this layout, there is an overlap for mobile devices and only one toolbar is visible. For example, you can have a toolbar at the bottom or the top of the form, or, after or before panels in the form.

For the mobile layout, you can add action buttons using icons.

![Mobile fixed layout for toolbar](assets/toolbar_layout_mobile_fixed.png) 
>[!MORE_LIKE_THIS]
>
>* [Introduction to adaptive forms authoring](../../forms/using/introduction-forms-authoring.md)
>* [Creating an adaptive form](../../forms/using/creating-adaptive-form.md)
>* [Creating forms with repeatable sections](../../forms/using/creating-forms-repeatable-sections.md)
>* [Creating a custom adaptive form template](../../forms/using/custom-adaptive-forms-templates.md)
