# section-2.3-wrap-your-agent-in-an-agentic-workflow.md

## section-2.3-wrap-your-agent-in-an-agentic-workflow.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-2.-building-agents-and-use-cases/section-2.3-wrap-your-agent-in-an-agentic-workflow.md).

## Section 2.3 Wrap your Agent in an agentic workflow

1. Click the \*\*Create and Manage\*\* tab
2. Under the \*\*Agentic workflows\*\* tab, click \*\*New\*\*
3. Click on the “\*\*Generate details\*\*” in the \*\*Define key requirements\*\* page, copy and paste this into the dialog

> This workflow will be the “Incident Solution Agent workflow” . This use case provides recommendations to resolve incidents”. Provide a recommendation on how to resolve a given incident using an easy-to-follow numbered step-by-step list format

4. Click on “\*\*Generate\*\*.” Scroll down and see how it's filled in the fields for you!
5. Click \*\*Recommend\*\* button, then find the AI Agent you created previously&#x20;


![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-7455f76989c141.png)
6. Click “\*\*+\*\*” button under \*\*Add AI agent\*\*
7. You will get prompted for possible duplicates. Click “\*\*Ignore and continue\*\*. “In Define user access, click “Save and continue” on the following two steps
8. Select “\*\*Any Authenticated user\*\*’ from the User access drop-down
9. Select the \*\*Dynamic user\*\*, search and select ‘\*\*itil\*\*’ and “\*\*admin\*\*” from the approved roles
10. In the \*\*Add Trigger\*\* page, click \*\*Add Trigger\*\*, and fill in the following fields:
11. \*\*Select Trigger\*\*: Created
12. \*\*Trigger name:\*\* “\[Your initials] Incident Created and Objective: “Help me resolve $(number)”
13. Trigger is toggled ‘\*\*on\*\*’
14. \*\*Table\*\*: “Incident”
15. \*\*Choose\*\* to "Run As User"
16. \*\*Conditions\*\*: Active is True AND Assigned to is not empty
17. \*\*Sys\\\_user\*\*: “Assigned to \[task]”
18. \*\*Channel\*\*: “Now Assist panel”
19. \*\*Show alert to users\*\*: “no”
20. Click “Save and continue”
21. Next, in the \*\*Select channels and status\*\*, you can enable Agents to communicate via the Now Assist for Virtual Agent (via Employee center, or Service Portal), but for this example, we will NOT change the selection.
22. In the Communicate, this AI agent’s process to users, click on “\*\*Generate messages\*\*” letting Now assist create them for you, when the agent is ‘thinking’ and when it has completed its task
23. Click Add
24. Click \*\*Save and Continue\*\*
25. On the \*\*Select channel and status page\*\*, make sure the Now Assist Panel Display toggle is set to \*\*On\*\*
26. Click \*\*Save and Test\*\* Now let’s test your new workflow! Let’s continue to use the same incident record as we’ve used previously – INC0010248. In the Task box enter

> Help me resolve INC0010248 \*\*Click Continue to Test Chat response\*\*
