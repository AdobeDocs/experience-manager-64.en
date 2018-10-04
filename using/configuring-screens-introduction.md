---
title: Configuring and Deploying AEM Screens
seo-title: Configuring and Deploying Screens
description: null
seo-description: The AEM Screens player is available for Android, Chrome OS and Windows. This page describes the configuration and deployment of AEM Screens followed by Device Registration process.
uuid: bac0c6c2-d818-4df6-b443-27bea175531f
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/configuring-screens-introduction
contentOwner: Jyotika syal
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-06-27T17 40 59.077-0400
cq-lastmodifiedby: jsyal
cq-lastreplicated: 2018-06-18T10 26 44.348-0400
cq-lastreplicatedby: jsyal
cq-lastreplicationaction: Activate
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: screens
cq-template: /apps/help/templates/article-3
discoiquuid: 261b8c5a-28ef-4212-894b-c6645e7bb784
firstPublishExternalDate: 2017-10-31T16:18:07.311-0400
jcr-created: 2018-02-07T08 01 17.521-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-06-18T10:26:44.096-0400
lochandoffdate: 2018-04-30T03 26 42.597-0400
lr-lastreplicatedby: jsyal@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/screens;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/screens
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Deploying Screens
publishexternaldate: 2018-06-18T10 26 44.096-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring-screens-introduction.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/aem-screens-introduction/configuring-screens
sha1: 9419c0e097bc168d09e580317dc6068988107bf3
topicBrowsingSortDate: 2018-06-18T10:26:44.096-0400
index: y
internal: n
snippet: y
translate: y
---

# Configuring and Deploying AEM Screens

This page shows how to install and configure the Screens players on your devices.

The AEM Screens player is available for Android, Chrome OS and Windows.

>[!NOTE]
>
>To download **AEM Screens Player**, click [here](https://download.macromedia.com/screens/).
>
>AEM Screens is also available in **Google Play**. 
>
>For implementation of Chrome OS Player, see [**Chrome Management Console**](/content/help/en/experience-manager/6-4/sites/administering/using/implementing-chrome-os-player.html?cq_ck=1513900475345) for more information.

## Server Configuration

>[!NOTE]
>
>**Important**:
>
>AEM Screens player does not make use of the Cross-Site Request Forgery (CSRF) token. Therefore, in order to configure and AEM server to be ready to use for AEM Screens, skip the referrer filter by allowing empty referrers.

The following key points below helps to configure and AEM server to be ready to use for AEM Screens:

>[!NOTE]
>
>**Recommendation:**
>
>It is recommended to use HTTPS for AEM Screens Server in production use.

### AEM Screens Player for Android

To install and configure the Screens player on your Android device:

1. Download Android Player from [AEM Screens Player Downloads](https://download.macromedia.com/screens/).

1. Install the application and tap **DONE**.

   ![](assets/chlimage_1.png)

1. Find the **AEM Settings** widget and drag and drop it to the home screen.

   ![](assets/chlimage_1.jpeg)

1. Open the settings widget from the home screen and configure it accordingly.

   ![](assets/chlimage_1.png)

   >[!NOTE]
   >
   >
   >
   >The **device id**, **User **and **Password** will be filled by the registration process.

## Device Registration

The devices registration process is done on 2 separate machines:

* The actual device to be registered, for example your Signage Display
* The AEM server that is used to register your device

1. On your device, start the AEM Screens Player. The registration UI is shown.

   ![](assets/chlimage_1.png)

1. In AEM, navigate to the **Devices** folder of your project.

   >[!NOTE]
   >
   >
   >
   >To get more information on creating a new project for Screens in the AEM dashboard, see [Creating and Managing Screens Project](/content/help/en/experience-manager/6-4/sites/authoring/using/creating-a-screens-project).
   >
   >

1. Tap/click the **Device Manager** button in the action bar.

   ![](assets/chlimage_1.png)

1. Tap/click the **Device Registration** button on the top right.

   ![](assets/chlimage_1.png)

1. Select the required device (same as step 1) and tap/click **Register Device**.

   ![](assets/chlimage_1.png)

1. In AEM, wait for the device to send its registration code.

1. In your device, check the **Registration Code**.

   ![](assets/chlimage_1.png)

1. If the **Registration Code** is the same on both machines, tap/click **Validate** button in AEM.

   ![](assets/chlimage_1.png)

1. Set the desired name for the device, and select** Register **button.

   ![](assets/chlimage_1.png)

   >[!NOTE]
   >
   >
   >
   >If you don't set a name, it will use its unique identifier as name.

1. Tap/click** Finish** to complete the registration process .

   ![](assets/chlimage_1.png)

   >[!NOTE]
   >
   >
   >
   >The **Go Back** button would allow you to register a new device.
   >
   >
   >The **Assign Display** button would let you directly add the device to a display.

In your device, the registration UI should be updated to show the device identifier.

![](assets/chlimage_1.png)

In AEM, the device should be added to the list and remain unassigned. To learn how to assign it, see [Device Assignment](/content/help/en/experience-manager/6-4/sites/authoring/using/managing-devices).

Before, you learn device assignment, it is recommended you have prior knowledge on how to:

* [Manage Channels](/content/help/en/experience-manager/6-4/sites/authoring/using/managing-channels)
* [Manage Locations](/content/help/en/experience-manager/6-4/sites/authoring/using/managing-locations)
* [Manage Displays](/content/help/en/experience-manager/6-4/sites/authoring/using/managing-displays)

![](assets/chlimage_1.png) 

### Limitations on Device Registration

System wide user password restrictions might cause failure in the device registration. The device registration uses a random generated password to create the device user.

If the password is restricted by the *AuthorizableActionProvider* configuration, creating the device user might fail.

>[!NOTE]
>
>The current generated random password is composed of 36 ASCII characters, ranging from 33 - 122 (includes almost all special characters).

When the device registration fails, check the *** [AuthorizableActionProvider](http://localhost:4502/system/console/configMgr/org.apache.jackrabbit.oak.spi.security.user.action.DefaultAuthorizableActionProvider)*** configuration to see if there are any restrictions.

The following error logs show failed device registration:

```java
25.09.2016 16:54:03.140 *ERROR* [59.100.121.82 [1474844043109] POST /content/screens/svc/registration HTTP/1.1] com.adobe.cq.screens.device.registration.impl.RegistrationServlet Error during device registration
javax.jcr.nodetype.ConstraintViolationException: Password violates password constraint (^(?=.*\d).{7,9}$).
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.validatePassword(PasswordValidationAction.java:105)
        at org.apache.jackrabbit.oak.spi.security.user.action.PasswordValidationAction.onPasswordChange(PasswordValidationAction.java:76)
        at org.apache.jackrabbit.oak.security.user.UserManagerImpl.onPasswordChange(UserManagerImpl.java:308)
```

#### Additional Resources

To learn about AEM Screens Player, see [Working with Screens Player](/content/help/en/experience-manager/6-4/sites/authoring/using/working-with-screens-player).
