---
title: What is Researcher agent in Microsoft 365 Copilot?
description: Researcher is an advanced AI assistant in Microsoft 365 Copilot that iteratively gathers enterprise and web data to deliver comprehensive, source-backed answers.
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
manager: dansimp
ms.date: 10/23/2025
audience: Admin
ms.reviewer: dansimp
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

# Researcher Agent overview and usage

Researcher is an advanced AI Copilot agent in Microsoft 365 designed to tackle complex, multi-step questions by acting as a deep research assistant. Unlike a standard Copilot chat which responds almost instantly in one step, Researcher engages in an iterative reasoning process - asking clarifying questions, searching through enterprise data and web sources, invoking other specialized agents if needed, and finally producing a detailed, source-backed report-style answer.

## Architecture

Researcher's architecture is built on the Microsoft 365 Copilot platform, leveraging a multi-tier agent orchestration model. In simple terms, Researcher is a Copilot chat agent with a specialized workflow: it interprets your question, plans a research strategy, uses various tools to gather information, and then generates a detailed answer. Several components work together behind the scenes:

- **Copilot Orchestrator**- The Copilot service hosts and manages the Researcher agent. It maintains the conversation state and coordinates function calls (like searches or invoking sub-agents) on behalf of the AI. This orchestrator enables Researcher to perform complex sequences of actions rather than just answering immediately.

- **Advanced Reasoning LLM**- Instead of the regular chat model, Researcher uses a dedicated large Language Model optimized for reasoning. This model is fine-tuned to support lengthy, multi-step thought processes.

- **Integrated tools and connectors**- Researcher can tap into various data sources and tools as it works on your query. It has access to your Microsoft 365 "Work" data (emails, Teams chats, OneDrive/SharePoint files, meeting transcripts, etc.) through Microsoft Graph, and it can perform enterprise searches across all that content.

- **Connected Sub-Agents**- A unique aspect of Researcher is its ability to delegate subtasks to other Copilot agents. It treats certain domain-specific agents as "specialist helpers." For example, if your question involves sales data, Researcher can invoke the Sales Insights agent (which knows how to fetch CRM data from Dynamics 365) and incorporate that input into the answer. Similarly, it could call a Power BI agent to get a chart or a summary of a report.

## Related content

- [Microsoft 365 Copilot Researcher FAQ's](faq-researcher.yml)