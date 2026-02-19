---
title: "Microsoft 365 Copilot Tuning Overview (preview)"
f1.keywords:
author: lauragra
ms.author: lauragra
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
description: "Learn how to use Microsoft 365 Copilot Tuning to create task-specific fine-tuned LLMs based on your tenant data."
---

## Microsoft 365 Copilot Tuning overview (preview)

Microsoft 365 Copilot Tuning is an AI customization capability that enables organizations to create task-specific Copilot agents by tuning large language models (LLMs) with their own organizational data. Tuning allows agents to produce responses that reflect an organization’s domain knowledge, terminology, tone, and quality standards.

Unlike general-purpose AI experiences, tuned agents are designed for specific, repeatable tasks. Because they operate entirely within the Microsoft 365 tenant, organizational data remains protected by existing security, compliance, and governance controls.

This article provides an overview of Copilot Tuning, including key capabilities, supported scenarios, tuning concepts, and administrative governance.

> [!NOTE]
> Copilot Tuning is currently in preview. For requirements and enrollment details, see the [Copilot Tuning admin guide](copilot-tuning-admin-guide.md).

## Key capabilities

Copilot Tuning enables organizations to build AI experiences that align closely with their business needs. It offers the following features:

- **No-code customization** - Create tuned agents using templates in Agent Builder without coding or data science expertise. Business users and domain experts can guide tuning using curated examples and organizational content.

- **Task-specific agents** - Build agents optimized for high-value scenarios such as question answering, document generation, summarization, validation, and style alignment. Tuned agents produce outputs that reflect organizational vocabulary, structure, and expectations.

- **Improved efficiency and consistency** - By embedding organizational knowledge into Copilot, tuned agents can reduce the time required for complex content tasks while improving consistency and adherence to internal standards.

- **Integration with Microsoft 365 data** - Tuned agents can use selected organizational content and reason over live enterprise data through Microsoft Graph, ensuring responses are grounded in up-to-date information.

- **Enterprise-grade security** - All tuning operations occur within the Microsoft 365 trust boundary. Tuned agents honor access control lists (ACLs) from the training data and only return information that users are authorized to access.

## Supported scenarios

Copilot Tuning supports a set of task-oriented agent templates.

### Document writing

Document writing agents generate structured, long-form documents based on organizational templates, examples, and standards. These agents can produce first drafts of content such as proposals, contracts, policies, and technical documentation while adhering to formatting and compliance requirements.

### Document summarization

Document summarization agents generate tailored summaries based on tone, audience, purpose, and length. Organizations can tune these agents to reflect internal summarization standards and emphasize information that is most relevant for their use cases.

### Expert answers (Q&A)

Expert answers agents provide domain-specific responses by grounding answers in organizational content. These agents support scenarios that require deep search across large datasets, strict policy guardrails, or specialized terminology.

### Document validation

Document validation agents review documents for compliance with organizational guidelines, policies, branding standards, and regulatory requirements. They identify issues, categorize risks, and provide actionable feedback directly within documents.

### Style editor

Style editor agents refine drafts to align with an organization’s brand voice, tone, and writing guidelines. These agents help ensure consistency across content produced by different users and teams.

### Optimization agent

Optimization agents assist with business optimization problems such as resource allocation, task assignment, and planning. Users define objectives and constraints, and the agent produces explainable solutions based on uploaded data and organizational rules.

## How agent tuning works

Each agent template includes a predefined inference workflow that specifies the foundation model, instructions, grounding approach, tool usage, and output generation. When you create an agent from a template, you start with this default configuration.

In many cases, the base agent meets quality expectations without further customization. If improvements are needed, tuning can be applied across several dimensions.

### Context tuning

Context tuning defines the agent's goals and success criteria. You provide the primary task, domain, and representative examples. Based on this input, the system proposes subgoals and evaluation rubrics that you can review and refine. These rubrics establish a measurable baseline for assessing agent performance.

### Model tuning

Model tuning improves reasoning and output quality by updating the model using supervised fine-tuning or reinforcement learning techniques. Training data and evaluation rubrics guide the tuning process to align the agent’s behavior with organizational expectations.

Model tuning runs asynchronously while users continue to access the existing agent. When tuning completes, evaluation results are provided, and the updated agent can be published if results meet expectations.

### Tool tuning

Tool tuning extends agent capabilities by integrating more tools or subagents. For example, you can compose agents to perform research, enforce validation rules, or align tone before delivering a final response.

Tuning is iterative. Organizations should monitor real-world usage, incorporate feedback, and periodically update context, data, or rules as requirements evolve.

## Using tuned agents

After creation or tuning, agents can be shared with eligible users across the organization. Users interact with tuned agents through supported Microsoft 365 Copilot experiences, such as the Microsoft 365 Copilot app or Copilot Chat in Microsoft Teams.

Tuned agents provide the following benefits:

- Increased productivity through faster content creation and analysis  
- Improved accuracy by grounding responses in organizational data  
- Consistent outputs aligned with internal standards  
- Broader access to organizational knowledge across teams

### Best practices

Apply the following best practices to make the best use of tuned agents:

- Understand the agent’s scope and limitations.  
- Use clear, specific prompts. 
- Provide starter prompts to guide users.  
- Refine outputs through multi-turn interactions.  
- Follow organizational security and compliance policies. 
- Encourage user feedback to improve agent quality over time.  

## Admin settings and governance

Copilot Tuning includes tenant-wide governance controls managed in the Microsoft 365 admin center under **Copilot > Copilot Tuning settings**.

### Availability controls

Admins can configure who has access to tuning via the following availability settings:

- **Enable for all users** (default for eligible tenants)  
- **Enable for specific users or groups**  
- **Disable tuning** for the entire tenant  

When access is limited to specific users or groups, eligible users can request access through in-product prompts, subject to admin approval.

### Security and compliance

Tuned models are trained in tenant-isolated environments and inherit permissions from the training data. No customer data is transmitted to external services during training or inference. Microsoft Graph data returned in responses continues to honor document-level permissions.

Admins can view, block, disable, or delete tuned agents from the Agent 365 portal. Deleting an agent also removes its associated tuned model and snapshot data.

Microsoft might perform service-managed upgrades to move agents to newer model architectures. Previous versions might be retained temporarily to ensure continuity and are automatically deleted after a defined retention period.

## Data handling and compliance considerations

Copilot Tuning adheres to Microsoft 365 privacy, security, and data protection commitments. Snapshot copies of selected SharePoint content are created solely for tuning purposes and remain within the Microsoft 365 service boundary.

Organizations are responsible for ensuring that their use of Copilot Tuning complies with applicable data protection, privacy, and intellectual property laws, including obligations under regulations such as GDPR and CCPA.

For tenants with Advanced Data Residency (ADR), Copilot Tuning is not enabled by default during preview. ADR customers may choose to participate by waiving ADR requirements through their Microsoft account team.

## Related content

- [Agents for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agents-overview)
- [Build agents with Copilot Studio agent builder](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-build)
- [Copilot Studio overview](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)

