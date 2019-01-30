---
title: Configuring SSL on Windows Vista
seo-title: Configuring SSL on Windows Vista
description: null
seo-description: Learn how to configure SSL on Windows Vista.
uuid: afbc1f4d-1f37-47a3-8882-05f4a1685d2b
acrolinxdate: 2016-05-31T06 57 57.171-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/configuring_ssl_windows_vista_admin_5e12de0b318c6865_2302_report.xml
acrolinxsentences: 7
acrolinxwords: 169
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 21cbe555-3603-49cc-9eac-f4ed41c40284
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring SSL on Windows Vista{#configuring-ssl-on-windows-vista}

To configure SSL on Windows Vista™, you need an SSL certificate with RSA keys for authentication. You can use the Java keytool to create the certificate.

>[!NOTE]
>
>Windows Vista will not work with DSA keys.

You can run keytool by using a single command that includes all the information that is required to create the certificate and keystore.

**Create an SSL certificate**

1. In a command prompt, navigate to *[JAVA HOME]*/bin and type the following command to create the certificate and keystore:

   `keytool -genkey -keyalg RSA -dname "CN=`*Host Name* `, OU=`*Group Name* `, O=`*Company Name* `,L=`*City******Name* `, S=`*State* `, C=`*Country Code* `" -alias`*"LC Cert"* `-keypass` `*key*`*_**password* `-keystore`*keystorename* `.keystore`

   >[!NOTE]
   >
   >Replace *[JAVA_HOME] with the directory where the JDK is installed, and replace the text in italic with values that correspond with your environment.*

1. Type `changeit` as the password. This password is the default for a Java installation, and the system administrator may have changed it.

