# Section 3.1 - Incident Summarization

In this exercise, you will use Now Assist to summarize an incident and post the generated summary to the work notes.

## Open Service Operations Workspace

1. Return to your lab instance by clicking the **ServiceNow** logo in the upper-left corner.

   Alternatively, remove any portal suffix from your instance URL.

![](../.gitbook/assets/assets/section-3/S3.1-1.png)

2. Select the **Workspace** tab, then select **Service Operations Workspace**.

   Service Operations Workspace provides a consolidated view to help agents manage the life cycle of task records, such as incidents, requests, and walk-ups.

![](../.gitbook/assets/section-3/S3.1-2.png)

## Find the Incident

3. In Service Operations Workspace, select **List view** and under **Incidents**, select **All** to display the incident list.

![](../.gitbook/assets/section-3/S3.1-3.png)

4. In the incident list, click the search button (magnifying glass) in the upper-left area.

5. Search "versioning errors".

6. Select the incident link.

   Your incident number may be different from the one shown. Open the incident in Service Operations Workspace by clicking the incident number.

![](../.gitbook/assets/section-3/S3.1-7.png)

## Generate the Incident Summary

7. Select **Summarize** to use generative AI to summarize the incident.

![](../.gitbook/assets/section-3/S3.1-8.png)

8. Review the generated summary.

    The summarization skill analyzes the short description, description, work notes, and related records before generating the issue, SLAs, impacted services, and actions taken up to that point.

![](../.gitbook/assets/section-3/S3.1-9.png)

{% hint style="info" %}
Your incident summarization may look slightly different from the screenshot shown.
{% endhint %}

9. Notice the icons at the bottom of the generated response.

| Icon or action | Purpose |
|---|---|
| Thumbs up or thumbs down | Send feedback during Now LLM retraining if the customer has opted into data sharing. |
| Copy | Copy the generated summary to the clipboard. |
| Regenerate | Generate a new version of the summary. |

10. Add the generated summary to the work notes by selecting **Share**.

![](../.gitbook/assets/section-3/S3.1-10.png)

11. Edit the summary by adding a bulleted item.

12. Select **Save to work notes**.

{% hint style="info" %}
If the customer has opted into data sharing, edits to the generated response are also sent to the Now LLM for fine-tuning.
{% endhint %}

13. Expand the work note activity stream to confirm that your edits were copied.

![](../.gitbook/assets/section-3/S3.1-11.png)

{% hint style="info" %}
**Bonus**

Return to the incident list and try the summarization skill with any in-progress incident. Try it a few times.
{% endhint %}

## Completion

Congratulations. You created an incident summary and posted it to the work notes.

Do not close Service Operations Workspace or the incident tab. You will use them in the next section.
