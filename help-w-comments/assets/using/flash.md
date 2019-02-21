---
title: [Redirect] Authoring Adobe Flash Content
seo-title: Authoring Adobe Flash Content
description: null
seo-description: null
uuid: baade1a7-794f-49e4-aa9f-efee7674c5d4
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: dee27895-2b22-439f-91ae-c5b4e0827c36
noindex: true
redirecttarget: /content/help/en/experience-manager/6-4/assets/user-guide
index: y
internal: n
snippet: y
---

# [Redirect] Authoring Adobe Flash Content{#redirect-authoring-adobe-flash-content}

<!--
Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2018-03-02T03:00:37.571-0500
<p>Chiradeep to check. May be legacy</p>
-->

Do you wish to manage your Flash based AIR application the same way you manage your web site? That is: authoring Flash content without being a developer? Or enabling your customers to view your Flash based web site on an iPad? The short answer is: AEM does it all for you!

AEM enables you to:

* Author Flash content for use in an AIR application.
* Author Flash content that can be viewed on Flash disabled devices like the iPad.

### Authoring Flash Content for AIR Applications {#authoring-flash-content-for-air-applications}

The Mobile Trader application is a Flash based AIR application that can run on any Flash enabled device. It consists of a window with four tabs (Assets, Watchlist, Alerts, Advisor) displaying some financial informations in a dynamic and interactive way. Its content can be managed with AEM, the same way a web page is authored with AEM. You can for example change a title, add an image or add a new tab. Once you have modified the content with AEM, you just have to refresh the application on your desktop computer to display the modifications.

The following procedure shows you how to set up the Mobile Trader application on your computer, to modify a title with AEM and to display the modified content in the AIR application:

1. Start an author AEM instance that runs on port 4502.
1. Start a publish AEM instance that runs on port 4503.
1. Download the Mobile Trader AIR application on your desktop. The application is available in the repository at:  
   `/etc/designs/geometrixx/clientlibs/flash/MobileTrader.air`  
   To download this file, you can [map the repository to your local filesystem](../../sites/administering/using/webdav-access.md) by using the WebDAV server that is embedded into AEM.  

1. Run the Mobile Trader application on your desktop by double-clicking the `MobileTrader.air` file.  
   The application connects to the AEM publish instance.  

1. Open the Mobile Trader page in the AEM author instance: in your browser, go to:  
   `http://localhost:4502/cf#/content/geometrixx_mobile/en/trader.touch.html`

1. Modify a title:

    1. Double-click the **Performance History** title.
    1. Edit the title.
    1. Press **Enter** to save the changes.

   Note: you can also right-click the title, select **Edit Component** to open the edit dialog, edit the title and click **OK**.

1. Activate the page corresponding to the tab that you have modified. In this example, as the **Assets** tab has been modified:

    1. Go to the **Site Admin** console.
    1. Select the **Assets** page below **Websites / Geometrixx Mobile Demo Site / Mobile Trader**.
    
    1. Click **Activate**.

1. Refresh the **Mobile Trader** AIR application to see the changes:

    1. In the AIR app, click the top title **Geometrixx Financial Services**.
    1. Click **OK** below the URL field to see the modified tab.

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.647-0500
<p>step 5: when I open the page from the siteadmin, it opens the html5 version.<br /> </p>
<p>-&gt; bug 37731<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.673-0500
<p>step 7: bug: the console doesn't show the replicated status icon<br /> </p>
<p>-&gt; this is a platform (known) issue<br /> </p>
-->

You can also:

* Rearrange the order of existing components on a page by dragging and dropping them.  
* Add a Mobile Trader component:

    1. In the Sidekick, in the **Components** tab, select the **MobileTrader** panel.
    
    1. Drag and drop the component into the page.

* Delete a component:

    1. Right-click the component.  
    1. Select Delete Component in the context menu.

* Add an image:

    1. Go into Design mode and make the **Mobile Image** () component available to the page.
    1. In the Sidekick, in the **Components** tab, select the **Mobile** panel.
    
    1. Drag and drop the **Mobile Image** component into the page.
    1. Drag and drop an image from the **Content Finder** into the component.
    1. Edit the image: double-click it, modify it and click **OK**.

* Add a new tab:

    1. Right-click a tab at the bottom of the page.
    1. Select **New Tab** in the context menu.
    1. In the **Create Page** dialog, add a title, a name and select the **Geometrixx Mobile Trader Content Page** template. Click **Create**.

  Note: a tab corresponds to a AEM page.
* Delete a tab:

    1. Right-click the tab to be deleted at the bottom of the page.
    1. Select **Delete Tab** in the context menu.
    1. Click **Yes** in the Delete Page dialog.

>[!NOTE]
>
>To see the changes in the AIR application, you need to perform the steps 7 and 8 of the above procedure.

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.738-0500
<p>Is it possible to add some text?</p>
<p>I've been able to add a text component in the browser but it's not showing in the AIR app.<br /> </p>
<p>It's because the flash-text component is not enabled<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.761-0500
<p>The following section ("Authoring Flash Content for Web Sites") should be discarded as the feature should not be available in its current state. </p>
<p>The corresponding content will be removed from the repository. </p>
<p>Discussed with David N. and Tobi B. on 18.10.2011.<br /> </p>
-->

<!--
Comment Type: draft

<h3>Authoring Flash Content for Web Sites</h3>
-->

<!--
Comment Type: draft

<p>With CQ it is possible to create and manage Adobe Flash content within a browser environment. The Flash content is managed the same way a web page is authored with CQ. You can manage titles, texts and images.</p>
<p>The following procedure shows you how to create a web page that includes Flash content consisting of a title, some text and an image:</p>
<ol>
<li>In <strong>Site Admin</strong> console, create a page below <strong>Websites / Geometrixx Demo Site / English</strong>:
<ul>
<li><strong>Title</strong>: My Flash Page</li>
<li>Select the <strong>Mosaic Content Page</strong> template</li>
<li>Click <strong>Create</strong>.</li>
</ul> </li>
<li>Open the new page.</li>
<li>Add a title to the page: from the <strong>Components</strong> tab of the Sidekick, drag and drop a <strong>Title</strong> component to the page.</li>
<li>Edit the title:<br />
<ol>
<li>Click the <strong>Title</strong> component.</li>
<li>Edit the title.</li>
<li>Press <strong>Enter</strong> to save the changes.<br /> You can also double-click the <strong>Title</strong> component, define the title in the dialog and click <strong>OK</strong>.<br /> </li>
</ol> </li>
<li>Add a <strong>Text</strong> component to the page: from the <strong>Components</strong> tab of the Sidekick, drag and drop a <strong>Text</strong> component to the page.</li>
<li>Edit the text:<br />
<ol>
<li>Double-click the <strong>Text</strong> component.</li>
<li>Edit the text.</li>
<li>Click <strong>OK</strong> to save the changes.<br /> You can also right-click the <strong>Text</strong> component, define the text in the dialog and click <strong>OK</strong>.<br /> </li>
</ol> </li>
<li>Add an <strong>Image</strong> component to the page: from the <strong>Components</strong> tab of the Sidekick, drag and drop an <strong>Image</strong> component to the page.</li>
<li>Edit the image:
<ol>
<li>Drag and drop an image from the <strong>Content Finder</strong> into the <strong>Image</strong> component.</li>
<li>Edit the image: double-click it, modify it and click <strong>OK</strong>.<br /> You can also right-click the image to open the edit dialog.</li>
</ol> </li>
</ol>
<p>You can also:</p>
<ul>
<li>Rearrange the order of existing components on a page by dragging and dropping them.<br /> </li>
<li>Delete a component:
<ol>
<li>Right-click the component.<br /> </li>
<li>Select <strong>Delete Component</strong> in the context menu.</li>
</ol> </li>
</ul>
<p></p>
-->

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.822-0500
<p>the component dialog doesn't display ok (some shifts in the lines).<br /> </p>
<p>-&gt; bug 37732<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.845-0500
<p>there is a typo in the context menu of the component:<br /> 'Edit Copmonent' should be 'Edit Component'<br /> </p>
<p>-&gt; known issue<br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: Jean-Christophe Kautzmann (jkautzma)
Last Modified Date: 2018-03-02T03:00:37.867-0500
<p>doesn't work on publish (javascript error):<br /> -&gt; tobi is not planning to invest more time on this feature as it is not known yet how customer will use this feature<br /> <br /> <br /> </p>
-->

### Viewing Flash Content on an iPad {#viewing-flash-content-on-an-ipad}

When a Flash disabled device like the iPad requests a AEM page that includes Flash-AEM compatible components, AEM automatically sends the page content in HTML5 format to the device.  
  
The following procedure shows you how to access Flash content on your iPad. To access the Mobile Trader pages:

1. On your iPad, open the Safari browser and go to the page:  
   `http://<aem-server-ip>:4502/content/geometrixx_mobile/en/trader.html`

1. Login with the default credentials ( `admin/admin`).  

1. Click the **Gx** icon.  
   You can also click the link Click "Add to Home Screen" to set a bookmark on the iPad Home Screen and then click the icon: you would then view the pages in the iPad app way (without e.g. the browser navigation bar).  

1. The Flash based pages are displayed on your iPad.

>[!NOTE]
>
>There is a small icon in the top right corner of the screen that tells you if you are online (green) or offline (yellow).

