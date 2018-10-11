---
title: Single Sign On
seo-title: Single Sign On
description: null
seo-description: Learn how to configure Single Sign On (SSO) for an AEM instance.
uuid: 093c32f6-0637-4c91-836a-2ed5611ed806
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/single-sign-on
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 29 09.314-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 46 07.916-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
topic-tags: Security
cq-template: /apps/help/templates/article-3
discoiquuid: a19f8c81-c887-4854-b1bd-cd48f5a9765d
firstPublishExternalDate: 2017-10-31T16:17:35.321-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 03 22.395-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:46:06.011-0400
lochandoffdate: 2018-04-30T03 29 09.313-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/security;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/security
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Single Sign On
publishexternaldate: 2018-04-03T08 46 06.011-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/single-sign-on.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/single-sign-on
sha1: c8ee33afa2288bcd5dd1c7b2f981818a0bc314b0
topicBrowsingSortDate: 2018-04-03T08:46:06.011-0400
index: y
internal: n
snippet: y
translate: y
---

# Single Sign On

Single Sign On (SSO) allows a user to access multiple systems after providing authentication credentials (such as a user name and password) once. A separate system (known as the trusted authenticator) performs the authentication and provides Experience Manager with the user credentials. Experience Manager checks and enforces the access permissions for the user (i.e. determines which resources the user is allowed to access).

The SSO Authentication Handler service ( `com.adobe.granite.auth.sso.impl.SsoAuthenticationHandler`) processes the authentication results that the trusted authenticator provides. The SSO Authentication Handler searches for a ssid (SSO Identifier) as the value of a special attribute in the following locations in this order:

1. Request Headers
1. Cookies
1. Request Parameters

When a value is found, the search is finished and this value is used.

Configure the following two services to recognize the name of the attribute that stores the ssid:

* The login module.
* The SSO Authentication service.

You must specify the same attribute name for both services. The attribute is included in the `SimpleCredentials` that is provided to `Repository.login`. The value of the attribute is irrelevant and ignored, the mere presence of it is important and verified.

## Configuring SSO
To configure SSO for a AEM instance, you need to configure the [SSO Authentication Handler](osgi-configuration-settings.md#AdobeGraniteSSOAuthenticationHandler):

1. When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](configuring-osgi.md) for more details and the recommended practices.

   For example, for NTLM set:

    * **Path:** as required; for example, `/`
    
    * **Header Names**: `LOGON_USER` 
    
    * **ID Format**: `^<DOMAIN>\\(.+)$`  
      Where `<*DOMAIN*>` is replaced by your own domain name.

   For CoSign:

    * **Path:** as required; for example, `/`
    
    * **Header Names**: remote_user  
    
    * **ID Format:** AsIs

   For SiteMinder:

    * **Path:** as required; for example, `/`
    
    * **Header Names: **SM_USER
    * **ID Format**: AsIs

1. Confirm that Single Sign On is working as required; including authorization.

>[!CAUTION]
>
>Make sure that users cannot access AEM directly if SSO is configured.
>
>By requiring users to go through a web server that runs your SSO system's agent, it is ensured that no user can directly send a header, cookie or parameter that will lead the user to be trusted by AEM, as the agent will filter such information if sent from the outside.
>
>Any user who can directly access your AEM instance without going through the web server will be able to act as any user by sending the header, cookie or parameter if the names are known.
>
>Also make sure that of headers, cookies and request parameter names, you only configure the one that is required for your SSO setup.
>

>[!NOTE]
>
>Single Sign On is often used in conjunction with [LDAP](/content/help/en/experience-manager/6-4/sites/administering/using/ldap-config).

>[!NOTE]
>
>If you are also using the [Dispatcher](/content/help/en/experience-manager/dispatcher/using/dispatcher) with the Microsoft Internet Information Server (IIS) then additional configuration will be required in:
>
>* `disp_iis.ini`
>* IIS
>
>In `disp_iis.ini` set:  
>(see [installing the Dispatcher with the Microsoft Internet Information Server](/content/help/en/experience-manager/dispatcher/using/dispatcher-install#MicrosoftInternetInformationServer) for full details)  

>
>* `servervariables=1` (forwards IIS server variables as request headers to the remote instance)
>* `replaceauthorization=1` (replaces any header named "Authorization" other than "Basic" with its "Basic" equivalent)
>
>In IIS:
>
>* disable **Anonymous access** 
>
>* enable **Integrated Windows authentification**
>

You can see which authentication handler is being applied to any section of the content tree by using the **Authenticator** option of the Felix Console; for example:

`http://localhost:4502/system/console/slingauth`

The handler that best matches the path is queried first. For example, if you configure handler-A for the path `/` and handler-B for the path `/content`, then a request to `/content/mypage.html` will query handler-B first.

![](assets/screen_shot_2012-02-15at21006pm.png) 

#### Example
For a cookie request (using the URL `http://localhost:4502/libs/wcm/content/siteadmin.html`):

```xml
GET /libs/cq/core/content/welcome.html HTTP/1.1
Host: localhost:4502
Cookie: TestCookie=admin
```

Using the following configuration:

* **Path**: `/`

* **Header Names**: `TestHeader`

* **Cookie Names**: `TestCookie`

* **Paramater Names**: `TestParameter`

* **ID Format**: `AsIs`

The response would be:

```xml
HTTP/1.1 200 OK
Connection: Keep-Alive
Server: Day-Servlet-Engine/4.1.24 
Content-Type: text/html;charset=utf-8
Date: Thu, 23 Aug 2012 09:58:39 GMT
Transfer-Encoding: chunked

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <title>Welcome to Adobe&reg; CQ5</title>
....
```

This also works if you request:  
`http://localhost:4502/libs/cq/core/content/welcome.html?TestParameter=admin`

Or you can use the following curl command to send the `TestHeader` header to `admin:`  
`curl -D - -H "TestHeader: admin" http://localhost:4502/libs/cq/core/content/welcome.html`

>[!NOTE]
>
>When using the request parameter in a browser you will only see some of the HTML - without CSS. This is because all the requests from the HTML are made without the request parameter.

## Removing AEM Sign Out Links
When using SSO, sign in and sign out are handled externally, so that AEMs own sign-out links are no longer applicable and should be removed.

The sign out link on the welcome screen can be removed using the following steps.

1. Overlay `/libs/cq/core/components/welcome/welcome.jsp` to `/apps/cq/core/components/welcome/welcome.jsp`

1. remove the following part from the jsp.

   `<a href="#" onclick="signout('<%= request.getContextPath() %>');" class="signout"><%= i18n.get("sign out", "welcome screen") %>`

To remove the sign out link that is available in the user's personal menu in the top-right corner, follow these steps:

1. Overlay `/libs/cq/ui/widgets/source/widgets/UserInfo.js` to `/apps/cq/ui/widgets/source/widgets/UserInfo.js`

1. Remove the following part from the file:

   ```
   menu.addMenuItem({
       "text":CQ.I18n.getMessage("Sign out"),
       "cls": "cq-userinfo-logout",
       "handler": this.logout
   });
   menu.addSeparator();
   ```

