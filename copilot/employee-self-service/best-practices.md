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

Deploying the Employee Self-Service (ESS) Agent successfully takes more than just installing the technology. It’s about bringing the right people together, aligning on goals, and completing the deployment successfully.

ESS deployment success depends on a cross-functional team working across HR, IT, and business leadership. Each persona plays a distinct role in getting ESS deployed, adopted, and delivering measurable impact.

## Personas and roles for deploying and using ESS

|ESS Persona                   |Real-world role                                                 |What they do |
|------------------------------|----------------------------------------------------------------|-------------|
|HR/IT stakeholder             |HR director, IT lead, Employee experience owner.                |Defines business goals, prioritizes use cases, and ensures ESS delivers meaningful impact. |
|Business decision maker (BDM) |VP or GM of digital transformation or employee experience.      |Approves the deployment and ensures ESS aligns with company priorities, compliance, and risk requirements. |
|Implementation manager (IM)   |Program or project manager resposible for rollout execution.    |Manages project timelines, stakeholders, and adoption readiness. They keep the deployment on-track. |
|Tech admin                    |Power Platform admin, Copilot Studio maker, or Integration SME. |Installs, configures, and maintains ESS. Ensures integration, access, and system readiness. |
|Champion                      |Change management lead or ESS advocate.                         |Drives awareness, adoption, and excitement around ESS. Collects feedback to improve rollout success. |
|End user                      |Employees using ESS day-to-day.                                 |Uses ESS in their daily work, validating its value through real-world usage and feedback. |

## The stages of ESS deployment

ESS deployment typically moves through four main stages, from readiness to rollout. Each stage has specific owners, goals, and potential pitfalls.

XXX We need more than little overview sentences here. We need technical meat for this section to be relevant. Link out to relevant articles at least? Making note here.

### Stage 1: Initiate

Stakeholders: HR, IT, BDM

Deploying ESS begins by assessing readiness:

- Defining use cases
- Aligning on goals
- Organizing the right team to own deployment

### Stage 2: Deploy

Stakeholders: IM, Tech admin

Install and configure ESS in the Power Platform environment. This stage is where you build the technical foundation.

### Stage 3: Pilot

Stakeholders: IM, Champion, End-users

A small group tests ESS, providing early feedback and validating value.

### Stage 4: Rollout

Stakeholders IM, Champion, End-users

Broad adoption of ESS, driving awareness, gathering feedback, and continuously improving the experience.

## FAQ

### Do I need to license everone in my organization to use ESS?

No. Start by licensing your implementation and pilot users, the stakeholders, admins, and early adopters who configure and validate ESS. As adoption grows, scale licenses gradually based on usage and feedback.

### What licensing is required to use the ESS Agent, and how is usage billed?

Users with Microsoft 365 Copilot licenses can access the ESS Agent at no additional cost. For users without a Microsoft 365 Copilot license, the ESS Agent is available on a pay-as-you-go (PAYG) basis, with usage metered through Copilot Studio.

> [!IMPORTANT]
> For the latest information on licensing, see [this article](/microsoft-copilot-studio/billing-licensing).

### If premium Power Platform connectors are needed (for example, ServiceNow), does the Microsoft 365 Copilot license cover setup, or are extra licenses required?

There's no additional charge for ESS users with an M365 Copilot Premium license to retrieve or update data from third-party systems through Power Platform Connectors.

### How can I show value quickly with ESS?

Start with knowledge retrieval scenarios, like surfacing HR or IT policies from SharePoint. These require minimal setup and deliver immediate impact while you plan more advanced task automation later.

### How do we maintain momentum with ESS deployment?

Set clear success criteria before you start. Define measurable goals (such as ticket reduction, faster response times, or improved satisfaction). These criteria tell you when it’s time to move from pilot to production rollout.

### Who should I include in the initial pilot?

Start with a focused group of early adopters, such as HR or IT support teams, people operations, or helpdesk staff who regularly answer employee questions. Their hands-on feedback is essential for refining before full rollout.

### Can I use ESS even if my organization doesn’t use Microsoft 365 Copilot yet?

Yes. ESS can still be deployed using Copilot Studio’s pay-as-you-go (PAYG) model. This option allows you to experiment and prove value before committing to full Copilot licensing.

### What should I track to measure ESS success?

Focus on time-to-value metrics and employee engagement signals:

- Reduced ticket volume or average handle time.
- Increased self-service resolution rates.
- Number of daily active users.
- Sentiment or satisfaction feedback from employees.

These metrics demonstrate ROI and build the case for broader adoption.
