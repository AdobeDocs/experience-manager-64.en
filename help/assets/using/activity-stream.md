---
title: Activity stream in timeline
seo-title: Activity stream in timeline
description: This article describes how to display activity logs for assets on the timeline. 
seo-description: Display activity logs for assets on the timeline.
uuid: 3990dbd2-6a85-4fa3-b59a-2ca7a9f6cf95
acrolinxdate: 2019-01-12T17 10 46.896-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: green
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/activity_stream_krs_workflow_f3c2f2ccebf6138e_77_report.xml
acrolinxsentences: 13
acrolinxwords: 187
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: authoring
discoiquuid: caf05164-c975-405c-a6f1-099c8aabd799
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Activity stream in timeline{#activity-stream-in-timeline}

This article describes how to display activity logs for assets on the timeline. 

This feature displays activity logs for assets on the timeline. If you perform any of the following asset-related operations in Adobe Experience Manager (AEM) Assets, the Activity stream feature updates the timeline to reflect the activity.

The following operations are logged in the activity stream:

* Create
* Delete
* Download (including renditions)
* Publish
* Unpublish
* Approve
* Reject
* Move

The activity logs to be displayed in the timeline are fetched from the location */var/audit/com.day.cq.dam/content/dam* in CRX, where log files are stored. 

>[!NOTE]
>
>Transient workflows are not displayed in the timeline, because no history information is saved for these workflows.

To view the activity stream, perform one or more of the operations on the asset, select the asset, and then choose **Timeline** from the GlobalNav list.

![](assets/Timeline-3.png)

The timeline displays the activity stream for the operations you perform on the assets. 

![](assets/activity_stream.png)

>[!NOTE]
>
>The default log storage location for **Publish** and **Unpublish** tasks is */var/audit/com.day.cq.replication/content*. For **Move** tasks, the default location is */var/audit/com.day.cq.wcm.core.page*.

