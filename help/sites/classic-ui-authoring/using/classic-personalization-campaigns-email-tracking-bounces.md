---
title: Tracking Bounced Emails
seo-title: Tracking Bounced Emails
description: null
seo-description: When you send a newsletter to many users, there are usually some invalid emails addresses in the list. Sending newsletters to those addresses bounce back. AEM is capable of managing those bounces and can stop sending newsletters to those addresses after the configured bounce counter is exceeded.
uuid: e5eefc84-5826-49e8-ac91-9dd83cf9f389
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 9385387e-854f-4573-90b4-d05a201b2a23
index: y
internal: n
snippet: y
---

# Tracking Bounced Emails{#tracking-bounced-emails}

>[!NOTE]
>
>Adobe is not planning to further enhance E-mail tracking of open/bounces (not deliverable) send by AEM SMTP service.  
>Recommendation is to [leverage Adobe Campaign and the integration to AEM](../../../sites/administering/using/campaign.md).

When you send a newsletter to many users, there are usually some invalid emails adresses in the list. Sending newsletters to those addresses bounce back. AEM is capable of managing those bounces and can stop sending newsletters to those adresses after the configured bounce counter is exceeded. By default, the bounce rate is set to 3 but is configurable.

To set AEM up to track bounced emails, you need to set up AEM to poll an existing mailbox where bounced emails are received (usually this is the "from" email address that you specify where you send the newsletter). AEM polls this inbox and imports all emails below the path specified in the polling configuration. A workflow is then triggered to search for the bounced email adresses within the users and updates the bounceCounter property value of the user accordingly. After the configured max bounces is exceeded, the user is removed from the newsletter list.

### Configuring the Feed Importer {#configuring-the-feed-importer}

The feed importer lets you repeatedly import content from external sources into your repository. With this configuration of the feed importer, AEM checks the sender's mailbox for bounced emails.

To configure the feed importer for tracking bounced emails:

1. In **Tools**, select the Feed Importer.  

1. Click **Add** to create a new configuration.

   ![](assets/chlimage_1.png)

1. Add a new configuration by selecting the type and by adding information to the polling URL to configure the host and port. In addition, you need to add some mail and protocol-specific parameters to the URL query. Set the configuration to poll at least once a day.

   All configurations need information about the following in the polling URL:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><p>username</p> </td> 
   <td>The username to use for connecting</td> 
  </tr> 
  <tr> 
   <td>password</td> 
   <td>The password to use for connecting</td> 
  </tr> 
 </tbody> 
</table>

   In addition, depending on the protocol, you can configure certain settings.

   **POP3 configuration properties:**

   | pop3.leave.on.server |Defines whether to leave messages on server or not. Set to true to leave messages on server, false otherwise. Defaults to true. |
   |---|---|

   **POP3 examples:**

   | pop3s://pop.gmail.com:995/INBOX?username=user&password=secret |Using pop3 over SSL to connect to GMail on port 995 with user/secret, leaving messages on server by default |
   |---|---|
   | pop3s://pop.gmail.com:995/INBOX?username=user&password=secret&pop3.leave.on.server=false |pop3s://pop.gmail.com:995/INBOX?username=user&password=secret&pop3.leave.on.server=false |

   **IMAP configuration properties:**

   Allows you to set flags to search for.

   | imap.flag.SEEN |Set false for new/unseen message, true for already-read messages |
   |---|---|

   See [http://java.sun.com/products/javamail/javadocs/javax/mail/Flags.Flag.html](http://java.sun.com/products/javamail/javadocs/javax/mail/Flags.Flag.html) for the full list of flags.

   **IMAP examples:**

   | imaps://imap.gmail.com:993/inbox?username=user&password=secret |Using IMAP over SSL to connect to GMail on port 993 with user/secret. Getting new messages only by default. |
   |---|---|
   | imaps://imap.gmail.com:993/inbox?username=user&password=secret&imap.flag.SEEN=true |Using IMAP over SSL to connect to GMail 993 with user/secret, only getting already seen message. |
   | imaps://imap.gmail.com:993/inbox?username=user&password=secret&imap.flag.SEEN=true&imap.flag.SEEN=false |Using IMAP over SSL to connect to GMail 993 with user/secret, getting already read OR new messages. |

1. Save the configuration.

### Configuring the newsletter service component {#configuring-the-newsletter-service-component}

After configuring the feed importer, you need to configure the From address and the bounce counter.

To configure the newsletter service:

1. In the OSGi console at `<host>:<port>/system/console/configMgr` and navigate to **MCM Newsletter**.  

1. Configure the service and save the changes when finished.

   ![](assets/chlimage_1-1.png)

   The following configurations can be set to adjust the behavior:

   | Bounce Counter Maximum (max.bounce.count) |Defines the number of bounces until a user will be omitted when sending a newsletter. Setting this value to 0 disables the bounce check completely. |
   |---|---|
   | Activity No Cache (sent.activity.nocache) |Defines the cache setting to use for the newsletter sent activity |

   Once saved, the newsletter MCM service does the following:

    * Writes an activity to the users hidden stream upon successful sending of a newsletter.
    * Writes an activity if a bounce is detected and the users bounce counter changes.

   <!--
   Comment Type: draft

   <p>Still available in 5.5? not in osgi console.</p>
   <p>sent.activity.pathprefix</p>
   <p>Defines the pathprefix to use for the newsletter sent activity.</p>
   -->

   <!--
   Comment Type: draft

   <p>How does this information display? How do you know it's working?<br /> </p>
   -->

