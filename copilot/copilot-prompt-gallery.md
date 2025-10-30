---
title: "Understand Prompt Gallery in Copilot"
f1.keywords:
- NOCSH
ms.author: mabond
author: mkbond007
manager: dansimp
ms.date: 10/30/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
description: "Learn about the Copilot Prompt Gallery and how your users can use Copilot prompts in your organization."
---

# Understand Prompt Gallery in Copilot

Microsoft Prompt Gallery in Copilot is a resource of Microsoft-created prompts, videos, and articles that help your users understand and use Microsoft Copilot effectively. Prompt Gallery is available within Microsoft 365 Copilot or Copilot Chat.

As an admin, you can use analytics and reporting tools to track usage and engagement with Prompt Gallery content, including the following:

- The saved, liked, and shared prompts of a specific user.
- The prompts shared with a specific team.

For information on how you can export this data, see [Export prompts that users saved, liked, or shared in Prompt Gallery](copilot-prompt-gallery-export-prompts.md).

This article covers Prompt Gallery architecture, data flows, security, and privacy.

## Overview

:::image type="content" source="media/copilot-prompt-gallery-overview.png" alt-text="Screenshot showing the prompts available to try in Copilot Prompt Gallery." lightbox="media/copilot-prompt-gallery-overview.png":::

Prompt Gallery is a comprehensive catalog of Copilot prompts created by Microsoft that highlights key scenarios and capabilities of Microsoft Copilot, designed to help users become proficient in using Copilot to accomplish their tasks.

Copilot prompts can also be saved and shared across teams using Prompt Gallery to promote consistency and collaboration. Each prompt within Prompt Gallery includes tips for personalization and extension, allowing users to tailor experiences to organizational needs.

For more information about how your users can use Copilot Prompt Gallery, see [Learn about Copilot prompts](https://support.microsoft.com/topic/f6c3b467-f07c-4db1-ae54-ffac96184dd5) and [Sharing prompts with your team](https://support.microsoft.com/topic/2fa7a228-8645-4dc4-beec-d75d6d0bc752).

## Data flow and compliance considerations

Prompt Gallery processes and manages data in a structured manner to ensure compliance and security. The following are key data flows and compliance considerations:

:::image type="content" source="media/prompt-gallery-copilot-architecture.png" alt-text="Diagram showing the data flow for Prompt Gallery in the Copilot app." lightbox="media/prompt-gallery-copilot-architecture.png":::

1. Authenticated users can access Prompt Gallery from Microsoft 365 Copilot or Copilot Chat (including within Microsoft Word). For users that aren't authenticated, they can only see Microsoft-authored prompts online at [Copilot Prompts](https://m365.cloud.microsoft/copilot-prompts), but they must authenticate to try any of them in Copilot.
1. Prompt Gallery accesses Microsoft-authored Copilot prompts from the public catalog.
1. Prompt Gallery also accesses user-created Copilot prompts from user, group, and tenant collections in the Microsoft 365 Substrate data store.

The Copilot prompts are stored in collections within the Substrate Data Store, which is a storage type that allows applications to store files and data and enables efficient indexing and search. There are collections for users, groups, and tenants, all of which are within the tenant boundary. All data is encrypted, transported via a secure pipeline, and is accessible only via Substrate APIs.

## Related content

- [Export prompts that users saved, liked, or shared in Copilot Prompt Gallery](copilot-prompt-gallery-export-prompts.md)
- [Copilot Prompt Gallery](https://m365.cloud.microsoft/copilot-prompts)
- [Microsoft Copilot help & learning](https://support.microsoft.com/copilot-skilling)
- [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md)
