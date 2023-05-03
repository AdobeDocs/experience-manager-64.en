---
title: Using autosave in AEM Forms app
seo-title: Using autosave in AEM Forms app
description: Learn how to use autosave feature in AEM Forms app that lets you avoid data loss. 
seo-description: Learn how to use autosave feature in AEM Forms app that lets you avoid data loss. 
uuid: f18ab6b4-dd4a-4dcb-88e6-e349777d47ea
contentOwner: sashanka
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 133d93b0-512c-46db-b5f9-f981d77b565f
exl-id: 6eb00c31-6806-478a-99d1-55912798ea69
---
# Using autosave in AEM Forms app {#using-autosave-in-aem-forms-app}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

When a user enters data in the Adobe Experience Manager Forms app, the autosave feature saves it at regular intervals. The autosave feature in the AEM Forms app helps you avoid data loss if the app is accidentally closed.

Your app can accidentally close:

* If your device shuts down due to low battery
* If the user kills the app  
* If an unexpected crash occurs

You can specify the intervals after which the app saves the entered data.

>[!NOTE]
>
>Select autosave frequency judiciously. Frequent autosave operations can have a noticeable impact on the performance of your device.

Perform the following steps to use the autosave feature in AEM Forms app:

1. Log in to the app, and navigate to **[!UICONTROL Settings > General]**.
1. In the General screen, use the **[!UICONTROL Autosave Frequency]** option to select the intervals at which you want the app to save the entered data. 
    [ ![Setting autosave frequency](assets/using-autosave-freq-07.png)](assets/using-autosave-freq-07-1.png)

1. When you restart the app and log in with the same user, you are prompted to restore your task with Recover Unsaved Task dialog. Click **[!UICONTROL OK]** in the Recover Unsaved Task dialog to resume working with the saved task. You can click **[!UICONTROL Cancel]** to delete the saved data corresponding to the last triggered autosave and start working with a new task.

   When you click **[!UICONTROL OK]**, the task is restored with the data corresponding to the latest autosave triggered before the app crashed. It includes the form data and all the attachments associated with the task.
    [ ![Getting a task recovered](assets/autosave-flow.png)](assets/using-autosave-freq-06.png)**A.** A work-in-progress form **B.** App closed forcefully **C.** App restarted with Recover Unsaved Task dialog **D.** Form restored with original data
