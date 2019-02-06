---
title: AEM Repo Tool
seo-title: AEM Repo Tool
description: The AEM Repo Tool is a simple solution to transfer JCR content between your local filesystem and the AEM server via the command line comparable to FTP. The AEM Repo Tool is similar to the Jackrabbit FileVault tool, but is faster, has minimal dependencies, and is a simple bash script.
seo-description: The AEM Repo Tool is a simple solution to transfer JCR content between your local filesystem and the AEM server via the command line comparable to FTP. The AEM Repo Tool is similar to the Jackrabbit FileVault tool, but is faster, has minimal dependencies, and is a simple bash script.
uuid: 52d13379-2958-4470-a287-2ecc55171b08
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: development-tools
content-type: reference
discoiquuid: 5ed187db-8b85-49c3-8616-2867ad2a0438
index: y
internal: n
snippet: y
---

# AEM Repo Tool{#aem-repo-tool}

The AEM Repo Tool is a simple solution to transfer JCR content between your local filesystem and the AEM server via the command line comparable to FTP. The AEM Repo Tool is similar to the [Jackrabbit FileVault tool](../../../sites/developing/using/ht-vlttool.md), but is faster, has minimal dependencies, and is a simple bash script.

This tool simplifies the transfer of files for the developer and also can be integrated into IntelliJ and Eclipse to make development even more efficient.

### Overview {#overview}

For a given path inside a `jcr_root` filevault structure on the filesystem, AEM Repo Tool creates a package with a single filter for the entire subtree and pushes that to the server (similar to FTP `put`), fetches it from the server ( `get`) or compares the differences ( `status` and `diff`).

The tool does not support multiple filter paths or FileVault's `filter.xml`.

>[!CAUTION]
>
>Please note that the AEM Repo Tool will always overwrite the entire file or directory specified.

### Download and Documentation {#download-and-documentation}

The [AEM Repo Tool is available on GitHub via this link](https://github.com/Adobe-Marketing-Cloud/tools/tree/master/repo) along with detailed installation and usage instructions.

If you wish to download the source of the AEM Repo Tool, refer to the GitHub project linked below.

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open tools project on GitHub](https://github.com/Adobe-Marketing-Cloud/tools)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/tools/archive/master.zip)

