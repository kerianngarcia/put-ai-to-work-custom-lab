# section-a3-ai-search-set-up.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/appendix/section-a3-ai-search-set-up.md).
# Section A3: AI Search Set-Up
In this section, we will run a quick fix to ensure AI Search is running on your lab instance.
1. Log out of your lab instance.
2. You can open a new private or incognito browser tab
3. n your browser, edit the URL to remove the /external\\_logout.do. You will be presented with a fresh login page.
4. Log into your instance again, this time with the following credentials:
1. User: aislab.admin
2. Password: aislab.admin
5. Navigate to All > Repair Machine Learning Settings Tool.
![](/files/hEsz7pMc029DA05ZUf24)

6. In the pane on the right, you will see “Repair/Reset Machine Learning Settings”. Click “Reset”.
7. After a few minutes, your instance will be ready to go.
8. Use your magic link to log in again as admin.
9. To return to the beginning of the lab, click to go back to Lab Configuration on the right navigation of this guide
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/appendix/section-a3-ai-search-set-up.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
