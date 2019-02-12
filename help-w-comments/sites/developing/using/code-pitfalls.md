---
title: Code pitfalls
seo-title: Code pitfalls
description: Common coding pitfalls to avoid when developing for AEM
seo-description: Common coding pitfalls to avoid when developing for AEM
uuid: fbd8d807-45cd-4056-98eb-23e3e78c1cc0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 26d93371-ae83-4768-ab52-867ce0f464f0
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
