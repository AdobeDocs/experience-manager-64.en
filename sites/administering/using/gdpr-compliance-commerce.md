---
title: AEM Commerce - GDPR Readiness
seo-title: AEM Commerce - GDPR Readiness
description: null
seo-description: null
uuid: 305519b2-27cc-41d2-985b-5b6addccf848
contentOwner: carlino
discoiquuid: 5736757d-98a6-4c93-80ca-21deb649b605
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# AEM Commerce - GDPR Readiness{#aem-commerce-gdpr-readiness}

The European Union's General Data Protection Regulation on data privacy rights takes effect as of May 2018. For further information see the [GDPR page at the Adobe Privacy Center](https://www.adobe.com/privacy/general-data-protection-regulation.html).

>[!NOTE]
>
>See [AEM GDPR Readiness](/content/help/en/experience-manager/6-4/managing/using/gdpr-compliance) for further details.

![](assets/screen_shot_2018-03-22at111606.jpg)

In our out-of-the-box Commerce integrations, AEM is the experience layer, consuming services and sending data back to the customer commerce platform that runs in a headless mode.

For some commerce platforms, we store profile information ( `/home/users`) and commerce tokens (to login in the commerce platform) in AEM. For these use cases, please read [Handling GDPR Requests for the AEM Platform](../../administering/using/handling-gdpr-requests-for-aem-platform.md).

![](assets/screen_shot_2018-03-22at111621.jpg)

### Handling GDPR Requests for AEM Commerce {#handling-gdpr-requests-for-aem-commerce}

For the Salesforces Commerce Cloud integration, AEM Commerce does not store any GDPR relevant information. You should forward the request to the [Salesforce Cloud](https://documentation.demandware.com/).

For the hybris and IBM WebSphere integrations, there is some data in AEM. You should use the [AEM Platform GDPR instructions](../../administering/using/handling-gdpr-requests-for-aem-platform.md) and consider these questions:

1. **Where is my data stored/used?** Cached user profile information such as name, commerce user identifier, token, password, address data, and so on is shown from AEM.
1. **With whom do I share the covered GDPR data?** Any update of GDPR relevant data in AEM Commerce does not get stored (except relevant profile information, as mentionned above) but is proxied back to the commerce platform.
1. **How to delete my user data**? Delete the user profile in AEM and invoke the user deletion on the commerce platform.

<!--
Comment Type: annotation
Last Modified By: wmitchel
Last Modified Date: 2018-05-14T10:55:21.465-0400
Change to ", AEM Commerce does not store information covered by the GDPR." this should be narrowed to this service, because other parts of AEM does contain GDPR
-->

<!--
Comment Type: annotation
Last Modified By: wmitchel
Last Modified Date: 2018-05-14T10:57:49.489-0400
change to "With whom do I share the covered GDPR data? Any update of data covered by the GDPR in AEM..." Should this be "AEM Commerce"?
-->

>[!NOTE]
>
>Have a look at the [hybris wiki](https://wiki.hybris.com/) or the [Websphere Commerce documentation](http://www-01.ibm.com/support/docview.wss?uid=swg27036450) if required.

