---
title: Tagging Enablement Resources
seo-title: Tagging Enablement Resources
description: Tagging of enablement resources allows for filtering of resources and learning paths as members browse catalogs
seo-description: Tagging of enablement resources allows for filtering of resources and learning paths as members browse catalogs
uuid: daf8a4f4-486b-498c-99e9-d1533a830e64
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: c012d639-c6e6-4f73-bbd8-78a4baa38c17
---

# Tagging Enablement Resources{#tagging-enablement-resources}

## Overview {#overview}

Tagging of enablement resources allows for filtering of resources and learning paths as members browse [catalogs](../../communities/using/functions.md#catalog-function).

Essentially:

* [create a tag namespace](../../sites/administering/using/tags.md#creating-a-namespace) for each catalog

    * [set tag permissions](../../sites/administering/using/tags.md#setting-tag-permissions)

        * for community members only (closed community)

            * allow read access for the [community site's member group](../../communities/using/users.md#publish-group-roles)

        * for any site visitor, whether signed-in or anonymous (open community)

            * allow read access for the `Everyone`group

    * [publish the tags](../../sites/administering/using/tags.md#publishing-tags)

* [define the scope of tags for a community site](../../communities/using/sites-console.md#tagging)

    * [configure catalogs that exist in the site's structure](../../communities/using/functions.md#catalog-function)

        * can add tags to the catalog instance to control the list of tags presented in the UI filters
        * can add [pre-filters](../../communities/using/catalog-developer-essentials.md#pre-filters), to restrict a catalog's included resources

* [publish the community site](../../communities/using/sites-console.md#publishing-the-site)
* [apply tags to enablement resources](../../communities/using/resources.md#create-a-resource) so they may be categorically filtered
* [publish the enablement resources](../../communities/using/resources.md#publish)

## Community Site Tags {#community-site-tags}

When creating or editing a community site, the [Tagging setting](../../communities/using/sites-console.md#tagging) sets the scope of tags available for features of the site by selecting a subset of existing tag namespaces.

While tags may be created and added to the community site at any time, it is recommended to design a taxonomy beforehand, similar to designing a database. See [Using Tags](../../sites/authoring/using/tags.md).

When later adding tags to an existing community site, it is necessary to save the edit before being able to add the new tag to a catalog function in the site's structure.

For a community site, after the site is published and the tags are published, it is necessary to enable read access to members of the community. See [Setting Tag Permissions](../../sites/administering/using/tags.md#setting-tag-permissions).

The following is how it appears in CRXDE when an administrator applies read permissions to `/etc/tags/ski-catalog` for the group `Community Enable Members`.

![](assets/chlimage_1-420.png)

## Catalog Tag Namespaces {#catalog-tag-namespaces}

The catalog feature uses tags to define itself. When configuring the catalog function in a community site, the set of tag namespaces to choose from are defined by the scope of tag nmespaces set for the community site.

The Catalog function includes a tag setting which defines the tags listed in the filter UI for the catalog. The setting "All Namespaces" refers to the scope of tag namespaces selected for the community site.

![](assets/chlimage_1-421.png)

## Applying Tags to Enablement Resources {#applying-tags-to-enablement-resources}

Enablement resources and learning paths will appear in all catalog when `Show in Catalog` is checked. Adding tags to resources and learning paths will allow for pre-filtering into specific catalogs as well as filtering in the catalog UI.

Restricting enablement resources and learning paths to specific catalogs is accomplished by creating [pre-filters](../../communities/using/catalog-developer-essentials.md#pre-filters).

The catalog UI allows for visitors to apply a tag filter to the list of resources and learning paths that appear in that catalog.

The administrator applying the tags to enablement resources must be aware of the tag namespaces associated with the catalogs, as well as the taxonomy in order to select a sub-tag for more refined categorization.

For example, if a `ski-catalog` namespace were created and set on a catalog named `Ski Catalog`, it might have two child tags: `lesson-1` and `lesson-2`.

Thus, any enablement resource tagged with one of:

* ski-catalog:
* ski-catalog:lesson-1
* ski-catalog:lesson-2

will appear in `Ski Catalog` after the enablement resource has been published.

![](assets/chlimage_1-422.png)

## Viewing Catalog on Publish {#viewing-catalog-on-publish}

Once everything has been setup from the author environment and published, the experience of using the catalog to find enablement resources can be experienced in the publish environment.

If no tag namespaces appear in the drop-down, ensure the permissions have been set properly in the publish environment.

If tag namespaces were added and are missing, ensure the tags and the site were re-published.

If no enablement resources appear after selecting a tag when viewing the catalog, ensure there is a tag from the catalog's namespace(s) applied to the enablement resource.

![](assets/chlimage_1-423.png)

