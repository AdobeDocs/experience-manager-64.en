---
title: Version Purging
seo-title: Version Purging
description: This article describes the available options for version purging.
seo-description: This article describes the available options for version purging.
uuid: 4c191737-14ad-44c0-958b-14ee574108d9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
discoiquuid: ab17bab4-12a3-446f-95ea-00720cb1b188
index: y
internal: n
snippet: y
---

# Version Purging{#version-purging}

In a standard installation AEM creates a new version of a page or node when you activate a page after updating the content.

>[!NOTE]
>
>If no content changes are made then you will see the message stating that the page has been activated, but no new version will be created

You can create additional versions on request using the **Versioning** tab of the sidekick. These versions are stored in the repository and can be restored if required.

These versions are never purged, so the repository size will grow over time and therefore need to be managed.

AEM is shipped with various mechanisms to help you manage your repository:

* the [Version Manager](#versionmanager)  
  This can be configured to purge old versions when new versions are created.  

* the ** [Purge Versions](#purgeversionstool) **tool  
  This is used as part of [monitoring and maintaining](../../../sites/deploying/using/monitoring-and-maintaining.md) your repository.  
  It allows you to intervene to remove old versions of a node, or a hierarchy of nodes, according to these parameters:

    * The maximum number of versions to be kept in the repository.  
      When this number is exceeded, the oldest version is removed.  
    
    * The maximum age of any version kept in the repository.  
      When the age of a version exceeds this value, it is purged from the repository.

## Version Manager {#version-manager}

In addition to explicit purging by means of the purge tool, the Version Manager can be configured to purge old versions when new versions are created.

To configure the Version Manager, create a configuration for:

`PID com.day.cq.wcm.core.impl.VersionManagerImpl`

The following options are available:

* `versionmanager.createVersionOnActivation` (Boolean, default: true)  
  whether to create a version when pages are activated.  
  A version is created unless the replication agent is configured to suppress creation of versions, which is honoured by the Version Manager  
  A version is only created if the activation happens on a paths that is contained in versionmanager.ivPaths (see below).

* `versionmanager.ivPaths` (String[], default: {"/"})  
  paths on which versions are implicitly created on activation if versionmanager.createVersionOnActivation is true.

* `versionmanager.purgingEnabled` (Boolean, default: false)  
  whether to enable purging when new versions are created

* `versionmanager.purgePaths` (String[], default: {"/content"})  
  on which paths to purge versions when new versions are created

* `versionmanager.maxAgeDays` (int, default: 30)  
  on purge, any version older than this value will be removed. If this value is less than 1, purging is not performed based on the age of the version  

* `versionmanager.maxNumberVersions` (int, default 5)  
  on purge, any version older than the n-th newest version will be removed. If this value is less than 1, purging is not performed based on the number of versions

* `versionmanager.minNumberVersions` (int, default 0)  
  The minimum number of versions to keep regardless of the age. If this value is set to a value less than 1 no minimum number of versions is retained.

### Combining Retention Options {#combining-retention-options}

The options defining how which versions should be retained ( `maxAgeDays`, `maxNumberVersions`, `minNumberVersions`), can be combined depending on your requirements.

For example, when defining the maximum number of versions to retain AND the oldest version to retain:

* Setting:

    * `maxNumberVersions` = 7  
    
    * `maxAgeDays` = 30

* With:

    * 10 versions made within the past 60 days
    * 3 of those versions created within the past 30 days

* Will mean that:

    * The last 3 versions will be retained

For example, when defining the maximum AND minimum number of versions to retain AND the oldest version to retain:

* Setting:

    * `maxNumberVersions` = 3 
    * `maxAgeDays` = 30 
    * `minNumberVersions` = 3

* With:

    * 5 versions made 60 days ago

* Will mean that:

    * 3 versions will be retained

## Purge Versions Tool {#purge-versions-tool}

The **Purge Versions** tool is intended for purging the versions of a node or a hierarchy of nodes in your repository. Its primary purpose is to help you reduce the size of your repository by removing old versions of your nodes.
