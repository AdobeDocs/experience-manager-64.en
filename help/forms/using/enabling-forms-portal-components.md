---
title: Enabling forms portal components
seo-title: Enabling forms portal components
description: Out of the box, Forms Portal components are disabled. Enable Document Services and Document Services Predicates groups to enable Forms Portal components.
seo-description: Out of the box, Forms Portal components are disabled. Enable Document Services and Document Services Predicates groups to enable Forms Portal components.
uuid: addc078c-6f1b-4961-adbd-41e071c956d2
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: publish
discoiquuid: 9373a017-1d2e-4bb6-8a09-5c12a7dad013
index: y
internal: n
snippet: y
---

# Enabling forms portal components{#enabling-forms-portal-components}

Out of the box, forms portal components are not available for use. To make the components appear in the list of available components in AEM sidekick, perform the following steps:

1. Log in to the author instance of your website and open an AEM Sites page.   

1. For the pages using a static template, perform the following steps:

    1. In the page header, tap ![](assets/canvas-drop-down.png) &gt; **Design** to open the page in Design mode.
    1. Tap any component (with a blue border) and then tap ![](assets/field-level.png) to select the paragraph system containing the current component.
    1. In the paragraph system, tap ![](assets/settings_icon.png) to open the Edit dialog for the paragraph system.
    1. From the list of **[!UICONTROL **Allowed Components**]**, enable checkboxes for **[!UICONTROL **Document Services**]** and **[!UICONTROL **Document Services Predicates**]** components. Tap **[!UICONTROL **OK**]**.

1. For the pages using a dynamic template, perform the following steps:

    1. In the page header, tap ![](assets/properties.png) &gt; **Edit Template** to open the template of the page.
    1. Tap Layout Container and tap ![](https://chl-author-preview.corp.adobe.com/content/dam/help/en/aem-forms/icons/FeedManagement.png). In the **Allowed Components **tab, enable the **Document Services and Document Services Predicates **options, and tap ![](https://helpx.adobe.com/content/dam/help/en/aem-forms/icons/AEM_6_3_Forms_save.PNG).

>[!NOTE]
>
>You can also enable specific components from these categories by selecting the components. For more information about the components and their usage, see [Creating a form portal page](../../forms/using/creating-form-portal-page.md) and [Embedding link component in a page](../../forms/using/embedding-link-component-page.md).

Now, the Document Services and Document Services Predicates component categories are available in the components browser. The components are enabled for all the pages that use the same template.
