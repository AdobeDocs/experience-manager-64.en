---
title: Authoring Nested Groups
seo-title: Authoring Nested Groups
description: Create nested groups
seo-description: Create nested groups
uuid: b478454a-24c6-4e1c-a6e0-afeb1bc4992c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 955a1876-4882-4926-82e9-846bc8bb332c
---

# Authoring Nested Groups{#authoring-nested-groups}

<!--One row table`| ** [⇐ Experience the Published Site](/help/communities/published-site.md)** |  |
|---|---|`-->

## Creating Groups on Author {#creating-groups-on-author}

On author, from global navigation

* select** Communities, Sites**
* select **engage folder** to open it
* select the card for the **Getting Started Tutorial** English site

    * select the card image
    * do *not* select an icon

The result is to reach the [Groups console](/help/communities/groups.md):

![](assets/chlimage_1-53.png)

The groups function will display as a folder in which instances of groups are created. Select the Groups folder to open it. The group created on publish is visible.

![](assets/chlimage_1-54.png)

## Create Main Arts Group {#create-main-arts-group}

This group can be created because the site structure for engage includes a groups function. The configuration of the function in the site's `Reference Template` defaults to allowing the selection of any enabled group template. Thus, the template chosen for this new group will be the `Reference Group`.

These consoles are very similar to the Communities Sites console.

* select **Create Group**
* `1 Community Group Template`:

    * Community Group Title: Arts
    * Community Group Description: A parent group for various arts groups.
    * Community Group Root: *leave as default*
    * Additional Available Community Group Language(s):use the pull down menu to select the available community group language(s). The menu displays all the language(s) in which the parent community site is created. Users can select among these languages to create groups in multiple locales in this single step. Same group gets created in multiple specified languages in the Groups console of the respective community sites.
    * Community Group Name: arts
    * Template: pull down to select `Reference Group`
    * `select Next`

![](assets/parenttonestedgroup.png)

Continue through the other panels with these settings:

* **2 Design**

    * you can change the design or allow to default to parent site's design
    * select **Next**

* **3 Settings**

    * **Moderation**

        * leave empty (inherit from parent site)

    * **Membership**

        * use default `Optional Membership`

    * **Thumbnail**

        * `*optional*`

    * `select Next`

* select **Create**

### Nesting Groups within Arts Group {#nesting-groups-within-arts-group}

The `groups` folder should now contain two groups (it may be necessary to refresh the page).

![](assets/createcommunitygroup.png)

#### Publish Group {#publish-group}

Before creating groups nested within the `arts`group, hover over the `arts` card and select the publish icon to publish it.

![](assets/chlimage_1-55.png)

Wait for confirmation that the group was published.

![](assets/chlimage_1-56.png)

The `arts` group should also contain a `groups` folder, but one that is empty and in which new groups can be created. Navigate to the arts group folder and create 3 nested groups, each with a different membership setting:

1. Visiual

    * Title: `Visual Arts`
    * Name: `visual`
    * Template: `Reference Group`
    * Membership: select `Optional Membership`  
      a public group, open to all members

1. Auditory

    * Title: `Auditory Arts`
    * Name: `auditory`
    * Template: `Reference Group`
    * Membership: select `Required Membership`  
      an open group, available for members to join

1. History

    * Title: `Art History`
    * Name: `history`
    * Template: `Reference Group`
    * Membership: select `Restricted Membership`  
      a secret group, visible only to invited members  
      as an example, invite [demo user](/help/communities/tutorials.md#demo-users) `emily.andrews@mailinator.com`

Refresh the page to see all three nested groups (sub-communities).

If necessary, to navigate to the nested groups from the Communities Sites console:

* select engage folder
* select Getting Started Tutorial card
* select Groups folder
* select arts card
* select Groups folder

![](assets/chlimage_1-57.png)

## Publishing Groups {#publishing-groups}

![](assets/chlimage_1-58.png)

After publishing the main community site, it is necessary to

* publish each group individually

    * waiting for confirmation that the group was published

* publish parent group before publishing any groups nested within

    * all groups must be published in a top-down fashion.

![](assets/chlimage_1-59.png)

## Experience on Publish {#experience-on-publish}

It is possible to experience the different groups when signed in, for example with the [demo users](/help/communities/tutorials.md#demo-users) used for

* Art/History group member: emily.andrews@mailinator.com/password

    * the restricted (secret) group, arts/history, will be visible
    * can see optional (public) groups
    * can join restricted (open) groups

* Group manager: aaron.mcdonald@mailinator.com/password

    * can see optional (public) groups
    * can join restricted (open) groups
    * will not see retricted (secret) groups

Access the Communities [Members and Groups consoles](/help/communities/members.md) on author to add other users to various member groups that correspond to the community groups.

<!--One row table`| ** [⇐ Experience the Published Site](/help/communities/published-site.md)** |  |
|---|---|`-->

