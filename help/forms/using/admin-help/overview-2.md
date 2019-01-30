---
title: Basics of managing certificates and credentials
seo-title: Basics of managing certificates and credentials
description: null
seo-description: Learn about the basics of managing certificates and credentials.
uuid: 9cc99865-d132-47f0-a35c-faca5f3f389f
acrolinxdate: 2016-05-31T07 02 18.990-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/overview_2_admin_5e12de0b318c6865_2345_report.xml
acrolinxsentences: 16
acrolinxwords: 293
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_certificates_and_credentials
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: ae18ff48-79d4-4db5-959b-81271b414adb
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Basics of managing certificates and credentials{#basics-of-managing-certificates-and-credentials}

A *credential* contains your private key information needed for signing or identifying documents. A *certificate* is public key information that you configure for trust. AEM forms uses certificates and credentials for several purposes:

* Acrobat Reader DC extensions uses a credential to enable Adobe Reader usage rights in PDF documents. (See [Configuring credentials for use with Acrobat Reader DC extensions](../../../forms/using/admin-help/configuring-credentials-acrobat-reader-dc.md#configuring-credentials-for-use-with-acrobat-reader-dc-extensions).)
* You can configure Rights Management to display credentials for use in Acrobat only from trusted issuers. (See [Configure Rights Management display settings](../../../forms/using/admin-help/configuring-client-server-options.md#configure-document-security-display-settings).) The Common Name (CN) must be present in the certificate.
* The Signature service accesses certificates and credentials. For details on the Signature service, see [Services Reference](http://www.adobe.com/go/learn_aemforms_services_63).

**Generating a pair key**

AEM forms uses its Trust Store to store and manage certificates, credentials, and certificate revocation lists (CRLs). Additionally, you can use an independent Hardware Security Module (HSM) device to store private keys.

AEM forms does not provide any option to generate a key pair. However, you can generate it using tools, such as Java keytool, and import it in AEM forms Trust Store. For more information on Java keytool, see the following:

[http://docs.oracle.com/javase/tutorial/security/toolsign/step3.html](http://docs.oracle.com/javase/tutorial/security/toolsign/step3.html)

[http://docs.oracle.com/cd/E19798-01/821-1841/gjrgy/index.html](http://docs.oracle.com/cd/E19798-01/821-1841/gjrgy/index.html)

[http://blogs.adobe.com/livecycle/2010/01/creating_ssl_keys_and_certific.html](http://blogs.adobe.com/livecycle/2010/01/creating_ssl_keys_and_certific.html)

The following signature types are supported and can be imported in AEM forms:

* XML signature
* XMLTimeStampToken 
* RFC 3161 TimeStampToken
* PKCS#7
* PKCS#1
* DSA Signatures

**Handling lost or compromised key**

If you suspect that your key is lost or has been compromised, take the following actions:

1. Inform the certifying authority, so that they add the compromised key on the certificate revocation list to revoke the key.
1. Obtain a new key and its certificates from the certifying authority.
1. Sign the documents that were signed using the compromised key again using the new key.

