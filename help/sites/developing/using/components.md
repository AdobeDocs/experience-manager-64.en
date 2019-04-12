---
title: Components Overview
seo-title: Components
description: Components are modular units which realize specific functionality to present your content on your website
seo-description: Components are modular units which realize specific functionality to present your content on your website
uuid: fb39aeb8-8f43-4091-8083-ebfab89e6e63
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: components
content-type: reference
discoiquuid: 45efff93-2fe5-4313-83a0-0e23a540da93
---

# Components Overview{#components-overview}

This page provides an overview of Adobe Experience Manager (AEM) components such as those [used for page authoring](../../../sites/authoring/using/default-components-foundation.md).

## What Exactly is a Component? {#what-exactly-is-a-component}

Components:

* Are modular units which realize specific functionality to present your content on your website.
* Are re-usable.
* Are developed as self-contained units within one folder of the repository.
* Have no hidden configuration files.
* Can contain other components.
* Can run anywhere within any AEM system. They can also be limited to run under specific components.
* Have a standardized user interface.
* Have edit behavior that can be configured.
* Use dialogs that are built using sub-elements based on Granite UI components   
* Are developed using [HTL](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (recommended) or JSP.
* Can be developed to create customized components that extend the default functionality.

Because components are modular, you can:

1. Develop a new component on your local instance.
1. Deploy this to your test environment.
1. Deploy it to your live authoring environment, where they allow authors and/or administrators to add and configure content.
1. Deploy it to your live publish environment(s), where they are used to render content for visitors to your website. Certain components, for example for Communities, also accept input from your users.

Each AEM component:

* Is a resource type
* Is a collection of scripts that completely realize a specific function
* Can function in *isolation*, meaning either within AEM or a portal

## Out-of-the-Box Components Within AEM {#out-of-the-box-components-within-aem}

AEM comes with a variety of [out-of-the-box components](../../../sites/authoring/using/default-components.md) that provide comprehensive functionality including:

* Paragraph System ( `parsys`)
* Page ( `responsivegrid` - touch-enabled UI only)  

* Text  
* Image, with accompanying text
* Toolbar

The components provided and their usage within the [sample We.Retail websites](../../../sites/developing/using/we-retail.md) provided illustrate how to implement and use components. The components are provided with all source code and can be used as is or as starting points for modified or extended components.

### Core Components and Foundation Components {#core-components-and-foundation-components}

There are two sets of Adobe-provided AEM components available:

* [Core Components](https://helpx.adobe.com/experience-manager/core-components/user-guide.html)
* [Foundation Components](../../../sites/authoring/using/default-components-foundation.md)

**Core Components** were introduced with AEM 6.3 and offer flexible and feature-rich authoring functionality. The [We.Retail reference site](../../../sites/developing/using/we-retail.md) illustrates how the core components can be used and represent the current best-practices of component development.

**Foundation Components** have been available with AEM for many versions and are available out-of-the-box in a standard AEM installation. Although still supported, most have been deprecated, are no longer enhanced, and are based on legacy technologies.

>[!NOTE]
>
>[Core Components](https://helpx.adobe.com/experience-manager/core-components/user-guide.html) represent the current best practices for component design and development and serve as reference implementations.

### Viewing Available Components {#viewing-available-components}

For an overview of all of the available components in your AEM instance, use the [Components Console](../../../sites/authoring/using/default-components-console.md).

Alternatively, you can also use CRXDE Lite to get a list of all the components available in the repository.

1. In CRXDE Lite, select **Tools** from the toolbar, then **Query**, which opens the **Query** tab.  

1. In the **Query** tab, select `XPath` as **Type**.

1. In the **Query** input field, enter following string:  
   `//element(*, cq:Component)`

1. Click **Execute **and the components are listed.

## Further Reading {#further-reading}

The following pages provide more detailed information about developing these (and other) components:

* [AEM Components - The Basics](../../../sites/developing/using/components-basics.md)
* [Developing AEM Components](../../../sites/developing/using/developing-components.md)
* [Developing AEM Components - Code Samples](../../../sites/developing/using/developing-components-samples.md)
* [Configuring Multiple In-Place Editors](../../../sites/developing/using/multiple-inplace-editors.md)
* [Developer Mode](../../../sites/developing/using/developer-mode.md)
* [Testing Your UI](../../../sites/developing/using/hobbes.md)
* [Components for Content Fragments](../../../sites/developing/using/components-content-fragments.md)
* [Obtaining Page Information in JSON Format](../../../sites/developing/using/pageinfo.md)
* [Internationalizing Components](../../../sites/developing/using/i18n.md)
* [Core Components](https://helpx.adobe.com/experience-manager/core-components/user-guide.html)
* [Using Hide Conditions](../../../sites/developing/using/hide-conditions.md)
* Classic UI

    * [AEM Components (Classic UI)](../../../sites/developing/using/developing-components-classic.md)
    * [Using and Extending Widgets (Classic UI)](../../../sites/developing/using/widgets.md)
    * [Using xtypes (Classic UI)](../../../sites/developing/using/xtypes.md)
    * [Developing Forms (Classic UI)](../../../sites/developing/using/developing-forms.md)

