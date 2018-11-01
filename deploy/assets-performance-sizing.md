---
title: Assets Performance Guide
seo-title: Assets Performance Guide
description: null
seo-description: Learn how to determine the optimal hardware sizing for a new Digital Asset Management (DAM) setup and how to troubleshoot performance issues
uuid: c71be076-a9d9-4583-ac46-96a09d5290a8
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
discoiquuid: b592e40f-e073-4154-a2c9-56006eb8f67a
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
publishexternaldate: 2018-04-03T08 39 30.226-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/assets-performance-sizing.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/performance/assets-performance-sizing
sha1: e6eb5ee80a0c70db81e7957e806c30556a478199
topicBrowsingSortDate: 2018-04-03T08:39:30.226-0400
index: y
internal: n
snippet: y
---

# Assets Performance Guide

Digital asset management is often used in cases where performance matters; however, the typical DAM setup contains a number of hardware and software components that can affect performance. This document provides the following:

* Information for system administrators on determining the optimal hardware sizing for a new Digital Asset Management setup
* Information for software developers looking to troubleshoot DAM instances with performance issues

## Performance Issues

Poor performance in digital asset management can impact the user experience in three ways: interactive performance, asset processing, and download speed. To improve performance, it is important to measure the observed performance properly and to establish target metrics.

**1. Interactive searching and browsing** Users are searching for assets or browsing the DAM Finder and complain about slow response times or that search results do not show up immediately. This is an interactive performance problem.

Interactive performance is measured in terms of page response time. This is the time it takes from receiving the HTTP request to closing the HTTP response, which can be determined from the request log files. Typical target performance is a page response time below two seconds.

**2. Asset processing** An asset processing problem is when users are uploading assets and it takes minutes until assets are readily converted and ingested into AEM DAM.

Asset processing performance is measured in terms of average workflow process completion time. This is the time it takes from invoking the Asset update workflow process to its completion, which can be determined from the workflow reports user interface. Typical target performance depends on the size and type of assets processed and the number of renditions. Examples target performances could be as follows:

* below ten seconds for images smaller than 1280x1280 pixels using standard renditions
* below one minute for images smaller than 100 MB using standard renditions
* below five minutes for HD video clips shorter than one minute

**3. Download speed** A throughput issue is when downloading from AEM DAM takes long and thumbnails do not show up immediately when browsing the DAM Admin or the DAM Finder.

Throughput performance is measured in terms of download rate in kilobits per second. Typical target performance is 300 kilobits per second for 100 concurrent downloads.

**4. Factors influencing asset processing performance**

To be able to estimate what hardware you require to process assets, the following aspects need to be taken into account:

* The resolution of the images in amount of pixels
* The heap assigned to AEM's process

The amount of pixels contained in the image determines the processing time - more pixels means processing takes a longer time.  
Image type, compression rate, or the related size of the file the image is stored in does not influence the overall performance significantly.

Heap has been identified to be the most important limiting factor. Whenever the asset exceeds the available free memory, the processing performance drops rapidly.

The DAM processes are well suited well to be performedin paralell for large amounts. Uploading assets in a batch and multi-core processors speeds up the absolute time spent per asset.

**5. Estimating Hardware Requirements for Performing Asset Processing**

Extensive processing of digital assets requires optimized hardware resources, the most relevant factors are image size and the peak throughput of processed images.

Allocate at least 16GB of heap and configure the DAM Update Asset workflow to use the [Camera Raw package](/content/help/en/experience-manager/6-4/assets/using/camera-raw) for the ingestion of raw images.

## Understanding the System

A typical DAM setup consists of end users accessing DAM via a load balancer. The DAM instance might be part of a clustered setup, where each DAM instance runs in a Java Virtual machine process on either a physical machine or a virtual machine. DAM storage is either provided by a RAID disk in cases of single-machine setups or a managed network attached storage in case of clustered setups.

<!-- 

Comment Type: draft

<img alt="CQ5 DAM Architecture and Performance Pitfalls" imageRotate="0" src="assets/chlimage_1-125.png" title="DAM Architecture" />

 -->

The following legend describes the possible performance pitfall areas with some solutions, as appropriate.

**Network connection to end user** A slow network connection can cause throughput issues, in some rare cases also latency issues. Sometimes the user has a slow connection from the ISP, especially in intranets. This is a sign of incorrect network topology.

**Temporary File System** A slow local file system can cause interactive performance problems, especially when it comes to search, because the search indexes are stored on the local disk. It can additionally cause asset processing problems if the command line process is being used.

**AEM DAM Finder** Interactive performance problems, often experienced in searches are caused by high CPU utilization due to many concurrent users or other CPU-consuming processes on the same instance. Moving from virtual machines to dedicated machines and making sure no other services run on the machine can help improving performance. If high CPU load is caused due to asset processing and many concurrent users, Day recommends adding additional cluster nodes.

**AEM DAM Workflow** Long-running workflow processes during asset ingestion cause asset processing performance problems. Depending on the type of assets being processed, this can indicate CPU over-utilization. Day recommends that you reduce the number of other processes running on the system and to increase the number of available CPUs by adding cluster nodes.

**NAS Connectivity** Poor network connectivity to the NAS causes interactive performance problems, because accessing new nodes during asset processing is slowed down due to network latency. Additionally, slow network throughput adversely affects throughput, but also asset processing performance, because loading and saving renditions is slowed down.

Reasons for bad latency and throughput in a NAS are usually network topology or NAS over-utilization by other services.

**Network Attached Storage** Over-used network attached storage systems can cause an array of problems:

* Low disk space is a frequently encountered trouble that can be prevented through proper sizing of a DAM project.
* High disk latency will propagate into slow access times for CRX and may result in interactive performance problems.  
* Low disk throughput may result in low performance for CQ5 DAM.

## Testing for Performance

For every DAM project, be sure to establish a performance testing regime that can identify and resolve bottlenecks quickly. To do so, consider the following checkpoints:

1. End-to-end performance tests using JMeter - Simulate an example search-and-browse session to detect interactive performance problems.
1. Throughput and latency tests using JMeter - Running on a client computer ensures there are no topology-related issues.
1. Standardized asset processing tests - Ingest a small number of example assets and measure the time. This should include external workflow integration.
1. Monitor CPU, Disk, and memory utilization of each cluster node.
1. CRX read/write performance diagnostics to identify non-processing related issues.
1. Monitor network latency and throughput from DAM cluster to your NAS.
1. Test read and write performance as well as disk latency directly on the NAS, if possible.

## Tweaking Bottlenecks

The following performance tweaks have been used in projects so far:

* Selective rendition generation: only generate the renditions you need by adding conditions to the asset processing workflow, so that more costly renditions are only generated for select assets.
* Shared data store among instances: when running low on disk space this can considerably reduce the amount of disk space needed at the cost of higher configuration efforts and losing the auto-cleanup of the datastore.

## Further Reading

* [Analyzing Slow and Blocked Processes](/content/help/en/experience-manager/kb/AnalyzeSlowAndBlockedProcesses)

