---
title: Reports Console
seo-title: Reports Console
description: Learn how to access reports
seo-description: Learn how to access reports
uuid: 580f5eb8-24b2-4404-90d4-81f7108d1ee6
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0042893e-3d2c-469e-8759-404be16e7436
---

# Reports Console{#reports-console}

## Overview {#overview}

For AEM Communities, there are various reports that may be accessed in several ways from the author environment.

In general, the various reports are:

* [Assignments Report](#assignments-report) - for an [enablement community](../../communities/using/overview.md#enablement-community), provides an overview of learners' progress on their assignments, including an associated score if implementing the SCORM standard
* [Views Report](#views-report) - provides a chart of views of content by community members and site visitors for any community site
* [Posts Report](#posts-report) - provides a chart of various types of posts by community members to any community site

When [Adobe Analytics is enabled](../../communities/using/sites-console.md#analytics), reports will include the number of views, plays, comments and ratings for each enablement resource over time

Tabular reports can be exported in .csv format for subsequent processing.

## Reporting Consoles {#reporting-consoles}

### Reports for Community Sites {#reports-for-community-sites}

* from global navigation: **Navigation**, **Communities, Reports**

* choose from

    * **Assignments Report**

        * generate a report for selected Community Site, User or Group, and Assignment

    * **Posts Report**

        * generate a report for selected Community Site, Content Type, and Time Period

    * **Views Report**

        * generate a report for selected Community Site, Content Type, and Time Period

![](assets/chlimage_1-156.png)

### Reports for Enablement Resources and Learning Paths {#reports-for-enablement-resources-and-learning-paths}

* from global navigation: **Navigation**, **Communities, Resources**

* select an existing enablement community site

    * select **Report **icon to generate reports which cover all enablement resources
    * select an enablement learning path
    * select **Report **icon to generate reports for

        * the included enablement resources
        * the learners assigned to the learning path

* these reports provide:

    * table data, downloadable as CSV

        * identifying learner
        * their status
        * whether assigned or accessed through catalog
        * number of comments made
        * star rating given

For more details, see [Reports section](../../communities/using/resources.md#report) of the Resources console.

## Assignments Report {#assignments-report}

The Assignments console allows reports to be filtered by enablement community site, users or groups, and assignment.

The report provides information on their progress as well as any comments or ratings provided.

![](assets/chlimage_1-157.png)

Select the criteria for the report:

* **Site** 
  select an enablement community site

* **User or Group** 
  * select User to generate a report for one learner  
  * select Group to generate a report for a group of learners  
  The tunnel service will access members and member groups from the publish environment

* **Assignment** 
  Choose from among the enablement resources assigned to the selected learner(s)

Select **Generate** to create the report:

![](assets/chlimage_1-158.png)

## Views Report {#views-report}

The Views console allows reports to be generated on page views by community feature(s) for a given time period.

![](assets/chlimage_1-159.png)

Select the criteria for the report:

* **Site** 
  select a community site

* **Content Type** 
  may choose All content or select one of the features present on the site

* time frame  
  select one of

    * Last 7 days
    * Last 30 days
    * Last 90 days
    * Last year

Select **Generate** to create the report:

![](assets/chlimage_1-160.png)

## Posts Report {#posts-report}

The Posts console allows reports to be generate on number of posts to community feature(s) for a given time period.

![](assets/chlimage_1-161.png)

Select the criteria for the report:

* **Site** 
  select a community site

* **Content Type** 
  may choose All content or select one of the features present on the site

* time frame  
  select one of

    * Last 7 days
    * Last 30 days
    * Last 90 days
    * Last year

Select **Generate** to create the report:

![](assets/chlimage_1-162.png)

## Troubleshooting {#troubleshooting}

### No community sites listed {#no-community-sites-listed}

If no community sites are listed, ensure Adobe Analytics has been enabled for a site. If choosing reports on assignments, ensure the assignments function is in the community site's structure.