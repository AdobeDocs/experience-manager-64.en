---
title: Planning Your Upgrade
seo-title: Planning Your Upgrade
description: null
seo-description: This article helps establish clear goals, phases and deliverables when planning the AEM upgrade.
uuid: 2b75c72f-b8ea-4ff2-ba56-a550000a0b60
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/old-upgrade-planning-page
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-03T08 43 18.323-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 49 00.090-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Deactivate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 447c62c8-5e33-42b9-8995-89a605310d70
firstPublishExternalDate: 2017-10-31T16:17:48.354-0400
jcr-created: 2017-12-01T19 06 04.810-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:18.305-0400
lochandoffdate: 2017-11-29T05 07 20.313-0500
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Planning Your Upgrade
publishexternaldate: 2018-04-03T08 43 18.305-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/old-upgrade-planning-page.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/upgrade/planning
sha1: 8a1111a6f00308335db10df88a3277730d6ef662
topicBrowsingSortDate: 2018-04-03T08:43:18.305-0400
index: y
internal: n
snippet: y
translate: y
---

# Planning Your Upgrade

## AEM Project Overview
AEM is often used in high impact deployments that might serve millions of users. In most cases, there are custom applications that are deployed on the instances which adds to the complexity. Any effort to upgrade such a deployment needs to be handled methodically.

This guide helps in establishing clear goals, phases and deliverables when planning your upgrade. It focuses on the overall project execution and guidelines, it has enough details of the actual upgrade steps, but it refers to available technical resources where suitable. It should be used in conjunction with the available technical resources referred to in the document.

The AEM Upgrade process needs carefully handled planning, analysis and execution phases with key deliverables defined for each phase.

### Assumptions
This guide focuses on upgrading from 6.1 to 6.3, and also covers the migration to the Oak based repository. However, note that it is possible to upgrade directly from AEM versions 5.4 and up to 6.3. Customers running 5.3 and below need to upgrade first to version 5.4 or above (6.2 recommended).

Please note that new oak segment tar format is used now for the segment node store, a repository migration to this new format is mandatory even for 6.0, 6.1 and 6.2.

This guide assumes the following source and target topologies:

![](assets/old-upgrade-planning-page/chlimage_1.png)

### What has changed since 6.1 ?
This is the list of key changes in AEM between 6.1 to 6.3 to be considered while planning an upgrade:

* AEM 6.0 introduced the new Jackrabbit Oak repository. Persistence Managers have been replaced by [Micro Kernels](platform.md#main-pars_title_4). Starting from version 6.1, CRX2 is no longer supported. A migration tool called crx2oak needs to be run to migrate the repository from 5.6.1 instances. For more information, see Using the [CRX2OAK Migration Tool](using-crx2oak.md).  

* Periodic garbage collection of revisions and data store garbage collection are now routine maintenance tasks that need to be performed periodically. See [Maintaining the Repository](storage-elements-in-aem-6.md#MaintainingtheRepository) for information on how to configure these tasks.  

* The crx2oak tool has been updated to handle the new oak segment tar format for the segment node store.
* The crx2oak tool command line usage options have been changed to be automation friendly and support more upgrade paths.
* The pre-upgrade maintenance tasks have been optimized to support automation.
* The new oak segment tar format is used now for the segment node store, a repository migration is mandatory.
* The post-upgrade checks have also been made automation friendly.

For more details about what changed in 6.3, see the complete release notes [here](/content/help/en/experience-manager/6-4/release-notes).

### Upgrade Scope and Requirements
Below you will find a list of areas that are impacted in a typical AEM Upgrade project:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Component</strong></td> 
   <td><strong>Impact</strong></td> 
   <td><strong>Description</strong></td> 
  </tr>
  <tr>
   <td>Operating System</td> 
   <td valign="top" width="78"><p>Uncertain, but subtle effects</p> </td> 
   <td valign="top" width="347"><p>At the time of the AEM upgrade, it may be time to upgrade the operating system as well and this might have some impact.</p> </td> 
  </tr>
  <tr>
   <td>Java Runtime</td> 
   <td valign="top" width="78"><p>Moderate Impact</p> </td> 
   <td valign="top" width="347"><p>AEM 6.3 requires JRE 1.7.x (64bit) or later.</p> </td> 
  </tr>
  <tr>
   <td>Content Repository (CRX or Oak)</td> 
   <td valign="top" width="78"><p>High Impact</p> </td> 
   <td valign="top" width="347"><p>Starting from version 6.1, AEM does not support CRX2, so a migration to Oak (CRX3) is required if upgrading from an older version. The crx2oak tool is used for this purpose.</p> </td> 
  </tr>
  <tr>
   <td>AEM Components/Content</td> 
   <td valign="top" width="78"><p>Moderate Impact</p> </td> 
   <td valign="top" width="347"><p><span class="code">/libs</span> and <span class="code">/apps</span> easily handled through the upgrade, but more work is needed for <span class="code">/etc</span>.</p> </td> 
  </tr>
  <tr>
   <td>AEM Services</td> 
   <td valign="top" width="78"><p>Low Impact</p> </td> 
   <td valign="top" width="347"><p>Most AEM core services are tested for upgrade. This is an aera of low impact.<br /> </p> </td> 
  </tr>
  <tr>
   <td>Custom Application Services<br /> </td> 
   <td valign="top" width="78"><p>Low to High Impact</p> </td> 
   <td valign="top" width="347"><p>Depending on the application and customization, there may be be dependencies on JVM, operating system versions and some indexing related changes, as indexes are not generated automatically in Oak.</p> </td> 
  </tr>
  <tr>
   <td>Custom Application Content<br /> </td> 
   <td valign="top" width="78"><p>Low to High Impact</p> </td> 
   <td valign="top" width="347"><p>Content that will not be handled through the upgrade can be backed up before the upgrade takes place and then moved back into the repository. Most content can be handled through the migration tool.</p> </td> 
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>The upgrade will require downtime for the Author tier and Publish tier as most AEM upgrades are performed as in place upgrades.

### Upgrade Best Practices

* If you are using version **5.4** or newer, you can upgrade to AEM 6.3 directly. If you are using version **5.3** or earlier you need to upgrade to AEM 6.x first(6.2 recommended), and then to 6.3

* The exact production environment needs to be duplicated and testing should be performed on it after upgrade to make sure all applications and custom code still run as desired. You need to regress all your customization and execute **performance**, **load** and **security** testing.

* Check the [Adobe Support coverage](https://www.adobe.com/support/products/enterprise/eol/eol_matrix.html#cq) for your AEM version
* Explore the opportunity to leverage new features
* Review the list of deprecated and removed features in the [Release Notes](/content/help/en/experience-manager/6-4/release-notes)
* Review the difference in the JCR API with previous versions
* The upgrade project should include implementation, regression, full testing, downtime, go-live and production operations plans
* Based on observations made in testing there could be ways to optimize the custom code. This might include refactoring the code to traverse the repository, custom indexing, use of unordered nodes in JCR and other optimizations  
* Evaluate how long the content migration will take for moving from CRX2 to Oak
* Account for additional space requirements for TarMK based on your upgrade testing.

### AEM 6.3 Technical Requirements
For more information, see the [AEM 6.3 Technical Requirements](technical-requirements.md) page.

### AEM 6.3 Testing Requirements
A comprehensive test plan should be prepared for testing upgrades and should cover the following:

* Testing the AEM implementation and all associated custom code
* Integrations with other Marketing Cloud solutions
* Integration with third party systems
* Performance testing including page load times
* A few key items to cover in the test plan in addition to core functionality testing of the AEM application and customization
* Testing of custom indexes and custom queries
* Search performance for custom queries
* Creating content and authoring
* Touch UI features
* Instance monitoring setup
* Maintenance activities
* Backup process
* Disaster Recovery plan.

## AEM Upgrade Project Phases
An AEM Upgrade project can be divided into several major phases:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Phase</strong></td> 
   <td><strong>Key Activities</strong><br /> </td> 
  </tr>
  <tr>
   <td valign="top" width="113"><p>Assessment and Planning</p> </td> 
   <td valign="top">
    <ul> 
     <li>Identify the scope of the project required</li> 
     <li>Identify the customizations and impact</li> 
     <li>Prepare upgrade plan with the schedule and dates</li> 
     <li>Prepare the test plan for testing the AEM implementation, integrations with other Marketing Cloud solutions, third party systems and performance.</li> 
    </ul> <br /> </td> 
  </tr>
  <tr>
   <td valign="top" width="113"><p>Upgrade Preparation</p> </td> 
   <td valign="top">
    <ul> 
     <li> Perform test upgrades on non production environments</li> 
     <li>Execute the upgrade test plan, including performance testing. Test custom applications and integrations. </li> 
    </ul> </td> 
  </tr>
  <tr>
   <td valign="top" width="113"><p>Upgrade Execution</p> </td> 
   <td>
    <ul> 
     <li>Actual upgrade steps performed on AEM production instances and go live event</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td valign="top" width="113"><p>Post Upgrade Activities</p> </td> 
   <td valign="top" width="373">
    <ul> 
     <li>Post upgrade smoke tests, monitoring and maintenance tasks.</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

The detailed workflows for each phase is explained in the following section, *please note that the **Duration** and **Ownership** columns for each workflow step are dependent on organizational and contract structure for each customer and has been left blank, please fill as appropriate*.

### Assesment and Planning

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Phase Prerequisite</strong></td> 
   <td valign="top" width="374"><p>Review Upgrade Scope and Requirements</p> </td> 
  </tr>
  <tr>
   <td><strong>Phase Deliverable</strong></td> 
   <td valign="top" width="374"><p>Impact Assessment Report, Upgrade Schedule, Upgrade Test Plans, AEM 6.3 Development Plan</p> </td> 
  </tr>
 </tbody>
</table>

* In the assessment and planning stage, the impact and scope of the upgrade is defined and teams are identified for upgrade tasks. Please note that for accurate assessment of the impact and effort to upgrade the custom code, craft new custom indices and other tasks, its best to clone and upgrade a development environment and perform testing beforehand.
* Development effort for moving the AEM implementation is assessed and key areas of developer effort are identified.
* Test plan documents are prepared for testing the upgrade in a staging environment, before upgrading the production environment.

#### Assesment and Planning Checklist
Duration and Owner columns are left for the reader to add their own estimate and organizational structure

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="32"><p><strong>ID</strong></p> </td> 
   <td valign="top" width="302"><p><strong>Task Description</strong></p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Assessment</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>1</p> </td> 
   <td valign="top" width="302"><p>Review the business and technical requirements associated with the AEM upgrade</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>2</p> </td> 
   <td valign="top" width="302"><p>Review roadmap for projects planned to be on-boarded onto the AEM platform</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>3</p> </td> 
   <td valign="top" width="302"><p>Review of current and go-forward architecture, hardware, infrastructure and server environment</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>4</p> </td> 
   <td valign="top" width="302"><p>Assess downtime tolerance to select appropriate upgrade options</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>5</p> </td> 
   <td valign="top" width="302"><p>Review of standards for taxonomy, tagging, templates, components, pages and content</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>6</p> </td> 
   <td valign="top" width="302"><p>Analyze the current AEM workflow models and custom processes</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>7</p> </td> 
   <td valign="top" width="302">Assess the impact of upgrade on the content structure</td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>8</p> </td> 
   <td valign="top" width="302"><p>Validate forward compatibility of templates, components, services and add-ons with new AEM version</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>8b</p> </td> 
   <td valign="top" width="302"><p>Perform repository clone analysis to see what parts of repository can be migrated smoothly with the migration tool</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>8c</p> </td> 
   <td valign="top" width="302"><p>Its also highly recommended to do a quick upgrade of a developer environment and basic smoke testing to get a better understanding of the level of effort required to get code and indexes up to speed</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>9</p> </td> 
   <td valign="top" width="302"><p>Present recommendations on upgrade strategy, execution plan, potential areas of risk and gaps and mitigation plan to close those gaps.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>9b</p> </td> 
   <td valign="top" width="302">
    <ul> 
     <li>Review the features released in 6.3</li> 
     <li>Determine communication and training requirements. Perform follow-up and update documentation based on review</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>10</p> </td> 
   <td valign="top" width="302"><p>Define success criteria for the upgrade including keeping to the planned upgrade timeline</p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Planning</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>11</p> </td> 
   <td valign="top" width="302">Customer IT and business leaders schedule dates for the following milestones of the upgrade:
    <ul> 
     <li>Readiness of the development and test plans</li> 
     <li>Upgrade of the Development Environment<br /> </li> 
     <li>Completion of the AEM 6.3 code changes</li> 
     <li>QA test and fix cycle</li> 
     <li>QA certification</li> 
     <li>Upgrade of the staging environment</li> 
     <li>Integration, Performance and Load Testing</li> 
     <li>Staging environment certification</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>12</p> </td> 
   <td valign="top" width="302">Define the rollback strategy in case upgrade success criteria are not met</td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>13</p> </td> 
   <td valign="top" width="302">Prepare Development and Test Plans including the verification of rollback strategy</td> 
  </tr>
  <tr>
   <td valign="top" width="32"><p>14</p> </td> 
   <td valign="top" width="302"><p>Create project specific upgrade run book based on detailed upgrade steps and output of upgrade assessment and planning steps</p> </td> 
  </tr>
 </tbody>
</table>

#### Upgrade Project Preparation

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="122"><p><strong>Phase Prerequisite</strong></p> </td> 
   <td valign="top" width="365"><p>Test Plans, 6.3 Development Plans</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="122"><p><strong>Phase Deliverable</strong></p> </td> 
   <td valign="top" width="365"><p>Application code ready for 6.3, QA/Development/Staging Upgrade Certification</p> </td> 
  </tr>
 </tbody>
</table>

The upgrade project preparation is mostly about upgrading the Development, QA and Staging environments and executing the test plans on these instance. Please refer to the [Upgrade instructions documentation](upgrade.md) for more details on how to perform upgrades.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="90"><p><strong>ID</strong></p> </td> 
   <td valign="top" width="252"><p><strong>Task Name</strong></p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Development Environment Upgrade</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>1. </p> </td> 
   <td valign="top" width="252"><p>Setup 6.1 environment with Production code</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>2. </p> </td> 
   <td valign="top" width="252"><p>Follow <a href="https://docs.adobe.com/content/docs/en/aem/prerelease/upgrade.html">Upgrade Steps</a> to upgrade the instances in the environment.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>3. </p> </td> 
   <td valign="top" width="252"><p>Follow the Development Plan to make code and infrastructure 6.3 ready to the environment. This may take a few weeks to months based on the impact on the AEM implementation.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>4. </p> </td> 
   <td valign="top" width="252"><p>Perform User Acceptance testing on the AEM implementation after the development phase, and file and fix any bugs encountered.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>5. </p> </td> 
   <td valign="top" width="252"><p>Commit the development changes for the 6.3 environment implementation to source control. If there is active development work on the current version, use a separate source control branch as suitable.</p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Milestone: 6.3 Development Complete</strong></p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>QA Certification</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>6. </p> </td> 
   <td valign="top" width="252"><p>Clone the QA environment with the latest content from production</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>7. </p> </td> 
   <td valign="top" width="252"><p>Upgrade the QA Environment to the latest code on 6.3</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>8. </p> </td> 
   <td valign="top" width="252"><p>Time the duration of all major upgrade steps as well as overall duration</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>9. </p> </td> 
   <td valign="top" width="252"><p>Go ahead with testing and the fix cycle based on the test plan, including the rollback strategy. Report any relevant issues to Adobe.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>10. </p> </td> 
   <td valign="top" width="252"><p>QA Cycle - Certify Environment</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>11. </p> </td> 
   <td valign="top" width="252"><p>Dev/Adobe QA Support</p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Milestone: Dev Environment QA Certified</strong></p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Stage Environment Upgrade</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>12. </p> </td> 
   <td valign="top" width="252"><p>Clone the staging environment with the latest content from production</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>13. </p> </td> 
   <td valign="top" width="252"><p>Upgrade Staging Environment to the latest code on 6.3</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>14. </p> </td> 
   <td valign="top" width="252"><p>Time the duration of all major upgrade steps as well as overall duration</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>15. </p> </td> 
   <td valign="top" width="252"><p>Perform testing and start the fix cycle for integration, performance and load testing, including the rollback strategy.</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>16. </p> </td> 
   <td valign="top" width="252"><p>Commit fixes or changes to source control for the 6.3 environment</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>17. </p> </td> 
   <td valign="top" width="252"><p>Get certification from QA<br /> </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>18. </p> </td> 
   <td valign="top" width="252"><p>Dev/Adobe QA Support</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="90"><p>19. </p> </td> 
   <td valign="top" width="252"><p>Define estimated upgrade duration and timeline based on QA and staging upgrades. Update run book with the timeline and lessons learned.</p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="486"><p><strong>Milestone: Stage Environment Certified</strong></p> </td> 
  </tr>
 </tbody>
</table>

#### Upgrade Project Execution

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="108"><p><strong>Phase Prerequisite</strong></p> </td> 
   <td valign="top" width="378"><p>Staging Upgrade Certification with full performance and load testing</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="108"><p><strong>Phase Deliverable</strong></p> </td> 
   <td valign="top" width="378"><p>Production Environment on 6.3</p> </td> 
  </tr>
 </tbody>
</table>

The upgrade project execution refers to the upgrade and go live of the production environment. The prerequisite to this phase is that the staging environment (which should be an exact copy of the production environment), went through the same upgrade, all the tests were performed and any bugs reported are fixed.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="6%"><p><strong>ID</strong></p> </td> 
   <td valign="top" width="62%"><p><strong>Task Name</strong></p> </td> 
  </tr>
  <tr>
   <td colspan="2" valign="top" width="100%"><p><strong>Production Environment Upgrade</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="6%"><p>1. </p> </td> 
   <td valign="top" width="62%"><p>Production Cutover / Detailed Planning with date and time identified based on the planned upgrade duration</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="6%"><p>2. </p> </td> 
   <td valign="top" width="62%">Stop authoring activities and start production upgrade setup using <a href="https://docs.adobe.com/content/docs/en/aem/prerelease/upgrade.html">Upgrade Procedure</a><strong>, </strong>summarized here<strong>:</strong>
    <ul> 
     <li>Clone or create images of the running instance (author or publish). These can be used later for backups.</li> 
     <li>Disable replication queues and <span class="code">Custom Login Modules</span></li> 
     <li>Run maintenance tasks</li> 
     <li>Run automated migration of the content on the target author and publish instances</li> 
     <li>Run the actual upgrade steps including re-enabling the replication queues, <span class="code">Custom Login Modules</span> and installation of the recommended hotfixes</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td valign="top" width="6%"><p>3. </p> </td> 
   <td valign="top" width="62%"><p><strong>Conduct smoke testing</strong></p> </td> 
  </tr>
  <tr>
   <td valign="top" width="6%"><p>4</p> </td> 
   <td valign="top" width="62%"><p><strong>Certify the Production instance</strong></p> </td> 
  </tr>
 </tbody>
</table>

#### Post Upgrade Activities

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="108"><p>Phase Prerequisite</p> </td> 
   <td valign="top" width="378"><p>A clean and successful upgrade of the production environment</p> </td> 
  </tr>
  <tr>
   <td valign="top" width="108"><p>Phase Deliverable</p> </td> 
   <td valign="top" width="378"><p>Performance testing and Production validation, Scheduled Maintenance tasks.</p> </td> 
  </tr>
 </tbody>
</table>

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td valign="top" width="5%"><p>ID</p> </td> 
   <td valign="top" width="62%"><p>Task Name<strong></strong></p> </td> 
   <td valign="top" width="11%"><p>Duration</p> </td> 
   <td valign="top" width="20%"><p>Owner: Customer | AGS | Partner | Managed Services</p> <p>Role: Business | Developer | Operations</p> </td> 
  </tr>
  <tr>
   <td colspan="4" valign="top" width="100%"><p>Post Production Procedure </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="5%"><p>1</p> </td> 
   <td valign="top" width="62%"><p>Post-Cutover: Production Validation</p> </td> 
   <td valign="top" width="11%"><p> </p> </td> 
   <td valign="top" width="20%"><p> </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="5%"><p>2</p> </td> 
   <td valign="top" width="62%"><p>Schedule regular maintenance for Revision clean up(compaction) and Data Store garbage collection.</p> </td> 
   <td valign="top" width="11%"><p> </p> </td> 
   <td valign="top" width="20%"><p> </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="5%"><p>3</p> </td> 
   <td valign="top" width="62%"><p>Conduct performance testing again like performed on the staging environment after the upgrade and see if the indexing strategy needs to be revisited.</p> </td> 
   <td valign="top" width="11%"><p> </p> </td> 
   <td valign="top" width="20%"><p> </p> </td> 
  </tr>
  <tr>
   <td valign="top" width="5%"><p>4</p> </td> 
   <td valign="top" width="62%"><p>Decommission activities</p> </td> 
   <td valign="top" width="11%"><p> </p> </td> 
   <td valign="top" width="20%"><p> </p> </td> 
  </tr>
 </tbody>
</table>

### Upgrade Procedure
Let’s look at the topology in more detail: the content from the Author instance gets copied to the Publish instance through replication.

When performing an upgrade, the following sequence should be followed on the topology:

![](assets/old-upgrade-planning-page/chlimage_1-1.png)

1. Stop authoring new content
1. Stop replication
1. Take a backup of all instance repositories, as any customization to libs or core components might be overwritten during migration
1. Upgrade the Author Instance to 6.3 including Oak migration then start it
1. Upgrade the Publish Instance 1 to 6.3 including Oak migration then start it
1. Upgrade Publish Instance 2 to 6.3 including Oak migration then start it  
1. Upgrade the Dispatcher modules on the web servers if needed
1. Enable replication queues.

### Upgrade Procedure Summary
The upgrade procedure can be summarized as follows:

![](assets/chlimage_1.jpeg)

>[!NOTE]
>
>&#42; Workflow purges are highly recommended unless there are regulatory concerns.
>
>&#42;&#42; Enable replication agents after all author and publish instances have been upgraded.

