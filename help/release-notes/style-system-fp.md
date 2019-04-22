---
title: Style System
seo-title: Style System
description: null
seo-description: null
page-status-flag: de-activated
uuid: a4a54042-e80f-46b8-abbb-d83b399e814b
contentOwner: bohnert
discoiquuid: a6032031-180e-4233-b96d-2d0a74b9b591
---

# Style System {#style-system}

The Style System allows a template author to define style classes in the component policy of components so that a content author can select these when editing the component on a page. These styles can be visual variations of the component, allowing better component reuse.

This eliminates the need to develop a custom component for each style or customize the component dialog to enable such style functionality, enabling more flexible components that can be more quickly easily adapted to the needs of the content authors without any need for AEM back-end development.

## Use Case {#use-case}

Template authors need the ability to not only configure how the components function for the content authors, but they also need the ability to configure the possible visual variations of the components.

Likewise, content authors need not only the ability to structure and arrange their content, but also the ability to select how it is visually presented.

The style system provides a unified solution to both the template author's and content author's requirements:

* Template authors can define style classes in the component policy of components.
* Content authors can then select these classes from a drop-down when editing the component on a page in order to apply the corresponding styles.

The style class is then inserted on the decoration wrapper element of the component, so that the component developer doesn't need to be concerned about handling the styles beyond providing the CSS of the different styles.

## Overview {#overview}

Using the style system generally takes the following form.

1. The web designer creates different visual variations for a component.  

1. The HTML developer is provided with the HTML output of the components and the desired visual variations to implement.  

1. The HTML developer defines the CSS classes that correspond to the visual variation, which are to be inserted on the element wrapping the components.  

1. The HTML developer implements the corresponding CSS code (and optionally JS code) for each of the visual variation to look as defined.  

1. The AEM developer places the provided CSS (and optional JS) in a [Client Library](/help/sites/developing/using/clientlibs.md) and deploys it.  

1. The AEM developer or template author configures the page templates and edits the policy of each styled component with the defined CSS classes, defining user-friendly names for each style, and defining which styles can be combined.  

1. The AEM page author can then choose the designed styles in the page editor through the style menu of the component's toolbar.

Note that only the last three steps are actually carried out in AEM. This means all development of the necessary CSS and Javascript can be done without AEM.

Actually implementing the styles only requires deployment on AEM and selection within the components of the desired templates.

The following diagram illustrates the architecture of the style system.

![](/help/sites/authoring/using/assets/aem-style-system.png) 

## Use {#use}

[Feature pack 18678](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/featurepack/cq-6.3.0-featurepack-18678) for AEM 6.3 is required to enable the style system feature and can be downloaded from Package Share.

To demonstrate the feature, styles need to be created for a component. Using [We.Retail](/help/sites/developing/using/we-retail.md)'s implementation of core component's [list component](https://helpx.adobe.com/experience-manager/core-components-v2/using/core-components-v1-authoring-list.html) as a basis, you can install the attached package containing styles in order to explore the feature's functionality.

Style system demo package

[Get File](/help/sites/authoring/using/assets/package_-_style_systemdemo.zip)
The following sections [As a Content Author](/help/release-notes/style-system-fp.md#as-a-content-author) and [As a Template Author](#as-a-template-author) describe how to test the functionality of the style system using the style system demo package on top of We.Retail.

If you wish to use the style system for your own components follow these steps:

1. Install the CSS as client libraries as discussed in the section [Overview](#overview).
1. Configure the CSS classes that you wish to make available to your content authors as described in the section [As a Template Author](#as-a-template-author).
1. Content authors can then use the styles as described in the section [As a Content Author](#as-a-content-author).

### As a Content Author {#as-a-content-author}

1. After installing the style system demo package, navigate to We.Retail's English language master home page at `http://localhost:4502/sites.html/content/we-retail/language-masters/en` and edit the page.
1. Select the **List** component at the bottom or the top of the parsys. Do not confuse it with the **Articles List** component.

   ![](/help/sites/authoring/using/assets/screen_shot_2017-11-15at162032.png)

1. Tap or click the **Styles** button on the toolbar of the **List **component to open the style menu and change the appearance of the component.

   ![](/help/sites/authoring/using/assets/screen_shot_2017-11-15at162358.png)

   >[!NOTE]
   >
   >In this example, the **Layout** styles (**Block** and **Grid**) are mutually exclusive, while the **Display** options (**Image** or **Date**) can be combined. This can be [configured in the template as the template author](/help/release-notes/style-system-fp.md#as-a-template-author).

### As a Template Author {#as-a-template-author}

1. While editing We.Retail's English language master home page at `http://localhost:4502/sites.html/content/we-retail/language-masters/en`, edit the template of the page via **Page Information -&gt; Edit Template**.

   ![](/help/sites/authoring/using/assets/screen_shot_2017-11-15at162922.png)

1. Edit the policy of the **List** component by tapping or clicking the **Policy** button of the component. Do not confuse this with the **Article List** component.

   ![](/help/sites/authoring/using/assets/screen_shot_2017-11-15at163133.png)

1. On the Styles tab of the properties, you can see how the styles have been configured.

   ![](assets/screen_shot_2017-11-15at163546.png)

    * **Group Name:** Styles can be grouped together within the style menu that the content author will see when configuring the style of the component.
    * **Multiple:** Allows for multiple styles within that group to be selected at one time.
    * **Style Name:** The description of the style that will display to the content author when configuring the style of the component.
    * **CSS Classes:** The atual name of the CSS class associated with the style.

   Use the drag handles to arrange the order of the groups and the styles within the groups. Use the add or delete icons to add or remove groups or styles within the groups.

>[!CAUTION]
>
>The CSS classes (as well as any necessary Javascript) configured as style properties of a components policy must be deployed as [Client Libraries](/help/sites/developing/using/clientlibs.md) in order to work.

## Setup {#setup}

>[!NOTE]
>
>[Version 2 of the core components](https://helpx.adobe.com/experience-manager/core-components-v2/user-guide.html) is fully enabled to take advantage of the style system and requires no additional configuration.
>
>Follow the next steps to enable the style system for your own custom components.

In order for a component to work with AEM's style system and show the style tab in its design dialog, the component developer must include that tab from the product with the following settings on the component:

* `path = "/mnt/overlay/cq/gui/components/authoring/dialog/style/tab_design/styletab"`
* `sling:resourceType = "granite/ui/components/coral/foundation/include"`

With the component configured, the styles configured by the page authors will be automatically insterted by AEM on the decoration element that AEM automatically wraps around every editable component. The component itself need not do anything else to make this happen.

### Styles with Element Names {#styles-with-element-names}

A developer can also configure a list of allowed element names for styles on the component with the `cq:styleElements` string array property. Then in the Styles tab of the policy within the design dialog, the template author can also choose an element name to be set for each style. This will set the element name of the wrapper element.

This property is set on the `cq:Component` node. For example:

* `/apps/weretail/components/content/list@cq:styleElements=[div,section,span]`

>[!CAUTION]
>
>Avoid defining element names for styles that can be combined. When multiple element names are defined, the order of priority is:
>
>1. HTL takes precedence over everything: `data-sly-resource="${'path/to/resource' @ decorationTagName='span'}`
>1. Then among multiple active styles, the first style in the list of styles configured in the component's policy is taken.
>1. Finally, the component's `cq:htmlTag`/ `cq:tagName` will be considered as a fallback value.
>

This ability to define style names is useful for very generic components, like the Layout Container, or the Content Fragment component, in order to provide them with additional meaning.

For instance it allows a Layout Container to be given semantics like `<main>`, `<aside>`, `<nav>`, etc.
