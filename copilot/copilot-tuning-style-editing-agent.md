---
title: Copilot Tuning Style Editing agent
description: Learn how to use and tune the Style Editing agent in Microsoft 365 Copilot to rewrite content so it aligns with your organization’s brand tone, voice, and writing standards.
author: david-salas
ms.author: dsalasbarran
manager: calvind
ms.date: 02/19/2026
ms.update-cycle: 180-days
audience: Admin
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
---

# Copilot Tuning Style Editing agent

The **Style Editing Tunable agent** helps organizations standardize how content is rewritten so it consistently reflects their brand tone, voice, and writing standards. By using Copilot Tuning, you can configure the agent to apply style rules automatically while preserving the original meaning and intent of the content.

This agent is designed for teams that produce large volumes of written content and want consistent, high‑quality results without repeated manual editing.

> [!IMPORTANT]
> Copilot Tuning is currently available in the [Frontier early access program](https://adoption.microsoft.com/copilot/frontier-program/). Frontier includes early access to experimental features, which means features are subject to change. For more information, see [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7).

## What the Style Editing agent does

The Style Editing agent can:

- Rewrite drafts to align with a defined tone, voice, and writing style
- Preserve meaning and intent while improving clarity and consistency
- Apply organizational style rules automatically after tuning
- Support additional refinement through context tuning and model tuning

Use the default agent for ad-hoc rewriting or tune it to create a specialized agent that writes in your organization’s voice by default.

The default agent applies style based on instructions or guidelines you provide directly in the prompt.

The tuned agent persists your organization's style guide and examples in the agent, so you don't need to restate rules for each rewrite.

## Use the agent before tuning

Before tuning, test the Style Editing agent by using the default template.

To get started, provide either a text excerpt, or a document link, along with a rewrite instruction, such as *rewrite*.

The following are example prompts:

- Rewrite IdeaCoachAgentDocumentation.docx.
- Rewrite "We took a quick look at the document and a few sections feel wordy…".

## Training approach

Tune the Style Editing agent by using **high-quality positive examples** that represent your organization’s brand voice and tone. A combination of a definitive style guide and strong writing samples is sufficient to begin tuning.

Before tuning, prepare the following items:

1. **Clear goals** - Define what the ideal rewritten output should look like.
1. **Sample files** - Provide at least **20 files** that reflect your brand voice. Supported formats include:
   - .txt  
   - .pdf  
   - .docx  
   - .md  
   - .html or .htm  
   - .csv  
1. **Style guide** - A comprehensive document describing tone, voice, and writing rules.

## Context tuning

Context tuning teaches the agent how to apply your style rules consistently across rewriting tasks.

### Define goals and tasks

In the Context Tuning experience, define how the agent should behave when rewriting content. Update the default goal prompt to reflect your desired outcomes.

The following are goal examples:

- The agent should rewrite content so it aligns with the Microsoft tone and voice.  
- The agent must preserve meaning and intent while improving clarity and consistency.

Rewrites should:

- Align with the Microsoft style guide
- Use tone-appropriate language
- Preserve meaning and intent
- Maintain approximate length

### Optional guidelines

Add optional guidelines to specify extra constraints or quality indicators the agent must follow.

## Business category or industry

Specify one or more categories that represent the agent's usage context, such as:

- Technical Content Writer
- Legal
- Human Resources
- Project Management

These categories help the system interpret goals and generate relevant evaluations.

## File upload for testing

Upload example input files that represent typical content the agent processes at runtime. Use these files to simulate evaluations.

> [!TIP]  
> You don't need to upload ideal output samples during context tuning.

## Review clarifying questions

The system generates clarifying questions that reflect how the agent interprets its task. Review and refine these questions to ensure they align with your intended behavior.

## Review metrics

Metrics define how the system evaluates output quality.

During evaluation, the system generates a benchmark by using sample inputs.

## Related content

- [Copilot Tuning overview](copilot-tuning-overview.md)
