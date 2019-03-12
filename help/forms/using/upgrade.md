---
title: Upgrade to AEM 6.4 Forms
seo-title: Upgrade to AEM 6.4 Forms
description: You can perform a direct upgrade from AEM 6.1 Forms, AEM 6.2 Forms, and LiveCycle ES4 SP1 to AEM 6.3 Forms. 
seo-description: You can perform a direct upgrade from AEM 6.1 Forms, AEM 6.2 Forms, and LiveCycle ES4 SP1 to AEM 6.3 Forms. 
uuid: 1435246a-9215-4d88-b52c-59a5c329bb77
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: e745033f-8015-4fae-9d82-99d35802c0a6
index: y
internal: n
snippet: y
---

# Upgrade to AEM 6.4 Forms{#upgrade-to-aem-forms}

AEM 6.4 Forms includes several new features and enhancements that streamline the creation, management, and user experiences with forms and correspondences. To learn about all the new capabilities and enhancements of AEM 6.4 Forms, see [New features summary document](../../forms/using/whats-new.md).

You can upgrade your existing LiveCycle or AEM Forms installation to obtain new capabilities and enhancements offered in AEM 6.4 Forms while retaining existing data, processes, and assets intact. On upgrade, metadata and state of the processes are also preserved. You can choose an upgrade path to get started with upgrade.

The following diagram displays the available upgrade paths for AEM Forms on OSGi:

![](do-not-localize/osgi-upgrade.png)

You can perform a direct upgrade from:

* AEM 6.2 Forms on OSGi  
* AEM 6.3 Forms on OSGi

You can also perform a multi-hop upgrade from

* AEM 6.0 Forms on OSGi
* AEM 6.1 Forms on OSGi

The following diagram displays the available upgrade paths for AEM Forms on JEE:

![](do-not-localize/jee-upgrade-6-4.png)

You can perform a direct upgrade from:

* LiveCycle ES3  
* LiveCycle ES4 SP1  
* AEM 6.2 Forms on JEE  
* AEM 6.3 Forms on JEE

You can also perform a multi-hop upgrade from

* LiveCycle ES2  
* AEM 6.0 Forms on JEE   
* AEM 6.1 Forms on JEE

You can perform a direct upgrade from AEM 6.2 Forms or AEM 6.3 Forms to AEM 6.4 Forms. Do the following:

1. Upgrade the existing AEM instance to AEM 6.4. The steps are listed below:

    1. Install the latest service pack and patches for AEM 6.2 Forms or AEM 6.3 Forms. For details, see:

        * [AEM 6.2 release notes](https://helpx.adobe.com/experience-manager/6-2/release-notes.html)
        * [AEM 6.3 release notes](../../release-notes.md)
        * [AEM Sustenance Hub](https://helpx.adobe.com/experience-manager/aem-releases-updates.html)

    1. Prepare the source instance for the upgrade. For detailed steps, see [Upgrading to AEM 6.4](../../sites/deploying/using/upgrade.md#preparing%20the%20source%20instance).
    1. Download the [AEM 6.4 QuickStart](../../sites/deploying/using/deploy.md#getting%20the%20software).
    1. **(Unix/Linux-based installations only)** If you are using UNIX or Linux as the underlying operating system, open the terminal window, navigate to the folder containing crx-quickstart, and run the following command:

       `chmod -R 755 ../crx-quickstart`
    
    1. Upgrade your AEM instance to AEM 6.3. For step by step instructions, see [Upgrading to AEM 6.4](../../sites/deploying/using/upgrade.md).

       Before continuing with the next steps, wait until the ServiceEvent REGISTERED and ServiceEvent UNREGISTERED messages stop appearing in the &lt;crx-repository&gt;/error.log file.

       >[!NOTE]
       >
       >After the server is up and running, a few AEM Forms bundles remain in install state. The number of bundles can vary for every installation. You can safely ignore the state these bundles. The bundles are listed at http://[server]:[port]/system/console/.

1. Install AEM Forms add-on package. The steps are listed below:

    1. Log in to the AEM server as an administrator and open the package share. The default URL of the package share is http://[server]:[port]/crx/packageshare.
    1. In package share, search **AEM 6.4 Forms add-on packages**, click the package applicable to your operating system, and click **Download**. Read and accept the license agreement and click **OK**. The download starts. Once downloaded, the word **Downloaded **appears next to the package.

       Alternately, you can also use the hyperlinks listed in [AEM Forms releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) to manually download a package.
    
    1. After the download is complete, click **Downloaded**. You are redirected to package manager. In the package manager, search the downloaded package, and click **Install**.

       If you manually download the package using the direct link listed in [AEM Forms releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html), then open AEM Package Manager, click **Upload Package**, select the downloaded package, and click upload. After the package is uploaded, click package name, and click **Install.**

       >[!NOTE]
       >
       >After the package is installed, you are prompted to restart the AEM instance. **Do not immediately stop the server.** Before stopping the AEM Forms server, wait until the ServiceEvent REGISTERED and ServiceEvent UNREGISTERED messages stop appearing in the &lt;crx-repository&gt;/error.log file and the log is stable. Also note, a few packages can remain in the installed state. You can safely ignore the state of these packages.

    1. Stop the AEM instance and delete the following files:

        * [AEM_Installation_Directory]\[crx-quickstart]\launchpad\ext\bcmail-jdk15-1.35
        * [AEM_Installation_Directory]\[crx-quickstart]\launchpad\ext\bcprov-jdk15-1.35

    1. Start the AEM instance.

1. Perform post-installation activities.

    * **Run Migration Utility**

      The migration utility makes the adaptive forms and correspondence management assets of earlier versions compatible with AEM 6.4 forms. You can download the utility from AEM package share. For step-by-step information to configure and use the migration utility, see [migration utility](../../forms/using/migration-utility.md).

      If you are using [Sample for integrating drafts & submissions component](https://helpx.adobe.com/experience-manager/6-3/forms/using/integrate-draft-submission-database.html) with the database and upgrading from a previous version, then run the following SQL queries after performing the upgrade:

      ```    
      UPDATE metadata m, additionalmetadatatable am
      SET m.dataType = am.value
      WHERE m.id = am.id
      AND am.key = 'dataType'
      
      ```

      ```    
      DELETE from additionalmetadatatable
      WHERE `key` = 'dataType'
      
      ```

    * **(If upgrading from AEM 6.2 Forms or previous versions only) Reconfigure Adobe Sign**

      If you had Adobe Sign configured in the previous version of AEM Forms, then reconfigure Adobe Sign from AEM Cloud services. For more details, see [Integrate Adobe Sign with AEM Forms](../../forms/using/adobe-sign-integration-adaptive-forms.md).
    
    * **(If upgrading from AEM 6.2 Forms or previous versions only) Reconfigure analytics and reports  
      **

      In AEM 6.4 Forms, traffic variable for source and success event for impression are not available. So, when you upgrade from AEM 6.2 Forms or previous versions, AEM Forms stops sending data to Adobe Analytics server and analytics reports for adaptive forms are not available. Moreover, AEM 6.4 Forms introduces traffic variable for the version of form analytics and success event for the amount of time spent on a field. So, reconfigure analytics and reports for your AEM Forms environment. For detailed steps, see [Configuring analytics and reports](../../forms/using/configure-analytics-forms-documents.md).

1. Verify that the server is upgraded successfully, all the data is also migrated successfully, and it can operate normally.

    * **Verify the status of the bundles: **Ensure that all the bundles are in active state.  
    
    * **Verify replication and reverse replication:** Publish, fill, and submit a few migrated forms. Verify the submitted data also.
    * **Verify access to admin and developer user interfaces:** Log in to AEM instance from an admin account and verify that you have access to the following URLs:

        * http://[server]:[port]/crx/packmgr
        * http://[server]:[port]/crx/de
        * http://[server]:[port]/aem/forms.html/content/dam/formsanddocuments

   >[!NOTE]
   >
   >In AEM 6.4 Forms, the structure of crx-repository has changed. After you upgrade to AEM 6.4 forms, use the changed paths for customization that you create afresh. For the complete list of changed paths, see [Forms Repository Restructuring in AEM 6.4](../../sites/deploying/using/forms-repository-restructuring-in-aem-6-4.md).

Direct upgrade path from **AEM 6.0 Forms** and **AEM 6.1 Forms** to AEM 6.4 Forms is not available. Perform an intermediate [upgrade to AEM 6.2 Forms](../../forms/using/upgrade.md) or [upgrade to AEM 6.3 Forms](../../forms/using/upgrade.md) and then upgrade from AEM 6.2 Forms or AEM 6.3 Forms to AEM 6.4 Forms.

Perform the following procedure to upgrade existing AEM 6.2 Forms on JEE or AEM 6.3 Forms on JEE to AEM 6.4 Forms on JEE:

1. Download the AEM 6.4 Forms on JEE installer from the [Adobe Licensing Website (LWS)](http://licensing.adobe.com/). You require a valid Maintenance & Support contract to download the installer.
1. See [Upgrade checklist and planning](http://www.adobe.com/go/learn_aemfroms_upgrade_checklist_63) to learn about the checks to perform to ensure a successful upgrade.
1. See [Prepare to upgrade to AEM Forms](http://www.adobe.com/go/learn_aemforms_prepareupgrade_63) to learn and perform the tasks that ensure the upgrade runs correctly with minimal server downtime.
1. Depending on your existing environment and application server, choose one of the following documents and follow the instructions.

    * [Upgrade from AEM 6.2 or AEM 6.3 Forms to AEM 6.4 Forms for JBoss](assets/upgrade-jboss.pdf)
    * [Upgrade from AEM 6.2 or AEM 6.3 Forms to AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic.pdf)
    * [Upgrade from AEM 6.2 or AEM 6.3 Forms to AEM 6.4 Forms for WebSphere](assets/upgrade-websphere.pdf)
    * [Upgrade from AEM 6.2 or AEM 6.3 Forms to AEM 6.4 Forms for JBoss Turnkey](assets/upgrade-turnkey.pdf)

Direct upgrade from LiveCycle ES2, LiveCycle ES3, AEM 6.0 Forms, AEM 6.1 Forms to AEM 6.4 Forms is not available. You can perform an intermediate upgrade to one or more versions of LiveCycle or AEM Forms and then upgrade from AEM 6.4 Forms. For the list of intermediate versions and corresponding upgrade instructions, see [Choose an upgrade path](../../forms/using/upgrade.md#main-pars-header).

Upgrading LiveCycle ES4 SP1 to AEM 6.4 Forms on JEE is an out-of-place upgrade, as it involves migrating assets and data from previous versions to the fresh instances (new versions) of supported application servers, operating systems, and databases.

Following is an overview of the procedure to upgrade an existing LiveCycle ES4 SP1 server to AEM 6.4 Forms. For detailed instructions, see the documents listed at the end of the procedure.

1. Before you upgrade:

    1. Download the AEM 6.4 Forms on JEE installer from the [Adobe Licensing Website (LWS)](http://licensing.adobe.com/). You require a valid Maintenance & Support contract to download the installer.
    1. Decide the Content Repository (CRX Repository) type to use. Only a few AEM Forms on JEE capabilities use Content Repository persistence to store content and assets. Install and configure Content Repository only if you plan to use such AEM Forms on JEE capabilities:

        * In LiveCycle ES4 SP1, the Correspondence Management, Forms Portal, HTML Workspace, and Process Reporting capabilities use Content Repository. If you did not use these capabilities in LiveCycle ES4 and plan not to use these capabilities in AEM Forms, then Content Repository is not required.
        * In AEM Forms, Adaptive Forms, Correspondence Management, HTML5 Forms (Known as Mobile Forms in LiveCycle ES4 SP1), Forms Portal, HTML Workspace, Process Reporting, Forms centric workflows on OSGi, capabilities use Content Repository. If you plan to use AEM Forms for these capabilities, then Content Repository is required.
        * You do not require Content Repository for AEM Forms Document Security.

       Moreover, repository type of LiveCycle and AEM Forms are different. For available repository types and related information, see [Choosing a persistence type for an AEM Forms installation](../../forms/using/choosing-persistence-type-for-aem-forms.md). 
    
    1. Create a backup of LiveCycle ES4 SP1 content and data:

       Create a backup of LiveCycle ES4 SP1 database, Global Data Storage (GDS), and crx-repository (not required for document security). If you're upgrading to MongoMK or RDBMK persistence, export LiveCycle ES4 SP1 correspondence management assets in a .cmp file and forms assets as an AEM package.
    
    1. Ensure your existing platform (that is, application server, database, operating system, Adobe Acrobat, third-party applications, and hardware) is supported for AEM 6.4 Forms on JEE. For information about supported hardware and software, refer to the [Supported Platform Combinations](../../forms/using/AEM-forms-JEE-supported-platforms.md) document.

       If you create a fresh instance of the database, import the data backed up in step 3 to the database. For information about how to import data to a database, see documentation of corresponding database vendor.

       >[!NOTE]
       >
       >If you are using RDBMK persistence format, use a single database for both repository persistence and document services running on AEM Forms on JEE.

1. Perform the upgrade:

    1. 
       Install AEM 6.4 Forms on JEE on a new server by running the installation program. The installer places all of the required files onto your computer, within one installation directory structure.  
    1. After installation is complete, run the **Configuration Manager **to configure various AEM Forms modules and set appropriate configurations. Along with configuring settings, it allows to specify the path of Global Data Storage (GDS) and crx-repository.

       >[!NOTE]
       >
       >On the Upgrade Task Selection screen, select the **Upgrade from Adobe Experience Manager Forms 6.2.0** option. The **Upgrade from Adobe Experience Manager Forms 6.2.0** option allows the configuration manager to upgrade from LiveCycle ES4 SP1 to AEM 6.4 Forms.

    1. (Not required for AEM Forms document security module) Import content to the Content Repository (CRX-Repository) to AEM 6.4 Forms server.

       >[!NOTE]
       >
       >
       >    
       >    
       >    * After the crx-repository is upgraded and the content is migrated, change the password of the admin account. For detailed instructions, see [Changing the Password for an Existing User](../../sites/administering/using/granite-user-group-admin.md).
       >    
       >

1. Perform the post-deployment tasks to verify login credentials, configure document services, correspondence management, document security, and more depending on your use case.
1. Verify that the server is upgraded successfully:

   Perform a few routine operations on upgraded AEM Forms server to ensure that the server is upgraded successfully. You can fill and submit a few migrated forms or protect documents to ensure a successful upgrade.

   >[!NOTE]
   >
   >In AEM 6.4 Forms, the structure of crx-repository has changed. After you upgrade to AEM 6.4 forms, use the changed paths for customization that you create afresh. For the complete list of changed paths, see [Forms Repository Restructuring in AEM 6.4](../../sites/deploying/using/forms-repository-restructuring-in-aem-6-4.md).

**Depending on your existing environment and application server, choose one of the following documents and follow the detailed instructions:**

* [Upgrade from LiveCycle ES4 SP1 to AEM 6.4 Forms for JBoss](assets/upgrade-jboss-livecycle.pdf)
* [Upgrade from LiveCycle ES4 SP1 to AEM 6.4 Forms for WebLogic](assets/upgrade-weblogic-livecycle.pdf)
* [Upgrade from LiveCycle ES4 SP1 to AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle.pdf)
* [Upgrade from LiveCycle ES4 SP1 to AEM 6.4 Forms using JBoss Turnkey](assets/upgrade-turnkey-livecycle.pdf)

<details> 
 <summary>LiveCycle ES3 &gt; AEM 6.4 Forms on JEE</summary> 
 <p>Upgrading LiveCycle ES3 to AEM 6.4 Forms on JEE is an out-of-place upgrade, as it involves migrating assets and data from previous versions to the fresh instances (new versions) of supported application servers, operating systems, and databases. </p> 
 <p>Following is an overview of the procedure to upgrade an existing LiveCycle ES3 server to AEM 6.4 Forms. For detailed instructions, see the documents listed at the end of the procedure.</p> 
 <ol> 
  <li><p>Before you upgrade: <br /> </p> 
   <ol> 
    <li><p>Download the AEM 6.4 Forms on JEE installer from the <a href="http://licensing.adobe.com/">Adobe Licensing Website (LWS)</a>. You require a valid Maintenance &amp; Support contract to download the installer.</p> </li> 
    <li><p>Decide the Content Repository (CRX Repository) type to use. Only a few AEM Forms on JEE capabilities use Content Repository persistence to store content and assets. Install and configure Content Repository only if you plan to use such AEM Forms on JEE capabilities:</p> 
     <ul> 
      <li>In AEM Forms, Adaptive Forms, Correspondence Management, HTML5 Forms, Forms Portal, HTML Workspace, Process Reporting, and Forms centric workflows on OSGi capabilities use Content Repository. If you plan to use AEM Forms for these capabilities, then Content Repository is required.</li> 
      <li>You do not require Content Repository for AEM Forms Document Security.</li> 
     </ul> <p>Moreover, repository type of LiveCycle and AEM Forms are different. For available repository types and related information, see <a href="../../forms/using/choosing-persistence-type-for-aem-forms.md">Choosing a persistence type for an AEM Forms installation</a>. </p> </li> 
    <li><p>Create a backup of LiveCycle ES3 database, Global Data Storage (GDS), and Content Repository (not required for document security). If you're upgrading to MongoMK or RDBMK persistence, export LiveCycle ES3 correspondence management assets as an archive.</p> </li> 
    <li><p>Ensure your existing platform (that is, application server, database, operating system, Adobe Acrobat, third-party applications, and hardware) is supported for AEM 6.4 Forms on JEE. For information about supported hardware and software, refer to the <a href="../../forms/using/AEM-forms-JEE-supported-platforms.md" target="_blank">Supported Platform Combinations</a> document.</p> <p>If you create a fresh instance of the database, import the data backed up in step 3 to the database. For information about how to import data to a database, see documentation of corresponding database vendor.<br /> </p> 
     <note type="note"> 
      <p>If you are using RDBMK persistence format, use single database for both repository persistence and document services running on AEM Forms on JEE.</p> 
     </note></li> 
   </ol></li> 
  <li><p>Perform the upgrade:</p> 
   <ol> 
    <li> 
     <div>
       Install AEM 6.4 Forms on JEE on a new server by running the installation program. The installer places all of the required files onto your computer, within one installation directory structure. 
     </div> </li> 
    <li><p>After installation is complete, run the <strong>Configuration Manager </strong>to configure various AEM Forms modules and set appropriate configurations. Along with configuring settings, it allows to specify the path of Global Data Storage (GDS) and crx-repository. </p> 
     <note type="note"> 
      <p>On the Upgrade Task Selection screen, select the <strong>Upgrade from Adobe Experience Manager Forms 6.2.0</strong> option. The <strong>Upgrade from Adobe Experience Manager Forms 6.2.0</strong> option allows the configuration manager to upgrade from LiveCycle ES3 to AEM 6.4 Forms.<br /> </p> 
     </note></li> 
    <li><p>(Not required for AEM Forms document security module) Upgrade and import the CRX repository to AEM 6.4 Forms server.</p> 
     <note type="note"> 
      <ul> 
       <li>After the crx-repository is upgraded and the content is migrated, change the password of the admin account. For detailed instructions, see <a href="../../sites/administering/using/granite-user-group-admin.md">Changing the Password for an Existing User</a>.</li> 
      </ul> 
     </note></li>   
   </ol></li> 
  <li><p>Perform the post-deployment tasks to verify login credentials, configure document services, correspondence management, document security, and more depending on your use case.</p> </li> 
  <li><p>Verify that the server is upgraded successfully:<br /> </p> <p>Perform a few routine operations on upgraded AEM Forms server to ensure that the server is upgraded successfully. You can fill and submit a few migrated forms or protect documents to ensure a successful upgrade.<br /> </p> 
   <note type="note"> 
    <p>In AEM 6.4 Forms, the structure of crx-repository has changed. After you upgrade to AEM 6.4 forms, use the changed paths for customization that you create afresh. For the complete list of changed paths, see <a href="../../sites/deploying/using/forms-repository-restructuring-in-aem-6-4.md" target="_blank">Forms Repository Restructuring in AEM 6.4</a>.</p> 
   </note></li> 
 </ol> 
 <p><strong>Depending on your existing environment and application server, choose one of the following documents and follow the detailed instructions:</strong></p> 
 <ul> 
  <li><a href="assets/upgrade-jboss-livecycle-es3.pdf" target="_blank">Upgrade from LiveCycle ES3 to AEM 6.4 Forms for JBoss</a></li> 
  <li><a href="assets/upgrade-weblogic-livecycle-es3.pdf" target="_blank">Upgrade from LiveCycle ES3 to AEM 6.4 Forms for WebLogic</a></li> 
  <li><a href="assets/upgrade-websphere-livecycle-es3.pdf" target="_blank">Upgrade from LiveCycle ES3 to AEM 6.4 Forms for WebSphere</a></li> 
  <li><a href="assets/upgrade-turnkey-livecycle-es3.pdf" target="_blank">Upgrade from LiveCycle ES3 to AEM 6.4 Forms using JBoss Turnkey</a></li> 
 </ul> 
</details>

Download the [AEM 6.3 QuickStart](https://docs.adobe.com/docs/en/aem/6-3/deploy.html#Getting%20the%20software).

Upgrade your AEM 6.2 instance to AEM 6.3. For step by step instructions, see [https://docs-author.corp.adobe.com/content/docs/en/aem/6-3/deploy/upgrade.html](https://docs.adobe.com/docs/en/aem/6-3/release-notes.html)

**(Unix/Linux-based installations only)** If you are using UNIX or Linux as the underlying operating system, open the terminal window, navigate to the folder containing crx-quickstart, and run the following command:

`chmod -R 755 ../crx-quickstart`

[Work in Progress]

Migration involves moving only assets (PDF, XDP, images, adaptive forms, correspondence management assets) from one server to another - processes (LCA), settings, configurations, and a few other pieces of metadata are not migrated. Perform the following steps to migrate to AEM 6.3 Forms:

1. Set up a fresh environment of [AEM 6.3 Forms](http://adobe.com/go/learn_aemforms_documentation_63). 
1. Move XDP or other compatible assets to the freshly set instance. For detailed instructions, see [Importing and exporting assets to AEM Forms](../../forms/using/import-export-forms-templates.md). [  
   ](../../forms/using/import-export-forms-templates.md) 
1. Build the required services, if any.

   For example, if you are using AEM Forms on JEE Document Services, changes are required in the code to use document services available in AEM Forms on OSGi.

1. Perform post-installation activities:

    * **Run Migration Utility**

      The migration utility makes the adaptive forms and correspondence management assets of earlier versions compatible with AEM 6.3 forms. You can download the utility from AEM package share. For step-by-step information to configure and use the migration utility, see [migration utility](../../forms/using/migration-utility.md) documentation.
    
    * **Reconfigure Adobe Sign**

      If you had Adobe Sign configured in the previous version of AEM Forms, then reconfigure Adobe Sign from AEM Cloud services. For more details, see [Integrate Adobe Sign with AEM Forms](../../forms/using/adobe-sign-integration-adaptive-forms.md).

      Moreover, AEM 6.3 Forms release has introduced many new Adobe Sign features. For step-by-step information to use Adobe Sign, see [Using Adobe Sign in an adaptive form](../../forms/using/working-with-adobe-sign.md).
    
    * **Reconfigure analytics and reports  
      **

      In AEM 6.3 Forms, traffic variable for source and success event for impression are not available. So, when you upgrade to AEM 6.3 Forms, AEM Forms stops sending data to Adobe Analytics server and analytics reports for adaptive forms are not available. Moreover, AEM 6.3 Forms introduces traffic variable for the version of form analytics and success event for the amount of time spent on a field. So, reconfigure analytics and reports for your AEM Forms environment. For detailed steps, see [Configuring analytics and reports](../../forms/using/configure-analytics-forms-documents.md).

      Methods to calculate average fill time for forms and average read time for have changed. So, when you upgrade to AEM 6.3 forms, older data (data from previous AEM Forms release) for these metrics is available only in Adobe Analytics. It is not visible in AEM Forms analytics reports. For these metrics, AEM Forms analytics reports display data which is captured after performing the upgrade.

[TBD]
