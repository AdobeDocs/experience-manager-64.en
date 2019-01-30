---
title: Purging process data
seo-title: Purging process data
description: null
seo-description: Process data that is generated when a long-lived process is invoked can become too large, resulting in lower AEM forms performance and the use of unnecessary disk space. See how you can purge process data.
uuid: 92ec9f7e-6ca0-4367-a4b9-6f93a72c7d7d
acrolinxdate: 2016-05-31T07 02 42.280-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/purging_process_data_admin_5e12de0b318c6865_2355_report.xml
acrolinxsentences: 8
acrolinxwords: 151
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 7f0734c6-3832-41d5-818f-0a30935758be
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Purging process data{#purging-process-data}

Process data that is generated when a long-lived process is invoked can become too large, resulting in lower AEM forms performance and the use of unnecessary disk space. It is good practice to purge process data when records are no longer necessary. AEM forms provides several means of purging process data:

* You can use administration console to perform a one-time purge of obsolete records related to long-lived processes, or to schedule regular automatic purges. (See [Purge records from the Job Manager database](../../../forms/using/admin-help/purge-records-job-manager-database.md#purge-records-from-the-job-manager-database).)
* You can use the AEM forms Java API and web service API to programmatically purge process data related to long-lived processes. (See "Purging Process Data" in [Programming with AEM forms](http://www.adobe.com/go/learn_aemforms_programming_63).)
* Use the process purge tool to purge processes based on the process name and other parameters. For details, see the process purge tool readme file, located in *[aem_forms root]*\sdk\misc\Foundation\ProcessPurgeTool\ReadMe.txt.

