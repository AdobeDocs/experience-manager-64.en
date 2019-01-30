---
title: Create accessible complex tables in HTML5 forms
seo-title: Create accessible complex tables in HTML5 forms
description: null
seo-description: Learn how to create accessible tables in HTML5 forms. 
uuid: dac3f8a6-fe78-4fc2-a258-8240ba7b636d
acrolinxdate: 2016-05-31T06 47 23.834-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/accessible_tables_admin_5e12de0b318c6865_2109_report.xml
acrolinxsentences: 12
acrolinxwords: 322
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: d4127590-3da4-4f97-91fe-e035c0275ccf
isreadyforlocalization: false
lastpublishqadate: 2015-08-18T08 14 13.593-0400
index: y
internal: n
snippet: y
---

# Create accessible complex tables in HTML5 forms{#create-accessible-complex-tables-in-html-forms}

The default implementation of tables in HTML5 Forms uses HTML DIV elements to render a table. Rendering involves using ARIA roles to satisfy the accessibility requirements.

To avoid accessibility issues with screen-readers which do not fully support the ARIA-roles used with data-tables, HTML5 Forms provides an alternate rendition for the tables. These tables are based on the new table format introduced in Designer which also supports:

* Row Headers
* Row-span

To use the new format in HTML5 Forms, mark the table as complex. To mark the table as complex, add `extras` tag in the XML source of table subform as follows:   
`&lt;/extras&gt;  
&lt;text name="complexTable"&gt;1&lt;/text&gt;  
</extras>`

The tables which are marked as *complexTable* follow the native HTML rendition, and provide better accessibility support for certain screen readers.  To create a row span, select consecutive cells of a table in the same column, right-click on the selection, and then click **Merge Cells**.

***Note:** Creating a row-span works for leftmost cells only.*

To mark a row as row header, select all cells in the row, right-click on the selection, and then click **Mark Header**.

To mark a cell as column header, select any cell in the column, right-click on the selection, and then click **Mark Header**.

Limitations in new *AccessibleTable* format:

* Lack of support for grow-able fields if rowspan is used in the table
* No support for nested tables (tables within table cells)
* Support for rowspan is limited to the header rows and header cells
* Support is limited to regular tables
* No support for data prefills in tables with rowspan &gt; 1

