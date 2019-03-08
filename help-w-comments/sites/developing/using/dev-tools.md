---
title: Development Tools
seo-title: Development Tools
description: To develop your JCR, Apache Sling or AEM applications, a number of tool sets are available
seo-description: To develop your JCR, Apache Sling or AEM applications, a number of tool sets are available
uuid: 9b5e6276-0b41-4c52-8d5f-299f79a8d79a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: development-tools
content-type: reference
discoiquuid: cc053f37-7684-4309-a9f1-5a9c3ac895a9
index: y
internal: n
snippet: y
---

# Development Tools{#development-tools}

To develop your JCR, Apache Sling or AEM applications, the following tool sets are available:

* one set consisting of [CRXDE Lite](../../../sites/developing/using/developing-with-crxde-lite.md) and WebDAV. CRXDE Lite is embedded into CRX/AEM and enables you to perform standard development tasks in the browser. With CRXDE Lite, you can create and edit files (like .jsp and .java), folders, templates, components, dialogs, nodes, properties** **and bundles while logging and integrating with SVN.   
  CRXDE Lite is recommended when you do not have direct access to the CRX/AEM server, when you develop an application by extending or modifying the out-of-the-box components and Java bundles or when you do not need a dedicated debugger, code completion and syntax hightlighting.

* one set consisting of an Integrated Development Environment (for example: [Eclipse](../../../sites/developing/using/howto-projects-eclipse.md) or [IntelliJ](../../../sites/developing/using/ht-intellij.md)), a build tool (for example: [Apache Maven](../../../sites/developing/using/ht-projects-maven.md)), FileVault which has been developed by Adobe to map a repository to a file system, a version control system (for example: Subversion), a bug tracker system (for example: Jira), a central dependency management system (for example: Apache Archiva) and a build automation system (for example: Apache Continuum).  
  This setup allows you to fully integrate your application (content, code, configuration) into any development environment and process.The link between the different elements is the file system representation of the repository through FileVault, as all of the aforementioned development tools can work with files.

### Extensions for Integrated Development Environments {#extensions-for-integrated-development-environments}

Adobe released the following extensions:

* [AEM Eclipse Extension](../../../sites/developing/using/aem-eclipse.md)
* [AEM Brackets Extension](../../../sites/developing/using/aem-brackets.md)
* [AEM IntelliJ Extension](https://github.com/headwirecom/aem-ide-tooling-4-intellij/blob/master/documenation/AEM%20Tooling%20Plugin%20for%20IntelliJ%20IDEA.pdf) (from Headwire)

### Other Tools {#other-tools}

AEM ships with other tools that facilitate development:

* [Dialog Editor](../../../sites/developing/using/dialog-editor.md)
* [Using Translator to Manage Dictionaries  
  ](../../../sites/developing/using/i18n-translator.md)
* [Site Importer](../../../sites/developing/using/site-importer.md)
* [Managing Packages Using Maven](../../../sites/developing/using/vlt-mavenplugin.md)
* [How to Develop AEM Projects Using Eclipse](../../../sites/developing/using/howto-projects-eclipse.md)
* [How to Build AEM Projects using Apache Maven](../../../sites/developing/using/ht-projects-maven.md)
* [How to Develop AEM Projects using IntelliJ IDEA](../../../sites/developing/using/ht-intellij.md)
* [How to use the VLT Tool](../../../sites/developing/using/ht-vlttool.md)
* [How to use the Proxy Server Tool](../../../sites/developing/using/ht-proxy-server.md)
* [Dialog Conversion Tool](../../../sites/developing/using/dialog-conversion.md)
* [AEM Repo Tool](../../../sites/developing/using/aem-repo-tool.md)

Tools that facilitate creation of new projects:

* [AEM Project Archetype](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype)
* [AEM Lazybones Templates](https://github.com/Adobe-Consulting-Services/lazybones-aem-templates)

>[!NOTE]
>
>Following tutorial might be of interest for starting a new AEM project:  
>[Getting Started with AEM Sites Part 1 - Project Setup](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part1.html)

