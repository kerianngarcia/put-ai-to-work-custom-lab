# section-2.4-optional-build-an-ai-agent-that-checks-outages-in-similar-incidents.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-2.-building-agents-and-use-cases/section-2.4-optional-build-an-ai-agent-that-checks-outages-in-similar-incidents.md).
# Section 2.4 - OPTIONAL- Build an AI Agent that checks outages in similar incidents
First, let’s create an outage in incident INC0010248.
1. Open the incidents table (\*\*All > Incident > All)\*\*
2. Search for I\*\*NC0010248\*\* and open it
3. Scroll down to the bottom of the page, and select the \*\*Outages tab.\*\* If the tab is not visible, ask your instructor how you can add it as a related list.
4. Click \*\*New\*\*
![](/files/0045KK2XEFW2duhfg5p9)

5. In the \*\*Outage New record page\*\*, select \*\*Degradation\*\* from the Type list, and fill in the T\*\*ask number\*\* field with the incident number \*\*“INC0010248\*\*”:
![](/files/oR8XohMTggMrx0gXaT1W)

6. Click \*\*Submit\*\*
7. Click the \*\*Update\*\* button to return to the incidents list
Now, we need to switch scope to “\*\*Platform AI Agents and Skills\*\*”.
8. Click the Application Scope icon at the top of the page
![](/files/06hsPU8jPbBkNWSSv30e)

9. Select \*\*Application scope\*\*: Global, and then filter for and select \*\*Platform AI Agents and Skills.\*\*
{% hint style="info" %}
NOTE: If you can’t find the scope “Platform AI Agents and Skills”. Please click to check \*\*Appendix Section A4: Application Scope at the end of the document.\*\*
{% endhint %}
Now let’s go to \*\*Flow Designer\*\* and modify the existing “Get Similar records” action and have it return outages found in similar incidents as well.
10. Open Flow Designer (\*\*All > Flow Designer\*\*) - this will open Flow Designer in a new tab
11. Under the Actions tab, find “\*\*Get Similar Records\*\*” and open it. \*\*DO NOT OPEN “Get Similar Incident Records”\*\*
![](/files/6jBtTbZ8DP6L10AYSZZJ)

12. Copy the action by clicking on the three dots (...) in the top right of the page
![](/files/nQpNhMyMkPFt8J9FSc5a)

13. Change the action name to “\*\*\[Your initials] Get Similar Records and Outages”\*\* and be sure that \*\*“Platform AI Agents and Skills”\*\* is the Application selected.
![](/files/WgmeB3iyzylMQTYxcKPR)

14. Click \*\*Copy\*\*
15. On the left, click S\*\*cript Step\*\*
![](/files/UZ6XmFfO7RncW2f7tdY5)

16. Please use the script text box below to copy/paste
```
(function execute(inputs, outputs) {
var groupSkillId;
var action\_skill\_id;
var recSysId = UXCGAFUtil.getSysId(inputs.table, 'number', inputs.record\_number);
// Map the skills based on table
var tableMapping = {
'incident': { group: UXCConstants.ITSM\_GROUPING, action: UXCConstants.ITSM\_ACTION\_STRATEGY },
'sn\_customerservice\_case': { group: UXCConstants.CSM\_GROUPING, action: UXCConstants.CSM\_ACTION\_STRATEGY },
'sn\_hr\_core\_case': { group: UXCConstants.HR\_GROUPING, action: UXCConstants.HR\_ACTION\_STRATEGY }
};
var config = tableMapping[inputs.table];
if (config) {
groupSkillId = config.group;
action\_skill\_id = config.action;
}
var grpSysId = UXCGAFUtil.getGroupSysId(recSysId, inputs.table, inputs.record\_number, groupSkillId);
var recs = grpSysId ? UXCGAFUtil.getGAFSimilarRecs(grpSysId, groupSkillId) : UXCGAFUtil.getRecReferences(inputs.table, recSysId);
outputs.references = JSON.stringify(recs);
// Extract IDs - Handling potential casing issue (sys\_id vs sys\_Id)
var sysIds = [];
if (Array.isArray(recs)) {
recs.forEach(function(item) {
var id = item.sys\_id || item.sys\_Id;
if (id) sysIds.push(id.toString());
});
}
outputs.sys\_ids = JSON.stringify(sysIds);
if (sysIds.length === 0) {
outputs.outage\_details = "No related records found.";
return;
}
// --- Optimized Outage Retrieval ---
var reportLines = [];
var outageGR = new GlideRecord('cmdb\_ci\_outage');
outageGR.addQuery('task\_number', 'IN', sysIds); // Batch query is much faster
outageGR.orderBy('task\_number');
outageGR.query();
var currentTask = "";
while (outageGR.next()) {
// Grouping header in the report
if (currentTask != outageGR.task\_number.getDisplayValue()) {
currentTask = outageGR.task\_number.getDisplayValue();
reportLines.push("\n--- Outages for Task: " + currentTask + " ---");
}
reportLines.push(" ----------------------------------------");
reportLines.push(" Outage: " + outageGR.getDisplayValue());
reportLines.push(" Begin: " + outageGR.begin.getDisplayValue());
reportLines.push(" End: " + outageGR.end.getDisplayValue());
reportLines.push(" Description: " + (outageGR.description || "No description"));
reportLines.push(" ----------------------------------------");
}
outputs.outage\_details = reportLines.length > 0 ? reportLines.join('\n') : "No outages found for these records.";
})(inputs, outputs);
```
17. In the Output Variables window (below the Script window), delete both existing variables, and create the following:
![](/files/lckkMcRtD0AoRKAYiJym)

18. On the left, click \*\*Outputs\*\*, then click \*\*Edit Outputs\*\*
19. Delete the message output (confirm the popup window)
20. Change the label from “References” to “similar records”
21. Click Create Output with the label “outage details”, the name “outage\\_details”, and the type String
![](/files/tdnK13fFsBOB82AnvLfU)

22. Click on \*\*Exit Edit Mode\*\*
23. Drag and drop the script step variables from the right into their corresponding boxes in the middle, like this:
![](/files/o7qaGTsD6ydgy1dQpu3K)

24. Click \*\*Test\*\*
25. Type “incident” into the type field, and “\*\*INC0010248\*\*” into the record\\_number field, then click \*\*Run Test\*\*
26. When it appears, click “Your test has finished running. View the Action execution details.”
Your results should look like:
![](/files/MnoN80B9YlWnbz0II0pc)

27. Return to the previous window, and click Save, then Publish
28. Close the Workflow Studio browser tab, and return to the main lab browser tab
29. Let’s change the Application Scope back to Global
![](/files/g71LI9JWQdU9iLZZM17I)

Now let’s create another Flow Action for creating an outage.
  
30. Open Flow Designer (All > Flow Designer) and search for “outage” under the Actions tab.
![](/files/YyLwqQnRawTngqQdjADf)

31\. Click on Create Outage and copy the action, name it “\[Your Initials] Create outage.”
![](/files/kxbC216noZJbVXvMzJAn)

32. Delete the following inputs:
1. “configuration item”
2. “type”
3. “begin”
![](/files/21dIYLlSMLrhs5T0qZ9G)

33. On the left, click \*\*Script Step\*\* and delete the following variables:
1. “cmdbCI”
2. “type”
3. “begin”
![](/files/durIpPy39MGumLJM0D66)

34\. Replace the existing script with this one:
```
(function execute(inputs, outputs) {
var parentTable = GlideDBObjectManager.get().getBase(inputs.source.getRecordClassName());
var outage = new GlideRecord("cmdb\_ci\_outage");
outage.initialize();
//outage.setValue("cmdb\_ci", inputs.cmdbCi);
outage.setValue("type", "Degradation");
//outage.setValue("begin", inputs.begin);
outage.setValue("short\_description", "degradation");
if (parentTable == "task")
outage.setValue("task\_number", inputs.source.getUniqueValue());
outputs.OutageRecord = outage.insert();
// Add this line to get the outage number as a string
outputs.outagerecordnumber = outage.getValue("number");
})(inputs, outputs);
```
35. Then add an output variable with the following values:
1. Label: “OutageRecordNumber”
2. Name: outagerecordnumber
3. Type: String
4. Mandatory: True
![](/files/iPnUbob9yYyZ0nfVy1Bd)

36. On the left, click Outputs, then Edit Outputs, then Create Output
37. Edit the new Output with the following values:
1. Label: “Outage Number”
2. Name: “outage\\_number”
3. Type: String
![](/files/1PbTnrDG5oud3L9mwmkd)

38. Click Exit Edit Mode
39. Drag the “OutageRecordNumber” Script variable to the Outage Number Action Output box.
![](/files/AcguS9yLnhstg0hZm3Sj)

40. Click Test
41. Select “INC0000001” as the Source Record, and click Run Test
42. When it appears, click “Your test has finished running. View the Action execution details.”
Your results should look like:
![](/files/NeUoeOAuxanfB0zDAmLB)

43. Return to the previous window, and click Save, then Publish
44. Close the Workflow Studio browser tab, and return to the main lab browser tab
\*\*Section 2.4.2 - Extra - Build the AI Agent\*\*
Now, let's open AI Agent Studio and build another AI agent. This time, we will duplicate the previously created AI agent “Incident Solution Recommender”.
1. Open AI Agent Studio (All > AI Agent Studio > Overview)
2. Click the Create and Manage module
3. Click on the AI Agent tab, then select the "Incident Solution Recommender” and on the form, use the button at the top right to duplicate the agent

![](/files/ULY4Vs9GuiwMqNhsjI3J)

4. Click Duplicate when prompted
5. Update the fields with the following values:
1. Name: “Incident Solution Recommender with Outage Check”
2. Instructions (include the numbering):
```
1. Get details of an incident.
2. Get current similar incidents. The table name is "incident".
3. Using the incident's short description, search the Knowledge Base for relevant articles.
4. Based on the similar incidents' details, the kb articles returned, and the outages found in similar incidents, add resolution steps, along with any relevant similar incidents, knowledge articles, and outages found in similar incidents, to the Additional Comments section of the incident record. When adding a comment, make sure to include a qualifier that states the comment was added by an AI Agent. Your output message to the user should be formatted to be easy to read with new line characters in a list format. Also provide your reasoning for recommending these steps.
5. If outages are found in similar incidents, ask the user if they want to create an outage for the current incident being resolved. If no outages exist in similar incidents, do not mention anything back to the user.
6. If an outage record was created successfully, please add the outage number to the Additional Comments section of the incident record.
7. End.
```
6. Click Save and continue
7. Click on the existing “Get Similar Incident Records” flow action and change the name to “Get Similar Incident Records and Outages”
8. Select “\[Your Initials] Get Similar Records and Outages” as the flow action.![](/files/kF0PoNSZgiPSQqkAtjxk)

9. Click \*\*Save\*\*
10. Click the Add tool dropdown list, and select Flow action, then complete the fields with the following information:
1. Name: “Create Outage”
2. Description: “Create an outage for the task/record being resolved”
3. Flow action: \[Your initials] Create Outage
4. Execution mode: Autonomous
5. Display output: Yes
6. Output Transformation strategy: Concise.
11\. Click Add-Your tools should look like this:
![](/files/nmQjNBCPPoLnnDmUrhMT)

12\. Click \*\*Save and Continue\*\*
13\. On the Define Availability page, make sure the Status toggle is set to On
14\. Click \*\*Save and Test\*\*
\*\*Now let’s test the agent!\*\*
· In the Task box enter “INC0010004” and click Start test.
· At the end of the test, check the comments in INC0010004:
![](/files/5UXiOBlnKtIRToQRrVy1)

Congratulations! You have completed the advanced part of the lab!
17. In the Output Variables window (below the Script window), delete both existing variables, and create the following:
![](/files/U9QGw9kmzEd6qFfYnCfG)

18. On the left, click \*\*Outputs,\*\* then click \*\*Edit Outputs\*\*
19. Delete the message output (confirm the pop-up window)
20. Change the label from “References” to “similar records.”
21. Click Create Output with the label “outage details”, the name “outage\\_details”, and the type String.
![](/files/EDZvsEGqbhn0Mg8C0ujj)

22. Click on \*\*Exit Edit Mode\*\*
23. Drag and drop the script step variables from the right into their corresponding boxes in the middle, like this:
![](/files/VMlYS2BEYZImrQ74P5Tb)

24. Click \*\*Test\*\*
25. Type “incident” into the type field, and “INC0010004” into the record\\_number field, then click \*\*Run Test\*\*
![](/files/F6a5DKSyvpJDF7w9gff1)

26. When it appears, click “Your test has finished running. View the Action execution details.” Results should look like this.
![](/files/1RRwk27nRo51md8UI7y7)

27. Return to the previous window, and click \*\*Save, then Publish\*\*
28. Close the Workflow Studio browser tab, and return to the main lab browser tab
29. Let’s change the Application Scope back to Global
![](/files/7ACGJBk1kt834pIZN8WN)

Now let's create another Flow Action for creating an outage.
30. Open Flow Designer (\*\*All > Flow Designer\*\*) and search for “outage” under the Actions tab.
![](/files/dHEorDUypauK4JZU7Kqb)

31. Click on \*\*Create Outage\*\* and copy the action, name it “\[Your Initials] Create outage”
![](/files/ZxQc36Sa2i6lNMPR3n81)

32. Delete the following inputs:
1. “configuration item"
2. “type”
3. “begin”
![](/files/vrmqFsQGetvk2rGGq7ut)

33. On the left, click \*\*Script Step\*\* and delete the following variables:
1. "cmdbCI"
2. “type”
3. “begin”
![](/files/xc3exZiDyPH8uTfeJ4qu)

34. Replace script with this one:
```
(function execute(inputs, outputs) {
var parentTable = GlideDBObjectManager.get().getBase(inputs.source.getRecordClassName());
var outage = new GlideRecord("cmdb\_ci\_outage");
outage.initialize();
//outage.setValue("cmdb\_ci", inputs.cmdbCi);
outage.setValue("type", "Degradation");
//outage.setValue("begin", inputs.begin);
outage.setValue("short\_description", "degradation");
if (parentTable == "task")
outage.setValue("task\_number", inputs.source.getUniqueValue());
outputs.OutageRecord = outage.insert();
// Add this line to get the outage number as a string
outputs.outagerecordnumber = outage.getValue("number");
})(inputs, outputs);
```
35.