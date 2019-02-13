---
title: Experience the Published Site
seo-title: Experience the Published Site
description: Browse to a published site
seo-description: Browse to a published site
uuid: 7f517098-1e7a-4b59-9d45-8c50f7300169
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 59f3f0a9-6785-4a8f-96e8-3a8bc098db19
index: y
internal: n
snippet: y
---

# Experience the Published Site{#experience-the-published-site}

| ** [⇐ Author a New Community Site](../../communities/using/create-site.md)** |** [Authoring Nested Groups ⇒](../../communities/using/nested-groups.md)** |
|---|---|

## Browse to New Site on Publish {#browse-to-new-site-on-publish}

Now that the newly created communities site has been published, browse to the URL displayed when creating the site, but on the publish server, e.g.

* author URL = http://localhost:4502/content/sites/engage/en.html
* publish URL = http://localhost:4503/content/sites/engage/en.html

To minimize confusion as to which member is signed in on author and publish, it is suggested to use different browsers for each instance.

When first arriving at the published site, the site visitor would typically not already be signed in and would be anonymous.

#### http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![](assets/chlimage_1-311.png) 

## Anonymous Site Visitor {#anonymous-site-visitor}

An anonymous site visitor sees the following in the UI:

* Title of the site. Which is Getting Started Tutorial
* no profile link
* no messages link
* no notifications link
* search field
* Log in link
* The brand banner
* Menu links for the components included in the Reference Site Template

If you select various links, you will find they are in read-only mode.

### Prevent anonymous access on JCR {#prevent-anonymous-access-on-jcr}

A known limitation exposes the community site content to anonymous visitors through  jcr  content and  json , though **allow anonymous access** is disabled for the site's content. However, this behavior can be controlled using Sling Restrictions as a workaround.

To protect your community site's content from access by anonymous users through  jcr  content and  json , follow these steps:

1. On AEM Author instance, go to http://&lt;host&gt;:&lt;port&gt;/editor.html/content/site/&lt;sitename&gt;.html.

   >[!NOTE]
   >
   >Do not go to the localized site.

1. Go to **Page Properties**.

   ![](assets/site-authentication.png)

1. Go to **Advanced **tab.

   ![](assets/page-properties.png)

1. Enable **Authentication Requirement**.
1. Add the path of the login page. For example,** /content/......./GetStarted**.
1. Publish the page.

## Trusted Community Member {#trusted-community-member}

This experience assumes [Aaron McDonald](../../communities/using/tutorials.md#demousers) was assigned the roles of [community manager and moderator](../../communities/using/create-site.md#roles). If not, return to the author environment to [modify the site settings](../../communities/using/sites-console.md#modifyingsiteproperties) and select Aaron McDonald as both community manager and moderator.

In the upper right corner, select `Log in`, and sign with username "aaron.mcdonald@mailinator.com" and password "password". Notice the ability to sign in with Twitter or Facebook credentials.

![](assets/chlimage_1-312.png)

Once signed in, notice there is a new menu item, `Administration`, which appears because the member was given the role of Moderator. Now selecting various links is more interesting.

![](assets/chlimage_1-313.png)

Notice the Calendar page is the home page because the chosen Reference Site Template included the Calendar function first, followed by Activity Stream function, Forum function, and so on. This structure is visible from the [Site Template](../../communities/using/sites.md#editsitetemplate) console or when modifying site properties in the author environment :

![](assets/chlimage_1-314.png)

>[!NOTE]
>
>For more information on Communities components and functions, visit
>
>* [Communities Components](../../communities/using/author-communities.md) (for authors)
>* [Component, Function, and Feature Essentials](../../communities/using/essentials.md) (for developers)
>

### Forum link {#forum-link}

View the basic forum feature by selecting the Forum link.

Members are able to post a new topic or follow a topic.

Site visitors are able to view posts and sort them in various ways.

![](assets/chlimage_1-315.png) 

### Groups link {#groups-link}

Since Aaron is a group administrator, selecting the Groups link will allow Aaron to create a new community group by selecting a group template, image, whether the group is open or secret, and inviting members.

This is an example where a group is created in the publish environment.

Groups may also be created in the author environment and managed within the community site in the author environment (the [Community Groups console](../../communities/using/groups.md)). The experience of [creating groups on author](../../communities/using/nested-groups.md) is next in this tutorial.

![](assets/chlimage_1-316.png)

Create a Reference Group :

1. select **New Group**
1. **Settings tab**

    * Group Name : `Sports`
    * Description : `A parent group for various sporting groups`
    * Group URL Name : `sports`
    * select `Open Group` (allow any community member to participate by joining)

1. **Template tab**

    * select `Reference Group` (contains a groups function in its structure to allow nested groups)

1. select **Create Group**

![](assets/chlimage_1-317.png)

After new group is created, **select the new Sports group** in order to create two groups (nested) within it. As a site structure can not begin with the groups function, after opening the Sports group, it is necessary to select the Groups link :

![](assets/chlimage_1-318.png)

The second set of links, beginning with `Blog`, belong to the currently selected group, the `Sports`group. By selecting the Sports' `Groups` link, it is possible to nest two groups within the Sports group.

As an example, add two n `ew groups.`

* one named `Baseball`

    * leave it set as an `Open Group` (required membership)
    * on Templates tab, select `Conversational Group`

* one named `Gymnastics`

    * change its setting to `Member Only Group` (restricted membership)
    * on Templates tab, select `Conversational Group`

**Notice **:

* a refresh of the page may be necessary before both groups are displayed
* this template does *not *include the groups function, so no further nesting of groups will be possible
* on author, the [Groups console](../../communities/using/groups.md) provides a third choice - a `Public Group` (optional membership)

Once both groups are created, select the Baseball group, an open group, and notice its links :

`Discussions` `What's New` `Members`

The group's links are displayed below the main site's links and results in the following display :

![](assets/chlimage_1-319.png)

On author - with administrative privileges, navigate to the [Communities Groups console](../../communities/using/members.md) and add Weston McCall to the `Community Engage Gymnastics <uid> Members` group.

Continuing on publish, log out as Aaron McDonald, and view the groups in the Sports Group as an anonymous site visitor :

* from home page 
* select `Groups`link
* select `Sports`link
* select the Sports' `Groups`link

Only the Baseball group will be visible.

Log in as Weston McCall (weston.mccall@dodgit.com / password), and navigate to the same location. Notice that Weston is able to `Join` the open `Baseball` group and either `enter or Leave` the private `Gymnastics`group.

![](assets/chlimage_1-320.png) 

### Web Page link {#web-page-link}

View the basic web page included in the site by selecting the Web Page link. The standard AEM authoring tools may be used to add content to this page in the author environment.

For example, go to **author** instance, open the `engage` folder in the [Communities Sites console](../../communities/using/sites-console.md), select the **Open Site** icon to enter author edit mode. Then select preview mode to select the `Web Page`link, then select edit mode to add Title and Text components. Last, re-publish either just the page or the entire site.

![](assets/chlimage_1-321.png) 

### Administration Link {#administration-link}

When the community member has moderation privileges, then the Administration link will be visible and selecting it will display the community content posted and allow it to be [moderated](../../communities/using/moderate-ugc.md) in a manner similar to the [moderation console](../../communities/using/moderation.md) in the author environment.

Use the browser's back button to return to the published site. Most consoles are not accessible from global navigation in the publish environment. [](../../communities/using/moderate-ugc.md)

![](assets/chlimage_1-322.png) 

## Self-Registration {#self-registration}

After logging out, it is possible to create a new user registration.

* select `Log In`
* select `Sign up for a new account`

![](assets/chlimage_1-323.png) ![](assets/chlimage_1-324.png)

By default, the email address is the login id. If unchecked, the visitor is able to enter their own login id (user name). The user name must be unique in the publish environment.

After specifying the user's name, email, and password, selecting `Sign Up`will create the user and enable them to sign.

Once signed in, the first page presented is their `Profile`page, which they can personalize.

![](assets/chlimage_1-325.png)

If the member forgets their login id, it is possible to recover is using their email address.

![](assets/chlimage_1-326.png)

| ** [⇐ Author a New Community Site](../../communities/using/create-site.md)** |** [Authoring Nested Groups ⇒](../../communities/using/nested-groups.md)** |
|---|---|

