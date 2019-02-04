---
title: Using Maven for Communities
seo-title: Using Maven for Communities
description: null
seo-description: AEM Communities API jar and AEM Uber API jar
uuid: 866f74a2-64b8-437f-93cd-027e1cf82e81
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 6492a12c-3e13-429c-a1c4-221117267d26
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

<!--
Comment Type: draft

<h2>Javadocs</h2>
-->

<!--
Comment Type: draft

<p>The <a href="/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/package-summary">online javadocs</a> reflect the APIs available in the AEM 6.3 release (Communities version 1.11.170).</p>
<p>When a <a href="../../communities/using/deploy-communities.md#latestfeaturepack">feature pack</a>* is released, its javadoc jar is made available to be loaded into an IDE or downloaded to a local disk, exploded, and referenced using a browser.</p>
<p>For example, the AEM 6.3 javadoc jar is located within this Adobe public repository folder :</p>
<ul>
<li><a href="https://repo.adobe.com/nexus/content/groups/public/com/adobe/cq/social/cq-socialcommunities-api/1.11.170/">https://repo.adobe.com/nexus/content/groups/public/com/adobe/cq/social/cq-socialcommunities-api/1.11.170/</a>
<ul>
<li>cq-socialcommunities-api-1.11.170-javadoc.jar</li>
<li>cq-socialcommunities-api-1.11.170-javadoc.jar.md5</li>
<li>cq-socialcommunities-api-1.11.170-javadoc.jar.sha1</li>
<li>cq-socialcommunities-api-1.11.170.jar</li>
<li>cq-socialcommunities-api-1.11.170.jar.md5</li>
<li>cq-socialcommunities-api-1.11.170.jar.sha1</li>
<li>cq-socialcommunities-api-1.11.170.pom</li>
<li>cq-socialcommunities-api-1.11.170.pom.md5</li>
<li>cq-socialcommunities-api-1.11.170.pom.sha1</li>
</ul> </li>
</ul>
<p>* feature packs for AEM 6.3 Communities are versions labeled 1.12.xxx</p>
-->

