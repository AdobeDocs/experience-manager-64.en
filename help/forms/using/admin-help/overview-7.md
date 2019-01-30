---
title: Basics of configuring forms
seo-title: Basics of configuring forms
description: null
seo-description: Learn about the various forms services that help you create interactive data capture applications.
uuid: ddee4c74-66f2-4beb-bb28-f7c4cc13ca35
acrolinxdate: 2016-05-31T07 02 22.872-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/overview_7_admin_5e12de0b318c6865_2348_report.xml
acrolinxsentences: 10
acrolinxwords: 182
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e0475688-0b89-4a03-a1e7-bd23648640ed
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Basics of configuring forms{#basics-of-configuring-forms}

The Forms service enables you to create interactive data capture client applications that validate, process, transform, and deliver forms typically created in Designer. Form authors develop a single form design that the Forms service renders in various formats:

* as PDF in Adobe Reader or in a browser
* as HTML in various browser environments including a compliant XHTML 1.0 rendering
* as form Guides in various browser environments that support Adobe Flash Player.

For additional information about the Forms service, see [Services Reference](http://www.adobe.com/go/learn_aemforms_services_63).

Using the Forms page in administration console, you can configure the behavior of the Forms service. These settings apply to all invocations of the service. Any parameters sent through the AEM forms SDK override the settings set in administration console; however, they affect only that particular invocation.

After you change the Forms settings in administration console, click Save. You do not need to restart the server for the changes to take effect. However, you may need to stop and restart the Forms service when configuring cache mode settings. (See [Starting and stopping services](../../../forms/using/admin-help/starting-stopping-services.md#starting-and-stopping-services).)
