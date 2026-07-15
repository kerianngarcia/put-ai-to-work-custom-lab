# duplicate-ootb-agentic-workflow.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.3-building-ai-agents/duplicate-ootb-agentic-workflow.md).
# Duplicate OOTB Agentic Workflow
1\. Open the Agentic Workflow again via the “Create and manage” tab, OR when still in the testing console click “Edit workflow”
\
2\. On the right side of the screen, you will see a button with three vertical dots, click this to Duplicate the agentic workflow:

![](/files/nyqFsJqyGectCkwZaMEv)

3\. Give your copy a name – use your imagination J
\
4\. Change the description so it includes the fact that we want to determine the assignment group:
{% code overflow="wrap" %}
```
This agentic workflow enables fulfillers to identify the category, subcategory, service, offering, configuration item and assignment group for an incident automatically, and finally link a major incident or problem.
```
{% endcode %}
5\. Change the list of steps as well, so that it includes an extra AI Agent to be called in the workflow:
{% code overflow="wrap" %}
```
IMPORTANT:
- The incident number is the only input required from the fulfiller — no other details are needed.
- \*\*All four AI Agents must be executed\*\* — none should be skipped.
- Execute all AI Agents in parallel, since there are no dependencies between them.
- \*\*Ensure each Agent runs fully and independently\*\*, even if previous Agents complete early or produce empty results.
1. Categorize the Incident
- Execute the "Categorize ITSM Incident AI Agent" agent.
- Purpose: Identify the appropriate category and sub-category based on incident details.
2. Classify Service, Offering, and CI
- Execute the "Classify Service and CI AI Agent" agent.
- Purpose: Determine the correct service, service offering, and configuration item (CI) for the incident.
3. Determine Assignment Group
- Execute the "Determine Assignment Group AI Agent" agent.
- Purpose: Determine the correct assignment group for the incident.
4. Link Major Incident or Problem
- Execute the "Link Major Incident or Problem AI Agent" agent.
- Purpose: Check for any related Major Incidents or Problems and link them to the current incident if a match is found.
```
{% endcode %}
6\. Create a new Version (version 2).

![](/files/XZ15oNFFknfcSNbWcYeI)

7. Click “Save and continue”
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.3-building-ai-agents/duplicate-ootb-agentic-workflow.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
