# Section 3.1 - Incident Summarization

In this exercise, you will use Now Assist to summarize an incident and post the generated summary to the work notes.

## Open Service Operations Workspace

1. Return to your lab instance by clicking the **ServiceNow** logo in the upper-left corner.

   Alternatively, remove any portal suffix from your instance URL.

<p align="center">
  <img src="../assets/section-3/S3.1-1.png" width="100%">
</p>

2. Select the **Workspace** tab, then select **Service Operations Workspace**.

   Service Operations Workspace provides a consolidated view to help agents manage the life cycle of task records, such as incidents, requests, and walk-ups.

<p align="center">
  <img src="../assets/section-3/S3.1-2.png" width="100%">
</p>

## Find the Incident

3. In Service Operations Workspace, select **List view** and under **Incidents**, select **All** to display the incident list.

<p align="center">
  <img src="../assets/section-3/S3.1-3.png" width="100%">
</p>

4. In the incident list, select the **Filter** button with the GenAI sparkle icon in the upper-left area.

<p align="center">
  <img src="../assets/section-3/S3.1-4.png" width="100%">
</p>

5. Select and copy the following query and watch Now Assist create the filter for you.

```text
Any incident that has a description that contains Versioning errors
```

<p align="center">
  <img src="../assets/section-3/S3.1-5.png" width="100%">
</p>

6. Select **Apply** to process the query.

<p align="center">
  <img src="../assets/section-3/S3.1-6.png" width="100%">
</p>

9. Select the incident link.

   Your incident number may be different from the one shown. Open the incident in Service Operations Workspace by clicking the incident number.

<p align="center">
  <img src="../assets/section-3/S3.1-7.png" width="100%">
</p>

## Generate the Incident Summary

10. Select **Summarize** to use generative AI to summarize the incident.

<p align="center">
  <img src="../assets/section-3/S3.1-8.png" width="100%">
</p>

11. Review the generated summary.

    The summarization skill analyzes the short description, description, work notes, and related records before generating the issue, SLAs, impacted services, and actions taken up to that point.

<p align="center">
  <img src="../assets/section-3/S3.1-9.png" width="100%">
</p>

{% hint style="info" %}
Your incident summarization may look slightly different from the screenshot shown.
{% endhint %}

12. Notice the icons at the bottom of the generated response.

| Icon or action | Purpose |
|---|---|
| Thumbs up or thumbs down | Send feedback during Now LLM retraining if the customer has opted into data sharing. |
| Copy | Copy the generated summary to the clipboard. |
| Regenerate | Generate a new version of the summary. |

13. Add the generated summary to the work notes by selecting **Share**.

<p align="center">
  <img src="../assets/section-3/S3.1-10.png" width="100%">
</p>

14. Edit the summary by adding a bulleted item.

15. Select **Save to work notes**.

{% hint style="info" %}
If the customer has opted into data sharing, edits to the generated response are also sent to the Now LLM for fine-tuning.
{% endhint %}

16. Expand the work note activity stream to confirm that your edits were copied.

<p align="center">
  <img src="../assets/section-3/S3.1-11.png" width="100%">
</p>

{% hint style="info" %}
**Bonus**

Return to the incident list and try the summarization skill with any in-progress incident. Try it a few times.
{% endhint %}

## Completion

Congratulations. You created an incident summary and posted it to the work notes.

Do not close Service Operations Workspace or the incident tab. You will use them in the next section.
