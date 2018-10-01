---
uuid: b6683c12-198b-4b9d-9305-7f6d92275714
index: y
internal: n
snippet: y
translate: y
---

# DITA Element and Style Guide for Marketing Cloud Help

This DITA project shows element samples (XML tags) and descriptions of how the Technical Publications team uses them. It can be a resource for new technical writers and a reference for developers who need to know which DITA elements require styling for output (namely, for an integration with AEM).

**Developers:** There are DITA elements in the XML, such as draft-comment, that are hidden at build time. Meaning, the [output](https://marketing.adobe.com/resources/help/en_US/internal/) for this content does not contain all of the element information that you (and writers) need. The output is intended to show only the formatting that the public sees in production. There are attributes for certain elements to consider as well.

**Writers:** This page resembles a typical **[!DNL home.xml] landing page with cross-references to new or frequently accessed topics, solution help, release notes, embedded videos, and community resources. It includes names of element tags and descriptions about their purpose. 

<table class="simpletable" id="table_5E612F746A704FE095B809A013EE977F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>New and Popular Topics</b> (Bold Para) </p> 
    <ul id="ul_7BB21A4734964D80AD468B71C862E096"> 
     <li id="li_691C20C786A140ED8C2656C8A6DD6DBE">Unordered List (ul) with List (li) </li> 
     <li id="li_A28D232ED1424D19A45F61D81452E744"> <a format="dita" href="composite-dita-topic.md#topic_298651E53E82415B9A8AD7B2F3E6927A" scope="local">Composite DITA Topic</a> (File cross-reference) </li> 
     <li id="li_063F046E3915417A8C7271F13662A217"> <a format="dita" href="concept-topic.md#concept_4CEEF9F74266431691A249916837FF46" scope="local">Concept DITA Topic</a> </li> 
     <li id="li_40E19D11726C4E5DB4487788B74FD2AD"><a format="dita" href="task-dita-topic.md#task_5103974C88264AAEB37A79E6BC8B0199" scope="local">Task DITA Topic</a> </li> 
    </ul> <p class="head">Implementation Topics (Attribute &gt; Heading Outputclass = Head) </p> 
    <ul id="ul_96ABE71D10E24459B00237067408CC3B"> 
     <li id="li_D5B18AF31E6D4E42874147AB022AAEC2"> <a format="dita" href="composite-dita-topic.md#topic_298651E53E82415B9A8AD7B2F3E6927A" scope="local">Composite DITA Topic</a> </li> 
     <li id="li_CA769AE3FEEA4A91B4F864FBDDB19E13"> <a format="dita" href="concept-topic.md#concept_4CEEF9F74266431691A249916837FF46" scope="local">Concept DITA Topic</a> </li> 
    </ul> </td> 
   <td colname="col2"> <p> <b>Release Notes &amp; Solution Help</b> (Bold Para) </p> 
    <ul id="ul_4F06F170F214492780C7D25A069F799F"> 
     <li id="li_45A7CD556FE44F4DAB035C736A058F36"><a format="dita" href="lists.md#concept_11C5663D9B954FDF9E8F3285EED642EF" scope="local">Lists</a> (A file cross-reference to a nested folder) </li> 
    </ul> <p> <b>Community Learning Resources</b> </p> 
    <ul id="ul_9CAA2B3846954AACBC9C0F4A1F3BE36E"> 
     <li id="li_51336103CDB743F5932880596D295A76"> <p>Unordered List (ul) with List (li) with para </p> <p>second para embedded in list </p> </li> 
     <li id="li_0D36177FB5C44779BDFAF1D612B55107"><q> List </q> - a list with q element, for quotes </li> 
     <li id="li_B17C0DEDE8C24E6694C57553059A8D55"> List </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

