---
title: Set up environment for AEM Forms app
seo-title: Set up environment for AEM Forms app
description: null
seo-description: Hardware, software, and licenses to build and deploy the AEM Forms app.
uuid: ced177e7-a5b9-4a6f-83d4-1ff23b557fa8
acrolinxdate: 2016-05-31T06 50 30.178-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/setup_environment_mobile_workspace_admin_5e12de0b318c6865_2166_report.xml
acrolinxsentences: 7
acrolinxwords: 272
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 8eb39fad-1a32-46de-a588-50291344402a
firstpublishqadate: 2013-02-20T08 58 22.917-0500
isreadyforlocalization: false
lastpublishqadate: 2015-11-20T08 18 46.009-0500
publishqadate: 2015-11-20T08 18 46.009-0500
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/mobile-workspace/setup-environment-mobile-workspace.html
index: y
internal: n
snippet: y
---

# Set up environment for AEM Forms app{#set-up-environment-for-aem-forms-app}

You need the following hardware, software, and licenses to build and deploy the AEM Forms app:

## For Windows devices {#for-windows-devices}

* Microsoft Windows 8.1 or Windows 10
* Microsoft Visual Studio 2015
* Microsoft Visual Studio Tools for Apache Cordova

## For iOS devices {#for-ios-devices}

* Intel-based Apple Mac running Mac OS X 10.9.5 or above
* iOS SDK 8.4 or above
* Xcode version: Xcode 6.4 for OS X or above
* Membership of the iOS Developer Enterprise program
* Enterprise certificate for distributing in-house iOS apps
* Apple iPad with iOS 8.4 or later

## For Android devices {#for-android-devices}

* Android Development Toolkit (ADT bundle) that can be downloaded from [http://developer.android.com/sdk/index.html](http://developer.android.com/sdk/index.html)
* If the environment is set up on a MAC system, the ADT should be installed in the Applications folder.
* If the ADT is installed in any other location on MAC, or if the environment is set up on a Windows system, the ADT SDK path needs to be updated in `local.properties` file that is available in `src\android` folder in the extracted the source archive `mobileworkspace-src.zip`. In this file, point the `sdk.dir` variable to ADT SDK location on your desktop.

>[!NOTE]
>
>The adobe-lc-mobileworkspace-src.zip contains PhoneGap SDK 5.0. Ensure that PhoneGap SDK is not pre-installed.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

>[!MORE_LIKE_THIS]
>
>* [Set up your environment](../../forms/using/setup-environment-mobile-workspace.md)
>* [Set up the Xcode project and build the iOS app](../../forms/using/setup-xcode-project-build-installer.md)
>* [Set up the Eclipse project and build the Android app](../../forms/using/setup-eclipse-project-build-installer.md)
>* [Set up the Visual Studio project and build the Windows app](../../forms/using/setup-visual-studio-project-build-installer.md)
>* [Distribute the AEM Forms app](../../forms/using/distribute-mobile-workspace-app.md)
>* [Building a secure AEM Forms app for iOS](../../forms/using/building-secure-mobile-workspace-app.md)
