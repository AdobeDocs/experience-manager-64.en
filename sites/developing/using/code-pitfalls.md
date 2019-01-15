---
title: Code pitfalls
seo-title: Code pitfalls
description: null
seo-description: Common coding pitfalls to avoid when developing for AEM
uuid: 6327c05f-54a2-4e0f-9489-3cbae14cfea0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 478c1fb5-6296-482c-99b3-ea0a7c420a9f
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Code pitfalls{#code-pitfalls}

### Avoid Sling Bindings in Java code {#avoid-sling-bindings-in-java-code}

Sling Bindings are an inappropriate way to get access to a service in 90% of cases. Instead, you should use *@Reference* or *@Inject* annotations.

### Avoid Thread.interfupt in Java code {#avoid-thread-interfupt-in-java-code}

*Thread.interrupt* is dangerous because it can close files, including Lucene files and persistent cache files, when called at the wrong time.

### Avoid mixing Java synchronization with ReadWriteLocks {#avoid-mixing-java-synchronization-with-readwritelocks}

This can lead to a race condition in which the code will eventually deadlock. 
