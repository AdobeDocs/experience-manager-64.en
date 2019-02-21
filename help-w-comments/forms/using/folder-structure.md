---
title: Understanding the folder structure
seo-title: Understanding the folder structure
description: How to understand the folder structure of AEM Forms workspace source code to customize.
seo-description: How to understand the folder structure of AEM Forms workspace source code to customize.
uuid: 26e882b9-4a16-4258-a1fa-8f999312ea41
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: e4b9a8b3-0e11-48a3-b1ed-766c5cc6bb17
index: y
internal: n
snippet: y
---

# Understanding the folder structure{#understanding-the-folder-structure}

AEM Forms workspace components are designed on MVC architecture using Backbone. Each component has a file for:

* Model, that contains business logic.
* Template, that is an HTML file containing interface controls.
* View, that acts as a Controller class to Template.

The assets for all the components are placed in the folder structure described below. To access the assets, log in to CRXDE Lite and browse to `/libs/ws/js/runtime/`.

**models** Contains backbone models.

**views** Contains backbone views.

**templates** Contains only the HTML templates for the components.

**routes** Contains universal routes. Templates folder inside routes contains the HTML code and the references to the components.

**services** Contains service interface to call Adobe Experience Manager server APIs on REST endpoint.

**util** Contains generic utilities usable by multiple components.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

<!--
<related-links>
<a href="../../forms/using/backbone-interaction.md">Backbone interaction</a>
<a href="../../forms/using/description-reusable-components.md">Description of the reusable components</a>
<a href="../../forms/using/folder-structure.md">Understanding the folder structure</a>
<a href="../../forms/using/document-details-renderer.md">Document details for renderer</a>
<a href="../../forms/using/integrating-html-ws-components-web.md">Integrating AEM Forms workspace components in web applications</a>
<a href="../../forms/using/new-render-submit-service.md">New Render and Submit service</a>
</related-links>
-->

