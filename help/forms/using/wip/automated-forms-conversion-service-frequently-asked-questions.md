---
title: "Automated Forms Conversion service: frequently asked questions"
seo-title: "Automated Forms Conversion service: frequently asked questions"
description: null
seo-description: null
uuid: 86d113c5-66be-4a6d-8e5e-76822fa093fb
acrolinxdate: 2018-11-30T13 41 10.110-0500
acrolinxlastcheckedby: khsingh
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/ms_conversion_service___frequently_asked_questions_krs_workflow_27a21c3e5e538b90_145_report.xml
acrolinxsentences: 60
acrolinxwords: 874
discoiquuid: c4778967-4c8f-47cc-9025-a6697bb3bbda
firstpublishinternaldate: 2018-12-04T02 07 46.581-0500
lastpublishinternaldate: 2019-01-22T08 32 34.556-0500
preview: true
publishinternaldate: 2019-01-22T08 32 34.556-0500
publishinternalurl: https //helpx-internal.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/wip/automated-forms-conversion-service-frequently-asked-questions.html
index: y
internal: n
snippet: y
---

# Automated Forms Conversion service: frequently asked questions{#automated-forms-conversion-service-frequently-asked-questions}

* The service can convert non-interactive PDF forms into adaptive forms. It has limited support for AcroForms and XFA-based PDF forms. The service does not support scanned forms.  
* The service converts only English-languag forms to adaptive forms. You can translate converted adaptive forms to another language using [AEM translation workflow](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/using-aem-translation-workflow-to-localize-adaptive-forms.html).

We are regularly adding support for other source types. Keep the [What’s supported](../../../forms/using/wip/aem-forms-automated-forms-conversion-service-beta.md) section on your watchlist for a regular update on newly added features and capabilities.

The service does not produce an XDP output for the time being. We are regularly adding features and to the service. Keep the [What’s supported](../../../forms/using/wip/aem-forms-automated-forms-conversion-service-beta.md) section on your watchlist for a regular update on newly added features and capabilities.

The service generates JSON schema.

No, the service does not convert Microsoft Word forms to adaptive forms. You can save a Microsoft Word forms as PDF and convert the PDF to an adaptive form.

The service can convert non-interactive PDF forms to adaptive forms. It has limited support for AcroForms and XFA-based PDF forms. Scanned forms and colored forms are not supported for the time being. We are regularly adding features and to the service. Keep the [What’s supported](../../../forms/using/wip/aem-forms-automated-forms-conversion-service-beta.md) section on your watchlist for a regular update on newly added features and capabilities.

The most common reasons for the service to fail are:

* Secured PDF forms are provided for the conversion. Do not use password protected, Document Security protected, or any other protected PDF forms for conversion.
* Internet connection is interrupted. Ensure that you are connected to the internet during the conversion.
* Service URL is not provided or provided service URL is incorrect. Specify correct service URL in the cloud configuration.

When a non-interactive PDF form is converted to an adaptive form, to improve the quality of conversion, the fonts are embedded in the PDF form. The support for embedding fonts is restricted to non-interactive PDF forms. To optimize the conversion of AcroForm and XFA-based PDF forms, fallback fonts are used.

Only forms available in the custom fonts directory listed in the ****[!UICONTROL Customer fonts directory]**** field of the ****[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]**** configuration are embedded in non-interactive PDF form.

Adaptive forms use [themes to style a form](../../../forms/using/themes.md). The service uses the fonts and font styles specified in the theme applied during the conversion. You can change fonts and font styles of the theme to provide a distinct look and feel to the fonts of an adaptive form.

Automated Forms Conversion service is trained on a large set of forms. However, there are some fields and styles in PDF forms which are easily visible to the human eye but difficult to understand for the service. The service can fail to identify such fields. You can use the [Review and Correct](../../../forms/using/wip/review-correct-ui-edited.md) editor to help identify missing or incorrectly identified fields. For example, if a choice group is identified as a panel or a text box is not identified. You can use the Review and Correct editor make improvements and regenerate the adaptive form to get an output closer to the desired experience.

* You can share such patterns with Adobe and opt in to the program where you share your forms with Adobe to improve the accuracy of the service. Once you provide the permission, the service is trained on your forms and patterns. It helps improve the accuracy and fix patterns in future conversions.
* You can also use meta-model to map the form objects to adaptive form component of your choice and pre-configure validations, rules, data patterns, help text, and accessibility properties for the components. All the specified properties are applied during the conversion. For example, one set of your forms provide combo box to select a hospital and other set provides radio buttons to select a hospital. You can use meta-model to decide, after the conversion, all hospital fields are represented as drop-down list component in the adaptive form.

The service supports only blank or unfilled forms. Do not upload filled forms or forms with personally identifiable information (PII) .

Place header and footer in adaptive forms template. If your form has header and footer, the service detects and replaces these header and footer during the conversion with header and footer available in adaptive form template. If any extra header or footer is included in the adaptive form, you can use the [Review and Correct](../../../forms/using/wip/review-correct-ui-edited.md) editor to fix or remove such header or footer.

The amount of time depends on the size, complexity, and various other factors. In general, in comparison to the manual process of planning, creating assets (themes, templates), and creating an adaptive form, the conversion service has forms ready for deployment in a production environment in almost half time. The service saves approximately 50% of your time in comparison to manual process.

Contact Adobe Support to request a feature or to report a bug.

During the beta phase, Adobe support can log a JIRA issue on with the following details to report an issue:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>JIRA field</td> 
   <td>Options and Description</td> 
  </tr> 
  <tr> 
   <td>Project</td> 
   <td> 
    <ul> 
     <li>CQ: Use the CQ<strong> </strong>project to report bug or improvements in the conversion service.</li> 
     <li>CQDOC: Use the CQDOC<strong> </strong>project to report bug or improvements in the documentation.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Issue Type</td> 
   <td> 
    <ul> 
     <li>Bug: Use the Bug issue type when the behavior is not as expected or documented instructions are incorrect.</li> 
     <li>Improvement: Use the Improvement issue type when a key aspect of the feature is missing and should be provided or documented instructions are insufficient to understand or use the feature. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Component<br /> </td> 
   <td>Forms - Sensei</td> 
  </tr> 
  <tr> 
   <td>FixVersion<br /> </td> 
   <td>AFF 1.0.0 L&amp;lt;xx&amp;gt;, where &amp;lt;xx&amp;gt; is the version number of the <a href="https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=lc&amp;title=Automated+Forms+Conversion+Service+Beta+-+Latest+Builds">release</a>. </td> 
  </tr> 
  <tr> 
   <td>Label<br /> </td> 
   <td>Flamingo-BETA</td> 
  </tr> 
  <tr> 
   <td>Description</td> 
   <td>Provide the following information in the description field:<br /> 
    <ul> 
     <li>Problem statement</li> 
     <li>Steps to reproduce the issue<br /> </li> 
     <li>Actual result of the conversion<br /> </li> 
     <li>Expected result of the conversion<br /> </li> 
     <li>Attach collaterals or provide links to download</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

