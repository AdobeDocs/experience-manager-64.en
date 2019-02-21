---
title: Content Properties and Nodes
seo-title: Content Properties and Nodes
description: Follow this page to learn about content properties and nodes.  
seo-description: Follow this page to learn about content properties and nodes.  
uuid: 92f679d3-6255-4983-ad5e-f35789f687d3
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-on-demand-services-app
discoiquuid: b35e54cd-e4eb-468f-ab53-1b09e75471f4
index: y
internal: n
snippet: y
---

# Content Properties and Nodes{#content-properties-and-nodes}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](../../sites/developing/using/spa-overview.md).

Articles, Banners, and Collections are represented as cq:Pages in AEM.

They share the same common properties found in any cq:Page in addition to several others shown below that represent Adobe Experience Manager (AEM) Mobile On-Demand services metadata and integration supporting properties.

The following tables describe the content properties and nodes.

##

### Common Integration Properties {#common-integration-properties}

| **Property Name** |**Type** |**Defaults or Expected Values** |**Description** |
|---|---|---|---|
| dps-id |String |  |assigned by AEM Mobile and stored by AEM once uploaded to AEM Mobile or imported from AEM Mobile |
| dps-resourceType |String |dps:Article | dps:Banner | dps:Collection |entity type property |
| dps-version |String |  |version of AEM Mobile entity (also contained within the full aemm-id) |
| dps-lastSynced |Date |  |date of last sync/import from AEM Mobile into AEM |
| dps-lastUploaded |Date |  |date of last upload from AEM to AEM Mobile |
| dps-lastUploadedBy |String:userid |  |id user that performed the last upload request from AEM to AEM Mobile |

##

### Core Metadata Properties {#core-metadata-properties}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Property Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Defaults or Expected Values</strong></td> 
  </tr>
  <tr>
   <td>dps-title<br /> </td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-shortTitle</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-abstract</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-shortAbstract</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-department</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-category</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-keywords</td> 
   <td>String[]</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-internalKeywords</td> 
   <td>String[]</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-importance</td> 
   <td>String[]</td> 
   <td>Importance from {"low", "normal", "high"}</td> 
  </tr>
 </tbody>
</table>

### Articles {#articles}

| **Property Name** |**Type** |**Defaults or Expected Values** |
|---|---|---|
| dps-author |String |  |
| dps-authorURL |String |  |
| dps-hideFromBrowsePage |Boolean |  |
| dps-access |String |ProtectedAccess from {"protected", "metered", "free"} |
| **Social** |  |  |
| dps-socialShareURL |String |  |
| dps-articleText |String |  |
| dps-url |String |  |

### Banners {#banners}

| **Property Name** |**Type** |**Defaults or Expected Values** |
|---|---|---|
| dps-tapAction |  |TapAction from {webLink} |
| dps-tapActinUrl |  |  |

### Collections {#collections}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Property Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Defaults or Expected Values</strong></td> 
  </tr>
  <tr>
   <td>dps-productId</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-readingPosition</td> 
   <td>String</td> 
   <td>from {"reset","retain"}</td> 
  </tr>
  <tr>
   <td>dps-horizontalSwipe</td> 
   <td>Boolean</td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>dps-allowDownlaod</p> </td> 
   <td>Boolean</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>dps-openDefault</td> 
   <td>String</td> 
   <td>from {"browsePage","contentView"}</td> 
  </tr>
  <tr>
   <td>dps-layout</td> 
   <td>String</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Content Nodes {#content-nodes}

### Common Nodes {#common-nodes}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Node Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Defaults or Expected Values</strong></td> 
   <td><strong>Description</strong></td> 
  </tr>
  <tr>
   <td>image</td> 
   <td><p>jcr:primaryType=nt:unstructured</p> <p>sling:resourceType=foundation/components/image</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Entities {#entities}

#### Articles {#articles-1}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node Name</td> 
   <td>Type</td> 
   <td>Defaults of Expected Values</td> 
   <td>Description</td> 
  </tr>
  <tr>
   <td>social-share-image</td> 
   <td> </td> 
   <td><p>jcr:primaryType=nt:unstructured</p> <p>sling:resourceType=foundation/components/image</p> <p> </p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

#### Banners {#banners-1}

| Node Name |Type |Defaults of Expected Values |Description |
|---|---|---|---|
|   |  |  |  |

#### Collections {#collections-1}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node Name</td> 
   <td>Type</td> 
   <td>Defaults of Expected Values</td> 
   <td>Description</td> 
  </tr>
  <tr>
   <td>background-image</td> 
   <td><p>jcr:primaryType=nt:unstructured</p> <p>sling:resourceType=foundation/components/image</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

