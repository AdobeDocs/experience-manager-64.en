---
title: Initial Setup for Enablement
seo-title: Initial Setup
description: null
seo-description: Initial Setup for Enablement
uuid: a7bd3771-ba7a-4978-9e88-04f97ebd2920
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: ba65ab71-74c8-4a42-b28b-a1626e565697
index: y
internal: n
snippet: y
---

# Initial Setup for Enablement{#initial-setup-for-enablement}

|   |** [Author a New Community Site for Enablement ⇒](../../communities/using/enablement-create-site.md)** |
|---|---|

## Start Author and Publish Instances {#start-author-and-publish-instances}

For development and demonstration purposes, it will be necessry to run one author and one publish instance.

Follow the basic AEM [Getting Started](../../sites/deploying/using/deploy.md#gettingstarted) instructions which will result in

* author environment on [localhost:4502](http://localhost:4502/)
* publish environment on [localhost:4503](http://localhost:4503/)

For AEM Communities,

* the author environment is for

    * development of sites, templates, components, enablement resources and learning paths
    * assignment of members and groups of members to enablement resources and learning paths
    * generating reports on assignments, views, and posts
    * administrative and configuration tasks

* the publish environment is for

    * learning/training based on topics managed by the Enablement Manager
    * commenting and rating enablement resources and learning paths
    * getting in touch with the resource contacts

>[!NOTE]
>
>If not familiar with AEM, view the documentation on [basic handling](../../sites/authoring/using/basic-handling.md) and a [quick guide to authoring pages](../../sites/authoring/using/qg-page-authoring.md).

## Install Latest Communities Release {#install-latest-communities-release}

This tutorial creates an [enablement community site](../../communities/using/overview.md#enablementcommunity). To ensure the latest feature pack is installed, visit :

* [Latest Releases](../../communities/using/deploy-communities.md#latestreleases)

For a tutorial that creates an [engagement community site](../../communities/using/overview.md#engagementcommunity), visit [Getting Started with AEM Communities](../../communities/using/getting-started.md).

## Configure Enablement Features {#configure-enablement-features}

To follow this tutorial, it is necessary to correctly install and [configure enablement](../../communities/using/enablement.md), which requires third-party products, such as MySQL and FFmpeg.

## Configure Analytics {#configure-analytics}

When [Adobe Analytics is configured for the community site](../../communities/using/analytics.md), more information is available in the [reports](../../communities/using/reports.md) generated on enablement resources and learning paths assigned to community members (learners).

## Configure Email for Notifications {#configure-email-for-notifications}

The notifications feature, available by default for all sites created using the `Communities Sites` console, provides an email channel for notifications.

What is necessary is for email to be properly configured for the site.

See [Configuring Email](../../communities/using/email.md).

## Enable the Tunnel Service {#enable-the-tunnel-service}

When creating a community site in the author environment, the tunnel service makes possible the ability to create and manage users and user groups registered in the publish environment (members), assign roles to trusted community members, and assign content to learners.

For more information see [Managing Users and User Groups](../../communities/using/users.md).

For simple instructions to enable the tunnel service, see [Tunnel Service](../../communities/using/deploy-communities.md#tunnelserviceonauthor).

## Create Tutorial Tags {#create-tutorial-tags}

Create tags to use for the engage and enablement tutorials, using the tag namespace of `Tutorial`.

Use the [Tagging console](../../sites/administering/using/tags.md#taggingconsole) to create the following tags :

* `Tutorial : Sports / Baseball`
* `Tutorial : Sports / Gymnastics`
* `Tutorial : Sports / Skiing`
* `Tutorial : Arts / Visual`
* `Tutorial : Arts / Auditory`
* `Tutorial : Arts / History`

![](assets/chlimage_1-429.png)

Then follow the instructions to

1. [set the tag permissions](../../sites/administering/using/tags.md#settingtagpermissions)
1. [publish the tags](../../sites/administering/using/tags.md#publishingtags)

Sample package of tags created for the AEM Communities Getting Started Tutorials

[Get File](assets/communities_tutorialtags-10.zip)

## Create Enablement Members and Groups {#create-enablement-members-and-groups}

For an enablement community site, site visitors should not be able to [self-register nor use social login](../../communities/using/sites-console.md#usermanagement).

Instead, with the [tunnel service](#enablethetunnelservice) enabled, the [Members console](../../communities/using/members.md) is used to register new members in the publish environment.

In this tutorial, three members are created in the publish environment. Two members will be become members of a user group that is assigned to a learning path, while the third member will become an enablement resource contact.

A fourth user is created in the author environment and assigned the roles of Communities Administrator and Community Enablement Manager.

>[!NOTE]
>
>These members are being created prior to creation of the *Enablement Tutorial* community site.
>
>If they were created afterwards, they could be added as members of the *Enablement Tutorial members group* during member creation.
>
>Instead, later, they'll be [assigned to the members group](../../communities/using/enablement-create-site.md#assignuserstocommunityenablemembersgroup).

#### Riley Taylor - Enrollee {#riley-taylor-enrollee}

[Create a member](../../communities/using/members.md#createnewmember) who will be added to a group of Learners - the Community Ski Class group.

* **ID** : riley
* **Email **: riley.taylor@mailinator.com
* **Password **: password
* **Confirm Password** : password
* **First Name** : Riley
* **Last Name **: Taylor

#### Sidney Croft - Enrollee {#sidney-croft-enrollee}

[Create a second member](../../communities/using/members.md#createnewmember) who will be added to the Community Ski Class group.

* **ID** : sidney
* **Email **: sidney.croft@mailinator.com
* **Password **: password
* **Confirm Password** : password
* **First Name** : Sidney
* **Last Name **: Croft

#### Quinn Harper - Enablement Resource Contact and Moderator {#quinn-harper-enablement-resource-contact-and-moderator}

[Create a member](../../communities/using/members.md#createnewmember) who will be added to the Community Site's member group once the site has been created. This membership will allow the member to be assigned as the enablement [Resource Contact](../../communities/using/resources.md#3settings) when an enablement resource is created for the site.

* **ID** : quinn
* **Email **: quinn.harper@mailinator.com
* **Password **: password
* **Confirm Password** : password
* **First Name** : Quinn
* **Last Name **: Harper

#### Add a User Group - Community Ski Class {#add-a-user-group-community-ski-class}

[Add a new group](../../communities/using/members.md#createnewgroup) named Community Ski Class.

* **ID **: community-ski-class
* **Name** : Community Ski Class
* **Description **: a sample group for assigning enablement resources
* **Add Members To Group** - add :

    * riley
    * sidney

* select **Save**

#### Community Ski Class properties {#community-ski-class-properties}

![](assets/chlimage_1-430.png)

>[!NOTE]
>
>During creation of the community site, existing members and groups may be added to the community site's members group.

## Community Administrator Role {#community-administrator-role}

Members of the Community Administrators group are able to create community sites, manage sites, manage members (they can ban members from the community), and moderate content.

#### Create User {#create-user}

Create a user on *author*, who is assigned the role of Community Administrator :

* on the author instance

    * for example, [http://localhost:4502/](http://localhost:4503/)

* sign in with administrator privileges

    * for example, username 'admin' / password 'admin'

* from the main console, navigate to **Tools, Operations, Security, Users**
* from the **Edit **menu, select **Add User**

* in the `Create New User` dialog enter

    * **ID&#42;** : sirius
    * **Emai Address** : sirius.nilson@mailinator.com
    * **Password&#42;** : password
    * **Confirm Password&#42;** : password
    * **First Name** : Sirius
    * **Last Name&#42;** : Nilson

#### Assign Sirius to Community Administrators Group {#assign-sirius-to-community-administrators-group}

Scroll down to `Add User to Groups` :

* enter 'C' to search

    * select `Community Administrators`
    * select `Community Enablement Managers`

* select **Save**

![](assets/chlimage_1-431.png)

|   |** [Author a New Community Site for Enablement ⇒](../../communities/using/enablement-create-site.md)** |
|---|---|

