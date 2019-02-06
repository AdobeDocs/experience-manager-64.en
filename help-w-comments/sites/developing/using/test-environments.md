---
title: Which Test Environments will be needed?
seo-title: Which Test Environments will be needed?
description: Several environments will need to be considered as part of testing
seo-description: Several environments will need to be considered as part of testing
uuid: 4ee1fe6d-7819-4c6c-8bc2-f5a0cda54380
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: a74189fd-9bbc-4e77-9126-d38051bb6916
index: y
internal: n
snippet: y
---

# Which Test Environments will be needed?{#which-test-environments-will-be-needed}

To define which configurations you will need / use for testing, you will need to consider:

**Development** For Unit, and certain Integration tests.

**Testing** For the majority of the tests.

**Live** For final performance and stress tests. Also for acceptance tests with the customer.

You will also need to decide which instances you will need where (usually at least one of each for all levels of testing):

**Author** This instance allows authors to input, and publish, content.

**Publish** This instance presents the website in its published form for access from visitors.

Should be tested in conjunction with the Dispatcher.

Finally, the actual hardware must be considered - any performance tests should be made on a system as close in configuration to the final live environment as possible. For this reason, it is also recommended that the Project Launch be split into a:

**Soft Launch** Reduced availability; which allows time for performance tests, tuning and optimization under realistic conditions on the production environment.

**Hard Launch** Full availability.
