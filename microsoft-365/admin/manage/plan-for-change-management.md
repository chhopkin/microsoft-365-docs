---
title: "Plan for change management in Microsoft 365"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 03/13/2026
ms.reviewer: pamelaar, gsaini
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
search.appverid: MET150
description: "Learn how to plan for change management in Microsoft 365."
appliesto: 
- Microsoft 365 admin center
---

# Plan for change management in Microsoft 365

Microsoft 365 is changing faster and more continuously than ever, especially as AI and Copilot capabilities roll out across workloads. For IT admins, this means fewer discrete release moments and a steady flow of updates that can affect users, support teams, and governance. A *frontier firm* is an organization that is designed to operate in this environment of continuous change, where updates are expected and managed as part of normal operations rather than treated as exceptions. Unlike traditional change management models—which rely on reactive planning, long validation cycles, and broad delays to reduce risk—frontier firms plan for change proactively and harness AI into their everyday workflows to accelerate decision-making, foster innovation, and prioritize governance, security, and compliance. Microsoft’s modern change management approach supports this shift by providing earlier planning signals, clearer impact communication, and flexible release options, helping you and your organization manage risk, meet compliance requirements, and adopt new Microsoft 365 features with confidence.

This modern change management model for Microsoft 365 helps your Frontier Firm stay on top of major updates in the following ways:

- Manage how your organization experiences major feature updates with audience-based release phases aligned to your organization’s workflows
  - Opt into the release of new major features for testing and validation before releasing to the rest of your organization
- Easily understand feature updates with new Message center enhancements, such as:
  - Feature update announcements at the time of availability
  - Bullet point summaries that present key information in a clear, scannable format
  - Embedded links that connect to curated supplemental resources
  - Purpose-specific post structure to explain impact and actions to take (including for compliance)
- Connect AI tools to the Microsoft Release Communications MCP Server to instantly access trusted, up-to-date Microsoft 365 and Azure feature release information using natural language
- Use AI‑powered access to Message center and Service Health insights to streamline identification of changes and issues and help teams act with clearer context
- Track upcoming changes with the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to understand planned features and expected timing

## Customize your organization’s release experience for Microsoft 365

From the Microsoft admin center, you can choose between two general availability release channels for Microsoft 365 updates: Standard release and Deferred release.

With Standard release, your organization receives new features as soon as they’re generally available. You can immediately manage individual policies and settings for these new features. Your organization is on standard release by default.
IT admins who need extra time to do security reviews and compliance checks before releasing Microsoft 365 deferred-capable features to their organization might want to assign most users in your organization to Deferred release. To get up to 30 days to prepare for new Microsoft 365 deferred-capable features, switch to deferred release. After 30 days, generally available Microsoft 365 features appear to your users. For either standard or deferred release channel, you can manage individual policies and settings for these new features.

If you want to do early experimentation or validation before the broad rollout of M365 features, you can opt-in users for Targeted release or enable the Frontier program.

For more information about release options and how to configure them, see [Configure release options for Microsoft 365 features](configure-release-options.md).

### Compare release options for Microsoft 365 services

The following table compares the release options available for Microsoft 365 features to help you understand the differences and choose the right approach for your organization’s needs.

| Release audience | Primary purpose | Feature readiness | Key considerations for IT admins |
| ----- | ----- | ----- | ----- |
| **Frontier** | Early experimentation and feedback | Pre‑GA, not fully supported | Features may change or be removed, are not guaranteed to reach GA, and do not include support, stability, or SLA commitments equivalent to GA |
| **Targeted release** | Validation before broad rollout | Pre‑GA validation | Not all features are guaranteed to reach GA; functionality may still evolve; intended for readiness and validation, not reliance on fully supported GA features |
| **Standard release** | Default GA rollout | Fully supported GA features | Features are supported, communicated through Message Center and release notes, and expected to remain available under standard lifecycle policies |
| **Deferred release** | Delayed GA for additional preparation | Fully supported GA features (delayed) | Same functionality as Standard release, with timing delayed (up to \~30 days) to support governance and compliance readiness |

## Use the updated Message Center interface

Enhance your organization’s ability to deliver timely, relevant, and actionable communications to users with our launch-focused release announcement hub. By integrating bullet-point summaries and supplemental resources into Message Center, you can deliver more applicable and accessible information to your users.

- Stay informed with concise announcements at launch that feature bullet-point summaries and direct links to resources
- Incorporate a structured and more effective messaging format that includes change descriptions, rollout timelines, affected users and platforms, action checklists, and compliance impacts (including data handling)

For more details on the updated layout and information on keeping track of changes using the Microsoft 365 Message Center, see [Message center in the Microsoft 365 admin center](message-center.md).

## Enable AI clients to retrieve product release information with MRC MCP server

By integrating the MRC MCP Server with your AI tools, you can automate the retrieval of release information and generate tailored communications for your organization. For information on how to start using MRC MCP server, see [Get started with Release Communications MCP Server](mrc-mcp.md).

## Related articles

[Configure release options for Microsoft 365 features](configure-release-options.md)

[Track new and changed features in the Microsoft 365 Message center](message-center.md)

[Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md)
