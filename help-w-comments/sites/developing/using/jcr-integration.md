---
title: JCR Integration
seo-title: JCR Integration
description: Tips for when you must integrate at the JCR level
seo-description: Tips for when you must integrate at the JCR level
uuid: d917879a-7341-4d5c-a4d4-5eae471b0014
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 242e3132-837d-45b3-b781-dec8d202d9a4
index: y
internal: n
snippet: y
---

# JCR Integration{#jcr-integration}

### Prefer the Sling Resource API to JCR API {#prefer-the-sling-resource-api-to-jcr-api}

The Sling API works at a higher, more abstract level than the JCR API. This allows your code to be more reusable and independent of the underlying storage. This makes it easier to include external virtual data via the ResourceProvider mechanism if needed.

### Avoid queries wherever possible {#avoid-queries-wherever-possible}

It is always faster to navigate the repository to retrieve data than it is to run a query. There are cases in which queries will be necessary, such as an end user query or needing to find structured content from across the entire repository, but for all other cases, it is preferred to navigate to the necessary nodes. Queries should always be avoided in render logic such as navigation components, a “recent items list”, counts of items, etc. In these cases, it is better to walk through the hierarchy or pre-cache the result so that it can be used directly when rendered.

### Restrict the scope of JCR observation {#restrict-the-scope-of-jcr-observation}

When listening for events in the repository, it is important to narrow the scope as much as possible. For example, it is much better to listen for an event at /etc/mycompany than to listen at /etc. Never listen for events at the repository root. Additionally, make sure that the callback methods execute as quickly as possible when there is nothing for them to do.

### Eliminate use of JCR admin access {#eliminate-use-of-jcr-admin-access}

As of AEM 6, login Administrative has been deprecated as has getting an administrative session from the ResourceResolverFactory. Rather, service accounts should be created for the back office operations that would require this type of access and the ResourceResolverFactory can be used to get a ResourceResolver for this account. For more information, see [http://www.wemblog.com/2014/08/how-to-use-sessions-and-resource.html](http://www.wemblog.com/2014/08/how-to-use-sessions-and-resource.html).
