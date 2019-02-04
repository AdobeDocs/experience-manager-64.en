---
title: Configuring redirect page
seo-title: Configuring redirect page
description: null
seo-description: After filling an adaptive form, users can be redirected to a webpage that form authors can configure while creating the form.
uuid: d50d77cf-f350-4d00-bb8d-fd0a916a0559
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 425f3cf8-0a7c-4e39-8964-f0c8d1c3bdc9
index: y
internal: n
snippet: y
---

# Configuring redirect page{#configuring-redirect-page}

Form authors can configure a page for each form, to which the form users are redirected after submitting a form.

1. In the edit mode, select a component, then click ![](assets/field-level.png) &gt; **Adaptive Form Container**, and then click ![](assets/cmppr.png-).

1. In the sidebar, click **Submission**.  

1. Provide the URL of the redirect page under Thank You Page in the Submission section.  
1. Optionally, under Submit Action, for the Submit to REST endpoint action, you can configure the parameter to be passed to the redirect page.

![Redirect page configuration](assets/thank-you-setting-1.png)

Form authors can use the following parameters that are passed to the Thank you page. For all the available submit actions, `status`** **and `owner` parameters are passed. Besides these two parameters, some additional parameters are passed for the following submit actions:

* **Store content action** (deprecated) : `contentPath`--the path of the node in the repository where submitted data is stored--is passed.

* **Store PDF action** (deprecated) : `contentPath`--of the submitted data and path to the node storing the PDF file in the repository--is passed.  

* **Submit to Forms workflow**: Output parameters returned from forms workflow are passed.  

* **Submit to REST endpoint**: Parameters added for in-field to parameter mapping are passed. `status` and `owner` parameters are not passed in this submit action. For more information, see [Configuring the Submit to REST endpoint submit action](../../forms/using/configuring-submit-actions.md).

>[!MORE_LIKE_THIS]
>
>* [Introduction to Adaptive forms authoring](../../forms/using/introduction-forms-authoring.md)
>* [Creating an Adaptive form](../../forms/using/creating-adaptive-form.md)
>* [Configuring the Submit action](../../forms/using/configuring-submit-actions.md)
