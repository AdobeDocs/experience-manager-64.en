---
title: Review credential use information
seo-title: Review credential use information
description: null
seo-description: Learn how to review credential use information.
uuid: 8af3c1e9-540e-4320-a71d-e0866d79c1bf
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: b349b3bd-5f1d-49cc-a22a-0dda66f06505
index: y
internal: n
snippet: y
---

# Review credential use information{#review-credential-use-information}

The credential contains information describing its intended use that is accessible through the Acrobat Reader DC extensions end-user web application. You can use this information to determine the type of credential installed (either evaluation or production) and its validity dates.

1. Open a web browser and enter this URL:

   http://localhost:*[port]*/ReaderExtensions (where *[port]* is your application server’s port number)

1. Log in using the default user name and password:

   User name: administrator

   Password: password

   >[!NOTE]
   >
   >You must have administrator or super user privileges to log in using the default user name and password. To allow other users to access Acrobat Reader DC extensions, create the user accounts in User Management and grant the users the Acrobat Reader DC extensions Web Application role.

1. Select the credential alias from the Select Credential list and review the information included in the Expiration Date and Intended Use Notice.

>[!NOTE]
>
>The credential’s expiration date is also available on the Settings &gt; Trust Store Management &gt; Local Credentials page of administration console, under Expiration Date.

