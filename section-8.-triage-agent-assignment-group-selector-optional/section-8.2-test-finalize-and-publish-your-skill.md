# section-8.2-test-finalize-and-publish-your-skill.md

## section-8.2-test-finalize-and-publish-your-skill.md

> For the complete documentation index, see [llms.txt](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/llms.txt). Markdown versions of documentation pages are available by appending `.md` to page URLs; this page is available as [Markdown](https://servicenow-events-or-lab-guidebo.gitbook.io/world-forums-learning-labs-2026/world-forums-and-summits-learning-labs/put-ai-to-work-shop-for-service-operations/section-8.-triage-agent-assignment-group-selector-optional/section-8.2-test-finalize-and-publish-your-skill.md).

## Section 8.2 Test, finalize and publish your skill

Before we can use the skill in an AI agent we should test the functionality and then publish the skill. 1. Start by running a test on your new skill. In the prompt editor scroll down and click Run test. Then add an incident number, for example INC0099969 (this one is about issues with a printer) before hitting Run test again.

2\. You should then see an output below, for example:\
{"name":"Hardware","sys\\\_id":"8a5055c9c61122780043563ef53438e3","confidence":"95%"}\
in this example you can see that the skill has selected the hardware assignment group with a high confidence. You can try changing the content of the incident to see changes in behaviour. 3. Let’s finalize the prompt, publish it and then activate in through skill kit admin. First select the lock icon to finalize the prompt\
then Publish skill from top right in the editor where you can select your skill in the dialogue box:

If you gave a different name to your prompt it might look slightly different however there should only be one option for you to choose. 4. Once your prompt is published navigate in the filter navigator to Now Assist Admin -> Skills.

From here you should have the list of all skills in your instance, if you have not made any other changes you will find your skill under the section other go ahead and activate your skill.

Congratulations, your skill is now published and available for use in agents!
