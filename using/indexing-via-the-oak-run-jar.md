---
title: Indexing via the Oak-run Jar
seo-title: Indexing via the Oak-run Jar
description: null
seo-description: Learn how to perform indexing via the Oak-run Jar.
uuid: 620f87fc-4c6e-4b5c-a33d-d3ad64355fb5
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/indexing-via-the-oak-run-jar
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 22.116-0400
cq-lastmodifiedby: trushton
cq-lastreplicated: 2018-04-19T15 18 20.095-0400
cq-lastreplicatedby: trushton
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: deploying
cq-template: /apps/help/templates/article-3
discoiquuid: 16f9f75d-1b9c-4360-b502-a7076e28b78f
firstPublishExternalDate: 2018-04-03T08:43:48.053-0400
firstpublishinternaldate: 2018-04-06T10 13 52.867-0400
isreadyforlocalization: false
jcr-created: 2018-03-27T07 29 13.544-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-19T15:18:19.909-0400
lastpublishinternaldate: 2018-04-06T15 03 54.144-0400
lochandoffdate: 2018-04-30T03 27 22.115-0400
lr-lastreplicatedby: trushton@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying
noindex: true
pagecreatedat: en
publishexternaldate: 2018-04-19T15 18 19.909-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/indexing-via-the-oak-run-jar.html
publishinternaldate: 2018-04-06T15 03 54.144-0400
publishinternalurl: https //helpx-internal.corp.adobe.com/content/help/en/experience-manager/6-4/sites/deploying/using/indexing-via-the-oak-run-jar.html
sha1: 350ba49ce27d060f877520f319fc3712fc809586
topicBrowsingSortDate: 2018-04-19T15:18:19.909-0400
index: y
internal: n
snippet: y
translate: y
---

# Indexing via the Oak-run Jar

Oak-run supports all indexing use cases on the command line without having to operate from the JMX level. Advantages of the oak-run approach are:

1. It is a new indexing toolset for AEM 6.4
1. It decreases time-to-reindex which beneficially impacts re-index times on larger repositories
1. It is reducing resource consumption during re-indexing in AEM which results in better system performance for other AEM activities
1. Oak-run provides Out-of-band support: If production conditions doesn't allow to run re-index on production instances, a cloned environment can be used for re-indexing to avoid critical performance impact.

Below you will find a list of use cases that can be leveraged when performing indexing operations via the `oak-run` tool.

## Index Consistency Checks

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Use Case 1 - Index Consistency Check](oak-run-indexing-usecases.md#main-pars_header).

* `oak-run.jar`quickly determines if lucene oak indexes are corrupt.
* It is safe to run on an in-use AEM instance for consistency check levels 1 and 2.

![](assets/screen_shot_2017-12-14at135758.png) 

## Index Statistics

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Use Case 2 - Index Statistics](oak-run-indexing-usecases.md#main-pars_header_2069837756)

* `oak-run.jar` dumps all index definitions, important index stats and index contents for offline analysis.

* Safe to execute on an in-use AEM instance.

![](assets/image2017-12-19_9-47-40.png) 

## <p>Re-indexing Approach Decision Tree</p>

This diagram is a decision tree for when to use the various re-indexing approaches.

![](assets/oak_-_reindexingwithoak-run.png) 

## <p>Re-indexing MongoMK / RDMBMK</p>

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Use Case 3 - Reindexing](oak-run-indexing-usecases.md#main-pars_header_1966814117).

### Text Pre-extraction for SegmentNodeStore and DocumentNodeStore

[Text pre-extraction](best-practices-for-queries-and-indexing.md#Howtoperformtextpreextraction) (a feature that has existed with AEM 6.3) can be used to reduce the time to re-index. Text pre-extraction can be used in conjunction with all re-indexing approaches.

Depending on the `oak-run.jar` indexing approach there will be various steps on either side of the Perform Re-index step in the diagram below.

![](assets/4.png)

>[!NOTE]
>
>Orange denotes activities where AEM must be in a maintenance window.

### Online re-indexing for MongoMK or RDBMK using oak-run.jar

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Reindex - DocumentNodeStore](oak-run-indexing-usecases.md#main-pars_header_1264240815).

This is the recommended method for reindexing MongoMK (and RDBMK) AEM installations. No other method should be used.

This process needs to be executed only against a single AEM instance in the cluster.

![](assets/5.png) 

## Re-indexing TarMK

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Reindex - SegmentNodeStore](oak-run-indexing-usecases.md#main-pars_header_833164464).

* ** Cold Standby considerations (TarMK)**

    * There are no special consideration for Cold Standby; the Cold Standby instances will sync changes as usual.

* **AEM Publish Farms (AE Publish Farms should always be TarMK)**

    * For publish farm it needs to be done for all OR execute the steps on a single publish and then clone the setup for others (taking all the usual precations when cloning AEM instances; sling.id - should link to something here)

### Online Re-Indexing for TarMK

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Online Reindex - SegmentNodeStore](oak-run-indexing-usecases.md#main-pars_header_1140524246).

This is the method used before te introudction of the new indexing capabilities of oak-run.jar. It can done by setting the `reindex=true` property on the Oak index.

This approach can be used if the time and performance effects to index are acceptable to the customer. This is often the case for small to medium sized AEM installations.

![](assets/6.png) 

### Online Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Online Reindex - SegmentNodeStore - The AEM Instance is Running](oak-run-indexing-usecases.md#main-pars_header_1975944462).

Online-reindexing of TarMK is faster than the Online TarkMK reindexing decribed above. However, it also requires execution during a maintenance window, with the methion that the window will be shorter, and more steps are required to perform the re-indexing.

>[!NOTE]
>
>Orange denotes operations where AEM must be performed in a maintenance period.

![](assets/7.png) 

### Offline Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Online Reindex - SegmentNodeStore - The AEM Instance is Shut Down](oak-run-indexing-usecases.md#main-pars_header_1014954409).

Offline re-indexing of TarMK is the simplest `oak-run.jar` based re-indexing approach for TarMK as it requires a single `oak-run.jar` comment. However, it requires the AEM instance to be shutdown.

>[!NOTE]
>
>Red denotes operations where AEM must be shut down.

![](assets/8.png) 

### Out-of-band Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
>For more detailed information regarding this scenario, see [Out of Band Reindex - SegmentNodeStore](oak-run-indexing-usecases.md#main-pars_header_703104640).

Out-of-band re-indexing minimizes the impact of re-indexing on in-use AEM instances.

>[!NOTE]
>
>Red denotes operations where AEM may be shut down.

![](assets/9.png) 

## Updating Indexing Definitions

>[!NOTE]
>
>For more detailed information about this scenario, see [Use Case 4 - Updating Index Definitions](oak-run-indexing-usecases.md#main-pars_header_2126383393).

### Creating and Updating index definitions on TarMK using ACS Ensure Index

>[!NOTE]
>
>ACS Ensure Index is a community supported project, and is not supported by Adobe Support.

This allows shipping index definition via content package which later results in re-indexing via setting the reindex flag to `true`. This works for smaller setups where reindexing does not take long time.

For more info, see the [ACS Ensure Index documentation](https://adobe-consulting-services.github.io/acs-aem-commons/features/ensure-oak-index/index.html) for details.

### Creating and Updating index definitions on TarMK using oak-run.jar

If the time or performance impact of re-indexing using non `oak-run.jar` methods is too high, the following `oak-run.jar` based approach can be used to import and re-index Lucene Index definitions in a TarMK based AEM installation.

![](assets/10.png) 

### Creating and Updating Index Definitions on MonogMK using oak-run.jar

If the time or performance impact of re-indexing using non `oak-run.jar` methods is too high, the following `oak-run.jar` based approach can be used to import and re-index Lucene Index definitions in MongoMK based AEM installations.

![](assets/11.png) 