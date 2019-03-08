---
title: File Library Essentials
seo-title: File Library Essentials
description: Working with the file library feature
seo-description: Working with the file library feature
uuid: 18f09d88-bb28-4e22-a5a8-88cfc9b9ab37
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: dd54d357-4027-4823-a9c3-a5c00341f73e
index: y
internal: n
snippet: y
---

# File Library Essentials{#file-library-essentials}

This page provides the essential information for working with the file library feature.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/filelibrary/components/hbs/filelibrary</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.voting<br /> cq.social.hbs.filelibrary</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/filelibrary/components/hbs/filelibrary/filelibrary.hbs<br /> /libs/social/filelibrary/components/hbs/folder/folder.hbs<br /> /libs/social/filelibrary/components/hbs/folder/item.hbs<br /> /libs/social/filelibrary/components/hbs/document/document.hbs<br /> /libs/social/filelibrary/components/hbs/document/item.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/filelibrary/components/hbs/filelibrary/clientlibs/filelibrary.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/file-library.md">File Library Feature</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [File Library API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/filelibrary/client/api/package-summary.md)

* [File Library Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/filelibrary/client/endpoints/package-summary.md)

* [Server-side Customizations](../../communities/using/server-customize.md)

### File Library Function {#file-library-function}

A community site structure that includes the [File Library function](../../communities/using/functions.md#file-library-function), includes a configured `file library` component.

### Accessing Comments Posted for File Libraries (UGC) {#accessing-comments-posted-for-file-libraries-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

