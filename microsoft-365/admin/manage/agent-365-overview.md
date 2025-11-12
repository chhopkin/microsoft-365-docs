---
title: Agent 365 Overview in the Microsoft 365 admin center
description: Agent 365 Overview in the Microsoft 365 admin center.
#customer intent: As an IT admin, I want to manage agents for Microsoft 365 Copilot so that I can control their availability and functionality within my organization.
f1.keywords:
- NOCSH
ms.author: frankroj
author: frankroj
manager: scotv
ms.date: 11/12/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
- operations-pod
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
---

# Agent 365 Overview in the Microsoft 365 admin center

The **Agent 365 Overview** page in [Microsoft 365 admin center](https://admin.microsoft.com/) serves as the control plane for all agents. It provides IT administrators with a centralized dashboard to:

- Track agent adoption and usage trends.
- Identify alerts and governance gaps.
- Enable visibility and control across all agents in the tenant.

You can view Overview by going to **Agents** > **Overview**, or by using **AI home page** > Select **View in Agent 365 overview**.

## Key Features

- Provide a snapshot of agent health and actionable insights for the last 30 days.
- Highlight critical actions for admins. For example:
  - Approve pending requests.
  - Manage agents with alerts.
  - Exceptions.
- Surface governance signals to maintain compliance and reduce risk.
- Enable quick navigation to All agent pages.

## Hero Metrics

A high-level summary of the most critical indicators of agent adoption and impact. These metrics give admins an immediate sense of scale, engagement, and business value.

- **Agent Inventory** - The total count of all agents available in your organization's catalogue, including Microsoft-built, partner-built, and custom (LOB) agents. This reflects the breadth of automation capabilities deployed across your tenant. You can directly select the **Explore All agents** > **Inventory** to go through your inventory in detail.

- **Active Users** - The number of unique users who have interacted with at least one agent within last 30 days. A user is considered "active" if they have initiated at least one interaction with any agent in the time frame, regardless of how many agents they have interacted with.

- **Time Saved with Agents** - The estimated cumulative hours saved by employees through agent-assisted tasks, based on modeled productivity gains. Demonstrates ROI and business impact.

## Agent Analytics

Detailed insights into how agents are distributed and used, helping admins understand adoption patterns and optimize resources.

- **Agents by Publishers** - Breakdown of all agents in your inventory by their source of publisher (who created and shared it). There are two categories in this:

  - It can be **Created by your organization** - shared by creator, used only by creator, published by your organization, etc.
  - It can be **Created by external partners**.

- **Agents by Platforms** - Shows which creation platforms are most used for building agents. For example:

  - Copilot Studio (Full/Lite).
  - Azure AI Foundry.
  - Any external partner platforms.

- **Active Users Over Time** - A trend chart showing daily active user engagement with agents over the past 30 days. Reveals adoption momentum and helps spot usage spikes or declines.

## Top actions for you

Actionable governance cards that surface urgent tasks for admins to maintain compliance and improve adoption.

- **Pending Requests for Agents** - The total number of agent requests awaiting admin approval within last 30 days. Lists oldest 3 pending requests prioritized by oldest first. The card also displays the delta badge next to the key metric to highlight week-over-week change in the total requests.

    To take immediate action you can directly select the **Manage requests** button on the card.  Navigates to the **Agent Inventory** > **Requests** tab. This tab lists all pending agent requests submitted by users within organization.

- **Ownerless Agents** - Total Agents without an assigned owner, still pending owner assignment.

- **Assign owner button** - You can directly select the **Assign Owner** button. It takes you to the **Agent Inventory** > **Ownerless Agents** filter, showing agents without an assigned owner.
