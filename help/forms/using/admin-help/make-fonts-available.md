---
title: Make fonts available
seo-title: Make fonts available
description: Ensure that the fonts used within a form are available for use on the J2EE application server hosting AEM forms.
seo-description: Ensure that the fonts used within a form are available for use on the J2EE application server hosting AEM forms.
uuid: ed8c2a3c-3247-4a43-94bf-f881a585aabc
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 9e529d21-4527-4a18-8d6a-ff31d85efce6
index: y
internal: n
snippet: y
---

# Make fonts available{#make-fonts-available}

Ensure that the fonts used within a form are available for use on the J2EE application server hosting AEM forms. For example, consider the following scenario. A form designer adds a font to the font directory that Designer uses and creates a form that uses that font on a separate computer. In order for the Output service to use the font, place it in the Customer fonts directory. If the Customer fonts directory does not exist, create a directory on the J2EE application server hosting AEM forms.

For information on additional font settings, see [Configure general AEM forms settings](../../../forms/using/admin-help/configure-general-aem-forms-settings.md#configure-general-aem-forms-settings).

**Specify the location of the Customer fonts directory**

1. In administration console, click Settings &gt; Core Systems Settings &gt; Configurations.
1. In the Location Of The System Fonts Directory box, type the path to the Customer fonts directory. Multiple directories can be added, separated by a semicolon (;)
1. Click OK.
1. Restart the system on which AEM forms is installed.

>[!NOTE]
>
>Fonts are picked from the Windows system font cache and a system restart is required to update the cache. After specifying the Customer font directory, ensure that you restart the system on which AEM forms is installed.

