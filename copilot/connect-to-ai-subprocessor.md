---
title: "Integrate and manage Anthropic's AI Models in Microsoft 365 Copilot"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 11/12/2025
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

# Integrate and manage Anthropic's AI Models in Microsoft 365 Copilot

Microsoft has transitioned Anthropic from an Independent Data Processor (IDP) to a sub-processor for Microsoft 365 Copilot. This change ensures that Copilot experiences using Anthropic models now include Microsoft's contractual commitments, data protection standards, and compliance with Microsoft's privacy requirements. As an administrator, you need to understand how to manage and integrate these models for your organization.

## Overview of Anthropic integration

As a sub-processor for Copilot experiences, Anthropic will operate under Microsoft's direction and contractual safeguards, including coverage under the [Microsoft Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) and [Online Services Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd). Microsoft remains accountable for Anthropic's compliance under these commitments. Additionally, the use of Anthropic models in Microsoft 365 Copilot falls under our [Enterprise Data Protection standards](http://aka.ms/EDPLearn).

Anthropic models will be enabled by default for many organizations, allowing users to choose from multiple AI models within their Microsoft 365 Copilot experiences. This update supports Microsoft's commitment to offering a choice between leading AI models while maintaining enterprise-grade security and compliance.

Your users can elect to use Anthropic's AI models in Microsoft 365 Copilot, Researcher, and Copilot Studio. For more information, see **TBD**. Anthropic’s AI models can help people in your organization with some of the following:

- Summarize complex information
- Answer questions using source material
- Synthesize across multiple sources
- Generate ideas, draft, and edit content

## Before you begin

Before users in your organization can use Anthropic in the Microsoft 365 Copilot app and in Microsoft Copilot Studio, they need to be assigned a [Microsoft 365 Copilot license](../microsoft-365/admin/manage/assign-licenses-to-users.md).
Note: Anthropic’s models are not supported in Government clouds (GCC, GCC High, DoD).

> [!NOTE]
> Anthropic's models are not supported in Government clouds (GCC, GCC High, DoD).

## Manage Anthropic's model settings in the Microsoft 365 admin center

You don't need to take any action as the administrator. Anthropic models will be available by default in certain regions for Microsoft 365 Copilot, Researcher, and Copilot Studio. Your organization will no longer need to opt-in to Anthropic's Commercial Terms of Service to use Anthropic models in the Microsoft 365 Copilot experiences.

In the Microsoft 365 Copilot (web, desktop, and mobile), UI indicators will show when Anthropic and Claude models are in use. In Copilot Studio, makers must select the model during agent creation.

## Unsupported regions

Support for Anthropic's models is not available in all regions. For these regions, the toggle will appear but remain off:

- Organizations in the European Union (EU), the European Free Trade Association (EFTA), or the United Kingdom (UK)
- Organizations with Microsoft Education subscriptions
- Customers in regions where local processing commitments apply (e.g., the United Arab Emirates)
- Any custom exclusion list provided by Microsoft legal and compliance teams

## Opt-in to Anthropic's models

If your organization is in a region that doesn't support Anthropic as a sub-processor by default, you can choose to opt-in so Anthropic's models are available for your organization.

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **Data access** page, select **AI providers of other external large language models as a sub-processor**.
3. Under **Available sub-processors for your organization**, select **Allow third-party AI sub-processors for Anthropic (Claude)**.

After you connect, it may take a few hours for the connection to complete.

## Additional controls for Copilot Studio in the Power Platform Admin Center

Once enabled in the Microsoft 365 admin center, additional admin controls are available in the Microsoft Power Platform admin center (PPAC) to allow Anthropic to be used in Copilot Studio. For more information, see [Allow external large language models (LLMs) for generative responses](https://go.microsoft.com/fwlink/?linkid=2334706).

## Disable connection to Anthropic's models

Your organization can opt-out to restrict Anthropic models in the Microsoft admin center through \[DATE\]. After \[DATE\], Anthropic models will be available by default. You must be a member of the global administrator role to perform this task. For more information, see [About admin roles](https://learn.microsoft.com) and [Global administrator](/entra/identity/role-based-access-control/permissions-reference)

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **Data access** page, select **AI providers of other external large language models as a sub-processor**.
3. Under **Available sub-processors for your organization**, select **Disable** to disable Anthropic (Claude) for your organization.

Once you disconnect Anthropic, users won't have the option to use Anthropic's AI models. After completing the steps to disconnect Anthropic, it may take several hours for the service to be fully disabled for your users.

## Anthropic as an independent processor

[Anthropic as an independent processor](connect-to-ai-models.md) will be deprecated and replaced by the Anthropic as a sub-processor functionality. For more information, see **TBD**.
