---
title: Introduction to multi-step form sequence
seo-title: Introduction to multi-step form sequence
description: With AEM Forms, you can define a sequence of form panel in which you want users to navigate and fill an adaptive form.
seo-description: With AEM Forms, you can define a sequence of form panel in which you want users to navigate and fill an adaptive form.
uuid: b2b94e4c-0c28-47ba-8e23-fd8742baf71c
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 4a51ebc4-e019-4fc5-93a1-d97f695126f5
feature: Adaptive Forms
exl-id: eec8bcbe-e2ba-42f1-98ea-08a4ca723e48
---
# Introduction to multi-step form sequence {#introduction-to-multi-step-form-sequence}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Adaptive forms enables Form Authors to create multi-step data capture experience with great ease. It comes with built-in support for creating multiple panels and associating each panel with different navigation patterns. Form Authors can group form fields in logical sections and represent a group as a panel. The overall navigation between panels is controlled using the panel layout. Authors can choose to arrange panels in different layouts, for example, placing sequentially using the Wizard layout or in an ad-hoc manner using the Tabbed layout. For information about panel layouts, see [Layout capabilities of adaptive forms](/help/forms/using/layout-capabilities-adaptive-forms.md).

In a typical form filling experience, there are more steps involved than just capturing data. A complete form submission can include other steps, like signing the form digitally, verifying the information filled in the form, processing payments, and so on. It differs from case to case.

If your use case mandates a set of steps for data capturing or there are regulations that need certain steps to be followed, AEM Forms provides a way to enforce that common structure across forms. The premeditated implementation of form structure defines the sequence of steps for a form. ![Example of a multi-step form sequence](assets/formpipeline.png)

Let's take a use case where you need to create a sequence for fill, verify, sign, and confirmation steps for a form. The steps to create such a sequence is as follows:

1. Define a form template and add required panel to it. Note that there should be one panel for each step in the sequence. However, you can include sub-panels inside a panel.

   In this example, we can add the following panels:

    * **Fill**: It contains forms fields for capturing data. Here, you can include nested sub-panels to create sections for different types of information, such as personal, family, financial, and so on. 
    * **Verify**: It contains the **Verify** component that can be used in an XFA-based adaptive form. It displays the information captured in the Fill panel in read-only mode for verification. 
    * **E-sign**: It contains the **Sign** component that can be used in an XFA-based adaptive form. it provides the following signing services:

        * Adobe Document Cloud eSign services
        * Scribble signature

    * **Confirmation**: It contains the **Summary** component that displays a message confirming the form submission after a user signs the form and reaches the Confirmation (Summary) step in the sequence. Authors can configure the text of the Summary component, show a thank you message, show a link to the generated PDF, and so on.

1. Select the layout of the root panel as **[!UICONTROL Wizard]**.
1. Complete the remaining steps to create the form template. For more information, see [Creating a custom adaptive form template](/help/forms/using/custom-adaptive-forms-templates.md).

After you have defined the form sequence in the form template, you can use it create forms that will have the basic structure defined as the sequence in place, though you can always customize the form to suit your requirements.
