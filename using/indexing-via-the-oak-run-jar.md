---
uuid: 03be19dc-c200-4329-8ba3-2bf46b282a33
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

---

## Index Consistency Checks

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header">Use Case 1 - Index Consistency Check</a>.</p>

* `oak-run.jar`quickly determines if lucene oak indexes are corrupt.
* It is safe to run on an in-use AEM instance for consistency check levels 1 and 2.

![](assets/screen_shot_2017-12-14at135758.png) 

---

## Index Statistics

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_2069837756" target="_blank">Use Case 2 - Index Statistics</a></p>

* `oak-run.jar` dumps all index definitions, important index stats and index contents for offline analysis.
* Safe to execute on an in-use AEM instance.

![](assets/image2017-12-19_9-47-40.png) 

---

## <p>Re-indexing Approach Decision Tree</p>

This diagram is a decision tree for when to use the various re-indexing approaches.
![](assets/oak_-_reindexingwithoak-run.png) 

---

## <p>Re-indexing MongoMK / RDMBMK</p>

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_1966814117" target="_blank">Use Case 3 - Reindexing</a>.</p>

### Text Pre-extraction for SegmentNodeStore and DocumentNodeStore

[Text pre-extraction](best-practices-for-queries-and-indexing.md#Howtoperformtextpreextraction) (a feature that has existed with AEM 6.3) can be used to reduce the time to re-index. Text pre-extraction can be used in conjunction with all re-indexing approaches.

Depending on the `oak-run.jar` indexing approach there will be various steps on either side of the Perform Re-index step in the diagram below.
![](assets/4.png) 
>[!NOTE]
>
><p>Orange denotes activities where AEM must be in a maintenance window.</p>

### Online re-indexing for MongoMK or RDBMK using oak-run.jar

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_1264240815" target="_blank">Reindex - DocumentNodeStore</a>.</p>

This is the recommended method for reindexing MongoMK (and RDBMK) AEM installations. No other method should be used.

This process needs to be executed only against a single AEM instance in the cluster.
![](assets/5.png) 

---

## Re-indexing TarMK

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_833164464" target="_blank">Reindex - SegmentNodeStore</a>.</p>

* ** Cold Standby considerations (TarMK)**

    * There are no special consideration for Cold Standby; the Cold Standby instances will sync changes as usual.

* **AEM Publish Farms (AE Publish Farms should always be TarMK)**

    * For publish farm it needs to be done for all OR execute the steps on a single publish and then clone the setup for others (taking all the usual precations when cloning AEM instances; sling.id - should link to something here)

### Online Re-Indexing for TarMK

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_1140524246" target="_blank">Online Reindex - SegmentNodeStore</a>.</p>

This is the method used before te introudction of the new indexing capabilities of oak-run.jar. It can done by setting the `reindex=true` property on the Oak index.

This approach can be used if the time and performance effects to index are acceptable to the customer. This is often the case for small to medium sized AEM installations.
![](assets/6.png) 

### Online Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_1975944462" target="_blank">Online Reindex - SegmentNodeStore - The AEM Instance is Running</a>.<br /> &nbsp;</p>

Online-reindexing of TarMK is faster than the Online TarkMK reindexing decribed above. However, it also requires execution during a maintenance window, with the methion that the window will be shorter, and more steps are required to perform the re-indexing.

>[!NOTE]
>
><p>Orange denotes operations where AEM must be performed in a maintenance period.</p> 
![](assets/7.png) 

### Offline Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_1014954409" target="_blank">Online Reindex - SegmentNodeStore - The AEM Instance is Shut Down</a>.</p>

Offline re-indexing of TarMK is the simplest `oak-run.jar` based re-indexing approach for TarMK as it requires a single `oak-run.jar` comment. However, it requires the AEM instance to be shutdown.

>[!NOTE]
>
><p>Red denotes operations where AEM must be shut down.</p> 
![](assets/8.png) 

### Out-of-band Re-Indexing TarMK using oak-run.jar

>[!NOTE]
>
><p>For more detailed information regarding this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_703104640" target="_blank">Out of Band Reindex - SegmentNodeStore</a>.</p>

Out-of-band re-indexing minimizes the impact of re-indexing on in-use AEM instances.

>[!NOTE]
>
><p>Red denotes operations where AEM may be shut down.</p> 
![](assets/9.png) 

---

## Updating Indexing Definitions

>[!NOTE]
>
><p>For more detailed information about this scenario, see <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/oak-run-indexing-usecases.html#main-pars_header_2126383393" target="_blank">Use Case 4 - Updating Index Definitions</a>.<br /> &nbsp;</p>

### Creating and Updating index definitions on TarMK using ACS Ensure Index

>[!NOTE]
>
><p>ACS Ensure Index is a community supported project, and is not supported by Adobe Support.</p>

This allows shipping index definition via content package which later results in re-indexing via setting the reindex flag to `true`. This works for smaller setups where reindexing does not take long time.

For more info, see the [ACS Ensure Index documentation](https://adobe-consulting-services.github.io/acs-aem-commons/features/ensure-oak-index/index.html) for details.

### Creating and Updating index definitions on TarMK using oak-run.jar

If the time or performance impact of re-indexing using non `oak-run.jar` methods is too high, the following `oak-run.jar` based approach can be used to import and re-index Lucene Index definitions in a TarMK based AEM installation.
![](assets/10.png) 

### Creating and Updating Index Definitions on MonogMK using oak-run.jar

If the time or performance impact of re-indexing using non `oak-run.jar` methods is too high, the following `oak-run.jar` based approach can be used to import and re-index Lucene Index definitions in MongoMK based AEM installations.
![](assets/11.png) 