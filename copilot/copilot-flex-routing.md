---
title: "European Union Data Boundary (EUDB) Flex Routing"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 03/24/2026
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
description: "Learn about flex routing and how it affects inferencing for Microsoft 365 Copilot and Copilot chat during times of peak load."
---

# European Union Data Boundary (EUDB) flex routing

Flex routing lets customers in the European Union (EU) and the European Free Trade Association (EFTA) choose to allow large language model (LLM) inferencing – and storage of associated pseudonymized data – outside the EU Data Boundary during periods of peak demand. Inferencing is the phase of processing when an AI model executes the prompt to produce an output or response (for example, generating text, summarizing content, answering a question, or calculating values). At times of peak demand, more flexibility in where LLM inferencing can occur helps keep Copilot responsive for European customers. Tenant administrators can access the flex routing setting in the Microsoft 365 admin center. This setting applies to Copilot in Microsoft 365, Dynamics 365, Power Platform, and Copilot Studio.

> [!NOTE]
> If flex routing is allowed in the Microsoft 365 admin center, you can also access this setting in the Power Platform admin center. By default, the flex routing setting in the Power Platform admin center will match the setting in the Microsoft 365 admin center unless you choose a more restrictive setting in the Power Platform admin center. For more information see <PPAC learn link>.

## Eligibility

Flex routing is available for tenants located in countries in the EU or EFTA. For more information, see [EU Data Boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn).

## Set up flex routing

Flex routing is on by default for tenants in EU and EFTA countries, except for enterprise and public sector tenants that were created before March 25th, 2026.

As the administrators you're encouraged to check your tenant's flex routing setting to ensure it aligns with your company's requirements.

1. Sign in to the Microsoft 365 admin center as a tenant administrator assigned the [AI Administrator role](/entra/identity/role-based-access-control/permissions-reference).
2. Go to **Copilot** -> **Settings** -> **EU flex routing for Microsoft 365 Copilot.**.
3. Select **Allow EU flex routing for Microsoft 365 Copilot**.
    1. This setting allows Microsoft to execute some LLM calls outside of the EU during exceptional, high-demand time windows. All Microsoft 365 data processing and data residency commitments will continue to apply, and all data will remain encrypted both in transit and at rest.
4. If you don’t want to allow EU flex routing, select **Don’t allow EU flex processing**.
    1. If you select this option, LLM requests will be processed inside the EU Data Boundary, even at times of peak load.

## Frequently asked questions

### Why don’t I see the flex routing setting in the Microsoft 365 admin center?

The flex routing setting is only visible for tenants located in EU or EFTA countries. Tenants outside these regions do not see this option. See the [EU data boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn) topic for more information.

### How does flex routing affect Microsoft’s EU data boundary commitments?

Microsoft 365 data residency and processing commitments remain unchanged. All data is encrypted both in transit and at rest, and you can disable flex routing at any time to ensure LLM inferencing occurs inside the EU data boundary.

### Where does LLM inferencing occur when flex routing is enabled?

If flex routing is enabled, LLM inferencing may occur in the United States, Canada, or Australia during times of peak load, depending on available capacity.

### Will Customer Data be stored outside the EU data boundary when flex routing is enabled?

No, flex routing is limited to LLM inferencing and doesn't change where Customer Data is stored.

### Can I see where LLM inferencing occurs when flex routing is enabled?

There is currently no way for customers to see where LLM inferencing occurs, regardless of their flex routing setting.

