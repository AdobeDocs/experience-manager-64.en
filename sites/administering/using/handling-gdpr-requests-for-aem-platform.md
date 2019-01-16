---
title: Handling GDPR Requests for the AEM Foundation
seo-title: Handling GDPR Requests for the AEM Foundation
description: null
seo-description: null
uuid: 8881313e-1184-4cd3-850e-e0442e714a25
contentOwner: sarchiz
discoiquuid: bc7d735f-900c-4ef7-8b8c-4eb84d9ac964
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Handling GDPR Requests for the AEM Foundation{#handling-gdpr-requests-for-the-aem-foundation}

## AEM Foundation GDPR support {#aem-foundation-gdpr-support}

At the AEM Foundation level, the Personal Data that is stored  is  the User Profile. Therefore, the information in this article primarily addresses how to access and delete user profiles, to address the GDPR Access and Delete requests respectively.

<!-- 

Comment Type: annotation
Last Modified By: wmitchel
Last Modified Date: 2018-05-14T10:37:37.136-0400

change "Personally Identifiable Information (PII in short) data" to "Personal Data".

 -->

## Accessing a User Profile {#accessing-a-user-profile}

### Manual Steps {#manual-steps}

1. Open the User Administration console, by browsing to **Settings - Security - Users **or by browsing directly to *http://serveraddress:serverport/libs/granite/security/content/useradmin.html*

   ![](assets/useradmin2.png)

1. Then, search for the user in question by typing the name in the search bar at the top of the page:

   ![](assets/usersearch.png)

1. Finally, open the user profile by clicking it, then check under the **Details** tab.

   ![](assets/userprofile_small.png)

### HTTP API {#http-api}

As mentioned, Adobe provides APIs for accessing user data, in order to facilitate automation. There are several types of APIs which you can use:

**UserProperties API**

```shell
curl -u user:password http://localhost:4502/libs/granite/security/search/profile.userproperties.json\?authId\=cavery
```

**Sling API**

*Discovering the user home:*

```xml
curl -g -u user:password 'http://localhost:4502/libs/granite/security/search/authorizables.json?query={"condition":[{"named":"cavery"}]}'
     {"authorizables":[{"type":"user","authorizableId_xss":"cavery","authorizableId":"cavery","name_xss":"Carlene Avery","name":"Carlene Avery","home":"/home/users/we-retail/DSCP-athB1NYLBXvdTuN"}],"total":1}
```

*Retrieving user data*

Using the node path from the home property of the JSON payload returned from the above command:

```shell
curl -u user:password  'http://localhost:4502/home/users/we-retail/DSCP-athB1NYLBXvdTuN/profile.-1.json'
```

```shell
curl -u user:password  'http://localhost:4502/home/users/we-retail/DSCP-athB1NYLBXvdTuN/profiles.-1.json'
```

<!-- 

Comment Type: remark
Last Modified By: Arun Taneja (taneja)
Last Modified Date: 2018-03-16T03:56:55.484-0400

<p>Should probably clarify in these sections, what user:password refers to...I will try to get some info on this.</p>

 -->

## Disabling a User and Deleting the Associated Profiles {#disabling-a-user-and-deleting-the-associated-profiles}

### Disable User {#disable-user}

1. Open the User Administration console and search for the user in question, as described above.
1. Hover over the user and click the select icon. The profile will turn grey indicating that it is selected.  

1. Press the Disable button in the upper menu to disable the user:

   ![](assets/userdisable.png)

1. Fianlly, confirm the action:

   ![](assets/image2018-2-6_1-40-58.png)

   The user interface will then indicate that the user has been deactivated by greying out and adding a lock to the profile card:

   ![](assets/disableduser.png)

### Delete User Profile Information {#delete-user-profile-information}

1. Log in to CRXDE Lite, then search for the `userId`: 

   ![](assets/image2018-2-6_1-57-11.png)

1. Open the user node which is located under `/home/users` by default:

   ![](assets/image2018-2-6_1-58-25.png)

1. Delete profile nodes and all their children. There are two formats to the profile nodes, depeding on the AEM version:

    1. The default private profile under `/profile`  
    
    1. `/profiles`, for new profiles created using AEM 6.4.

   ![](assets/image2018-2-6_2-0-4.png)

### HTTP API {#http-api-1}

The following procedures use the `curl` command line tool to illustrate how to disable the user with the **cavery** `userId` and delete her profiles available at the default location.

* *Discovering the user home*

```shell
curl -g -u user:password 'http://localhost:4502/libs/granite/security/search/authorizables.json?query={"condition":[{"named":"cavery"}]}'
     {"authorizables":[{"type":"user","authorizableId_xss":"cavery","authorizableId":"cavery","name_xss":"Carlene Avery","name":"Carlene Avery","home":"/home/users/we-retail/DSCP-athB1NYLBXvdTuN"}],"total":1}
```

* *Disabling the user*

Using the node path from the home property of the JSON payload returned from the above command:

```shell
curl -X POST -u user:password -FdisableUser="describe the reasons for disabling this user (GDPR in this case)" 'http://localhost:4502/home/users/we-retail/DSCP-athB1NYLBXvdTuN.rw.userprops.html'
```

* *Deleting user profile(s)*

Using the node path from the home property of the JSON payload returned from the account discovery command and the known out of the box profile node locations:

```shell
curl -X POST -u user:password -H "Accept: application/json,**/**;q=0.9" -d ':operation=delete' 'http://localhost:4502/home/users/we-retail/DSCP-athB1NYLBXvdTuN/profile'
```

```shell
curl -X POST -u user:password -H "Accept: application/json,**/**;q=0.9" -d ':operation=delete' 'http://localhost:4502/home/users/we-retail/DSCP-athB1NYLBXvdTuN/profile'
```

