---
title: Researcher Agent with computer use set up in Microsoft 365 Copilot
description: The following instructions help you configure the admin settings for Researcher Agent computer use in Microsoft 365 copilot.
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
manager: dansimp
ms.date: 10/24/2025
audience: Admin
ms.reviewer: dansimp
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot

ms.custom: [copilot-learning-hub]
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Researcher Agent with Computer use set up

## Overview

Researcher with Computer use is a powerful extension that builds on the capabilities of the Researcher agent. With Computer use, Researcher agent can securely interact with public, gated, and interactive web content through a virtual computer-enabling users to uncover deeper insights, take action, and generate richer reports grounded in both their work data and the web.

:::image type="content" source="../../media/agents/computer-use-active-option.png" alt-text="Screenshot showing the computer use option active in Researcher Agent." lightbox="../../media/agents/computer-use-active-option.png":::

## Configure admin settings for Researcher Agent with Computer use

Follow these instructions to configure admin settings for Researcher Agent with **Computer use** by following the setup instructions. After setup is complete, contact us to enable the experience for your tenant. The experience will follow the admin settings you've configured.

1. Navigate to [Microsoft Admin Controls (MAC) Agents](https://admin.cloud.microsoft/?#/copilot/agents) page.

:::image type="content" source="../../media/agents/microsoft-admin-control-agents-page.png" alt-text="Screenshot showing the Microsoft Admin Controls Agents page." lightbox="../../media/agents/microsoft-admin-control-agents-page.png":::

2. Select **Researcher** and check if there is an additional tab for **Computer use**. If you do not see the following, reach out to Microsoft support.

:::image type="content" source="../../media/agents/computer-use-researcher-agent.png" alt-text="Screenshot showing the option to allow Researcher to access work data." lightbox="../../media/agents/computer-use-researcher-agent.png":::

3. Customize users that have access to Researcher with Computer use.

    a. There are 3 options for configuring who has access to the experience-

    - Allow all users in your organization
    - Allow specific users or groups only
    - No users in your organization

:::image type="content" source="../../media/agents/computer-use-enabled.png" alt-text="Screenshot showing the Computer use option enabled in Researcher Agent." lightbox="../../media/agents/computer-use-enabled.png":::

:::image type="content" source="../../media/agents/computer-use-disabled.png" alt-text="Screenshot showing the Computer use option disabled in Researcher Agent." lightbox="../../media/agents/computer-use-disabled.png":::

    b. For users that have it disabled, the **Computer Use** option will appear grayed out.

> [!NOTE]
> (Private Preview)- The experience won't be enabled for users until you notify that admin settings are complete.

4. Configure Work access for Researcher with Computer use

    a. This allows users to toggle on **Work** in the Sources menu, allowing Researcher to leverage a user's work content, for example, emails, chats, files, with Computer Use.
    
    b. When enabled by admins, users must still manually toggle on Work access.
    
    c. When disabled, the **Work** source will appear grayed out and not selectable.

:::image type="content" source="../../media/agents/work-toggle-enabled.png" alt-text="Screenshot showing the Work option enabled in Researcher Agent." lightbox="../../media/agents/work-toggle-enabled.png":::
:::image type="content" source="../../media/agents/work-toggle-disabled.png" alt-text="Screenshot showing the Work option disabled in Researcher Agent." lightbox="../../media/agents/work-toggle-disabled.png":::

5. Select which websites are allowed for Computer use

    a. There are 3 options for configuring websites the virtual device can access-

    - All websites
    - Allow specific URLs or domains only
    - Exclude specific URLs or domains

    b. You can allow "All websites", block some with the "Exclude specified" option, or only allow certain sites with the "Allow specified" option.

6. After completing the set up, contact the Researcher Agent team to enable the experience.

Contact the Researcher Agent team or your CAPE contact to let us know you are ready for your tenant to be enabled using admin settings.



It takes 24 hours for the **Computer use** option to appear in Researcher agent for the specific users listed in admin settings. After Researcher for Computer use has been enabled for your tenant, you can continue to make changes to and update the admin settings.
