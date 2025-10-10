---
title: Frequently asked questions related to Microsoft 365 copilot
description: Frequently asked questions related to Microsoft 365 Copilot Researcher agent.
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
manager: dansimp
ms.date: 10/09/2025
audience: Admin
ms.reviewer: mandia
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
ms.custom: [copilot-learning-hub]
appliesto:
  - ✅ Microsoft 365 Copilot
---

# How Researcher works in Microsoft 365 Copilot

## General functionality

| Questions | Answers |
|---------|---------|
| **What is Researcher Agent and how is it different from Copilot chat?** | Researcher is designed for deep, multi-step research tasks, unlike standard Copilot chat which handles quick Q&A.|
| **Does Researcher Agent use the Archive Mailbox/Folder?** | Yes, archived emails are included as backfill when primary inbox lacks sufficient data. |
| **Does Researcher provide citations for its answers** | Yes, building trust through source citations is a core design principle. |
| **Is Researcher available in Sovereign Clouds** | To be released soon. |
| **Can Researcher fetch data from Graph Connectors?** | Yes, and future updates will allow connector configuration. |
| **How does Researcher interact with enterprise and web data?** | It uses Microsoft Graph, connectors, and Bing index for recent web data. |
| **Can we restrict which websites or web content the Researcher agent can pull information from (aside from disabling web search entirely)?** | No. There isn’t a granular setting to block or allow specific websites. The only admin control over web content is the global _web search toggle_. If web search is enabled, Researcher will use Bing to search the web generally; if web search is disabled at the tenant level, Researcher will not use any web data. |
| **Is the Researcher agent available on mobile devices (iOS and Android)?** | Yes, it is available on iOS and Android in the Copilot mobile app. |

## Administration and controls

| Questions | Answers |
|---------|---------|
| **How can administrators disable the Researcher Agent?** | <ul><li>Disable Researcher Agent for all users in the tenant</li><li>Disable all Copilot agents (including Researcher) for specific users by turning off Copilot Extensibility</li></ul>

>
> [!NOTE] Researcher Agent cannot be selectively blocked for an individual user or group. See [Manage Microsoft 365 Copilot agents in the Microsoft 365 admin center](../microsoft-365/admin/manage/manage-copilot-agents-integrated-apps.md) |
| **How can users disable Researcher?** | |
| **If the Researcher agent is automatically enabled (and even pre-pinned) for users, can an individual user remove or hide it?** | No. Researcher is a core part of the Microsoft 365 Copilot experience and users cannot independently remove or unpin it. In Microsoft’s internal deployment, it is pre-installed and pinned for all users, and external tenants see it auto-enabled in the Copilot app’s agent list. |
| **Is there any report or dashboard available for admins to track the usage of the Researcher (and Analyst) agent in their tenant?** | Not yet. As of now, Microsoft hasn’t provided a specific usage reporting tool for Copilot agents like Researcher and Analyst. |

## Functionality and architecture

| Questions | Answers |
|---------|---------|
| **What is the high-level architecture of Researcher?** | Researcher is built on Microsoft's Copilot orchestration layer, which routes user queries to appropriate agents and connectors. It uses a combination of retrieval-augmented generation (RAG), grounding services, and LLMs to generate responses.|
| **Which LLM models does Researcher use?** | Researcher primarily uses GPT-4 and o3 models, depending on tenant configuration and query complexity. Model selection is dynamic and optimized for performance and accuracy. |
| **How does Researcher switch between models?** | Model switching is handled by the orchestration layer based on query type, latency, and grounding requirements. Users do not need to manually select models.|
| **How does Researcher integrate with connectors?** | Researcher uses Microsoft Graph connectors to access enterprise content across SharePoint, OneDrive, Teams, and other sources. Connector configuration affects the scope of content available to Researcher.|
| **What is the roadmap for agent-to-agent handoff?** | Microsoft is actively developing agent-to-agent handoff capabilities. This will allow Researcher to collaborate with other Copilot agents (for example, Planner, Loop) to complete multi-step tasks.|

## Accuracy and citations

| Questions | Answers |
|---------|---------|
| **How does Researcher handle hallucinations** | Researcher uses grounding techniques to reduce hallucinations. It prioritizes content from trusted enterprise sources and provides citations to validate responses.|
| **Can Researcher cite paywalled sources?** | Researcher can cite paywalled enterprise content (for example, internal SharePoint documents) if the user has access. It does not cite external paywalled sources unless explicitly configured. |
| **What is the granularity of citations?** | Citations typically link to the paragraph or section of the source document. Hyperlink granularity may vary depending on the content type and connector configuration.|

## Enterprise controls

| Questions | Answers |
|---------|---------|
| **What controls do admins have over Researcher?** | <ul><li>Enable/disable Researcher through policy</li><li>Scope access to specific users or groups.</li><li>Configure connectors and data sources</li><li>Monitor usage through audit logs and analytics</li></ul> |
| **Can Researcher be disabled or scoped to specific users?** | Yes. Researcher can be disabled tenant-wide or scoped to licensed users through Microsoft 365 admin center or through Windows PowerShell. |
