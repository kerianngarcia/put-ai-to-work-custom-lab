# Section A1 - Now Creator Sample Prompts

This appendix contains sample prompts that can be used with **Now Assist for Creator** when generating flows, scripts, and other automation assets.

These examples are intended to inspire experimentation and demonstrate the types of requests that can be translated into workflows or code.

## Text-to-Flow Examples

Use prompts like the following when generating flows from natural language.

### Example 1 - High Priority Incident Notification

```text
Anytime an incident record is created. Wait 1 minute. If the incident priority equals High, then send a Teams message.
```

### Example 2 - Change Approval Process

```text
Whenever a change request is created or updated where the model is an unauthorized demo, do the following:

- Apply change approval policy.
- If approvals are approved or skipped, update the change request as Approved.
- If approvals are not approved, update the change request as Rejected.
- Evaluate the model again.
- If rejected, send an email.
- Wait until Active is False.
- Disregard change request approvals.
- Evaluate the change model again.
```

### Example 3 - Expense Approval Workflow

```text
When an expense claim is submitted:

- Email the user that the claim has been received.
- Request manager approval.
- If the manager approves:
  - Change the status to Approved.
  - Notify the user by email.
- If the request is rejected:
  - Send a rejection email.
```

---

## Text-to-Code Examples

Use prompts like the following to generate scripts, business rules, script actions, or other server-side logic.

### Temperature Conversion

```javascript
// Write a function that takes an input in Celsius and returns the value in Fahrenheit
```

### Email Validation

```javascript
// Validate that the variable emails is a string and has allowed syntax
```

```javascript
// If the syntax is allowed, return true
```

### Incident Queries

```javascript
// Return all critical incidents created in the last 6 months
```

```javascript
// Function to query the incident table and find the most recent record created in the last quarter by the current user
```

```javascript
// Get all active incidents where the caller is a VIP
```

### Email Domain Verification

```javascript
// If email is provided, ensure it is from my domain
```

```javascript
// If not, abort the action
```

### SLA Monitoring

```javascript
// If 90 percent of the SLA has been consumed, send an alert to the assignment group manager
```

### Reporting and Analytics

```javascript
// Use GlideAggregate to count the number of P1 incidents closed between March 3 and April 13, 2023 assigned to Admin
```

---

## Email Script Example

Use prompts like the following when generating email scripts.

```javascript
// Find all open incidents assigned to inactive users and email the manager
```

---

## Fix Script Example

Use prompts like the following when generating fix scripts.

```javascript
// Write a GlideRecord query to find all locked-out users and email their manager
```

---

## Script Include Example

Use prompts like the following when generating Script Includes.

```javascript
// Create a function that uses a regular expression to identify Social Security Numbers and mask them with *
```

---

## Tips for Better Results

{% hint style="info" %}
When working with Now Assist for Creator:

- Be specific about business requirements.
- Include trigger conditions whenever possible.
- Specify expected outcomes and actions.
- Mention ServiceNow tables, fields, and record types when relevant.
- Break complex requirements into logical steps.
{% endhint %}

## Completion

These sample prompts are intended to help you explore the capabilities of Now Assist for Creator and accelerate flow and script development.