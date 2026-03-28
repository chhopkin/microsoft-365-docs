---
title: "Manage Copilot Cowork for your organization"
description: "Details on managing Copilot Cowork in Microsoft 365 Copilot for organizations"
ms.date: 03/30/2026
ms.topic: overview
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
ms.subservice: cowork
appliesto:
- Microsoft 365 Copilot
---

# Manage Copilot Cowork for your organization

[!INCLUDE [cowork-top-note](../includes/cowork-top-note.md)]
[!INCLUDE [cowork-preview](../includes/cowork-preview.md)]

Copilot Cowork is available to all Microsoft 365 Copilot tenants. IT administrators can control who has access to it, deploy it on behalf of users, and pin it in the Copilot experience using the same governance tools in Microsoft 365 Copilot.

## Default availability

By default, Copilot Cowork is **available to all licensed users** in your tenant. This means:

- Users can discover and install it themselves from the Agent Store.
- It is **not pre-installed** or pre-pinned for users—no action is required to enable it.
- Users who do not want to use it can simply leave it uninstalled.

Admins can change this default at any time.

## How users find and install Copilot Cowork

Users can discover Copilot Cowork through the **Agent Store**, the built-in marketplace within Microsoft 365 Copilot.

**In Microsoft 365 Copilot (web or desktop):**

1. Open Microsoft 365 Copilot.
1. In the left navigation pane, select **Agents**, and then select **All agents**.
1. Search for **Copilot Cowork** and select **Add**.

**In Microsoft Teams:**

1. In the right navigation pane, select **Get agents**.
1. Search for **Copilot Cowork** and select **Add**.

Once added, Copilot Cowork appears in the user's agent list in the Copilot rail.

> **Note:** Users can only install Copilot Cowork if your organization makes it available to them. If you restrict access to specific groups, only those users see it in the Agent Store.

For more information about how users interact with agents, see [Use agents in Microsoft 365 Copilot](/copilot/microsoft-365/agent-essentials/m365-agents-admin-guide).

## Control access with the Microsoft 365 admin center

You manage Copilot Cowork the same way you manage any agent, through the **Microsoft 365 admin center**.

**Navigation:** [admin.microsoft.com](https://admin.microsoft.com) → **Copilot** → **Agents** → **All agents**

From there, find **Copilot Cowork** and select it to manage its settings. The key availability controls are:

| Setting | Effect |
|---|---|
| **Available to all users** | All licensed Copilot users in your tenant can find and install Cowork (default). |
| **Available to specific users or groups** | Only the users or security groups you specify can find and install Cowork. |
| **Blocked** | No users in your tenant can access Cowork. |

To restrict access to specific security groups or user segments, select **Available to specific users or groups** and add the relevant groups. This approach works best for phased rollouts or departmental pilots.

> **Note:** Country or region-based scoping isn't a supported option for agent availability. Use security groups to represent geographic or organizational segments.

For a full walkthrough of these controls, see [Manage agents in the Microsoft 365 admin center](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).

## Pre-install Copilot Cowork for your users

Instead of waiting for users to install Copilot Cowork themselves, admins can **deploy** it on behalf of all users or a specific group. Deploying an agent automatically installs it, and users don't need to take any other action.

**To deploy Copilot Cowork:**

1. In the admin center, go to **Copilot** → **Agents** → **All agents**.
2. Select **Copilot Cowork**.
3. Under **Deploy to**, choose **Entire organization** or **Specific users/groups**.
4. Select **Deploy**.

When you deploy Copilot Cowork, it's installed for the target users and appears in their agent list. The deployment process accepts users' permissions on their behalf.

For details, see [Deploy agents in Microsoft 365 Copilot](/agent-essentials/agent-lifecycle/agent-deploy).

## Pre-pin Copilot Cowork in the Copilot rail

Pinning makes Copilot Cowork persistently visible in the Copilot rail (the right-side agent panel) without the user needing to open the Agent Store. Pinning is a separate step from deployment—an agent must be deployed before it can be pinned.

**To pin Copilot Cowork for your users:**

1. In the admin center, go to **Copilot** → **Agents** → **Manage pinned agents**.
2. Select **Add a pinned agent** and choose **Copilot Cowork**.
3. Choose whether to pin it for the entire organization or specific groups.
4. Save your changes.

Users will see Copilot Cowork in their Copilot rail the next time they open Copilot. Users can unpin admin-pinned agents from their own view if they prefer.

For more information, see [Manage pinned agents for Microsoft 365 Copilot](/admin/manage/agent-registry).

## Security and compliance

Microsoft 365 Copilot applies the same security and compliance controls to Copilot Cowork as it does to all agents.

### Data loss prevention

Microsoft Purview DLP policies apply to Copilot agent interactions. Copilot agents, including Copilot Cowork, block sensitive information from being processed. This sensitive information includes content that matches DLP rules or documents with sensitivity labels. For more information, see [Learn about the Microsoft 365 Copilot location for DLP](/purview/dlp-microsoft365-copilot-location-learn-about).

### Audit logs

Microsoft Purview audit logs capture all interactions with Copilot Cowork under **Copilot activities**. Log entries include the agent name, agent ID, and version. Audit Standard provides these logs at no extra cost. For more information, see [Audit log activities for Microsoft 365 Copilot](/purview/audit-copilot).

### Data residency

By default, Copilot Cowork stores conversation content in your tenant's local region geography. It also supports Advanced Data Residency (ADR) and Multi-Geo configurations. For more information, see [Data residency for Microsoft 365 Copilot](/microsoft-365/enterprise/m365-dr-service-copilot).

## Related resources

- [Manage agents in the Microsoft 365 admin center](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps)
- [Agent availability settings](/copilot/microsoft-365/agent-essentials/agent-lifecycle/agent-availability)
- [Deploy agents in Microsoft 365 Copilot](/copilot/microsoft-365/agent-essentials/agent-lifecycle/agent-deploy)
- [Microsoft 365 Copilot agent installation overview](/copilot/microsoft-365/copilot-agent-install)
- [Agents admin guide for Microsoft 365 Copilot](/copilot/microsoft-365/agent-essentials/m365-agents-admin-guide)