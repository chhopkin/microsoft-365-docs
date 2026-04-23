---
title: Understand Shadow AI in Microsoft 365 admin center
description: Understand Shadow AI in Microsoft 365 admin center.
#customer intent: Learn about Shadow AI in Microsoft 365 admin center.
f1.keywords:
- NOCSH
ms.author: frankroj
author: frankroj
manager: scotv
ms.date: 04/23/2026
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

## Prerequisites

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

- [Microsoft Intune](/intune/fundamentals/what-is-intune) enrollment for managed Windows devices.
- Opt in to the [Frontier preview experience](https://www.microsoft.com/microsoft-365-copilot/frontier-program) in the Microsoft 365 admin center.

## What is Shadow AI?

Shadow AI refers to AI-powered tools and agents used by users without IT awareness or approval. While these tools might improve productivity, unmanaged usage can introduce risks related to:

- Data leakage.
- Compliance violations.
- Security vulnerabilities.
- Lack of auditability and governance.

Common examples of Shadow AI tools include:

- Unauthorized AI coding assistants. For example, OpenClaw.
- Local agents, MCP servers, and Agentic CLIs.
- Browser extensions with AI capabilities.

The Shadow AI experience helps administrators identify and manage these risks without disrupting legitimate business workflows.

## Features available in public preview

During public preview, the Shadow AI experience allows admins to detect and block the following:

| Agent    | Detection | Blocking  |
| -------- | --------- | --------- |
| OpenClaw | Available | Available |

> [!NOTE]
>
> Shadow AI detection and blocking currently apply only to managed Windows devices enrolled with Microsoft Intune.

## Access the Shadow AI (Frontier) agent

The **Shadow AI (Frontier)** page in the Microsoft 365 admin center is a dedicated experience separate from the **All agents** page. It focuses exclusively on unmanaged AI agents that require detection and governance.

To access the **Shadow AI (Frontier)** page in the Microsoft 365 admin center, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Agents** to expand it.

1. Under **Agents**, select **Shadow AI (Frontier)**

1. The **Shadow AI (Frontier)** page displays a list of known Shadow AI agents and developer tools that can be detected in your environment.

### View Shadow AI agent details

1. To view Shadow AI agent details, such as OpenClaw details, select the Shadow AI agent from the list of agents in the **Shadow AI (Frontier)** page.

1. The details pane opens for the selected Shadow AI agent. Make sure **Details** is selected. From **Details**ou can view information regarding the type of agent. For example:

   - When it was last scanned.
   - If there are any Microsoft Intune security policies currently applied.

### Enable detection for a Shadow AI agent

To proactively configure detection for a Shadow AI agent before broad adoption, follow these steps:

1. In the Shadow AI agent details pane, select **Security policies**.

1. Under **Security policies**, select **Continuously detect managed devices**.

1. Select **Apply policies** to confirm.

### View detected devices for a Shadow AI agent

Once you have enabled detection for a Shadow AI agent, you can view detected devices in the Shadow AI agent details pane by following these steps:

1. In the Shadow AI agent details pane, select the **Detected devices** tab.

1. A list and count of detected devices is displayed.

    > [!NOTE]
    >
    > The detected devices list and count is only populated if a detection policy is applied. After initially enabling the detection policy, it might take some time for devices to sync with Microsoft Intune and for the detected devices to populate in the list.

1. In **Detected devices**, you can search for a specific device name. You can also see the following device data:

   - **Device name**: Name of the device.
   - **Device type**: Type of device (Desktop, Virtual Machine, Server, Laptop, etc.)
   - **Operating system**: Operating system installed on the device.
   - **Last Intune scan**: The last time Microsoft Intune scanned the device.

### Blocking a Shadow AI agent

After detection is enabled and the Shadow AI agent is identified in your environment, you can block it to prevent execution on managed devices.

When a Shadow AI agent is blocked, the following occurs:

- The Shadow AI agent can no longer run on managed devices.
- Devices receive compliance indicators.
- Users are notified that the Shadow AI agent is blocked.
- Detection is continuous so attempted usage remains visible.
- Future downloads of the blocked Shadow AI agent are also prevented.

Blocking a Shadow AI agent creates a new Microsoft Intune policy that automatically propagates to all managed Windows devices enrolled in Intune. Depending on how Intune is configured in your organization, this Intune policy update could take anywhere from 15 minutes up to 8 hours to apply. Full policy details, including when Intune policy applies, can be found in Intune. For more information, see [Assign policies in Microsoft Intune](/intune/device-configuration/assign-device-profile).

> [!IMPORTANT]
> The Microsoft Intune policy created when blocking a Shadow AI agent enforces a strict execution block on detected devices. When enabled, it prevents the following from running:
>
> - Docker CLI.
> - Node.js.
> - Windows Subsystem for Linux (WSL).
> - The default network ports used by the Shadow AI agent such as OpenClaw.
>
> This action is highly impactful. While it is effective at disrupting the most common methods used to run OpenClaw on managed devices, it also blocks widely used developer tooling and workflows.

To block a Shadow AI agent:

1. In the Shadow AI agent details pane, select **Security policies**.

1. Under **Security policies**, select **Block AI agents from *\<Shadow AI agent name>***. For example, select **Block AI agents from OpenClaw**.
