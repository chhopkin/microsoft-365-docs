---
title: "Connect to Anthropic's AI models"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 09/18/2025
audience: Admin
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
- operations-pod
- OtherAILLMs
appliesto:
- ✅ Microsoft 365 Copilot
description: "Learn about how to connect your organization to Anthropic's AI models."
---

# Connect to Anthropic's AI models

You can now use Claude models by Anthropic within your Microsoft products. These models are hosted by Anthropic outside of Microsoft. You can elect to use Anthropic's AI models with the Researcher agent in Microsoft 365 Copilot and Copilot Studio. Anthropic’s AI models can help people in your organization with some of the following:  

- Summarize complex information
- Answer questions using source material
- Synthesize across multiple sources
- Idea generation, drafting and editing
- Organizing research

When your organization chooses to use an Anthropic model with Researcher in Microsoft 365, your organization is choosing to share your data with Anthropic to power the features. This data is processed outside all Microsoft‑managed environments and audit controls, therefore Microsoft’s customer agreements including the Product Terms and Data Processing Addendum do not apply.

In addition, Microsoft’s data‑residency commitments, audit and compliance requirements, service level agreements, and Customer Copyright Commitment do not apply. to your use of Anthropic services. Instead, your use is governed by Anthropic’s [Commercial Terms of Service](https://www.anthropic.com/legal/commercial-terms) and Anthropic’s [Data Processing Addendum](https://www.anthropic.com/legal/data-processing-addendum).

## Before you begin

Before users in your organization can use Anthropic in the Microsoft Researcher agent, they need to be assigned a Microsoft 365 Copilot license.

## Licensing requirement

Before users in your organization can use Anthropic in the Microsoft Researcher agent, they need to be assigned a Microsoft 365 Copilot license.

## Connect to Anthropic in the Microsoft 365 admin center

> [!IMPORTANT]
> Before your organization can connect to Anthropic AI models, you must allow access in the Microsoft 365 admin center. For Copilot Studio, additional admin controls are available in the Microsoft Power Platform admin center once you turn on access in the Microsoft 365 admin center. For more information, see Enable other AI models in Microsoft Copilot Studio.

You have to be a member of the [Global administrator role](/entra/identity/role-based-access-control/permissions-reference) to perform this task. For more information, see [About admin roles in the Microsoft 365 admin center](../add-users/about-admin-roles.md).

1. Go to the Microsoft 365 admin center and select **Copilot** -> **Settings**.
2. On the **User access** page, select **AI providers for other large language models**.
3. Under LLM providers for your organization, choose Anthropic and follow the steps to allow the provider.

After you connect, it can take a few hours for the connection to replicate.

## Block connection Anthropic

Your organization may decide that it no longer wants users to be able to access other LLMs. You can block the model provider:

1. Go to the Microsoft 365 admin center and select **Copilot** -> **Settings**.
2. On the **User access** page, select **AI providers for other large language models**.
3. Under **Available model providers for your organization**, choose **Anthropic**, and select **Block provider**.

Once you disconnect Anthropic, users won’t have the option to use Anthropic’s LLMAI models. After you disconnect, it can take a few hours for replication.
