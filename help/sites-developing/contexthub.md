---
title: ContextHub
seo-title: ContextHub
description: ContextHub is a framework for storing, manipulating, and presenting context data
seo-description: ContextHub is a framework for storing, manipulating, and presenting context data
uuid: 14e6ff4f-ffbe-454a-b2ec-a35333526e27
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: acf5c17a-95b7-43ba-9734-241e20f4f374
exl-id: 0a6b815a-5055-4c44-96d1-ff238b4285f3
---
# ContextHub{#contexthub}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

ContextHub is a framework for storing, manipulating, and presenting context data. The client-side Javascript API enables you to access the data for personalizing content.

>[!NOTE]
>
>The [We.Retail reference implementation](/help/sites-developing/we-retail.md) implements ContextHub and can serve as a reference as you integrate ContextHub into your own project.

>[!CAUTION]
>
>The path containing the sample ContextHub configuration that is used by the [We.Retail reference implementation](/help/sites-developing/we-retail.md) ( `/libs/settings/cloudsettings/legacy`) should only be used as a reference for creating your own configuration.
>
>It should not be used in a project as your own ContextHub configuration.

## Persistence {#persistence}

ContextHub stores persist context data on the client. The ContextHub Javascript API enables you to access stores to create, update, and delete data as necessary. As such, ContextHub represents a data layer on your pages.

Each ContextHub store is an instance of a predefined store type:

* ContextHub provides several [sample store types](/help/sites-developing/ch-samplestores.md).
* Use AEM consoles to [create stores](/help/sites-administering/contexthub-config.md#creating-a-contexthub-store).
* Developers can [create custom store types](/help/sites-developing/ch-extend.md#creating-custom-store-candidates). 
* Developers can [access store data](/help/sites-developing/ch-adding.md#interacting-with-contexthub-stores) via Javascript.

## Segmentation {#segmentation}

ContextHub includes a segmentation engine that manages segments and determines which segments are resolved for the current context. Several segments are defined. You can use the Javascript API to [determine resolved segments](/help/sites-developing/ch-adding.md#determining-resolved-contexthub-segments).

## Presentation {#presentation}

The [ContextHub toolbar](/help/sites-authoring/ch-previewing.md) enables marketers and authors to see and manipulate store data for simulating the user experience when authoring pages. The toolbar consists of groups of UI modules that provide access to ContextHub stores.

Each ContextHub UI module is an instance of a predefined module type:

* ContextHub provides several [sample module types](/help/sites-developing/ch-samplemodules.md).
* Use AEM consoles to [add UI modules](/help/sites-administering/contexthub-config.md#adding-a-ui-module), and to [group them in UI modes](/help/sites-administering/contexthub-config.md#adding-a-ui-mode).

* Developers can [create custom module types](/help/sites-developing/ch-extend.md#creating-contexthub-ui-module-types).

Developers need to [add the ContextHub component to the page](/help/sites-developing/ch-adding.md).
