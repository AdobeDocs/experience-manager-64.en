---
title: Post Upgrade Checks and Troubleshooting
seo-title: Post Upgrade Checks and Troubleshooting
description: null
seo-description: Learn how to troubleshoot issues that might appear after an upgrade.
uuid: f3419299-bb61-43a5-9004-89a498084407
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/post-upgrade-checks-and-troubleshooting
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 51.982-0400
cq-lastmodifiedby: taneja
cq-lastreplicated: 2018-04-04T10 21 56.860-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 3d1fd402-28e2-4674-a3be-a5b5279442fc
firstPublishExternalDate: 2017-11-29T07:07:26.144-0500
isreadyforlocalization: false
jcr-created: 2018-02-10T08 01 15.199-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-04T10:21:56.071-0400
lochandoffdate: 2018-04-30T03 27 51.982-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
publishexternaldate: 2018-04-04T10 21 56.071-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/post-upgrade-checks-and-troubleshooting.html
sha1: 59db336546a610d5623fa11ed4d668df8d59b37b
topicBrowsingSortDate: 2018-04-04T10:21:56.071-0400
index: y
internal: n
snippet: y
---

# Post Upgrade Checks and Troubleshooting



## Post Upgrade Checks

Following the [In-Place Upgrade](in-place-upgrade.md) the following activities should be executed to finalize the upgrade. It is assumed AEM has been started with the 6.4 jar and that the upgraded code base has been deployed.

* [Verify logs for upgrade success](post-upgrade-checks-and-troubleshooting.md#main-pars_header_290365562)

* [Verify OSGi Bundles](/content#main-pars_header_1637350649)

* [Verify Oak Version](/content#main-pars_header_1293049773)

* [Inspect the PreUpgradeBackup folder](/content#main-pars_header_988995987)

* [Initial Validation of Pages](/content#main-pars_header_20827371)

* Verify application pages

* [Apply AEM Service Packs](/content#main-pars_header_215142387)

* [Migrate AEM features](/content#main-pars_header_1434457709)

* [Verify Scheduled Maintenance Configurations](/content#main-pars_header_1552730183)

* [Enable Replication Agents](/content#main-pars_header_823243751)

* [Enable Custom Scheduled Jobs](/content#main-pars_header_244535083)

* [Execute Test Plan](/content#main-pars_header_1167972233)

### Verify logs for Upgrade Success

**upgrade.log**

In the past, inspecting the post upgrade state of your instance required careful inspection of various log files, parts of the repository and the launchpad. Generating a post upgrade report can help detect defective upgrades before going live.

The main purpose of this feature is to reduce the need for manual interpretation or complex parsing logic across multiple endpoints required to qualify the success of an upgrade. The solution aims to provide unambiguous information for external automation systems to react on the success or the identified failure of an update.

More specifically, it ensures that:

* Upgrade failures detected by the upgrade framework can are centralized in a single upgrade report;  
* The upgrade report includes indicators about necessary manual intervention.

To accomodate this, changes have been made in the way logs are generated in the `upgrade.log` file.

Here is a sample report that show no errors during upgrade:

![](assets/1487887443006.png)

Here is a sample report that shows a bundle that was not installed during the upgrade process: 

![](assets/1487887532730.png)

**error.log**

The error.log should be carefully reviewed during and following the start up of AEM using the target version jar. Any warnings or errors should be reviewed. In general it is best to look for issues at the beginning of the log. Errors that occur later in the log may actually be side-effects of a root cause that is called out early in the file. If repeated errors and warnings occur see below for [Analyzing Issues with the Upgrade](post-upgrade-checks-and-troubleshooting.md#Analyzing Issues With The Upgrade).

### Verify OSGi Bundles

Navigate to the OSGi console `/system/console/bundles` and look to see if any bundles are not started. If any bundles are in an installed state consult the `error.log` to determine root issue.

### Verify Oak Version

Following the upgrade you should see that Oak version has been updated to **1.6.1**. To verify the Oak version navigate to the OSGi console and look at the version associated with Oak bundles: Oak Core, Oak Commons, Oak Segment Tar.

### Inspect PreUpgradeBackup folder

During the upgrade AEM will attempt to backup customizations and store them beneath `/var/upgrade/PreUpgradeBackup/<time-stamp-of-upgrade>`. In order to view this folder in CRXDE Lite you may need to [temporarily enable CRXDE Lite](/content/help/en/experience-manager/6-4/sites/administering/using/enabling-crxde-lite).

The folder with the time stamp should have a property named `mergeStatus` with a value of `COMPLETED`. The **to-process** folder should be empty and the **overwritten** node indicates which nodes were overwritten during the upgrade. Content beneath the **leftovers** node indicate content that could not be safely merged during the upgrade. If your implementation is dependent on any of the children nodes (and not already installed by your upgraded code package) they will need to be merged manually.

Disable CRXDE Lite following this exercise if on a Stage or Production environment.

### Initial Validation of Pages

Perform an initial validation against several pages in AEM. If upgrading an Author environment open the Start page and Welcome page ( `/aem/start.html`, `/libs/cq/core/content/welcome.html`). On both Author and Publish environments open a few application pages and smoke test that they render correctly. If any issues occur consult the `error.log` to troubleshoot.

### Apply AEM Service Packs

Apply any relevant AEM 6.4 Service Packs if they have been released.

### Migrate AEM Features

Several features in AEM require additional steps following the upgrade. A full list of these features and steps to migrate them in AEM 6.4 can be found on the [Upgrading Code and Customizations](upgrading-code-and-customizations.md) page.

### Verify Scheduled Maintenance Configurations

#### Enable Data Store Garbage Collection

If using a File Data Store ensure that the Data Store Garbage Collection task is enabled and added to the Weekly Maintenance list. Instructions are outlined [here](/content/help/en/experience-manager/6-4/sites/administering/using/data-store-garbage-collection).

>[!NOTE]
>
>This is not recommended for S3 custom data store installations or when using a shared data store.

#### Enable Online Revision Cleanup

If using MongoMK or the new TarMK segment format ensure that the Revision Clean Up task is enabled and added to the Daily Maintenance list. Instructions outlined [here](revision-cleanup.md).

### Execute Test Plan

Execute detailed test plan against as defined [Upgrading Code and Customizations](upgrading-code-and-customizations.md) under the **Test Procedure** section.

### Enable Replication Agents

Once publish environment has been fully upgraded and validated, enable replication agents on the Author Environment. Verify that agents are able to connect to respective Publish instances. See U [pgrade Procedure](upgrade-procedure.md) for more details on order of events.

### Enable Custom Scheduled Jobs

Any scheduled jobs as part of the code base can be enabled at this point.

## Analyzing Issues With The Upgrade

This section contains some issue scenarios one might face along the upgrade procedure to AEM 6.3.

These scenarios should help to track down the root cause of issues related to upgrade and should help to identify project or product specific issues.

### Repository Migration Failing

The data migration from CRX2 to Oak should be feasible for any scenario starting with Source Instances based on CQ 5.4. Make sure that you exactly follow the upgrade instructions in this document which include the preparation of the `repository.xml`, making sure no custom custom authenticator is started via JAAS and the instance has been checked for inconsistencies before starting the migration.

If the migration still fails you can figure out what is the root cause by inspecting the `upgrade.log`. If the issue is not yet known, please report it to Customer Support.

### The Upgrade Did Not Run

Before starting the preparation steps, make sure you run the **source** instance first by executing it with the java -jar aem-quickstart.jar command. This is required in order to make sure that the quickstart.properties file is generated properly. If it is missing, the upgrade will not work. Alternatively, you can check whether the file is present by looking under `crx-quickstart/conf` in the installation folder of the source instance. Additionally, when starting AEM to kick off the upgrade, it must be executed with the java -jar aem-quickstart.jar command. Starting up from a start script will not start AEM in upgrade mode.

### Packages and Bundles Fail to Update

In case packages fail to install during the upgrade, the bundles they contain will not be updated either. This category of issues is usually caused by data store misconfiguration. They will also appear as **ERROR** and **WARN** messages in the error.log. Since in most of these cases the default login may fail to work, you can use CRXDE directly in order to inspect and find the configuration problems.

### Some AEM Bundles are not Switching to the Active State

In case of bundles not starting up you should check for any unsatisfied dependencies.

In case this problem is present but it is based on a failed package installation which led to bundles not being upgrade they will be deemed incompatible for the new version. For more info on how to troubleshoot this, see **Packages and Bundles Fail to Update** above.

It is also recommended to compare the bundle list of a fresh AEM 6.4 instance with the upgraded one to detect the bundles that where not upgraded. This will provide a closer scope of what to search for in the `error.log`.

### Custom Bundles not Switching to the Active State

In case your custom bundles are not switching to the active state it is most likely that there is code that is not importing change API. This will most often lead to unsatisfied dependencies.

API that was removed should be marked as deprecated in one of the pervious releases. You might find instructions about a direct migration of your code in this deprecation notice. Adobe aims for semantic versioning where possible so the versions can indicate breaking changes.

It is also best to check if the change that has caused the problem was absolutely necessary and revert it if it is not. Also check if the version increase of the package export was increased more than necessary, following strict semantic versioning.

### Malfunctioning Platform UI

In case of certain UI functionality that is not working properly after the upgrade, you should first check for custom overlays of the interface. Some structures might have changed and the overlay might need an update or is obsolete.

Next, check for any Javascript errors that can be tracked down to custom added extensions that are hooked to client libraries. The same can apply for custom CSS that might be causing problems to the AEM layout.

Finally, check for misconfiguration that Javascript might not be able to deal with. This is usually the case with improperly deactivated extensions.

### Malfunctioning Custom Components, Templates or UI Extensions

In most cases, the root causes for these issues are the same as for bundles that are not started or packages not being installed with the only difference that the issues start occurng when first using the components.

The way to deal with erroneous custom code is to first perfom smoke tests in order to identify the cause. Once you find it, look at the recommendations in this [link] section of the article for ways of fixing them.

### Missing Customizations Under /etc

`/apps` and `/libs` are handled well by the upgrade, but changes under `/etc` may be need to be manually restored from `/var/upgrade/PreUpgradeBackup` after upgrading. Make sure to check this location for any content that needs to be manually merged.

### Analyzing the error.log and upgrade.log

In most situations the logs need to be consulted for errors in order to find the cause of a problem. However, in case of upgrades it is also necessary to monitor dependency issues as old bundles might not be upgraded properly.

The best way to do this is to strip down the error.log by removing of all messages that are expected to be unrelated to the issue you are facing. You can do this via tool like grep, by using:

```shell
grep -v UnrelatedErrorString
```

Some error messages might not be immediately explicative. In this case, looking at the context in which they occur can also help understand where the error was created. You can separate the error using:

* `grep -B` for adding lines before the error;

or

* `grep -A` for adding lines after.

In a few cases errors can also be found WARN messages as there can be valid cases leading to this state and the application is not always able to decide if this is an actual error. Make sure you consult these messages as well.

### Contacting Adobe Support

If you have gone through the advice on this page and are still seeing issues, please reach out to Adobe Support. To provide as much information as possible to the support engineer who works on your case, please make sure to include the upgrade.log file from your upgrade.
