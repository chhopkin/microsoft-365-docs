---
title: "European Union data boundary (EUDB) Flex Routing"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 03/11/2026
audience: Admin
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Microsoft 365copilot
- magic-ai-copilot
- essentials-overview
- operations-pod
- OtherAILLMs
appliesto:
- ✅ Microsoft 365 Copilot
description: "Learn about Anthropic as a subprocessor for Microsoft."
---

# European Union data boundary (EUDB) flex routing

Flex routing allows customers in the European Union (EU) and the European Free Trade Association (EFTA) to choose whether large language model (LLM) inferencing for Microsoft 365 Copilot and Copilot chat can occur outside the [EU Data Boundary](/privacy/eudb/eu-data-boundary-learn) during times of peak load.

This helps ensure the best possible experience for customers in EU and EFTA countries as demand continues to surge for Microsoft 365 Copilot and Copilot Chat.

## Eligibility

Flex routing is available to Microsoft 365 tenants located in countries that are part of the EU or EFTA. For more information, see [EU Data Boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn).

## How flex routing works

Flex routing is specific to the LLM inferencing step for Microsoft 365 Copilot and Copilot Chat. This is the moment when Copilot sends a user’s prompt, along with the grounding data needed to answer it, to a large language model to generate a response.  

When flex routing is enabled, LLM inferencing may occur in the United States, Canada, or Australia during times of peak load. EU and EFTA customers can change their flex routing setting in the Microsoft 365 admin center under Copilot.

> [!NOTE]
> Flex routing doesn't change where customer content is stored or how it is protected. Microsoft 365 data residency, encryption, and processing commitments remain unchanged. For more information, see the EU Data Boundary documentation on LMC.

## Update the flex routing setting

Flex routing is on by default for tenants in EU and EFTA countries, except for enterprise and public sector tenants that were created before **April X, 2026**.

Review the flex routing setting in your tenant to ensure it aligns with your organizations requirements and compliance policies. To update the settings, follow these steps.

1. Sign in to the Microsoft 365 admin center using an account with the required administrative permissions.
2. Go to **Copilot** -> **Settings** -> **Flex routing**.
3. Select the option to allow LLM requests to be processed outside the EU data boundary during peak loads.
4. Or select the option to require all LLM requests to be processed inside the EU data boundary, even during times of peak load.

## Frequently asked questions

### Why don’t I see the flex routing setting in the Microsoft 365 admin center?

The flex routing setting is only visible for tenants located in EU or EFTA countries. Tenants outside these regions do not see this option. See the [EU data boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn) topic for more information.

### How does flex routing affect Microsoft’s EU data boundary commitments?

Microsoft 365 data residency and processing commitments remain unchanged. All data is encrypted both in transit and at rest, and you can disable flex routing at any time to ensure LLM inferencing occurs inside the EU data boundary.

### Where does LLM inferencing occur when flex routing is enabled?

If flex routing is enabled, LLM inferencing may occur in the United States, Canada, or Australia during times of peak load, depending on available capacity.

### Is customer content stored outside the EU data boundary when flex routing is enabled?

No, flex routing is limited to LLM inferencing and doesn't change where customer content is stored.

### Can I see where LLM inferencing occurs when flex routing is enabled?

There is currently no way for customers to see where LLM inferencing occurs, regardless of their flex routing setting.
