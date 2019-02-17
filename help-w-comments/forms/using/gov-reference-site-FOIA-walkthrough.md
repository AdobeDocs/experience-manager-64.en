---
title: We.Gov reference site FOIA walkthrough
seo-title: We.Gov reference site FOIA walkthrough
description: See the We.Gov reference site walkthrough to understand how AEM Forms helps governments receive and impart information requested by individuals under the Freedom of Information Act. 
seo-description: See the We.Gov reference site walkthrough to understand how AEM Forms helps governments receive and impart information requested by individuals under the Freedom of Information Act. 
uuid: cb92db29-e983-480d-b93f-8c11b233fc46
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 4d1cbef3-0414-4401-b335-0c7d4250119d
index: y
internal: n
snippet: y
---

# We.Gov reference site FOIA walkthrough{#we-gov-reference-site-foia-walkthrough}

## Pre-requisite {#pre-requisite}

Set up your We.Gov reference site as described in the [Set up and configure AEM Forms reference sites](../../forms/using/setup-reference-sites.md).

## Reference site Freedom of Information Act scenario {#reference-site-freedom-of-information-act-scenario}

We.Gov is a state run organization that lets adoptive parents enroll for child support if they adopted a child. We.Gov also allows parents to request information from the following government departments under the freedom of information act:

* Defense Logistics Agency
* Department of Defense Office of Inspector General
* Department of Justice - Office of Information Policy
* Department of the Navy
* Environmental Protection Agency

For more information on the Freedom Of Information Act, see [www.foia.gov](http://www.foia.gov).

The scenario involves the following personas:

* Sarah Rose, the person requesting information under 
* John Jacobs, the person who handles the request the forwards it to the appropriate department
* Gloria Rios, the government employee who furnishes the information as per the request

## Sarah initiates request for information under FOIA {#sarah-initiates-request-for-information-under-foia}

Under the Freedom of Information Act, Sarah requests for copy of the Administration for Children and Families case logs for years (FY) 2013 through 2016. Sarah submits this request to the Departent of Justice - Office Of Information Policy and also signifies that she is willing to pay up to USD 100 for the printing and postage costs.

### How it works {#how-it-works}

<!--
Comment Type: draft

<p>Sarah's eligibility is validated through an eligibility barrier created using rule editor. The rule editor lets you specify conditions that are met before an applicant can fill the application form. When Sarah, the applicant, meets all the eligibility conditions, she lands on the application form. </p>
<p>The eligibility check is a part of the child support application adaptive form. The rule validates eligibility when:</p>
<ul>
<li>The applicant is a custodial parent</li>
<li>The applicant and the child stay in the state of GX</li>
<li>The applicant has the main day-to-day care of the child</li>
<li>The age of the child getting support services coverage is under 16 years.<br /> </li>
</ul>
-->

### See it yourself {#see-it-yourself}

In your browser, open `http://<hostname>:<PublishPort>/wegov`. In the We.Gov site, tap Applications &gt; All Applications. In the All Applications page, tap Apply under Application for FOIA Request.

<!--
Comment Type: draft

<p>To see the rules:</p>
<ol>
<li>Open the form in edit mode on the author instance. URL: http://&lt;hostname&gt;:&lt;AuthorPort&gt;/editor.html/content/forms/af/we-gov/child-support/css.html.</li>
<li>Select a component and click <img src="assets/edit-rules.png" />.<br /> The Rule Editor opens listing all the rules applied in the form.<br /> </li>
<li>In the left side panel, click rules passMsg and failMsg to understand how the eligibility check works.</li>
</ol>
-->

## Sarah starts her application for information under FOIA {#sarah-starts-her-application-for-information-under-foia}

Sarah clicks **Apply** and in the Freedom of Information Act Request Form page, Sarah enters information including the following:

* **Agency: **Sarah specifies the agency to which the request was addressed as Department of Justice - Office of Information Policy**. **

* **Will Pay Up To**: Sarah specifies that she is willing to pay up to USD 100 for printing and postage expenses. 
* **Describe the request in detail**: Sarah specifies "Requesting copy of the Administration for Children and Families case logs for fiscal years 2013 through 2016."

![Requesting copy of the Administration for Children and Families case logs for fiscal years 2013 through 2016](assets/sarahfiosform.png)

Requesting copy of the Administration for Children and Families case logs for fiscal years 2013 through 2016

At any time, Sarah can tap save to Save the draft of the form and come back later to fill up the form and submit it. Sarah submits the form.

>[!NOTE]
>
>The resume-from-email workflow works with logged in users only. In the reference site scenario, ensure that the user Sarah Rose is added. Sarah's login credentials are `srose/password`.

## John Jacobs receives and approves the application {#john-jacobs-receives-and-approves-the-application}

John Jacobs receives the requests and routes it to the right person. AEM Inbox lets her see all the submitted applications in one place.

### How it works {#how-it-works-1}

When Sarah fills and submits the FOIA application, a record of the application is sent to John Jacobs's inbox. John Jacobs can view the submitted application and accept or reject it.

### See it yourself {#see-it-yourself-1}

You can access the AEM inbox at http://&lt;***hostname***&gt;:&lt;***PublishP******ort***&gt;/content/we-finance/global/en/login.html?resource=/aem/inbox.html. Log in to the AEM inbox, using jjacobs/password as the username/password for John Jacobs, and see the FOIA application. For information about using AEM Inbox for forms-centric workflow tasks, see [Manage Forms applications and tasks in AEM Inbox](../../forms/using/manage-applications-inbox.md).

![](assets/johnjacobs.png)

John Jacobs can see, approve, or reject the application from the application dashboard. John Jacobs selects and opens the request details and after reviewing the request, approves it.

![](assets/johnjacobstaskdetail-1.png) 

### <strong>Sarah receives an acknowledgement email</strong> {#strong-sarah-receives-an-acknowledgement-email-strong}

After John Jacobs approves the application, Sarah receives an acknowledgement email from the We.Gov site. Sarah is informed about the fees and time required for processing her application. The email also includes email and phone details sarah can contact for updates on her application. 

![](assets/sarahroseemail.png) 

## Gloria receives the FOIA request for second level approval {#gloria-receives-the-foia-request-for-second-level-approval}

After John Jacobs fills in the required information and approves Sarah's request, the requests goes to Gloria Rios for the final approval. Gloria reviews the attached document of record and approves the request. 

![](assets/gloriariosinbox.png) 

### How it works {#how-it-works-2}

When John Jacobs approves the FOIA request, a PDF or Document of Record of the application is created and sent to Gloria Rios' inbox. Gloria can view the submitted request, and approve or reject it.

### See for yourself {#see-for-yourself}

You can access the AEM inbox at http://&lt;***hostname***&gt;:&lt;***PublishP******ort***&gt;/content/we-finance/global/en/login.html?resource=/aem/inbox.html. Log in to the AEM inbox using grios/password as the username/password for Gloria Rios, and see the FOIS request.

Gloria opens the request and examines the details of the FOIA request. After reviewing the details of the request and checking the feasibility of furnishing the required documents, Gloria approves the request. 

![](assets/gloriariosapproves.png) 

## Sarah receives notification that her request is approved {#sarah-receives-notification-that-her-request-is-approved}

After Gloria approves the FOIA request, Sarah receives an email notifying her that her request is approved. The email also includes the information about the tentative timeline for furnishing the document and contact details for follow up on the request. 

![](assets/sarahroseemailapproval.png)

