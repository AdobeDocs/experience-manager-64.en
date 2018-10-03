---
title: Enabling HTTP Over SSL
seo-title: Enabling HTTP Over SSL
description: null
seo-description: Learn how to enable and configure HTTP over SSL in AEM.
uuid: 8126c0c2-85ad-43b9-a20a-80177504f170
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/config-ssl
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 52.736-0400
cq-lastmodifiedby: msm-service
cq-lastreplicated: 2018-04-03T08 39 49.803-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 33b9bc21-1373-4619-a206-076dc21e8f1a
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:18:13.796-0400
gnavtheme: light
isreadyforlocalization: false
jcr-created: 2018-02-07T08 01 35.441-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:39:48.622-0400
lochandoffdate: 2018-04-30T03 26 52.735-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Enabling HTTP Over SSL
noindex: true
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 39 48.622-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/config-ssl.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/config-ssl
redirecttarget: /content/help/en/experience-manager/6-4/sites/administering/using/ssl-by-default
sha1: c5137a2d14270bef8673734b14b3d9e63d744120
topicBrowsingSortDate: 2018-04-03T08:39:48.622-0400
index: y
internal: n
snippet: y
translate: y
---

# Enabling HTTP Over SSL

Enable HTTP over SSL to employ more secure connections to your servers. Configure the following items in your environment according to the connections that you wish to secure:

* **Author instance:** Secure client connections to the author instance.
* **Publish instance:** Secure client connections to the publish instance.
* **Replication agents on author:** Secure connections from the author instance to the publish. instance.
* **Web server that hosts Dispatcher:** Secure client connections to the web server (and, indirectly, to the publish instance)

For information about connecting replication agents to the publish instance using MSSL, see [Replicating Using Mutual SSL](mssl-replication.md). 

---

## Obtain or Create the Credential

Create or obtain the credential that the server uses to sign HTTP messages:

* For development environments, a self-signed certificate is adequate. When self-signed certificates are used for SSL, the web browser requires you to manually trust the certificate when opening a web page.
* For production environments, use a certificate that is signed by a certificate authority (CA). When the public certificate of the CA is imported in the web browser, your certificate is automatically trusted.

### Create a Credential for Development

Use the Java keytool to create a self-signed credential and to store it in a keystore file. The following procedure uses a single command that includes all of the information needed to create the keystore. For complete information about the command, see the [Oracle Java SE Documentation](http://docs.oracle.com/javase/6/docs/technotes/tools/solaris/keytool.html).

1. Create a directory named ssl in the directory where the quickstart JAR file is located.

1. In the command prompt, type the following command to create the credential and keystore:

   ```shell
   keytool -genkeypair -keyalg RSA -validity 3650 -alias cqse -keystore [quickstart_dir]/ssl/keystorename.keystore  -keypass key_password -storepass  storepassword -dname "CN=Host Name, OU=Group Name, O=Company Name,L=City Name, S=State, C=Country_ Code"
   ```

The following example generates a private/public key pair with the following properties:

* alias: cqse
* keystore file: cqkeystore.keystore
* key password: password
* keystore password: password

```shell
keytool -genkeypair -keyalg RSA -validity 3650 -alias cqse -keystore ~/Applications/cq5.5/author/ssl/cqkeystore.keystore -keypass password -storepass password -dname "CN=sbroders-w7, OU=CQ, O=Adobe, L=Ottawa, S=Ontario, C=CA"
```

### Obtain a Credential for Use in Production

In production environments you should use a certificate that is signed from a trusted certificate authority (CA). Use the Java keytool to generate a certificate signing request, and when obtained import it to your keystore.

#### Generate a Certificate Signing Request (CSR)

1. Use keytool to generate the public/private key pair and add it to a keystore (See [Create a Credential for Development](#CreateaCredentialforDevelopment)).

1. Type the following command to generate a certificate request:

   ```shell
   keytool -certreq -alias "LC Cert" -keystorekeystorename.keystore -file LCcertRequest.csr
   ```

1. When you recieve the signed certificate from the CA, complete the next procedure.

#### Use a Credential Obtained from a CA to Enable SSL

1. In a command prompt, type the following command to import the trusted certificate of the CA into your keystore:

   ```shell
   keytool -importcert -trustcacerts -file rootcert.pem -keystorekeystorename.keystore -alias root
   ```

   You must configure the project and path.

1. Type the following command to import your signed credential into the keystore:

   ```shell
   keytool -importcert -trustcacerts -file CACertificateName.crt -keystore keystorename.keystore
   ```

   >[!NOTE]
   >
   ><p>In version 6 of Java SE, the <span class="code">-import</span> command is renamed to <span class="code">-importcert</span>.&nbsp;</p>

---

## Enable SSL on the Author Instance

Configure the Apache Felix Jetty-based HTTP service to use SSL, employing your certificate.

1. Open CRXDE Lite and select the `/apps` folder. Click **Create** > **Create Folder** to create a folder named `system` ( [http://localhost:4502/crx/de](http://localhost:4502/crx/de)).

1. Below the system folder create a folder named `config.author`.

1. Select the `/apps/system/config.author` node.

1. Click **Create **&gt; **Create Node** and enter the following properties:

    * **Name**: `org.apache.felix.http`    
    * **Type**: `sling:OsgiConfig`

1. Add properties to the node according to the following table:

   | Name |Type |Value |
   |---|---|---|
   | `org.apache.felix.https.enable` | `Boolean` | `true` |
   | `org.osgi.service.http.port.secure` | `Long` | `5433` |
   | `org.apache.felix.https.nio` | `Boolean` | `true` |
   | `org.apache.felix.https.keystore` | `String` | `*[quickstart_dir]*/ssl/cqkeystore.keystore` |
   | `org.apache.felix.https.keystore.password` | `String` |The password. |
   | `org.apache.felix.https.keystore.key` | `String` |alias e.g. `cqse` |
   | `org.apache.felix.https.keystore.key.password` | `String` |The password. |
   | `org.apache.felix.https.truststore` |String |Path to truststore |
   | `org.apache.felix.https.truststore.password` |String |Truststore password. |
   | `(Optional) org.apache.felix.https.clientcertificate` |String |Defaults to none |

1. Click **Save All**.

---

## Enable SSL on the Publish Instance

Enable HTTP over SSL on the publsih instance to secure connections with web clients and with replication agents. (Secure connections with replication agents also require changes to the agent configurations, which is described in the next section.)

Follow the same procedure as for configuring the author instance, with the following differences:

* Create the org.apache.felix.http node below /apps/system/config.publish on the publish instance ( [http://localhost:4503/crx/de](http://localhost:4503/crx/de)).
* If your author and publish instances are on the same computer, use a different port for the `org.osgi.service.http.port.secure`property.

---

## Configure Replication Agents to Use Secure URLs

If you want content replication to occur using HTTP over SSL, configure replication agents to use the HTTPS protocol and the port that the publish instance uses for SSL.

The following procedure configures the publish agent on the author instance. Perform the procedure for all replication agents that you want to communicate over SSL.

1. Open the Tools page ( [http://localhost:4502/miscadmin](http://localhost:4502/miscadmin)).

1. Click the **Tools/Replication/Agents** on author folder.

1. In the right-hand frame, right-click **Default Agent **and click **Open**.

1. Click **Edit** (below the **Test Connection** link) and then click the **Transport** tab.

1. In the URI box, change the URL so that it uses the HTTPS protocol and the port that you configured for SSL on the publish instance.

1. If you used a self-signed certificate to enable SSL on publish, select **Enable Relaxed SSL**.

1. Click **OK**.

1. Click** Test Connection**.

---

## Forcing the Use of the SSL Port

If you want all users to connect over SSL, redirect traffic to the URL that uses HTTP over SSL.

>[!NOTE]
>
><p>The steps presented below do not force the use of the SSL port for HTTP requests to CRXDE Lite, Package Manager or Content Explorer. The requests going to these administrative consoles do not go through the Sling request pipeline. For these scenarios, you should utilize Dispatcher to redirect the requests by using the Apache Web Server. For further details, see the <a href="https://docs.adobe.com/content/docs/en/dispatcher/disp-install.html#Apache Web Server - Add the Dispatcher Module" >Dispatcher</a>&nbsp;and the <a href="https://httpd.apache.org/docs/2.4/rewrite/avoid.html#redirect" >official Apache</a> documentation.</p>

The following example redirects traffic to `localhost:4502` to `https://localhost:5433`. To configure the redirect, create a `sling:mapping` node. Use a node name that matches requested URL. Add a `sling:redirect` property to specify the URL for redirection.

1. Open CRXDE Lite in your web browser ( [http://localhost:4502/crx/de](http://localhost:4502/crx/de)).

1. Click the `/etc/map/http`** **folder and click **Create **&gt; **Create Node**:

    * **Name**: `localhost.4502`    
    * **Type**: `sling:mapping`

1. Create the following property for this node:

    * **Name**: `sling:redirect`    
    * **Type**: `String`    
    * **Value**: `https://localhost:5433`

1. Click **Save All**.

Alternatively, you can specify the text for matching the requested URL as a `sling:match` property (See [Mappings for Resource Resolution](http://sling.apache.org/site/mappings-for-resource-resolution.html) in the Apache Sling documentation).

---

## Configuring SSL When Using a Dispatcher

When client requests target a dispatcher before reaching an author or publish instance, decide which requests are transmitted over SSL:

* From users to the web server.
* From the author instance to the dispatcher via the flush replication agent.

This section assumes that you have already installed and configured Dispatcher on your web server (See [Dispatcher](https://docs.adobe.com/content/docs/en/dispatcher.html)).

For information about configuring Dispatcher to use SSL connections with the publish instance, see [Using SSL with Dispatcher](https://docs.adobe.com/content/docs/en/dispatcher/disp-ssl.html).

### Configure the Web Server

Configure the web server to use SSL to secure connections between web clients and the web server. For information about enabling SSL for the web server, see the documentation for your web server.

* Apache HTTP Server: [http://httpd.apache.org/docs/2.0/ssl/ssl_howto.html](http://httpd.apache.org/docs/2.0/ssl/ssl_howto.html)
* Microsoft IIS: [http://learn.iis.net/page.aspx/144/how-to-set-up-ssl-on-iis/](http://learn.iis.net/page.aspx/144/how-to-set-up-ssl-on-iis/)
* Oracle iPlanet Web Server: [http://docs.oracle.com/cd/E19146-01/821-1828/gbthq/index.html](http://docs.oracle.com/cd/E19146-01/821-1828/gbthq/index.html)

Enabling separate caches for secure and unsecure connection types is beyond the scope of this article. However, you could investigate the following strategies:

* Route all SSL connections to a separate Apache web server and Dispatcher on a different subdomain.
* Use URL redirection rules (for example mod_rewrite directives on Apache) to cache content to different locations below DocumentRoot.

### Send Flush Requests over SSL

If you want to send flush requests to the dispatcher over SSL, configure the Dispatcher Flush replication agent.

Follow the procedure in [Configure Replication Agents](#ConfigureReplicationAgents), using the SSL port that is confgured for the web server (typically 443).
