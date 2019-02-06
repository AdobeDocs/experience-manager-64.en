---
title: DO NOT PUBLISH BACKUP Content Fragments REST API
seo-title: DO NOT PUBLISH BACKUP Content Fragments REST API
description: null
seo-description: null
page-status-flag: never-activated
uuid: 95e6332f-1ace-4f6b-88f5-02a50815e390
discoiquuid: afda43c3-e6bc-4dbc-a39b-eeaf32017114
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH BACKUP Content Fragments REST API{#do-not-publish-backup-content-fragments-rest-api}

## Overview {#overview}

The Assets REST API allows developers to access content (stored in AEM) directly over the HTTP API, via CRUD operations (Create, Read, Update, Delete).

The API can be used to realize headless Content Management Services (CMS) by providing Content Services to a JavaScript front end application. Or any other application that can execute HTTP requests and handle JSON responses.

For example, Single Page Applications (SPA), framework-based or custom, require content provided over the HTTP API, often in JSON format.

While AEM Core Components provide a very comprehensive, flexible and customizable API that can serve (at least) the Read operations for this purpose, they do require WCM know-how for implementation as they must be hosted in (API) pages that are based on dedicated AEM templates. Not every SPA development organization has access to such resources. This page-based approach may also be inconvenient or even inadequate for some use-cases.

This is when the Assets REST API can be used. It allows developers to access assets (images and content fragments) directly, without need to embed them in a page. Contrary to the API provided through AEM Core Components, the Assets REST API also allows developers to change content - by creating new, updating, or deleting existing assets and folders.

The Assets REST API:

* follows the [HATEOAS principle](https://en.wikipedia.org/wiki/HATEOAS)   

* implements the [SIREN format](https://github.com/kevinswiber/siren)

## Prerequisites {#prerequisites}

The Assets REST API is available on each out-of-the-box install of a recent AEM version.

>[!NOTE]
>
>For AEM 6.4 you have to install a Prerelease Feature Pack to get full support for content fragments. For some use-cases you then have to perform some additional configuration; see the [Security](../../assets/using/assets-api-content-fragments-backup.md#security) section.

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

The exact format of supported requests is defined in the reference section of this documentation.

### Transactional Behavior {#transactional-behavior}

All requests are atomic.

This means that subsequent ( `write`) requests cannot be combined into a single transaction that could succeed or fail as a single entity.

### AEM (Assets) REST API versus AEM Components {#aem-assets-rest-api-versus-aem-components}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Aspect</td> 
   <td>Assets REST API<br /> </td> 
   <td>AEM Component</td> 
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
       /content/dam/we-retail/en/products/apparel/gloves/Classic Leather.jpg</code><br /> request:<br /> <span class="code">/api/assets//we-retail/en/products/apparel/gloves/Classic Leather.jpg.json</span></p> </td> 
   <td><p>Needs to be referenced through an AEM component on an AEM page.</p> <p>Uses the <span class="code">.model</span> selector to create the JSON representation.</p> <p>An example URL would look like:<br /> <span class="code">http://.../content/we-retail/language-masters/en/products/men/gloves/classic-leather-gloves/jcr:content/root/product/image.json</span></p> </td> 
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
>* [the README of this GitHub repository](https://git.corp.adobe.com/Granite/com.adobe.granite.cors)
>* [CORS/AEM explained](/content/help/en/experience-manager/kt/platform-repository/using/cors-security-article-understand)
>* [Video](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/cors-security-technical-video-develop.html)
>

In environments with specific authentication requirements, OAuth is recommended. To configure please see this [Gem session](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem). Additional information is available under [OAuth scopes](/content/help/en/experience-manager/kt/platform-repository/using/oauth-code-sample-develop)

## Available Features {#available-features}

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

## Extensibility {#extensibility}

For further information see this [Overview of the Granite HTTP API Framework](https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html).

## Entity Types {#entity-types}

### Folders {#folders}

Folders act as containers for assets and other folders. They reflect the structure of the AEM content repository.

The Assets REST API exposes access to the properties of a folder; for example its name, title, etc. Assets are exposed as child entities of folders.

>[!NOTE]
>
>Depending on the asset type the list of child entities may already contain the full set of properties that defines the respective child entity. Alternatively, only a reduced set of properties may be exposed for an entity in this list of child entities.

### Assets {#assets}

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

See:

* Assets REST API
* Content Fragments REST API

### API URLs {#api-urls}

## Additional Resources {#additional-resources}

For further information see:

* [AEM Gem session: OAuth](/content/help/en/experience-manager/kt/eseminars/gems/aem-oauth-server-functionality-in-aem)
* [HAF Extensibility (GitHub)](https://git.corp.adobe.com/pages/granite/com.adobe.granite.rest.api/index.html)   

* [Existing Assets REST API docs](../../assets/using/mac-api-assets.md)

