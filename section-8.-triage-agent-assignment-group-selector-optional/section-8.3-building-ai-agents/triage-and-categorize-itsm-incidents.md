# Triage and Categorize ITSM Incidents

## triage-and-categorize-itsm-incidents.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.3-building-ai-agents/triage-and-categorize-itsm-incidents.md).

## Triage and Categorize ITSM Incidents

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-83e03ac9f14e97.png)

We are going to check how the out-of-the-box (OOTB) Agentic Workflow “Triage and categorize ITSM incidents” is built, how we can test it and also how we can modify the OOTB experience. 1. Open AI Agent Studio (All > AI Agent Studio > Overview). You will be taken to the AI Agent Studio Home page, which is your one-stop-shop for building, maintaining and testing AI Agents.\\

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-db710041f70c1d.png) 2. Locate the tab “Create and manage” and click this.\
3\. Make sure that you have the tab “Agentic Workflows” selected.

4\. Locate the “Triage and categorize ITSM incidents” workflow and open this. You will notice this is an OOTB workflow, as it is marked to be read-only. 5. Check how the agentic workflow is constructed:\
a. It has name, description and a list of steps;\\

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-c748c8485c7e8b.png) b. There are three AI Agents underneath this workflow.\
c. Feel free to open up one of the AI Agents, and check how they have been setup. Also these single AI Agents will be marked read-only, indicating they are OOTB AI Agents provided by the ITSM content pack for AI Agents.

6\. Click “Continue”, to go to the next section of the Agentic Workflow setup\\

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-c7ee71670a4b1a.png) 7. You will be taken through the security controls, triggers and channels and status. We won’t change anything here, and continue all the way to the end of the settings:

8\. Now we click “Save and Test” which will take us to the testing console. Enter an incident number and click “Continue to Test Chat Response”:

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-f0a8236461a7cd.png)

9\. The agentic workflow is kicked off, and you will see the AI Agents being fired of by the agentic workflow:

![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-02f2d5a2af7ba8.png)
