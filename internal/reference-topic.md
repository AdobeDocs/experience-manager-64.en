---
uuid: b9fa002c-696b-416c-b7ef-876a568fa520
index: y
internal: n
snippet: y
translate: y
---

# Reference DITA Topic

Shows elements used in a Reference DITA topic.

The &lt;refsyn&gt; element is a special section inside a reference topic. The section often contains syntax or signature content (for example, a command-line utility's calling syntax, or an API's signature). The &lt;refsyn&gt; contains a brief, possibly diagrammatic description of the subject's interface or high-level structure.

** Note:** Writers are not using this Properties table, but we ought to provide a style for it in UH. 

<table cellpadding="4" cellspacing="0" class="simpletable properties" id="properties_6365A0D114374FAC8E8B3B3F2E94FF3D"> 
 <thead class="prophead sthead"> 
  <tr> 
   <th class="proptypehd">Property Type</th> 
   <th class="propvaluehd">Property Value</th> 
   <th class="propdeschd">Property Description</th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr class="property strow"> 
   <td class="proptype stentry">The proptypehd element supports headings for the type column of a properties table. </td> 
   <td class="propvalue stentry">The &lt;propvalue&gt; element indicates one or more values for the current property type. </td> 
   <td class="propdesc stentry"> <p>The &lt;properties&gt; element gives a list of properties for the subject of the current topic, for example whether a class is public or protected. Each property can include the type, value, and a description. The typical rendering is usually in a table-like format. </p> <p>Only the Property Description can (and should) use the para element. </p></td> 
  </tr> 
  <tr class="property strow"> 
   <td class="proptype stentry">The &lt;proptype&gt; element describes the type of the property. </td> 
   <td class="propvalue stentry">The &lt;propvalue&gt; element indicates one or more values for the current property type.</td> 
   <td class="propdesc stentry"> <p>The &lt; propdesc&gt; element is used to provide a short description of the property type and its listed values. </p></td> 
  </tr> 
  <tr class="property strow"> 
   <td class="proptype stentry">Text </td> 
   <td class="propvalue stentry">text</td> 
   <td class="propdesc stentry">text</td> 
  </tr> 
  <tr class="property strow"> 
   <td class="proptype stentry">text</td> 
   <td class="propvalue stentry">text</td> 
   <td class="propdesc stentry">text</td> 
  </tr> 
 </tbody> 
</table>

---

## Section in a Reference

Same as section in other topic types. 
