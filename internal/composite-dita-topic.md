---
uuid: 8fb48c26-0b8b-4e6c-93e8-2fa64bc52baa
index: y
internal: n
snippet: y
translate: y
---

# Composite DITA Topic

---

## Composite DITA Topic

We do not often use the Composite <dita> topic, but we might begin using them if they look better in Unified Help. This <dita> element lets us combine several topic types (Concept, Task, Reference) on a single page. These nested elements will be structurally identical to the separate files of the same type (Concept, Task, or Reference). For example, the available elements in a <task> element nested in this file will be the same as the available elements in a stand-alone Task file.

<para> in the <body> element.

<bodydiv> element. Not used often. Its purpose is to contain informal blocks of information within the body of a topic. As such, it does not contain an explicit title to avoid enabling the creation of deeply nested content that would otherwise be written as separate topics. Content that requires a title should use a section element or a nested topic.

The bodydiv element may nest itself, which means that it may be used by specializers to create structured information within a body. Another common use case for the bodydiv element is to group a sequence of related elements for reuse, so that another topic may reference the entire set with a single conref attribute.

---

## Concept Title

A nested <concept> in a <composite> element.

<paragraph> in a <conbody> element.

---

## Task Title

A nested <task> in a <composite> element.

<para> in a <context> element. The <context> element lets you add conceptual information before the <steps> element.

1. **`Step element with a Command element in the Taskbody in the Task element.`
1. **`Step element` 

   Step Result

