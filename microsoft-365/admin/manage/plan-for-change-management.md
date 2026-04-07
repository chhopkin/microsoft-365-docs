---
title: "Modern change management for Microsoft 365 - Overview"
f1.keywords:
- CSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 04/06/2026
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
description: "IT admins can enable their organizations to proactively plan for change using AI-enabled tools to help teams assess impact, prioritize work, and make informed decisions."
appliesto: 
- Microsoft 365 admin center
---

# Modern change management for Microsoft 365 - Overview

Organizations now operate in an environment of continuous change. Managing continuous service change using traditional management models can be a challenge for IT admins trying to keep pace.

With new and modern change management solutions, IT admins can enable their organizations to proactively plan for change using AI enabled tools to help teams assess impact, prioritize work, and make informed decisions. Modern change management capabilities help IT admins manage risk, meet compliance requirements, and adopt Microsoft 365 features with confidence.

This modern change management model for Microsoft 365 helps your organization stay on top of major updates in the following ways:

- Connect AI tools to the MRC MCP Server to instantly access trusted, up-to-date Microsoft 365 and Azure feature release information using natural language
- Use AI‑powered access to Message center and Service Health insights to streamline identification of changes and issues and help teams act with clearer context
- Manage how your org experiences **major** feature updates  
- Control feature delivery by using audience-based release phases aligned to your organization’s workflows
- Configure general availability release settings in the Microsoft 365 admin center based on your organizational readiness for new features with Standard or Deferred release options
- Opt into the release of new features for testing before releasing to the rest of your organization
- Easily understand feature updates with new Message center enhancements, such as:
  - New **Timing of change** column allows you to sort and filter posts by when a rollout is planned
  - Feature update announcements at the time of availability
  - Bullet point summaries that present key information in a clear, scannable format
  - Embedded links that connect to curated supplemental resources
  - Purpose-specific post structure to explain impact and actions to take (including for compliance)
- Track upcoming changes with the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to understand planned features and expected timing

## Communication channels for Microsoft 365 updates

The following table shows various communication channels we have that you can use to help manage change:

| Communication channel | Description | Documentation |
| ----- | ----- | ----- |
| Microsoft 365 Roadmap | - Understand what features are coming, when they’re expected to release, and which environments they apply to.<br/>- Provides early planning signals that complement Message center announcements and supports proactive change management across Microsoft 365. | [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) |
| Message center | - Learn about official service announcements and feature changes.<br/>- Read these messages in the Microsoft 365 admin center, the admin mobile app, or receive a weekly digest in email.<br/>- Share these messages with others in your organization when you see a message someone else should act on. | [Message center in the Microsoft 365 admin center](message-center.md) |

## Release settings

The following table displays various features you can integrate into your workflow to manage change:

| Feature | Description | Documentation |
| ----- | ----- | ----- |
| Microsoft Release Communications (MRC) Model Context Protocol (MCP) Server | Connect AI tools to the MRC MCP Server to instantly access trusted, up-to-date Microsoft 365 and Azure feature release information using natural language | [Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md) |
| Release options | - Configure general availability release settings in the Microsoft 365 admin center based on your organizational readiness for new features with Standard or Deferred release options | [Configure release options for Microsoft 365](configure-release-options.md) |
| Frontier program | - Offers early access to select AI and Microsoft 365 Copilot features before general availability.<br/> - Designed for exploration and feedback, and features might change or might not reach general availability. | [Microsoft Frontier Program](https://www.microsoft.com/microsoft-365-copilot/frontier-program) |

## Enable AI clients to retrieve product release information with MRC MCP server

AI-enabled organizations use intelligent tooling to accelerate their internal processes. By integrating the MRC MCP Server with your AI tools, you can connect to the latest release information for Microsoft 365 and Azure updates to create the infrastructure for AI-assisted reasoning over upcoming changes, priorities, and business impact.

For information on how to start using MRC MCP server, see [Get started with Release Communications MCP Server](mrc-mcp.md).

## Customize your organization’s release experience for Microsoft 365

From the Microsoft admin center, you can choose between various release options for Microsoft 365 updates, either during general availability or before general availability.

### General availability

With **Standard release**, your organization receives new features as soon as they’re generally available (GA). Standard release is the default option and should be the primary release channel for most customers. Microsoft thoroughly tests and validates all features and services prior to release. Your organization is configured as standard release by default.

If you have additional validation requirements, your organization may want to consider **Deferred release** for all or some users. Major Microsoft 365 releases are considered “deferred-capable”, meaning admins will get up to 30 days to prepare for the release. After 30 days, generally available Microsoft 365 features appear to your users. You can see which features are deferred-capable in the Message center.

For more information about release options and how to configure them, see [Configure Standard and Deferred release options for Microsoft 365](configure-release-options.md).

> [!NOTE]
> Standard and deferred release channels aren’t currently available for GCC, GCC High, and DoD cloud environments. Check this article for updates regarding future support.

### Before general availability

As an IT admin, you can opt in to use features *before* general availability by assigning users to specific release audiences.

The **Microsoft Frontier program** gives organizations early access to innovative and emerging AI capabilities in Microsoft 365 before those features reach general availability. By opting in to Frontier program, IT administrators can evaluate new Copilot agents and AI-powered experiences, determine readiness for broader deployment across their tenant, and provide feedback about Frontier feature capabilities to Microsoft.

The Frontier program supports early experimentation, but the features aren't fully supported, may change, and might not reach GA. They’re intended for evaluation and readiness, not production use.

For more information on the Frontier program, see [Microsoft Frontier program](https://www.microsoft.com/microsoft-365-copilot/frontier-program).

## Use the updated Message center interface

Enhance your organization’s ability to deliver timely, relevant, and actionable communications to users with our launch-focused release announcement hub. With the Message center, you can deliver more applicable and accessible information to your users.

- Stay informed with concise announcements at launch that feature bullet-point summaries and direct links to resources
- Incorporate a structured and more effective messaging format that includes change descriptions, rollout timelines, affected users and platforms, action checklists, and compliance impacts (including data handling)

For more details on the updated layout and information on keeping track of changes using the Microsoft 365 Message center, see [Message center in the Microsoft 365 admin center](message-center.md).

## Modern change management development

This is the first step in our modernization change management journey. Not all Microsoft 365 workloads are available in this new model. We’re starting with Microsoft 365 Copilot. Existing and legacy change management tools and methodologies can still be used for these experiences.

| Modern change management | Legacy change management |
| ----- | ----- |
| - [Modern change management - Overview](plan-for-change-management.md) <br/> - [Configure modern release options](configure-release-options.md) <br/> - FAQ – release options <br/> - [Release Communications MCP server](mrc-mcp.md) <br/> - [Message Center](message-center.md) <br/> - [FAQ – Message Center](message-center-faq.md) | - [Set up the Standard or Targeted release options](release-options-in-office-365.md) <br/> - [Microsoft 365 change guide - Microsoft 365 Apps](/microsoft-365-apps/best-practices/microsoft-365-change-guide) <br/> - [Stay on top of changes](stay-on-top-of-updates.md) |

## Related articles

[Get started with the Microsoft Release Communications MCP Server](mrc-mcp.md)

[Configure modern release options for Microsoft 365](configure-release-options.md)

[Release options FAQ](release-options-faq.md)

[Track new and changed features in the Microsoft 365 Message center](message-center.md)
