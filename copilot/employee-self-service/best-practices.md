---
title: Best practices for deploying the Employee Self-Service agent
f1.keywords: NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 10/29/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Best practices to employ when preparing to deploy Employee Self-Service agent.
appliesto:
- ✅ Microsoft 365 Copilot
---

# Planning for a successful Employee Self-Service agent deployment

Deploying the Employee Self-Service Agent successfully takes more than just installing the technology. It’s about bringing the right people together, aligning on goals, and completing the deployment successfully.

Agent deployment success depends on a cross-functional team working across HR, IT, and business leadership. Each persona plays a distinct role in getting the deployed, adopted, and delivering measurable impact.

## Personas and roles for deploying and using the Employee Self-Service agent

|Agent Persona                   |Real-world role                                                 |What they do |
|--------------------------------|----------------------------------------------------------------|-------------|
|HR/IT stakeholder               |HR director, IT lead, Employee experience owner.                |Defines business goals, prioritizes use cases, and ensures the agent delivers meaningful impact. |
|Business decision maker (BDM) |VP or GM of digital transformation or employee experience.      |Approves the deployment and ensures the agent aligns with company priorities, compliance, and risk requirements. |
|Implementation manager (IM)   |Program or project manager resposible for rollout execution.    |Manages project timelines, stakeholders, and adoption readiness. They keep the deployment on-track. |
|Tech admin                    |Power Platform admin, Copilot Studio maker, or Integration SME. |Installs, configures, and maintains the Employee Self-Service agent. Ensures integration, access, and system readiness. |
|Champion                      |Change management lead or Employee Self-Service agent advocate. |Drives awareness, adoption, and excitement around the Employee Self-Service agent. Collects feedback to improve rollout success. |
|End user                      |Employees using the agent day-to-day.                            |Uses the agent in their daily work, validating its value through real-world usage and feedback. |

## The stages of Employee Self-Service agent deployment

Agent deployment typically moves through four main stages, from readiness to rollout. Each stage has specific owners, goals, and potential pitfalls.

XXX We need more than little overview sentences here. We need technical meat for this section to be relevant. Link out to relevant articles at least? Making note here.

### Stage 1: Initiate

Stakeholders: HR, IT, BDM

Deploying the agent begins by assessing readiness:

- Defining use cases
- Aligning on goals
- Organizing the right team to own deployment

### Stage 2: Deploy

Stakeholders: IM, Tech admin

Install and configure the agent in the Power Platform environment. This stage is where you build the technical foundation.

### Stage 3: Pilot

Stakeholders: IM, Champion, End-users

A small group tests the agent, providing early feedback and validating value.

### Stage 4: Rollout

Stakeholders IM, Champion, End-users

Broad adoption of the agent, driving awareness, gathering feedback, and continuously improving the experience.

## FAQ

### Do I need to license everone in my organization to use the Employee Self-Service agent?

No. Start by licensing your implementation and pilot users, the stakeholders, admins, and early adopters who configure and validate the agent. As adoption grows, scale licenses gradually based on usage and feedback.

### What licensing is required to use the Employee Self-Service agent, and how is usage billed?

Users with Microsoft 365 Copilot licenses can access the agent at no additional cost. For users without a Microsoft 365 Copilot license, the agent is available on a pay-as-you-go (PAYG) basis, with usage metered through Copilot Studio.

> [!IMPORTANT]
> For the latest information on licensing, see [this article](/microsoft-copilot-studio/billing-licensing).

### If premium Power Platform connectors are needed (for example, ServiceNow), does the Microsoft 365 Copilot license cover setup, or are extra licenses required?

There's no additional charge for agent users with an M365 Copilot Premium license to retrieve or update data from third-party systems through Power Platform Connectors.

### How can I show value quickly with the Employee Self-Service agent?

Start with knowledge retrieval scenarios, like surfacing HR or IT policies from SharePoint. These require minimal setup and deliver immediate impact while you plan more advanced task automation later.

### How do we maintain momentum with agent deployment?

Set clear success criteria before you start. Define measurable goals (such as ticket reduction, faster response times, or improved satisfaction). These criteria tell you when it’s time to move from pilot to production rollout.

### Who should I include in the initial pilot?

Start with a focused group of early adopters, such as HR or IT support teams, people operations, or helpdesk staff who regularly answer employee questions. Their hands-on feedback is essential for refining before full rollout.

### Can I use the Employee Self-Servie agent even if my organization doesn’t use Microsoft 365 Copilot yet?

Yes. Employee Self-Service agent can still be deployed using Copilot Studio’s pay-as-you-go (PAYG) model. This option allows you to experiment and prove value before committing to full Copilot licensing.

### What should I track to measure agent success?

Focus on time-to-value metrics and employee engagement signals:

- Reduced ticket volume or average handle time.
- Increased self-service resolution rates.
- Number of daily active users.
- Sentiment or satisfaction feedback from employees.

These metrics demonstrate ROI and build the case for broader adoption.
