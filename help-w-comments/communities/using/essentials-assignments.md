---
title: Assignments Essentials
seo-title: Assignments Essentials
description: Assignments feature overview for enablement communities
seo-description: Assignments feature overview for enablement communities
uuid: a6553ddf-9192-4a54-8605-a344c1e29315
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: e55f89bf-ddab-4598-890b-98e93086f166
index: y
internal: n
snippet: y
---

# Assignments Essentials{#assignments-essentials}

This page provides the essential information for working with the assignments feature of [enablement community](../../communities/using/overview.md#enablement-community) sites.

The assignments feature is the ability to assign enablement resources and learning paths to members of enablement communities.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/enablement/components/hbs/myassigned</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.enablement.hbs.breadcrumbs<br /> cq.social.enablement.hbs.myassigned<br /> cq.social.enablement.hbs.resource<br /> cq.social.enablement.hbs.learningpath</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/myassigned.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/clientlibs/myassigned.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/assignments.md">Assignments Feature</a></td> 
  </tr>
 </tbody>
</table>

### Completion and Success Status {#completion-and-success-status}

Completion and Success status are used in reports as well as status banners on Assignments.

Completion Status:

* Not Assigned
* Not Started (New)
* In Progress
* Complete

Success Status:

* Unknown
* Pass
* Fail

The only possible Combinations of Completion and Success Status are :

| **Completion** |**Success** |
|---|---|
| Not Started |Unknown |
| In Progress |Unknown |
| Complete |Pass |
| Complete |Fail |

## Essentials for Server-Side {#essentials-for-server-side}

### Assignments Function {#assignments-function}

A community site structure that includes the [Assignments function](../../communities/using/functions.md#assignments-function), includes a configured ` [assignments](../../communities/using/assignments.md)` component.

### Reference APIs {#reference-apis}

* [Enablement API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/client/api/package-summary.md)

* [Reporting API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/client/reporting/api/package-summary.md)

* [Reporting Analytics API](/content/docs/en/aem/6-3/develop/ref/javadoc/com/adobe/cq/social/enablement/client/reporting/analytics/api/package-summary.md)

