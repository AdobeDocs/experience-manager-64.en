---
title: Site Templates
seo-title: Site Templates
description: How to access the Site Templates console
seo-description: How to access the Site Templates console
uuid: 2db488d4-b230-4e77-a72a-c8db4c1d7252
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 2f91e83d-0501-470f-9cfc-93d587d00d07
index: y
internal: n
snippet: y
---

# Site Templates{#site-templates}

The Site Templates console is very similar to the [Group Templates](../../communities/using/tools-groups.md) console, which is focused on functions of interest to Community groups.

>[!NOTE]
>
>The consoles for the creation of [community sites](../../communities/using/sites-console.md), [community site templates](../../communities/using/sites.md), [community group templates](../../communities/using/tools-groups.md) and [community functions](../../communities/using/functions.md) are for use only in the author environment.

## Site Templates Console {#site-templates-console}

In the author environment, to reach the community sites console

* from global navigation : **Tools, Communities, Site Templates**

This console displays the templates from which a [community site](../../communities/using/sites-console.md) can be created and allows new site templates to be created.

![](assets/chlimage_1-18.png)

## Create Site Template {#create-site-template}

To get started creating a new site template, select `Create`.

This will bring up the Site Editor panel which contains 3 sub-panels :

#### BASIC INFO {#basic-info}

![](assets/chlimage_1-19.png)

On the Basic Info panel, a name, description and whether the template is enabled or disabled are configured :

* **Community Site Template Name ** 
  the template name id

* **Community Site Template Description** 
  the template description

* **Disabled/Enabled** 
  a toggle switch controlling whether the template is referenceable

#### THUMBNAIL {#thumbnail}

![](assets/chlimage_1-20.png)

(Optional) Select the Upload Image icon in order to display a thumbnail along with the name and description to creators of community sites.

#### STRUCTURE {#structure}

![](assets/chlimage_1-21.png)

To add community functions, drag from the right side to the left in the order the site menu links should appear. Styles will be applied to the template during creation of the site.

For example, if you want a home page, drag the Page function from the library and drop under the template builder. This will result in the page configuration dialog opening. See the [functions console](../../communities/using/functions.md) for information about the configuration dialogs.

Continue dragging and dropping any other community functions desired for a community site based on this template.

The page function provides an empty page. The groups function provides the ability to create a group site (sub-community) within the community site.

>[!CAUTION]
>
>The groups function must *not *be the *first nor the only* function in the site structure.
>
>Any other function, such as the [page function](../../communities/using/functions.md#pagefunction), must be included and listed first.

![](assets/chlimage_1-22.png)

### Group Templates for Groups Function {#group-templates-for-groups-function}

When including a groups function in the site template, the configuration requires the specification of the group template choices allowed when a new group is created in the publish environment.

>[!CAUTION]
>
>The Groups function must *not *be the *first nor the only* function in the site structure.

![](assets/chlimage_1-23.png)

By selecting two or more community group templates, a choice is provided to the group administrator when actually creating a new group in the community.

![](assets/chlimage_1-24.png)

## Edit Site Template {#edit-site-template}

When viewing site templates in the main [Site Templates console](#sitetemplatesconsole), it is possible to select an existing site template for edit.

This process provides the same panels as [creating a site template](#createsitetemplate).
