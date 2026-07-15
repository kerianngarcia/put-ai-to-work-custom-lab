# section-4.2-now-assist-for-the-virtual-agent.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-4.-now-assist-for-the-employee-persona/section-4.2-now-assist-for-the-virtual-agent.md).
# Section 4.2 Now Assist for the Virtual Agent
Before we test out Now Assist for Virtual Agent, let's pause for a quick history lesson:
All chatbots – including ServiceNow's Virtual Agent (VA) – require some development. VA provides out-of-the-box conversations to reduce development, but customers must still use developers to modify them to suit their unique needs.
Generative AI changed all that. If a user's request could be answered by a knowledge article or a catalog item (in many cases, up to 70% of incidents/cases fall into this category), then Now Assist in VA would dynamically generate the conversation – NO DEVELOPMENT needed. This is huge, and you're about to see why.
1. In the same enhanced screen, let’s ask a new question
![](/files/QLSjk4SgmQjZPOCCguWa)

{% hint style="info" %}
Tip: If you can’t see the VA icon, you’re probably not in the Employee Center. Double-check that you’re using the correct URL!
{% endhint %}
2. \*\*Copy and paste\*\* the following into the Now Assist window and \*\*hit enter\*\*
> What are my current assets?
![](/files/HYXkBC7Vmk73Dim4cTVa)

3. Now, \*\*copy and paste\*\* the following and \*\*hit enter\*\*:
> I a need a new macbook ASAP, I have a critical meeting in 2 days
![](/files/qDedn6qL1ASqpGiOFl7K)

![](/files/ZUp5KsBHNO7hVj7SAkSb)

Note how Now Assist switches tracks and follows the change in conversation. Hover over the Replacement laptop option and c\*\*lick Start Request\*\*, then respond to the questions as needed.
![](/files/6L6LPLsOTtbblmO1FACq)

4. Next, \*\*copy and paste\*\* the following and \*\*hit enter\*\*
> How do I connect to VPN?
![](/files/umoalpovKZF88Zbuw0xP)

Because the Admin's assets are recorded in ServiceNow, Now Assist knows that Abel has a Mac and provides the appropriate instructions. Also, easily pivoting from question to question.
\*\*Congratulations,\*\* you have tested search, engaged in a multi-turn conversation with Now Assist, and even ordered a replacement laptop. You have completed this section!
  
---
# Agent Instructions
This documentation is published with GitBook. GitBook is the documentation platform designed so that both humans and AI agents can read, navigate, and reason over technical content effectively. Learn more at gitbook.com.
## Querying This Documentation
If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.
Perform an HTTP GET request on the current page URL with the `ask` query parameter, and the optional `goal` query parameter:
```
GET https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-4.-now-assist-for-the-employee-persona/section-4.2-now-assist-for-the-virtual-agent.md?ask=&goal=
```
`ask` is the immediate question: it should be specific, self-contained, and written in natural language.
`goal` is optional and describes the broader end goal you are ultimately trying to accomplish on behalf of the user. GitBook uses it to tailor the answer towards what is most useful for that goal.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.
Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
