---
title: Log files
seo-title: Log files
description: null
seo-description: Events such as run-time or startup errors are recorded to the application server log files, which can be  opened using any text editor.
uuid: 9e0b290f-3d46-45e2-a8a7-b0ea422e4b47
acrolinxdate: 2016-05-31T07 01 56.757-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/log_files_admin_5e12de0b318c6865_2336_report.xml
acrolinxsentences: 6
acrolinxwords: 123
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: bbc7f2cd-1162-46aa-a9db-8c0be2605ada
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Log files{#log-files}

Events such as run-time or startup errors are recorded to the application server log files. If you have any problems deploying to the application server, you can use the log files to help you find the problem. You can open the log files using any text editor.

(JBoss) The following log files are located in the *[appserver root]*/server/*[server]*/log directory:

* boot.log
* server.log.*[yyyy-mm-dd]*
* server.log

(WebLogic) Domain log files are located in the *[appserverdomain]* directory, and server log files are located in the *[appserverdomain]/servers/[appserver name]/logs *directory:

* access.log 
* *[appserver name]*.log 
* *[appserver name]*.out.*[incremental number]*

(WebSphere) The following log files are located in the *[appserver root]*/profiles/default/logs/*[appserver name]* directory:

* SystemErr.log
* SystemOut.log
* StartServer.log

