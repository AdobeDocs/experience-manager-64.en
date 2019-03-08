---
title: Running AEM forms in maintenance mode
seo-title: Running AEM forms in maintenance mode
description: Maintenance mode is useful when performing tasks such as patching a DSC, upgrading AEM forms, or applying a service pack. Learn more about running AEM forms in maintenance mode.
seo-description: Maintenance mode is useful when performing tasks such as patching a DSC, upgrading AEM forms, or applying a service pack. Learn more about running AEM forms in maintenance mode.
uuid: 4617bdbd-f503-498b-960f-bb7db32d339b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 68232bfa-dad9-4a93-bbdb-1a2cd00fc7f3
index: y
internal: n
snippet: y
---

# Running AEM forms in maintenance mode{#running-aem-forms-in-maintenance-mode}

Maintenance mode is useful when performing tasks such as patching a DSC, upgrading AEM forms, or applying a service pack.

Avoid invoking any processes while the server is in maintenance mode. This is what happens if a process is invoked while the server is in maintenance mode:

* If the process is long-lived, it is added to the job database, but is not started. When you exit maintenance mode, AEM forms processes the long-lived jobs in its queue, even if the server was restarted while in maintenance mode.
* If the process is short-lived, it is processed right away.

**Put AEM forms in maintenance mode**

1. In a web browser, enter:

   `http://`*[hostname]* `:`*[port]* `/dsc/servlet/DSCStartupServlet?maintenanceMode=pause&user=`*[administrator username]* `&password=`*[password]*

   A "now paused" message is displayed in the browser window.

   >[!NOTE]
   >
   >If you shut down the server while it is maintenance mode, it will still be in maintenance mode when it is restarted. You must turn off maintenance mode when you are finished your maintenance tasks.

**Check whether AEM forms is running in maintenance mode**

1. In a web browser, enter:

   `http://`*[hostname]:[port]* `/dsc/servlet/DSCStartupServlet?maintenanceMode=isPaused&user=`*[administrator username]* `&password=`*[password]*

   The status is displayed in the browser window. A status of "true" indicates that the server is running in maintenance mode, and "false" indicates that the server is not in maintenance mode.

**Turn off maintenance mode**

1. In a web browser, enter:

   `http://`*[hostname]:[port]* `/dsc/servlet/DSCStartupServlet?maintenanceMode=resume&user=`*[administrator username]* `&password=`*[password]*

   A "now running" message is displayed in the browser window.

