---
title: Encryption Support for Configuration Properties
seo-title: Encryption Support for Configuration Properties
description: null
seo-description: null
uuid: d080edc1-1d88-4567-b75d-1704012d6781
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SITES
discoiquuid: fa1c85b8-2d12-452d-a841-bed0831dbf6b
index: y
internal: n
snippet: y
---

# Encryption Support for Configuration Properties{#encryption-support-for-configuration-properties}

### Overview {#overview}

This feature allows all OSGi configuration properties to be stored in a protected encrypted form instead of clear text. The form in the the Web Console UI is used to create encrypted text from clear text using the system wide encryption master key.

OSGi Configuration Plugin support was added in order to decrypt the property before it is used by a service.

>[!NOTE]
>
>Services that expect an encrypted value need to use the IsProtected check to see if the value is encrypted before trying to decrypt it, as it may already have been decrypted.

### Enabling Encryption Support {#enabling-encryption-support}

These steps show how to encrypt the SMTP password for the Mail service. You can complete these steps for an OSGI property you want encrypted.

1. Go to the AEM Web Console at *http://serveraddress:serverport/system/console/configMgr*
1. In the upper left corner, go to **Main - Crypto Support**

   ![](assets/chlimage_1-339.png)

1. The **Adobe Experience Manager Web Console Crypto Support** page is displayed.

   ![](assets/screen_shot_2018-08-01at113417am.png)

1. In the **Plain Text** field, enter the text of the sensitive data you want to protect.
1. Select **Protect**. The Protected text is displayed as encrypted text.

   ![](assets/screen_shot_2018-08-01at113844am.png)

1. Copy the Protected Text from Step#5 and paste it into OSGI Form value. In this example, the ecrypted **SMTP password** is added to the *Day CQ Mail Service*.

   ![](assets/screen_shot_2016-12-18at105809pm.png)

1. Save the Day CQ Mail Service properties. The SMTP password will now be sent as an encrypted value.

### Decryption Support {#decryption-support}

AEM now provides a Configuration Plugin to decrypt configuration properties. This AEM Plugin will automatically decrypt and retrieve the clear text properties. 
