---
title: Code pitfalls
seo-title: Code pitfalls
description: Common coding pitfalls to avoid when developing for AEM
seo-description: Common coding pitfalls to avoid when developing for AEM
uuid: 4af09293-201f-4cea-a2e4-fe57c27ce695
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: e0c59e3d-8d02-48b9-b113-d0f3641ecd5c
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
