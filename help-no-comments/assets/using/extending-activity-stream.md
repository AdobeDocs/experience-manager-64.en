---
title: Integrating Assets with Activity Stream
seo-title: Integrating Assets with Activity Stream
description: Describes the recording capabilities of AEM and how to configure AEM to record specific events.
seo-description: Describes the recording capabilities of AEM and how to configure AEM to record specific events.
uuid: 986bf975-b961-4880-817a-3555ca391dc4
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: extending-assets
content-type: reference
discoiquuid: f70ad785-5af4-4dff-ac0c-128e5120559e
index: y
internal: n
snippet: y
---

# Integrating Assets with Activity Stream{#integrating-assets-with-activity-stream}

Adobe Experience Manager (AEM) Assets users perform many actions like creating, uploading and deleting Assets. These actions can be recorded so you are able to provide an history of what has been done by a user. This section describes the recording capabilities of AEM and how to configure AEM in order to record specific events.

### Performance Considerations and Default Behavior {#performance-considerations-and-default-behavior}

This integration could be CPU and disk space consuming for example when doing bulk import. For these reasons the AEM Assets integration with the Activity Stream is disabled by default.

### Supported Action Events {#supported-action-events}

The following events can be configured to be recorded:

* License accepted (ACCEPTED)
* Asset created (ASSET_CREATED)
* Asset moved (ASSET_MOVED)
* Asset removed (ASSET_REMOVED)
* License rejected (REJECTED)
* Asset downloaded (DOWNLOADED)
* Asset versioned (VERSIONED)
* Asset version restored (RESTORED)
* Asset Metadata updated (METADATA_UPDATED)
* Asset published to external system (PUBLISHED_EXTERNAL)
* Asset's original updated (ORIGINAL_UPDATED)
* Asset Rendition updated (RENDITION_UPDATED)
* Asset Rendition removed (RENDITION_REMOVED)
* Sub-asset updated (SUBASSET_UPDATED)
* Sub-asset removed (SUBASSET_REMOVED)

### Configuring AEM Assets Events Recording {#configuring-aem-assets-events-recording}

The [Web console](../../sites/deploying/using/configuring-osgi.md) provides access to the AEM Assets Event Recorder tuning. To configure the AEM Assets Event Recorder, proceed as follows:

1. Navigate to the **Web console** 

1. Click **Configuration**.  

1. Double click **Day CQ DAM Event Recorder**.  

1. Check **Enables this service**.  

1. Check which **Event Types** you want to be recorded in the user activity stream.  

1. Click **Save**.

### Reading recorded events {#reading-recorded-events}

The recorded events are stored as activities. You can read them programmatically by using the [ActivityManager API](/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager).  

