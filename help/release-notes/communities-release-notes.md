---
title: AEM Communities Release Notes
seo-title: AEM Communities
description: Release notes specific to Adobe Experience Manager 6.4 Communities.
seo-description: Release notes specific to Adobe Experience Manager 6.4 Communities.
uuid: a441f242-d7f8-4605-b300-07de4cc6aa5b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: baec0338-8597-4c8b-8632-1ac0c68774ec
index: y
internal: n
snippet: y
---

# AEM Communities Release Notes{#aem-communities-release-notes}

This section provides information on the improvements to AEM Communities since the 6.3 release. To learn about the new features in greater detail, see [What's New in AEM 6.4 Communities](/communities/using/whats-new-aem-communities.html?cq_ck=1522837662674).

To obtain the latest release, see the [Deploying Communities](../communities/using/deploy-communities.md#latestreleases) section of the documentation.

## Main improvements {#main-improvements}

Community Sites:

* Community Administrators can now:

    * Delete permanently Community Sites
    * Select a context-aware configuration folder for Community Sites

Community Groups:

* Community Administrators can now:

    * Delete permanently Community Groups
    * Create Community Groups in multiple languages
    * Add enablement catalog & assignments within Community Groups

* Enablement Managers can now

    * Create and assign resources and learning paths within Community Groups

File Library:

* Community Members now have multiple enhancements to the File Library e.g. sort orders, tagging...

Notifications:

* Community Members now receive notifications upon approval of contributions that went through a moderation process

Moderation:

* Automated Spam Detection Filter
* Community Moderators have additional Moderation filters (e.g. answered/unanswered questions)
* Community Moderators can bookmark and link moderation to predefined filters (e.g. all posts pending approval)

Overall compatibility with foundational changes in AEM 6.4.

Note: all these features are also available for 6.3. Please check the AEM Communities release notes for [6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes.html).

## Known Issues {#known-issues}

* **Moderation** - Not able to delete parent post as a single delete operation from the bulk moderation UI (CQ-4236797)
* **Console** - Forgot Username or Password link is redirecting to the Login Page instead of the corresponding password retrieval form (CQ-4237682)

## Select Features {#select-features}

Expert Scoring ( *Powered by Sensei*) - is used to enable gamification, which is an effective way of encouraging and rewarding valuable community behavior. It can also be used to identify experts for recommendation or marketing purposes.  

## Demonstrations {#demonstrations}

All these features can be demonstrated using the [AEM Demo Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) available publicly on GitHub.com when using the AEM Communities demo scenario and also within the new We.Retail reference implementation.
