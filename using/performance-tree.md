---
title: Performance Tree
seo-title: Performance Tree
description: null
seo-description: Learn about the steps that need to be taken in order to troubleshoot performance issues in AEM.
uuid: d1bab739-4029-4b01-a72f-558a924874dd
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/performance-tree
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 46.124-0400
cq-lastmodifiedby: msm-service
cq-lastreplicated: 2018-04-03T08 43 05.342-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
cq-template: /apps/help/templates/article-3
discoiquuid: 3afc085c-a2af-4a6e-8a9c-450b28866554
firstPublishExternalDate: 2017-10-31T16:17:49.000-0400
isreadyforlocalization: false
jcr-created: 2018-01-30T07 01 02.636-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:04.673-0400
lochandoffdate: 2018-04-30T03 27 46.123-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/best-practices;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/best-practices
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 43 04.673-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/performance-tree.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/performance/performance-tree
sha1: 606f3f12db311f1556dee412c543ff19b3121948
topicBrowsingSortDate: 2018-04-03T08:43:04.673-0400
index: y
internal: n
snippet: y
translate: y
---

# Performance Tree

---

## Scope

The below diagram is meant to provide guidance on the steps that need to be taken in order to troubleshoot performance issues. It is split in 5 sections for easier reading.

Each step in the diagram is linked to a documentation resource or a recommendation.

---

## Prerequisites and Assumptions

The assumption is that a performance issue is observed on a given page (either an AEM console or a web page) and can be reproduced consistently. Having a way to test or monitor the performance is a pre-requisite before starting the investigation.

The analysis starts at step 0. The goal is to determine which entity (dispatcher, external host or AEM) is responsible for the performance issue then determine which area (server or network) should be investigated.

### Section 1
![](assets/chlimage_1.png) 

### Section 2
![](assets/chlimage_1.png) 

### Section 3
![](assets/chlimage_1.png) 

### Section 4
![](assets/chlimage_1.png) 

### Section 5
![](assets/chlimage_1.png) 

---

## Reference Links

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Step</strong></td> 
   <td><strong>Title</strong></td> 
   <td><strong>Resources</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Step 0</strong></td> 
   <td>Analyze Request Flow</td> 
   <td><p>You can use standard HTTP request analysis in the browser to analyze the request flow. For more info on how to do this on Chrome, see:<br /> </p> <p><a href="https://developers.google.com/web/tools/chrome-devtools/profile/network-performance/resource-loading">https://developers.google.com/web/tools/chrome-devtools/profile/network-performance/resource-loading</a><a href="https://developers.google.com/web/tools/chrome-devtools/profile/network-performance/understanding-resource-timing"><br /> https://developers.google.com/web/tools/chrome-devtools/profile/network-performance/understanding-resource-timing</a><br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 2</strong></td> 
   <td>Are requests coming from external hosts?</td> 
   <td>You can use standard HTTP request analysis in the browser to analyze the request flow. See the above links on how to do this on Chrome.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 3</strong></td> 
   <td>Can the requests be cached?</td> 
   <td>For more information on cacheable requests and general Dispatcher performance optimization advice, see <a href="configuring-performance.md#OptimizingPerformancewhenusingtheDispatcher">Dispatcher Performance Optimization</a>.</td> 
  </tr> 
  <tr> 
   <td><strong>Step 4</strong></td> 
   <td>Are requests coming from the Dispatcher?</td> 
   <td><p>Check the <a href="/content/help/en/experience-manager/dispatcher/using/dispatcher-configuration#Debugging">Dispatcher debugging documentation</a> to see if the requests are cached properly.<br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 5</strong></td> 
   <td>Is the Dispatcher trying to authenticate each request via AEM?</td> 
   <td>Check if the dispatcher sends <span class="code">HEAD</span> requests to AEM for authentication before delivering the cached resource. You can do this by looking for <span class="code">HEAD</span> requests in the AEM <span class="code">access.log</span>. For more information, see <a href="configure-logging.md">Logging</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 6</strong></td> 
   <td>Is the geographic location of the Dispatcher far away from the users?</td> 
   <td>Move the Dispatcher closer to the users.</td> 
  </tr> 
  <tr> 
   <td><strong>Step 7</strong></td> 
   <td>Is the network layer of the Dispatcher OK?</td> 
   <td><br /> Investigate the network layer for saturation and latency issues.<p> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 8</strong></td> 
   <td>Is the slowness reproducible with a local instance?</td> 
   <td><br /> <p>Use <a href="/content/help/en/experience-manager/6-4/sites/developing/using/tough-day">Tough Day</a> to replicate "real world" conditions from the production instances. If this is not realistic for the slace of your development, make sure to test the production instance (or an identical staging one) in a different network context.<br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 9</strong></td> 
   <td>Is the geographical location of the server far away from the users?</td> 
   <td>Move the server closer to the users.</td> 
  </tr> 
  <tr> 
   <td><strong>Steps 10 and 29</strong></td> 
   <td>Investigate network layer</td> 
   <td><p>Investigate the network layer for saturation and latency issues.</p> <p>For the author tier, it is recommended that the latency does not surpass 100 milliseconds.</p> <p>For more information on performance optimization tips, see <a href="/content/help/en/experience-manager/kb/performance-tuning-tips">this page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 11</strong></td> 
   <td>Move server closer or add one per region</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 12</strong></td> 
   <td>Troubleshoot AEM server</td> 
   <td>Check the following sub steps in the diagram for more information.</td> 
  </tr> 
  <tr> 
   <td><strong>Step 13</strong></td> 
   <td>Check hardware requirements</td> 
   <td>Check the documentation on <a href="/content/help/en/experience-manager/6-4/managing/using/hardware-sizing-guidelines">Hardware Sizing Guidelines</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 14</strong></td> 
   <td>Check for frequent causes of performance issues</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 15</strong></td> 
   <td>Find slow requests</td> 
   <td><p>You can check for slow requests by analysing the <span class="code">request.log</span> or by using <span class="code">rlog.jar</span>.</p> <p>For more information about using rlog.jar, see this page.</p> <p>See <a href="monitoring-and-maintaining.md#Usingrlogjartofindrequestswithlongdurationtimes">Using rlog.jar to find requests with long duration times</a>.<br /> </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 16</strong></td> 
   <td>Profile server</td> 
   <td><p>For information about profiling tools you can use with AEM, see <a href="monitoring-and-maintaining.md#ToolsforMonitoringandAnalyzingPerformanc">Tools for Monitoring and Analyzing Performance</a>.<br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 17</strong></td> 
   <td>Find slow methods in profiling</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 18</strong></td> 
   <td>Common scenarios of profiling</td> 
   <td>See <a href="monitoring-and-maintaining.md#AnalyzingSpecificScenarios">Analyzing Specific Scenarios</a> in the Performance Optimization section.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 19</strong></td> 
   <td>100% CPU</td> 
   <td><a href="monitoring-and-maintaining.md#MonitoringPerformance">https://helpx.adobe.com/experience-manager/6-3/sites/deploying/using/monitoring-and-maintaining.html#MonitoringPerformance</a></td> 
  </tr> 
  <tr> 
   <td><strong>Step 20</strong></td> 
   <td>Out of memory</td> 
   <td><br /> 
    <ol> 
     <li><a href="monitoring-and-maintaining.md#OutofMemory">Out Of Memory</a></li> 
     <li><a href="troubleshooting.md">My application throws out-of-memory errors</a></li> 
     <li><a href="/content/help/en/experience-manager/kb/AnalyzeMemoryProblems">Analyze Memory Problems on Helpx.</a><br /> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 21</strong></td> 
   <td>Disk I/O</td> 
   <td><p>See the <a href="monitoring-and-maintaining.md#DiskI2FO">Disk I/O</a> section in the Monitoring and Maintaining documentation.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Steps 22 and 22.1</strong></td> 
   <td>Cache ratio</td> 
   <td>See <a href="configuring-performance.md#CalculatingtheDispatcherCacheRatio">Calculating the Dispatcher Cache Ratio</a>.<br /> <br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 23</strong></td> 
   <td>Slow queries</td> 
   <td><a href="best-practices-for-queries-and-indexing.md">Best Practices for Queries and Indexing</a></td> 
  </tr> 
  <tr> 
   <td><strong>Step 24</strong></td> 
   <td>Repository tuning</td> 
   <td> 
    <ul> 
     <li><a href="/content/help/en/experience-manager/kb/performance-tuning-tips">Performance Tuning Tips</a></li> 
     <li><a href="configuring-performance.md#ConfiguringforPerformance">Configuring for Performance</a></li> 
     <li><a href="http://www.slideshare.net/jukka/repository-performance-tuning">Repository Performance Tuning</a></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 25</strong></td> 
   <td>Workflows running</td> 
   <td> 
    <ul> 
     <li><a href="configuring-performance.md#ConcurrentWorkflowProcessing">Concurrent Workflow Processing</a></li> 
     <li><a href="configuring-performance.md#ConfiguretheQueueforaSpecificWorkflow">Configure the Queue for a Specific Workflow</a></li> 
     <li><a href="/content/help/en/experience-manager/6-4/sites/administering/using/workflows-administering#RegularPurgingofWorkflowInstances">Regular Purging of Workflow Instances</a></li> 
     <li><a href="/content/help/en/experience-manager/6-4/sites/developing/using/workflows.html?#TransientWorkflows">Transient Workflows</a><br /> </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 26</strong></td> 
   <td>MSM Infrastructure</td> 
   <td><p><a href="/content/help/en/experience-manager/6-4/sites/administering/using/msm-best-practices">Multi Site Manager Best Practices</a><br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 27</strong></td> 
   <td>Assets tuning</td> 
   <td> 
    <ol> 
     <li><a href="configuring-performance.md#CQ5DAMAssetSynchronizationService">Assets Synchronization Service</a></li> 
     <li><a href="configuring-performance.md#MultipleDAMinstances">Multiple DAM Instances</a></li> 
     <li>Performance tuning tips articles <a href="/content/help/en/experience-manager/kb/performance-tuning-tips">here</a> and <a href="/content/help/en/experience-manager/kb/performance-tuning-tips">here</a>.<br /> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 28</strong></td> 
   <td>Unclosed sessions</td> 
   <td><p> </p> <p><a href="/content/help/en/experience-manager/6-4/sites/administering/using/troubleshoot#CheckingforunclosedJCRsessions">Checking for unclosed JCR sessions</a></p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 30</strong></td> 
   <td>Move dispatcher closer (add one per "region"?)</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 31</strong></td> 
   <td>Use CDN in front of dispatcher</td> 
   <td><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher#UsingDispatcherwithaCDN">Using Dispatcher with a CDN</a><br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 32</strong></td> 
   <td>Use session management at the dispatcher level to offload AEM server</td> 
   <td><p><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher-configuration#EnablingSecureSessionssessionmanagement">Enabling Secure Sessions</a></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 33</strong></td> 
   <td>Make requests cacheable</td> 
   <td> 
    <ol> 
     <li><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher">General Dispatcher Configuration</a></li> 
     <li><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher-configuration#ConfiguringtheDispatcherCachecache">Configuring the Dispatcher Cache</a></li> 
    </ol> <p>How to improve cache ratio; make requests cache-able (Dispatcher best practices)</p> <p>Also, take into consideration the below settings in order to optimize your caching configurations<br /> </p> 
    <ol> 
     <li>Set a no-cache rule for HTTP requesrst that are not GET</li> 
     <li>Configure query strings to not be cacheable</li> 
     <li>Do not cache URLs with missing extensions</li> 
     <li>Cache authentication headers (possible since Dispatcher version 4.1.10)</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 34</strong></td> 
   <td>Upgrade dispatcher version</td> 
   <td>You can download the latest Dispatcher version at this location:<a href="https://www.adobeaemcloud.com/content/companies/public/adobe/dispatcher/dispatcher.html"><br /> https://www.adobeaemcloud.com/content/companies/public/adobe/dispatcher/dispatcher.html</a></td> 
  </tr> 
  <tr> 
   <td><strong>Step 35</strong></td> 
   <td>Configure dispatcher</td> 
   <td><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher-configuration">Configuring the Dispatcher</a><br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 36</strong></td> 
   <td>Check cache invalidation</td> 
   <td><br /> 
    <ul> 
     <li><a href="/content/help/en/experience-manager/dispatcher/using/page-invalidate#InvalidatingDispatcherCachefromtheAuthoringEnvironment">Cache Invalidation for the Author tier;</a></li> 
     <li><a href="/content/help/en/experience-manager/dispatcher/using/page-invalidate#InvalidatingDispatcherCachefromaPublishingInstance">Cache Invalidation for the Publish tier.</a></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Steps 37 and 38</strong></td> 
   <td>Lazy-loading</td> 
   <td><a href="https://docs.adobe.com/ddc/en/gems/aem-web-performance.html">See the Gem Session on AEM Web Performance.</a><br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 39</strong></td> 
   <td>Use pre-connect to reduce connection overhead</td> 
   <td>See the Gem Session indicated above. Also, additional documentation preconnect on W3c:<a href="https://www.w3.org/TR/resource-hints/#dfn-preconnect"> https://www.w3.org/TR/resource-hints/#dfn-preconnect</a></td> 
  </tr> 
  <tr> 
   <td><strong>Steps 40 and 41</strong><br /> </td> 
   <td>External hosts latency and response time</td> 
   <td>Investigate the latency and response time for the external hosts.</td> 
  </tr> 
  <tr> 
   <td><strong>Steps 45<br /> and 47</strong><br /> </td> 
   <td>Using HTTP/2</td> 
   <td>See the Gem Session for steps 37,38 and 39. Also, check out <a href="http://help-forums.adobe.com/content/adobeforums/en/experience-manager-forum/adobe-experience-manager.topic.html/forum__kdzc-does_anyoneknowwhe.html">this</a> forum post on HTTP/2 support.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 49</strong></td> 
   <td>Shrink payload size</td> 
   <td><a href="osgi-configuration-settings.md#AdobeGraniteHTMLLibraryManager">Enable Gzip</a> and <a href="https://docs.adobe.com/ddc/en/gems/aem-web-performance.html">shrink the image size</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>Steps 42 and 43</strong></td> 
   <td>Keep-Alive</td> 
   <td><p>Is the <span class="code">Keep-Alive</span> header present in the different requests to re-use connections? Otherwise, it would mean that each requests leads to another connection establishment, which introduces unnecessary overhead. (Standard HTTP request analysis in the browser)</p> <p>You can check the <a href="/content/help/en/experience-manager/6-4/sites/administering/using/proxy-jar">Proxy Server tool</a> to check for Keep-Alive connections.<br /> </p> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 44</strong></td> 
   <td>How many requests are made?</td> 
   <td>Perform standard HTTP request analysis in the browser.</td> 
  </tr> 
  <tr> 
   <td><strong>Step 46</strong></td> 
   <td>Reduce number of requests</td> 
   <td> 
    <ol> 
     <li>Concatenate resources (images, CSS sprites, JSON, etc.)<br /> </li> 
     <li>Clientlibs embedding: 
      <ol> 
       <li><a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#CreatingClientLibraryFolders">Creating Client Library Folders</a> - see heading Using embedding to minimize requests</li> 
      </ol> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Step 48</strong></td> 
   <td>What is the size of the payload?</td> 
   <td>Standard HTTP request analysis in the browser</td> 
  </tr> 
  <tr> 
   <td><strong>Steps 50 and 51</strong></td> 
   <td>JS code blocking</td> 
   <td><a href="https://docs.adobe.com/ddc/en/gems/aem-web-performance.html">https://docs.adobe.com/ddc/en/gems/aem-web-performance.html</a></td> 
  </tr> 
 </tbody> 
</table>

