---
title: Translating Content for Multilingual Sites
seo-title: Translating Content for Multilingual Sites
description: null
seo-description: Learn how to translate content for multilingual sites.
uuid: 7a0bafea-7508-4777-8808-a6095da0875d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 45a32c24-98f2-43c3-94b9-87e686968abf
isreadyforlocalization: false
legacypath: /content/docs/en/aem/6-0/administer/integration/third-party-services/machine-translation
index: y
internal: n
snippet: y
---

# Translating Content for Multilingual Sites{#translating-content-for-multilingual-sites}

Automate the translation of page content, assets, and user-generated content to create and maintain multilingual websites. To automate translation workflows, you integrate translation service providers with AEM and create projects for translating content into multiple languages. AEM supports human and machine translation workflows.

* Human translation: Content is sent to your translation provider and translated by professional translators. When complete, the translated content is returned and imported into AEM. When your translation provider is integrated with AEM, content is automatically sent between AEM and the translation provider. 
* Machine translation: The machine translation service immediately translates your content.

Translating content involves the following steps:

1. [Connect AEM with your translation service provider](../../administering/using/tc-tic.md#main-pars-title-0) and [create translation integration framework configurations](../../administering/using/tc-tic.md). 

1. [Associate the pages of your language master](../../administering/using/tc-tic.md#main-pars-title-21) with the translation service and framework configurations.
1. [Identify the type of content](../../administering/using/tc-rules.md) to translate.
1. [Prepare the content for translation](../../administering/using/tc-prep.md) by authoring the language master and creating the root pages of language copies.
1. [Create translation projects](../../administering/using/tc-manage.md#main-pars-title-4) to gather the content to translate and to prepare the translation process.
1. Use the translation projects to [manage the content translation process](../../administering/using/tc-manage.md).

If your translation service provider does not provide a connector to integration with AEM, AEM supports the manual extraction and re-insertion of translation content in XML format.

>[!NOTE]
>
>Your user needs to be a member of the project-administrators group to use the Language Copy features.

## Best Practices {#best-practices}

The [Translation Best Practices](../../administering/using/tc-bp.md) page contains important information regarding your implementation.
