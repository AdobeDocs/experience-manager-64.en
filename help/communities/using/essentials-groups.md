---
title: Community Group Essentials
seo-title: Community Group Essentials
description: Creating community sites dynamically
seo-description: Creating community sites dynamically
uuid: 292a5d76-1995-4a60-b992-c08f1e18798e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 08b8702b-0889-4e9f-8dd1-c5745f918ab0
---

# Community Group Essentials{#community-group-essentials}

The community groups feature is the ability for a sub-community to be dynamically created within a community site by authorized users from the publish and author environments.

As of Communities [feature pack 1](../../communities/using/deploy-communities.md#latestfeaturepack), it is possible for groups to be nested within other groups

## Essentials for Client-Side {#essentials-for-client-side}

#### Community Groups Member List {#community-groups-member-list}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
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

#### Community Groups {#community-groups}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
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

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Community Group API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/group/client/api/package-summary.md)

* [Community Group Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/group/client/endpoints/package-summary.md)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Groups Function {#groups-function}

A community site structure that includes a [Groups function](../../communities/using/functions.md#groups-function) will support the creation of new `community groups` from the publish and author environments. The community group created will include a `community groups member list` component that will list the members of the group.

One or more [community group templates](../../communities/using/tools-groups.md), which provide the design of the community group page(s), may be configured for the Groups function when the function is being added to a [community site template](../../communities/using/sites.md) or nested within a community group template.

The inclusion of multiple community group templates results in a choice of design being presented to the authorized user at the time a new community group is created for the community site, as shown in the section on [community groups](../../communities/using/creating-groups.md) for authors.

### Nested Groups {#nested-groups}

As of Communities [FP1](../../communities/using/deploy-communities.md#latestfeaturepack), it is possible for a Groups function to be included within a group template, thus allowing for nested groups (sub-communities).

When a community site or group template includes the Groups function, it is possible to

* create a sub-community in the author environment
* create a group in the publish environment, when configured to allow it

When creating a group in the author environment, it is necessary to first publish the community site, and then to publish the group. Publishing the community site will publish the pages of the group, without creating the sub-community's member groups to which ACLs are set. Thus, a restricted (secret) group may be visible until the group is explicitly published.

## Links and Related Information {#links-and-related-information}

* [Managing Users and User Groups](../../communities/using/users.md)
* [Communities Groups Console](../../communities/using/groups.md)
* [Groups Function](../../communities/using/functions.md#groups-function)
* [Group Templates](../../communities/using/tools-groups.md)

