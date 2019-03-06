---
title: Tagging User Generated Content
seo-title: Tagging User Generated Content
description: Tagging of user generated content (UGC) is how community members can help other members search for content
seo-description: Tagging of user generated content (UGC) is how community members can help other members search for content
uuid: a5a0494d-51cb-43c2-a358-968226e007b6
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: f748c90b-0ace-404a-bf0b-63a977a6733e
index: y
internal: n
snippet: y
---

# Tagging User Generated Content{#tagging-user-generated-content}

## Overview {#overview}

Tagging of user generated content (UGC) is the means by which community members can help other members search for content.

Typically, tags are applied by authors and administrators in the author environment. Tagging UGC is unique in that UGC tags are applied by community members in the publish envronment.

The tag namespaces and taxonomies are the same for both applications.

## Communities Features {#communities-features}

The AEM Communities features which can be configured to allow tagging are

* [Blog](../../communities/using/blog-feature.md)
* [Calendar](../../communities/using/calendar.md)
* [File Library](../../communities/using/file-library.md)
* [Forum](../../communities/using/forum.md#configuretheaddedforum)
* [Questions and Answers](../../communities/using/working-with-qna.md)

## Administering Tags {#administering-tags}

See [Administering Tags](../../sites/administering/using/tags.md#taggingconsole) for creating and managing tag namespaces and taxonomies.

See [Tag Essentials](../../communities/using/tag.md) for developer information.

See [Using Social Tag Cloud](../../communities/using/tagcloud.md) for adding a Social Tag Cloud component to a page to facilitate searching for posted UGC using the tags applied.

### Tag Permissions {#tag-permissions}

The default permissions are set to not allow tag namespaces to be read by everyone in the publish environment.

Because tags are applied to UGC in the publish environment, read permission needs to be enabled for community members in order for them to be able to select tags to apply.

See [Setting Tag Permissions](../../sites/administering/using/tags.md#settingtagpermissions).

The following is how it appears in CRXDE when an administrator applies read permissions to `/etc/tag/discussions` for the group `*Community Engage Members*`.

![](assets/chlimage_1-74.png)

