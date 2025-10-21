---
title: Development environments for Microsoft 365 agents
f1.keywords:
ms.author: erikre
author: ErikRe
manager: dansimp
ms.date: 10/08/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Learn about development environment for Microsoft 365 agents.
---

# Development environments for Microsoft 365 agents

As an admin, you can configure and deploy out-of-the-box agents without having to create and publish a new agent. However, when your organization needs to customize Copilot functionality, such extending Copilot’s knowledge, automate workflows, or deliver tailored user experiences, users, and developers at your organization can build agents that you can manage and deploy. 

There are two types of approaches to building agents for Microsoft 365 Copilot. Users and developers at your organization can use the [declarative](/microsoft-365-copilot/extensibility/agents-overview#declarative-agents) approach or the [custom engine agents](/microsoft-365-copilot/extensibility/agents-overview#custom-engine-agents). Because both approaches use Copilot's AI infrastructure, model, and orchestrator, they adhere to the security, compliance, and Responsible AI (RAI) requirements for Microsoft 365.

Declarative agents enable members of your organization to configure Copilot for specific scenarios. These agents are designed to be used by individuals. Also, these agents are limited to Copilot's orchestrator and models, where they use your instructions. Declarative agents rely on user-initiated interactions. Members of your organization can create declarative agents using Microsoft SharePoint and Copilot Studio (lite). Also, a [Copilot agent](/microsoft-copilot-studio/microsoft-copilot-extend-copilot-extensions#what-are-copilot-agents-tools-knowledge-and-suggested-prompts), created in [Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) (full), is equivalent to a declarative agent created in Microsoft 365 Copilot (lite). For more information, see [declarative agents](/microsoft-365-copilot/extensibility/agents-overview#declarative-agents).

Custom engine agents are fully customized AI assistants. When members of your organization build a custom engine agent, they can collaborate with a group or create these type of agents on their own. They can choose the AI models and orchestration as well. Custom engine agents also allow members of your organization to enable triggering actions automatically, even without direct user input. Custom engine agents must be published and approved by your organization, such as an admin, before they're available to your organization. Members of your organization can create custom engine agents using [Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) (full) and  Microsoft 365 Agents Toolkit. For more information, see [custom engine agents](/microsoft-365-copilot/extensibility/agents-overview#custom-engine-agents).


