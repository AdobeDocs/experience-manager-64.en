---
title: Troubleshoot AEM Forms Android app build issues
seo-title: Troubleshoot AEM Forms Android app build issues
description: null
seo-description: Steps to troubleshoot AEM Forms Android App build issues
page-status-flag: never-activated
uuid: ab8e7b57-423b-49ce-890b-ca037ae68a32
acrolinxdate: 2018-08-21T00 13 31.358-0400
acrolinxlastcheckedby: anujkapo
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/troubleshoot_aem_forms_android_app_build_issues_krs_workflow_a9d8be2d910fe9fc_218_report.xml
acrolinxsentences: 14
acrolinxwords: 174
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: forms-app
discoiquuid: 8c862b61-49ce-4da1-996b-0ca1a5933d82
preview: true
index: y
internal: n
snippet: y
---

# Troubleshoot AEM Forms Android app build issues{#troubleshoot-aem-forms-android-app-build-issues}

This article describes the error messages that might be displayed while building AEM Forms Android app and the steps to resolve them.

The error messages described in this article are:

* [Unsupported version of Gradle](../../forms/using/troubleshoot-aem-forms-android-app-build-issues.md#main-pars-header)
* [Gradle and Android Gradle plug-in compatibility issues](../../forms/using/troubleshoot-aem-forms-android-app-build-issues.md#main-pars-header-857885282)

## Unsupported version of Gradle {#unsupported-version-of-gradle}

**Error Message:** The project is using an unsupported version of Gradle.

The error message is displayed when you are using an unsupported version of Gradle and you select **Build APK** option from the **Build** menu on the Android Studio user interface.

**Resolution: **Click **Fix Gradle wrapper and re-import project ** to resolve the issue.

![](assets/gradle_unsupported_version.png) 

## Gradle and Android Gradle plug-in compatibility issues {#gradle-and-android-gradle-plug-in-compatibility-issues}

**Error Message:** The versions of the Android Gradle plugin and Gradle are not compatible.

The error message is displayed when you select **Build APK** option from the **Build** menu on the Android Studio user interface. 

![](assets/gradle_plugin_compatibility.png)

**Resolution: **Open **gradle-wrapper.properties** and edit **distributionUrl**.

For example, the Android Studio console recommends downgrading the Gradle version to 3.5. Edit the version in **distributionUrl **of** gradle-wrapper.properties** file.

Select **Build** &gt; **Build APK **to resolve the error and generate the .apk file. 

![](assets/gradle_wrapper_properties.png)

