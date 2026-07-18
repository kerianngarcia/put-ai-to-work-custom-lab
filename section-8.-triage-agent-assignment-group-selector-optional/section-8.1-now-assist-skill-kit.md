# Section 8.1 - Now Assist Skill Kit

In this exercise, you will create a custom Now Assist Skill Kit (NASK) skill that predicts the most appropriate assignment group for an incident.

## Create the Skill

Before you begin, verify that you are in the **IT Service Management AI Agent Collection** application scope.

![](../.gitbook/assets/section-8/S8.1-1.png)

{% hint style="info" %}
You may create a test incident using the `incident.list` table if desired. However, demo data is already available in the lab instance and can be used for testing.
{% endhint %}

1. Navigate to:

   `Now Assist Skill Kit > Home`

2. Create a new skill using the following values.

   | Field | Value |
   |---------|---------|
   | Skill name | Assignment group selector |
   | Description | This skill selects assignment groups based on information in the incident |
   | Default provider | Azure OpenAI |
   | Default provider API | Chat Completions |

![](../.gitbook/assets/section-8/S8.1-2.png)

3. Scroll down to **Apply role restrictions to skill**.

4. Add the following role:

   ```text
   itil
   ```

![](../.gitbook/assets/section-8/S8.1-3.png)

![](../.gitbook/assets/section-8/S8.1-4.png)

5. Select **Skip to Prompt Editor**.

{% hint style="info" %}
You could follow the guided prompt setup process, but for this lab we will save time by jumping directly to the Prompt Editor.
{% endhint %}

## Configure the Skill

6. Begin building the skill.

![](../.gitbook/assets/section-8/S8.1-5.png)

### Add an Input

7. Select **+** to add an input.

8. Configure the input using the following values.

   | Field | Value |
   |---------|---------|
   | Data type | String |
   | Name | incidentnumber |

Use **incidentnumber** as a single word.

### Add the Prompt

9. Add the following prompt.

Notice the references enclosed in double braces (`{{ }}`). These values will be populated by tools you add later.

      ```text
      You are an IT Service Management incident triage classifier. Your task is to
      analyze a single incident and select the most appropriate assignment group
      from a provided candidate list. You must return your answer as strict JSON.

      ## Incident

      Short Description:
      {{LookupIncident.output.short_description}}

      Description:
      {{LookupIncident.output.description}}

      ## Candidate assignment groups

      The following JSON array contains every group that may receive this incident.
      Each item has a sys_id, a name, and a description of the group's
      responsibilities.

      {{assignmentgroup.output}}

      ## How to choose

      1. Read the short description and description together to identify:
      - The affected service, system, or technology (e.g. database, network,
      hardware, software, LDAP, change request, problem record).
      - The type of work required (e.g. troubleshooting, approval, access
      request, configuration change).
      - Any location or scope signals (e.g. "New York database", "Atlanta DB").

      2. For each candidate group, weigh how well its name and description align
      with the incident. Prefer the most specialized group whose responsibilities
      explicitly cover the issue. Avoid generic catch-all groups unless no
      specialist group fits.

      3. If two groups are close, prefer the one whose description directly names
      the technology, service, or location mentioned in the incident.

      4. If no group is a clear specialist match, fall back to a general service
      desk or help desk group present in the candidate list. Do not invent a
      group.

      5. Self-rate the confidence of your selection as a percentage value.

      ## Output format

      Return ONLY a single JSON object with exactly these three fields and nothing
      else. No prose, no markdown fences, no comments, and no trailing commas.

      {
      "name": "",
      "sys_id": "",
      "confidence": "90%"
      }

      Hard rules:
      - The sys_id MUST be copied verbatim from one entry in the candidate list.
      - The name MUST be copied verbatim from the same entry.
      - Do not output any group that is not in the candidate list.
      - Do not output explanations, reasoning, or apologies. JSON only.

10. Go to the “Add tools” tab to add tools. 

In the tool editor we need to add two tools. For this exercise we will use script tools that are the fastest to add, however in a deployment we would rather recommend using a flow action or sub flows as these are easier to maintain and test.

