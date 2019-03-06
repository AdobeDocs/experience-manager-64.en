---
title: Distribute AEM Forms app
seo-title: Distribute AEM Forms app
description: Use Mobile Device Management (MDM) for the large-scale deployment of apps on mobile devices.
seo-description: Use Mobile Device Management (MDM) for the large-scale deployment of apps on mobile devices.
uuid: 5a1ef0bb-bea6-452c-8d57-c3a540b3c3d5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 637d7189-18bd-45b9-a421-e5816687bc8e
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

<!--
<related-links>
<a href="../../forms/using/setup-environment-mobile-workspace.md" target="_blank">Set up your environment</a>
<a href="../../forms/using/setup-xcode-project-build-installer.md" target="_blank">Set up the Xcode project and build the iOS app</a>
<a href="../../forms/using/setup-eclipse-project-build-installer.md" target="_blank">Set up the Eclipse project and build the Android app</a>
<a href="../../forms/using/setup-visual-studio-project-build-installer.md" target="_blank">Set up the Visual Studio project and build the Windows app</a>
<a href="../../forms/using/distribute-mobile-workspace-app.md" target="_blank">Distribute the AEM Forms app</a>
<a href="../../forms/using/building-secure-mobile-workspace-app.md" target="_blank">Building a secure AEM Forms app for iOS</a>
</related-links>
-->

