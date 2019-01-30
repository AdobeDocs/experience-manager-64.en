---
title: Distribute AEM Forms app
seo-title: Distribute AEM Forms app
description: null
seo-description: Use Mobile Device Management (MDM) for the large-scale deployment of apps on mobile devices.
uuid: 861c7d54-f333-4299-bc69-e4a32a4f399e
acrolinxdate: 2016-05-31T06 50 07.277-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/distribute_mobile_workspace_app_admin_5e12de0b318c6865_2157_report.xml
acrolinxsentences: 12
acrolinxwords: 249
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 1ee7af91-ac73-4173-9d9b-8ca035fc7f80
firstpublishqadate: 2013-02-20T08 58 59.097-0500
isreadyforlocalization: false
lastpublishqadate: 2015-11-20T08 18 46.748-0500
publishqadate: 2015-11-20T08 18 46.748-0500
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-1/mobile-workspace/distribute-mobile-workspace-app.html
index: y
internal: n
snippet: y
---

# Distribute AEM Forms app{#distribute-aem-forms-app}

Mobile Device Management (MDM) enables the large-scale deployment of apps on mobile devices.

>[!NOTE]
>
>This distribution is applicable for iOS and Android devices only.

## Main features generally provided by MDM solutions: {#main-features-generally-provided-by-mdm-solutions}

* Enable device enrollment in your enterprise environment  
* Allow the configuring and updating device settings  
* Enforce security compliance.  
* Secure mobile access to corporate resources

An MDM solution along with Mobile Application Management, allows you to manage internal, public, and purchased apps across the mobile devices in your enterprise.

The MDM administrator can upload both ipa and apk files to the MDM server and control the users who can access the ipa or apk files. The administrator can also control the profile setting corresponding to each application.

## Profile settings affecting the AEM Forms app <br> {#profile-settings-affecting-the-aem-forms-app-br}

The following Profile settings on your device will affect the functioning of the AEM Forms app on you device:

* **Allow use of camera** in the **Device functionality** section

If you disable **Allow use of camera**, the camera feature of the [Photograph annotation](../../forms/using/add-attachments.md) will not function. You need to enable this option to use the camera in the app.

* **Require passcode on device** in the Passcode policies section

To enable **encryption of application data**, you are recommended to enable the **passcode** on your device. If passcode is not set on device, application data stored on the device is not encrypted.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

>[!MORE_LIKE_THIS]
>
>* [Set up your environment](../../forms/using/setup-environment-mobile-workspace.md)
>* [Set up the Xcode project and build the iOS app](../../forms/using/setup-xcode-project-build-installer.md)
>* [Set up the Eclipse project and build the Android app](../../forms/using/setup-eclipse-project-build-installer.md)
>* [Set up the Visual Studio project and build the Windows app](../../forms/using/setup-visual-studio-project-build-installer.md)
>* [Distribute the AEM Forms app](../../forms/using/distribute-mobile-workspace-app.md)
>* [Building a secure AEM Forms app for iOS](../../forms/using/building-secure-mobile-workspace-app.md)
