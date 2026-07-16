# Page 1

````
# Build an Agent with Tools

In this exercise, you will create an AI Agent, configure tools, and test the agent against an incident.

**Estimated time:** 15 minutes

---

## Create the AI Agent

1. Open **AI Agent Studio**.

   Navigate to:

   `All > AI Agent Studio > Overview`

2. Select **Create and Manage**.

3. Open the **AI Agents** tab and click **Add**.

4. Enter the following prompt:

```text
I want an agent that can recommend solutions for all incidents...
```

5. Review the generated values and verify that the following are populated:

   - Agent name
   - Agent role
   - Agent workflow steps

> Screenshot: Generated AI Agent

[Insert screenshot here]

6. If the **Possible duplications found** dialog appears, select **Ignore and continue**.

---

## Add Recommended Tools

1. Select **Recommended Tools**.

2. Add the suggested tools in the order presented.

3. Click **Save and Continue**.

> Important
>
> If the recommended tools are not displayed, use **Add Tool** and add the tools manually.

[Insert screenshot here]

---

## Create the Additional Comments Tool

1. Select **Add Tool**.

2. Configure the tool using the following values.

| Field | Value |
|---------|---------|
| Tool Type | Flow Action |
| Flow Action | Add Worknote |
| Name | Update additional comments in incident record |
| Execution Mode | Autonomous |
| Display Output | Yes |

3. Under **Advanced**, configure:

| Setting | Value |
|---------|---------|
| Output Transformation Strategy | Concise |
| Generate Messages | Enabled |

4. Click **Add**.

[Insert screenshot here]

---

## Configure Security

1. Click **Save and Continue**.

2. Configure user access.

| Setting | Value |
|---------|---------|
| User Access | Any Authenticated User |

3. Configure data access.

| Setting | Value |
|---------|---------|
| Approved Roles | itil, admin |

4. Click **Save and Continue**.

---

## Activate the Agent

1. Generate the communication messages.

2. Review the generated text.

3. Set **Status** to **On**.

4. Click **Save and Test**.

---

## Test the Agent

1. In the Task field, enter:

```text
Help me resolve INC0010248
```

2. Click **Continue**.

[Insert screenshot here]

---

## What to Observe

As the agent executes:

- Review the reasoning produced by the LLM.
- Observe which tools are selected.
- Review the generated recommendations.
- Verify that comments are written back to the incident.

In the next exercise, we will add this agent to an Agentic Workflow.
````
