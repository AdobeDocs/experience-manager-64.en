---
title: Create and Assign Enablement Resources
seo-title: Create and Assign Enablement Resources
description: Add enablement resources
seo-description: Add enablement resources
uuid: da940242-0c9b-4ad8-8880-61fd41461c3b
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 8fe97181-600e-42ac-af25-d5d4db248740
---

# Create and Assign Enablement Resources{#create-and-assign-enablement-resources}

## Add an Enablement Resource {#add-an-enablement-resource}

To add an enablement resource to the new community site:

* on the author instance

    * for example, [http://localhost:4502/](http://localhost:4503/)

* sign in as a system administrator
* from global navigation, select **Communities, [Resources](/help/communities/resources.md)**

![](assets/chlimage_1-199.png) ![](assets/chlimage_1-200.png)

* select the community site to which enablement resources are being added

    * select `Enablement Tutorial`

* from the menu, select **+ Create**
* select **Resource**

![](assets/chlimage_1-201.png) 

### Basic Info {#basic-info}

Fill in the basic information for the Resource:

* **Site Name**:  
  set to the name of the selected community site: Enablement Tutorial

* **Resource Name&#42;**: Ski Lesson 1
* **Tags**: Tutorial: Sports / Skiing
* **Show in Catalog**: On
* **Description**: Sliding on snow for beginners
* **Add Image**:  
  add an image to represent the Resource to the member in their Assignments view

![](assets/chlimage_1-202.png)

* select **Next**

### Add Content {#add-content}

While it appears as if multiple Resources might be selected, only one is allowed.

Select the `'+' icon`, in the upper right corner, to begin the process of choosing the Resource by identifying the source.

![](assets/chlimage_1-203.png) ![](assets/chlimage_1-204.png)

Upload a Resource. If a video resource, either upload a custom image to display before the video starts playing, or allow a thumbnail to be generated from the video (may take a few minutes - it's not necessary to wait).

![](assets/chlimage_1-205.png)

* select **Next**

### Settings {#settings}

* **Social Settings** 
  Leave default settings to experience commenting and rating of enablement resources by learners.

* **Due Date** 
  *(Optional)* A date by which the assignment should be completed may be selected.

* **Resource Author** 
  *(Optional)* Leave blank.

* **Resource Contact&#42;** 
  *(Required)* Use the pulldown menu to select member `Quinn Harper`.

* **Resource Expert** 
  *(Optional)* Leave blank.

**Note**: if users or groups are not visible, check that they were added to the `Community Enable Members` group and *Saved* on the publish instance.

![](assets/chlimage_1-206.png)

* select **Next**

### Assignments {#assignments}

* **Add Assignees** 
  Leave unset as this enablement resource will be added to a learning path. If a learner is assigned to the individual enablement resource as well as a learningpPath containing the enablement resource, the learner will be assigned to the enablement resource twice.

![](assets/chlimage_1-207.png)

* select **Create**

![](assets/chlimage_1-208.png)

Successful creation of the Resource returns to the Resources console with the newly created Resource selected. From this console, it is possible to publish, add learners and change other settings.

To upload a new version of the enablement resource, it is recommended to create a new Resource, and then unenroll members from the old version and enroll them in the new version.

### Publish the Resource {#publish-the-resource}

Before Enrollees are able to see the assigned Resourse, it must be published:

* select the world `Publish`icon

Activation is confirmed with a success message:

![](assets/chlimage_1-209.png) 

## Add a Second Enablement Resource {#add-a-second-enablement-resource}

Repeat the steps above to create and publish a second related enablement resource from which a learning path will be created.

![](assets/chlimage_1-210.png)

**Publish **the second Resource.

Return to the Enablement Tutorial listing of it's Resources.

*Hint: if both Resources are not visible, refresh the page.*

![](assets/chlimage_1-211.png) 

## Add a Learning Path {#add-a-learning-path}

A learning path is a logical grouping of enablement resources which form a course.

* from the Resources console, select **+ Create**
* select **Learning Path**

![](assets/chlimage_1-212.png)

Add the **Basic Info**:

* **Learning Path Name **: Ski Lessons
* **Tags**: Tutorial: Skiing
* **Show in Catalog**: leave unchecked
* **upload an image **to represent the learning path in the Resources console

![](assets/chlimage_1-213.png)

* select **Next**

Skip the next panel as there are no prerequisite learning paths to add.

* select **Next**

On the Add Resources panel

* select **+ Add Resources** to select the 2 ski lessions resources to add to the learning path  
  Note: only **published **Resources will be selectable.

>[!NOTE]
>
>You can only select the resources available at the same level as the learning path. For example, for a learning path created in a group only the group level resources are available; for a learning path created in a community site the resources in that site are available for adding to the learning path.

* select **Submit.**

![](assets/chlimage_1-214.png) ![](assets/chlimage_1-215.png)

* select **Next**

![](assets/chlimage_1-216.png)

* **Add Assignees** 
  Use the pulldown menu to select the `Community Ski Class` group, which should included members `Riley Taylor` and `Sidney Croft.`

* **Learning Path Contact&#42;** 
  *(Required)* Use the pulldown menu to select member `Quinn Harper`.

* select **Create**

![](assets/chlimage_1-217.png)

Successful creation of the learning path returns to the Resources console with the newly created learning path selected. From this console, it is possible to publish, add learners and change other settings.

**Publish** the learning path.

