---
title: Experience the Published Site
seo-title: Experience the Published Site
description: Browse to a published site for enablement
seo-description: Browse to a published site for enablement
uuid: 6dd9b97c-1d54-4d19-b4fb-699f5e62ca19
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: f5fff179-c166-4525-92c0-3d71374f8168
index: y
internal: n
snippet: y
---

# Experience the Published Site{#experience-the-published-site}

| ** [⇐ Create and Assign Enablement Resources](../../communities/using/resource.md)** |  |
|---|---|

## Browse to New Site on Publish {#browse-to-new-site-on-publish}

Now that the newly created community site and its enablement resources and learning path have been published, it is possible to experience the Enablement Tutorial site.

Begin by browsing to the URL displayed when creating the site, but on the publish server, e.g.

* author URL = [http://localhost:4502/content/sites/enable/en.html](http://localhost:4502/content/sites/enable/en.html)
* publish URL = [http://localhost:4503/content/sites/enable/en.html](http://localhost:4503/content/sites/enable/en.html)

If the [default home page was set](../../communities/using/enablement-create-site.md#changethedefaulthomepage), then simply browsing to [http://localhost:4503/](http://localhost:4503/) should launch the site.

When first arriving at the published site, the site visitor would typically not already be signed in and would be anonymous.

#### http://localhost:4503/content/sites/enable/en.html {#http-localhost-content-sites-enable-en-html}

![](assets/chlimage_1-433.png) 

## Anonymous Site Visitor {#anonymous-site-visitor}

An anonymous site visitor is immediately presented with the login page for this private enablement community site. Note that there is no option to self-register nor login with Facebook or Twitter.

Notice this  home page  shows four menu items: `Assignments, Ski Catalog, What's New` and `Discussions`, but none may be reached without signing in.

>[!NOTE]
>
>It is possible to grant anonymous access to an enablement site without allowing site visitors to self-register.  
>If an enablement resource is set to `show in catalog` and `allow anonymous access`, it will be possible for anonymous site visitors to view resources in the catalog.

### Prevent anonymous access on JCR {#prevent-anonymous-access-on-jcr}

A known limitation exposes the community site content to anonymous visitors through  jcr  content and  json , though **allow anonymous access** is disabled for the site's content. However, this behavior can be controlled using Sling Restrictions as a workaround.

To protect your community site's content from access by anonymous users through  jcr  content and  json , follow these steps:

1. On AEM Author instance, go to http://&lt;host&gt;:&lt;port&gt;/editor.html/content/site/&lt;sitename&gt;.html.

   >[!NOTE]
   >
   >Do not go to the localized site.

1. Go to **Page Properties**.

   ![](assets/page-properties-1.png)

1. Go to **Advanced** tab.
1. Enable **Authentication Requirement**.

   ![](assets/site-authentication-1.png)

1. Add the path of the login page. For example, **/content/......./GetStarted**.
1. Publish the page.

## Enrolled Member {#enrolled-member}

This experience relies on users `Riley Taylor` and `Sidney Croft` being [created](../../communities/using/enablement-setup.md#publishcreateenablementmembers) and [assigned](../../communities/using/resource.md#settings) to the *Ski Lessons* learning path through their membership in the *Community Ski Class* group.

Login with

* username : riley
* password : password

If the user profile was not created through self-registration, the very first time a member signs in, their Profile page is displayed so they may verify and modify it as necessary.

The next time the member signs in, the home page, identified by the first menu item, is displayed.

![](assets/chlimage_1-434.png) 

### Assignments {#assignments}

The Assignments page is where the member is shown all of the learning paths and enablement resources assigned specifically to them.

Each assignment provides basic information as to

* the type of Assignment
* whether it is a new Assignment
* the name
* details relevant for the type of Assignment
* Assignment contact, expert, and author (if provided)

The type of Assignment is indicated by an icon in the upper left corner of the card. The image of a road is for a learning path with the number of included enablement resources.

![](assets/chlimage_1-435.png)

Selecting *Ski Lessons* will display the two enablement resources referenced by the learning path.

![](assets/chlimage_1-436.png)

Selecting *Ski Lesson 1* will open the enablement resource's details page.

From the details page, the member is able to learn, [rate](../../communities/using/rating.md) the lesson and add [comments](../../communities/using/comments.md). Any member activity will be reflected in the What's New section of the site.

Interactions with the enablement resource will be noted in the Report section accessible in the author environment.

![](assets/chlimage_1-437.png) 

### Ski Catalog {#ski-catalog}

The Ski Catalog page is the catalog of enablement resources tagged with tags from the `Tutorial` namespace. The two *Ski Lesson* resources are tagged with the `Skiing` tag, such that if any tags other than `All` or `Tutorial: Sports / Skiing` is selected, nothing is displayed.

When a member has not been assigned enablement resources, either directly or through a learning path, it is possible to interact with enablement resources located within a catalog and provide feedback through comments and ratings.

![](assets/chlimage_1-438.png) 

### Discussions {#discussions}

In addition to rating and commenting on enablement resources ([when enabled](../../communities/using/enablement-create-site.md#step33asettings)), the community site template from which `Enablement Tutorial` was created includes the [forum function](../../communities/using/functions.md#forumfunction) (title is `Discussions)`.

Select the `Discussions`link and post a topic.

Log out and Log in as Sidney Croft (sidney / password) and reply to the question, as well as Follow the topic.

Notice, in addition to inline moderation, there are options to share the topic on social media or to email the topic.

![](assets/chlimage_1-439.png) 

### What's New {#what-s-new}

The `What's New` menu item is the title given the [activity stream function](../../communities/using/functions.md#activitystreamfunction) in this community site's structure.

Still signed in as Sidney, select the `What's New` link to show the activity.

![](assets/chlimage_1-440.png) 

## Trusted Community Member {#trusted-community-member}

This experience assumes ` [Quinn Harper](../../communities/using/enablement-setup.md#publishcreateenablementmembers)` was assigned the roles of [moderator](../../communities/using/enablement-create-site.md#moderation) and [resource contact](../../communities/using/resource.md#settings).

Login with

* username : quinn
* password : password

Once signed in, notice there is a new menu item, `Administration`, which appears because the member was given the role of moderator. 

![](assets/chlimage_1-441.png)

The home page is identified by the first menu item, Assignments. Quinn is the moderator and enablement resource contact and was not enrolled in any enablement resources or learning paths, and so there is nothing to display.

### Administration {#administration}

What there is, is activity by the two learners, `Riley Taylor` and `Sidney Croft. By s`electing the `Administration`link to access the Moderation Console, Quinn is able to use the [bulk moderation console](../../communities/using/moderation.md) to moderate their posts.

Selecting the side-panel icon toggles open the filters used to search community content.

Hovering over a comment card displays moderation actions.

![](assets/chlimage_1-442.png) 

## Reports on Author {#reports-on-author}

There are two ways to access reporting on learners and enablement resources.

On author, navigate to the **Communities, [Resources console](../../communities/using/resources.md)**, where the enablement resources are managed, and after selecting a community site, it is possible to generate reports for

* all enablement resources and learning paths
* one specific enablement resource or learning path

Navigate to the **Communities, [Reports console](../../communities/using/reports.md)**, and generate reports according to

* assignments to enablement resources and learning paths
* posts to a community site over a specific period
* views (site visits) of a community site over a specific period

* posts and views may be to all content, or to specific content :

    * Forum
    * Forum Topic
    * QnA
    * QnA Question
    * Blog
    * Blog Article
    * Calendar
    * Calendar Event

### Resources Console {#resources-console}

With a little activity and interaction with the Resources on publish, viewing the reports on author is worth a look.

* on author
* sign in with administrative privileges
* navigate from the main menu to **Communities &gt; Resources**
* select the `Enablement Tutorial` site
* select the `Report`icon for a summary of all Resources
* select a Resource and then the `Report`icon for a report on that Resource

Notice that it is likely too soon to show data from Adobe Analytics, which can take from 1 to 12 hours to appear. However, basic SCORM reporting is already available.

#### Ski Lessons Resource Report {#ski-lessons-resource-report}

![](assets/chlimage_1-443.png) 

#### Ski Lessons User Report {#ski-lessons-user-report}

* select **Communities**, **Resources**

* open card `Enablement Tutorial`
* open card `Ski Lessons`
* `select Report, User Report`

![](assets/chlimage_1-444.png) 

### Reports Console {#reports-console}

The Reports console allows for generation of reports on

* **Assignments** for any enablement community site
* **Views** for any community site
* **Posts** for any community site

For reports on assignments :

* on author
* sign in with administrative privileges
* navigate to **Communities, Reports, Assignments Report**
* select a **Site **from the pull-down menu (select `Enablement Tutorial`)

* select **Group** (select `Community Ski Class`)

* select an **Assignment **(select `Ski Lessons`)

* select **Generate**

![](assets/chlimage_1-445.png)

For reports on views :

* on author
* sign in with administrative privileges
* navigate to **Communities, Reports, Views Report**
* select a **Site **from the pull-down menu (select `Enablement Tutorial`)

* select **Content Type** (select `all`)

* select a **date range** (select `Last 7 days`)

* select **Generate**

![](assets/chlimage_1-446.png)

| ** [⇐ Create and Assign Enablement Resources](../../communities/using/resource.md)** |  |
|---|---|

