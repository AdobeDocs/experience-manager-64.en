---
title: Upgrading to AEM 6.4
seo-title: Upgrading to AEM 6.4
description: null
seo-description: Learn about the basics of upgrading an older AEM installation to AEM 6.4.
uuid: 219d210c-75e3-4efc-b36f-9d7bbae4774c
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/upgrade
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-27T04 37 49.538-0400
cq-lastmodifiedby: sarchiz
cq-lastreplicated: 2018-07-27T04 37 49.620-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
topic-tags: upgrading
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 241f4043-8b9e-4759-9e6c-9cac186aa4ec
firstPublishExternalDate: 2017-11-29T07:06:51.286-0500
isreadyforlocalization: false
jcr-created: 2018-03-15T09 01 19.228-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-07-27T04:37:49.517-0400
lochandoffdate: 2018-04-30T03 29 25.095-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-07-27T04 37 49.517-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/upgrade.html
sha1: f3648919770c79ac29fb998f823fd7e3a7443b01
targetaudience: target-audience upgrader
topicBrowsingSortDate: 2018-07-27T04:37:49.517-0400
index: y
internal: n
snippet: y
translate: y
---

# Upgrading to AEM 6.4

In this section, we cover upgrading an AEM installation to AEM 6.4:

* [Planning Your Upgrade](upgrade-planning.md)
* [Assessing the Upgrade Complexity with Pattern Detector](pattern-detector.md)
* [Backward Compatibility in AEM 6.4](backward-compatibility.md)
* [Upgrade Procedure](upgrade-procedure.md)
* [Upgrading Code and Customizations](upgrading-code-and-customizations.md)
* [Pre-Upgrade Maintenance Tasks](pre-upgrade-maintenance-tasks.md)
* [Performing an In-Place Upgrade](in-place-upgrade.md)
* [Post Upgrade Checks and Troubleshooting](post-upgrade-checks-and-troubleshooting.md)
* [Sustainable Upgrades](sustainable-upgrades.md)
* [Lazy Content Migration](lazy-content-migration.md)
* [Repository Restructuring in AEM 6.4](repository-restructuring-in-aem64.md)

For easier reference to the AEM instances involved in these procedures, the following terms are used throughout these articles:

* The *source* instance is the AEM instance that you are upgrading from.
* The *target* instance is the one that you are upgrading to.

>[!NOTE]
>
><p>As part of the efforts to improve the reliability of upgrades, AEM 6.4 has undergone a comprehensive repository restructuring. For more information on how to align with the new structure, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/repository-restructuring.html" target="_blank">Repository Restructuring in AEM 6.4</a></p>

<!-- <p>Added as part of the effort in https://jira.corp.adobe.com/browse/CQDOC-12872</p> -->

---

## What Has Changed?
The following are major changes of note over the last several releases of AEM:

AEM 6.0 introduced the new Jackrabbit Oak repository. Persistence Managers were replaced by [Micro Kernels](platform.md#contentbody_title_4). Starting from version 6.1, CRX2 is no longer supported. A migration tool called crx2oak needs to be run to migrate CRX2 repositories from 5.6.1 instances. For more information, see [Using the CRX2OAK Migration Tool](using-crx2oak.md).

If Asset Insights is to be used and you are upgrading from a version older than AEM 6.2, assets must be migrated and have IDs generated through a JMX bean. In our internal tests, 125K assets on a TarMK environment were migrated in an hour, but your results may vary.

6.3 introduced a new format for the `SegmentNodeStore`, which is the basis of the TarMK implementation. If you are upgrading from a version older than AEM 6.3, this will require a repository migration as part of the upgrade, involving system downtime.

Adobe Engineering estimates this to be around 20 minutes. Note that reindexing will not be necessary. Additionally, a new version of the crx2oak tool has been released to work with the new repository format.

**This migration is not required if upgrading from AEM 6.3 to AEM 6.4.**

The pre-upgrade maintenance tasks have been optimized to support automation.

The crx2oak tool command line usage options have been changed to be automation friendly and support more upgrade paths.

The post-upgrade checks have also been made automation friendly.

Periodic garbage collection of revisions and data store garbage collection are now routine maintenance tasks that need to be performed periodically. With the introduction of AEM 6.3, Adobe supports and recommends Online Revision Cleanup. See [Revision Cleanup](revision-cleanup.md) for information on how to configure these tasks.

**AEM 6.4** introduces the [Pattern Detector](pattern-detector.md) for assessment of complexity of the upgrade as you start planning for the upgrade. 6.4 also has a strong focus on [backward compatibility](backward-compatibility.md) of features. Finally, best practices for [sustainable upgrades](sustainable-upgrades.md) are also added.

For more details about what else has changed in recent AEM versions, see the complete release notes:

* [https://helpx.adobe.com/experience-manager/6-2/release-notes.html](https://helpx.adobe.com/experience-manager/6-2/release-notes.html)
* [https://helpx.adobe.com/experience-manager/6-3/release-notes.html](https://helpx.adobe.com/experience-manager/6-3/release-notes.html)
* [https://helpx.adobe.com/experience-manager/6-4/release-notes.html](https://helpx.adobe.com/experience-manager/6-4/release-notes.html)

---

## Upgrade Overview
Upgrading AEM is a multi-step, sometimes multi-month process. The following outline has been provided as an overview of what is included in an upgrade project and the content that has been included in this documentation:

![](assets/screen_shot_2018-03-30at80708am.png)

---

## <p>Upgrade Flow with 6.4 Upgrade Improvements</p>
The diagram below captures the overall recommended flow highlight the upgrade approach. Please note the refernce to the new features we have introduced. The upgrade should start with the Pattern Detector(see [Assessing the Upgrade Complexity with Pattern Detector](pattern-detector.md)) which should let you decide the path you want to take for compatibility with AEM 6.4 based on the patterns in the generated report.

There was a big focus in 6.4 to keep all the new features backward compatible, but in cases where you still see some backward compatibility issues, the compatibility mode allows you to temporarily defer development to keep your custom code compliant with 6.4. This approach helps you avoid development effort immediately after the upgrade(see [Backward Compatibility in AEM 6.4](backward-compatibility.md)).

Finally, in your 6.4 development cycle, features introduced under Sustainable Upgrades(see [Sustainable Upgrades](sustainable-upgrades.md)) help you follow best practices to make future upgrades even more efficient and seamless.

![](assets/6_4_upgrade_overviewflowchart-newpage3.png)

