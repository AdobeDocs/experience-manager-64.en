---
title: ContextHub
seo-title: ContextHub
description: ContextHub is a framework for storing, manipulating, and presenting context data
seo-description: ContextHub is a framework for storing, manipulating, and presenting context data
uuid: f53cb415-b944-44c6-b811-98fa68b43aa4
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 57f95eb1-96dc-421b-9971-60400d135be8
index: y
internal: n
snippet: y
---

# ContextHub{#contexthub}

ContextHub is a framework for storing, manipulating, and presenting context data. The client-side Javascript API enables you to access the data for personalizing content.

>[!NOTE]
>
>The [We.Retail reference implementation](../../../sites/developing/using/we-retail.md) implements ContextHub and can serve as a reference as you integrate ContextHub into your own project.

>[!CAUTION]
>
>The path containing the sample ContextHub configuration that is used by the [We.Retail reference implementation](../../../sites/developing/using/we-retail.md) ( `/libs/settings/cloudsettings/legacy`) should only be used as a reference for creating your own configuration.
>
>It should not be used in a project as your own ContextHub configuration.

### Persistence {#persistence}

ContextHub stores persist context data on the client. The ContextHub Javascript API enables you to access stores to create, update, and delete data as necessary. As such, ContextHub represents a data layer on your pages.

Each ContextHub store is an instance of a predefined store type:

* ContextHub provides several [sample store types](../../../sites/developing/using/ch-samplestores.md).
* Use AEM consoles to [create stores](../../../sites/administering/using/contexthub-config.md#main-pars-title-1).
* Developers can [create custom store types](../../../sites/developing/using/ch-extend.md#main-pars-title). 
* Developers can [access store data](../../../sites/developing/using/ch-adding.md#main-pars-title-1408164230) via Javascript.

### Segmentation {#segmentation}

ContextHub includes a segmentation engine that manages segments and determines which segments are resolved for the current context. Several segments are defined. You can use the Javascript API to [determine resolved segments](../../../sites/developing/using/ch-adding.md#main-pars-title-949252178).

### Presentation {#presentation}

The [ContextHub toolbar](../../../sites/authoring/using/ch-previewing.md) enables marketers and authors to see and manipulate store data for simulating the user experience when authoring pages. The toolbar consists of groups of UI modules that provide access to ContextHub stores.

Each ContextHub UI module is an instance of a predefined module type:

* ContextHub provides several [sample module types](../../../sites/developing/using/ch-samplemodules.md).
* Use AEM consoles to [add UI modules](../../../sites/administering/using/contexthub-config.md#main-pars-title-2108758587), and to [group them in UI modes](../../../sites/administering/using/contexthub-config.md#main-pars-title-1407953594).

* Developers can [create custom module types](../../../sites/developing/using/ch-extend.md#main-pars-title-2121301991).

Developers need to [add the ContextHub component to the page](../../../sites/developing/using/ch-adding.md).
