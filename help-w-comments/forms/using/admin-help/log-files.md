---
title: Log files
seo-title: Log files
description: Events such as run-time or startup errors are recorded to the application server log files, which can be  opened using any text editor.
seo-description: Events such as run-time or startup errors are recorded to the application server log files, which can be  opened using any text editor.
uuid: 30547ee5-ac8e-4496-a492-97c763cf1d5b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_aem_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: a9fff4f0-54c8-49b1-a78c-dcaa2606a802
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

