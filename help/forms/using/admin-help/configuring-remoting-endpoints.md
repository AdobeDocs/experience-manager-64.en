---
title: Configuring Remoting endpoints
seo-title: Configuring Remoting endpoints
description: null
seo-description: Learn how to configure remoting endpoints.
uuid: 7e5506f5-0c9f-4a7e-9b0a-d64b79f035e0
acrolinxdate: 2016-05-31T06 57 18.670-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/configuring_remoting_endpoints_admin_5e12de0b318c6865_2295_report.xml
acrolinxsentences: 4
acrolinxwords: 117
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d62866c9-993c-415b-a9b9-9b7304935820
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring Remoting endpoints{#configuring-remoting-endpoints}

A remoting endpoint enables an application built with Flex to invoke the service using (Deprecated for AEM forms) AEM forms Remoting. A remoting endpoint is automatically created for each activated service. A Flex destination that has the same name as the endpoint is created, and Flex clients can create remote objects that point to this destination to invoke operations on the relevant service.

## Remoting endpoint settings {#remoting-endpoint-settings}

**Flex Client Authentication Method:** Determines the type of response that the server sends back to the client when the invoked service is security enabled, the operation invoked does not support anonymous invocations, and the client passes in either no or invalid credentials.
