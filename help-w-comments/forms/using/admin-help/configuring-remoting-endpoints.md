---
title: Configuring Remoting endpoints
seo-title: Configuring Remoting endpoints
description: Learn how to configure remoting endpoints.
seo-description: Learn how to configure remoting endpoints.
uuid: d96cce5d-c2e6-4881-b020-ed4b2b261913
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 4a92f7b5-451b-4af1-8f07-71b7f33e4554
index: y
internal: n
snippet: y
---

# Configuring Remoting endpoints{#configuring-remoting-endpoints}

A remoting endpoint enables an application built with Flex to invoke the service using (Deprecated for AEM forms) AEM forms Remoting. A remoting endpoint is automatically created for each activated service. A Flex destination that has the same name as the endpoint is created, and Flex clients can create remote objects that point to this destination to invoke operations on the relevant service.

## Remoting endpoint settings {#remoting-endpoint-settings}

**Flex Client Authentication Method:** Determines the type of response that the server sends back to the client when the invoked service is security enabled, the operation invoked does not support anonymous invocations, and the client passes in either no or invalid credentials.
