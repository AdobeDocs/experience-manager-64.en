---
title: JSON Exporter for Content Services
seo-title: JSON Exporter for Content Services
description: AEM Content Services are designed to generalize the description and delivery of content in/from AEM beyond a focus on web pages. They provide the delivery of content to channels that are not traditional AEM web pages, using standardized methods that can be consumed by any client. 
seo-description: AEM Content Services are designed to generalize the description and delivery of content in/from AEM beyond a focus on web pages. They provide the delivery of content to channels that are not traditional AEM web pages, using standardized methods that can be consumed by any client. 
uuid: 6b321b51-67da-492e-8eb9-d16d608c8d5e
contentOwner: User
content-type: reference
topic-tags: components
products: SG_EXPERIENCEMANAGER/6.4/SITES
discoiquuid: 9ef012ad-885c-4556-991a-9f47763fe8d8
index: y
internal: n
snippet: y
---

# JSON Exporter for Content Services{#json-exporter-for-content-services}

AEM Content Services are designed to generalize the description and delivery of content in/from AEM beyond a focus on web pages.

They provide the delivery of content to channels that are not traditional AEM web pages, using standardized methods that can be consumed by any client. These channels can include:

* Single Page Applications
* Native Mobile Applications 
* other channels and touch-points external to AEM

With content fragments that use structured content, you can provide content services by using the JSON exporter to deliver the contents of an(y) AEM page in JSON data model format. This can then be consumed by your own applications.

>[!NOTE]
>
>The functionality described here is available for all components since [release 1.1 of the Core Components](https://docs.adobe.com/content/docs/en/core-components/v1.html).

### JSON Exporter with Content Fragment Core Components {#json-exporter-with-content-fragment-core-components}

Using the AEM JSON exporter you can deliver the contents of an(y) AEM page in JSON data model format. This can then be consumed by your own applications.

Within AEM the delivery is achieved using the suffix

`.model.json`

1. For example, a URL such as:

   ```shell
   http://localhost:4502/content/we-retail/language-masters/en.model.json
   ```

1. Will deliver content such as:

   ![](assets/chlimage_1-199.png)

You can alternatively deliver the contents of a structured content fragment by targeting it specifically.

This is done using the entire path to the fragment (via the `jcr:content`); for example with a suffix such as.

`.../jcr:content/root/responsivegrid/contentfragment.model.json`

Your page can contain either a single content fragment or multiple components of various types. You can also use mechanisms such as list components to automatically search for relevant content.

* For example, a URL such as:

  ```shell
  http://localhost:4502/content/we-retail/language-masters/en/manchester-airport/jcr:content/root/responsivegrid/contentfragment.model.json
  ```

* Will deliver content such as:

  ![](assets/chlimage_1-200.png)

  >[!NOTE]
  >
  >You can [adapt your own components](../../../sites/developing/using/json-exporter-components.md) to access and use this data.

### Further Information {#further-information}

See also:

* Assets HTTP API

    * [Assets HTTP API](../../../assets/using/mac-api-assets.md)

* Sling Models:

    * [Sling Models - Associating a model class with a resource type since 130](https://sling.apache.org/documentation/bundles/models.html#associating-a-model-class-with-a-resource-type-since-130)

* AEM with JSON:

    * [Obtaining Page Information in JSON Format](../../../sites/developing/using/pageinfo.md)

## Related Documentation {#related-documentation}

For further details see:

* The [Content Fragments topic in the Assets user guide](https://helpx.adobe.com/experience-manager/6-4/assets/user-guide.html?topic=/experience-manager/6-4/assets/morehelp/content-fragments.ug.js)  

* [Content Fragment Models](../../../assets/using/content-fragments-models.md)
* [Authoring with Content Fragments](../../../sites/authoring/using/content-fragments.md)
* [Enabling JSON Export for a Component](../../../sites/developing/using/json-exporter-components.md)  

* [Core Components](https://helpx.adobe.com/experience-manager/core-components/user-guide.html) and the [Content Fragment component](https://helpx.adobe.com/experience-manager/core-components/using/content-fragment-component.html)

