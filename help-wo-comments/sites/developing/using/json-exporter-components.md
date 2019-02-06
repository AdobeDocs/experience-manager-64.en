---
title: Enabling JSON Export for a Component
seo-title: Enabling JSON Export for a Component
description: Components can be adapted to generate JSON export of their content based on a modeler framework.
seo-description: Components can be adapted to generate JSON export of their content based on a modeler framework.
uuid: ca5b5bdd-9e97-4b56-a11e-3d1ec2e2ff7a
contentOwner: User
content-type: reference
topic-tags: components
products: SG_EXPERIENCEMANAGER/6.4/SITES
discoiquuid: bd6ed195-1d65-4229-9d6d-9fe26552af37
index: y
internal: n
snippet: y
---

# Enabling JSON Export for a Component{#enabling-json-export-for-a-component}

Components can be adapted to generate JSON export of their content based on a modeler framework.

### Overview {#overview}

The JSON Export is based on [Sling Models](https://sling.apache.org/documentation/bundles/models.html), and on the [Sling Model Exporter](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) framework (which itself relies on [Jackson annotations](https://github.com/FasterXML/jackson-annotations/wiki/Jackson-Annotations)).

This means that the component must have a Sling Model if it needs to export JSON. Therefore you will need to follow these two steps to enable JSON export on any component.

* [Define a Sling Model for the component](../../../sites/developing/using/json-exporter-components.md#main-pars-title-673822892)
* [Annotate the Sling Model interface](/content#contentbody_title_820975085)

## Define a Sling Model for the Component {#define-a-sling-model-for-the-component}

First a Sling Model must be defined for the component.

>[!NOTE]
>
>For an example of using Sling Models see the article [Developing Sling Model Exporters in AEM](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/sling-model-exporter-tutorial-develop.html).

The Sling Model implementation class must be annotated with the following:

```java
@Model(... adapters = {..., ComponentExporter.class})
@Exporter(name = ExporterConstants.SLING_MODEL_EXPORTER_NAME, extensions = ExporterConstants.SLING_MODEL_EXTENSION)
@JsonSerialize(as = MyComponent.class)
```

This ensures that your component could be exported on its own, using the `.model` selector and the `.json` extension.

In addition, this specifies that the Sling Model class can be adapted into the `ComponentExporter` interface.

>[!NOTE]
>
>Jackson annotations are not usually specified at the Sling Model class level, but rather at the Model interface level. This is to ensure that the JSON Export is considered as part of the component API.

>[!NOTE]
>
>The `ExporterConstants` and `ComponentExporter` classes come from the `com.adobe.cq.export.json` bundle.

## Annotate the Sling Model Interface {#annotate-the-sling-model-interface}

To be taken into account by the JSON Exporter framework, the Model interface should implement the `ComponentExporter` interface (or `ContainerExporter`, in the case of a container component).

The corresponding Sling Model interface ( `MyComponent`) would be then annotated using [Jackson annotations](https://github.com/FasterXML/jackson-annotations/wiki/Jackson-Annotations) to define how it should be exported (serialized).

The Model interface needs to be properly annotated to define which methods should be serialized. By default, all methods that respect the usual naming convention for getters will be serialized and will derive their JSON property names naturally from the getter names. This can be prevented or overridden using `@JsonIgnore` or `@JsonProperty` to rename the JSON property.

## Example {#example}

The Core Components have supported JSON export since release [1.1.0 of the core components](/content/help/en/experience-manager/core-components/user-guide) and can be used as a reference.

For an example, see the Sling Model implementation of the Image Core Component and its annotated interface.

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-core-wcm-components project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/archive/master.zip)

## Related Documentation {#related-documentation}

For further details see:

* The [Content Fragments topic in the Assets user guide](https://helpx.adobe.com/experience-manager/6-4/assets/user-guide.html?topic=/experience-manager/6-4/assets/morehelp/content-fragments.ug.js)  

* [Content Fragment Models](../../../assets/using/content-fragments-models.md)
* [Authoring with Content Fragments](../../../sites/authoring/using/content-fragments.md)
* [JSON Exporter for Content Services](../../../sites/developing/using/json-exporter.md)
* [Core Components](/content/help/en/experience-manager/core-components/user-guide) and the [Content Fragment component](/content/help/en/experience-manager/core-components/using/content-fragment-component)

