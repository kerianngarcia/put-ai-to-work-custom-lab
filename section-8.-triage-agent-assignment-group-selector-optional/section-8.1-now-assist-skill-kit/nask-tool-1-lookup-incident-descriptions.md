# NASK Tool 1: Lookup incident descriptions | World Forums and Summits Learning Labs 2026

## nask-tool-1-lookup-incident-descriptions.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.1-now-assist-skill-kit/nask-tool-1-lookup-incident-descriptions.md).

## NASK Tool 1: Lookup incident descriptions

Select the + symbol between start and your skill prompt add a tool node and tool type script.\
Give your script the exact name \*\*LookupIncident\*\* and write your own script, copy in the script below, ensure to not get any extra line breaks.

```javascript
(function runScript(context) {
var incidentNumber = context.getValue('incidentnumber');
var result = {
short\_description: '',
description: '',
found: false
};
if (!incidentNumber) {
gs.warn('[IncidentLookup] No incident\_number provided');
return result;
}
var gr = new GlideRecord('incident');
gr.addQuery('number', incidentNumber);
gr.setLimit(1);
gr.query();
if (gr.next()) {
result.short\_description = gr.getValue('short\_description') || '';
result.description = gr.getValue('description') || '';
result.found = true;
} else {
gs.warn('[IncidentLookup] No incident found for number=' + incidentNumber);
}
return result;
})(context);
```

Your configuration should now look like this:<br>


![Screenshot](https://raw.githubusercontent.com/kerianngarcia/put-ai-to-work-custom-lab/main/.gitbook/assets/recovered-b46cdcf6a7eef7.png)

No other configuration is needed you can now select continue until the tool is added.
