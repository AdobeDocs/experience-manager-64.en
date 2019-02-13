---
title: MySQL Configuration for Enablement Features
seo-title: MySQL Configuration for Enablement Features
description: Connecting your MySQL server
seo-description: Connecting your MySQL server
uuid: 9f0f66d5-3411-47c0-9210-55e747d98230
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: a3e4040a-2639-41f8-9882-3e5c2973fa85
index: y
internal: n
snippet: y
---

# MySQL Configuration for Enablement Features{#mysql-configuration-for-enablement-features}

MySQL is a relational database primarily used for SCORM tracking and reporting data for enablement resources. Included are tables for other features such as tracking video pause/resume.

These instructions describe how to connect to the MySQL server, establish the enablement database, and populate the database with initial data.

## Requirements {#requirements}

Before configuring MySQL for Communities' enablement feature, be sure to

* install [MySQL server](http://dev.mysql.com/downloads/mysql/) Community Server version 5.6

    * version 5.7 is not supported for SCORM
    * may be same server as author AEM instance

* on all AEM instances, install the official [JDBC driver for MySQL](../../communities/using/deploy-communities.md#jdbcdriverformysql)
* install [MySQL workbench](http://dev.mysql.com/downloads/tools/workbench/)
* on all AEM instances, install the [SCORM package](../../communities/using/enablement.md#scorm)

## Installing MySQL {#installing-mysql}

MySQL should be downloaded and installed following the instructions for the target OS.

### Lower case table names {#lower-case-table-names}

As SQL is case insensitive, for case sensitive operating systems, it is necessary to include a setting to lower case all table names.

For example, to specify all lower case table names on a Linux OS :

* edit file `/etc/my.cnf`
* in the `[mysqld]` section, add the following line :  
  `lower_case_table_names = 1`

### UTF8 character set {#utf-character-set}

To provide better multilingual support, it is necessary to use the UTF8 character set.

Change MySQL to have UTF8 as its character set :

* mysql&gt; SET NAMES 'utf8';

Change the MySQL database to default to UTF8 :

* edit file `/etc/my.cnf`
* in the `[client]` section, add the following line:  
  `default-character-set=utf8`

* in the `[mysqld]` section, add the following line:  
  `character-set-server=utf8`

## Installing MySQL Workbench {#installing-mysql-workbench}

MySQL Workbench provides an UI for executing SQL scripts which install the schema and initial data.

MySQL Workbench should be downloaded and installed following the instructions for the target OS.

## Enablement Connection {#enablement-connection}

When the MySQL Workbench is first launched, unless already in use for other purposes, it will not yet show any connections :

![](assets/chlimage_1-327.png) 

### New Connection Settings {#new-connection-settings}

1. select the '+' icon to the right of `MySQL Connections`.
1. in the dialog `Setup New Connection`, enter values appropriate for your platform  
   for demonstration purposes, with the author AEM instance and MySQL on the same server :

    * Connection Name: `Enablement`
    * Connection Method: `Standard (TCP/IP)`
    * Hostname: `127.0.0.1`
    * Username: `root`
    * Password: `*no password by default*`
    * Default Schema: `*leave blank*`

1. select `Test Connection` to verify the connection to the running MySQL service

**Notes **:

* the default port is 3306
* the `Connection Name` chosen is entered as the `datasource` name in [JDBC OSGi configuration](#configurejdbcconnections)

#### Successful Connection {#successful-connection}

![](assets/chlimage_1-328.png) 

#### New Enablement Connection {#new-enablement-connection}

![](assets/chlimage_1-329.png) 

## Database Setup {#database-setup}

Upon opening the new Enablement connection, notice there is a test schema and default user accounts.

![](assets/chlimage_1-330.png) 

### Obtain SQL Scripts {#obtain-sql-scripts}

The SQL scripts are obtained using CRXDE Lite on the author instance. The [SCORM package](../../communities/using/deploy-communities.md#scorm) must be installed :

1. browse to CRXDE Lite

    * for example, [http://localhost:4502/crx/de](http://localhost:4502/crx/de)

1. expand the `/libs/social/config/scorm/` folder
1. download&#42; `database_scormengine.sql`
1. download&#42; `database_scorm_integration.sql`

![](assets/chlimage_1-331.png)

&#42; One method for downloading the schema is to

* select the `jcr:content`node for the sql file
* notice the value for the `jcr:data`property is a view link

* select the view link to save the data to a local file

### Create SCORM Database {#create-scorm-database}

The Enablement SCORM Database to be created is :

* name : `ScormEngineDB`
* created from scripts :

    * schema : `database_scormengine.sql`
    * data : `database_scorm_integration.sql`

Follow the steps below ([open](#step1opensqlfile), [execute](#step2executesqlscript)) to install each [SQL script](#obtainsqlscripts) . [Refresh](#refresh) when necessary to see the results of the script execution.

Be sure to install the schema before installing the data.

>[!CAUTION]
>
>If the database name is changed, be sure to specify it correctly in
>
>* [JDBC config](#configurejdbcconnections)
>* [SCORM config](#configurescorm)
>

#### Step 1 : open SQL file {#step-open-sql-file}

In the MySQL Workbench

* from the File pulldown menu
* select `Open SQL Script ...` 
* in this order, select one of :

    1. `database_scormengine.sql`
    1. `database_scorm_integration.sql`

![](assets/chlimage_1-332.png) 

#### Step 2 : execute SQL Script {#step-execute-sql-script}

In the Workbench window for the file opened in Step 1, select the `lightening (flash) icon` to execute the script.

Note that the execution of the `database_scormengine.sql` script to create the SCORM database may take a minute to complete.

![](assets/chlimage_1-333.png) 

#### Refresh {#refresh}

Once the scripts are executed, it is necessary to refresh the `SCHEMAS`section of the `Navigator` in order to see the new database. Use the refresh icon to the right of 'SCHEMAS' :

![](assets/chlimage_1-334.png) 

####  Result : scormenginedb {#result-scormenginedb}

After installing and refreshing SCHEMAS, the **`scormenginedb`**will be visible.

![](assets/chlimage_1-335.png) 

## Configure JDBC Connections {#configure-jdbc-connections}

The OSGi configuration for **Day Commons JDBC Connections Pool** configures the MySQL JDBC Driver.

All publish and author AEM instances should point to the same MySQL server.

When MySQL runs on a server different from AEM, the server hostname must be specified in place of 'localhost' in the JDBC connector (which populates the [ScormEngine](#configurescormengineservice) config).

* on each author and publish AEM instance
* signed in with administrator privileges
* access the [web console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* locate the `Day Commons JDBC Connections Pool`
* select the '+' icon to create a new configuration

![](assets/chlimage_1-336.png)

* enter the following values :

    * **JDBC driver class** : com.mysql.jdbc.Driver
    * **JDBC connection URI** : jdbc:mysql://localhost:3306/aem63reporting  
      specify server in place of localhost if MySQL server is not the same as 'this' AEM server  
    
    * **Username **: root  
      or enter the configured Username for the MySQL server, if not 'root'
    
    * **Password** :   
      clear this field if no password set for MySQL,  
      else enter the configured password for the MySQL Username
    
    * **...**
    * **Datasource name** : name entered for the [MySQL connection](#newconnectionsettings), for example, 'enablement'

* select **Save**

## Configure Scorm {#configure-scorm}

### AEM Communities ScormEngine Service {#aem-communities-scormengine-service}

The OSGi configuration for **AEM Communities ScormEngine Service** configures SCORM for an enablement community's use of the MySQL server.

This configuration is present when the [SCORM package](../../communities/using/deploy-communities.md#scormpackage) is installed.

All publish and author instances point to the same MySQL server.

When MySQL runs on a server different from AEM, the server hostname must be specified in place of 'localhost' in the ScormEngine Serivce, which is typically populated from the [JDBC Connection](#configurejdbcconnections) config.

* on each author and publish AEM instance
* signed in with administrator privileges
* access the [web console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* locate the `AEM Communities ScormEngine Service`
* select the edit icon

![](assets/chlimage_1-337.png)

* verify the following parameter values are consistent with the [JDBC Connection](#configurejdbcconnectionspool) config :

    * **JDBC connection URI** : jdbc:mysql://localhost:3306/ScormEngineDB  
      *ScormEngineDB* is the default database name in the SQL scripts
    
    * **Username **: root  
      or enter the configured Username for the MySQL server, if not 'root'
    
    * **Password** :   
      clear this field if no password set for MySQL,  
      else enter the configured password for the MySQL Username

* regarding the following parameter :

    * **Scorm User Password** : DO NOT EDIT  
      For internal use only. It is for a special service user used by AEM Communities to communicate with the scorm engine.

* select **Save**

### Adobe Granite CSRF Filter {#adobe-granite-csrf-filter}

To ensure enablement courses work correctly in all browsers, it is necessary to add Mozilla as a User Agent that is not checked by the CSRF filter.

* on each publish AEM instance
* signed in with administrator privileges
* access the [web console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* locate `Adobe Granite CSRF Filter`
* select the edit icon

![](assets/chlimage_1-338.png)

* select the `[+]` icon to add a Safe User Agent
* enter `Mozilla/*`
* select **Save**

