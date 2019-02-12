---
title: Considerations when running AdministrationConsole
seo-title: Considerations when running AdministrationConsole
description: This document lists a few points to consider when running Administration Console.
seo-description: This document lists a few points to consider when running Administration Console.
uuid: f877ad78-8326-4f64-b15d-a3b61cbf47ec
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_application_server
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: b01e8f9b-e389-4807-a0f9-0e5f70dd816a
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

