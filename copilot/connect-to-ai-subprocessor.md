---
title: "Anthropic as a subprocessor for Microsoft 365 Copilot"
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

# Anthropic as a subprocessor for Microsoft 365 Copilot

Microsoft is introducing a new offering with Anthropic AI models as part of Microsoft Online Services, delivering enterprise-grade commitments and safeguards to ensure secure and responsible use of Anthropic models within your organization.

To enable this change, Anthropic has onboarded as a Microsoft subprocessor. As part of this update, we are deprecating the previous option that allowed Microsoft tenant admins to opt-in to use Anthropic under Anthropic’s separate commercial terms and data processing agreement. This change simplifies the experience and strengthens compliance and security under Microsoft’s enterprise framework.

As a subprocessor, Anthropic will operate with Microsoft oversight through contractual safeguards and appropriate technical and organizational measures. The Microsoft [Product Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd) and [Microsoft Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) apply to use of Anthropic through Microsoft’s enterprise Online Services. It is also covered under our [Enterprise Data Protection](enterprise-data-protection.md). The Microsoft [Customer Copyright Commitment (CCC)](/azure/ai-foundry/responsible-ai/openai/customer-copyright-commitment) applies to Anthropic models used within products covered by the CCC’s, including Microsoft 365 Copilot and Copilot Studio.

For more information about subprocessor data access, see [Microsoft Data Access Management](https://www.microsoft.com/trust-center/privacy/data-access). To see a list of Microsoft subprocessors, see [Service Trust Portal](https://servicetrust.microsoft.com/DocumentPage/7a132d00-29c2-4d26-b0f5-486923c41223).

Microsoft will enable Anthropic models by default for many organizations. This update gives users in your organization the ability to use multiple AI models in their Microsoft 365 Copilot experiences. This affirms Microsoft’s commitment to offering choice between leading AI models while maintaining enterprise-grade security and compliance.

> [!IMPORTANT]
> Anthropic models deployed in Microsoft 365 Copilot, Researcher, and Copilot Studio are currently excluded from EU Data Boundary. Customers within the EU Data Boundary and customers in the UK will have Anthropic models disabled by default. Anthropic models are not currently available for use in government clouds (GCC, GCC High, DoD) or sovereign clouds.

## Manage Anthropic's model settings in the Microsoft 365 admin center

Microsoft is making Anthropic models available by default in certain regions. In Microsoft 365 Copilot (web, desktop, and mobile), UI indicators will show when Anthropic and Claude models are in use. In Copilot Studio, creators must select the model during agent creation. In Agent mode for Excel and Researcher, users can select Try Claude.

## Before you begin

Before users in your organization can use Anthropic in Microsoft 365 Copilot and in Microsoft Copilot Studio, they need to be assigned a [Microsoft 365 Copilot license](../microsoft-365/admin/manage/assign-licenses-to-users.md).

## Opt-in regions and exclusions

In some regions, Anthropic’s models are not available by default. For these regions and entities, the toggle will appear but the default is **Off**. These regions include the European Union (EU), the European Free Trade Association (EFTA), and the United Kingdom (UK).

In addition, Anthropic models are not available in government clouds (GCC, GCC High, DoD) as there is no FedRAMP certification in place yet. They are also not yet available in other sovereign clouds. No toggle will be present for government or sovereign clouds.

## Opt-in to use Anthropic's models

If your organization is in a region that has Anthropic as a subprocessor set to **Off** by default, you can choose to opt-in so Anthropic's models are available for your organization. You must be a member of the global administrator role to perform this task. For more information, see [About admin roles](https://learn.microsoft.com) and [Global administrator](/entra/identity/role-based-access-control/permissions-reference).

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **User access** page, select **AI providers operating as Microsoft subprocessors**.
3. On the **AI providers operating as Microsoft subprocessors** page, under available subprocessors for your organization, select **Enable Anthropic as a Microsoft subprocessor subject to the above terms**.

After you connect, it may take a few hours for the connection to complete.

> [!NOTE]
> Some features are only available when Anthropic models are enabled. If you turn off Anthropic as a subprocessor, certain features may no longer be accessible.

## Additional controls for Copilot Studio in the Power Platform Admin Center

Once enabled in the Microsoft 365 admin center, additional admin controls are available in the Microsoft Power Platform admin center (PPAC) to allow Anthropic to be used in Copilot Studio. For more information, see [Allow external large language models (LLMs) for generative responses](https://go.microsoft.com/fwlink/?linkid=2334706).

## Disable connection to Anthropic's models

If your organization is in a region that has Anthropic as a subprocessor set to **On** by default, you can opt-out to restrict Anthropic models in the Microsoft 365 admin center. You must be a member of the global administrator role to perform this task. For more information, see [About admin roles](https://learn.microsoft.com) and [Global administrator](/entra/identity/role-based-access-control/permissions-reference).

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **User access** page, select **AI providers operating as Microsoft subprocessors**.
3. On the **AI providers operating as Microsoft subprocessors** page, under **Available subprocessors for your organization**, select **Disable Anthropic as a Microsoft subprocessor**.

Once you disable Anthropic as an AI subprocessor, users won't have the option to use Anthropic's AI models. After completing the steps to disable Anthropic, it may take several hours for the service to be fully disabled for your users.

## Deprecation of legacy Anthropic admin toggle

The legacy Anthropic toggle to opt-in to Anthropic’s [separate commercial terms and data processing agreement](connect-to-ai-models.md) will be deprecated and replaced by this new Anthropic as a subprocessor admin toggle.

- Dec 8, 2025: New admin toggle for Anthropic models will appear in the Microsoft 365 admin center, enabled by default. [Some customer and region exclusions apply](#opt-in-regions-and-entities).
- January 7, 2026: Anthropic as a Microsoft subprocessor becomes enabled on your tenant. The legacy admin toggle to opt-in to Anthropic’s commercial Terms and Data Processing agreement is deprecated. You will not have the option to use Anthropic as an Independent Data Processor after this date.
    - If you previously opted in to the legacy Anthropic toggle, and you’re in an excluded region, you need to opt in to the new subprocessor toggle to use Anthropic’s AI provider.
