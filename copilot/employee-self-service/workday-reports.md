---
title: Creating reports for your Workday integration
f1.keywords:
- NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: scotv
ms.reviewer: semani
ms.date: 11/05/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.custom: ess-agent
description: "Learn how to create reports for your Workday integration with the Employee Self-Service agent."
---

# Create reports for your Workday integration

>[!NOTE]
>The Employee Self-Service agent is currently in preview. Deployment processes are subject to change before this product becomes generally available.

The Employee Self-Service agent for Workday requires a few user context attributes including **Employee ID**, **First Name**, **Last Name**, **Is Manager**, and more to be passed to execute a scenario. These attributes are retrieved from the user mapping with matching usernames from both Microsoft Entra and Workday.

For SOAP API set, the following custom report should be created and exposed as a web service (Reports as a Service) to retrieve these attributes:

## Create calculated fields

The following calculated fields should be created at the report level (see definition in the next section) and not as global calculated fields to avoid any accidental notifications by admins:

- ISO 2 Country Code
- Level of Employee
- Worker Type
- CF LRV Sup Org Ref ID

## List of reports

- [Workday User Columns Custom Report](workday-user-columns-support-config.md)
- [Workday User Context Custom Report - SORT](workday-sort-support-config.md)
- [Workday User Context Custom Report - FILTER](workday-filter-support-config.md)
- [Workday User Context Custom Report - SUB-FILTER](workday-sub-filter-support-config.md)
- [Workday User Context Custom Report - PROMPTS](workday-prompts-support-config.md)
- [Workday User Context Custom Report - OUTPUT](workday-output-support-config.md)
- [Workday User Context Custom Report - SHARE](workday-share-support-config.md)
- [Workday User Context Custom Report - ADVANCED](workday-advanced-support-config.md)
