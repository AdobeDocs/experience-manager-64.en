---
title: Review credential use information
seo-title: Review credential use information
description: Learn how to review credential use information.
seo-description: Learn how to review credential use information.
uuid: 02af75f9-c235-470d-a98b-a2102aa31381
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cdf61cff-768b-49f7-9926-400bc96b0708
exl-id: abd62cca-edf0-4b44-94c3-7af3116b0c54
---
# Review credential use information {#review-credential-use-information}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

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
