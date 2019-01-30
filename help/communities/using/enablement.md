---
title: Configuring Enablement Features
seo-title: Configuring Enablement Features
description: null
seo-description: Configure enablement features in Communities
uuid: 4a4fd8ab-d997-4b67-9675-b760e5188e71
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 4711fbfa-9b99-45ec-a914-827b1ea91bf3
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring Enablement Features{#configuring-enablement-features}

## Overview {#overview}

The enablement features provide the ability to create [enablement communities](../../communities/using/overview.md#enablementcommunity).

* This feature requires additional licensing for use in a production environment.*

Use of the enablement features requires the following:

Installation of :

* **SCORM** 
  Sharable Content Object Reference Model (SCORM) is a collection of standards and specifications for e-learning. SCORM also defines how content may be packaged into a transferable ZIP file.

* **MySQL** 
  MySQL is a relational database primarily used for SCORM tracking and reporting data for Enablement, as well as tables for tracking video progress. The SCORM for enablement feature pack requires the MySQL JDBC driver.

* **FFmpeg** 
  FFmpeg is a solution for converting and streaming audio and video and, when installed, is used for proper transcoding of [Video Assets](../../sites/authoring/using/default-components-foundation.md#video). For enablement communities, it is used in the author environment to obtain metadata for uploaded resources as well as generate a thumbnail to display when listing the resource.

Setup of :

* **Community Managers** 
  For enablement communities, only members of the `Community Enablement Managers` user group may be assigned the role of `*Community Site* Enablement Manager`, whose permissions may include content creation, assignments, and member management in the publish environment.

Optional configuration of :

* **Adobe Analytics** 
  Integration with Adobe Analytics adds comprehensive reporting features and supports the Video Heartbeat addtion to Analytics.

* **Dispatcher**

## Configuration Steps {#configuration-steps}

Following are the steps necessary for enablement communities.

Each step links to documentation which provides the necessary details.

**On all author/publish instances :**

1. ** [install JDBC driver for MySQL](../../communities/using/deploy-communities.md#jdbcdriverformysql)** 
use Web Console (bundles) : *http://localhost:4502/system/console/bundles* 
install *before* installing SCORM package

2. ** [install SCORM package](../../communities/using/deploy-communities.md#scormpackage)** 
use Package Manager : *http://localhost:4502/crx/packmgr/*

**On any server:**

3. ** [install MySQL, MySQL Workbench](../../communities/using/mysql.md)**

4. ** [install MySQL databases](../../communities/using/mysql.md#databasesetup)** 
execute SQL scripts downloaded from author instance  
use MySQL Workbench

**On same server hosting author instance:**

5. ** [install FFmpeg](../../communities/using/ffmpeg.md)**

**On all author/publish instances :**

6. ** [configure JDBC Connections pool](../../communities/using/mysql.md#configurejdbcconnections)** 
use Web Console (configMgr) : *http://localhost:4502/system/console/configMgr*

7. ** [configure SCORM engine service](../../communities/using/mysql.md#aemcommunitiesscormengineservice)** 
use Web Console (configMgr) : *http://localhost:4502/system/console/configMgr*

8. ** [configure CSRF filters](../../communities/using/mysql.md#adobegranitecsrffilter)** 
use Web Console (configMgr) : *http://localhost:4502/system/console/configMgr*

**On author instance :**

9. (*optional*) ** [configure Analytics service](../../communities/using/analytics.md)** 
use Tools, Deployment, Cloud Services console : *http://localhost:4502/etc/cloudservices/sitecatalyst.html*

10. ** [configure FFmpeg](../../communities/using/ffmpeg.md#configureffmpegtranscodingservice)** 
use Workflow/Models console

11. ** [enable Tunnel Service](../../communities/using/deploy-communities.md#tunnelserviceonauthor)** 
use Web Console (configMgr) : *http://localhost:4502/system/console/configMgr*

12. ** [create Community administrators](../../communities/using/users.md#creatingcommunitymembers) **for author environment  
use classic-UI Security console: *http://localhost:4502/useradmin* 
- create user(s) with path = /home/users/community  
- add members(s) to the following groups :  
Community Enablement Managers  
Communities Administrators

## Dispatcher {#dispatcher}

When the deployment includes [AEM's Dispatcher](/content/help/en/experience-manager/dispatcher/using/dispatcher), in order for the enablement features to work properly, the `clientheader`and `filter`sections need modification. See [Configuring Dispatcher for Communities](../../communities/using/dispatcher.md#enablement).
