---
title: Calendar Essentials
seo-title: Calendar Essentials
description: Calendar feature overview
seo-description: Calendar feature overview
uuid: a932fa42-f9d3-4917-927c-83214fb8aa2d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4192481c-300b-4c66-975d-2b96f61ddd3d
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
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/client-customize.md#clientlibsforscf"><strong>clientllibs</strong></a></td> 
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

* [Calendar APIs](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/api/package-summary)

* [Calendar Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/calendar/client/endpoints/package-summary)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Calendar Function {#calendar-function}

A community site structure that includes the [Calendar function](../../communities/using/functions.md#calendarfunction) will have a configured c `alendar`component. The Calendar function supports identifying a [privileged member user group](../../communities/using/users.md#privilegedmembersgroup).

### Accessing Calendar Posts (UGC) {#accessing-calendar-posts-ugc}

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

