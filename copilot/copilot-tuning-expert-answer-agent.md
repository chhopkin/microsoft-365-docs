---
title: Copilot Tuning Expert Answers agent
author: lauragra
ms.author: lauragra
manager: calvind
ms.collection: operations-pod
ms.reviewer: riyazp
ms.date: 02/19/2026
ms.service: microsoft-365-copilot
ms.topic: how-to
ms.localizationpriority: medium
description: Learn how to use Copilot Tuning to build an AI model for expert answers.
---

# Copilot Tuning Expert Answers agent

The **Expert Answers** agent is a tunable Copilot agent designed to answer complex, domain-specific questions grounded in your organization's content. You can further tune the agent using enterprise data to improve answer quality, relevance, and consistency.

This article describes common scenarios, tuning options, requirements, and limitations to help you implement the Expert Answers agent effectively.

> [!IMPORTANT]
> Copilot Tuning is currently available in the [Frontier early access program](https://adoption.microsoft.com/copilot/frontier-program/). Frontier includes early access to experimental features, which means features are subject to change. For more information, see [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7).

## Expert Answers agent overview

The Expert Answers agent performs deep searches across your enterprise content and generates grounded answers based on that data.

Common scenarios include:

- Question answering over large grounding datasets, such as legal or compliance repositories with thousands of files
- Enforcing specific tone or guardrails, such as for internal HR or policy agents
- Working with datasets that contain company-specific terminology or jargon, such as internal knowledge bases

A typical workflow starts with testing the non-customized agent. You can then customize the agent by using the **Expert Answers agent** template in Agent Builder, and optionally tune the agent to further improve its responses.

Final responses combine:

- Declarative agent capabilities configured in Agent Builder
- Expert Answers capabilities configured through the tuning flow

In most cases, Microsoft recommends using both approaches together by adding knowledge in Agent Builder and refining behavior through agent tuning.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-response-architecture-diagram.png" alt-text="Diagram showing how final responses combine declarative agent capabilities configured in Agent Builder with Expert Answers capabilities configured through the tuning flow." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-response-architecture-diagram.png":::

## Tuning flow

Tuning allows you to evaluate and improve agent responses. You can tune an Expert Answers agent in three ways.

| Tuning type | When to use |
|------------|-------------|
| **Context** | Add Expert Answers search capabilities in addition to declarative agent features, and evaluate agent behavior |
| **Model** | Improve how the agent searches and retrieves relevant files |
| **Tools** | Add sub-agents to enforce guardrails, apply tone, or generate deeper responses by using Researcher |

## Use the non-customized agent

Before customizing the agent, you can test the default experience.

You must select a SharePoint site before asking a question. The agent answers questions using content from that site. If no site is selected, the agent searches previous messages for a referenced site.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-sharepoint-site-selection.png" alt-text="Screenshot showing the SharePoint site selection interface before asking a question in the non-customized Expert Answers agent." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-sharepoint-site-selection.png":::

## Customize the agent

Start by selecting the **Expert Answers agent** template in Agent Builder. 

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-template-selection.png" alt-text="Screenshot showing the Expert Answers agent template selection in Agent Builder." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-template-selection.png":::

Provide the following information:

- **Name**
- **Description**
- **Instructions**

You can optionally add **knowledge** and **capabilities**.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-agent-configuration.png" alt-text="Screenshot of the agent configuration page where you provide name, description, instructions, and optionally add knowledge sources and capabilities." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-agent-configuration.png":::

### Use the customized agent

After customization, the agent answers questions using the SharePoint sites you configured as knowledge sources.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-customized-agent-chat.png" alt-text="Screenshot showing the customized Expert Answers agent answering questions using the configured SharePoint sites as knowledge sources." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-customized-agent-chat.png":::

## Context tuning

Context tuning lets you define the agent's goals, generate evaluation data, and improve how the Expert Answers search capability retrieves information.

You provide the following information during this step.

| Information | Page | Purpose |
|------------|------|---------|
| Main goal and domain | Define tuning goals | Guides search behavior and suggests subgoals and metrics |
| Example file upload | Define tuning goals | Creates evaluation data |
| Subgoals | Review clarifying questions | Guides search behavior and evaluation |
| Metrics | Review metrics | Evaluates agent responses |
| Grounding information | Agent context | Defines search behavior |

### Define tuning goals

- **Main goal**: Refines the agent's objective. Existing instructions are used as a starting point. The goal guides the Expert Answers search capability during inference.
- **Domain**: Specifies a high-level subject area, such as human resources.
- **Example files**: Sample files used to generate evaluation questions and answers. These should represent the document types and topics users are likely to ask about.

Microsoft recommends selecting these files from the grounding dataset. Providing more files (up to 50) and increasing topic diversity improves evaluation quality.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-define-tuning-goals.png" alt-text="Screenshot showing the Define tuning goals page where you specify the main goal, domain, and upload example files for evaluation." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-define-tuning-goals.png":::

### Review clarifying questions

Subgoals are used with your uploaded documents to generate question-and-answer pairs for evaluation. They also help guide the Expert Answers search capability.

Focus these questions on the types of queries users are expected to ask. Answer-quality criteria are defined in the metrics step.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-review-clarifying-questions.png" alt-text="Screenshot showing the Review clarifying questions page where you define subgoals that guide search behavior and evaluation." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-review-clarifying-questions.png":::

### Review metrics

Metrics define how the agent is evaluated. In addition to the metrics you specify, Microsoft applies a built-in accuracy metric that compares the agent's response with a "golden" answer derived from your data.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-review-metrics.png" alt-text="Screenshot showing the Review metrics page where you define evaluation criteria for agent responses." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-review-metrics.png":::

### Agent context

Review the agent's grounding data. This data is used by the Expert Answers search capability to generate responses.


:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-agent-context.png" alt-text="Screenshot showing the Agent context page where you review the grounding data used by the Expert Answers search capability." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-agent-context.png":::

## Evaluations

After you complete context tuning and subsequent steps, evaluation results appear on the **Tune agent** homepage.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-evaluation-results.png" alt-text="Screenshot showing evaluation results displayed on the Tune agent homepage after completing context tuning." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-evaluation-results.png":::

## Model tuning

Model tuning trains the Expert Answers search capability. The agent uses a **training dataset** to learn how to write better queries and select more relevant documents from the **grounding dataset**.

Although the grounding dataset is primarily used to generate final answers, information from the training dataset might also appear in responses. In most cases, Microsoft recommends using the same dataset for grounding and training.

Model tuning is most effective when:

- The grounding dataset contains several hundred or more files
- Queries include company-specific language or concepts

To tune a model:

1. **Provide preferred outputs:** Select a **training dataset**. In most scenarios, this should match the dataset used for grounding.

    :::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-model-tuning-training-dataset.png" alt-text="Screenshot showing the training dataset selection interface for model tuning where you provide preferred outputs." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-model-tuning-training-dataset.png":::

1. **Review access:** Review the access recommendations.

    :::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-model-tuning-access-review.png" alt-text="Screenshot showing the access recommendations review page during model tuning." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-model-tuning-access-review.png":::

## Tool tuning

Tool tuning lets you add additional tools that the agent can use when generating responses, including:

- **Style Editor (tunable agent)** to rewrite responses to match a specific tone
- **Document Reviewer (tunable agent)** to enforce defined guardrails
- **Researcher** to perform longer, deeper searches

To use tunable agents, they must first be context tuned.

You can also provide orchestration instructions that define how tools are used together. If all tools are selected, the default flow is:

1. Use Researcher as an additional source
2. Rewrite the response with the Style Editor
3. Validate the response with the Document Reviewer

Examples of custom orchestration instructions include:

- If the initial answer is incomplete, use Researcher before generating the final response.
- If the question is about benefits, use the validation agent.
- Use the validation agent first, then apply tone alignment.

:::image type="content" source="media/copilot-tuning-expert-answer-agent/expert-answers-tool-tuning-interface.png" alt-text="Screenshot showing the Tool tuning interface where you add additional tools like Style Editor, Document Reviewer, and Researcher, and define orchestration instructions." lightbox="media/copilot-tuning-expert-answer-agent/expert-answers-tool-tuning-interface.png":::

## Limitations

### Context tuning

- Only SharePoint files and folders are supported.
- Expert Answers search is subject to known retrieval limitations.

### Model tuning

- Only SharePoint files and folders are supported.
- Supported file types: .docx, .pdf, .aspx, .doc, .html, .txt.
- Only text content is used for training.
- For .aspx and .html files, only extracted text is used.

### Tool tuning

- If you add knowledge or capabilities in Agent Builder, responses might not follow tone or guardrails defined by the Style Editor or Document Reviewer. This can occur when additional information is added after these agents run.
- To ensure tone and rule enforcement, avoid adding capabilities in Copilot Studio Lite.

## FAQ

### What knowledge sources should I add in Agent Builder, context tuning, and model tuning?

In most cases, use the same knowledge source across all three. You might choose a different approach if:

- You do not want to use declarative agent capabilities, in which case you should not add knowledge in Agent Builder.
- You want the Expert Answers search capability to focus on a subset of files, in which case you can limit the files added during context and model tuning.

### When should I retrain my agent?

Incremental changes to grounding data typically do not significantly reduce performance. New files are included in responses automatically. However, information from files removed after training might still appear in responses until the agent is retrained.

## Related content

- [Copilot Tuning overview](copilot-tuning-overview.md)