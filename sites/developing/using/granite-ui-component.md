---
title: Creating a New Granite UI Field Component
seo-title: Creating a New Granite UI Field Component
description: null
seo-description: Granite UI provides a range of components designed to be used in forms, called fields
uuid: 8cd348f7-18b1-43a9-912f-90b652210471
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 8fbfa6e0-5f3e-43a0-b99c-8a6b4a382849
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Creating a New Granite UI Field Component{#creating-a-new-granite-ui-field-component}

Granite UI provides a range of components designed to be used in forms; these are called *fields* in the Granite UI vocabulary. The standard Granite form components are available under:

`/libs/granite/ui/components/foundation/form/*`

>[!NOTE]
>
>These Granite UI form fields are of particular interest as they are used for [component dialogs](../../developing/using/developing-components.md).

>[!NOTE]
>
>For full details about fields, please see the [Granite UI documentation](/developing/using/reference-materials/granite-ui/api/index).

Use the Granite UI Foundation framework to develop and/or extend Granite components. This has two elements:

* server-side:

    * a collection of foundation components

        * foundation - modular, composable, layerable, reusable
        * components - Sling components

    * helpers to aid application development

* client-side:

    * a collection of clientlibs providing some vocabulary (i.e. extension of the HTML language) to achieve generic interaction patterns through an Hypermedia-driven UI

The generic Granite UI component `field` is composed of two files of interest:

* `init.jsp`: handles the generic processing; labelling, description, and provides form value you will need when rendering your field.
* `render.jsp`: this is where the actual rendering of the field is performed and needs to be overridden for your custom field; is included by `init.jsp`.

Please refer to the [Granite UI documentation - Field](/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/foundation/form/field/index) if you want more details.

For examples, see:

* `cqgems/customizingfield/components/colorpicker`

    * provided by the [Code Sample](../../developing/using/developing-components-samples.md#codesamplehowtocustomizedialogfields)

* `granite/ui/components/foundation/form`

>[!NOTE]
>
>As this mechanism uses JSP, i18n and XSS are not given out-of-the-box. This means that you will need to internationalize and escape your Strings. The following directoriy contains the generic fields from a standard instance, you can use these as a reference: 
>
>`/libs/granite/ui/components/foundation/form` directory

### Creating the server-side script for the component {#creating-the-server-side-script-for-the-component}

Your customized field should only override the `render.jsp` script, where you provide the markup for your component. You can consider the JSP (i.e. the rendering script) as a wrapper for your markup.

1. Create a new component that uses the `sling:resourceSuperType` property to inherit from:

   `/libs/granite/ui/components/foundation/form/field`

1. Override the script:

   `render.jsp`

   In this script, you need to generate the hypermedia markup (i.e. enriched markup, containing the hypermedia affordance) so that the client knows how to interact with the generated element. This should follow the Granite UI server-side style of coding.

   When customizing, the only contract that you *must* fulfill is to read the form value (initialized in `init.jsp`) from the request using:

   ```
   // Delivers the value of the field (read from the content)
   ValueMap vm = (ValueMap) request.getAttribute(Field.class.getName());
   vm.get("value, String.class"); 
   ```

   For more details, please refer to the implementation of out-ot-the-box Granite UI fields; for example, `/libs/granite/ui/components/foundation/form/textfield`.

   >[!NOTE]
   >
   >At the moment, JSP is the preferred scripting method, as passing information from one component to another (which is quite frequent in the context of form/fields) is not easily achieved in HTL.

### Creating the client-library for the component {#creating-the-client-library-for-the-component}

To add specific client-side behavior to your component:

1. Create a clientlib of category `cq.authoring.dialog`.
1. Create a clientlib of category `cq.authoring.dialog` and define your `JS`/ `CSS` inside it.

   Define your `JS`/ `CSS` inside the clientlib.

   >[!NOTE]
   >
   >At the moment, the Granite UI does not provide any out-of-the-box listeners or hooks that you can use directly to add JS behavior. So, to add additional JS behavior to your component, you have to implement a JS hook to a custom class that you then assign to your component during the markup generation.

