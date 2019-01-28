---
title: Development Tools
seo-title: Development Tools
description: null
seo-description: To develop your JCR, Apache Sling or AEM applications, a number of tool sets are available
uuid: 81c54c99-9cb9-4249-8a38-f4cb4782ac96
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: development-tools
content-type: reference
discoiquuid: 7aa277df-2395-405c-bc5d-e641f4e45764
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Development Tools{#development-tools}

To develop your JCR, Apache Sling or AEM applications, the following tool sets are available:

* one set consisting of [CRXDE Lite](../../developing/using/developing-with-crxde-lite.md) and WebDAV. CRXDE Lite is embedded into CRX/AEM and enables you to perform standard development tasks in the browser. With CRXDE Lite, you can create and edit files (like .jsp and .java), folders, templates, components, dialogs, nodes, properties** **and bundles while logging and integrating with SVN.   
  CRXDE Lite is recommended when you do not have direct access to the CRX/AEM server, when you develop an application by extending or modifying the out-of-the-box components and Java bundles or when you do not need a dedicated debugger, code completion and syntax hightlighting.

* one set consisting of an Integrated Development Environment (for example: [Eclipse](../../developing/using/howto-projects-eclipse.md) or [IntelliJ](../../developing/using/ht-intellij.md)), a build tool (for example: [Apache Maven](../../developing/using/ht-projects-maven.md)), FileVault which has been developed by Adobe to map a repository to a file system, a version control system (for example: Subversion), a bug tracker system (for example: Jira), a central dependency management system (for example: Apache Archiva) and a build automation system (for example: Apache Continuum).  
  This setup allows you to fully integrate your application (content, code, configuration) into any development environment and process.The link between the different elements is the file system representation of the repository through FileVault, as all of the aforementioned development tools can work with files.

### Extensions for Integrated Development Environments {#extensions-for-integrated-development-environments}

Adobe released the following extensions:

* [AEM Eclipse Extension](../../developing/using/aem-eclipse.md)
* [AEM Brackets Extension](../../developing/using/aem-brackets.md)
* [AEM IntelliJ Extension](https://github.com/headwirecom/aem-ide-tooling-4-intellij/blob/master/documenation/AEM%20Tooling%20Plugin%20for%20IntelliJ%20IDEA.pdf) (from Headwire)

### Other Tools {#other-tools}

AEM ships with other tools that facilitate development:

* [Dialog Editor](../../developing/using/dialog-editor.md)
* [Using Translator to Manage Dictionaries  
  ](../../developing/using/i18n-translator.md)
* [Site Importer](../../developing/using/site-importer.md)
* [Managing Packages Using Maven](../../developing/using/vlt-mavenplugin.md)
* [How to Develop AEM Projects Using Eclipse](../../developing/using/howto-projects-eclipse.md)
* [How to Build AEM Projects using Apache Maven](../../developing/using/ht-projects-maven.md)
* [How to Develop AEM Projects using IntelliJ IDEA](../../developing/using/ht-intellij.md)
* [How to use the VLT Tool](../../developing/using/ht-vlttool.md)
* [How to use the Proxy Server Tool](../../developing/using/ht-proxy-server.md)
* [Dialog Conversion Tool](../../developing/using/dialog-conversion.md)
* [AEM Repo Tool](../../developing/using/aem-repo-tool.md)

Tools that facilitate creation of new projects:

* [AEM Project Archetype](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype)
* [AEM Lazybones Templates](https://github.com/Adobe-Consulting-Services/lazybones-aem-templates)

>[!NOTE]
>
>Following tutorial might be of interest for starting a new AEM project:  
>[Getting Started with AEM Sites Part 1 - Project Setup](/content/help/en/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop/part1)

