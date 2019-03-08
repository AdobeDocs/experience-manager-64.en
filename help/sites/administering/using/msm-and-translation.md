---
title: Website Administration
seo-title: Website Administration
description: Learn how to manage multilingual websites in AEM.
seo-description: Learn how to manage multilingual websites in AEM.
uuid: dd71acf8-7b75-45f0-9028-c45d37aa6db5
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 55334c59-5c23-4250-b931-b04a26234578
index: y
internal: n
snippet: y
---

# Website Administration{#website-administration}

The following administration tools are available for managing websites and pages:

* Multi Site Manager (MSM) enables you to use the same site content in multiple locations, while allowing for variations:

    * [Reusing Content: Multi Site Manager and Live Copy](../../../sites/administering/using/msm.md)

* Translation allows you to automate the translation of page content, assets, and user-generated content to create and maintain multilingual websites:

    * [Translating Content for Multilingual Sites](../../../sites/administering/using/translation.md)

* These two features can be combined to cater for websites that are both [Multinational and Multilingual](#multinational-and-multilingual-sites).

## Multinational and Multilingual Sites {#multinational-and-multilingual-sites}

You can efficiently create content for multinational and multilingual sites through the combined use of the Multi Site Manager and the translation workflow. Create a master site in one language, for a specific country, then use that content as a basis for the other sites, using translation where required:

* [Translate](../../../sites/administering/using/translation.md) the master site into different languages.   

* Use [Multi Site Manager](../../../sites/administering/using/msm.md) to:

    * Re-use content from the master site, and the translations, to create sites for other countries and cultures.
    * Make sure to limit the use of Multi Site Manager to content within one language, e.g. English master -&gt; English language branches in country sites, French master -&gt; French language branches in country sites. 
    * Where required, detach elements of the live copies to add localization details.

The following diagram illustrates how the main concepts intersect (but does not show all levels/elements involved):

![](assets/chlimage_1-71.png)

>[!NOTE]
>
>In this, and comparable, scenarios MSM does not manage the different language versions as such.
>
>* [MSM](../../../sites/administering/using/msm.md) manages the deployment of translated content from a blueprint (e.g. a global master) to the live copies (e.g. the local sites), within the boundaries of a language.
>* The [translation](../../../sites/administering/using/translation.md) integration capabilities of AEM, in conjunction with third-party translation management services, manages the languages and translating content into these different languages.
>
>For more advanced use-cases, MSM may be used across language masters as well.

>[!NOTE]
>
>For all use-cases it is recommended to read the following best practices:
>
>* [Best Practices for MSM](../../../sites/administering/using/msm-best-practices.md); particularly: >
>    * [Create Site](../../../sites/administering/using/msm-best-practices.md#create-site)
>    * [MSM and Multilingual Websites](../../../sites/administering/using/msm-best-practices.md#msm-and-multilingual-websites)
>
>* [Best Practices for Translation](../../../sites/administering/using/tc-bp.md)
>

