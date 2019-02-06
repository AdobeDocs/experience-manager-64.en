---
title: Troubleshoot AEM Forms Android app build issues
seo-title: Troubleshoot AEM Forms Android app build issues
description: Steps to troubleshoot AEM Forms Android App build issues
seo-description: Steps to troubleshoot AEM Forms Android App build issues
page-status-flag: never-activated
uuid: 1c9811d7-4814-4f9f-aea5-30fb9a5ab02c
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: forms-app
discoiquuid: 62ed84ed-af2b-4d23-9ae0-200f1d9e089e
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

