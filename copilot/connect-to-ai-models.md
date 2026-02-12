---
title: "Connect to xAI's models"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 02/11/2026
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
description: "Learn about onboarding xAI for your Microsoft 365 organization."
---

# Connect to xAI's models

You can now use xAI models within your Microsoft products. These models are hosted by xAI outside of Microsoft. You can elect to use XAI's models with certain features in Microsoft 365.

xAI models can help people in your organization with some of the following:

- Summarize complex information
- Answer questions using source material
- Synthesize across multiple sources
- Idea generation, drafting and editing

When your organization chooses to use an xAI model, your organization is choosing to share your data with xAI to power the features. This data is processed outside all Microsoft managed environments and audit controls, therefore Microsoft’s customer agreements, including the Product Terms and Data Processing Addendum don't apply. In addition, Microsoft’s data residency commitments, audit and compliance requirements, service level agreements, and Customer Copyright Commitment don't apply to your use of xAI services. Instead, use of xAI's services is governed by xAI’s terms.

## Before You Begin

Before users in your organization can use xAI, they need to be assigned a Microsoft 365 Copilot license.

## Connect to xAI in the Microsoft 365 Admin Center

Before your organization can connect to xAI AI models, you must allow access in the Microsoft 365 admin center.
You have to be a member of the Global administrator role to perform this task. For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

1.  Go to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Copilot** -\> **Settings**.
2.  On the **Data access** page, select **AI providers for other large language models**.
3.  Under **LLM providers for your organization**, choose **xAI**.
4.  Agree to the Terms and Conditions and select **Allow provider**.

After you connect, it may take a few hours for the connection to complete.

## Controls for Copilot Studio in the Microsoft Power Platform Admin Center

Once enabled in the Microsoft 365 admin center, additional administrator controls are available in the Microsoft Power Platform admin center (PPAC) to allow xAI to be used in Copilot Studio. For more information, see [Allow external large language models (LLMs) for generative responses](https://docs.microsoft.com/power-platform/admin/allow-external-large-language-models).

## Disable Connection to xAI

Your organization may decide that it no longer wants users to be able to access other LLMs. You can disable the model provider:

1. Go to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Copilot** -\> **Settings**.
2. On the **Data access** page, select **AI providers for other large language models**.
3. Under **Available model providers for your organization**, choose **xAI**, and select **Block provider**.

Once you disconnect xAI, users cannot use xAI's AI models. After completing the steps to disconnect xAI in Microsoft 365, it may take several hours for the service to be fully disabled for your users.
