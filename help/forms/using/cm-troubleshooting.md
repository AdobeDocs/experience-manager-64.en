---
title: "Correspondence Management: Troubleshooting"
seo-title: Correspondence Management Troubleshooting
description: null
seo-description: Correspondence Management Troubleshooting
uuid: 07b4d402-ccc6-4e5b-8ceb-af10513065c8
acrolinxdate: 2016-05-31T06 51 38.959-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/cm_troubleshooting_admin_5e12de0b318c6865_2185_report.xml
acrolinxsentences: 9
acrolinxwords: 153
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: 903b4c01-5543-43ce-b8b6-4ca867cad1f1
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Correspondence Management: Troubleshooting{#correspondence-management-troubleshooting}

## Errors when saving a letter {#errors-when-saving-a-letter}

### Issue {#issue}

One of the following errors displayed when saving a letter:

* Data binding not present for the text module
* Please provide the property information needed for the following

### Reason {#reason}

These errors could occur due to one of the following:

* A data dictionary is bound to the letter but is not present on the server. 
* A data dictionary is bound to the letter but has an underscore (_) in its name.

### Workaround {#workaround}

Ensure that the data dictionary you are using in the letter is present on the server and does not have an underscore (_) in its name.

## Error when previewing a letter {#error-when-previewing-a-letter}

### Issue {#issue-1}

While previewing a letter, the error "Error in loading letter: Could not import asset from XML input" appears even when a previously unpublished text asset in the letter is published.

### Workaround {#workaround-1}

Reset the letter cache on the publish instance using the following steps and then retry viewing the letter:

1. Go to **http://[server]:[port]/[contextPath]/system/console/configMgr** and log in as Admin.
1. Select **Correspondence Management Configurations**.
1. In **Correspondence Management Configurations**, disable **Enable Letter Cache **and then click** Save.**
1. Enable **Enable Letter Cache** and then click **Save**.
1. Retry viewing the letter.

