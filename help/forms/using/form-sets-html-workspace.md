---
title: Working with Formsets in AEM Forms workspace
seo-title: Working with Formsets in AEM Forms workspace
description: null
seo-description: A formset is a collection of HTML5 forms grouped and presented as a single set of forms to end users. Learn how you can work with formsets in AEM Forms workspace.
uuid: 70448b8a-2e56-455d-a9bf-8427398997d0
acrolinxdate: 2016-05-31T06 28 50.825-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/form_sets_html_workspace_admin_5e12de0b318c6865_1928_report.xml
acrolinxsentences: 17
acrolinxwords: 298
contentOwner: vishgupt
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ea937ba3-55e6-4c65-880d-d8bb26139825
firstpublishqadate: 2015-09-29T10 29 52.587-0400
isreadyforlocalization: false
lastpublishqadate: 2015-10-05T05 10 55.332-0400
publishqadate: 2015-10-05T05 10 55.332-0400
publishqaurl: https //helpx.stage.adobe.com/aem-forms/6-2/form-sets-html-workspace.html
index: y
internal: n
snippet: y
---

# Working with Formsets in AEM Forms workspace{#working-with-formsets-in-aem-forms-workspace}

A formset is a collection of HTML5 forms grouped and presented as a single set of forms to end users. When end users start filling a formset, they are seamlessly transitioned from one form to another. The set of forms can then be submitted in just one click. For more info on formsets and how to set them up, see [Formset in AEM Forms](../../forms/using/formset-in-aem-forms.md).

AEM Forms workspace supports formsets. With formsets, multiple forms related to a service or process can be grouped to automate a business process and presented to the end users. In such a scenario, the users can fill the whole set as one and there is no need to file, submit, and track individual forms or processes.

## Attaching a formset to startpoint in an AEM Forms workspace app <br> {#attaching-a-formset-to-startpoint-in-an-aem-forms-workspace-app-br}

1. Create the business process workflow in Workbench. For more information, see [Workbench help](http://www.adobe.com/go/learn_aemforms_workbench_63).
1. From the process properties of the startpoint, select **Use A CRX Asset** in Presentation & Data.

   ![](assets/1-1.png)

1. Click  ![](assets/browse.png){width="18"}

   (Browse) next to the CRX asset path. The Select Form Asset dialog appears.

   ![](assets/2.png)

1. Click the **Formset** tab, select the relevant formset from the list, and then click **OK**.  

1. Deploy the application after updating other relevant process properties.

## Using formset in&nbsp;AEM Forms workspace {#using-formset-in-nbsp-aem-forms-workspace}

Once a formset is attached to a startpoint, the startpoint can be invoked, as any other startpoint is invoked, from the AEM Forms workspace.

The operations supported on formset through the AEM Forms workspace are:

* Save as draft 
* Lock 
* Abandon
* Submit 
* Add Attachments 
* Add Notes
* Move between forms in a formset using Back or Next buttons

![](assets/3-1.png)

>[!NOTE]
>
>For performance improvement during the movement from previous and next forms in a formset, all the workspace buttons (Back, Next, Save, Submit, and ... (More)) are disabled until the relevant form renders fully.

