---
title: WebDAV Access
seo-title: WebDAV Access
description: null
seo-description: Learn about WebDAV access in AEM.
uuid: 847b4bfa-ebbc-498c-b703-0aba62a52ed0
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: ae8ae078-ecc7-441b-b4ff-65dd4d830f1c
index: y
internal: n
snippet: y
---

# WebDAV Access{#webdav-access}

To connect to AEM via WebDAV with KDE:

AEM offers WebDAV support that lets you display and edit repository content. Connecting via WebDAV gives you direct access to the content repository through your desktop. Text and PDF files that are added to the repository through the WebDAV connection are automatically full-text indexed and can be searched with the standard search interfaces and through the standard Java APIs.

## General {#general}

[Detailed instructions per operating system](../../../sites/administering/using/webdav-access.md#main-pars-title-1659997064) are included in this document, but the essentially to connect to your repository using the WebDAV protocol, you point your WebDAV client to the following location:

```xml
http://localhost:4502
```

![](assets/chlimage_1-123.png)

This URL, when connected from the operating system level, provides WebDAV access to the default workspace ( `crx.default`). While being simpler for the user, it does not give them the additional flexibility of specifying workspace names, which can be accomplished using additional [WebDAV URLs](../../../sites/administering/using/webdav-access.md#main-pars-title-812278149).

AEM displays the repository content as follows:

* A node of the type `nt:folder` is displayed as a folder. Nodes below the `nt:folder` node are displayed as the folder content.

* A node of the type `nt:file` is displayed as a file. Nodes below the `nt:file` node are not displayed, but form the content of the file.

When you use WebDAV to create and edit folders and files, AEM creates and edits the necessary `nt:folder` and `nt:file` nodes. If you plan to use WebDAV to import and export content, try to work with `nt:file` and `nt:folder` node types as much as possible.

>[!NOTE]
>
>Before setting up WebDAV, please check the [Technical Requirements](../../../sites/deploying/using/technical-requirements.md#main-pars-title-29).

## WebDAV URLs {#webdav-urls}

The URL for the WebDAV server has the following structure:

<table> 
 <colgroup>
  <col width="100" />
  <col width="100" />
  <col width="100" />
  <col width="100" />
  <col width="100" />
 </colgroup>
 <tbody>
  <tr>
   <td>
    <nobr>
     <strong>URL Component</strong>
    </nobr></td> 
   <td><span class="code">http://&lt;host&gt;:&lt;port&gt;</span></td> 
   <td><span class="code">/&lt;crx-webapp-path&gt;</span></td> 
   <td><span class="code">/repository</span></td> 
   <td><span class="code">/&lt;workspace&gt;</span></td> 
  </tr>
  <tr>
   <td>
    <nobr>
     <strong>Example</strong>
    </nobr></td> 
   <td><span class="code">http://localhost:4502</span></td> 
   <td><span class="code">/crx</span></td> 
   <td><span class="code">/repository</span></td> 
   <td><span class="code">/crx.default</span></td> 
  </tr>
  <tr>
   <td><strong>Description</strong></td> 
   <td>Host and port on which AEM runs</td> 
   <td>Path for the AEM repository webapp</td> 
   <td>Path to which WebDAV servlet is mapped</td> 
   <td>Name of the workspace</td> 
  </tr>
 </tbody>
</table>

By changing the workspace element in the path, you can map workspaces other than the default ( `crx.default`). For example, to map a workspace named `staging`, use the following URL:

```xml
http://localhost:4502/crx/repository/staging
```

## Connecting via WebDAV {#connecting-via-webdav}

[As mentioned above](../../../sites/administering/using/webdav-access.md#main-pars-title), to connect to your repository using the WebDAV protocol, you point your WebDAV client to your repository location. However depending on your OS, the steps involved to connect your client differ and there may be configuration of the OS required.

Instructions on how to connect the following opererating systems are provided:

* [Windows](../../../sites/administering/using/webdav-access.md#main-pars-title-1061601332)
* [macOS](../../../sites/administering/using/webdav-access.md#main-pars-title-899281330)
* [Linux](../../../sites/administering/using/webdav-access.md#main-pars-title-1743152979)

### Windows {#windows}

To successfully connect a Microsoft Windows 7 (and greater) system to an AEM instance that is not secured with SSL, the option to establish basic authentication over an unsecured network must be explicitly enabled in Windows. This requires a change in the Windows Registry of the WebClient.

Once the registry is updated, then the AEM instance can be mapped as a drive.

#### Windows 7 and Greater Configuration {#windows-and-greater-configuration}

To update the registry to allow basic authentication over an unsecured network:

1. Locate the following registry subkey:

   ```xml
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WebClient\Parameters
   ```

1. Set the `BasicAuthLevel` registry entry subkey to a value of `2` or greater.

   If it is not present, add the subkey.

1. You must restart the system for the registry change to take effect.

See [Microsoft Support KB 841215](http://support.microsoft.com/default.aspx/kb/841215) for more information on this registry change.

See [Microsoft Support KB 2445570](http://support.microsoft.com/kb/2445570) for information about improving the responsivness of the WebDav Client under Windows.

>[!NOTE]
>
>Adobe recommends that you create a Windows user with the same credentials as the repository user, otherwise you may encounter permission conflicts.

#### Windows 8 Configuration {#windows-configuration}

For Windows 8 you also need to change the registry entry [as described for Windows 7 and greater](../../../sites/administering/using/webdav-access.md#main-pars-title-1834264689). However, before you can do this, the Desktop Experience must be enabled in order to see the registry entry.

To enable the Desktop Experience, open **Server Manager**, then **Features**, then **Add Features**, then **Desktop Experience**.

After rebooting the registry entry described for Windows 7 and greater is available. Modify it as described for Windows 7 and greater.

#### Connecting in Windows {#connecting-in-windows}

To connect to AEM via WebDAV in a Windows environment:

1. Open **Windows Explorer** or **File Explorer** and click on **Computer** or **This PC**.

   ![](assets/chlimage_1-124.png)

1. Click **Map network drive** to start the wizard.
1. Enter the mapping details:

    * **Drive**: Choose any available letter
    * **Folder**: `http://localhost:4502`
    
    * Check **Connect using different credentials**

   Click Finish

   ![](assets/chlimage_1-125.png)

   >[!NOTE]
   >
   >If AEM is located on another port, use that port number instead of 4502. Also, if you are not running the content repository on your local machine, replace `localhost` with the respective server name or IP address.

1. Enter username `admin` and password `admin`. Adobe recommends that you use the pre-configured admin account for testing.

   ![](assets/chlimage_1-126.png)

1. The wizard closes and the newly-mapped drive is opened in a Windows Explorer or File Explorer window.

   ![](assets/chlimage_1-127.png)

Windows has now mapped AEM as a drive via WebDAV and you can use it as any other drive.

### macOS {#macos}

There are no configuration steps required to connect via WebDAV on macOS. You simply need to connect to the WebDAV server.

1. Navigate to any **Finder **window and click **Go **and **Connect to Server**, or press **Command+k**.
1. In the **Connect to Server** window, enter the AEM location:

    * `http://localhost:4502`

   >[!NOTE]
   >
   >If AEM is located on another port, use that port number instead of 4502. Also, if you are not running the content repository on your local machine, replace `localhost` with the respective server name or IP address.

1. When you are prompted for authentication, enter username `admin` and password `admin`. Adobe recommends that you use the pre-configured admin account for testing.

macOS has now connected to AEM via WebDAV and you can use it as any other folder on your Mac.

### Linux {#linux}

Connecting via WebDAV on Linux doesn't require any configuration, but does involve a few steps to make the connection which vary depending on your desktop environment.

#### GNOME {#gnome}

To connect to AEM via WebDAV with GNOME:

1. In Nautilus (file explorer), select **Places** and select **Connect to Server**.
1. In the **Connect to Server **window, select WebDAV (HTTP) in Service Type.  

1. In **Server**, enter `http://localhost:4502/crx/repository/crx.default`

   >[!NOTE]
   >
   >If AEM is located on another port, use that port number instead of 4502. Also, if you are not running the content repository on your local machine, replace `localhost` with the respective server name or IP address.

1. In** Folder**, enter `/dav`
1. Enter the username `admin`*. *Adobe recommends that you use the pre-configured admin account for testing.
1. Leave the port blank and enter any name for your connection.
1. Click **Connect**. AEM prompts you for your password.
1. Enter the password `admin` and click **Connect**.

GNOME has now mounted AEM as a volume and you can use it like any other volume.

#### KDE {#kde}

1. Open the Network Folder wizard.
1. Select **WebFolder **(webdav) and click Next.
1. In **Name**, type a connection name.
1. In **User**, enter `admin.` Adobe recommends that you use the pre-configured admin account.
1. In **Server**, enter `http://localhost:4502/crx/repository/crx.default`

   >[!NOTE]
   >
   >If AEM is located on another port, use that port number instead of 4502. Also, if you are not running the content repository on your local machine, replace `localhost` with the respective server name or IP address

1. In **Folder**, enter `dav`  

1. Click **Save and Connect**.
1. When prompted for your password, enter the password `admin` and click **Connect**.

KDE has now mounted AEM as a volume and you can use it like any other volume.
