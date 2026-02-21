---
title: Copilot Tuning Document Validation Agent
description: Learn how to use and tune the Document Validation agent in Microsoft 365 Copilot to review documents for compliance with organizational guidelines, policies, branding, and regulatory requirements.
author: david-salas
ms.author: dsalasbarran
manager: calvind
ms.reviewer: riyazp
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

# Copilot Tuning Document Validation Agent

The **Document Validation agent** for Microsoft 365 Copilot helps organizations review documents for compliance with internal guidelines, policies, branding standards, and regulatory requirements. It automates manual review workflows by identifying noncompliant content, categorizing violations by risk, and providing actionable remediation guidance directly within documents.

This agent is designed for high‑stakes and repeatable review scenarios where accuracy, consistency, and auditability are critical.

> [!IMPORTANT]
> Copilot Tuning is currently available in the [Frontier early access program](https://adoption.microsoft.com/copilot/frontier-program/). Frontier includes early access to experimental features, which means features are subject to change. For more information, see [What is Frontier?](https://support.microsoft.com/topic/what-is-frontier-17c671e0-1906-4d9d-892c-68e11fbff4c7).

## What the Document Validation agent does

The Document Validation agent:

- Extracts rules automatically from a provided rulebook or guidelines document
- Validates documents against those rules
- Identifies and categorizes violations by risk level (Critical or Advisory)
- Provides explanations and suggested fixes
- Inserts findings as comments in Microsoft Word documents

By standardizing document reviews, the agent reduces review time, improves consistency, and helps mitigate compliance risk across teams.

## Common scenarios

Use the Document Validation agent in workflows that require documents to follow strict or repeatable rules, such as:

- Contract reviews (supplier contracts, statements of work)
- Legal and compliance reviews
- Regulatory disclosures
- Financial or healthcare compliance checks
- Brand and policy adherence for customer-facing content

## Supported capabilities and limitations

The following features are supported:

- Validation against user-provided rulebooks.
- Automatic rule extraction with human review.
- Risk-based categorization with explanations.
- Inline comments with suggested fixes.
- Single document validation per prompt.

The following features aren't supported:

- Multimodal analysis (images, charts, scanned documents).
- Validation of multiple documents in a single prompt.
- Validation without a provided rulebook.

The following file formats are supported:

- .docx  
- .txt  
- .html  

The agent doesn't support other formats, including PowerPoint, images, handwritten documents, and scanned files.

## Get started

To use the Document Validation agent, you need a **rulebook or guidelines document** that defines the standards your document should follow.

To use the agent:

1. In Microsoft 365 Copilot chat, start a new chat with the Document Validation agent.
1. Provide a rulebook (.docx or .txt) and the document you want to validate.
1. The agent extracts rules from the rulebook.
1. The agent validates the document against each rule.
1. The agent returns a document with inline comments that include:
   - Identified violations
   - Risk level (Critical or Advisory)
   - Explanation and suggested remediation

## Tuneable agent overview

The Document Validation agent is **tuneable**, so your organization can adapt it to your specific review and compliance needs.

By tuning the agent, you can:

- Persist rules and guidelines across sessions
- Customize tone and severity of feedback
- Improve accuracy with domain-specific examples
- Evaluate agent quality against scenario-specific goals

Tuneable agents support **goal-based evaluations**, so you can measure success using metrics aligned to your organization’s priorities, not just generic accuracy scores.

## Tune Context

**Tune Context** allows you to customize the agent’s behavior without full model fine-tuning. It's ideal for teams that want persistent rules and consistent review behavior with minimal setup.

Use Tune Context when:

- You want rules baked into the agent for repeated use
- You want to review and edit extracted rules
- You want to configure tone, verbosity, and risk levels
- You don't yet have sufficient data for model fine-tuning

With Tune Context, you can:

- Save rulebooks, policies, or guidelines as persistent context
- Review, edit, add, or remove extracted rules
- Assign risk levels (Critical or Advisory)
- Configure tone (formal, friendly, advisory)
- Rerun evaluations and update context over time

### Best practices for rulebooks

For best results:

- Use clear, concise, and unambiguous rules
- Avoid vague or open-ended guidance
- Include explicit criteria where possible
- Mark high-impact rules as **Critical**
- Avoid excessively large rule sets to reduce latency

## Tune Model

**Tune Model** is the most advanced customization option. It fine-tunes the underlying model using your organization’s data to achieve higher precision and recall.

Use Tune Model when:

- Rules are complex or nuanced
- The scenario involves high regulatory or legal risk
- Context tuning doesn't provide sufficient accuracy
- You have sufficient training data

### Required data

- **Rulebook**: Clear rules or policies used for training and evaluation
- **Golden examples**: At least 50 violation-free documents that demonstrate ideal compliance

### Evaluation rubrics

Model-tuned agents are evaluated using:

- Recall for Critical violations
- Precision for Advisory violations
- User-defined goals and metrics from Tune Context

### Limitations of model-tuned agents

- Rules can't be modified after fine-tuning
- Retraining isn't currently supported
- Multimodal validation isn't supported
- Only one document can be validated per prompt

## Evaluating tuneable agents

At each tuning stage, the agent is evaluated using:

- User-defined goals
- Sample documents
- Autogenerated subgoals and metrics
- System-generated evaluation data

Evaluation results show quality scores and delta improvements between tuning stages, helping you decide when the agent is ready to publish.

## Agent sharing and governance

A tuned Document Validation agent is saved as a specialized agent and can be shared across the organization.

- Only the agent owner can tune or modify the agent
- Other users can use the agent but can't change its configuration
- All data remains within Microsoft 365 tenant boundaries

## FAQ

### Can I validate multiple documents at once? 

No. Each document must be validated in a separate prompt.

### Can I update rules after tuning? 

Context-tuned agents can be updated. Model-tuned agents can't be modified after fine-tuning.

### Does the agent support numeric validations?

Yes, when rules include numeric thresholds.

### What happens if my rulebook is large?  

Large rulebooks might increase latency during rule extraction and validation.

## Related content

- [Copilot Tuning overview](copilot-tuning-overview.md)