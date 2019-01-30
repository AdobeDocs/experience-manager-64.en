---
title: "DB2 database: Running a process weekly"
seo-title: "DB2 database: Running a process weekly"
description: null
seo-description: See how you can improve the performance of your AEM forms DB2 database.
uuid: 89838118-bee4-4831-a1ef-c7a11912c29e
acrolinxdate: 2016-05-31T06 59 26.606-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/db2_database_running_process_weekly_admin_5e12de0b318c6865_2313_report.xml
acrolinxsentences: 9
acrolinxwords: 138
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: a7c85475-ea43-496a-90d4-bcd92e6ef057
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# DB2 database: Running a process weekly{#db-database-running-a-process-weekly}

If your AEM forms DB2 database begins to run slowly, running the following process on a weekly basis can improve its performance:

1. Start DB2 Control Center:

   (Windows) Select Start &gt; Programs &gt; IBM DB2 &gt; General Administratison Tools &gt; Control Center.

   (Linux and UNIX) From a command prompt, type the `db2jcc` command.

1. In the DB2 Control Center object tree, click All Databases. 
1. Click the database you created for AEM forms and click the Tables folder.
1. Select all the database tables in the contents pane, right-click them and select Run Statistics.
1. Go to Statistics &gt; Index Statistics.
1. Select Collect Statistics For All Indexes, select Collect Statistics For Indexes With Extended Detailed Statistics, and then click OK.

A message appears when the process is completed. Close the message.
