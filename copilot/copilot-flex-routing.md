---
title: "European Union Data Boundary (EUDB) Flex Routing"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 03/27/2026
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

Flex routing lets customers in the European Union (EU) and the European Free Trade Association (EFTA) choose to allow large language model (LLM) inferencing and the storage of associated pseudonymized data to occur outside the EU Data Boundary during periods of peak demand.
Inferencing is the phase of processing when an AI model executes the prompt to produce an output or response (for example, generating text, summarizing content, answering a question, or calculating values). At times of peak demand, allowing inferencing to occur in more locations can help keep Copilot responsive for European customers.

Tenant administrators can manage the flex routing setting in the Microsoft 365 admin center or Power Platform admin center. The Microsoft 365 admin center setting applies to Microsoft 365 Copilot and Copilot Chat. The Power Platform admin center setting applies to Copilot experiences in Dynamics 365, Power Platform, and Copilot Studio in Microsoft 365 Copilot.

> [!NOTE]
> By default, the flex routing setting in the Power Platform admin center will match the setting in the Microsoft 365 admin center unless you choose a more restrictive setting in the Power Platform admin center. For more information see <PPAC learn link>.

## Eligibility

Flex routing is available for tenants located in countries in the EU or EFTA. For more information, see [EU Data Boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn).

## Set up flex routing

Flex routing is on by default for tenants in EU and EFTA countries, except for enterprise and public sector tenants that existed before March 25th, 2026.

As the administrator you're encouraged to check your tenant's flex routing setting to ensure it aligns with your company's requirements.

**Enable flex routing**

1. Sign in to the Microsoft 365 admin center as a tenant administrator assigned the [AI Administrator role](/entra/identity/role-based-access-control/permissions-reference).
2. Go to **Copilot** -> **Settings** -> **Flex routing during peak load periods**.
3. Select **Allow flex routing during periods of peak load**.
    1. This setting allows LLM inferencing and the storage of associated pseudonymized data to occur outside the EU data boundary during periods of peak demand. Typically, these periods are limited in duration and do not run continuously.
4. If you don’t want to allow EU flex routing, select **Do not allow EU flex processing**.
    1. If you select this option, LLM inferencing will occur inside the EU Data Boundary, even during periods of peak demand. All Microsoft 365 data processing and data residency commitments will continue to apply.

## Frequently asked questions

### Why don’t I see the flex routing setting in the Microsoft 365 admin center?

The flex routing setting is only visible in the Microsoft 365 admin center for tenants in EU/EFTA countries. See [EU data boundary countries and datacenter locations](/privacy/eudb/eu-data-boundary-learn) for more information.

### How does flex routing affect Microsoft’s EU data boundary commitments?

When flex routing is enabled, LLM inferencing and storage of associated pseudonymized data may occur outside the EUDB. Pseudonymized personal data is personal data that has had direct identifiers removed or replaced so it cannot be attributed to an individual without additional information that is stored separately. EU and EFTA customers can disable flex routing in the Microsoft 365 admin center at any time.

### Where does LLM inferencing occur when flex routing is enabled?

If flex routing is enabled, LLM inferencing may occur in the United States, Canada, or Australia during times of peak demand.

### Will data be stored outside the EU Data Boundary if flex routing is enabled?

Yes, some pseudonymized personal data may be stored outside the EU Data Boundary when flex routing is enabled. Pseudonymized personal data is personal data that has had direct identifiers removed or replaced so it cannot be attributed to an individual without additional information that is stored separately.

### How does flex routing help keep Copilot responsive?

Flex routing helps ensure that during periods of peak demand, some inferencing calls may be routed to regions that are experiencing less demand which results in a more responsive Copilot for all European customers.
