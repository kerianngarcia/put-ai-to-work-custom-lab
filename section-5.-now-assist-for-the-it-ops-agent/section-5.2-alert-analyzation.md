# section-5.2-alert-analyzation.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-5.-now-assist-for-the-it-ops-agent/section-5.2-alert-analyzation.md).
# Section 5.2 Alert Analyzation
Now Assist for ITOM can analyze a group of alerts and consider multiple factors, leading to an analysis that can significantly reduce the time an operator needs to spend reviewing each alert in the group and understanding what happened and how it relates to other alerts in the group.
In this part of the lab, you will use Now Assist for ITOM as an operator to gain hands-on experience with what an operator would see when analyzing individual alerts and groups of alerts.
1. Find the alert with the number \*\*Alert0010002\*\*. \*\*Click anywhere in the alert's Description\*\*. It opens the details panel.
![](/files/6jm3ecm4QKGdmGZcZWVT)

2. Click on the \*\*Analyze button\*\*. It may take a few moments to return, as Now Assist for ITOM is analyzing the group of alerts.
![](/files/qpY6s6l31S3EU0RAJBwP)

3. Once the result is returned, the analysis for the alert group is displayed. Read through it to see an example of the type of analysis Now Assist for ITOM will perform to help an operator quickly understand what happened and identify what to look for to fix the issue.
![](/files/shUUW8ecBSxSYuyJAsd3)

\*\*Congratulations,\*\* you have completed the Now Assist for ITOM portion of the lab!
  
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-5.-now-assist-for-the-it-ops-agent/section-5.2-alert-analyzation.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
