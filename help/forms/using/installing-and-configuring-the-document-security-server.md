---
title: Installing and configuring the document security server
seo-title: Installing and configuring the document security server
description: Use document security to safely distribute any information that you have saved in a supported format. Only authorized users can access protected documents. 
seo-description: Use document security to safely distribute any information that you have saved in a supported format. Only authorized users can access protected documents. 
uuid: d5bf76f4-6f01-4b45-a70f-7d4fb07182f0
contentOwner: khsingh
discoiquuid: 4f27c421-683c-492c-8b1f-686979f2ffea
index: y
internal: n
snippet: y
---

# Installing and configuring the document security server{#installing-and-configuring-the-document-security-server}

Use document security to safely distribute any information that you have saved in a supported format. Only authorized users can access protected documents. 

Adobe Experience Manager Forms document security ensures that only authorized users can use your documents. Using document security, you can safely distribute any information that you have saved in a supported format. Supported file formats include Adobe Portable Document Format (PDF) and Microsoft Word, Excel, and PowerPoint files.

You can protect documents by using policies. The confidentiality settings you specify in a policy determine how a recipient can use a document to which you apply the policy. For example, you can specify whether recipients can print or copy text, edit text, or add signatures and comments to protected documents.

The policies are stored on Document Security server; you apply the policies to documents through your client application. When you apply a policy to a document, the confidentiality settings specified in the policy protect the information that the document contains. You can distribute the policy-protected document to recipients who are authorized by the policy.

Document security also provides clients, viewers, and indexers to protect documents, view protected documents, and index protected documents. For detailed information about document security, see [about document security](../../forms/using/admin-help/document-security.md).

## Deployment Topology  {#deployment-topology}

The document security capability is available only in AEM Forms on JEE. You require a single instance of AEM Forms on JEE. You can also create a cluster or farm of AEM Forms servers, if necessary. The following topology is indicative topology to run the document security capability. For detailed information about the topology, see [Architecture and deployment topologies for AEM Forms](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/aem-forms-architecture-deployment.html).

![](assets/document-security-server_topology.png)

The following diagram shows the typical architecture for AEM Forms Document Security:

![](assets/document-security-typical-environment.png) 

## Installing AEM Forms on JEE {#installing-aem-forms-on-jee}

Perform the following steps to install and configure AEM Forms on JEE:

1. Download the AEM 6.4 Forms on JEE installer from the [Adobe Licensing Website (LWS)](http://licensing.adobe.com/). You require a valid Maintenance & Support contract to download the installer.

1. Read the [AEM Forms on JEE Supported Platforms document](../../forms/using/AEM-forms-JEE-supported-platforms.md) and ensure that have the software, hardware, operating systems, application server, databases, JDKs, and other infrastructure ready to install AEM Forms on JEE.
1. (Non-Turnkey installs only) Read the [Preparing to install AEM Forms single server](http://www.adobe.com/go/learn_aemforms_prepareInstallsingle_64) or [Preparing to install AEM Forms server cluster](http://www.adobe.com/go/learn_aemforms_prepareInstallcluster_64) and ready your environment to install and configure AEM Forms on JEE.
1. Depending on your environment and application server, choose one of the following documents and follow the instructions to complete the installation

    * [Installing and deploying AEM Forms on JEE using JBoss turnkey](http://www.adobe.com/go/learn_aemforms_installTurnkey_64)
    * [Installing and deploying AEM Forms on JEE for JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_64)
    * [Installing and deploying AEM Forms on JEE for WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_64)
    * [Installing and deploying AEM Forms on JEE for WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_64)
    * [Configuring AEM Forms on JEE on JBoss cluster](http://www.adobe.com/go/learn_aemforms_clusterJBoss_64)
    * [Configuring AEM Forms on JEE on WebLogic cluster](http://www.adobe.com/go/learn_aemforms_clusterWebLogic_64)
    * [Configuring AEM Forms on JEE on WebSphere cluster](http://www.adobe.com/go/learn_aemforms_clusterWebSphere_64)

   >[!NOTE]
   >
   >On the Module selection screen of AEM Forms on JEE configuration manager, select the Document Security option. The Document Security option does not require any other module to be selected.

1. Step text

## Next Steps {#next-steps}

* [Configure client and server options](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/admin-help/configuring-client-server-options.html)
* [Create and managing policies](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/admin-help/creating-policies.html)
* [Create and managing policy sets](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-4/forms/using/admin-help/creating-policy-sets.html)
* [Working with document security](/forms/using/admin-help/topics)

