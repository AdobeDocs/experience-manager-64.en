---
title: MySQL Configuration for DSRP
seo-title: MySQL Configuration for DSRP
description: How to connect to the MySQL server and establish the UGC database
seo-description: How to connect to the MySQL server and establish the UGC database
uuid: 6c6736b3-9c9f-42fe-9c77-d6819dd6087b
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 352fd2a5-9313-45d1-ac30-526970da429d
---

# MySQL Configuration for DSRP{#mysql-configuration-for-dsrp}

MySQL is a relational database that can be used to store user generated content (UGC).

These instructions describe how to connect to the MySQL server and establish the UGC database.

## Requirements {#requirements}

* [latest Communities feature pack](../../communities/using/deploy-communities.md#latestfeaturepack)
* [JDBC driver for MySQL](../../communities/using/deploy-communities.md#jdbcdriverformysql)
* a relational database :

    * [MySQL server](http://dev.mysql.com/downloads/mysql/) Community Server version 5.6 or later

        * may run on same host as AEM or run remotely

    * [MySQL workbench](http://dev.mysql.com/downloads/tools/workbench/)

## Installing MySQL {#installing-mysql}

[MySQL](http://dev.mysql.com/downloads/mysql/) should be downloaded and installed following the instructions for the target OS.

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

## Communities Connection {#communities-connection}

When the MySQL Workbench is first launched, unless already in use for other purposes, it will not yet show any connections :

![](assets/chlimage_1-104.png) 

### New Connection Settings {#new-connection-settings}

1. select the '+' icon to the right of `MySQL Connections`.
1. in the dialog `Setup New Connection`, enter values appropriate for your platform  
   for demonstration purposes, with the author AEM instance and MySQL on the same server :

    * Connection Name: `Communities`
    * Connection Method: `Standard (TCP/IP)`
    * Hostname: `127.0.0.1`
    * Username: `root`
    * Password: `*no password by default*`
    * Default Schema: `*leave blank*`

1. select `Test Connection` to verify the connection to the running MySQL service

**Notes **:

* the default port is 3306
* the Connection Name chosen is entered as the datasource name in [JDBC OSGi configuration](#configurejdbcconnections)

#### New Communities Connection {#new-communities-connection}

![](assets/chlimage_1-105.png) 

## Database Setup {#database-setup}

Open the Communities connection in order to install the database.

![](assets/chlimage_1-106.png) 

### Obtain the SQL Script {#obtain-the-sql-script}

The SQL script is obtained from the AEM repository :

1. browse to CRXDE Lite

    * for example, [http://localhost:4502/crx/de](http://localhost:4502/crx/de)

1. select the /libs/social/config/datastore/dsrp/schema folder
1. download&#42; `init-schema.sql`

![](assets/chlimage_1-107.png)

&#42; One method for downloading the schema is to

* select the `jcr:content`node for the sql file
* notice the value for the `jcr:data`property is a view link

* select the view link to save the data to a local file

### Create the DSRP Database {#create-the-dsrp-database}

Follow the steps below to install the database. The default name of the database is `communities`.

If the database name is changed in the script, be sure to also change it in the [JDBC config](#configurejdbcconnections).

#### Step 1 : open SQL file {#step-open-sql-file}

In the MySQL Workbench

* from the File pulldown menu
* select the downloaded `init_schema.sql`

![](assets/chlimage_1-108.png) 

#### Step 2 : execute SQL Script {#step-execute-sql-script}

In the Workbench window for the file opened in Step 1, select the `lightening (flash) icon` to execute the script.

In the following image, the `init_schema.sql` file is ready to be executed :

![](assets/chlimage_1-109.png) 

#### Refresh {#refresh}

Once the script is executed, it is necessary to refresh the `SCHEMAS`section of the `Navigator` in order to see the new database. Use the refresh icon to the right of 'SCHEMAS' :

![](assets/chlimage_1-110.png) 

## Configure JDBC Connection {#configure-jdbc-connection}

The OSGi configuration for **Day Commons JDBC Connections Pool** configures the MySQL JDBC Driver.

All publish and author AEM instances should point to the same MySQL server.

When MySQL runs on a server different from AEM, the server hostname must be specified in place of 'localhost' in the JDBC connector.

* on each author and publish AEM instance
* signed in with administrator privileges
* access the [web console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* locate the `Day Commons JDBC Connections Pool`
* select the '+' icon to create a new connection configuration

![](assets/chlimage_1-111.png)

* enter the following values :

    * **JDBC driver class** : com.mysql.jdbc.Driver
    * **JDBC connection URI** : jdbc:mysql://localhost:3306/communities?characterEncoding=UTF-8  
      specify server in place of localhost if MySQL server is not the same as 'this' AEM server  
      *communities* is the default database (schema) name
    
    * **Username **: root  
      or enter the configured Username for the MySQL server, if not 'root'
    
    * **Password** :   
      clear this field if no password set for MySQL,  
      else enter the configured password for the MySQL Username
    
    * **...**
    * **Datasource name** : name entered for the [MySQL connection](#newconnectionsettings), for example, 'communities'

* select **Save**

