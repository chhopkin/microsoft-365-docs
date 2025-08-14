---
title: "Management controls in Copilot Control System"
description: "Learn how to use the Copilot Control System framework to manage licensing, agent lifecycle, and customize  management controls for Microsoft 365 Copilot and agents."
author: aczechowski
ms.author: aaroncz
manager: dansimp
ms.reviewer: bensum
ms.service: microsoft-365-copilot
ms.topic: solution-overview
ms.date: 08/14/2025
---

# Management controls in Copilot Control System

Copilot Control System management controls help you decide how to deploy your Microsoft 365 Copilot licenses and agents to fit your organization's unique needs. You can find Copilot and agent management controls mainly in the [Microsoft 365 admin center](/microsoft-365/admin/admin-overview/admin-center-overview), [Power Platform admin center](/power-platform/admin/), and [Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio).

:::image type="content" source="media/management-controls.png" alt-text="A diagram of the Copilot Control System framework highlighting the Management Controls pillar.":::

> [!NOTE]
> The [Copilot Control System](overview.md) consists of three main pillars:
>
> - [Security and governance](security-governance.md)
> - **Management controls** (this article)
> - [Measurement and reporting](measurement-reporting.md)

The management controls pillar of the Copilot Control System focuses on the following key capabilities:

- Licensing and metering
- Agent lifecycle
- Customization

## Licensing and metering

To ensure compliance with policies and usage limits, manage Microsoft 365 Copilot license assignment. You can also monitor message capacity for both prepaid and pay-as-you-go consumption.

### Copilot and Copilot chat in the Microsoft 365 admin center

Use the [Microsoft 365 admin center](/microsoft-365/admin/admin-overview/admin-center-overview) to manage Microsoft 365 Copilot and Copilot Chat licensing. You can also configure pay-as-you-go billing so that you only pay when users use it:

:::image type="content" source="media/m365-admin-center-billing-usage-connections.png" alt-text="Screenshot of the Microsoft 365 Admin Center, Billing & usage node, showing the pane to Manage billing policy connections for Microsoft 365 Copilot Chat." lightbox="media/m365-admin-center-billing-usage-connections-large.png":::

For more information, see the following articles:

- [License plans for Microsoft 365 Copilot](../microsoft-365-copilot-licensing.md)
- [Microsoft 365 Copilot pay-as-you-go overview for IT admins](../pay-as-you-go/overview.md)

### Copilot Studio in the Power Platform admin center

Use the [Power Platform admin center](/power-platform/admin/) to manage message capacity for Copilot Studio:

:::image type="content" source="media/power-platform-admin-center-licensing.png" alt-text="Screenshot of the Power Platform admin center, Licensing node, showing the Copilot Studio page that summarizes message capacity." lightbox="media/power-platform-admin-center-licensing-large.png":::

For more information, see [Manage Copilot Studio messages and capacity](/power-platform/admin/manage-copilot-studio-messages-capacity).

## Agent lifecycle

The system provides visibility into the status, governance, and lifecycle of agents. It lets you review agent details, approve, block, and manage usage. You can also control environmental routing, groups, and rules that support organizational policies.

### Manage connectors and actions

- **Enable or block specific connectors and actions** in the Microsoft 365 admin center. You can control which plugins like Copilot Studio and Power Automate are available to users. For more information, see [Deploy and enable actions in Copilot Studio](/microsoft-copilot-studio/copilot-plugins-enable-admin).

- **Review connector access permissions** to ensure they align with your organization's visibility model. For more information, see [Review and manage access permissions in Microsoft Copilot connectors](/microsoftsearch/manage-access-permissions).

- **Delegate connector management** to AI Administrators by using Microsoft Entra ID roles and Graph API consent policies. For more information, see [Grant administrative rights to AI Administrators to manage connectors](/microsoft-365-copilot/extensibility/connector-admin-delegation).

### Limit agent sharing of coauthors or users

- **Control sharing permissions** by using Editor and Viewer roles in the Power Platform admin center. For more information, see [Control how agents are shared in Microsoft Copilot Studio](/microsoft-copilot-studio/admin-sharing-controls-limits).

- **Block or limit sharing** by setting rules at the managed environment or environment group level. For more information, see the release plan for [Block and limit sharing in Copilot Studio](/power-platform/release-plan/2025wave1/power-platform-governance-administration/turn-sharing-off-copilot-studio).

### Disable publish by blocking certain channels

- **Use Data Loss Prevention (DLP) policies** to block publishing agents through Copilot Studio supported channels. For more information, see [Configure data loss prevention policies for agents](/microsoft-copilot-studio/admin-data-loss-prevention).

### Define a lifecycle process to approve agents for production

- **Use Application Lifecycle Management (ALM)** with Power Platform solutions to move agents and actions across development, test, and production environments. For more information, see the release plan to [Use application lifecycle management in Copilot Studio](/power-platform/release-plan/2024wave1/data-platform/use-application-lifecycle-management-copilot-studio).

### Manage agent capabilities, data sources, and custom actions

- **Extend agent capabilities** with the following tools:
  - Code interpreter
  - Image generator
  - Connectors
  - Knowledge sources like SharePoint, OneDrive, and web search

  For more information, see [Add knowledge sources to your declarative agent](/microsoft-365-copilot/extensibility/knowledge-sources).

- **Use standard, premium, or custom connectors** to integrate external services and APIs. For more information, see [Use connectors in Copilot Studio](/microsoft-copilot-studio/advanced-connectors).

- **Add tools, topics, and knowledge** to agents for richer functionality. For more information, see [Extend the capabilities of your agent](/microsoft-copilot-studio/copilot-connectors-in-copilot-studio).

For more information on managing agents, see the following articles:

- [Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center](../../microsoft-365/admin/manage/manage-copilot-agents-integrated-apps.md)

- [Track, manage, and scale Copilot adoption in the Power Platform](/power-platform/admin/copilot/copilot-hub)

## Customization

Beyond the management controls already discussed in this article, use the **Copilot** pane of the Microsoft 365 admin center to configure other settings.

- Use the **Search** node to manage Copilot Search. You can specify organization-specific acronyms and websites that appear in search results. For more information, see [Microsoft 365 Copilot Search admin experience](../microsoft-365-copilot-search-admin-experience.md).

- Use the **Settings** node to manage everything related to Copilot. You can access many of the controls previously mentioned in this article through shortcuts in this node. For more information on the other settings that are available, see [Manage Microsoft 365 Copilot scenarios in the Microsoft 365 admin center](../microsoft-365-copilot-page.md).

## Related content

- [Manage Microsoft 365 Copilot scenarios in the Microsoft 365 admin center](../microsoft-365-copilot-page.md)

- [Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center](../../microsoft-365/admin/manage/manage-copilot-agents-integrated-apps.md)

- [Copilot Control System - Microsoft Adoption](https://adoption.microsoft.com/copilot/control-system/)
