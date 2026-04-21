---
title: Understand Shadow AI in Microsoft 365 admin center
description: Understand Shadow AI in Microsoft 365 admin center.
#customer intent: Learn about Shadow AI in Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: frankroj
author: frankroj
manager: scotv
ms.date: 04/21/2026
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.subservice: agent-management
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

# Shadow AI in Microsoft 365 admin center (Preview)

The Shadow AI page in the Microsoft 365 admin center helps IT administrators discover, monitor, and govern unmanaged AI agents used within their organization.

This preview capability provides a dedicated view for detecting and governing unapproved local AI agents such as OpenClaw, and enables administrators to take governance actions to maintain security and compliance.

> [!NOTE]
>
> Shadow AI is currently in public preview. Features, supported agents, and behaviors might change before general availability.

Prerequisites
To use Shadow AI detection and governance, you need:

- Microsoft 365 E7 or equivalent license.

- One of the following admin roles:

  - Security Administrator.
  - AI Administrator.
  - Global Reader.
  - Security Administrator.
  - Security Reader.
  - Security Operator.
  - Reports Reader.
  - User Experience Success Manager.
  - User Account Admin.

- Microsoft Intune enrollment for managed Windows devices.

## What is Shadow AI?

Shadow AI refers to AI-powered tools and agents used by users without IT awareness or approval. While these tools might improve productivity, unmanaged usage can introduce risks related to:

- Data leakage.
- Compliance violations.
- Security vulnerabilities.
- Lack of auditability and governance.

Common examples of Shadow AI tools include:

- Unauthorized AI coding assistants. For example, OpenClaw.
- Non-Microsoft AI productivity applications
- Browser extensions with AI capabilities

The Shadow AI experience helps administrators identify and manage these risks without disrupting legitimate business workflows.

## Features available in public preview

During public preview, the Shadow AI experience is split into two distinct capabilities:

- **[Unapproved/Unregistered locally run AI Agents (Shadow AI)](#shadow-ai-governance-for-unapprovedunregistered-locally-run-ai-agents)**

    These agents are unmanaged or unregistered agents that can introduce governance and security risk. These agents include:

    | Agent    | Detection | Blocking  |
    | -------- | --------- | --------- |
    | OpenClaw | Available | Available |

- **[Developer Tool Detection](#developer-tool-detection)**

    These developer tools are legitimate developer tools that can be detected on managed devices for IT visibility and inventory purposes. Developer tool detection isn't for blocking or governing as Shadow AI. Instead, this capability helps you understand which developer tools are running in your environment, not governing them as Shadow AI.

    | Agent | Detection | Blocking |
    | ----- | --------- | -------- |
    | GitHub Copilot CLI | Available | Not available in preview |

> [!NOTE]
>
> Shadow AI detection and blocking currently apply only to managed Windows devices enrolled with Microsoft Intune.

## Shadow AI: Governance for unapproved/unregistered locally run AI agents

This section covers governance scenarios for unapproved AI agents like OpenClaw that can be both detected and blocked.

### Access the Shadow AI (Frontier) page and agent details

The Shadow AI (Frontier) page in the Microsoft 365 admin center is a dedicated experience separate from the **All agents** page. It focuses exclusively on unmanaged AI agents that require detection and governance. It also provides visibility into developer tool usage.

To access the **Shadow AI (Frontier)** page in the Microsoft 365 admin center, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select **Shadow AI (Frontier)**

1. The **Shadow AI (Frontier)** page displays a list of known Shadow AI agents and developer tools that can be detected in your environment.

1. To view Shadow AI agent details, such as OpenClaw details, select the Shadow AI agent name

1. The details pane opens for the selected Shadow AI agent. In the details pane, you can view information regarding the type of agent. For example:

   - When it was last scanned.
   - If there are any security policies currently applied.
   - A count of detected devices. This count is only populated if a detection policy is applied.

### Enabling detection for a Shadow AI agent

To proactively configure detection for a Shadow AI agent before broad adoption, follow these steps:

1. Use the steps in the [Access the Shadow AI (Frontier) page and agent details](#access-the-shadow-ai-frontier-page-and-agent-details) section to access the **Shadow AI (Frontier)** page.

1. In the **Shadow AI (Frontier)** page, select the desired Shadow AI agent. For example, OpenClaw.

1. In the Shadow AI agent details pane that opens, select **Security policies**.

1. Under **Security policies**, select **Continuously detect managed devices**.

These steps create a new Microsoft Intune policy that automatically propagates to all managed Windows devices enrolled in Intune. A device receives the updated Intune policy when the next Intune sync cycle occurs. Depending on how Intune is configured in your organization, this Intune policy update could take anywhere from 15 minutes up to 8 hours to apply. Full policy details, including when Intune policy applies, can be found in Intune. For more information, see [Assign policies in Microsoft Intune](/intune/device-configuration/assign-device-profile).

### Detected Devices

After a detect security policy is applied on devices, **Detected devices** of the Shadow AI agent details pane populates. In **Detected devices**, you can search for a specific device name. You can also see the following device data:

- **Device name**: Name of this device.
- **Device type**: Type of device (Desktop, Virtual Machine, Server, Laptop, etc.)
- **Operating system**: Operating system installed on device.
- **Last Intune scan**: The last time Intune scanned the device.

### Blocking a Shadow AI agent

After detection is enabled and the Shadow AI agent is identified in your environment, you can block it to prevent execution on managed devices.

To block a Shadow AI agent:

1. Use the steps in the [Access the Shadow AI (Frontier) page and agent details](#access-the-shadow-ai-frontier-page-and-agent-details) section to access the **Shadow AI (Frontier)** page.

1. In the **Shadow AI (Frontier)** page, select the desired Shadow AI agent. For example, OpenClaw.

1. In the Shadow AI agent details pane that opens, select **Security policies**.

1. Under **Security policies**, select **Block AI agents from *<Shadow AI agent name>***. For example, select **Block AI agents from OpenClaw**.

Blocking a Shadow AI agent creates a new Intune policy that automatically propagates to all managed Windows devices enrolled in Intune. Depending on how Intune is configured in your organization, this Intune policy update could take anywhere from 15 minutes up to 8 hours to apply. Full policy details, including when Intune policy applies, can be found in Intune. For more information, see [Assign policies in Microsoft Intune](/intune/device-configuration/assign-device-profile).

When a Shadow AI agent is blocked, the following occurs:

- The Shadow AI agent can no longer run on managed devices.
- Devices receive compliance indicators.
- Users are notified that the Shadow AI agent is blocked.
- Detection is continuous so attempted usage remains visible.
- Future downloads of the blocked Shadow AI agent are also prevented.

## Developer tool detection

Detection capabilities are available for legitimate developer tools such as GitHub Copilot CLI. These tools aren't classified as Shadow AI. Detection gives IT administrators visibility into which developer tools are running on managed devices for inventory and awareness.

### Detect developer tool usage on managed devices

To detect a legitimate developer tool usage, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select [**All agents**](https://admin.cloud.microsoft/?#/agents/all).

1. In the **All agents** page, select **Local Agents (Frontier)**.

1. In the **Shadow AI** page, in the **Agent Registry**, select **GitHub Copilot CLI**.

1. In the agent details pane that opens, select **Configure detection**.

1. Detection begins immediately across all managed Windows devices.

> [!NOTE]
>
> Detection of legitimate developer tools is provided for IT visibility and device inventory purposes, not for Shadow AI governance.
