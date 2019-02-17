---
title: "Correspondence Management: Troubleshooting"
seo-title: Correspondence Management Troubleshooting
description: Correspondence Management Troubleshooting
seo-description: Correspondence Management Troubleshooting
uuid: d59288c1-09e7-4ffa-9950-ef0cffda969b
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: fdea54c5-e7d0-4453-b4b2-016b7c5ac574
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

