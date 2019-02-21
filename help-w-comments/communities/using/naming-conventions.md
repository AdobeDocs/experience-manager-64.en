---
title: Naming Conventions
seo-title: Naming Conventions
description: Hyphens in Java Package Name
seo-description: Hyphens in Java Package Name
uuid: fb1518d5-0b0a-40ff-b076-d12f96ba5a0b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 47c318ec-83ae-4607-96aa-e10673c4a756
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
