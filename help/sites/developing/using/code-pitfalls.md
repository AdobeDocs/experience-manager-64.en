---
title: Code pitfalls
seo-title: Code pitfalls
description: Common coding pitfalls to avoid when developing for AEM
seo-description: Common coding pitfalls to avoid when developing for AEM
uuid: a03ef241-36e9-4817-91bf-d36a48fe66fa
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 0d3f9b88-e390-4810-b850-6cad70eaf7b1
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
