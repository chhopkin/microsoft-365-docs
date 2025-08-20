---
title: Frequently asked questions related to Microsoft 365 copilot
description: Frequently asked questions related to Microsoft 365 Copilot Researcher agent.
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
manager: dansimp
ms.date: 08/19/2025
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

## Overview

| Questions | Answers |
|---------|---------|
| **What is Researcher in Microsoft 365 Copilot?** | Researcher is a Copilot agent designed to help users explore, summarize, and extract insights from enterprise data. It supports natural language queries and provides citations to source content, enabling users to build knowledge quickly and confidently.|
| **What are the key capabilities of Researcher in Microsoft 365 Copilot?** | <ul><li>Summarizes documents, emails, chats, and meeting transcripts</li><li>Answers questions using enterprise content</li><li>Provides citations and links to source material</li><li> Supports follow-up questions and iterative exploration</li></ul> |

## Security and privacy

| Questions | Answers |
|---------|---------|
| **Is Researcher auto-on for tenants?** | Yes, Researcher is enabled by default for eligible tenants. Admins can manage access through policy controls and licensing configurations.|
| **How does Researcher handle data in transit and at rest?** | Researcher adheres to Microsoft's enterprise-grade security standards. Data is encrypted in transit and at rest, and processed within the tenant boundary unless explicitly configured otherwise. |
| **What are the European Union data boundary (EUDB) and multi-geo implications?** | Researcher respects EUDB configurations and multi-geo policies. Data residency is maintained according to tenant settings, and processing is localized where applicable.|
| **Does Researcher log activity for eDiscovery?** | Yes. Researcher interactions are logged and discoverable through Microsoft Purview eDiscovery tools, subject to tenant configuration.|
| **How does Researcher interact with DLP and sensitivity labels?** | Researcher honors Microsoft Purview Data Loss Prevention (DLP) policies and sensitivity labels. It does not surface content that violates configured policies or access controls.|

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
| **What controls do admins have over Researcher?** | <ul><li>Enable/disable Researcher through policy</li><li>Scope access to specific users or groups.</li></ul>Configure connectors and data sources</li><li>Monitor usage through audit logs and analytics</li></ul> |
| **Can Researcher be disabled or scoped to specific users?** | Yes. Researcher can be disabled tenant-wide or scoped to licensed users through Microsoft 365 admin center or through Windows PowerShell. |
