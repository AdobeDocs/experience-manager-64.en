---
title: Consistency and Traversal Checks
seo-title: Consistency and Traversal Checks
description: null
seo-description: Learn how to perform consistency and traversal checks.
uuid: 4274d4d9-37c7-4e85-a0b6-a033703f38c0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
discoiquuid: 0adaa346-9828-402a-8e71-36e8e0fb5cbe
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Consistency and Traversal Checks{#consistency-and-traversal-checks}

When upgrading there can be problems due to workspace inconsistencies. You can either run a test upgrade to see if this will be an issue, or run the consistency checks as preventive action.

If you run a test upgrade that fails due to workspace inconsistencies you will see entries similar to the following in crx-quickstart/logs/crx/error.log:

```xml
*ERROR* TarPersistenceManager: No bundle found for uuid 'deadbeef-cafe-babe-cafe-babecafebabe'
 ...
*ERROR* RepositoryImpl: Failed to initialize workspace 'crx.default'
javax.jcr.RepositoryException: Error indexing workspace: Error indexing workspace: Error indexing workspace
...
```

### Perform a Consistency Check {#perform-a-consistency-check}

To perform a consistency check, navigate to the administration page for the JMX Mbean** com.adobe.granite (Repository)**. From the AEM main screen, go to:

**Tools &gt; Web Console &gt; Main(on menu bar) &gt; JMX &gt; com.adobe.granite (Repository)**

On a default installation, it is found here: ** [|Show Me|](http://localhost:4502/system/console/jmx/com.adobe.granite%3Atype%3DRepository)**

In the **Operations** section of the page you will find two methods: **`traversalCheck`** and **`consistencyCheck`**. To execute a check, click on the operation and enter the desired parameters.

![](assets/chlimage_1-134.png)

