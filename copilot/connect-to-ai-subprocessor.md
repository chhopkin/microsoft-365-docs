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

Microsoft has transitioned Anthropic from an Independent Data Processor (IDP) to a subprocessor for Copilot. This change means Copilot experiences that use Anthropic models now include Microsoft contractual commitments, data protection standards, and compliance with Microsoft’s privacy requirements.

As a subprocessor, Anthropic will operate under Microsoft’s direction and contractual safeguards. This includes coverage under the the [Microsoft Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA?lang=18&msockid=344e0e6ad66c6b3e19441848d7416abd) and and [Product Terms](https://www.microsoft.com/licensing/terms?msockid=344e0e6ad66c6b3e19441848d7416abd) with Microsoft remaining accountable for Anthropic’s compliance under our contractual commitments. In addition, use of Anthropic models in Microsoft 365 Copilot falls under our Enterprise Data Protection.

For more information about subprocessor data access, see [Microsoft Data Access Management](https://www.microsoft.com/trust-center/privacy/data-access). To see a list of Microsoft subprocessors, see [Service Trust Portal](https://servicetrust.microsoft.com/DocumentPage/7a132d00-29c2-4d26-b0f5-486923c41223).

Microsoft will enable Anthropic models by default for many organizations. This update gives users in your organization the ability to choose from multiple AI models in their Microsoft 365 Copilot experiences. This affirms Microsoft’s commitment to offering choice between leading AI models while maintaining enterprise-grade security and compliance.

> [!IMPORTANT]
> Anthropic models deployed in Microsoft 365 Copilot, Researcher, and Copilot Studio are currently excluded from EU Data Boundary and in-country processing commitments. Learn more about how Anthropic models work with Microsoft 365 Copilot here: (link to new page for Anthropic – draft copy here). Customers within the European Union data boundary and customers in the UK will have Anthropic models disabled by default. Anthropic’s models are not supported in Government clouds (GCC, GCC High, DoD).

Your users can elect to use Anthropic's AI models in Microsoft 365 Copilot, with [Researcher](https://support.microsoft.com/topic/use-claude-with-researcher-in-microsoft-365-copilot-23e2503b-d73e-4abb-902d-b9814205a38a), [Agent mode in Excel](https://support.microsoft.com/office/agent-mode-in-excel-frontier-a2fd6fe4-97ac-416b-b89a-22f4d1357c7a) and [Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/authoring-select-external-response-model). Anthropic’s AI models can help people in your organization with some of the following:

- Summarize complex information
- Answer questions using source material
- Synthesize across multiple sources
- Generate ideas, draft, and edit content

## Manage Anthropic's model settings in the Microsoft 365 admin center

Microsoft is making Anthropic models will be available by default in certain regions for Microsoft 365 Copilot. Your organization will no longer be required to opt-in to Anthropic’s Commercial Terms of Service to use Anthropic models in Microsoft 365 Copilot eExperiences.

In the Microsoft 365 Copilot (web, desktop, and mobile), UI indicators will show when Anthropic and Claude models are in use. In Copilot Studio, makers must select the model during agent creation. In Agent mode for Excel and Researcher, users can select Try Claude.

## Before you begin

Before users in your organization can use Anthropic in Microsoft 365 Copilot and in Microsoft Copilot Studio, they need to be assigned a [Microsoft 365 Copilot license](../microsoft-365/admin/manage/assign-licenses-to-users.md).

## Opt-in regions and entities

In some regions, Anthropic’s models are not available by default. For these regions and entities, the toggle will appear but remain **Off**.  These regions include:

- The European Union (EU), the European Free Trade Association (EFTA), the United Kingdom (UK).

Some organizations can't access Anthropic models. These include:

- Organizations with Microsoft Education subscriptions
- Sovereign cloud customers
- Government entities/customers

## Opt-in to use Anthropic's models

If your organization is in a region that doesn't support Anthropic as a sub-processor by default, you can choose to opt-in so Anthropic's models are available for your organization.

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **Data access** page, select **AI providers of other external large language models as a sub-processor**.
3. Under **Available sub-processors for your organization**, select **Allow third-party AI sub-processors for Anthropic (Claude)**.

After you connect, it may take a few hours for the connection to complete.

## Additional controls for Copilot Studio in the Power Platform Admin Center

Once enabled in the Microsoft 365 admin center, additional admin controls are available in the Microsoft Power Platform admin center (PPAC) to allow Anthropic to be used in Copilot Studio. For more information, see [Allow external large language models (LLMs) for generative responses](https://go.microsoft.com/fwlink/?linkid=2334706).

## Disable connection to Anthropic's models

Your organization can opt-out to restrict Anthropic models in the Microsoft admin center through **\[DATE\]**. After **\[DATE\]**, Anthropic models will be available by default. You must be a member of the global administrator role to perform this task. For more information, see [About admin roles](https://learn.microsoft.com) and [Global administrator](/entra/identity/role-based-access-control/permissions-reference)

1. Go to the Microsoft 365 admin center and select **Copilot** -\> **Settings**.
2. On the **Data access** page, select **AI providers of other external large language models as a sub-processor**.
3. Under **Available sub-processors for your organization**, select **Disable** to disable Anthropic (Claude) for your organization.

Once you disconnect Anthropic, users won't have the option to use Anthropic's AI models. After completing the steps to disconnect Anthropic, it may take several hours for the service to be fully disabled for your users.

## Anthropic as an independent processor deprecation

Anthropic as an [independent data processor (IDP)](connect-to-ai-models.md) will be deprecated and replaced by Anthropic as a sub-processor functionality.

- Effective December 8, 2025, the new admin toggle for Anthropic models will appear in the Microsoft admin center, enabled by default [Some customer and region exclusions apply](#opt-in-regions-and-entities).
- Effective January 7, 2026, Anthropic becomes a Microsoft subprocessor. The independent data processor (IDP) toggle is deprecated. If you opted in to the IDP and you're in a default off country you will need to opt in to the new subprocessor toggle.
