# add-ai-agent-to-agentic-workflow.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.3-building-ai-agents/add-ai-agent-to-agentic-workflow.md).
# Add AI Agent to Agentic Workflow
1\. Go back to “Define key requirements” section of the Agentic Workflow:

![](/files/fsUXThpRVdL9yP6fhjER)

2\. We want to add a new AI Agent into the set of AI Agents this workflow has access to. Click “\*\*Create new AI agent\*\*” under “\*\*Add AI agents\*\*”:
![](/files/UhkhZkUxtbq1jbyE8gF4)

3\. Fill in the following:
\
a. \*\*AI agent name\*\*: Determine Assignment Group AI Agent
\
b. \*\*AI agent Description:\*\*
{% code overflow="wrap" %}
```
This agent streamlines incident management by intelligently assigning incidents to the most appropriate support group. It fetches incident data, predicts the best assignment group using an AI skill, and ensures accuracy by requesting user confirmation for low-confidence predictions.
```
{% endcode %}
c. \*\*AI agent role:\*\*
{% code overflow="wrap" %}
```
You specialize in automatically determining and setting the correct assignment group for newly created incidents. You retrieve incident details, utilize a predictive skill to suggest an assignment group with a confidence score, and seek user confirmation if the confidence score is below a predefined threshold before applying the assignment.
```
{% endcode %}
d. \*\*List of steps\*\*:
{% code overflow="wrap" %}
```
1. Use the provided incident number in calling tools in this AI Agent.
2. Predict the Assignment Group for the incident number.
3. Evaluate the confidence score returned by the assignment group selector.
4. If the confidence score is less than 80%, ask the user for confirmation to set the predicted assignment group.
5. If the confidence score is 80% or higher, or if the user confirms, assign the incident to the predicted assignment group using the 'Assign incident to found assignment group' tool.
6. Write a summary of the steps executed in this AI Agent and save it to the work notes of the incident.
```
{% endcode %}
4\. Press “\*\*Save and continue\*\*”
\
5\. When potential duplicates are found, ignore and continue:
![](/files/AIqngW49rfNU51K5k9Bl)

6\. In the tools and information section, we are going to add a new tool which will call our earlier created NASK skill. Click “\*\*Add tool\*\*” -> “\*\*Now Assist skill\*\*”

![](/files/NMXE8dbezfK2ATbbZyTk)

7\. Select your NASK skill in the pop-up window:
![](/files/jeiU7t9yQwmSzECyLYNF)

{% hint style="info" %}
If you can’t find your skill, it is not published in Now Assist skill kit and/or not turned on in the Now Assist Admin Console.\*If you can’t find your skill, it is not published in Now Assist skill kit and/or not turned on in the Now Assist Admin Console.\*
{% endhint %}
8\. Enter the following attributes:
\
a. \*\*Name\*\*: Assignment group selector
\
b. \*\*Tool description\*\*: This tool will predict the right assignment group for the incoming incident
\
c. \*\*Execution mode\*\*: Autonomous
\
d. \*\*Display output\*\*: No
\
Click Add to save the tool to your AI Agent.
\\
\
We need a few more tools, so we can also update the incident with the determined assignment group and we want to be able to write to the work notes of the incident.
\\
\
9\. Click “\*\*Add tool\*\*” -> “\*\*Record operation\*\*”

![](/files/vJgBHa5G7u6XxVxwpe0L)

10\. Fill in the following attributes for the tool
\
a. Name: Update Incident
\
b. Tool description : Update incident
\
c. Input parameters:

|  |  |
| --- | --- |
| ***Input name*** | ***Description*** |
| *incident\_number* | *The incident number* |
| *assignment\_group* | *The sysid of the assignment group* |

d. \*\*Table\*\*: Incident
\
e. \*\*Select operatio\*\*n: Update records
\
f. \*\*Conditions\*\*:
i. Field: Active Operator: is True/False: true
\
ii. Click ‘and’ to add an additional condition
\
iii. Field: Number is {{incident\\_number}}
\\
\
![](/files/DxSQ2F5bgr9sivHyI8u2)
{% hint style="info" %}
You can use the inputs picker to reference variables like the incident number.
{% endhint %}
g. \*\*Field values\*\*:

|  |  |
| --- | --- |
| ***Field*** | ***Value*** |
| *Assignment group* | *{{assignment\_group}}* |

h. \*\*Execution mode\*\*: Autonomous
\
i. \*\*Display\*\* output: No
11\. Click “Add” to save the tool to the AI Agent.
12\. Add another tool to the AI Agent, this time it will be a script to update the worknotes. Click “\*\*Add tool\*\*” -> “\*\*Script\*\*”

![](/files/Ihjb2PGHT143vfAuLQHA)

13\. Fill in the following attributes for the tool
\
a. \*\*Name\*\*: Update incident worknotes
\
b. \*\*Tool\*\* \*\*description\*\*: This tool updates the incident worknotes
\
c. \*\*Input parameters\*\*:

|  |  |
| --- | --- |
| ***Input name*** | ***Description*** |
| *incident\_number* | *The incident number* |
| *worknotes* | *The worknotes to be added to the incident* |

d. \*\*Script\*\*:
{% code overflow="wrap" %}
```javascript
(function(inputs) {
var incidentNumber = inputs.incident\_number;
var worknotes = inputs.worknotes;
var gr = new GlideRecord('incident');
gr.addQuery('number', incidentNumber);
gr.query();
if (gr.next()) {
gr.work\_notes = worknotes;
gr.update();
return {
status: 'success',
incident\_number: incidentNumber,
incident\_sys\_id: gr.getUniqueValue(),
message: 'Work notes updated successfully on incident ' + incidentNumber
};
} else {
return {
status: 'error',
incident\_number: incidentNumber,
message: 'No incident found with number ' + incidentNumber
};
}
})(inputs);
```
{% endcode %}
e. \*\*Execution mode\*\*: Autonomous
\
f. \*\*Display output\*\*: No
14\. Click “\*\*Save and continue\*\*” to go to the next section to define security controls for this AI Agent:
\
a. \*\*Define user access\*\*: Any authenticated user, Save and continue
\
b. \*\*User identity type\*\*: AI user
\
c. \*\*AI user\*\*: itsm.aia.worker1.
![](/files/AOaiKtV3IDVS7YdgJbvz)

d. Click “\*\*Save and continue\*\*”
15\. We don’t need to add any triggers, so click again “\*\*Save and continue\*\*”
\
16\. In the Select channels and status, switch on the “\*\*Engage via the Now Assist Panel\*\*” and make sure the AI Agent is toggled to \*\*Active\*\*.
![](/files/ZWJvnTNtF0ZChhxyASE0)

17\. Save and add the AI agent to the Agentic Workflow.
\
18\. The final result should be that you have an extra AI Agent in your Agentic Workflow:
![](/files/YEjcxJiqMHobIazrE8Z3)
