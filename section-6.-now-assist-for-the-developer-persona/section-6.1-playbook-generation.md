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
   Step 1 - Concern Intake (Faculty, Staff, Students, and Student Care Team)
   - Submit a student concern through the Student Support portal.
   - Review the submitted concern and validate available information.
   - Create a Student of Concern case record.
   
   Step 2 - Initial Risk Assessment (Student Care Team)
   - Assess the reported behavior and available case details.
   - Determine whether the case presents Low, Medium, or High risk.
   - Escalate emergency situations to Campus Safety for immediate response.
   
   Step 3 - Parallel Case Review (Academic Advising, Residence Life, Counseling Services, Disability Services, and Student Affairs)
   - Academic Advising reviews academic performance, attendance trends, and faculty concerns.
   - Residence Life reviews housing incidents, resident assistant observations, and community concerns.
   - Counseling Services reviews previous support interactions and outreach opportunities.
   - Disability Services determines whether accommodations or support plans exist.
   - Student Affairs reviews conduct history and prior intervention records.
   
   Step 4 - Multidisciplinary Case Review (Student Affairs, Counseling Services, Academic Advising, Residence Life, and Campus Safety)
   - Review findings gathered from all participating departments.
   - Assess overall student risk and support needs.
   - Determine the appropriate intervention strategy and assign ownership.
   
   Step 5 - Intervention Planning and Execution (Assigned Support Teams)
   - Initiate counseling referrals and outreach activities when appropriate.
   - Create academic success plans and advisor follow-up activities when needed.
   - Launch conduct management activities when policy violations are identified.
   - Coordinate wellness checks and additional support services as required.
   - Execute multiple intervention activities concurrently based on the student's needs.
   
   Step 6 - Ongoing Monitoring (Student Care Team and Assigned Departments)
   - Monitor student progress and engagement with assigned services.
   - Collect status updates from participating departments on a recurring basis.
   - Track completion of intervention activities and follow-up tasks.
   - Escalate the case if new concerns or risk indicators emerge.
   
   Step 7 - Case Closure and Outcome Reporting (Student Affairs, Student Care Team, and Leadership)
   - Conduct a final review of interventions, outcomes, and recommendations.
   - Document services utilized, case resolution details, and follow-up guidance.
   - Close the Student of Concern case.
   - Generate leadership reports and trend analysis for continuous improvement.
   ```

5. Give your playbook a name.

6. Click **Generate flow preview**.

7. Review the generated flow.

8. When you are finished, click **Discard playbook** and try the additional scenarios.

## Additional Scenarios

**New Academic Program**
   ```text
   Step 1 - Program Concept Submission (Faculty and Department Leadership)
   - Identify a new academic program opportunity based on student demand, workforce needs, or institutional strategy.
   - Document program goals, target audience, and expected outcomes.
   - Submit the program proposal for initial review.
   
   Step 2 - Department Review (Department Leadership and Faculty Committee)
   - Evaluate academic merit, curriculum requirements, and faculty capacity.
   - Review alignment with departmental objectives and institutional priorities.
   - Approve the proposal for broader evaluation.
   
   Step 3 - Parallel Program Evaluation (Curriculum Committee, Registrar, Finance, Institutional Research, and Accreditation)
   - Curriculum Committee reviews course structure, learning outcomes, and degree requirements.
   - Registrar evaluates catalog impacts, academic policies, and scheduling considerations.
   - Finance assesses budget requirements, revenue projections, and resource needs.
   - Institutional Research evaluates market demand, enrollment forecasts, and competitor analysis.
   - Accreditation reviews compliance with regulatory and accreditation requirements.
   
   Step 4 - Program Approval Review (Provost, Academic Leadership, and Governance Bodies)
   - Review findings from all participating groups.
   - Assess academic, financial, and operational feasibility.
   - Determine final approval status and required modifications.
   
   Step 5 - Program Development and Launch Planning (Academic Affairs, Registrar, Marketing, and Department Leadership)
   - Finalize curriculum, course sequencing, and academic requirements.
   - Configure catalog, registration, and student information systems.
   - Develop marketing and recruitment materials.
   - Prepare faculty, staff, and support resources for program launch.
   
   Step 6 - Enrollment and Readiness Execution (Admissions, Advising, Registrar, and Academic Departments)
   - Open the program for student applications and enrollment.
   - Train advisors and support staff on program requirements.
   - Monitor enrollment targets and readiness milestones.
   - Address launch issues and stakeholder questions.
   
   Step 7 - Post-Launch Review and Reporting (Academic Leadership, Institutional Research, and Finance)
   - Evaluate enrollment, retention, and student success metrics.
   - Review financial performance and resource utilization.
   - Document lessons learned and improvement opportunities.
   - Generate leadership reports and long-term program recommendations.
   ```

**Faculty Hiring**
   ```text
   Step 1 - Position Request and Approval (Department Leadership and Dean)
   - Identify faculty staffing needs based on enrollment, curriculum, and strategic priorities.
   - Define position requirements, qualifications, and budget assumptions.
   - Submit the faculty hiring request for approval.
   
   Step 2 - Position Planning (Human Resources and Department Leadership)
   - Develop the job description and recruitment strategy.
   - Define evaluation criteria, interview process, and hiring timeline.
   - Launch the recruitment effort.
   
   Step 3 - Parallel Candidate Evaluation (Search Committee, Human Resources, Dean's Office, and Diversity/Compliance Teams)
   - Search Committee reviews applications and evaluates academic qualifications.
   - Human Resources validates eligibility, credentials, and employment requirements.
   - Dean's Office reviews alignment with college priorities and workforce plans.
   - Diversity and Compliance teams review adherence to institutional hiring policies.
   - Conduct initial candidate screenings and rankings.
   
   Step 4 - Interview and Selection Review (Search Committee, Department Leadership, and Dean)
   - Conduct interviews, teaching demonstrations, and stakeholder meetings.
   - Gather feedback from faculty, students, and administrators.
   - Review candidate evaluations and determine finalist recommendations.
   
   Step 5 - Offer and Pre-Employment Processing (Human Resources and Department Leadership)
   - Extend a hiring recommendation to the selected candidate.
   - Prepare and negotiate offer terms.
   - Complete background checks, credential verification, and employment documentation.
   - Initiate visa sponsorship activities when required.
   
   Step 6 - Faculty Onboarding Preparation (Human Resources, IT, Facilities, and Academic Departments)
   - Provision systems, email, learning platforms, and campus access.
   - Assign office space, equipment, and required resources.
   - Schedule new faculty orientation and training activities.
   - Prepare courses and academic assignments.
   
   Step 7 - Onboarding Completion and Performance Readiness (Department Leadership, Human Resources, and Faculty Support Teams)
   - Complete onboarding activities and policy acknowledgments.
   - Confirm teaching assignments and academic responsibilities.
   - Monitor readiness for the first academic term.
   - Generate onboarding completion and hiring outcome reports.
   ```

**Approvals, Committees, and Other Natural Disasters**   
   ```text
   Step 1 - Great Idea Appears (Random Employee)
   - Attend an AI conference.
   - Watch three YouTube videos.
   - Become convinced AI will solve everything.
   - Tell coworkers, "We need this."
   
   Step 2 - Build the Business Case (Project Champion)
   - Calculate hours spent on repetitive work.
   - Estimate potential savings.
   - Create a PowerPoint with way too many slides.
   - Add at least one AI-generated image.
   
   Step 3 - Gather Support (Can Happen Simultaneously)
   - IT says, "We need security review."
   - Finance says, "What's the budget?"
   - Legal says, "We should read the contract."
   - Department leaders say, "Can it help my team too?"
   - Everyone asks for a demo.
   
   Step 4 - Executive Review (Leadership Team)
   - Present business case.
   - Answer questions about risk.
   - Answer questions about ROI.
   - Answer questions about questions.
   - Promise to follow up with more information.
   
   Step 5 - Approval Maze (Can Happen Simultaneously)
   - Procurement reviews pricing.
   - Security reviews architecture.
   - Finance reviews funding.
   - Governance committee reviews AI usage.
   - Someone requests another meeting.
   
   Step 6 - Board Presentation (Executive Sponsors)
   - Explain what AI is.
   - Explain what AI is not.
   - Explain why this AI is different from the last AI.
   - Show examples.
   - Survive Q&A.
   
   Step 7 - Decision Time (Board and Executives)
   - Approve purchase.
   - Request more information.
   - Form a committee.
   - Form a committee to oversee the committee.
   
   Step 8 - Implementation Planning (IT and Business Teams)
   - Select pilot groups.
   - Identify initial use cases.
   - Schedule training.
   - Promise everyone this will reduce administrative work.
   
   Step 9 - Realization Moment (Everyone)
   - Discover AI does not replace people.
   - Discover AI does remove a lot of tedious work.
   - Celebrate getting back hours of productive time.
   - Wonder why this took six months to approve.
   
   Exception Path - More Information Requested (Everyone)
   - Board requests additional analysis.
   - Executive team requests revised ROI assumptions.
   - Finance requests three more cost models.
   - IT requests another architecture review.
   - Schedule two follow-up meetings and one working session.
   - Return to Step 4 and repeat until everyone is tired enough to approve the purchase.
   
   Success Metrics (Leadership Dashboard)
   - Number of approval meetings reduced from 47 to only 46.
   - Time spent creating PowerPoint slides reduced by 73%.
   - Number of people saying "Let's circle back" reduced by 15%.
   - Hours returned to staff from repetitive work increases significantly.
   - Executive confidence in AI increases from "I'm skeptical" to "Let's pilot it."
   - Number of committees created remains below the number of committees created to govern committees.
   ```

Now Assist for Creator gives you a jumpstart on playbook development.
