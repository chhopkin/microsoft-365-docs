---
title: New title <<<
f1.keywords: NOCSH
ms.author: hokavian
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 2/02/2026
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: New description <<<<<
appliesto:
- ✅ Microsoft 365 Copilot
---


Microsoft Copilot Studio has a new evaluation tool that enables automated testing for output quality. Unlike [testing in the chat pane](/microsoft-copilot-studio/authoring-test-bot?tabs=webApp), the agent evaluation tool runs repeatable, scenario-based test sets using different user profiles without requiring manual testing of each prompt. [Learn more about the evaluation tool](/microsoft-copilot-studio/analytics-agent-evaluation-intro) and [how to approach agent evaluations](/microsoft-copilot/blog/copilot-studio/how-to-evaluate-ai-agents/).


<br>
In this article:
- Get started creating your own test cases and run automated tests
- Explore test results and get help improving common quality issues
- Learn more about how to create a custom evaluations strategy for your ESS agent

# Why invest in evaluations for your agent?
Move from guesswork to a strategic, test driven approach to measuring the quality of the ESS agent’s responses. This means thinking through a clear evaluation strategy with well crafted golden queries, running structured test sets, and having the support to interpret results and fix quality issues. This might mean refining agent instructions, editing topic triggers, or revisiting knowledge sources. 
- Get a clearer picture on how your ESS agent responds and handles scenarios. 
- Deploy faster with less risk by validating changes before production. 
- Improve accuracy and relevance using grounded, consistent quality scoring. 
- Prevent regressions caused by prompt, model, or configuration changes. 
- Save manual QA time through automated dataset generation and evaluation. 
- Increase employee trust with more consistent, complete, and correct answers. 
- Demonstrate ROI with clear KPIs and analytics across conversation outcomes. 
- Support governance and compliance with auditable, repeatable, objective evaluation practices. 


# About the Copilot Studio evaluator tool
Copilot Studio evaluations are made up of test sets, which contain test cases. A test case is a single message, prompt, or question that simulates what a user would ask ESS. A test case can also include the answer you expect your agent to reply with, also called an expected response. [Learn more about creating test cases](/microsoft-copilot-studio/analytics-agent-evaluation-intro#how-agent-evaluation-works).


## Summary of evaluation options in Copilot Studio

To validate and improve agent quality at the right level of depth, Copilot Studio offers several evaluation options today. The content in this article will focus on running evaluations on your own custom query sets.

1. **Quickly generate prompts for general quality checks**. [Use AI‑generated prompts](microsoft-copilot-studio/analytics-agent-evaluation-create#generate-a-test-set-from-knowledge-or-topics) when you want a fast, lightweight pulse check on your agent’s behavior based on knowledge and topics setup in ESS. This is great for early exploration, spot‑checking new features, or validating a small change before doing deeper testing. These prompts help you identify surface‑level issues without needing a full test set. 
2.	**Use the “Evaluate” function in the Test pane for deeper, scenario‑level validation**. [From the Test copilot pane](/microsoft-copilot-studio/analytics-agent-evaluation-create#create-a-new-test-set), you can run an evaluation directly on the conversation you’re testing. 
3.	**Save a live conversation as an evaluation snapshot**. [Turn a real test chat interaction into a reusable evaluation artifact](/microsoft-copilot-studio/authoring-test-bot?tabs=webApp#save-conversation-snapshots). Saving a snapshot captures the full conversation and diagnostic details, allowing you to analyze what went wrong and convert that interaction into a future test case you can run again as part of your regression set.
4.	**Run evals on your own custom query sets**. [Use custom agent evaluations by uploading a csv. file](/microsoft-copilot-studio/analytics-agent-evaluation-create#create-a-test-set-file-to-import) when you need a repeatable, scalable, regression‑safe method for measuring quality. Custom test sets let you define expected responses, apply multiple graders, simulate user profiles, and compare results across versions over time. *Most of the guidance in this document will focus on this kind of evaluation*.



## Steps to create and run tests

Follow these steps to build and evaluate a test set for your ESS agent in Copilot Studio:

1. Navigate to the **Evaluation** tab for your ESS agent in Copilot Studio.
2. Select [Create new test set](/microsoft-copilot-studio/analytics-agent-evaluation-create#create-a-new-test-set) to begin.
3. Choose whether to **generate prompts** automatically or [import a CSV file](/microsoft-copilot-studio/analytics-agent-evaluation-create#create-a-test-set-file-to-import). You can [update test set details at any time](/microsoft-copilot-studio/analytics-agent-evaluation-edit).
4. Select the [evaluation methods](/microsoft-copilot-studio/analytics-agent-evaluation-overview) you want to use. 
5. Choose which **user profiles** should [run the tests so results](/microsoft-copilot-studio/analytics-agent-evaluation-results#compare-test-results) accurately reflect context, access levels, and permissions.
6. Run the test, review the results, and compare outcomes over time. You can also [export test results](/microsoft-copilot-studio/analytics-agent-evaluation-results#export-test-results) to share with stakeholders and reviewers.
7. Based on what you learn, you may decide to update a knowledge source, topic trigger, agent instructions, or other components. After each change, re‑run the evaluation to confirm the fix and ensure no regressions occur.


# How to use this guidance and toolkit
To help you confidently assess and improve the quality of your ESS agent, there are three approaches to getting started:
1. **Use sample test sets to see how the tool works**. This complete dataset can be used for ESS instances that haven’t been customized yet so you can quickly learn how the evaluation tool works and how to structure your evaluation strategy. 
2. **Use templated datasets to quickly test your agent’s responses**. These partially structured evaluation set you can quickly adapt to match your own policies, systems, and workflows. These templates are the starting point and can be edited and expanded to reflect your organization’s real policies, services, and workflows.
3. **Get guidance on creating a customized evaluation strategy**. Throughout this document, there are basic strategies, insights from employee experience research, and other tips to help you build custom data sets that can be regularly tested and scaled as your agent takes on new scenarios and capabilities. 

## Summary of the kinds of ESS quality tests the evaluator tool supports
The following kinds of tests can be run using the evaluator tool, and there are already starter golden query sets that supports these kinds of tests. The tests listed here are ideal for ESS agents because they tests different parts of the platform (knowledge, topics, instructions, etc.) while also testing skills every ESS agent needs.
These tests fall into 3 main categories:
1.	**Knowledge tests** that verify the agent is accurately retrieving and synthesizing official HR and IT documents from SharePoint, ServiceNow, and more. These tests focus on measuring accuracy, groundedness, relevance, and completeness.
2.	**Data and topic tests** that confirm the right topic is triggered, and the agent is correctly accessing and using data in integrated systems like Workday, SuccessFactors, etc. 
3.	**Conversational quality tests** that measure tone, empathy, refusal patterns, and safety handling across a variety of scenarios.


| Category               | Test types |
|------------------------|------------|
| Knowledge              | **Specific knowledge** tests measure knowledge accuracy and completeness when there is a specific, and fact-based answer. **General knowledge** tests measure the agent’s ability to use non-official knowledge to answer more open-ended kinds of questions.
| Data and topics        | Integrated services like **ServiceNow** and **Workday** can be tested to confirm certain workflows are getting triggered as expected, and that responses include the right data.
| Conversational quality  | Test instructions and topics that contribute to overall conversational quality like the **Seek Clarification Topic** or **Responsible AI** scenarios.










