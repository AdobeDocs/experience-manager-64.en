---
title: Considerations when running AdministrationConsole
seo-title: Considerations when running AdministrationConsole
description: null
seo-description: This document lists a few points to consider when running Administration Console.
uuid: f0337a4a-4f03-4a11-aa82-e0acf632249e
acrolinxdate: 2016-05-31T06 58 31.132-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/considerations_running_administration_console_admin_5e12de0b318c6865_2306_report.xml
acrolinxsentences: 6
acrolinxwords: 124
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_application_server
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 27965166-6bb6-47cb-86b7-ec1fc02d2612
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Considerations when running AdministrationConsole{#considerations-when-running-administrationconsole}

These are some things to consider when running Administration Console:

* If you access administration console using the URL http://*[hostname]*:*[port]*/adminui, the specified host name cannot contain underscore characters. Otherwise, links to some areas of the administration console may not work properly.
* If you run administration console in Windows Explorer on a Japanese OS, you may encouter these problems:

    * Clicking a link returns you to the login page instead of to the expected link.
    * Clicking a link displays a permission error.

  Best practice is run administration console from another browser, such as Mozilla Firefox, to ensure that no links will fail.

* Do not use backslash characters () when performing searches in administration console.

