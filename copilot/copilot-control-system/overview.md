---
title: "Copilot Control System overview"
description: "Learn about the Copilot Control System framework to secure, manage, and measure Microsoft 365 Copilot, Copilot Chat, Copilot Studio, and agents in your organization."
author: aczechowski
ms.author: aaroncz
manager: dansimp
ms.reviewer: bensum
ms.service: microsoft-365-copilot
ms.topic: solution-overview
ms.date: 08/14/2025
---

# Copilot Control System overview

The Copilot Control System is a framework of integrated controls and capabilities for Copilot and agents. Use it to help secure data, manage Copilot and agent experiences, and measure and analyze adoption and impact across your organization. It provides a governance structure for the use of Microsoft 365 Copilot, Copilot Chat, Microsoft Copilot Studio, and agents in your enterprise.

:::image type="content" source="media/copilot-control-system-overview.png" alt-text="A diagram of the Copilot Control System framework showing the three pillars.":::

The Copilot Control System consists of three main pillars:

- Security and governance
- Management controls
- Measurement and reporting

> [!TIP]
> As a framework, Copilot Control System is a conceptual model for how to structure your organization's approach to AI. These articles provide an overview and key points for each pillar, which then link out to supporting content with more detailed information and implementation instructions.

## Prerequisites

> *If this section is needed, make Prerequisites your first H2 in the article. Use clear and unambiguous language and use an unordered list format.*

> Link out to upcoming minimum requirements articles for Copilot Chat, M365 Copilot, and agents.

## Key capabilities

The following table outlines the key capabilities of each pillar of the Copilot Control System. It also includes the primary components that you use to support each pillar.

| Pillar | Capabilities | Components |
|---------|---------|---------|
| [Security and governance](security-governance.md) | - Data security<br>- AI security<br>- Compliance and privacy | - SharePoint Advanced Management<br>- Microsoft Purview<br>- Microsoft Defender for Cloud Apps |
| [Management controls](management-controls.md) | - Licensing and metering<br>- Agent lifecycle<br>- Customization | - Microsoft 365 admin center<br>- Power Platform admin Center<br>- Copilot Studio |
| [Measurement and reporting](measurement-reporting.md) | - Readiness and adoption<br>- Productivity impact<br>- Business value and return on investment (ROI) | - Copilot Analytics in Microsoft Viva<br>- Microsoft 365 admin center<br>- Power Platform admin Center |

## Process overview

> *Required: Process overview (H2)*
>
> *Use an H2 section to introduce the steps that are needed to get going with the solution. Use H3s to describe steps to set up/configure the solution.*
>
> Do we include this? Do we include links? Do we move each main step to the top of the pillar articles with links to subsections? 🤔

### Step 1: Security and governance actions

1. Prepare and secure your data.
    1. Use SharePoint Advanced Management to reduce potential oversharing.
    1. Implement data protection with Microsoft Purview.
1. Protect your organization against AI-based attacks.
    1. Understand the protections built-in to Copilot.
    1. Use Microsoft Defender for Cloud Apps to detect suspicious behaviors.
1. Create compliance plans.
    1. Understand the compliance controls built-in to Copilot.
    1. Use Purview to audit activity.
    1. Create data retention policies in Purview.

For more information, see [Security & governance in Copilot Control System](security-governance.md).

### Step 2: Deploy and manage Copilot controls

1. Develop and implement your licensing plan.
    1. Use the Microsoft 365 admin center to assign licenses.
    1. Meter license usage.
    1. Configure pay-as-you-go billing.
1. Manage agents for your organization.
    1. Use the Microsoft 365 admin center to review agent details: approve, block, and manage usage.
    1. Review agent consumption.

For more information, see [Management controls in Copilot Control System](management-controls.md).

### Step 3: Understand adoption and business impact

1. 

For more information, see [Measurement & reporting in Copilot Control System](measurement-reporting.md).

## End user guidance and support

[Microsoft Support](https://support.microsoft.com/copilot-skilling) offers many resources to help you get your entire organization on board and help users adopt the new processes. You'll find short videos, articles specific to each Microsoft 365 app, AI prompting information, and other training resources.

For more information, see [Microsoft 365 Copilot help & learning](https://support.microsoft.com/copilot-skilling).

## Related content

- [Security and governance](security-governance.md)
- [Management controls](management-controls.md)
- [Measurement and reporting](measurement-reporting.md)
- [Copilot Control System - Microsoft Adoption](https://adoption.microsoft.com/copilot/control-system/)
- [Transparency note for Microsoft 365 Copilot](../microsoft-365-copilot-transparency-note.md)
