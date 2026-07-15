# section-3.1-incident-summarization.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.1-incident-summarization.md).
# Section 3.1 Incident Summarization
1. Please return to your lab instance by clicking on the ServiceNow logo in the upper-left corner. Alternatively, y\*\*ou can remove any portal suffix from your instance URL\*\*; for example, my URL looks like this.
![](/files/jb0i3K56KrjgAgGqwiEQ)

2. \*\*Select the Workspace tab\*\* and \*\*select Service Operations Workspace.\*\* Service Operations Workspace provides a consolidated view to help agents manage the life cycles of task records, such as incidents, requests, and walk-ups.
![](/files/1PHBK5Dy5JiZRHq3HfGm)

3. Let’s get to know Service Operations Workspace a little. We are going to search for a specific incident to work with. First, select list view, and then under incidents, select All to get a list of incidents.
![](/files/qDrF44U6xEfBBMMosBPR)

4. In that list view, select the “\*\*Filter\*\*’ button with the Gen AI Sparkle on the upper left side.
![](/files/qBfXqV7zNrAggMmT19it)

5. \*\*Select and copy the following\*\*, and watch Now Assist create the filter for you
> Any incident that has a description that contains Versioning errors
![](/files/jkpCbqTtCTZKrbVh1zJk)

Select the "\*\*Apply\*\*" to process the query
![](/files/EsKiUTTsIlnnQCBNMnZq)

6. \*\*Select the incident link\*\*. Your incident number may be different from the one shown. Now, open that incident in the Service Operations workspace by clicking on the incident number
![](/files/kl44QfHwdV3dVsvsEjZ5)

7. Select the \*\*Summarize button\*\* to use Generative AI to summarize the incident.
![](/files/qjhGoWjDyipHFmV6Rk1C)

The summarization skill analyzes the short description, description, work notes, and related records before generating the issue, SLAs, impacted services, and actions taken up to that point.
As an agent, this is extremely helpful if there are multiple updates to the work notes and the text is dense; when a ticket is assigned to the agent, the Agent must spend 15 minutes reading all the work notes. Instead, they can quickly read the Now Assist summarization.
![](/files/JMLYGJY5PbvFt06ajHpp)

{% hint style="info" %}
Your incident summarization may look slightly different from the screenshot shown below.
{% endhint %}
8. Notice the different icons at the bottom. The thumbs up/down are used to send feedback during re-training of the Now LLM (if the customer has opted into data sharing). You can copy the text to a clipboard as well as regenerate the summary.
9. Let's add the generated summary to our work notes by \*\*selecting the Share button.\*\*
![](/files/GmylUJjLOeI5OhTqXcK1)

10. \*\*Edit the summary by adding a bulleted item\*\* like the one below and then select \*\*Save to work notes\*\*.
{% hint style="info" %}
If the customer has opted in for data sharing, then the edits to the generated response are also sent to the Now LLM for fine-tuning
{% endhint %}
11. Expand the work note activity stream to see that your edits were copied
![](/files/4Snc1ulan3plHPvwFJGE)

{% hint style="info" %}
Bonus: Return to the Incident list and try the summarization skill with ANY in-progress incident. Try it a few times!
{% endhint %}
\*\*Congratulations\*\*, you have created an incident summary and posted it to the work notes! Please don't close the Service Operations workspace or the incident tab; we will use it in the next section
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.1-incident-summarization.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
