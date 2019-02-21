---
title: Using Maven for Communities
seo-title: Using Maven for Communities
description: AEM Communities API jar and AEM Uber API jar
seo-description: AEM Communities API jar and AEM Uber API jar
uuid: fff3c6f0-939e-4c32-8715-0d545454c757
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: da414eab-8b25-448f-bd0c-1dfbea04a035
index: y
internal: n
snippet: y
---

# Using Maven for Communities{#using-maven-for-communities}

## Overview {#overview}

This section of the AEM Communities documentation is in addition to:

* [How to Build AEM Projects using Apache Maven](../../sites/developing/using/ht-projects-maven.md)

There are now two "uber" artifacts that replace individual artifacts :

* AEM [Communities API jar](#communitiesapijarartifact)
* AEM [Uber API jar](../../sites/developing/using/ht-projects-maven.md#whatistheuberjar)

## Communities API Jar Artifact {#communities-api-jar-artifact}

Following is an example of a GAV for the AEM Communities API jar :

```xml
<dependency>
    <groupId>com.adobe.cq.social</groupId>
    <artifactId>cq-socialcommunities-api</artifactId>
    <version>1.11.170</version>
    <scope>provided</scope>
</dependency>

```

The version specified should correspond to the Communities package version installed for AEM Communities. To verify the installed version number :

* login with adminstrative privileges
* browse to [Package Manager](../../sites/administering/using/package-manager.md)  
  for example, [http://localhost:4502/crx/packmgr/](http://localhost:4502/crx/packmgr/)

* locate the package *cq-socialcommunities-pkg-1.x.xxx*
* extract the version from the package name

    * first version for AEM 6.3 is version 1.11.170
    * feature packs will be versions 1.12.xxx

>[!NOTE]
>
>It is recommended to keep up-to-date with the most recent Communities release. 
>
>Visit the [Latest Releases](../../communities/using/deploy-communities.md#latestreleases) section to identify the most recent version.

## Maven Dependency Example {#maven-dependency-example}

The Communities API jar must be specified before the Uber API jar.

```xml
<dependency>
    <groupId>com.adobe.cq.social</groupId>
    <artifactId>cq-socialcommunities-api</artifactId>
    <version>1.11.170</version>
    <scope>provided</scope>
</dependency>
<dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>uber-jar</artifactId>
    <version>6.3.0</version>
    <scope>provided</scope>
    <classifier>apis</classifier>
</dependency>
```

