title: Microsoft 365 Copilot Personal Content Mode
description: Personal Content Mode (PCM) is a functionality that restricts the file content that Copilot can reason over.
ROBOTS: NOINDEX, NOFOLLOW
ms.author: davidedwards
author: davidedwards365
ms.update-cycle: 180-days
manager: scotv
ms.date: 12/02/2025
audience: Admin
ms.reviewer: s.francis
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- operations-pod
appliesto:
- ✅ Microsoft 365 Copilot
---

# Overview of Personal Content Mode

Personal Content Mode (PCM) is a functionality that restricts the file content that Copilot can reason over. In Personal Content Mode, the scope of Copilot's reasoning capabilities is limited to a user's personal graph. This restriction doesn't impact Search capabilities. The personal graph's scope is very similar to the boundaries defined by Restricted SharePoint Search, as explained at [Restricted SharePoint Search - SharePoint in Microsoft 365 | Microsoft Learn](/sharepoint/restricted-sharepoint-search#how-does-restricted-sharepoint-search-work). The personal graph is defined by the following file restrictions:

- Users' OneDrive files and files they have access to
- Files from their frequently visited SharePoint sites
- Files that were shared directly with them 
- Files that the users viewed, edited, or created

Unlike Restricted SharePoint Search, PCM does not use an allow list and does not limit users' ability to locate content with SharePoint Search. In Personal Content Mode, both Enterprise Search and custom Search applications continue to work without restrictions.

# Service Plan setting

A setting in the Enterprise Service Plan provides users with PCM when the service plan is off. To make PCM available to individual users, an admin must update a Copilot-licensed user's individual service plan setting called *Microsoft Copilot with Graph-grounded chat* by unchecking the box associated with that plan, as depicted in the screenshot below. When this box is checked for a given user, Copilot will reason over that user's entire M365 Graph without PCM.

:::image type="content" source="media/PCM_ServicePlanSetting.png" alt-text="Screenshot that shows the Microsoft 365 Copilot Enterprise Service Plan setting for Personal Content Mode.":::

# FAQ

