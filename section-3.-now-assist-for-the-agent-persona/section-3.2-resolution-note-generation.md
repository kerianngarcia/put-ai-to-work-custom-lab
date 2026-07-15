# section-3.2-resolution-note-generation.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.2-resolution-note-generation.md).
# Section 3.2 Resolution Note Generation
1. Within Service Operations Workspace, \*\*return\*\* to the incident from Section 3.1 with the short description, "Versioning…"
2. In the upper-right corner of the incident, locate the \*\*Resolve button\*\* on the right side. Click it to generate resolution notes.
![](/files/vaAxzqhg6ygEh3aUqIoj)

Now Assist reviews the work notes for the current ticket and generates a potential resolution.
3. In the Resolve pop-up window, \*\*select a resolution code\*\* from the drop-down: \*\*Solution provided\*\*.
4. From the resolution notes box, click on the Now Assist icon to generate the resolution notes:
![](/files/tyfyBzNDDTT7yyqYdbuB)
3. Click “\*\*Resolve\*\*” to save it to the ticket.
![](/files/8e9LXO4kja7uYKqGte77)

5. \*\*Select the details tab\*\* of the Incident. Notice that the resolution was copied to the Resolution notes field, and the state of the ticket went from New to Resolved.
{% hint style="info" %}
Bonus: Return to the Incident list and try to resolve ANY in-progress incident. Can you find another way to generate resolution notes? (Hint: look for the sparkles.)
{% endhint %}
Congratulations, you have generated resolution notes and resolved an incident! Please \*\*don't close\*\* your browser or incident tab; we will use it in the next section.
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-3.-now-assist-for-the-agent-persona/section-3.2-resolution-note-generation.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
