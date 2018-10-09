---
title: Application Server Install
seo-title: Application Server Install
description: null
seo-description: Learn how to install AEM with an application server.
uuid: fb13344b-35d5-4204-b813-c8c62637fe98
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/application-server-install
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 37.772-0400
cq-lastmodifiedby: msm-service
cq-lastreplicated: 2018-04-03T08 39 26.540-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: deploying
cq-template: /apps/help/templates/article-3
discoiquuid: c78ce252-c665-452c-998c-86fe951c2f76
firstPublishExternalDate: 2017-10-31T16:18:15.524-0400
isreadyforlocalization: false
jcr-created: 2018-03-13T09 02 55.459-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:39:24.200-0400
lochandoffdate: 2018-04-30T03 26 37.771-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Application Server Install
publishexternaldate: 2018-04-03T08 39 24.200-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/application-server-install.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/application-server-install
sha1: 4afcdd587a52c53afc968f951c50aefcca7a0317
topicBrowsingSortDate: 2018-04-03T08:39:24.200-0400
index: y
internal: n
snippet: y
translate: y
---

# Application Server Install

>[!NOTE]
>
>`JAR` and `WAR` are the file types AEM is released in. These formats are undergoing quality assurance to accomodate the support levels Adobe has committed to.
>

<!-- <p>This should not be the final form. To check later.<br /> </p> -->

This section tells you how to install Adobe Experience Manager (AEM) with an application server. Consult the [Supported Platforms](technical-requirements.md#ServletEnginesApplicationServers) section to see the specific support levels provided for the individual application servers.

The installation steps of the following Application Servers are described:

* [WebSphere 8.5](#WebSphere85)
* [JBoss EAP 6.3.0/6.4.0](#JBossEAP630640)
* [Oracle WebLogic 12.1.3/12.2](#OracleWebLogic1213122)
* [Tomcat 8/8.5](#Tomcat885)

Consult the appropriate application server documentation for more information on installing web applications, server configurations and how to start and stop the server.

>[!NOTE]
>
>If you are using Dynamic Media in a WAR deployment, please see the [dynamic media documentation](/content/help/en/experience-manager/6-4/assets/using/config-dynamic#EnablingDynamicMedia).

## General Description

#### Default behaviour when installing AEM in an Application Server
AEM comes as a single war file to deploy.

If deployed the following will happen by default:

* the run mode is `author`
* the instance (Repository, Felix OSGI environment, bundles etc.) is installed in `${user.dir}/crx-quickstart`where `${user.dir}` is the current working directory, this path to crx-quickstart is called `sling.home`  

* the context root is the war file name e.g : `aem-6` **[!UICONTROL   
  ]**

#### Configuration
You can change the default behaviour in the following way:

* run mode : configure the `sling.run.modes` parameter in the `WEB-INF/web.xml` file of the AEM war file before deployment

* sling.home: configure the `sling.home` parameter in the `WEB-INF/web.xml`file of the AEM war file before deployment  

* context root: rename the AEM war file

>[!NOTE]
>
>When using an EAR file , the web.xml file is located in EAR/WAR/Web-Inf.

#### Publish installation
To get a publish instance deployed you need to set the run mode to publish:

* Unpack the WEB-INF/web.xml from the AEM war file
* Change sling.run.modes parameter to publish
* Repack web.xml file into AEM war file
* Deploy AEM war file

#### Installation check
To check if all is installed you can:

* tail the `error.log`file to see that all content is installed
* look in `/system/console` that all bundles are installed

#### Two Instances on the same Application Server
For demonstration purposes it can be appropriate to install author and publish instance in one application server. For that do the following:

1. Change sling.home variable and sling.run.modes variables of the publish instance.
1. Unpack WEB-INF/web.xml file from the AEM war file.
1. Change sling.home parameter to a different path, (absolute and relative paths are possible).
1. Change sling.run.modes to publish for the publish instance.
1. Repack the web.xml file.
1. Rename the war files, so they have different names: e.g. one rename to aemauthor.war and the other to aempublish.war.
1. Use higher memory settings, e.g. for default AEM instances use e.g.: -Xmx3072m
1. Deploy the two web applications.
1. After Deployment stop the two web applications.
1. In both author and publish instances assure that in the sling.properties files the property felix.service.urlhandlers=false is set to false (default is that it is set to true).
1. Start the two web applications again.

<!-- <p>Upgrade info needs to be updated to 6.0. Until then, set old stuff to draft</p> -->

### Upgrade from previous CQ Versions
Before an upgrade read the [General Description](#GeneralDescription) above.

**Upgrade from CQ 5.5 resp CQ 5.5 SP2.1:**

1. Create a Backup from your instance.
1. Uninstall the CQ 5.5 web application (the crx-quickstart folder will remain).
1. Configure the AEM web application if needed, the sling.home and sling.run.modes parameter needs to be the same as in the CQ 5.5 version.
1. Install the AEM web application.

**Upgrade from CQ 5.4**

To upgrade from CQ 5.4 in your Application Server please consult the following page:

[Upgrading to AEM 5.6 with Application Servers](/content/docs/en/aem/6-3/deploy/upgrade/upgrading-to-5-6-1#Application Server Upgrade)

## Application Servers Installation Procedures

#### WebSphere 8.5
Before a deployment read the [General Description](#GeneralDescription) above.

**Server Preparation**

* Let Basic Auth Headers pass through:

    * One way to let AEM to authenticate a user is to disable the global administrative security of the WebSphere server, to do so: go to Security -&gt; Global Security and uncheck the Enable administrative security checkbox, save and restart the server.

* set `"JAVA_OPTS= -Xmx2048m"`
* If you want to install AEM using context root = / then you have first to change the context root of the existing Default web application

**Deploy AEM web application**

* Download AEM war file
* Make your configurations In web.xml if needed (see above in the General Description)

    * Unpack WEB-INF/web.xml file
    * change sling.run.modes parameter to publish
    * uncomment sling.home initial parameter and set this path as you need
    * Repack web.xml file

* Deploy AEM war file

    * Choose a context root (if you want to set the sling run modes you need to select the detailed steps of the deploy wizard, then specify it in step 6 of the wizard)

* Start AEM web application

#### JBoss EAP 6.3.0/6.4.0
Before a deployment read the [General Description](#GeneralDescription) above.

**Prepare JBoss server**

Set Memory arguments in your conf file(e.g. `standalone.conf`)

* JAVA_OPTS="-Xms64m -Xmx2048m"

if you use the deployment-scanner for to install the AEM web application it might be good to increase the `deployment-timeout,` for that set a `deployment-tiimeout` attribute in the xml file of your instance (e.g `configuration/standalone.xml)`:

```xml
<subsystem xmlns="urn:jboss:domain:deployment-scanner:1.1">
            <deployment-scanner path="deployments" relative-to="jboss.server.base.dir" scan-interval="5000" deployment-timeout="1000"/>
</subsystem>
```

**Deploy AEM web application**

- Upload the AEM web application in your JBoss Administration Console.

- Enable the AEM web application.

#### Oracle WebLogic 12.1.3/12.2
Before a deployment read the [General Description](#GeneralDescription) above.

This uses a simple Server Layout with only an Admin Server.

**WebLogic Server Preparation**

* In `${myDomain}/config/config.xml`add to the security-configuration section:

    * `<enforce-valid-basic-auth-credentials>false</enforce-valid-basic-auth-credentials>` see on [http://xmlns.oracle.com/weblogic/domain/1.0/domain.xsd](http://xmlns.oracle.com/weblogic/domain/1.0/domain.xsd) for the correct position (per default to position it at the end of the section is ok)

* Increase VM Memory settings:

    * open `${myDomain}/bin/setDomainEnv.cmd` (resp .sh)search for WLS_MEM_ARGS, set e.g set `WLS_MEM_ARGS_64BIT=-Xms256m -Xmx2048m`
    
    * restart WebLogic Server

* Create in `${myDomain}` a packages folder and inside a cq folder and in it a Plan folder

**Deploy AEM web application**

* Download AEM war file
* Put the AEM war file into the ${myDomain}/packages/cq folder
* Make your configurations In `WEB-INF/web.xml` if needed (see above in the General Description)

    * Unpack `WEB-INF/web.xml`file
    * change sling.run.modes parameter to publish
    * uncomment sling.home initial parameter and set this path as you need (see General Description)
    * Repack web.xml file

* Deploy AEM war file as an Application, (for the other settings use the default settings)
* The installation can take time...
* Check that the installation has finished as mentioned above in the General Description (e.g. tailing the error.log)
* You can change the context root in the Configuration tab of the web application in the WebLogic `/console`

#### Tomcat 8/8.5
Before a deployment read the [General Description](#GeneralDescription) above.

* **Prepare Tomcat Server**

    * Increase VM memory settings:

        * In `bin/catalina.bat` (resp `catalina.sh` on unix) add the following setting:
        
        * `set "JAVA_OPTS= -Xmx2048m`

    * Tomcat enables neither admin nor manager access at installation. Therefore you have to manually edit `tomcat-users.xml` to allow access for these accounts:

        * Edit `tomcat-users.xml` to include access for admin and manager. The configuration should look similar to the following example:
        * `&lt;?xml version='1.0' encoding='utf-8'?&gt;  
          &lt;tomcat-users&gt;  
          &lt;role rolename="manager"/&gt;  
          &lt;role rolename="tomcat"/&gt;  
          &lt;role rolename="admin"/&gt;  
          &lt;role rolename="role1"/&gt;  
          &lt;role rolename="manager-gui"/&gt;  
          &lt;user username="both" password="tomcat" roles="tomcat,role1"/&gt;  
          &lt;user username="tomcat" password="tomcat" roles="tomcat"/&gt;  
          &lt;user username="admin" password="admin" roles="admin,manager-gui"/&gt;  
          &lt;user username="role1" password="tomcat" roles="role1"/&gt;  
          </tomcat-users>`

    * If you like to deploy AEM with context root "/" then you have to change context root of the existing ROOT webapp:

        * Stop and undeploy ROOT webapp
        * Rename ROOT.war folder in tomcat's webapps folder
        * Start webapp again

    * If you install the AEM web application using the manager-gui then you need to increase the maximal size of an uploaded file, as the default only allows 50MB upload size. For that open the web.xml of the manager web application,   
      ` webapps/manager/WEB-INF/web.xml   
      `and increase the max-file-size and max-request-size to at least 500MB, see the following `multipart-config` example of such a a `web.xml` file:

        * `&lt;multipart-config&gt;  
          &lt;!-- 500MB max --&gt;  
          &lt;max-file-size&gt;524288000&lt;/max-file-size&gt;  
          &lt;max-request-size&gt;524288000&lt;/max-request-size&gt;  
          &lt;file-size-threshold&gt;0&lt;/file-size-threshold&gt;  
          </multipart-config>`

* **Deploy AEM web application**

    * Download AEM war file
    * Make your configurations In web.xml if needed (see above in the General Description)

        * Unpack WEB-INF/web.xml file
        * change sling.run.modes parameter to publish
        * uncomment sling.home initial parameter and set this path as you need
        * Repack web.xml file

    * Rename AEM war file to ROOT.war if you like to deploy it as root webapp, rename it to e.g aemauthor.war if you like to have aemauthor as context root
    * copy it into tomcat's webapps folder
    * wait until AEM is installed

## Troubleshooting
For information on dealing with issues that may come up during installation, see:

* [Troubleshooting](troubleshooting.md)

