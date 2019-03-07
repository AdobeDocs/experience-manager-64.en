---
title: Single Sign On and timeout handlers
seo-title: Single Sign On and timeout handlers
description: How-to set the session timeout value for AEM Forms workspace.
seo-description: How-to set the session timeout value for AEM Forms workspace.
uuid: fab8fd1d-b5a4-4ee1-8748-84def1d2c2b3
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 0be05845-6774-489c-8419-5e20d27fd43e
index: y
internal: n
snippet: y
---

# Single Sign On and timeout handlers{#single-sign-on-and-timeout-handlers}

AEM Forms workspace is SSO enabled. If a user has logged in to an AEM Forms application like Forms Manager or PDF Generator user interface and accesses AEM Forms workspace in the same browser session, then the user is logged in to AEM Forms workspace and vice versa.

## Handling server timeout in&nbsp;AEM Forms workspace {#handling-server-timeout-in-nbsp-aem-forms-workspace}

Session timeout for a user can be configured in the Administration Console.

To set the timeout, login to `http://[server]:[port]/adminui`, navigate to **Settings &gt; User Management &gt; Configuration &gt; Configure Advanced System Attributes**, and make the desired settings.

In AEM Forms workspace timeout is handled as:

* Session duration for a user is available in response of `initialize` call that initializes user session.
* A pop-up dialog notifies the user that session is about to expire, 15 seconds before the session expiry.

On this pop-up dialog:

* Click OK to end the user session.
* Click Cancel to reinitialize the user session.

>[!NOTE]
>
>If no action is taken, the user is automatically logged out of AEM Forms workspace three seconds before the session expiry.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
