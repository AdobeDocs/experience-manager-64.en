---
title: Mitigating serialization issues in AEM
seo-title: Mitigating serialization issues in AEM
description: null
seo-description: Learn how to mitigate serialization issues in AEM.
uuid: 52b25e16-8681-4699-92ea-70edd517b217
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: ca3a2f19-b05b-44bc-9dfd-35e3bb59c0db
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Mitigating serialization issues in AEM{#mitigating-serialization-issues-in-aem}

## Overview {#overview}

The AEM team at Adobe has been working closely with the open source project [NotSoSerial](https://github.com/kantega/notsoserial) to assist in mitigating the vulnerabilities described in **CVE-2015-7501**. NotSoSerial is licensed under the [Apache 2 license](http://www.apache.org/licenses/LICENSE-2.0) and includes ASM code licensed under its own [BSD-like license](http://asm.ow2.org/license.html).

The agent jar included with this package is Adobe's modified distribution of NotSoSerial. For more information, see the [Revision History](../../administering/using/mitigating-serialization-issues.md#main-pars-title-95812971) section below.  
  
NotSoSerial is a Java level solution to a Java level problem and is not AEM specific. It adds a preflight check to an attempt to deserialize an object. This check will test a class name against a firewall-style whitelist and/or blacklist. Due to the limited number of classes in the default blacklist, this is unlikely to have an impact on your systems or code.

By default, the agent will perform a blacklist check against current known vulnerable classes. This blacklist is intended to protect you from the current list of exploits that use this type of vulnerability.

The blacklist and whitelist can be configured by following the instructions in the [Configuring the Agent](../../administering/using/mitigating-serialization-issues.md#main-pars-title-421094637) section of this article.

The agent is intended to help mitigate the latest known vulnerable classes. If your project is deserializing untrusted data, it may still be vulnerable to denial of service attacks, out of memory attacks, and unknown future deserialization exploits.  
  
Adobe officially supports Java 6, 7, and 8, however our understanding is that NotSoSerial supports Java 5 as well.

## Installing the Agent {#installing-the-agent}

>[!NOTE]
>
>If you have previously installed the serialization hotfix for AEM 6.1, please remove the agent start commands from your java execution line.

1. Install the **com.adobe.cq.cq-serialization-tester** bundle.  

1. Go to the Bundle Web Console at `http://server:port/system/console/bundles`
1. Look for the serialization bundle and start it. This should dynamically autoload the NotSoSerial agent.

<!--
Comment Type: remark
Last Modified By: (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:00:47.998-0500
<p>To verify. The name of the bundle seems to have changed with 6.2 L18. Also, it doesn't look like it requires explicit installation.<br /> </p>
-->

## Installing the Agent on Application Servers {#installing-the-agent-on-application-servers}

The NotSoSerial agent is not included in the stardard distribution of AEM for application servers. However, you can extract it from the AEM jar distribution and use it with your application server setup:

1. First, download the AEM quickstart file and extract it:

   ```shell
   java -jar aem-quickstart-6.2.0.jar -unpack
   ```

1. Go to the location of the newly unzipped AEM quickstart, and copy the `crx-quickstart/opt/notsoserial/` folder to the `crx-quickstart` folder of the AEM application server installation.  

1. Change the ownership of `/opt` to the user running the server:

   ```shell
   chown -R opt <user running the server>
   ```

1. Configure and check that the agent has been properly activated as shown in the following sections of this article.

## Configuring the agent {#configuring-the-agent}

The default configuration is adequate for most installs. This includes a blacklist of known remote execution vulnerable classes and a whitelist of packages where deserialization of trusted data should be relatively safe.

The firewall configuration is dynamic, and can be changed at any time by:

1. Going to the Web Console at `http://server:port/system/console/configMgr`
1. Searching for and clicking **Deserialization Firewall Configuration.**

   >[!NOTE]
   >
   >You can also reach the configuration page directly by accessing the URL at:
   >
   >    
   >    
   >    * `http://server:port/system/console/configMgr/com.adobe.cq.deserfw.impl.DeserializationFirewallImpl`
   >    
   >

This configuration contains the whitelist, blacklist, and deserialization logging.

**Whitelisting**

In the whitelisting section, these are classes or package prefixes that will be allowed for deserialization. It is important to be aware that if you are deserializing classes of your own, you will need to add either the classes or packages to this whitelist.

**Blacklisting** 
  
In the blacklisting section are classes that are never allowed for deserializaiton. The initial set of these classes is limited to classes that have been found vulnerable to remote execution attacks. The blacklist is applied before any whitelisted entries.

**Diagnostinc Logging** 
  
In the section for diagnostic logging, you can chose several options to log when deserialization is taking place. These are only logged on first use, and are not logged again on subsequent uses.  
  
The default of **class-name-only** will inform you of the classes that are being deserialized.

You can also set the **full-stack** option which will log a java stack of the first deserialization attempt to inform you where your deserialization is taking place. This can be useful for finding and removing deserialization from your usage.

## Verifying the Agent's Activation {#verifying-the-agent-s-activation}

You can verify the deserialization agent's configuration by browsing to the URL at:

* `http://server:port/system/console/healthcheck?tags=deserialization`

Once you access the URL, a list of health checks related to the agent will be displayed. You can determine if the agent is properly activated by verifying that the health checks are passing. If they are failing, you may need to load the agent manually.

For more information on troubleshooting issues with the agent, see [Handling Errors With Dynamic Agent Loading](#main-pars-title-1104713798) below.

>[!NOTE]
>
>If you add `org.apache.commons.collections.functors` to the whitelist, the health check will always fail.

## Handling errors with dynamic agent loading {#handling-errors-with-dynamic-agent-loading}

If errors are exposed in the log, or the verification steps detect a problem loading the agent, you might need to load the agent manually. This is also recommended in case you are using a JRE (Java Runtime Environment) instead of a JDK (Java Development Toolkit), since the tools for dynamic loading are not available.

In order to load the agent manually, follow the below instructions:

1. Modify the JVM startup parameters of the CQ jar, adding the following option:

   ```shell
   -javaagent:<aem-installation-folder>/crx-quickstart/opt/notsoserial/notsoserial.jar
   ```

   >[!NOTE]
   >
   >This requires using the -nofork CQ/AEM option as well, along with the appropriate JVM memory settings, as the agent won't be enabled on a forked JVM.

   >[!NOTE]
   >
   >The Adobe distribution of the NotSoSerial agent jar can be found in the `crx-quickstart/opt/notsoserial/` folder of your AEM installation.

1. Stop and restart the JVM;  

1. Verify the agent's activation again by following the steps described above in [Verifying The Agent's Activation](../../administering/using/mitigating-serialization-issues.md#main-pars-title-304897080).

## Other Considerations {#other-considerations}

If you are running on an IBM JVM, please review the documentation on support for the Java Attach API at [this location](https://www.ibm.com/support/knowledgecenter/SSSTCZ_2.0.0/com.ibm.rt.doc.20/user/attachapi.html).

<!--
Comment Type: draft

<h2>Revision History</h2>
-->

<!--
Comment Type: draft

<p>Adobe has slightly modified NotSoSerial to allow for dynamic configuration and to start with an enhanced blacklist. We have contributed this source to the notsoserial project at [0]<br /> <br /> </p>
-->

<!--
Comment Type: remark
Last Modified By: (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:00:48.702-0500
<p>I don't think this should make it to public documentation. We might need to revise this if there will be a need for a revision history that lists the changes made on the Adobe version of the agent.<br /> </p>
-->

