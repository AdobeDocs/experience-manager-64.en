---
title: Initial Setup
seo-title: Initial Setup
description: Setting up Communities
seo-description: Setting up Communities
uuid: c53d280c-c5ae-47cf-8038-f0dea68e15ff
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 0d462ad1-5619-4bb6-9609-bc8987c40a0c
---

# Initial Setup{#initial-setup}

|   |** [Author a New Community Site ⇒](/help/communities/create-site.md)** |
|---|---|

## Start Author and Publish Instances {#start-author-and-publish-instances}

For development and demonstration purposes, it will be necessary to run one author and one publish instance.

To do so, follow the basic AEM [Getting Started](/help/sites-deploying/deploy.md#getting-started) instructions, which will result in

* author environment on [localhost:4502](http://localhost:4502/)
* publish environment on [localhost:4503](http://localhost:4503/)

For AEM Communities,

* the author environment is for

    * development of sites, templates and components
    * administrative and configuration tasks

* the publish environment is for

    * the community experience of posting and moderating content
    * creating community groups, members and member groups

>[!NOTE]
>
>If not familiar with AEM, view the documentation on [basic handling](/help/sites-authoring/basic-handling.md) and a [quick guide to authoring pages](/help/sites-authoring/qg-page-authoring.md).

## Install Latest Communities Release {#install-latest-communities-release}

This tutorial creates an [engagement community site](/help/communities/overview.md#engagement-community) and is based on AEM Communities 6.2 feature pack version 1.10.

To ensure the latest feature pack is installed, visit:

* [Latest Releases](/help/communities/deploy-communities.md#latest-releases)

For a tutorial that creates an [enablement community site](/help/communities/overview.md#enablement-community), visit [Getting Started with AEM Communities for Enablement](/help/communities/getting-started-enablement.md).

## Configure Analytics {#configure-analytics}

When [Adobe Analytics is configured for the community site](/help/communities/analytics.md), information on community activity is available that enhances the community member's experience as well as provides feedback to administrators of the site.

Integration with Adobe Analytics is optional.

## Configure Email for Notifications {#configure-email-for-notifications}

The notifications feature, available by default for all sites created using the `Communities Sites` console, provides an email channel for notifications.

What is necessary is for email to be properly configured for the site.

See [Configuring Email](/help/communities/email.md).

## Enable the Tunnel Service {#enable-the-tunnel-service}

When creating a community site in the author environment, the tunnel service makes possible the ability to assign roles to trusted community members registered in the publish environment. The tunnel service also allows access to community members from the [Members and Groups consoles](/help/communities/members.md) in the author environment.

The convention is for members and member groups created in the publish environment to *not *be recreated in the author environment. For more information see [Managing Users and User Groups](/help/communities/users.md).

For simple instructions to enable the tunnel service on an **author** instance, see [Tunnel Service](/help/communities/deploy-communities.md#tunnel-service-on-author).

## Community Administrator Role {#community-administrator-role}

Members of the Community Administrators group are able to create community sites, manage sites, manage members (they can ban members from the community), and moderate content.

### Create User {#create-user}

Create a user on *author*, who is assigned the role of Community Administrator:

* on the author instance

    * for example, [http://localhost:4502/](http://localhost:4503/)

* sign in with administrator privileges

    * for example, username 'admin' / password 'admin'

* from the main console, navigate to **Tools, Operations, Security, Users**
* from the **Edit **menu, select **Add User**

* in the `Create New User` dialog enter

    * **ID&#42;**: sirius
    * **Emai Address**: sirius.nilson@mailinator.com
    * **Password&#42;**: password
    * **Confirm Password&#42;**: password
    * **First Name**: Sirius
    * **Last Name&#42;**: Nilson

### Assign Sirius to Community Administrators Group {#assign-sirius-to-community-administrators-group}

Scroll down to `Add User to Groups`:

* enter 'C' to search

    * select `Community Administrators`
    * select `Community Enablement Managers`

* select **Save**

![](assets/chlimage_1-301.png)

## Enable Social Login {#enable-social-login}

Before the demonstration versions of social login with Facebook and Twitter may be used, it is necessary to

1. install a fix pack or [latest feature pack](/help/communities/deploy-communities.md#latestfeaturepack) (for March 2017 Facebook API changes)
1. [enable the OAuth provider](/help/communities/social-login.md#adobe-granite-oauth-authentication-handler) in the publish environment

For production servers, it is necessary to create the cloud services necessary to provide social login.

See [Social Login with Facebook and Twitter](/help/communities/social-login.md).

## Create Tutorial Tags {#create-tutorial-tags}

Create tags to use for the engage and enablement tutorials, using the tag namespace of `Tutorial`.

Use the [Tagging console](/help/sites-administering/tags.md#tagging-console) to create the following tags:

* `Tutorial: Sports / Baseball`
* `Tutorial: Sports / Gymnastics`
* `Tutorial: Sports / Skiing`
* `Tutorial: Arts / Visual`
* `Tutorial: Arts / Auditory`
* `Tutorial: Arts / History`

![](assets/chlimage_1-302.png)

Then follow the instructions to

1. [set the tag permissions](/help/sites-administering/tags.md#setting-tag-permissions)
1. [publish the tags](/help/sites-administering/tags.md#publishing-tags)

Sample package of tags created for the AEM Communities Getting Started Tutorials

[Get File](assets/tutorial_tags-v63.zip)

## MongoDB for UGC Common Store {#mongodb-for-ugc-common-store}

It is recommended, but optional, to set [MSRP](/help/communities/msrp.md) (MongoDB) as the [common store](/help/communities/working-with-srp.md) to experience the flexibility of moderating all UGC from either publish and/or author environments.

For instructions visit [How to Setup MongoDB for Demo](/help/communities/demo-mongo.md).

By default, the installation of the author and publish AEM instances result in user generated content (UGC) being stored in [JCR Tar storage](/help/sites-deploying/platform.md) which is accessed using [JSRP](/help/communities/jsrp.md). JSRP is not a common store, which means UGC is visible only on the instance on which it was entered. Typically, UGC is entered on a publish instance and would not be visible in the author environment, resulting in all moderation tasks needing to use the publish instance.

|   |** [Author a New Community Site⇒](/help/communities/create-site.md)** |
|---|---|
