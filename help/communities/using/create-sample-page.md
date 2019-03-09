---
title: Create a Sample Page
seo-title: Create a Sample Page
description: Create a Sample community site
seo-description: Create a Sample community site
uuid: 68c79289-8980-4711-a63b-395dfb92b9f1
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: developing
discoiquuid: 6e0438cb-a82b-4312-8bf3-c16f694eaa95
---

# Create a Sample Page{#create-a-sample-page}

As of AEM 6.1 Communities, the easiest way to create a sample page is to create a simple community site, consisting simply of a Page function.

This will include a parsys component so that you can [enable components for authoring](../../communities/using/basics.md#accessing-communities-components).

Another option for exploratoin with sample components is to use the features presented in the [Community Components Guide](../../communities/using/components-guide.md).

## Create a Community Site {#create-a-community-site}

This is very similar to creating a new site described in [Getting Started with AEM Communities](../../communities/using/getting-started.md).

The major difference is this tutorial will create a new community site template that only contains the [Page function](../../communities/using/functions.md#page-function) in order to create a simple community site free of other features (other than the pre-wired features basic to all community sites).

### Create New Site Template {#create-new-site-template}

To get started, create a simple [community site template](../../communities/using/sites.md).

From global navigation on an author instance select **Tools, Communities,** **Site Templates**.

![](assets/chlimage_1-82.png)

* select `Create button`
* BASIC INFO

    * `Name`: Single Page Template
    * `Description`: A template consisting of a single Page function.
    * select `Enabled`

![](assets/chlimage_1-83.png)

* STRUCTURE

    * drag a `Page`function to the Template Builder
    * for Configuration Function Details, enter

        * `Title`: Single Page
        * `URL`: page

![](assets/chlimage_1-84.png)

* select **`Save`**for the configuration
* select **`Save`**for the site template

### Create New Community Site {#create-new-community-site}

Now create a new community site based on the simple site template.

After creating the site template, from global navigation select **Communities**, **Sites**.

![](assets/chlimage_1-85.png)

* select**`Create`** `icon`

* step `1 - Site Template`

    * `Title`: Simple Community Site
    * `Description`: A Community Site consisiting of a single page for experimentation.
    * `Community Site Root :* (leave blank)*`
    * `Community Site Base Language : English`
    * `Name`: sample

        * url = http://localhost:4502/content/sites/sample

    * `Template`: choose `Single Page Template`

![](assets/chlimage_1-86.png)

* select `Next`
* step `2 - Design`

    * select any design

* select `Next`
* select `Next`  
  (accept all default Settings)

* select `Create`

![](assets/chlimage_1-87.png)

## Publish the Site {#publish-the-site}

![](assets/chlimage_1-88.png)

From the [community sites console](../../communities/using/sites-console.md), select the publish icon to publish the site, by default to http://localhost:4503.

## Open the Site on Author in Edit Mode {#open-the-site-on-author-in-edit-mode}

![](assets/chlimage_1-89.png)

Select the open site icon to view the site in edit mode.

The URL will be [http://localhost:4502/editor.html/content/sites/sample/en.html](http://localhost:4502/editor.html/content/sites/sample/en.html)

![](assets/chlimage_1-90.png)

On the simple home page it is possible to see what is pre-wired through the community functions and templates, and play with adding and configuring community components.

## View Site on Publish {#view-site-on-publish}

After publishing the page, open the page on the [publish instance](http://localhost:4503/content/sites/sample/en.html) to experiment with the features as an anonymous site visitor, signed in member, or an administrator. The Administration link visible in the author environement will not appear in the publish environment unless an administrator signs in.
