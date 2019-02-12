---
title: Integration with Adobe Sign | Handling user data
seo-title: Integration with Adobe Sign | Handling user data
description: null
seo-description: null
uuid: 29dd548d-3f65-4885-8756-9144faff34c6
topic-tags: grdp
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 204dd1f0-e479-4bd9-8453-1550558b9de6
index: y
internal: n
snippet: y
---

# Integration with Adobe Sign | Handling user data{#integration-with-adobe-sign-handling-user-data}

AEM Forms integrates with Adobe Sign to enable e-signature workflows in adaptive forms to process forms or agreements for legal, sales, payroll, human resource management workflows. It allows for single and multiuser signing, sequential and simultaneous signing workflows, signing forms as an anonymous or logged-in user, and multiple ways to authenticate users.

When a signer or multiple signers sign and submit an adaptive form, an Adobe Sign agreement is generated that includes information about the signers.

For more information about AEM Forms integration with Adobe Sign, see [Using Adobe Sign in an adaptive form](../../forms/using/working-with-adobe-sign.md).

## User data and data stores {#data}

Adobe Sign enabled adaptive form includes information about the signers and may include other user data collected by the adaptive form. The Adobe Sign service saves user data with the signature within the agreement. The agreement is saved on Adobe Sign server configured in AEM Forms cloud services. In addition, if the adaptive form is configured to use the Forms Portal submit action, the agreement data is saved in the forms portal data store along with the form data.

## Access and delete user data {#access-and-delete-user-data}

User data is collected within the agreement but not saved in any of the service tables. Adobe Sign enables administrators to make their own choices on managing data they control in the service. Privacy administrators on the Adobe Sign service can list or remove agreements based on the email address of a requestor.

Adobe Sign offers a web application that allows searching of agreements by participants, and if required, deleting them. For more information, see [Adobe Sign - Feature: Delete User Information](/content/help/en/sign/help/adobesign_gdpr_user_deletion).

Agreements data for adaptive forms configured to use the Forms Portal submit action is also saved in the forms portal data store. To access and delete data from forms portal data store, see [Forms portal | Handling user data](../../forms/using/forms-portal-handling-user-data.md).
