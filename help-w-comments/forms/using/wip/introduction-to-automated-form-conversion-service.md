---
title: Automated Forms Conversion service
seo-title: Automated Forms Conversion service
description: Speed up the conversion of print forms to adaptive forms
seo-description: Speed up the conversion of print forms to adaptive forms
uuid: 20b590fa-2ac3-4cb0-90f7-a8684c05fda6
contentOwner: khsingh
discoiquuid: 976185f5-77ff-45ed-8748-f36d6c2ffb4b
index: y
internal: n
snippet: y
---

# Automated Forms Conversion service{#automated-forms-conversion-service}

Speed up the conversion of print forms to adaptive forms

Automated Forms Conversion service helps accelerate digitization and modernization of data capture experience through automated conversion of legacy print forms to adaptive forms. The service, powered by Adobe Sensei, automatically converts your PDF forms to device-friendly and responsive adaptive forms. While leveraging the existing investments in PDF Forms, the service also applies appropriate validations to adaptive form fields during conversion. The service helps:

* Save manual effort required to convert legacy forms to adaptive forms
* Generate reusable adaptive form fragments
* Generate Document of Record during conversion
* Apply patterns and appropriate validations during conversion
* Enables Adobe Analytics during conversion

The service supports PDF forms created with any version of AEM Forms or Adobe LiveCycle, going all the way back to AEM 6.0 Forms and Adobe LiveCycle ES3. The service also supports forms created with Adobe Acrobat.

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:45:55.878-0500
Can a visual help better? Lots of bullet points to read for an overview. Or reduce word count. One way is to not write full sentences.
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:45:19.346-0500
effort not labour. Also, labor not labour.
-->

<!--
Comment Type: draft

<h2>Onboarding</h2>
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:11:53.395-0500
Sounds like it should come before workflow. If it must come after w/f then elaborate in title what is being overboarded. Gerund.
-->

<!--
Comment Type: draft

<p>The conversion service is available for purchase as an add-on to AEM 6.4 Forms. After you purchase, an email is sent to the administrator of your organization with a link to Adobe I/O. You require an Adobe ID account that has administrator privileges for the organization to create an integration on Adobe I/O.</p>
<p>The administrator can follow the link to integrate the Automated Forms Conversion service with AEM Forms. To integrate the service with AEM Forms, see <a href="../../../forms/using/wip/configure-the-automated-forms-conversion-service.md" target="_blank">Configure the Automated Forms Conversion service</a>.</p>
<p>The onboarding process is complete when the administrator configures the service and adds users in AEM. You are ready to convert legacy forms to adaptive forms. </p>
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:05:29.754-0500
Branding. Adobe I/O
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:56:03.973-0500
Froms?!
-->

## Supported languages and PDF forms {#supported-languages-and-pdf-forms}

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:11:38.823-0500
title case.
-->

<!--
Comment Type: annotation
Last Modified By: khsingh
Last Modified Date: 2018-11-21T09:33:33.003-0500

-->

Automated Forms Conversion service converts only English-languag forms to adaptive forms. You can translate converted adaptive forms to another language using [AEM translation workflow](../../../forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.md).

Conversion service supports non-interactive PDF forms, Acroforms, and XFA-based forms. Acroforms, and XFA-based forms has a limited support.

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:06:12.689-0500
Not part of w/f topic. Remove. Link to RNs.
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:54:23.519-0500
using, not with.
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:54:57.761-0500
English-language forms.
-->

## Conversion workflow  {#conversion-workflow}

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T06:49:26.826-0500
Need better title. Also, use sentence case.
-->

Automated Forms Conversion service runs on Adobe Cloud. You connect your AEM instance to the service, upload legacy forms to your AEM instance, specify configurations, and start the conversion. The complete conversion process is as listed below:

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-11-21T07:17:59.738-0500
Remove parenthetical content. These must already be covered below in detailed steps. From overview of this H1, no need to mention all details.
-->

<!--
Comment Type: remark
Last Modified By: Khushwant Singh (khsingh)
Last Modified Date: 2018-11-21T08:57:03.211-0500
<p>Call out these 3 top-level steps before details start.</p>
<p>Can be just an UL or a quick diagram (<a href="https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/sites/administering/using/rich-text-editor/jcr_content/main-pars/image_2035059177/rte_workflow_v1.png" target="_blank">example</a>).<br /> </p>
<ul>
<li>Configure the environment</li>
<li>Use the conversion service</li>
<li>Review converted forms</li>
</ul>
-->

![](assets/workflow.png)

1. **Set up the environment**: Before starting the conversion, connect your AEM Forms instance to the conversion service running on Adobe I/O, prepare templates, prepare themes, customize meta-model, and configure email service:

    1. Install [AEM Forms add-on package](../../../forms/using/installing-configuring-aem-forms-osgi.md) and [Conversion Manager package](../../../forms/using/wip/configure-the-automated-forms-conversion-service.md#download-and-install-conversion-manager-package): Install AEM Forms add-on package to avail AEM Forms capabilities and Conversion Manager package to avail conversion service capabilities.  
    
    1. Create an adaptive form theme: A theme provides a unique appearance and style to an adaptive form. You can apply out of the box themes provided with adaptive forms or [create custom themes](../../../forms/using/themes.md) of your own.
    1. Create an adaptive form template: A template contains a set of adaptive form components common for a set of forms. For example, identical header, footer, and logo for the forms of an organization. You can use the [template editor](../../../forms/using/template-editor.md) to create a template.   
    
    1. Customize meta-model: Meta-model defines mapping for all the adaptive form components. For example, a legacy form field with keywords phone, telephone, mobile phone, work phone, home phone, telephone number, telephone no, and phone number are all mapped to the adaptive form’s telephone component. It also allows the service to pre-configure validations, rules, data patterns, help text, and accessibility properties of adaptive form components. [Extend the default meta-model](../../../forms/using/wip/extending-the-default-meta-model.md) to add organization-specific mapping and validations.
    1. Configure email notifications: [Configure email-service](../../../forms/using/wip/configure-the-automated-forms-conversion-service.md#configure-email-notification) to receive the status of conversion.  
    
    1. Configure cloud services: Create a [cloud service configuration](../../../forms/using/wip/configure-the-automated-forms-conversion-service.md#configure-the-cloud-service) to connect your AEM instance to the conversion service. It also allows you to specify a template, theme, and form fragments for conversion.

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:22:56.068-0500
   with keywords?
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:23:28.361-0500
   are all mapped...
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:23:39.508-0500
   Space.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:24:58.106-0500
   Another idea to lessen the word count is to hyphenate like "organization-specific mapping and properties." 4 instead of 7 words :)
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:25:50.144-0500
   via email. Or just remove via email to shorten.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:26:13.167-0500
   AEM instance.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:26:38.640-0500
   for conversion.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:31:40.657-0500
   Can re-write as, "Install AEM Forms add-on package to avail AEM Forms capabilities and Conversion Manager package to avail x, y, and z."
   -->

   <!--
   Comment Type: remark
   Last Modified By: Ashish Gupta . (asgupta)
   Last Modified Date: 2018-11-21T07:10:33.343-0500
   <p><strong>Workflow diagram</strong></p>
   <p>Place before detailed text. Ideally, at the beginning and set the sequence of the textual instructions.</p>
   <p>Sleek arrows. Too big.</p>
   <p>Can add color coding to demarcate AEM and Adobe Cloud.</p>
   <p>The icons used in w/f diagram should ideally match with icons used in UI.</p>
   <p>Ampersand usage in Review and Correct.<br /> </p>
   -->

1. **Use the conversion service**: Use the conversion service to convert legacy PDF forms available on your AEM Forms instance to adaptive forms. To convert the forms:

    1. [Upload legacy forms](../../../forms/using/wip/convert-existing-forms-to-adaptive-forms.md): Upload the forms to be converted to a folder on your AEM Forms instance. The conversion is run on all the legacy forms available in the folder.  
    
    1. [Start the conversion](../../../forms/using/wip/convert-existing-forms-to-adaptive-forms.md#run-the-conversion): Select the folder containing the legacy forms and start the conversion. On the dialog box, select a cloud service configuration, specify output location, and click start conversion. Legacy forms are uploaded to Adobe Cloud for conversion.

   On successful conversion, an adaptive form and its schema are generated and downloaded to your AEM Forms instance. Adaptive forms fragments its schemas are also generated, if applicable.

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:35:20.093-0500
   Conversion service supports only x,y,andz.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:48:01.424-0500
   the dialog is not named start conversion.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:49:31.255-0500
   The second half of 2.b is not about starting the conversion. It is conceptual info about post-conversion.
   -->

1. **Review converted forms**: Your forms can have complex data capture requirements. Once automated conversion is complete, you can use the [Review and Correct editor](../../../forms/using/wip/review-correct-ui-edited.md) to review converted form and make necessary updates and generate an enhanced output closer to desired experience. After making required changes, resend the forms to the conversion service.

   Conversion of a PDF form to an adaptive form might take some time based on the load on the Adobe I/O servers. When the conversion is complete, an email notification is sent to configured email address.

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:09:03.159-0500
   Ampersand?
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:51:33.029-0500
   I think it should be real-world. Not sure. Check in Acrolinx.
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:52:25.596-0500
   Just say, you can review converted form to make necessary updates.... Saying review quality of conversion may hint that there are issues with quality :)
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:52:46.752-0500
   the required
   -->

   <!--
   Comment Type: annotation
   Last Modified By: asgupta
   Last Modified Date: 2018-11-21T07:53:44.175-0500
   Are the forms automatically sent? If yes, then this is correct. Just FYI conceptual info. If not automatically sent, then mention as actionable info. "After making the required changes, re-send the forms to the conversion service."
   -->

   <!--
   Comment Type: draft

   <li>Step text</li>
   -->

   <!--
   Comment Type: draft

   <li>Step text</li>
   -->

<!--
Comment Type: draft

<h2>Prerequisites </h2>
-->

<!--
Comment Type: draft

<p>Before you can use the Automated Forms Conversion service, ensure the following to create an integration on Adobe I/O:</p>
<ul>
<li>An Adobe ID account that has administrator privileges for the organization.</li>
<li>The Automated Forms Conversion service is enabled for your organization.</li>
</ul>
-->

## Previous {#previous}

* [Prerelease Program](../../../forms/using/wip/aem-forms-automated-forms-conversion-service-beta.md)

## Next {#next}

[Configure the Automated Forms Conversion service](../../../forms/using/wip/configure-the-automated-forms-conversion-service.md)
