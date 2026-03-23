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
description: "Learn how to manage continuous change in Microsoft 365."
appliesto: 
- Microsoft 365 admin center
---

# Manage continuous change in Microsoft 365

Microsoft 365 is changing faster and more continuously than ever, especially as AI and Copilot capabilities roll out across workloads. For IT admins, this means fewer discrete release moments and a steady flow of updates that can affect users, support teams, and governance. A *frontier firm* is an organization that is designed to operate in this environment of continuous change, where updates are expected and managed as part of normal operations rather than treated as exceptions. Unlike traditional change management models—which rely on reactive planning, long validation cycles, and broad delays to reduce risk—frontier firms plan for change proactively and harness AI into their everyday workflows to accelerate decision-making, foster innovation, and prioritize governance, security, and compliance. Microsoft’s modern change management approach supports this shift by providing earlier planning signals, clearer impact communication, and flexible release options, helping you and your organization manage risk, meet compliance requirements, and adopt new Microsoft 365 features with confidence.

> **Alternative intro:**
> Organizations now operate in an environment of continuous change. Instead of relying on reactive planning, lengthy validation cycles, and broad release delays, IT admins can enable their organizations to plan for change proactively and use AI enabled tools to help teams assess impact, prioritize work, and make informed decisions. Microsoft’s AI supported approach to change management helps organizations apply planning signals, understand impact more clearly, and use flexible release options. Together, these capabilities help IT admins manage risk, meet compliance requirements, and adopt Microsoft 365 features with confidence.

This modern change management model for Microsoft 365 helps your Frontier Firm stay on top of major updates in the following ways:

- Connect AI tools to the Microsoft Release Communications (MRC) Model Context Protocol (MCP) Server to instantly access trusted, up-to-date Microsoft 365 and Azure feature release information using natural language
- Use AI‑powered access to Message center and Service Health insights to streamline identification of changes and issues and help teams act with clearer context
- Manage how your organization experiences major feature updates with audience-based release phases aligned to your organization’s workflows
  - Opt into the release of new major features for testing and validation before releasing to the rest of your organization
  - Delay the release of generally available (GA) major features for up to 30 days for your organization or specific users, giving you more time to prepare for changes before they release to your users
- Easily understand feature updates with new Message center enhancements, such as:
  - Feature update announcements at the time of availability
  - Bullet point summaries that present key information in a clear, scannable format
  - Embedded links that connect to curated supplemental resources
  - Purpose-specific post structure to explain impact and actions to take (including for compliance)
- Track upcoming changes with the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to understand planned features and expected timing

## Communication channels for Microsoft 365 updates - alternative layout vs list

The following table shows various communication channels we have that you can use to help manage change:

| Communication channel | Description | Documentation |
| ----- | ----- | ----- |
| Microsoft 365 Roadmap | - Understand what features are coming, when they’re expected to release, and which environments they apply to.<br/>- Provides early planning signals that complement Message center announcements and supports proactive change management across Microsoft 365. | [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) |
| Message center | - Learn about official service announcements and feature changes.<br/>- Read these messages in the Microsoft 365 admin center, the admin mobile app, or receive a weekly digest in email.<br/>- Share these messages with others in your organization when you see a message someone else should act on. | [Message center in the Microsoft 365 admin center](message-center.md) |
| Microsoft 365 Insider Blog for apps | Get updates and insights about Microsoft 365 features as they release to preview channels on Windows, the web, Mac, iOS, and Android. | [Microsoft 365 Insider Blog - Microsoft Community Hub](https://techcommunity.microsoft.com/category/microsoft365/blog/microsoft365insiderblog) |
| Microsoft 365 Insider program (preview) | Provides early visibility into upcoming Microsoft 365 features so IT admins can evaluate changes, plan deployments, and gather feedback before features reach general availability. | [Microsoft 365 Insider program for Business](/microsoft-365-apps/insider/deploy/options) |

## Release settings - alternative layout vs list

The following table displays various features you can integrate into your workflow to manage change:

| Feature | Description | Documentation |
| ----- | ----- | ----- |
| Release Communications MCP Server | Connect AI tools to the MRC MCP Server to instantly access trusted, up-to-date Microsoft 365 and Azure feature release information using natural language | [Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md) |
| Release options | - Configure general availability release settings in the Microsoft 365 admin center based on your organizational readiness for new features with Standard or Deferred release options<br/> - Opt into the release of new features for testing and validation before releasing to the rest of your organization with Targeted release | [Configure release options for Microsoft 365](configure-release-options.md) |
| Frontier program | - Gain early access to select AI and Microsoft 365 Copilot features before general availability<br/> - Designed for exploration and feedback, and features might change or might not reach general availability. | [Frontier: Try what's next in AI](https://adoption.microsoft.com/copilot/frontier-program/)<br/>[Microsoft Adoption - Getting Started with Frontier](https://adoption.microsoft.com/files/copilot/Frontier_Getting-started-guide.pdf) |

## Customize your organization’s release experience for Microsoft 365

From the Microsoft admin center, you can choose between two *general availability* release audiences for Microsoft 365 updates: Standard release and Deferred release.

For access to major features in general availability, you can choose either Standard release or Deferred release for your organization and individual users. With Standard release, your organization receives new features as soon as they’re generally available. You can immediately manage individual policies and settings for these new features. Your organization is on standard release by default.

If your organization requires additional time to review features, such as for security reviews or compliance checks, you can use Deferred release to delay the rollout of major Microsoft 365 features. All major Microsoft 365 updates are deferred‑capable. If you assign IT admins and testers to Standard release and the rest of your organization to Deferred release, you get up to 30 days to evaluate and prepare for new features before they’re released to users in your organization. After the deferral period ends, features that are generally available are automatically released.

If you want to do early experimentation or validation before the broad rollout of M365 features, you can opt-in users for Targeted release or enable the Frontier program.

For more information about release options and how to configure them, see [Configure release options for Microsoft 365 features](configure-release-options.md).

### Compare release audiences for Microsoft 365 services

The following table compares the release options available for Microsoft 365 features to help you understand the differences and choose the right approach for your organization’s needs.

| Release audience | Primary purpose | Feature readiness | Key considerations for IT admins |
| ----- | ----- | ----- | ----- |
| **Frontier** | Early experimentation and feedback | Pre‑GA, not fully supported | Features may change or be removed, are not guaranteed to reach GA, and do not include support, stability, or SLA commitments equivalent to GA |
| **Targeted release** | Validation before broad rollout | Pre‑GA validation | Not all features are guaranteed to reach GA; functionality may still evolve; intended for readiness and validation, not reliance on fully supported GA features |
| **Standard release** | Default GA rollout | Fully supported GA features | Features are supported, communicated through Message Center and release notes, and expected to remain available under standard lifecycle policies |
| **Deferred release** | Delayed GA for additional preparation | Fully supported GA features (delayed) | Same functionality as Standard release, with timing delayed (up to ~30 days) to support governance and compliance readiness |

## Enable AI clients to retrieve product release information with MRC MCP server

AI-enabled organizations use intelligent tooling to accelerate their internal processes. By integrating the MRC MCP Server with your AI tools, you can connect to the latest release information for Microsoft 365 and Azure updates to create the infrastructure for AI-assisted reasoning over upcoming changes, priorities, and business impact.

For information on how to start using MRC MCP server, see [Get started with Release Communications MCP Server](mrc-mcp.md).

## Use the updated Message center interface

Enhance your organization’s ability to deliver timely, relevant, and actionable communications to users with our launch-focused release announcement hub. With the Message center, you can deliver more applicable and accessible information to your users.

- Stay informed with concise announcements at launch that feature bullet-point summaries and direct links to resources
- Incorporate a structured and more effective messaging format that includes change descriptions, rollout timelines, affected users and platforms, action checklists, and compliance impacts (including data handling)

For more details on the updated layout and information on keeping track of changes using the Microsoft 365 Message center, see [Message center in the Microsoft 365 admin center](message-center.md).

## Use the Microsoft 365 Roadmap to plan and manage change

The Microsoft 365 roadmap helps IT admins understand what features are coming, when they’re expected to release, and which environments they apply to. It provides early planning signals that complement Message center announcements and supports proactive change management across Microsoft 365.

Use the roadmap to do the following actions that help your organization stay on top of changes:

- Track upcoming features before they reach general availability
- Identify potential impacts to users, governance, and compliance
- Plan validation, communications, and support readiness
- Align feature timing with your organization’s release strategy

For more information, see [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

## Related articles

[Configure release options for Microsoft 365 features](configure-release-options.md)

[Track new and changed features in the Microsoft 365 Message center](message-center.md)

[Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md)
