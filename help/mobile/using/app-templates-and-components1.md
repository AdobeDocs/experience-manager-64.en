---
title: App Templates and Components
seo-title: App Templates and Components
description: Follow this page to learn about App Templates and Components. It provides detailed information on the structure of templates.
seo-description: Follow this page to learn about App Templates and Components. It provides detailed information on the structure of templates.
uuid: a33ec478-0dfb-459d-89ed-bc3f97794bda
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-on-demand-services-app
discoiquuid: 83daf978-5431-4060-899f-d9fe3e5b205d
index: y
internal: n
snippet: y
---

# App Templates and Components{#app-templates-and-components}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](../../sites/developing/using/spa-overview.md).

A Template is used to create a Page and defines which components can be used within the selected scope. A template is a hierarchy of nodes that has the same structure as the page to be created, but without any actual content.

Each Template will present you with a selection of components available for use.

* Templates are built up of [Components](../../sites/developing/using/components.md);
* Components use, and allow access to, Widgets and these are used to render the Content.

>[!NOTE]
>
>To learn how to develop your AEM application using CRXDE Lite, see [Developing with CRXDE Lite](../../sites/developing/using/developing-with-crxde-lite.md).

A template is the basis of a page.

To create a page, the template must be copied (node-tree **/apps/&lt;myapp&gt;/templates/&lt;mytemplate&gt;**) to the corresponding position in the site-tree: this is what happens if a page is created using the **Websites** tab.

This copy action also gives the page its initial content (usually Top-Level Content only) and the property sling:resourceType, the path to the page component that is used to render the page (everything in the child node jcr:content).

## Structure of a Template {#structure-of-a-template}

There are two aspects to be considered:

* the structure of the template itself
* the structure of the content produced when a template is used

A Template is created under a node of type **cq:Template**.

Various properties can be set, in particular:

* **jcr:title** - title for the template; appears in the dialog when creating a page.
* **jcr:description** - description for the template; appears in the dialog when creating a page.

This node contains *a jcr:content (cq:PageContent) *node which be used as the basis for the content node of resulting pages; this references, using *sling:resourceType*, the component to be used for rendering the actual content of a new page.

>[!NOTE]
>
>To learn the basics for templates and components in AEM, see the resources below:
>
>* [Templates](../../sites/developing/using/templates.md)
>* [Components](../../sites/developing/using/components.md)
>

Once you have the basic understanding of Templates and Components, See the following resources:

* [Creating and Adding Templates and Components](../../mobile/using/mobile-ondemand-app-templates.md)
* [Using Content Properties to Export Content](../../mobile/using/on-demand-content-properties-exporting.md)
* [Best Practices](../../mobile/using/best-practices-aem-mobile.md)
* [Developing AEM Mobile Content Services](../../mobile/using/developing-content-services.md)

### Additional Resources {#additional-resources}

To learn about additional topics on mobile apps, See the links below:

* [Mobile with Content Sync](../../mobile/using/mobile-ondemand-contentsync.md)
* [Testing Mobile Apps](../../mobile/using/develop-mobile-apps-testing.md)

