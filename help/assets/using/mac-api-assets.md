---
title: Assets HTTP API
seo-title: Assets HTTP API
description: null
seo-description: Learn about the implementation, data model, and features of Assets HTTP API. Use Assets HTTP API to perform various tasks around assets.
uuid: bec52133-a2d2-4bd6-9880-eb9302abe258
acrolinxdate: 2019-01-12T17 31 17.841-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: red
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/mac_api_assets_krs_workflow_f3c2f2ccebf6138e_151_report.xml
acrolinxsentences: 115
acrolinxwords: 936
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: extending-assets
content-type: reference
discoiquuid: c8f65039-a99c-4d6e-b213-e61904208877
disttype: dist5
gnavtheme: light
preview: true
index: y
internal: n
snippet: y
---

# Assets HTTP API{#assets-http-api}

<!--
Comment Type: remark
Last Modified By: Ashish Gupta . (asgupta)
Last Modified Date: 2018-12-13T03:12:21.192-0500
<p style="text-align: center;"><strong>DO NOT PUBLISH</strong></p>
<p>Contains AEM 6.5 content in Draft-only mode.</p>
<p>Article marked Preview to avoid accidental publishing.</p>
-->

## Overview {#overview}

The Assets HTTP API is a specific part of the general Marketing Cloud API. For general documentation, see Marketing Cloud API user documentation.

The Assets HTTP API is exposed at */api/assets*, and allows for create-read-update-delete (CRUD) operations on Assets, including binary, metadata, renditions, and comments.

<!--
Comment Type: annotation
Last Modified By: meyer
Last Modified Date: 2018-12-14T06:30:37.007-0500
I don't think we should use the term "Marketing Cloud API" (as "Marketing Cloud" anyway becomes "Experience Cloud"). IMO the first sentence can be removed
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T14:41:56.420-0500
Correct, must be removed ("marketing cloud api"), or refactored to "Adobe I/O", in case that is relevant. Not sure it as, as Assets HTTP API is an AEM REST API period.
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T14:43:11.503-0500
continue with ... and structured content with AEM Content Fragments
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-18T01:14:04.082-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<p>The Assets HTTP API is exposed at <em>/api/assets</em>, and allows for create-read-update-delete (CRUD) operations on Assets, including binary, metadata, renditions, and comments, together with structured content usng AEM Content Fragments.</p>
-->

<!--
Comment Type: annotation
Last Modified By: meyer
Last Modified Date: 2018-12-14T06:30:37.007-0500
I don't think we should use the term "Marketing Cloud API" (as "Marketing Cloud" anyway becomes "Experience Cloud"). IMO the first sentence can be removed
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T14:41:56.420-0500
Correct, must be removed ("marketing cloud api"), or refactored to "Adobe I/O", in case that is relevant. Not sure it as, as Assets HTTP API is an AEM REST API period.
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T14:43:11.503-0500
continue with ... and structured content with AEM Content Fragments
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-13T08:36:32.322-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>The Assets HTTP API encompasses the:</p>
<ul>
<li>Assets REST API
<ul>
<li>including <a href="../../assets/using/assets-api-content-fragments.md">support for Content Fragments</a></li>
</ul> </li>
</ul>
<p>The current implementation of AEM Assets HTTP API is REST.</p>
</note>
-->

## Current implementation {#current-implementation}

The Assets HTTP API was first introduced with Adobe Experience Manager (AEM) Assets 6.1.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-13T00:08:01.737-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<p><a href="../../assets/using/assets-api-content-fragments.md">Support for Content Fragments</a> was added in AEM Assets 6.5.</p>
-->

To access the API:

1. Start AEM
1. Open the API Service Document at `http://<*hostname*>:<*port*>/api.json`
1. Follow the Assets service link.

<!--
Comment Type: draft

<h2>Content Fragments</h2>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-13T00:08:14.330-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<p>A <a href="../../assets/using/content-fragments.md">content fragment</a> is a special type of asset. They can be used to access structured data, such as texts, numbers, dates, amongst others. </p>
<p>As there are several differences to <em>standard</em> assets (such as images or documents), some additional rules apply to handling them.</p>
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T15:08:07.919-0500
audio is not quite a "standard asset". Like video, it's streamed, progressively downloaded, etc etc. Just "images" suffices in the sentence here. Or "such as images or documents". Maybe use "images and documents" as synonym for "standard assets" throughout.
-->

<!--
Comment Type: draft

<p>For further information see <a href="../../assets/using/assets-api-content-fragments.md">Content Fragments Support in the AEM Assets HTTP API</a>.<br /> </p>
-->

## Data model {#data-model}

The Assets HTTP API exposes two major elements, folders and assets.

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T15:13:26.583-0500
continue with ..., for standard assets, and more detailed elements for custom data models describing structured content in Content Fragments. See
<here>
for more information about Content Fragment Data Models.
</here>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-18T01:20:40.372-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<p>The Assets HTTP API exposes two major elements, folders and assets (for standard assets).</p>
<p>Additionally, it exposes more detailed elements for the custom data models that describe structured content in Content Fragments. See <a href="../../assets/using/assets-api-content-fragments.md#contentfragments">Content Fragment Data Models</a> for further information.</p>
-->

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T15:13:26.583-0500
continue with ..., for standard assets, and more detailed elements for custom data models describing structured content in Content Fragments. See
<here>
for more information about Content Fragment Data Models.
</here>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-13T00:08:10.979-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-18T01:46:18.216-0500
<p>msiegel (yesterday)</p>
<p>with the addition above we shouldn't need this note anymore</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>The Data Model does not apply to <a href="../../assets/using/assets-api-content-fragments.md">Content Fragments</a>.<br /> </p>
</note>
-->

### Folders {#folders}

Folders are like directories in tradtional filesystems. They are containers for other folders or asserts. Folders have the following components:

**Entities**: The entities of a folder are its child elements, which can be folders and assets.

**Properties**:

```
name  -- Name of the folder. This is the same as the last segment in the URL path without the extension
title -- Optional title of the folder which can be displayed instead of its name
```

**Links**

Folders expose three links:

```xml
self      -- Link to itself
parent    -- Link to the parent folder
thumbnail -- (Optional) link to a folder thumbnail image
```

### Assets {#assets}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-12-18T01:34:49.495-0500
<p>6.5 content in Draft-only mode</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>Standard assets (such as images and documents) consist of the following elements.</p>
<p>For information about elements in Content Fragments see <a href="../../assets/using/assets-api-content-fragments.md#contentfragments">Content Fragments Support in AEM Assets HTTP API</a>.<br /> </p>
</note>
-->

Assets are actually multi-part elements:

* The properties and metadata of the asset
* Multiple renditions such as the original rendition (which is the originally uploaded asset), a thumbnail and various other renditions. Additional renditions may be images of different sizes, different video encodings, or extracted pages from PDF or InDesign.
* Optional comments

Folders have the following components:

**Entities**

The children of Assets are its renditions.

**Properties**

**Links**

<!--
Comment Type: annotation
Last Modified By: msiegel
Last Modified Date: 2018-12-17T15:12:30.823-0500
Here we need a final branch-off to Content Fragments. "Folders" above still applies for content fragments as well. Everything below "Assets" here is specific to "standard assets", or "standard assets such as images and documents". Something like Assets Assets such as images and documents consist of the following elements (see
<here>
for information about elements in Content Fragments): - the properties ... - multiple renditions ... ...
</here>
-->

## Available features {#available-features}

The Assets HTTP API includes the following features:

* Retrieve a folder listing
* Create a folder
* Create an asset
* Update asset binary
* Update asset metadata
* Create an asset rendition
* Update an asset rendition
* Create an asset comment
* Copy a folder or asset
* Move a folder or asset
* Delete a folder, asset, or rendition

<!--
Comment Type: annotation
Last Modified By: meyer
Last Modified Date: 2018-12-14T06:31:43.345-0500
For "browsing convenience", can we maybe have the different sections visible in the TOC that appears on the right side of the page?
-->

>[!NOTE]
>
>For the ease of readability the following examples omit the full cURL notation. In fact the notation does correlate with [Resty](https://github.com/micha/resty) which is a script wrapper for cURL.

**Prerequisites**

* Go to *http://&lt;Server&gt;:&lt;Port&gt;/system/console/configMgr*.
* Navigate to **Adobe Granite CSRF Filter**.
* Make sure the property **Filter Methods** incudes: POST, PUT, DELETE.

### Retrieve a Folder Listing {#retrieve-a-folder-listing}

Retrieves a Siren representation of an existing folder and of its child entities (subfolders or assets).

**Request**

```
GET /api/assets/myFolder.json
```

**Response codes**

```
200 - OK - success
404 - NOT FOUND - folder does not exist or is not accessible
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

**Response**

The class of the entity returned is assets/folder.

Properties of contained entities are a subset of the full set of properties of each entity. In order to obtain a full representation of the entity, clients should retrieve the contents of the URL pointed to by the link with a `rel` of `self`.

### Create a Folder {#create-a-folder}

Creates a new `sling`: `OrderedFolder` at the given path. If a &#42; is given instead of a node name the servlet will use the parameter name as node name. Accepted as request data is either a Siren representation of the new folder or a set of name-value pairs, encoded as `application/www-form-urlencoded` or `multipart`/ `form`- `data`, useful for creating a folder directly from an HTML form. Additionally, properties of the folder can be specified as URL query parameters.

The operation will fail with a `500` response code if the parent node of the given path does not exist. If the folder already exists a `409` response code is returned.

**Parameters**

```
name - Folder name
```

**Request**

```
POST /api/assets/myFolder -H"Content-Type: application/json" -d '{"class":"assetFolder","properties":{"title":"My Folder"}}'
```

Or

```
POST /api/assets/* -F"name=myfolder" -F"title=My Folder"
```

**Response codes**

```
201 - CREATED - on successful creation
409 - CONFLICT - if folder already exist
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Create an Asset {#create-an-asset}

Creates a DAM asset at the given path with the given file. If a &#42; is given instead of a node name the servlet will use the parameter name or the file name as node name.

**Parameters**

```
name - Asset name
file - File reference
```

**Request**

```
POST /api/assets/myFolder/myAsset.png -H"Content-Type: image/png" --data-binary "@myPicture.png"
```

or

```
POST /api/assets/myFolder/* -F"name=myAsset.png" -F"file=@myPicture.png"
```

**Response codes**

```
201 - CREATED - if Asset has been created successfully
409 - CONFLICT - if Asset already exist
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Update Asset binary {#update-asset-binary}

Updates an Assets binary (rendition with name original). This will trigger the default Asset workflow if configured.

**Request**

```
PUT /api/assets/myfolder/myAsset.png -H"Content-Type: image/png" --data-binary @myPicture.png
```

**Response codes**

```
200 - OK - if Asset has been updated successfully
404 - NOT FOUND - if Asset could not be found or accessed at the provided URI
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Update Asset metadata {#update-asset-metadata}

Updates the Asset metadata properties.

**Request**

```
PUT /api/assets/myfolder/myAsset.png -H"Content-Type: application/json" -d '{"class":"asset", "properties":{"dc:title":"My Asset"}}'
```

**Response codes**

```
200 - OK - if Asset has been updated successfully
404 - NOT FOUND - if Asset could not be found or accessed at the provided URI
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Create an Asset Rendition {#create-an-asset-rendition}

Creates a new asset rendition for an asset. If request parameter name is not provided the file name is used as rendition name.

**Parameters**

```
name - Rendition name
file - File reference
```

**Request**

```
POST /api/assets/myfolder/myasset.png/renditions/web-rendition -H"Content-Type: image/png" --data-binary "@myRendition.png"
```

or

```
POST /api/assets/myfolder/myasset.png/renditions/* -F"name=web-rendition" -F"file=@myRendition.png"
```

**Response codes**

```
201 - CREATED - if Rendition has been created successfully
404 - NOT FOUND - if Asset could not be found or accessed at the provided URI
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Update an Asset Rendition {#update-an-asset-rendition}

Updates respectively replaces an asset rendition with the new binary data.

**Request**

```
PUT /api/assets/myfolder/myasset.png/renditions/myRendition.png -H"Content-Type: image/png" --data-binary @myRendition.png
```

**Response codes**

```
200 - OK - if Rendition has been updated successfully
404 - NOT FOUND - if Asset could not be found or accessed at the provided URI
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Create an Asset Comment {#create-an-asset-comment}

Creates a new asset comment.

**Parameters**

```
message - Message
annotationData - Annotation data (JSON)
```

**Request**

```
POST /api/assets/myfolder/myasset.png/comments/* -F"message=Hello World." -F"annotationData={}"
```

**Response codes**

```
201 - CREATED - if Comment has been created successfully
404 - NOT FOUND - if Asset could not be found or accessed at the provided URI
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Copy a Folder or Asset {#copy-a-folder-or-asset}

Copies a folder or asset at the given path to a new destination.

**Request Headers**

```
X-Destination - a new destination URI within the API solution scope to copy the resource to
X-Depth - either 'infinity' or '0'. The value '0' only copies the resource and its properties, no children.
X-Overwrite - 'F' to prevent overwriting an existing destination
```

**Request**

```
COPY /api/assets/myFolder -H"X-Destination: /api/assets/myFolder-copy"
```

**Response codes**

```
201 - CREATED - if folder/asset has been copied to a non-existing destination
204 - NO CONTENT - if the folder/asset has been copied to an existing destination
412 - PRECONDITION FAILED - if a request header is missing or
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Move a Folder or Asset {#move-a-folder-or-asset}

Moves a folder or asset at the given path to a new destination.

**Request Headers**

```
X-Destination - a new destination URI within the API solution scope to copy the resource to
X-Depth - either 'infinity' or '0'. The value '0' only copies the resource and its properties, no children.
X-Overwrite - either 'T' to force deletion of existing resources or 'F' to prevent overwriting an existing resource.
```

**Request**

```
MOVE /api/assets/myFolder -H"X-Destination: /api/assets/myFolder-moved"
```

**Response codes**

```
201 - CREATED - if folder/asset has been copied to a non-existing destination
204 - NO CONTENT - if the folder/asset has been copied to an existing destination
412 - PRECONDITION FAILED - if a request header is missing or
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

### Delete a Folder, Asset, or Rendition {#delete-a-folder-asset-or-rendition}

Deletes a resource (-tree) at the given path.

**Request**

```
DELETE /api/assets/myFolder
```

or

```
DELETE /api/assets/myFolder/myAsset.png
```

or

```xml
DELETE /api/assets/myFolder/myAsset.png/renditions/original
```

**Response codes**

```
200 - OK - if folder has been deleted successfully
412 - PRECONDITION FAILED - if root collection cannot be found or accessed
500 - INTERNAL SERVER ERROR - if something else goes wrong
```

