# Duplicate OOTB Agentic Workflow

## duplicate-ootb-agentic-workflow.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.3-building-ai-agents/duplicate-ootb-agentic-workflow.md).

## Duplicate OOTB Agentic Workflow

1\. Open the Agentic Workflow again via the “Create and manage” tab, OR when still in the testing console click “Edit workflow”\\

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-b817c3172db88f.png) 2. On the right side of the screen, you will see a button with three vertical dots, click this to Duplicate the agentic workflow:

3\. Give your copy a name – use your imagination J\
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

6\\. Create a new Version (version 2).

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-cb61b5586fc10f.png)

7. Click “Save and continue”
