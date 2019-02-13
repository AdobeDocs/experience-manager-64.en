---
title: Social Graph Essentials
seo-title: Social Graph Essentials
description: follow component and following component overview
seo-description: follow component and following component overview
uuid: 466052f3-ff73-4526-86f3-8a3719607947
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 81e3e0ef-1f5e-4c3c-9b9f-4a834d1d43ed
index: y
internal: n
snippet: y
---

# Social Graph Essentials{#social-graph-essentials}

The ability for a Community member to follow [activities](../../communities/using/essentials-activities.md) as well as be followed is established through two components :

The `follow`component must be associated with another resource, and this association is already established for existing Communities members and features in a [community site](../../communities/using/overview.md#communitiessites).

The `following`component lists the members that are either following the current member or are being followed by the current member. This social graph of the relationships between members is included in the user profile established for a community site.

## Essentials for Client-Side {#essentials-for-client-side}

#### Following {#following}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/socialgraph/components/hbs/relationships</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.socialgraph</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/socialgraph/components/hbs/relationships/relationships.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/socialgraph/components/hbs/relationships/clientlibs/relationships.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/socialgraph.md">Using Social Graph</a></td> 
  </tr>
  <tr>
   <td style="vertical-align: top;"><strong> optional<br /> property</strong></td> 
   <td>
    <ul> 
     <li>Name : <strong><span class="code">outgoing</span></strong></li> 
     <li>Type : Boolean</li> 
     <li>Value :<br /> 
      <ul> 
       <li><i>true </i>- the <span class="code">following</span> component will list the members who the currently signed-in member <span class="code">follows</span></li> 
       <li><i>false </i>- the <span class="code">following</span> component will list the members who <span class="code">follow </span>the currently signed-in member</li> 
      </ul> </li> 
    </ul> <p>Defaults to <i>true</i> if the property is missing. Currently, it is not possible to set this property using the edit dialog in author mode. The property must be added to an instance of the <span class="code">following </span>node using <a href="../../sites/developing/using/developing-with-crxde-lite.md">CRXDE|Lite</a>.</p> </td> 
  </tr>
 </tbody>
</table>

#### Follow {#follow}

|  **resourceType** |social/socialgraph/components/hbs/following |
|---|---|
|  [**includable**](../../communities/using/scf.md#addorincludeacommunitiescomponent) |No |
|  **templates** | /libs/social/socialgraph/components/hbs/following/following.hbs |
|  **css** | /libs/social/socialgraph/components/hbs/following/clientlibs/following.css |

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Social Graph API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/graph/client/api/package-frame)

* [Social Graph Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/graph/client/endpoint/package-frame)

* [Server-side Customizations](../../communities/using/server-customize.md)

