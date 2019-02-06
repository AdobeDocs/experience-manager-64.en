---
title: Serial Uploads
seo-title: Serial Uploads
description: Learn how AEM Assets one asset at a time when assets are uploaded in bulk and the benefits of serial uploads.
seo-description: Learn how AEM Assets one asset at a time when assets are uploaded in bulk and the benefits of serial uploads.
uuid: 75950e2d-d4c5-4632-b3c9-c6e4f8e921d2
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 0a2840ea-35e7-4d68-b24a-1e63fb241d7a
index: y
internal: n
snippet: y
---

# Serial Uploads{#serial-uploads}

Uploading numerous assets in bulk consumes significant I/O resources, which may adversely impact the performance of your AEM Assets instance. In particular, if you have a slow internet connection, the time to upload drastically increases due to a spike in disk I/O. Moreover, your web browser may introduce additional restrictions to the number of POST requests AEM Assets can handle for concurrent asset uploads. As a result, the upload operation fails or terminate prematurely. In other words, AEM assets may miss some files while ingesting a bunch of files or altogether fail to ingest any file.

To overcome this situation, AEM Assets ingests one asset at a time (serial upload) during a bulk upload operation, instead of the concurrently ingesting all the assets.

Serial uploading of assets is enabled by default. To disable the feature and allow concurrent uploading, overlay the `fileupload` node in Crx-de and set the value of the `parallelUploads` property to `true`.
