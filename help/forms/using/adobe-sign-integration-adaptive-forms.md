---
title: Integrate Acrobat Sign with AEM Forms
seo-title: Integrate Acrobat Sign with AEM Forms
description: Learn how to configure Acrobat Sign for AEM Forms
seo-description: Learn how to configure Acrobat Sign for AEM Forms
uuid: 9efd5c44-3d87-4c56-aa6c-e65397fff243
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7d494c2e-d457-4d52-89be-a77ffa07eb88
feature: Adaptive Forms, Acrobat Sign
exl-id: e7c27623-a889-4bd5-bfff-cfe513cd1a35
---
# Integrate Acrobat Sign with AEM Forms {#integrate-adobe-sign-with-aem-forms}

Acrobat Sign enables e-signature workflows for adaptive forms. E-signatures improve workflows to process documents for legal, sales, payroll, human resource management, and many more areas.

In a typical Acrobat Sign and adaptive forms scenario, a user fills an adaptive form to **apply for a service**. For example, a credit card application and a citizen benefits form. When a user fills, submits, and signs the application form, the form is sent to the service provider for further action. Service provider reviews the application and uses Acrobat Sign to mark the application approved. To enable similar electronic-signature workflows, you can integrate Acrobat Sign with AEM Forms.

To use Acrobat Sign with AEM Forms, configure Acrobat Sign in AEM Cloud Services:

## Prerequisites {#prerequisites}

You require the following to integrate Acrobat Sign with AEM Forms:

* An active [Acrobat Sign developer account.](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html)
* An [SSL enabled](/help/sites-administering/ssl-by-default.md) AEM Forms server.
* An [Acrobat Sign API application](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/create_app.md).
* Credentials (Client ID and Client Secret) of Acrobat Sign API application.
* When reconfiguring, remove the existing Acrobat Sign configuration from both author and publish instances.
* Use [identical crypto key](/help/sites-administering/security-checklist.md#make-sure-you-properly-replicate-encryption-keys-when-needed) for author and publish instances.

## Configure Acrobat Sign with AEM Forms {#configure-adobe-sign-with-aem-forms}

After prerequisites are in place, perform the following steps to configure Acrobat Sign with AEM Forms on the Author instance:

1. On AEM Forms author instance, navigate to **Tools** ![hammer](assets/hammer.png) &gt; **General** &gt; **Configuration Browser**.
   * See the [Configuration Browser documentation](/help/sites-administering/configurations.md) for more information.
1. On the **[!UICONTROL Configuration Browser]** page, tap **[!UICONTROL Create]**.
1. In the **[!UICONTROL Create Configuration]** dialog, specify a **[!UICONTROL Title]** for the configuration, enable **[!UICONTROL Cloud Configurations]**, and tap **[!UICONTROL Create]**. It creates a configuration container for cloud services.
1. Navigate to **Tools** ![hammer](assets/hammer.png) &gt; **Cloud Services** &gt; **Acrobat Sign** and select the configuration container you created in the above step.

   >[!NOTE]
   >
   >You can either execute steps 1-4 to create a new configuration container and create an Acrobat Sign configuration in the container or use the existing `global` folder in **Tools** ![hammer](assets/hammer.png) &gt; **Cloud Services** &gt; **Acrobat Sign**. If you create the configuration in the new configuration container, ensure to specify the container name in the **[!UICONTROL Configuration Container]** field when you create an adaptive form.

   >[!NOTE]
   >
   >Ensure that the URL of the cloud services configuration page starts with **HTTPS**. If not, [enable SSL](/help/sites-administering/ssl-by-default.md) for AEM Forms server.

1. On the configuration page, tap **[!UICONTROL Create]** to create Acrobat Sign configuration in AEM Forms.
1. In the **[!UICONTROL General]** tab of the **[!UICONTROL Create Acrobat Sign Configuration]** page, specify a **Name** for the configuration and tap **Next**. You can optionally specify a title and browse to select a thumbnail for the configuration.

1. Copy the URL in your current browser window to a notepad. It is required to configure Acrobat Sign application with AEM Forms.

1. Configure OAuth settings for the Acrobat Sign application:

    1. Open a browser window and sign in to the Acrobat Sign developer account.
    1. Select the application configured for AEM Forms, and tap Configure OAuth for Application.
    1. In the **Redirect URL** box, add the HTTPS URL copied in the previous step and click **Save**.
    1. Enable the following OAuth settings for the Acrobat Sign application and click **Save**.

    * aggrement_read
    * aggrement_write
    * aggrement_send
    * widget_write
    * workflow_read

   For step-by-step information to configure OAuth settings for an Acrobat Sign application and obtain the keys, see [Configure oAuth settings for the application](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md) developer documentation.

   ![OAuth Config](assets/oauthconfig_new.png)

1. Go back to the **Create Acrobat Sign Configuration** page. In the **[!UICONTROL Settings]** tab, the **[!UICONTROL OAuth URL]** field mentions the following default URL:

   `https://secure.na1.echosign.com/public/oauth`

   where:

   **na1** refers to the default database shard.

   You can modify the value for the database shard. Restart the server to be able to use the new value for the database shard.

1. Specify the **Client ID** (also referred to as Application ID) and **Client Secret**. Select the **Enable Acrobat Sign for attachments also** option to append files attached to an adaptive form to the corresponding Acrobat Sign document sent for signing.

   Tap **[!UICONTROL Connect to Acrobat Sign]**. When prompted for credentials, provide username and password of the account used while creating Acrobat Sign application.

   Tap **[!UICONTROL Create]** to create the Acrobat Sign configuration.

1. Open AEM Web Console. The URL is `https://'[server]:[port]'/system/console/configMgr`
1. Open **Forms Common Configuration Service.**
1. In the **Allow** field, **select** All users - All the users, anonymous or logged in, can preview attachments, verify and sign forms, and click **Save.** Author instance is configured to use Acrobat Sign.
1. Use [replication](/help/sites-deploying/replication.md) to create identical configuration on corresponding publish instances. 

Now, Acrobat Sign is integrated with AEM Forms and ready for use in adaptive forms. To [use Acrobat Sign service in an adaptive form](../../forms/using/working-with-adobe-sign.md#configure-adobe-sign-for-an-adaptive-form), specify the configuration container created above in adaptive form properties.

## Configure Acrobat Sign scheduler to sync the signing status {#configure-adobe-sign-scheduler-to-sync-the-signing-status}

An Acrobat Sign enabled adaptive form is submitted only after all the signers complete the signing process. By default, the Acrobat Sign Scheduler services is scheduled to check (poll) signer response after every 24 hours. You can change the default interval for your environment. Perform the following steps to change the default interval:

1. Log in to AEM Forms server with admin credentials and navigate to **Tools** &gt; **Operations** &gt; **Web Console**.

   You can also open the following URL in a browser window:
   `https://[localhost]:'port'/system/console/configMgr`

1. Locate and open the **Acrobat Sign Configuration Service** option. Specify a [cron expression](https://en.wikipedia.org/wiki/Cron#CRON_expression) in the **Status Update Scheduler Expression** field and click **Save**. For example, to run the configuration service daily at 00:00 am, specify `0 0 0 1/1 * ? *` in the **Status Update Scheduler Expression** field.

Default interval to sync status of Acrobat Sign is now changed.

## Related Articles {#related-articles}

* [Using Acrobat Sign in an adaptive form](../../forms/using/working-with-adobe-sign.md)
* [Using Acrobat Sign with AEM Forms (Video)](https://helpx.adobe.com/experience-manager/kt/forms/using/adobe-sign-integration-feature-video.html)
* [Integrate Acrobat Sign with AEM Forms](../../forms/using/adobe-sign-integration-adaptive-forms.md)
