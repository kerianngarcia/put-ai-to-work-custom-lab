# nask-tool-2-lookup-assignment-groups.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.1-now-assist-skill-kit/nask-tool-2-lookup-assignment-groups.md).
# NASK Tool 2: Lookup assignment groups
Following the previous steps to add another script tool, this time name it \*\*assignmentgroup\*\*:
```javascript
(function runScript(context) {
var groups = [];
// Resolve the sys\_id of the 'itil' group type (avoid hardcoding)
var itilTypeSysId = '';
var typeGR = new GlideRecord('sys\_user\_group\_type');
typeGR.addQuery('name', 'itil');
typeGR.setLimit(1);
typeGR.query();
if (typeGR.next()) {
itilTypeSysId = typeGR.getUniqueValue();
}
// Query: active=true AND (type IS EMPTY OR type CONTAINS itil)
var gr = new GlideRecord('sys\_user\_group');
gr.addActiveQuery();
var qc = gr.addNullQuery('type');
if (itilTypeSysId) {
qc.addOrCondition('type', 'CONTAINS', itilTypeSysId);
}
gr.query();
while (gr.next()) {
groups.push({
sys\_id: gr.getUniqueValue(),
name: gr.getValue('name') || '',
description: gr.getValue('description') || ''
});
}
return JSON.stringify(groups);
})(context);
```
Configuration should now look like this:

![](/files/FZAhsXV6skdvUIsYYqSI)

Again, no other configuration is needed select continue until you have added the tool. Your flow should look similar to the image below. The exact order does not matter as both scripts will execute prior to the prompt.

![](/files/Lge18iI9YOuIvm0gvtLT)

To control, check back with your prompt, the {{inputs}} should be blue indicating that they are matched with the tools you have added.

![](/files/IE0p9UKwEE9soOZRTYON)

---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.1-now-assist-skill-kit/nask-tool-2-lookup-assignment-groups.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
