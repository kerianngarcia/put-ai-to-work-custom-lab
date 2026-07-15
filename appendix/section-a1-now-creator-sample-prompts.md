# section-a1-now-creator-sample-prompts.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/appendix/section-a1-now-creator-sample-prompts.md).
# Section A1: Now Creator Sample Prompts
\*\*Text to Flow Examples\*\*
> Anytime an incident record is created. Wait 1 minute. If the incident priority equals high, then send a Teams message.
> Whenever a change request is created or updated where the model is an unauthorized demo, do the following: Apply change approval policy. If approvals are approved or skipped, update change request record as approved. If not, update change request record as rejected. Evaluate the model once again. If rejected, send an email. Wait until active is false, disregard change request approvals, and evaluate the change model.\
> \
> When an expense claim is submitted, email the user that the claim has been received. Then, ask their manager for approval. If the manager approves, change the status to approved and inform the user via email. If rejected, send an email.
\*\*Text To Code Examples\*\*
```
//write a function which takes an input in Celsius and returns the value in Fahrenheit
```
```
//validate that the variable emails is a string and has allowed syntax
```
```
//if the syntax is allowed, return true
```
```
//return all critical incidents created in the last 6 months
```
```
// function to query the incident table to find the latest record created in the last quarter by the current user
```
```
// If email is provided, ensure it is from my domain.
```
```
//If not, abort the action
```
```
//Get all active incidents where the caller is a VIP
```
```
//If 90 percent of the SLA has been consumed, send an alert to the assignment group manager
```
```
//Use glide aggregate to count number of P1 incidents closed between March 3 to April 13 of 2023 assigned to admin
```
\*\*In an email script:\*\*
```
//Find all open incidents with an inactive assigned to the user and email the manager
```
\*\*Then contrast the result with something like a Fix Script:\*\*
```
// write a glide record query to find all locked-out users and email their manager
```
\*\*For a script include:\*\*
```
// create a function with regular expression search of text to find social security numbers and mask them with \*
```
  