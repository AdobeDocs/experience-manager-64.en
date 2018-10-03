---
title: Assets Performance Guide
seo-title: Assets Performance Guide
description: null
seo-description: Learn how to determine the optimal hardware sizing for a new Digital Asset Management (DAM) setup and how to troubleshoot performance issues
uuid: 1aad78e4-d838-4835-8fff-f85051feee83
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/assets-performance-sizing
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 38.067-0400
cq-lastmodifiedby: msm-service
cq-lastreplicated: 2018-04-03T08 39 31.310-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: configuring
cq-template: /apps/help/templates/article-3
discoiquuid: 7e93cccd-3337-4f8f-8507-5b542d86517f
firstPublishExternalDate: 2017-10-31T16:18:15.190-0400
isreadyforlocalization: false
jcr-created: 2018-01-24T19 02 11.679-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:39:30.226-0400
lochandoffdate: 2018-04-30T03 26 38.067-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Assets Performance Guide
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 39 30.226-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/assets-performance-sizing.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/performance/assets-performance-sizing
sha1: c5b8078ed7e25cc3e8161bb996103680dabb5b5a
topicBrowsingSortDate: 2018-04-03T08:39:30.226-0400
index: y
internal: n
snippet: y
translate: y
---

# Assets Performance Guide

Digital asset management is often used in cases where performance matters; however, the typical DAM setup contains a number of hardware and software components that can affect performance. This document provides the following:

* Information for system administrators on determining the optimal hardware sizing for a new Digital Asset Management setup
* Information for software developers looking to troubleshoot DAM instances with performance issues

---

## Performance Issues

Poor performance in digital asset management can impact the user experience in three ways: interactive performance, asset processing, and download speed. To improve performance, it is important to measure the observed performance properly and to establish target metrics.

**4. Factors influencing asset processing performance**

To be able to estimate what hardware you require to process assets, the following aspects need to be taken into account:

* The resolution of the images in amount of pixels
* The heap assigned to AEM's process

The amount of pixels contained in the image determines the processing time - more pixels means processing takes a longer time. Image type, compression rate, or the related size of the file the image is stored in does not influence the overall performance significantly.

Heap has been identified to be the most important limiting factor. Whenever the asset exceeds the available free memory, the processing performance drops rapidly.

The DAM processes are well suited well to be performedin paralell for large amounts. Uploading assets in a batch and multi-core processors speeds up the absolute time spent per asset.

**5. Estimating Hardware Requirements for Performing Asset Processing**

Extensive processing of digital assets requires optimized hardware resources, the most relevant factors are image size and the peak throughput of processed images.

Allocate at least 16GB of heap and configure the DAM Update Asset workflow to use the [Camera Raw package](/content/help/en/experience-manager/6-4/assets/using/camera-raw) for the ingestion of raw images.

---

## Understanding the System

A typical DAM setup consists of end users accessing DAM via a load balancer. The DAM instance might be part of a clustered setup, where each DAM instance runs in a Java Virtual machine process on either a physical machine or a virtual machine. DAM storage is either provided by a RAID disk in cases of single-machine setups or a managed network attached storage in case of clustered setups.
![CQ5 DAM Architecture and Performance Pitfalls](assets/chlimage_1.png) 

The following legend describes the possible performance pitfall areas with some solutions, as appropriate.

---

## Testing for Performance

For every DAM project, be sure to establish a performance testing regime that can identify and resolve bottlenecks quickly. To do so, consider the following checkpoints:

1. End-to-end performance tests using JMeter - Simulate an example search-and-browse session to detect interactive performance problems.
1. Throughput and latency tests using JMeter - Running on a client computer ensures there are no topology-related issues.
1. Standardized asset processing tests - Ingest a small number of example assets and measure the time. This should include external workflow integration.
1. Monitor CPU, Disk, and memory utilization of each cluster node.
1. CRX read/write performance diagnostics to identify non-processing related issues.
1. Monitor network latency and throughput from DAM cluster to your NAS.
1. Test read and write performance as well as disk latency directly on the NAS, if possible.

---

## Tweaking Bottlenecks

The following performance tweaks have been used in projects so far:

* Selective rendition generation: only generate the renditions you need by adding conditions to the asset processing workflow, so that more costly renditions are only generated for select assets.
* Shared data store among instances: when running low on disk space this can considerably reduce the amount of disk space needed at the cost of higher configuration efforts and losing the auto-cleanup of the datastore.

---

## Further Reading

* [Analyzing Slow and Blocked Processes](/content/help/en/experience-manager/kb/AnalyzeSlowAndBlockedProcesses)

