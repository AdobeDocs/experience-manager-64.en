---
title: Community Group Essentials
seo-title: Community Group Essentials
description: Creating community sites dynamically
seo-description: Creating community sites dynamically
uuid: 168e7aeb-6e9a-468d-8ac4-274007cea252
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4f85cd3c-5158-4f23-abe2-7e375fd0c8d4
---

# Community Group Essentials{#community-group-essentials}

The community groups feature is the ability for a sub-community to be dynamically created within a community site by authorized users from the publish and author environments.

As of Communities [feature pack 1](/help/communities/using/deploy-communities.md#latestfeaturepack), it is possible for groups to be nested within other groups

## Essentials for Client-Side {#essentials-for-client-side}

### Community Groups Member List {#community-groups-member-list}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/group/components/hbs/communitygroupmemberlist</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.communitygroups</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/group/components/hbs/communitygroupmemberlist/communitygroupmemberlist.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/group/components/hbs/communitygroupmemberlist/clientlibs/memberList.css</td> 
  </tr>
  <tr>
   <td><strong>properties</strong></td> 
   <td>see <a href="../../communities/using/creating-groups.md">Community Group</a></td> 
  </tr>
 </tbody>
</table>

### Community Groups {#community-groups}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/group/components/hbs/communitygroups</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.communitygroups</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/group/components/hbs/communitygroups/communitygroups.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/group/components/hbs/communitygroupmemberlist/clientlibs/communitygroups.css</td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](/help/communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Community Group API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/group/client/api/package-summary.html)

* [Community Group Endpoints](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/group/client/endpoints/package-summary.html)

* [Server-side Customizations](/help/communities/using/server-customize.md)

### Groups Function {#groups-function}

A community site structure that includes a [Groups function](/help/communities/using/functions.md#groups-function) will support the creation of new `community groups` from the publish and author environments. The community group created will include a `community groups member list` component that will list the members of the group.

One or more [community group templates](/help/communities/using/tools-groups.md), which provide the design of the community group page(s), may be configured for the Groups function when the function is being added to a [community site template](/help/communities/using/sites.md) or nested within a community group template.

The inclusion of multiple community group templates results in a choice of design being presented to the authorized user at the time a new community group is created for the community site, as shown in the section on [community groups](/help/communities/using/creating-groups.md) for authors.

### Nested Groups {#nested-groups}

As of Communities [FP1](/help/communities/using/deploy-communities.md#latestfeaturepack), it is possible for a Groups function to be included within a group template, thus allowing for nested groups (sub-communities).

When a community site or group template includes the Groups function, it is possible to

* create a sub-community in the author environment
* create a group in the publish environment, when configured to allow it

When creating a group in the author environment, it is necessary to first publish the community site, and then to publish the group. Publishing the community site will publish the pages of the group, without creating the sub-community's member groups to which ACLs are set. Thus, a restricted (secret) group may be visible until the group is explicitly published.

## Links and Related Information {#links-and-related-information}

* [Managing Users and User Groups](/help/communities/using/users.md)
* [Communities Groups Console](/help/communities/using/groups.md)
* [Groups Function](/help/communities/using/functions.md#groups-function)
* [Group Templates](/help/communities/using/tools-groups.md)

