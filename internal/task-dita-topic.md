---
uuid: 58ad754a-a8b7-4318-84b1-bd949a46ac0d
index: y
internal: n
snippet: y
translate: y
---

# Task DITA Topic

The short description (<shortdesc>) element occurs between the topic title and the topic body, as the initial paragraph-like content of a topic, or it can be embedded in an abstract element. The short description, which represents the purpose or theme of the topic, is also intended to be used as a link preview and for searching.

The &lt;context&gt; element provides background information for a task. This information helps the user understand what the purpose of the task is and what they will gain by completing the task. This section should be brief and does not replace or recreate a concept topic on the same subject, although the context section may include some conceptual information.

1. To create a task, click **[!UICONTROL Insert]** > **[!UICONTROL Topic Reference]**.
1. `The <step> element represents an action that a user must follow to accomplish a task. Each step in a task must contain a command <cmd> element which describes the particular action the user must do to accomplish the overall task.`

   The &lt;stepresult&gt; element provides information on the expected outcome of a step. If a user interface is being documented, the outcome could describe a dialog box opening or the appearance of a progress indicator. Step results are useful to assure a user that they are on track, but should not be used for every step as this quickly becomes tedious. Add screen shots only in the &lt;stepresult&gt;, using an &lt;image&gt; element inside a &lt;p&gt; (REQUIRED).

1. `The <cmd> element specifies a command, which is a required element inside the <step> element. It provides the active voice instruction to the user for completing the step, and should not be more than one sentence. If the step needs additional explanation, place the explanation in an <info> element following the <cmd>.` 

   The &lt;info&gt; element occurs inside a &lt;step&gt; element to provide additional information about the step. 

1. `Here is info about the <choices> element that can follow the <cmd>.`

    1. &lt;choices&gt; element. describes one way that the user could accomplish the current step.    
    1. &lt;choices&gt; element    
    1. more choices

1. `Here is info about <choicetable> following the <cmd>:` 

   | Option |Description |
   |---|---|
   | **choice option** | These are series of optional choices available within a step of a task. Don't use a para here.  |
   | **choice option** |description |
   | **choice option** |description |

1. `Here is info about <itemgroup> following the <cmd>:`

   The &lt;itemgroup&gt; element can be used to sub-divide or organize elements that occur inside a list item, definition, or parameter definition. 

1. `Step with substeps:`

    1. `<substep> following a numbered step.`    
    1. `Substep`    
    1. `Substep`     
    
       Step example &lt;stepxmp&gt;

1. `Final Step.`

