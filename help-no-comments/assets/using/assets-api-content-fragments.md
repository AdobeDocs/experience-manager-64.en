---
title: DO NOT PUBLISH Content Fragments Support in AEM Assets HTTP API
seo-title: DO NOT PUBLISH Content Fragments Support in AEM Assets HTTP API
description: null
seo-description: null
page-status-flag: never-activated
uuid: 981fa350-d670-4c11-bc38-029ed180d827
contentOwner: aheimoz
discoiquuid: f1786ffa-139c-4e04-8d59-bf123f8d44ca
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH Content Fragments Support in AEM Assets HTTP API{#do-not-publish-content-fragments-support-in-aem-assets-http-api}

## Overview {#overview}

>[!NOTE]
>
>The [Assets HTTP API](../../assets/using/mac-api-assets.md) encompasses the:
>
>* Assets REST API >
>    * including support for Content Fragments
>
>The current implementation of AEM Assets HTTP API is REST.

The Adobe Experience Manager (AEM) [Assets REST API](../../assets/using/mac-api-assets.md) allows developers to access content (stored in AEM) directly over the HTTP API, via CRUD operations (Create, Read, Update, Delete).

The API allows you to operate AEM as a headless CMS (Content Management System) by providing Content Services to a JavaScript front end application. Or any other application that can execute HTTP requests and handle JSON responses.

For example, Single Page Applications (SPA), framework-based or custom, require content provided over the HTTP API, often in JSON format.

While AEM Core Components provide a very comprehensive, flexible and customizable API that can serve required Read operations for this purpose, and whose JSON output can be customized, they do require AEM WCM (Web Content Management) know-how for implementation as they must be hosted in (API) pages that are based on dedicated AEM templates. Not every SPA development organization has access to such resources.

This is when the Assets REST API can be used. It allows developers to access assets (for example, images and content fragments) directly, without need to first embed them in a page, and deliver their content in serialized JSON format. (Note that it is not possible to customize JSON output from the Assets REST API). The Assets REST API also allows developers to modify content - by creating new, updating, or deleting existing assets, content fragments and folders.

The Assets REST API:

* follows the [HATEOAS principle](https://en.wikipedia.org/wiki/HATEOAS)   

* implements the [SIREN format](https://github.com/kevinswiber/siren)

## Prerequisites {#prerequisites}

The Assets REST API is available on each out-of-the-box install of a recent AEM version.

## Key Concepts {#key-concepts}

The Assets REST API offers [REST](https://en.wikipedia.org/wiki/Representational_state_transfer)-style access to assets stored within an AEM instance. It uses the `/api/assets` endpoint and requires the path of the asset to access it (without the leading `/content/dam`).

The HTTP method determines the operation to be executed:

* **GET** - to retrieve a JSON representation of an asset or a folder
* **POST** - to create new assets or folders
* **PUT** - to update the properties of an asset or folder
* **DELETE** - to delete an asset or folder

>[!NOTE]
>
>The request body and/or URL parameters can be used to configure some of these operations; for example, define that a folder or an asset should be created by a **POST** request.

The exact format of supported requests is defined in the [API Reference](../../assets/using/assets-api-content-fragments.md#apireference) documentation.

### Transactional Behavior {#transactional-behavior}

All requests are atomic.

This means that subsequent ( `write`) requests cannot be combined into a single transaction that could succeed or fail as a single entity.

### AEM (Assets) REST API versus AEM Components {#aem-assets-rest-api-versus-aem-components}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Aspect</td> 
   <td>Assets REST API<br /> </td> 
   <td>AEM Component<br /> (components using Sling Models)</td> 
  </tr> 
  <tr> 
   <td>Supported use-case(s)</td> 
   <td>General purpose.</td> 
   <td><p>Optimized for consumption in a Single Page Application (SPA), or any other (content consuming) context.</p> <p>Can also contain layout information.</p> </td> 
  </tr> 
  <tr> 
   <td>Supported operations</td> 
   <td><p>Create, Read, Update, Delete.</p> <p>With additional operations depending on the entity type.</p> </td> 
   <td>Read-only.</td> 
  </tr> 
  <tr> 
   <td>Access</td> 
   <td><p>Can be accessed directly.</p> <p>Uses the <span class="code">/api/assets </span>endpoint, mapped to <span class="code">/content/dam</span> (in the repository).</p> <p>For example, to access:<code class="code">
       /content/dam/we-retail/en/products/apparel/gloves/Classic Leather.jpg</code><br /> request:<br /> <span class="code">/api/assets/we-retail/en/products/apparel/gloves/Classic Leather.jpg.json</span></p> </td> 
   <td><p>Needs to be referenced through an AEM component on an AEM page.</p> <p>Uses the <span class="code">.model</span> selector to create the JSON representation.</p> <p>An example URL would look like:<br /> <span class="code">http://.../content/we-retail/language-masters/en/products/men/gloves/classic-leather-gloves/jcr:content/root/product/image.model.json</span></p> </td> 
  </tr> 
  <tr> 
   <td>Security</td> 
   <td><p>Multiple options are possible.</p> <p>OAuth is proposed; can be configured separately from standard setup.</p> </td> 
   <td>Uses AEM's standard setup.</td> 
  </tr> 
  <tr> 
   <td>Architectural remarks</td> 
   <td><p>Write access will typically address an author instance.</p> <p>Read may also be directed to a publish instance.</p> </td> 
   <td>As this approach is read-only, it will typically be used for publish instances.</td> 
  </tr> 
  <tr> 
   <td>Output</td> 
   <td>JSON-based SIREN output: verbose, but powerful. Allows for navigating within the content.</td> 
   <td>JSON-based proprietary output; configurable through Sling Models. Navigating the content structure is hard to implement (but not necessarily impossible).</td> 
  </tr> 
 </tbody> 
</table>

### Security {#security}

If the Assets REST API is used within an environment without specific authentication requirements, AEM's CORS filter needs to be configured correctly.

>[!NOTE]
>
>For further information see:
>
>* [CORS/AEM explained](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-article-understand)
>* [Video - Developing for CORS with AEM](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-technical-video-develop)
>

In environments with specific authentication requirements, OAuth is recommended.

## Available Features {#available-features}

Content Fragments are a specific type of Asset, see [Working with Content Fragments](../../assets/using/content-fragments.md).

For further information about features available through the API see:

* [Available Features](../../assets/using/mac-api-assets.md#availablefeatures) of the Assets REST API
* [Entity Types](../../assets/using/assets-api-content-fragments.md#entitytypes)

### Paging {#paging}

The Assets REST API supports paging (for GET requests) via the URL parameters:

* `offset` - the number of the first (child) entity to retrieve
* `limit` - the maximum number of entities returned

The response will contain paging information as part of the `properties` section of the SIREN output. This `srn:paging` property contains the total number of (child) entities ( `total`), the offset and the limit ( `offset`, `limit`) as specified in the request.

>[!NOTE]
>
>Paging is typically applied on container entities (i.e. folders or assets with renditions), as it relates to the children of the requested entity.

#### Example: Paging {#example-paging}

`GET /api/assets.json?offset=2&limit=3`

```
...
"properties": {
    ...
    "srn:paging": {
        "total": 7,
        "offset": 2,
        "limit": 3
    }
    ...
}
...
```

## Entity Types {#entity-types}

### Folders {#folders}

Folders act as containers for assets and other folders. They reflect the structure of the AEM content repository.

The Assets REST API exposes access to the properties of a folder; for example its name, title, etc. Assets are exposed as child entities of folders.

>[!NOTE]
>
>Depending on the asset type the list of child entities may already contain the full set of properties that defines the respective child entity. Alternatively, only a reduced set of properties may be exposed for an entity in this list of child entities.

### Assets {#assets}

If an asset is requested, the response will return its metadata; such as title, name and other information as defined by the respective assets schema.

The binary data of an asset is exposed as a SIREN link of type `content` (also known as the `rel attribute`).

Assets can have multiple renditions. These are typically exposed as child entities, one exception being a thumbnail rendition, which is exposed as a link of type `thumbnail` ( `rel="thumbnail"`).

### Content Fragments {#content-fragments}

A [content fragment](../../assets/using/content-fragments.md) is a special type of asset. They can be used to access structured data, such as texts, numbers, dates, amongst others.

As there are several differences to *standard* assets (such as images or audio), some additional rules apply to handling them.

#### Representation {#representation}

Content fragments:

* Do not expose any binary data.   
* Are completely contained in the JSON output (within the `properties` property).   

* Are also considered atomic, i.e. the elements and variations are exposed as part of the fragment's properties vs. as links or child entities. This allows for efficient access to the payload of a fragment.

#### Content Models and Content Fragments {#content-models-and-content-fragments}

Currently the models that define the structure of a content fragment are not exposed through an HTTP API. Therefore the *consumer* needs to know about the model of a fragment (at least a minimum) - although most information can be inferred from the payload; as data types, etc. are part of the definition.

To create a new content fragment, the (internal repository) path has to be provided.

#### Associated Content {#associated-content}

Associated content is currently not exposed.

## API Reference {#api-reference}

See here for detailed API references:

* Adobe Experience Manager Assets API - Content Fragments
* [Assets HTTP API](../../assets/using/mac-api-assets.md)

    * [Available Features](../../assets/using/mac-api-assets.md#availablefeatures)

## Additional Resources {#additional-resources}

For further information see:

* [Assets HTTP API documentation](../../assets/using/mac-api-assets.md)
* [AEM Gem session: OAuth](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem)

