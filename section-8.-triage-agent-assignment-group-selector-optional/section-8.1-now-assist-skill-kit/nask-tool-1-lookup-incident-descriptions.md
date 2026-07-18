# NASK Tool 1: Lookup Incident Descriptions


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


![](../.gitbook/assets/section-8/S8.1-7.png)

No other configuration is needed you can now select continue until the tool is added.
