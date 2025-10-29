---
title: "Understand Copilot Prompt Gallery"
f1.keywords:
- NOCSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 10/24/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
description: "Learn about the Copilot Prompt Gallery and how it works with your organization."
---

# Understand Prompt Gallery in Copilot

Microsoft Prompt Gallery in Copilot is a resource of Microsoft-created prompts, videos, and articles that help your users understand and use Microsoft Copilot effectively. Prompt Gallery is available within Microsoft Copilot. Unauthenticated users can explore sample prompts online at [Copilot Prompt Gallery](https://m365.cloud.microsoft/copilot-prompts), but they must authenticate to use any of them.

As an admin, you can support Prompt Gallery adoption and success within your organization. This article covers Prompt Gallery architecture, data flows, security, and privacy.

## Overview

:::image type="content" source="media/prompt-gallery-overview.png" alt-text="Screenshot showing the prompts available to try in Copilot Prompt Gallery." lightbox="media/prompt-gallery-overview.png":::

Prompt Gallery is a centralized repository of Microsoft-authored Copilot prompts designed to streamline user onboarding and enhance productivity. This resource offers curated examples that showcase key Copilot capabilities across common business scenarios.

Copilot Prompt Gallery supports:

- **User enablement**: Videos and articles guide users in effective prompting techniques
- **Knowledge sharing**: Prompts can be saved and shared across teams to promote consistency and collaboration
- **Customization**: Each prompt includes tips for personalization and extension, allowing admins and users to tailor experiences to organizational needs

Copilot Prompt Gallery serves as a one-stop hub to help users confidently adopt and optimize Copilot usage.

## Data flow and compliance considerations

Copilot Prompt Gallery processes and manages data in a structured manner to ensure compliance and security. The following are key data flows and compliance considerations:

:::image type="content" source="media/copilot-prompt-gallery-diagram.png" alt-text="Diagram showing the data flow for Copilot Prompt Gallery." lightbox="media/copilot-prompt-gallery-diagram.png":::

Copilot Prompt Gallery is a feature of the Copilot app that allows users to discover, manage, use, and share Copilot prompts:

- Authenticated users can access Copilot Prompt Gallery via Copilot in an app.
- Unauthenticated users can explore sample prompts online at [Copilot Prompts](https://m365.cloud.microsoft/copilot-prompts), but they must authenticate to try any of them.
- Copilot Prompt Gallery accesses Microsoft-authored Copilot prompts from the public catalog, as well as user-created Copilot prompts from user, group, and tenant collections in the Microsoft 365 Substrate data store.

The prompts are stored in collections within the Substrate Data Store, which is a storage type that allows applications to store files and data and enables efficient indexing and search. There are collections for users, groups, and tenants, all of which are within the tenant boundary. All data is encrypted, transported via a secure pipeline, and is accessible only via Substrate APIs.

For information about data, privacy, and security for Microsoft 365 Copilot, see [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md).

## Related content

- [Copilot Prompt Gallery](https://m365.cloud.microsoft/copilot-prompts)
- [Microsoft Copilot help & learning](https://support.microsoft.com/copilot-skilling)
- [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md)
