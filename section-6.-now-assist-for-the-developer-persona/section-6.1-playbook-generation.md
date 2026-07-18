# Section 6.1 - Playbook Generation

Everyone in the room has probably drawn a brilliant flow on a whiteboard and then had to figure out how to get it into ServiceNow.

In this exercise, you will use Now Assist for Creator to generate a playbook from process details.

## Open Workflow Studio

1. Open **Workflow Studio**.

   Navigate to:

   `All > Process Automation > Workflow Studio`

   The ServiceNow platform uses workflows to orchestrate process steps and integrate them into systems. Flow Designer is used to build those workflows.

   ![](../.gitbook/assets/section-6/S6.1-1.png)

2. In the new Workflow Studio tab, click **New** on the far right.

3. From the dropdown menu, select **Playbook**.

   ![](../.gitbook/assets/section-6/S6.1-2.png)

## Generate the Playbook

4. Copy and paste the following text into the description field.

   ```text
   Step 1 - Pre-Intake (GCR-Creative)
   - Review the upcoming GCR roadmap to identify expected creative needs.
   - Create placeholder projects for resource and skill forecasting.

   Step 2 - Project Intake (Requestors)
   - Creative requests submitted via the Parent GCR intake system (Jira).
   - Each Jira ticket generates a linked Jira Child ticket for GCR Creative's workflow.

   Step 3 - Resource Review (Creative Leads)
   - Weekly review of capacity and assign resources by skill, role, and availability.

   Step 4 - Project Kick-Off (Creative Leads and Team Members)
   - Finalize the creative brief, set milestones, confirm deliverables, and assign ownership.

   Step 5 - Concept and Create (Creative Team Members)
   - Execute tasks in alignment with the agreed timelines and quality standards.

   Step 6 - Review and Delivery (Creative Leads)
   - Review, approve, and deliver assets.

   Step 7 - Reporting and Finance Tracking (Creative Leads, Managers, and Finance/Operations)
   - Capture time spent, cost, and resource utilization data.
   - Link spend to specific initiatives, reconcile with finance systems, and update stakeholders.
   ```

   ![](../.gitbook/assets/section-6/S6.1-3.png)

   ![](../.gitbook/assets/section-6/S6.1-4.png)

5. Enter a flow name.

6. In **Attach an Image**, select the file you downloaded.

7. Click **Generate flow preview**.

8. Review the generated flow.

   Now Assist for Creator gives you a jumpstart on playbook development.

9. When you are finished, click **Discard playbook**.
