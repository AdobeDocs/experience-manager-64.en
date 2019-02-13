---
title: Naming Conventions
seo-title: Naming Conventions
description: Hyphens in Java Package Name
seo-description: Hyphens in Java Package Name
uuid: 70282e3f-16d1-4721-9ed8-4091de3f8fde
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: fcbbe499-2c03-4ec0-9f9a-90bf180b8048
index: y
internal: n
snippet: y
---

# Naming Conventions{#naming-conventions}

## Hyphens in Java Package Name {#hyphens-in-java-package-name}

When creating a location for a Java class, be aware that the package name must match that of the repository folder location with any hyphens in the path properly escaped.

While using hyphens in the names of repository items is a recommended practice in AEM development, hyphens are illegal within Java package names.

The underlying CRX platform must be able to distinguish between an actual underscore '_' and a hyphen '-'. Thus, in JCR, the hyphen must be replaced with its unicode value (u002d) and escaped with an underscore '_'.

For example, if the repository path is

**/apps/my-example/component/info/Info.java**

the package name should be

```java
  package apps.my_002dexample.component.info;
```

Notice that an underscore must similarly be escaped, such that '_' becomes '_005f'.
