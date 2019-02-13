---
title: Extracting Strings for Translating
seo-title: Extracting Strings for Translating
description: Use xgettext-maven-plugin to extract strings from your source code that need translating
seo-description: Use xgettext-maven-plugin to extract strings from your source code that need translating
uuid: 3a475846-6012-424a-b1c6-d41ea3873b52
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: components
discoiquuid: a603cabd-7bc3-4aac-970f-99ceb02b1edd
index: y
internal: n
snippet: y
---

# Extracting Strings for Translating{#extracting-strings-for-translating}

Use xgettext-maven-plugin to extract strings from your source code that need translating. The Maven plugin extracts strings to an XLIFF file that you send for translating. Strings are extracted from the following locations:

* Java source files
* Javascript source files
* XML representations of SVN resources (JCR Nodes)

### Configuring String Extraction {#configuring-string-extraction}

Configure how the xgettext-maven-plugin tool extracts strings for your project.

```xml
/filter { }
/parsers {
   /vaultxml { }
   /javascript { }
   /regexp {
      /files {
         /java { }        
         /jsp { }
         /extjstemplate { }
      }
   }
}
/potentials { }
```

| Section |Description |
|---|---|
| /filter |Identifies the files that are parsed. |
| /parsers/vaultxml  |Configures the parsing of Vault files. Identifies the JCR nodes that contain externalized strings and localization hints. Also identifies JCR nodes to ignore. |
| /parsers/javascript |Identifies the Javascript functions that externalize strings. You do not need to change this section. |
| /parsers/regexp |Configures the parsing of Java, JSP, and ExtJS Template files. You do not need to change this section. |
| /potentials |The formula for detecting strings to internationalize. |

#### Identifying the Files to Parse {#identifying-the-files-to-parse}

The /filter section of the i18n.any file identifies the files that the xgettext-maven-plugin tool parses. Add several include and exclude rules that identify files that are parsed and ignored, respectively. You should include all files and then exclude the files that you do not want to parse. Typically, you exclude file types that do not contribute to the UI, or files that define UI but are not being translated. The include and exclude rules have the following format:

```
{ /include "<i>pattern</i>" }

```

{ /exclude "*pattern*" }

The pattern part of a rule is used to match the names of the files to include or exclude. The pattern prefix indicate whether you are matching a JCR node (its representation in Vault) or the file system.

| Prefix |Effect |
|---|---|
| / |Indicates a JCR path. Therefore, this prefix matches files below the jcr_root directory. |
| &#42; |Indicates a regular file on the file system. |
| none |No prefix, or a pattern that begins with a folder or file name, indicates a regular file on the file system. |

When used within a pattern, the / character indicates a subdirectory and the &#42; character matches all. The following table lists several example rules.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>Example rule</th> 
   <th>Effect</th> 
  </tr> 
  <tr> 
   <td><span class="code">{ /include "*" }</span></td> 
   <td>Include all files.</td> 
  </tr> 
  <tr> 
   <td><span class="code">{ /exclude "*.pdf" }</span></td> 
   <td>Exclude all PDF files.</td> 
  </tr> 
  <tr> 
   <td><span class="code"> { /exclude "*/pom.xml" }</span></td> 
   <td>Exclude POM files.</td> 
  </tr> 
  <tr> 
   <td><code class="code">{ /exclude "/content/*" }
      { /include "/content/catalogs/geometrixx/templatepages" }
      { /include "/content/catalogs/geometrixx/templatepages/*" }</code></td> 
   <td><p>Exclude all files below the /content node.</p> <p>Include the /content/catalogs/geometrixx/templatepages node.</p> <p>Include all child nodes of /content/catalogs/geometrixx/templatepages.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Extracting the Strings  {#extracting-the-strings}

no POM:

```shell
mvn -N com.adobe.granite.maven:xgettext-maven-plugin:1.2.2:extract  -Dxgettext.verbose=true -Dxgettext.target=out -Dxgettext.rules=i18n.any -Dxgettext.root=.
```

With POM: Add this to POM:

```xml
<build>
    <plugins>
        <plugin>
            <groupId>com.adobe.granite.maven</groupId>
            <artifactId>xgettext-maven-plugin</artifactId>
            <version>1.1</version>
            <configuration>
                <rules>i18n.any</rules>
                <root>jcr_root</root>
                <xliff>cq.xliff</xliff>
                <verbose>true</verbose>
            </configuration>
        </plugin>
    </plugins>
</build>
```

the command:

```shell
mvn xgettext:extract
```

### Output Files {#output-files}

* `raw.xliff`: extracted strings
* `warn.log`: warnings (if any), if `CQ.I18n.getMessage()` API is used incorrectly. These always need a fix and then a re-run.

* `parserwarn.log`: parser warnings (if any), e.g. js parser issues
* `potentials.xliff`: "potential" candidates that are not extracted, but might be human readable strings that need translation (can be ignored, still produces a huge amount of false positives)
* `strings.xliff`: flattened xliff file, to be imported into ALF
* `backrefs.txt`: allows for quick lookup of source code locations for a given string

