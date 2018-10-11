---
title: Run Modes
seo-title: Run Modes
description: null
seo-description: Learn how to tune your AEM instance for specific purposes by using run modes.
uuid: d2a4362f-1590-4527-a5e9-e8a0abf820b9
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/configure-runmodes
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 29 07.970-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 40 26.884-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: b403524c-0af7-46c6-a214-916f63d9c07f
firstPublishExternalDate: 2017-10-31T16:18:13.334-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 21.369-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:40:25.509-0400
lochandoffdate: 2018-04-30T03 29 07.969-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Run Modes
publishexternaldate: 2018-04-03T08 40 25.509-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configure-runmodes.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/configure-runmodes
sha1: e7c285243fd188957a1b3d80928cb814e8a5ba59
topicBrowsingSortDate: 2018-04-03T08:40:25.509-0400
index: y
internal: n
snippet: y
---

# Run Modes

Run modes allow you to tune your AEM instance for a specific purpose; for example author or publish, test, development, intranet or others.

You can:

* [Define collections of configuration parameters for each run mode](#Definingconfigurationpropertiesforarunmode).  
  A basic set of configuration parameters is applied for all run modes, you can then tune additional sets to the purpose of your specific environment. These are applied as required.

* [Define additional bundles to be installed for a particular mode](#Definingadditionalbundlestobeinstalledforarunmode).

All settings and definitions are stored in the one repository and activated by setting the **Run Mode**.

### Installation Run Modes
Installation (or fixed) run modes are used at installation time and then fixed for the entire lifetime of the instance, they cannot be changed.

Installation run modes are provided out-of-the-box:

* `author`
* `publish`

* `samplecontent`
* `nosamplecontent`

These are two pairs of mutually exclusive run modes; for example, you can:

* define either `author` or `publish`, not both at the same time  

* combine `author` with either `samplecontent` or `nosamplecontent` (but not both)

>[!CAUTION]
>
>When using one of the above run modes (author, publish, samplecontent, nosamplecontent), the value used at installation time defines the run mode for the *entire lifetime* of that installation. 
>
>For these run modes you *cannot* change them after installation.

### Customized Run Modes
You can also create your own, customized, run modes. These can be combined to cover scenarios such as:

* `author` + `development`

* `publish` + `test`

* `publish + test + golive  
  `
* `publish` + `intranet`

* as required . . .

Customized run modes can also be selected at each startup.

## Using samplecontent and nosamplecontent

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:41:40.773-0500

<p><a href="https://issues.adobe.com/browse/DOC-3078">https://issues.adobe.com/browse/DOC-3078</a></p> 
<p>apparently doesn't do much for 5.6, but looks hopeful for 5.6.1</p> 
<p><a href="https://issues.adobe.com/browse/CQ5-31383">https://issues.adobe.com/browse/CQ5-31383</a></p>

 -->

These modes allow you to control the use of sample content. The sample content is defined before the quickstart is built and can include packages, configurations, etc:

* The `samplecontent` run mode will install this content (the default mode).  

* The `nosamplecontent` mode will not install the sample content.

The nosamplecontent run mode is designed for production installations.

## Defining configuration properties for a run mode
A collection of values for configuration properties, used for a particular run mode, can be saved in the repository.

The run mode is indicated by a suffix on the folder name. This allows you to store all configurations in one repository as. For example:

* `config`  
  Applicable for all run modes  

* `config.author`  
  Used for author run mode  

* `config.publish`  
  Used for publish run mode  

* `config.<*run-mode*>`  
  Used for the applicable run mode; for example, config

See [OSGi Configuration in the Repository](/configuring-osgi.html?cq_ck=1368002864971#OSGiConfigurationintheRepository) for further details on defining the individual configuration nodes within these folders and for creating configurations for combinations of multiple run modes.

>[!NOTE]
>
>For [Installation Run Modes](#InstallationRunModes) (e.g. author) the run mode cannot be changed after installation. However, changes to the individual configuration properties will take effect upon restart.

## Defining additional bundles to be installed for a run mode
Additional bundles that should be installed for a particular run mode can also be specified. For these definititions, install folders are used to hold the bundles. Again the run mode is indicated by a prefix:

* `install.author`
* `install.publish`

These folders are of type `nt:folder` and should contain the appropriate bundle.

## Starting CQ with a specific run mode
If you have defined configurations for multiple run modes then you need to define which is to be used upon startup. There are several methods for specifying which run mode to use; the order of resolution is:

1. [ `sling.properties` file](#Usingtheslingpropertiesfile)
1. [ `-r` option](#Usingtheroption)
1. [system properties ( `-D`)](#Usingasystemproperty)  

1. [Filename detection](#Filenamedetectionrenamingthejarfile)

When you are using an application server you can also [define the run mode in `web.xml`](#DefiningtherunmodeinwebxmlwithApplicationServer).

### Using the sling.properties file
The `sling.properties` file can be used to define the required run mode:

1. Edit the configuration file:  
   `<*cq-installation-dir*>/crx-quickstart/conf/sling.properties`

1. Add the following properties; the following example is for author:  
   `sling.run.modes=author`

### Using the -r option
A custom run mode can be activated by using the `-r` option when launching the quickstart. For example, use the following command to launch a AEM instance with run mode set to dev. ``

```shell
java -jar cq-56-p4545.jar -r dev
```

### Using a system property in the start script
A system property in the start script can be used to specify the run mode.

* For example use the following to launch an instance as a production publish instance located in the US:  
  `-Dsling.run.modes=publish,prod,us`

### Filename detection - renaming the jar file
The following two installation run modes can be activated by renaming the installation jar file before installation:

* publish
* author

The jar file must use the naming convention:

`cq5-<*run-mode*>-p<*port-number*>`

For example, set the `publish` run mode by naming the jar file:

`cq5-publish-p4503`

### Defining the run mode in web.xml (with Application Server)
When you are using an application server you can also configure the property:

`sling.run.modes`

in the file:

`WEB-INF/web.xml`

This is in the AEM `war` file and should be updated before deployment.

See [Installing AEM with an Application Server](application-server-install.md) for further details.
