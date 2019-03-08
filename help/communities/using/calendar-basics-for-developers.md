---
title: Calendar Essentials
seo-title: Calendar Essentials
description: Calendar feature overview
seo-description: Calendar feature overview
uuid: 4768f78a-62a0-4e0e-b74a-dd5b7c4529d3
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4e0b5189-dd6f-4c9d-bcd2-0e22bad4c2b1
index: y
internal: n
snippet: y
---

# Calendar Essentials{#calendar-essentials}

This page provides essential information on working with the calendar feature.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/calendar/components/hbs/calendar</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/client-customize.md#clientlibs-for-scf"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.calendar</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td>/libs/social/calendar/components/hbs/calendar/calendar.hbs</td> 
   <td> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td>/libs/social/calendar/components/hbs/calendar/clientlibs/css/calendar.css<br /> /libs/social/calendar/components/hbs/calendar/clientlibs/css/jqueryui.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/calendar.md">Using Calendars</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Calendar APIs](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/api/package-summary.md)

* [Calendar Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/endpoints/package-summary.md)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Calendar Function {#calendar-function}

A community site structure that includes the [Calendar function](../../communities/using/functions.md#calendar-function) will have a configured c `alendar`component. The Calendar function supports identifying a [privileged member user group](../../communities/using/users.md#privileged-members-group).

### Accessing Calendar Posts (UGC) {#accessing-calendar-posts-ugc}

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

