---
title: Configure the LDAP bind password
seo-title: Configure the LDAP bind password
description: null
seo-description: Learn how to configure the bind password field before you import the configuration file into another system. 
uuid: 34e4c5bc-2762-41aa-9f48-2081962f4115
acrolinxdate: 2016-05-31T06 53 31.873-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/configure_ldap_bind_password_admin_5e12de0b318c6865_2272_report.xml
acrolinxsentences: 12
acrolinxwords: 180
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_user_management
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 85b96e69-e4a9-40ce-8016-f96f865b7e53
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configure the LDAP bind password{#configure-the-ldap-bind-password}

To avoid security risks, the bind password field in the exported configuration file (config.xml) is not configured. Before you import the configuration file into another system, ensure that you configure this password. This password overrides an existing password that is stored in the database. A null password does not override an existing non-null password value.

1. In administration console, click Settings &gt; User Management &gt; Configuration &gt; Import And Export Configuration Files.
1. To export the current configuration setting to a file, click Export and save the configuration file in another location.
1. In the file, locate the `Domains` > *[Your domain name]* > `DirectoryConfigs` > `LDAPGroupConfig` node. Here is an example:

   ```as3
    <node name="LDAPGroupConfig"> 
        <map> 
            <entry key="bindanonymously" value="false" />  
            <entry key="basedn" value="dc=corp,dc=adobe,dc=com" />  
            <entry key="batchSize" value="200" />  
            <entry key="binduser" value="cn=Directory Manager" />  
            <entry key="bindpassword" value="" /> 
        </map>
   ```

   Type a value for `bindpassword` and save your changes.

1. In the file, locate the `Domains` > *[Your domain name]* > `DirectoryConfigs` > `LDAPGroupConfig` > `LDAPUserConfig` node. Here is an example:

   ```as3
    <node name="LDAPUserConfig"> 
        <map> 
            <entry key="bindanonymously" value="false" />  
            <entry key="batchSize" value="200" />  
            <entry key="basedn" value="dc=corp,dc=adobe,dc=com" />  
            <entry key="bindpassword" value="" /> 
            <entry key="binduser" value="cn=Directory Manager" />  
        </map>
   ```

   Type a value for `bindpassword` and save your changes.

1. To import the updated file, in User Management, click Configuration &gt; Import And Export Configuration Files.
1. Click Browse to find the file, click Import, and then click OK.

