---
title: Leaderboard Essentials
seo-title: Leaderboard Essentials
description: Leaderboard feature overview
seo-description: Leaderboard feature overview
uuid: ed3df008-e3f4-4921-956d-8a5a24ae1599
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 0e3c30cd-a3d5-4a2f-9d37-91f0b06a9e1c
index: y
internal: n
snippet: y
---

# Leaderboard Essentials{#leaderboard-essentials}

This page provides the essential information for working with the leaderboard feature.

Prior to including the leaderboard component on a page, it is necessary to configure [Communities Scoring and Badges](../../communities/using/implementing-scoring.md). See also [Scoring and Badges Essentials](../../communities/using/configure-scoring.md).

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/gamification/components/hbs/leaderboard</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.gamification.hbs.leaderboard</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/gamification/components/hbs/leaderboard/leaderboard.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/gamification/components/hbs/leaderboard/clientlibs/leaderboard.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/enabling-leaderboard.md">Leaderboard Feature</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

<!--
Comment Type: draft

<h2>Essentials for Server-Side</h2>
-->

<!--
Comment Type: draft

<ul>
<li>Leaderboard API ???</li>
</ul>
<ul>
<li>Leaderboard Endpoints ???</li>
</ul>
<ul>
<li><a href="../../communities/using/server-customize.md">Server-side Customizations</a> ???</li>
</ul>
-->

### File Library Function {#file-library-function}

A community site structure that includes the [Leaderboard function](../../communities/using/functions.md#leaderboardfunction), includes a configured `leaderboard` component.
