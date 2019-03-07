---
title: Messaging Feature
seo-title: Messaging Feature
description: Configuring Messaging components
seo-description: Configuring Messaging components
uuid: 51afead7-43e7-4b5a-a6cc-56fbcdddd1ee
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ca813169-01c1-4e86-ab91-4221fbdd06b3
index: y
internal: n
snippet: y
---

# Messaging Feature{#messaging-feature}

In addtion to the publicly visible interactions which occur in forums and comments, the messaging feature of** **AEM Communities enables community members to interact with one another more privately.

This feature may be included when a [community site](../../communities/using/overview.md#communitiessites) is created.

The messaging features provides the ability to :

* send a message to one or more community members
* send a message to a community member group
* send a message with attachments
* forward a message
* reply to a message
* delete a message
* restore a deleted message

In order to enable and modify the messaging feature, visit

* [Configuring Messaging](../../communities/using/messaging.md) for administrators
* [Messaging Essentials](../../communities/using/essentials-messaging.md) for developers

>[!NOTE]
>
>It is not supported to add `Compose Message, Message, or Message List` components (found in `Communities`component group) to a page in author edit mode.

## Configuring Messaging Components {#configuring-messaging-components}

When messaging is enabled for a community site, it is completely setup with no further configuration necessary. This information is provided if there is a need to change the default configuration.

### Configuring Message List (messagebox) {#configuring-message-list-messagebox}

In order to modify the configuration of the list of messages for **Inbox**, **Sent Items**, and **Trash **pages of the messaging feature, open the site in [author edit mode](../../communities/using/sites-console.md#authoringsitecontent).

In `Preview`mode, select the **Messages **link to open the main messaging page. Then select either **Inbox**, **Sent Items **or **Trash **in order to configure the component for that message list.

In `Edit` mode, select the component on the page.

In order to access the configuraiton dialog, it is necessary to cancel inheritance by selecting the `link`icon.

Once the configuration is complete, it is necessary to restore inheritance by selecting the `broken link` icon.

![](assets/chlimage_1-396.png)

Once inheritance is canceled, it will be possible to select the `configure` icon to open the configuration dialog.

![](assets/chlimage_1-397.png)

#### Basic tab {#basic-tab}

![](assets/chlimage_1-398.png)

* **Service selector** 
  (*Required*) Set this to the value of the property**`serviceSelector.name`** from the [AEM Communities Messaging Operations Service](../../communities/using/messaging.md#messagingoperationsservice).

* **Compose Page** 
  (*Required*) The page to open when a member clicks on the **`Reply`**button. The target page should contain the **Compose Message** form.

* **Reply/View as Resource** 
  If checked, the Reply URL and View URL will reference a resource, else data is passed as query parameters in the URL .

* **Profile Display Form** 
  The profile form to use to display the senders profile.

* **Trash Folder** 
  If checked, this Message List component displays only messages flagged as deleted (trash).

* **Folder Paths** 
  (*Required*) Referencing the values set for **inbox.path.name** and **sentitems.path.name **in the [AEM Communities Messaging Operations Service](../../communities/using/messaging.md#messagingoperationsservice). When configuring for an `Inbox`, add one entry using the value of **inbox.path.name**. When configuring for an `Outbox`, add one entry using the value of **sentitems.path.name**. When configuring for `Trash`, add two entries with both values.

#### Display tab {#display-tab}

![](assets/chlimage_1-399.png)

* **Mark Read Button** 
  If checked, displays a `Read`button allowing a message to be marked as read.

* **Mark Unread Button** 
  If checked, displays a `Mark Unread` button allowing a message to be marked as read.

* **Delete Button** 
  If checked, displays a `Delete`button allowing a message to be marked as read. Will duplicate the delete functionality if **`Message Options`** is also checked.

* **Message Options** 
  If checked, displays **`Reply`**, **`Reply All`**, **`Forward`**and **`Delete`**buttons allowing a message to be resent or deleted. Will duplicate the delete functionality if **`Delete Button`** is also checked.

* **Messages Per Page** 
  The number specified is the maximum number of messages displayed per page in a pagination scheme. If no number is specified (left blank), then all messages are displayed and there is no pagination.

* **Timestamp patterns** 
  Provide timestamp patterns for one or more languages. Default is for en, de, fr, it, es, ja, zh_CN, ko_KR.

* **Display User** 
  Choose either **`Sender`**or **`Recipients`**to determine whether to display the Sender or Recipients.

### Configuring Compose Message {#configuring-compose-message}

In order to modify the configuration of the compose message page, open the site in [author edit mode](../../communities/using/sites-console.md#authoringsitecontent).

In `Preview`mode, select the **Messages **link to open the main messaging page. Then select the New Message button to open the `Compose Message` page..

In `Edit` mode, select the main component on the page containing the Message body.

In order to access the configuraiton dialog, it is necessary to cancel inheritance by selecting the `link`icon.

Once the configuration is complete, it is necessary to restore inheritance by selecting the `broken link` icon.

![](assets/chlimage_1-400.png)

Once inheritance is canceled, it will be possible to select the `configure` icon to open the configuration dialog.

![](assets/chlimage_1-401.png)

#### Basic tab {#basic-tab-1}

![](assets/chlimage_1-402.png)

* **Redirect URL** 
  Enter the URL of the page shown after the message is sent. For example, `../messaging.html`.

* **Cancel URL** 
  Enter the URL of the page shown if the sender cancels the message. For example, `../messaging.html`.

* **Maximum length of Message Subject** 
  The maximum number of characters allowed in the Subject field. For example, 500. Default is no limit.

* **Maximum length of Message Body** 
  The maximum number of characters allowed in the Content field. For example, 10000. Default is no limit.

* **Service selector** 
  (*Required*) Set this to the value of the property**`serviceSelector.name`** from the [AEM Communities Messaging Operations Service](../../communities/using/messaging.md#messagingoperationsservice).

#### Display tab {#display-tab-1}

![](assets/chlimage_1-403.png)

* **Show Subject Field** 
  If checked, show the `Subject` field and enable adding a subject to the message. Default is not checked.

* **Subject Label** 
  Enter the text to display next to the `Subject` field. Default is `Subject`.

* **Show Attach File Field** 
  If checked, show the `Attachment` field and enable adding file attachments to the message. Default is not checked.

* **Attach File Label** 
  Enter the text to display next to the `Attachment` field. Default is **`Attach File`**.

* **Show Content Field** 
  If checked, show the `Content` field and enable adding a message body. Default is not checked.

* **Content Label** 
  Enter the text to display next to the `Content` field. Default is **`Body`**.

* **With Rich Text Editor** 
  If checked, indicates use of a custom Content text box with its own rich text editor. Default is not checked.

* **Timestamp patterns** 
  Provide timestamp patterns for one or more languages. Default is for en, de, fr, it, es, ja, zh_CN, ko_KR.

