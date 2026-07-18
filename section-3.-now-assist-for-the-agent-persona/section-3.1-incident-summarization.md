# Section 3.1 - Incident Summarization

In this exercise, you will use Now Assist to summarize an incident and post the generated summary to the work notes.

## Open Service Operations Workspace

1. Return to your lab instance by clicking the **ServiceNow** logo in the upper-left corner.

   Alternatively, remove any portal suffix from your instance URL.

![](../assets/section-3/S3.1-1.png)

2. Select the **Workspace** tab, then select **Service Operations Workspace**.

   Service Operations Workspace provides a consolidated view to help agents manage the life cycle of task records, such as incidents, requests, and walk-ups.

![](../assets/section-3/S3.1-2.png)

## Find the Incident

3. In Service Operations Workspace, select **List view** and under **Incidents**, select **All** to display the incident list.

![](../assets/section-3/S3.1-3.png)

4. In the incident list, select the **Filter** button with the GenAI sparkle icon in the upper-left area.

![](../assets/section-3/S3.1-4.png)

5. Select and copy the following query and watch Now Assist create the filter for you.

```text
Any incident that has a description that contains Versioning errors
```

![](../assets/section-3/S3.1-5.png)

6. Select **Apply** to process the query.

![](../assets/section-3/S3.1-6.png)

9. Select the incident link.

   Your incident number may be different from the one shown. Open the incident in Service Operations Workspace by clicking the incident number.

![](../assets/section-3/S3.1-7.png)

## Generate the Incident Summary

10. Select **Summarize** to use generative AI to summarize the incident.

![](../assets/section-3/S3.1-8.png)

11. Review the generated summary.

    The summarization skill analyzes the short description, description, work notes, and related records before generating the issue, SLAs, impacted services, and actions taken up to that point.

![](../assets/section-3/S3.1-9.png)

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

![](../assets/section-3/S3.1-10.png)

14. Edit the summary by adding a bulleted item.

15. Select **Save to work notes**.

{% hint style="info" %}
If the customer has opted into data sharing, edits to the generated response are also sent to the Now LLM for fine-tuning.
{% endhint %}

16. Expand the work note activity stream to confirm that your edits were copied.

![](../assets/section-3/S3.1-11.png)

{% hint style="info" %}
**Bonus**

Return to the incident list and try the summarization skill with any in-progress incident. Try it a few times.
{% endhint %}

## Completion

Congratulations. You created an incident summary and posted it to the work notes.

Do not close Service Operations Workspace or the incident tab. You will use them in the next section.
