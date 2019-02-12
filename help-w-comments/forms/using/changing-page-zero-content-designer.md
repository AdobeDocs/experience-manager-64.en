---
title: Changing Page Zero content in Designer
seo-title: Changing Page Zero content in Designer
description: Do you know how you can change the message displayed on Page Zero of an XFA PDF when viewing it in a non-Adobe PDF viewer?
seo-description: Do you know how you can change the message displayed on Page Zero of an XFA PDF when viewing it in a non-Adobe PDF viewer?
uuid: 0a76fccd-b03e-4a1d-bb23-d8c4452be883
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 875532dd-dbf8-4460-b225-ef09b11c0503
index: y
internal: n
snippet: y
---

# Changing Page Zero content in Designer{#changing-page-zero-content-in-designer}

Page Zero content is displayed by default when a non-Adobe PDF viewer, such as the default PDF viewer in Chrome or Firefox, cannot read the content of the PDF/XFA form. The default Page Zero message is shown below.

![](assets/defaultPage0Message.png)

AEM Forms Feature Pack 1 version of Designer allows you to change the message that is displayed on Page Zero. To change the Page Zero message, perform the following steps:

1. Ensure that you have the AEM Forms Feature Pack 1 version of Designer installed. You can check the version from the About screen of designer.  

1. Open the form for which you want to change the Page Zero content.  

1. Click **File &gt; Form Properties**.  

1. In the Form Properties dialog, click ![](assets/Plus.png) (Plus icon) to add a custom property.  

1. Specify **_pagezerocontent** as the name of the property.
1. Add the new Page Zero message, in Rich Text format, as value. For example:
1. Save the form as PDF.  

1. View the PDF form in browser to confirm that the message is updated. The example value above appears as follows:

   ![](assets/ChangedMessage.png)

>[!NOTE]
>
>The custom property you just created may not appear properly in the Form Properties dialog when you reopen the form. However, it works fine and the form displays the updated Page Zero message.

