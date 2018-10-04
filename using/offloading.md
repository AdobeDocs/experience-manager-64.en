---
title: Offloading Jobs
seo-title: Offloading Jobs
description: null
seo-description: Learn how to configure and use AEM instances in a topology in order to perform specific types of processing.
uuid: 42b5f658-cc94-488c-8dc5-a6a5d0be9c7b
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/offloading
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 31.615-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 43 22.841-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 7f626e3e-265c-4d7c-a412-b843e124b37f
firstPublishExternalDate: 2017-10-31T16:17:50.654-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 29.821-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:43:22.114-0400
lochandoffdate: 2018-04-30T03 27 31.614-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Offloading Jobs
publishexternaldate: 2018-04-03T08 43 22.114-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/offloading.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/offloading
sha1: 3b3a83adee039bc22b811c8fe3b5d6233e2f8075
topicBrowsingSortDate: 2018-04-03T08:43:22.114-0400
index: y
internal: n
snippet: y
translate: y
---

# Offloading Jobs

## Introduction

Offloading distributes processing tasks amoung Experience Manager instances in a topology. With offloading, you can use specific Experience Manager instances for performing specific types of processing. Specialized processing enables you to maximize the usage of available server resources.

Offloading is based on the [Apache Sling Discovery](http://sling.apache.org/documentation/bundles/discovery-api-and-impl.html) and Sling JobManager features. To use offloading, you add Experience Manager clusters to a topology and identify the job topics that the cluster process. Clusters are comprised of one or more Experience Manager instances, so that a single instance is considered to be a cluster.

For information about adding instances to a topology, see [Administering Topologies](offloading.md#main-pars_title_0).

#### Job Distribution

The Sling JobManager and JobConsumer enable the creation of jobs that are processed in a topology:

* JobManager: A service that creates jobs for specific topics.
* JobConsumer: A service that executes jobs of one or more topics. Multiple JobConsumer services can be registered for the same topic.

When JobManager creates a job, the Offloading framework selects an Experience Manager cluster in the topology to execute the job:

* The cluster must include one or more instances that are running a JobConsumer that is registered for the job topic.
* The topic must be enabled for at least one instance in the cluster.

See [Configuring Topic Consumption](offloading.md#main-pars_title_2) for information about refining job distribution.

![](assets/chlimage_1.png)

When the Offloading framework selects a cluster to execute a job, and the cluseter is comprised of multiple instances, Sling Distribution determines which instance in the cluster executes the job.

#### Job Payloads

The Offloading framework supports job payloads that associate jobs with resources in the repository. Job payloads are useful when jobs are created for processing resources and the job is offloaded to another computer.

Upon creation of a job, the payload is only guaranteed to be located on the instance that creates the job. When offloading the job, replication agents ensure that the payload is created on the instance that eventually consumes the job. When job execution is complete, reverse replication causes the payload to be copied back to the instance that created the job.

## Administering Topologies

Topologies are loosely-coupled Experience Manager clusters that are participating in offloading. A cluster consists of one or more Experience Manager server instances (a single instance is considered as a cluster).

Each Experience Manager instance runs the following Offloading-related services:

* Discovery Service: Sends requests to a Topology Connector to join the topology.
* Topology Connector: Receives the join requests and either accepts or refuses each request.

The Discovery Service of all members of the topology point to the Topology Connector on one of the members. In the sections that follow, this member is referred to as the root member.

![](assets/chlimage_1.png)

Each cluster in the topology contains an instance that is recognized as the leader. The cluster leader interacts with the topology on behalf of the other members of the cluster. When the leader leaves the cluster, a new leader for the cluster is automatically chosen.

#### Viewing the Topology

Use Topology Browser to explore the state of the topology in which the Experience Manager instance is participating. Topology Browser shows the clusters and instances of the topology.

For each cluster, you see a list of cluster members that indicates the order in which each member joined the cluseter, and which member is the Leader. The Current property indicates the instance that you are currently administering.

For each instance in the cluster, you can see several topology-related properties:

* A whitelist of topics for the instance's job consumer.
* The endpoints that are exposed for connecting with the topology.
* The job topics for which the instance is registered for offloading.
* The job topics that the instance processes.

1. Using the Touch UI, click the Tools tab. ( [http://localhost:4502/tools.html](http://localhost:4502/tools.html))

1. In the Granite Operations area, click Offloading Browser.

1. In the navigation panel, click Topology Browser.

   The clusters that are participating in the topology appear.

   ![](assets/chlimage_1.png)

1. Click a cluster to see a list of the instances in the cluster and their ID, Current status, and Leader status.

1. Click an instance ID to see more detailed properties.

You can also use the Web Console to view topology information. The console provides further information about the topology clusters:

* Which instance is the local instance.
* The Topology Connector services that this instance uses to connect to the topology (outgoing), and the services that connect to this instance (incoming).
* Change history for the topology and intance properties.

Use the following procedure to open the Topology Management page of the Web Console:

1. Open the Web Console in your browser. ( [http://localhost:4502/system/console](http://localhost:4502/system/console))

1. Click Main &gt; Topology Management.

   ![](assets/chlimage_1.png)

#### Configuring Topology Membership

The Apache Sling Resource-Based Discovery Service runs on each instance to control how Experience Manager instances interact with a topology.

The Discovery Service sends periodic POST requests (heartbeats) to Topology Connector services to establish and maintain connections with the topology. The Topology Connector service maintains a whitelist of IP addresses or host names that are allowed to join the topology:

* To join an instance to a topology, specify the URL of the Topology Connector service of the root member.
* To enable an instance to join a topology, add the instance to the whitelist of the root member's Topology Connector service.

Use the Web Console or a sling:OsgiConfig node to configure the following properties of the org.apache.sling.discovery.impt.Config service:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>Property Name</th> 
   <th>OSGi Name</th> 
   <th>Description</th> 
   <th>Default Value</th> 
  </tr> 
  <tr> 
   <td>Heartbeat timeout (seconds)</td> 
   <td>heartbeatTimeout</td> 
   <td>The amount of time in seconds to wait for a heartbeat response before the targeted instance is considered unavailable. </td> 
   <td>20</td> 
  </tr> 
  <tr> 
   <td>Heartbeat interval (seconds)</td> 
   <td>heartbeatInterval</td> 
   <td>The amount of time in seconds between heartbeats.</td> 
   <td>15</td> 
  </tr> 
  <tr> 
   <td>Minimal Event Delay (seconds)</td> 
   <td>minEventDelay</td> 
   <td><p>When a change occurs to the topology, the amount of time to delay the change of state from TOPOLOGY_CHANGING to TOPOLOGY_CHANGED. Each change that occurs when the state is TOPOLOGY_CHANGING increases the delay by this amount of time.</p> <p>This delay prevents listeners from being flooded with events. </p> <p>To use no delay, specify 0 or a negative number.</p> </td> 
   <td>3</td> 
  </tr> 
  <tr> 
   <td>Topology Connector URLs</td> 
   <td>topologyConnectorUrls</td> 
   <td>The URLs of the Topology Connector services to send heartbeat messages.</td> 
   <td>http://localhost:4502/libs/sling/topology/connector</td> 
  </tr> 
  <tr> 
   <td>Topology Connector Whitelist</td> 
   <td>topologyConnectorWhitelist</td> 
   <td>The list of IP addresses or host names that the local Topology Connector service allows in the topology. </td> 
   <td><p>localhost</p> <p>127.0.0.1</p> </td> 
  </tr> 
  <tr> 
   <td>Repository Descriptor Name</td> 
   <td>leaderElectionRepositoryDescriptor</td> 
   <td> </td> 
   <td>&lt;no value&gt;</td> 
  </tr> 
 </tbody> 
</table>

Use the following procedure to connect a CQ instance to the root member of a topology. The procedure points the instance to the Topology Connector URL of the root topology member. Perform this procedure on all members of the topology.

1. Open the Web Console in your browser. ( [http://localhost:4502/system/console](http://localhost:4502/system/console))

1. Click Main &gt; Topology Management.

1. Click Configure Discovery Service.

1. Add an item to the Topology Connector URLs property, and specify the URL of the root topology member's Topology Connector service. The URL is in the form http://rootservername:4502/libs/sling/topology/connector.

Perform the following procedure on the root member of the topology. The procedure adds the names of the other topology members to its Discovery Service whitelist.

1. Open the Web Console in your browser. ( [http://localhost:4502/system/console](http://localhost:4502/system/console))

1. Click Main &gt; Topology Management.

1. Click Configure Discovery Service.

1. For each member of the topology, add an item to the Topology Connector Whitelist property, and specify the host name or IP address of the topology member.

## Configuring Topic Consumption

Use Offloading Browser to configure topic consumption for the Experience Manager instances in the topology. For each instance, you can specify the topics that it consumes. For example, to configure your topology so that only one instance consumes topics of a specific type, disable the topic on all instances except for one.

Jobs are distributed amoung instances that have the associated topic enabled using round-robin logic.

1. Using the Touch UI, click the Tools tab. ( [http://localhost:4502/tools.html](http://localhost:4502/tools.html))

1. In the Granite Operations area, click Offloading Browser.

1. In the navigation panel, click Offloading Browser.

   The offloading topics and the server instances that that can consume the topics appear.

   ![](assets/chlimage_1.png)

1. To disable the consumption of a topic for an instance, below the topc name click Disable beside the instance.

1. To configure all topic consumption for an instance, click the instance identifier below any topic. 

   ![](assets/chlimage_1.png)

1. Click one of the following buttons beside a topic to configure the consumption behavior for the instance, and then click Save:

    * Enabled: This instance consumes jobs of this topic.    
    * Disabled: This instance does not consume jobs of this topic.    
    * Exclusive: This instance consumes jobs only of this topic.

   **Note:** When you select Exclusive for a topic, all of the other topics are automatically set to Disabled.

#### Installed Job Consumers

Several JobConsumer implementations are installed with Experience Manager. The topics for which these JobConsumers are registered appear in Offloading Browser. Additional topics that appear are those that custom JobConsumers have registered. The following table describes the default JobConsumers.

| Job topic |Service PID |Description |
|---|---|---|
| / |org.apache.sling.event.impl.jobs.deprecated.EventAdminBridge |Installed with Apache Sling. Processes jobs that the OSGi event admin generates, for backward compatibility. |
| com/day/cq/replication/job/* |com.day.cq.replication.impl.AgentManagerImpl |A replication agent that replicates job payloads. |
| com/adobe/granite/workflow/offloading |com.adobe.granite.workflow.core.offloading.WorkflowOffloadingJobConsumer |Processes jobs that the DAM Update Asset Offloader workflow generates. |

#### Disabling and Enabling Topics For an Instance

The Apache Sling Job Consumer Manager service provides topic whitelist and blacklist properties. Configure these properties to enable or disable the processing of specific topics on an Experience Manager instance.

**Note:** If the instance belongs to a topology, you can also use Offloading Browser on any computer in the topology to enable or disable topics.

The logic that creates the list of enabled topics first allows all of the topics that are in the whitelist, and then removes topics that are on the blacklist.By default, all topics are enabled (the whitelist value is `*`) and no topics are disabled (the blacklist has no value).

Use Web Console or a `sling:OsgiConfig` node to configure the following properties. For `sling:OsgiConfig` nodes, the PID of the Job Consumer Manager service is org.apache.sling.event.impl.jobs.JobConsumerManager.

| Property Name in Web Console |OSGi ID |Description |
|---|---|---|
| Topic Whitelist |job.consumermanager.whitelist |A list of topics that the local JobManager service processes. The default value of * causes all topics to be sent to the registered TopicConsumer service. |
| Topic Blacklist |job.consumermanager.blacklist |A list of topics that the local JobManager service does not process.  |

## Creating Replication Agents For Offloading

The offloading framework uses replication to transport resources between author and worker. The offloading framework automatically creates replication agents when instances join the topology. The agents are created with default values. You must manually change the password that the agents use for authentication.

>[!CAUTION]
>
><p>A known issue with the automatically-generated replication agents requires you to manually create new replication agents. Follow the procedure in <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/offloading.html#main-pars_title_14">Problems Using the Automatically Generated Replication Agents</a> before you create the agents for Offloading.</p>

Create the replication agents that transport job payloads between instances for offloading. The following illustration shows the agents that are required to offload from the author to a worker instance. The author has a Sling ID of 1 and the worker instance has a Sling ID of 2: 

![](assets/chlimage_1.png)

This setup requires the following three agents:

1. An outgoing agent on the author instance that replicates to the worker instance.
1. A reverse agent on the author instance that pulls from the outbox on the worker instance.
1. An outbox agent on the worker instance.

This replication scheme is similar to that used between author and publish instances. However, for the offloading situation all of the instances involved are authoring instances.

>[!NOTE]
>
><p>The Offloading framework uses the topology to obtain the IP addresses of the offloading instances. The framework then automatically creates the replication agents based on these IP addresses. If the IP addresses of the offloading instances later change, the change is automatically propaged on the topology after the instance restarts. However, the Offloading framework does not automatically update the replication agents to reflect the new IP addresses. To avoid this situaion, use fixed IP addresses for all instances in the topology.&nbsp;</p>

#### Naming the Replication Agents for Offloading

Use a specific format for the ***Name*** property of the replication agents so that the offloading framework automatically uses the correct agent for specific worker instances.

**Naming the outgoing agent on the author instance:**

`offloading_`* `<slingid>`*, where `*<slingid>*` is the Sling ID of the worker instance.

Example: `offloading_f5c8494a-4220-49b8-b079-360a72f71559`

**Naming the reverse agent on the author instance:**

`offloading_reverse_*<slingid>*`, where * `<slingid>`* is the Sling ID of the worker instance.

Example: `offloading_reverse_f5c8494a-4220-49b8-b079-360a72f71559`

**Naming the outbox on the worker instance:**

`offloading_outbox`

#### Creating the outgoing agent

1. Create a** Replication Agent **on author. (See the [documention for replication agents](replication.md)). Specify any **Title**. The **Name** must follow the naming convention. 

1. Create the agent using the following properties:

   | Property |Value |
   |---|---|
   | Settings > Serialization Type |Default |
   | Transport >Transport URI |http://*<ip of target instance>*:*<port>*/bin/receive?sling:authRequestLogin=1 |
   | Transport >Transport User |Replication user on target instance |
   | Transport >Transport Passoword |Replication user password on target instance |
   | Extended > HTTP Method |POST |
   | Triggers > Ignore Default |True |

#### Creating the reverse agent

1. Create a** Reverse Replication Agent **on author. (See the [documention for replication agents](replication.md).) Specify any **Title. **The **Name** must follow the naming convention. 

1. Create the agent using the following properties:

   | Property |Value |
   |---|---|
   | Settings > Serialization Type |Default |
   | Transport >Transport URI |http://*<ip of target instance>*:*<port>*/bin/receive?sling:authRequestLogin=1 |
   | Transport >Transport User |Replication user on target instance |
   | Transport >Transport Passoword |Replication user password on target instance |
   | Extended > HTTP Method |GET |

#### Creating the outbox agent

1. Create a **Replication Agent **on the worker instance. (See the [documention for replication agents](replication.md).) Specify any **Title**. The **Name** must be `offloading_outbox`.

1. Create the agent using the following properties.

   | Property |Value |
   |---|---|
   | Settings > Serialization Type |Default |
   | Transport >Transport URI |repo://var/replication/outbox |
   | Trigger > Ignore Default |True |

#### Finding the Sling ID

Obtain the Sling ID of an Experience Manager instance using either of the following methods:

* Open the Web Console and, in the Sling Settings, find the value of the Sling ID property ( [http://localhost:4502/system/console/status-slingsettings](http://localhost:4502/system/console/status-slingsettings)). This method is usefull if the instance is not yet part of the topology.
* Use the Topology browser if the instance is already part of the topology.

## Offloading the Processing of DAM Assets

Configure the instances of a topology so that specific instances perform the background processing of assets that are added or updated in DAM.

By default, Experience Manager executes the DAM Update Asset workflow when a DAM asset changes or one is added to DAM. Change the default behavior so that Experience Manager instead executes the DAM Update Asset Offloader workflow. This workflow generates a JobManager job that has a topic of `com/adobe/granite/workflow/offloading`. Then, configure the topology so that the job is offloaded to a dedicated worker.

>[!CAUTION]
>
><p>&nbsp;No workflow should be transient when used with workflow offloading. For example, the DAM Update Asset workflow must not be transient when used for asset offloading.&nbsp;To set/unset the transient flag on a workflow, see&nbsp;<a href="/content/help/en/experience-manager/6-4/assets/using/performance-tuning-guidelines.html#Workflows">Transient Workflows</a>.</p>

The following procedure assumes the following characteristics for the offloading topology:

* One or more Experience Manager instance are authoring instances that users interact with for adding or updating DAM assets.
* Users to do not directly interact with one or more Experience Manager instances that process the DAM assets. These instances are dedicated to the background processing of DAM assets.

1. On each Experience Manager instance, configure the Discovery Service so that it points to the root Topography Connector. (See [Configuring Topology Membership](#title4).)

1. Configure the root Topography Connector so that the connecting instances are on the whitelist. 

1. Open Offloading Browser and disable the `com/adobe/granite/workflow/offloading` topic on the instances with which users interact to upload or change DAM assets.

   ![](assets/chlimage_1.png)

1. On each instance that users interact with to upload or change DAM assets, configure workflow launchers to use the DAM Update Asset Offloading workflow:

    1. Open the Workflow console.    
    1. Click the Launcher tab.    
    1. Locate the two Launcher configurations that execute the DAM Update Asset workflow. One launcher configuration event type is Node Created, and the other type is Node Modified.    
    1. Change both event types so that they execute the DAM Update Asset Offloading workflow. (For information about launcher configurations, see [Starting Workflows When Nodes Change](/content/help/en/experience-manager/6-4/sites/administering/using/workflows-starting).)

1. On the instances that perform the background processing of DAM assets, disable the workflow launchers that execute the DAM Update Asset workflow.

### Further Reading

In addition to the details presented on this page, you can also read the following:

* For information about using Java APIs to create jobs and job consumers, see [Creating and Consuming Jobs for Offloading](/content/help/en/experience-manager/6-4/sites/developing/using/dev-offloading).
* For general guidelines and best practices for asset offloading, see [General Guidelines and Best Practices for Asset Offloading](/content/help/en/experience-manager/6-4/assets/using/assets-offloading-best-practices#GeneralGuidanceandBestPracticesforAssetOffloading).
* To know how to disable the automatic creation of offloading agents, see [Turning Off Automatic Agent Management](/content/help/en/experience-manager/6-4/assets/using/assets-offloading-best-practices#Turningoffautomaticagentmanagement).

### Known Offloading Issues

<!-- <p>Hidden this chapter as a result of <a href="https://jira.corp.adobe.com/browse/CQDOC-10772">CQDOC-10772</a> (see comments).</p> -->

The following issues are related to the behavior of the Offloading framework.

#### Working Offline

You can use offloading without using a network interface where all instances run on the same computer using different ports. This situation is useful for demonstration or development purposes. To enable this situation, configure all IP addresses and URLs using localhost as the computer name.

To use offloading offline, you should initially start your Experience Manager instances when the computer is offline so that the replication agents are created using `localhost as the IP address. Using localhost causes the correct behavior if the computer later goes online.`

If you initially start your instances when the computer has a network interface, the IP address of the computer is used in the properties of the replication agents. If you later go offline, the replication agents will not function correctly.

#### Problems Using the Automatically-Generated Replication Agents

<!-- <p>See Granite-3338</p> -->

By default, the offloading framework automatically creates the replication agents for transporting resources between author and offloading workers. These agents are meant to be administered using the Granite Replication Agent UI and therefore do not appear in the Experience Manager Replication Agent console. Limitations of the Granite Replication Agent UI prevent the full management of replication agents. Therefore, you must use the Experience Manager Replication console and use the following procedure to implement the following changes:

* Disable the automatic creation of the replication agents.
* Remove any automatically-created agents.
* Manually create the agents that the Offloading framework requires.

1. To disable the automatic creation of replication agents for offloading, on each computer in the topology use CRXDE Lite to delete the `/libs/granite/offloading/config.author/com.adobe.granite.offloading.impl.transporter.OffloadingAgentManager` node.

1. On all instances in the topology, use CRXDE Lite to delete all replication agent nodes below `/etc/replication/agents.author`. The node names are prefixed with `offloading_` as per the required naming convention.

1. To manually create the Offloading replication agents, use the procedure in [Creating Replication Agents for Offloading](offloading.md#main-pars_title_9).

