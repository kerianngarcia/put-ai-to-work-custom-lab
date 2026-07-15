# section-3.3-knowledge-creation.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.3-knowledge-creation.md).
# Section 3.3 Knowledge Creation
1. On the same “Versioning….” Incident, let's create a Knowledge article. In the upper right corner of the incident, locate the drop-down menu and click "\*\*Create Knowledge\*\*."
![](/files/XsUnaxcwcs9Jpr36mu1j)

{% hint style="info" %}
Tip: In this lab, the Generate Knowledge skill is only available when the incident is in a “Resolved” or “Closed” state. Availability filters can be updated to fit your processes.
{% endhint %}
2. A related record will be created, and the Create New Article template will appear. Select “IT” under Select Knowledge Base, choose ‘Standard' under Select Article Template, then click “\*\*Next\*\*.”
![](/files/Ff2v4xVTWA693hB3plJa)

3. Then an AI draft article pop-up appears; click “Y\*\*es, draft with Now Assist.\*\*"
![](/files/5pEc9W0vNcgHpVdnQrvf)

4. Review the article body. How closely does it match the details in the Incident?
![](/files/EbC1kztV6mrpUN0LKj3a)

\*\*Congratulations,\*\* you have created a knowledge article! Please \*\*don’t close\*\* your browser or the workspace; we’ll continue exploring it in the next section.  
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.3-knowledge-creation.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
