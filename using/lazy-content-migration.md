---
title: Lazy Content Migration
seo-title: Lazy Content Migration
description: null
seo-description: Learn about Lazy Content Migration in AEM 6.4.
uuid: 85320151-f149-4341-b732-27b2674790ee
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/lazy-content-migration
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 24.033-0400
cq-lastmodifiedby: dgonzale
cq-lastreplicated: 2018-04-03T08 53 43.737-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
cq-template: /apps/help/templates/article-3
discoiquuid: 31224c27-bff8-464b-bd34-c20193b8748b
firstPublishExternalDate: 2018-04-03T08:53:43.721-0400
isreadyforlocalization: false
jcr-created: 2018-03-23T07 28 51.511-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:53:43.721-0400
lochandoffdate: 2018-04-30T03 27 24.032-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 53 43.721-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/lazy-content-migration.html
sha1: 4d48a77f5aa3d3c0b74e7cdf438f7fad38edcee2
topicBrowsingSortDate: 2018-04-03T08:53:43.721-0400
unpublishinternaldate: 2018-03-30T04 56 09.608-0400
index: y
internal: n
snippet: y
translate: y
---

# Lazy Content Migration

For the sake of backwards compatibility, content and configuration in **/etc** and **/content** starting with AEM 6.3 will not be touched or transformed immediately with the upgrade. This is done in order to ensure that dependencies of customer applications on those structures stay intact. The functionality relating to these content structures is still the same even though the content in an out of the box AEM 6.4 would be hosted in another place.

While not all of those locations may be transformed automatically, there are a few delayed `CodeUpgradeTasks` also refered to as Lazy Content Migration. This allows customers to trigger those automatic transformations by restarting the instance with this system property:

```shell
-Dcom.adobe.upgrade.forcemigration=true
```

This will cause the `CodeUpgradeTasks` to be executed during the migration.

While the aim is an efficient execution, this upgrade process is synchronous and therefore comes with a downtime depending on the amount of the content that needs to be processed. It is recommended to evaluate the execution times on a stage environment ahead of a production system to plan an according maintenance window.

As this typically also requires adjusting application this activity should be performed along with the corresponding application deployment.

Below is the full list of `CodeUpgradeTasks` introduced in 6.4:

| **Name** |**Relevant** **for AEM versions prior to** |**Migration** **Type** |**Details** |
|---|---|---|---|
| `Cq561ProjectContentUpgrade` |< 5.6.1 |Immediate |  |
| `Cq60MSMContentUpgrade` |< 6.0 |Immediate |Detects all `LiveRelationShips` from `VersionStorage` that have been deleted and add exclusion property to parent |
| `Cq61CloudServicesContentUpgrade` |< 6.1 |Immediate |Restructures cloudservices for secure by default setup |
| `Cq62ConfContentUpgrade` |< 6.2 |Immediate |Removes property based linking from **/content** to **/conf** (replaced by the OSGi mechanism), generates corresponding OSGi configuration |
| `Cq62FormsContentUpgrade` |< 6.2 |Immediate |Due to merge_preserve handling the secure by default deny rule overrides given permissions leading to the need to reorder on upgrade |
| `CQ62Html5SmartFileUpgrade` |< 6.2 |Immediate |Detects components utilizing the Html5SmartFile widget, searches for usages of the component in the content and restructures persistence, effectively moving the binary a level down and not store it on component level. |
| `Cq62ProjectsCodeUpgrade` |< 6.2 |Immediate |Moves old style projects from **/etc/projects** to **/content/projects** |
| `Cq62TargetCampaignsContentUpgrade` |< 6.2 |Immediate |Introduces a container layer to hierarchy (Areas) and adjusts references. |
| `Cq62TargetContentUpgrade` |< 6.2 |Immediate |Sets fixed location names to target components. |
| `Cq62WorkflowContentUpgrade` |< 6.2 |Immediate |Complex transformation of workflow models predating 6.2 structures, instances, notifications, then merging back from the backup location from **/var/backup** |
| `CQ63AssetsMetadataFormsUpdate` |< 6.3 |Immediate |Moves assets, custom metadata schemas and processing profiles from **/apps** to **/conf** and translates the metadata schema and metadata profiles forms from coral2 to coral3. |
| `CQ63AssetsSearchFacetsUpdate` |< 6.3 |Immediate |Moves assets and custom search facets from **/apps** to **/conf** and translates the metadata schema and metadata profiles forms from coral2 to coral3. |
| `CQ63InboxItemsUpgrade` |< 6.3 |Immediate |Updates InboxItems for ordering of inbox items (adjusting metadata for efficient sorting) |
| `CQ63MetadataSchemaConfigUpdate` |< 6.3 |Immediate |Adjusts the metadataSchema property on folder by replacing relative paths to **/conf** in place of **/apps** |
| `CQ63MobileAppsNavUpgrade` |< 6.3 |Immediate |Adjusting navigation structure |
| `CQ63MonitoringDashboardsConfigUpdate` |< 6.3 |Immediate |Moves custom configurations for the monitoring dashboards from **/libs** and **/apps** |
| `CQ63ProcessingProfileConfigUpdate` |< 6.3 |Immediate |Translates the processingProfile property (used until 6.1) in Assets in order to match the 6.3 and later structure. Also adjusts the profile's relative paths to **/conf** in place of **/apps**. |
| `CQ63ToolsMenuEntriesContentUpgrade` |< 6.3 |Immediate |Upgrade task that removes obsolete CRXDE Lite and Web Console menu entries in case of an upgrade. |
| `CQ64CommunitiesConfigsCleanupTask` |< 6.3 |Delayed |Moving SRP cloud configurations, community watchwords configurations, cleans up **/etc/social** and **/etc/enablement** (any references and data needs to be be adjusted when lazy migration is run - no application part should be depending on this sturcture anymore). |
| `CQ64LegacyCloudSettingsCleanupTask` |< 6.4 |Delayed |Cleans up **/etc/cloudsettings** (containing ContextHub Configuration). Configuration is automatically migrated on first access. In case Lazy Content Migration is started along with upgrade this content in **/etc/cloudsettings** must be preserved via package before the upgrade and reinstalled for the implicit transformation to kick in, along with a subsequent uninstallation of the package after completion. |
| `CQ64UsersTitleFixTask` |< 6.4 |Delayed |Adjusts legacy title structure to title in user profile node. |

