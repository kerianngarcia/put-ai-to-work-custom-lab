# Section 8.4 Finalize and test the Agentic Workflow | World Forums and Summits Learning Labs 2026

For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). This page is also available as [Markdown](section-8.4-finalize-and-test-the-agentic-workflow.md).

The last settings before we can use the Agentic Workflow need to be made. Go through the following sections of the agentic workflow:
- Define security controls
- Add triggers
- Select channels and status

![](../.gitbook/assets/asset-0786cdd115804b67.png)

1. Define security controls:
a. Define user access: Allow if roles **itil**

![](../.gitbook/assets/asset-8222a0b96c219ef7.png)

b. Define data access:
i. **User identity type**: AI user
ii. **AI user**: itsm.aia.worker

![](../.gitbook/assets/asset-384bb4357ce54d31.png)

2. Activate the OOTB copy trigger, by selecting **Trigger is ON**:

![](../.gitbook/assets/asset-29806c329d8546df.png)

3. Select channels and status: make sure **Engage via the Now Assist Panel** is switched on:

![](../.gitbook/assets/asset-285789d0f048531d.png)

4. You can now **Save and test** the workflow.

In order to test the workflow, you can either create an incident, or use an existing incident in testing mode.
If everything is correct, you will see fields automatically being updated and worknotes being generated about what the AI Agents have been executing:

![](../.gitbook/assets/asset-19a93a5b58e23c60.png)

*Congratulations! You finsihed this lab section and created an Agentic Workflow including a custom AI Agent.*

[PreviousAdd AI Agent to Agentic Workflow](section-8.3-building-ai-agents/add-ai-agent-to-agentic-workflow.md)[NextAppendix](../appendix.md)

Last updated 2 days ago
