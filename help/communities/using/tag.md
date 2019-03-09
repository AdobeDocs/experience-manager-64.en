---
title: Tag Essentials
seo-title: Tag Essentials
description: Tag overview
seo-description: Tag overview
uuid: e20cda03-4e68-4f65-a97f-2cb3ba1a120e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 48bb86af-67a9-47fe-988a-14775a07ceb4
---

# Tag Essentials{#tag-essentials}

When AEM Communities components are configured with tagging enabled, community members are able to tag the content they post in the publish environment.

The underlying infrastructure for tags applied in the publish environment is the same as for tags applied to content in the author environment, such as pages and assets :

* See [Administering Tags](../../sites/administering/using/tags.md) and [Tagging User Generated Content](../../communities/using/tag-ugc.md) (UGC) for information about creating and managing tags.

* See [Tagging for Developers](../../sites/developing/using/tags.md) for information about the [tagging framework](../../sites/developing/using/framework.md) as well as including and extending tags in [custom applications](../../sites/developing/using/building.md).

* See [Using Social Tag Cloud](../../communities/using/tagcloud.md) for information for authors on how to add a `social tag cloud` component to a page to highlight the tags applied to UGC in the publish environment.

* See [Tagging Enablement Resources](../../communities/using/tag-resources.md) for information on tagging resources for catalogs.

Tagging of UGC may be enabled when configuring a [community site](../../communities/using/sites-console.md#tagging) or one of the following features :

* [blog](../../communities/using/blog-feature.md)
* [calendar](../../communities/using/calendar.md)
* [file library](../../communities/using/file-library.md)
* [forum](../../communities/using/forum.md)
* [QnA](../../communities/using/working-with-qna.md)

## Essentials for Client-Side {#essentials-for-client-side}

### Social Tag Cloud {#social-tag-cloud}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/commons/components/hbs/tagcloud</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.tagcloud</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/commons/components/hbs/tagcloud/tagcloud.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/commons/components/hbs/tagcloud/clientlibs/tagcloud.css</td> 
  </tr>
  <tr>
   <td><strong>properties</strong></td> 
   <td>see <a href="../../communities/using/tagcloud.md">Using Social Tag Cloud</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Social Tag Cloud API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/tagcloud/api/package-summary.md)

* [Social Tag Manager](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/tagging/package-summary.md)

* [Server-side Customizations](../../communities/using/server-customize.md)

## Tag Searching {#tag-searching}

As of [feature pack 1](../../communities/using/deploy-communities.md#latestfeaturepack) (FP1), tag searching is performed using [tag titles](../../sites/developing/using/framework.md#tag-characteristics).

Prior to FP1, search was performed using [tag ids](../../sites/developing/using/framework.md#tagid).
