---
title: Catalog Essentials
seo-title: Catalog Essentials
description: Catalog overview
seo-description: Catalog overview
uuid: a4ea0c45-4a96-4eb1-8854-45594d336388
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 13ca4e26-30b9-4e21-88c0-9f4fc3fdd8f7
index: y
internal: n
snippet: y
---

# Catalog Essentials{#catalog-essentials}

This page provides the essential information for working with the catalog feature of enablement community sites.

The catalog feature, when included in a community site, allows community members to browse and select enablement resources listed in a catalog.

The [ `enablement catalog` component](../../communities/using/catalog.md) allows community members to access a catalog of [enablement resources](../../communities/using/resources.md). The use of AEM tags is an important part of managing the appearance of enablement resources in a catalog.

See [Tagging Enablement Resources](../../communities/using/tag-resources.md).

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td>social/enablement/components/hbs/catalog</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.enablement.hbs.breadcrumbs<br /> cq.social.enablement.hbs.catalog<br /> cq.social.enablement.hbs.resource<br /> cq.social.enablement.hbs.learningpath</td> 
  </tr> 
  <tr> 
   <td> <strong>templates</strong></td> 
   <td> /libs/social/enablement/components/hbs/catalog/catalog.hbs<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>css</strong></td> 
   <td> /libs/social/enablement/components/hbs/catalog/clientlibs/catalog.css</td> 
  </tr> 
  <tr> 
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/catalog.md">Catalog Feature</a></td> 
  </tr> 
 </tbody> 
</table>

## Essentials for Server-Side {#essentials-for-server-side}

### Catalog Function {#catalog-function}

A community site structure that includes the [Catalog function](../../communities/using/functions.md#catalogfunction), includes a configured `enablement catalog` component.

### Pre-Filters {#pre-filters}

When a Catalog function has been added to a community site, it is possible to restrict the enablement resources and learning paths which appear in the catalog by specifying a pre-filter. This is done by setting properties on the instance of the catalog resource for the site.

Using the example of the [Enablement Tutorial](../../communities/using/getting-started-enablement.md) :

* on author
* using [CRXDE](../../sites/developing/using/developing-with-crxde-lite.md)

    * such as [http://&lt;server&gt;:&lt;port&gt;/crx/de](http://localhost:4502/crx/de)

* navigate to the catalog resource on the catalog page

    * for example, `/content/sites/enable/en/catalog/jcr:content/content/primary/catalog`

* add a child filters node

    * select the `catalog`node
    * select **Create Node**

        * Name : `filters`
        * Type : `nt:unstructured`

    * select **Save All**

* add `se_resource-tags` property to the `filters` node

    * select the `filters` node
    * add a Multi property

        * Name : `se_resource-tags`
        * Type : String
        * Value : *&lt;enter a [TagID](#prefiltertagids)&gt;*
        * select **Multi**
        * select **Add**

            * in popup dialog, select '+' to add additional pre-filter TagIDs

* re-publish the community site

![](assets/chlimage_1-189.png) 

#### Pre-filter TagIDs {#pre-filter-tagids}

The pre-filter [TagIDs](../../sites/developing/using/framework.md#tagid) must exactly match the tags applied to the enablement resources. These are visible in the `resources` folder for the site as the values of the property `se_resource-tags`.

![](assets/chlimage_1-190.png) 

### Reference APIs {#reference-apis}

* [Enablement API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/client/api/package-summary)

* [Reporting API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/client/reporting/api/package-summary)

* [Reporting Analytics API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/client/reporting/analytics/api/package-summary)

