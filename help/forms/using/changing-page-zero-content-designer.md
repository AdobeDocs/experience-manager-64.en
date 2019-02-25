---
title: Changing Page Zero content in Designer
seo-title: Changing Page Zero content in Designer
description: Do you know how you can change the message displayed on Page Zero of an XFA PDF when viewing it in a non-Adobe PDF viewer?
seo-description: Do you know how you can change the message displayed on Page Zero of an XFA PDF when viewing it in a non-Adobe PDF viewer?
uuid: aca2aa6a-1b43-48eb-a1e4-dd571b7811d5
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 979bc711-973d-4ec2-8e13-4c0dbe96cc86
---

# Changing Page Zero content in Designer{#changing-page-zero-content-in-designer}

Page Zero content is displayed by default when a non-Adobe PDF viewer, such as the default PDF viewer in Chrome or Firefox, cannot read the content of the PDF/XFA form. The default Page Zero message is shown below.

![](assets/defaultpage0message.png)

AEM Forms Feature Pack 1 version of Designer allows you to change the message that is displayed on Page Zero. To change the Page Zero message, perform the following steps:

1. Ensure that you have the AEM Forms Feature Pack 1 version of Designer installed. You can check the version from the About screen of designer.  

1. Open the form for which you want to change the Page Zero content.  

1. Click **File &gt; Form Properties**.  

1. In the Form Properties dialog, click ![](assets/plus.png) (Plus icon) to add a custom property.  

1. Specify **_pagezerocontent** as the name of the property.
1. Add the new Page Zero message, in Rich Text format, as value. For example:
1. Save the form as PDF.  

1. View the PDF form in browser to confirm that the message is updated. The example value above appears as follows:

   ![](assets/changedmessage.png)

>[!NOTE]
>
>The custom property you just created may not appear properly in the Form Properties dialog when you reopen the form. However, it works fine and the form displays the updated Page Zero message.

