---
title: AEM Forms JEE Patch Installer
description: null
uuid: e709871b-c04c-43bb-a7d0-45e89fbd3d44
content-type: reference
discoiquuid: 83bace08-1d4f-4192-a634-c7c4879963d8
---

# AEM Forms JEE Patch Installer {#aem-forms-jee-patch-installer}

>[!NOTE]
>
>[Contact Support](https://www.adobe.com/account/sign-in.supportportal.html) for more information or to obtain the patch.

## About the patch installer {#about-the-patch-installer}

The AEM 6.4 Forms JEE patch installer includes all fixed issues for all components of AEM 6.4 Forms JEE available until the release of this patch. See the latest  [Cumulative Fix Pack Release Notes](cfp-release-notes.md) for a complete list of fixed issues.

## Prerequisites to installing the patch {#prerequisites-to-installing-the-patch}

* AEM 6.4 Forms

## Installing and configuring the patch {#installing-and-configuring-the-patch}

1. Take a backup of the &lt;*AEM_forms_root*&gt;/deploy folder. It is required if you decide to uninstall the quick fix.
1. Stop your application server.
1. Extract the patch installer archive file to your hard drive.
1. In the directory named according to the operating system that you are using:

    * **Windows** 
      Navigate to the appropriate directory on the installation media or folder on your hard disk where you copied the installer, and double-click the `aemforms64_cfp_install.exe` file.

        * (Windows 32-bit) `Windows\Disk1\InstData\VM`
        * (Windows 64-bit) `Windows_64Bit`\ `Disk1\InstData\VM`

    * **Linux, Solaris, AIX** 
      Navigate to the appropriate directory, and from a command prompt, type `./aem64_cfp_install.bin`.

        * (Linux) `Linux/Disk1/InstData/NoVM`
        * (Solaris) `Solaris/Disk1/InstData/NoVM`
        * (AIX)
        
          ```        
          AIX/Disk1/InstData/VM
          ```

   This launches an install wizard that guides you through the installation.

1. On the Introduction panel, click **[!UICONTROL Next]**.
1. On the Choose Install Folder screen, verify that the default location displayed is correct for your existing installation, or click **[!UICONTROL Browse]** to select the alternate folder where AEM forms  is installed, and click **[!UICONTROL Next]**.

1. Read the Quick Fix Patch Summary information and click **[!UICONTROL Next]**.
1. Read the Pre-Installation Summary information and click **[!UICONTROL Install]**.
1. When the installation is complete, click **[!UICONTROL Next]**to apply the quick fix updates to your installed files.
1. [Windows only] Perform one of the following steps:

    * Deselect the Start Configuration Manager option before you click Done. Run Configuration Manager later by using the `ConfigurationManager.bat` file located in `[aem-forms root]\configurationManager\bin`. Using `ConfigurationManager.bat` helps you avoid manually updating name of axis.jar name in .lax files
    * Deselect the Start Configuration Manager option before you click Done. Before running configuration manager using **ConfigurationManager.exe** or **ConfigurationManager_IPv6.exe**, navigate to *&lt;AEMForms_Install_Dir&gt;\configurationManager\bin* directory and update **axis.jar** to **axis-1.4.1.1.jar** in the following files:

      * ConfigurationManager.lax
      * ConfigurationManager_IPv6.lax

1. (Unix-based only) The Start Configuration Manager check box is selected by default. Click **[!UICONTROL Done]** to run the Configuration Manager.

   To run Configuration Manager later, deselect the Start Configuration Manager option before you click Done. You can start Configuration Manager later using the appropriate script in the `[AEM_forms_root]/configurationManager/bin` directory.

1. Depending on your application server, choose one of the following documents and follow the instructions in the *Configuring and Deploying AEM forms* section.

    * [Installing and Deploying AEM forms for JBoss](http://www.adobe.com/go/learn_aemforms_installJBoss_64)
    * [Installing and Deploying AEM forms for WebSphere](http://www.adobe.com/go/learn_aemforms_installWebSphere_64)
    * [Installing and Deploying AEM forms for WebLogic](http://www.adobe.com/go/learn_aemforms_installWebLogic_64)

1. (JBoss only) After installing the patch and configuring the server, delete  tmp  and work directories of JBoss application server.

## Post-deployment configurations {#post-deployment-configurations}

### SAML configurations {#saml-configurations}

If you had SAML authentication configured and facing issues with large IDP metadata, do the following after installing the patch:

1. Set the following system property in your application server:  
   `um.saml.enable.large.xml=true`

1. Restart the server.
1. Delete existing SAML auth providers and add them again for existing domains as described in SAML settings.

## Impacted Modules {#impacted-modules}

* Document Services  
* Document Security
* Foundation JEE
* PDFG Service

[Contact Support](https://www.adobe.com/account/sign-in.supportportal.html)
