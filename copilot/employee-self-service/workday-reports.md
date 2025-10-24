---
title: Create reports for your Workday integration
f1.keywords:
- NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: scotv
ms.reviewer: semani
ms.date: 10/29/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.custom: ess-agent
description: "Learn how to create the reports for your Workday integration with the Employee Self-Service agent."
---

# Create reports for your Workday integration

>[!NOTE]
>The Employee Self-Service agent is currently in preview. Deployment processes are subject to change before this product becomes generally available.

The ESS agent for Workday requires a few user context attributes including **Employee ID**, **First Name**, **Last Name**, **Is Manager**, and more to be passed to execute a scenario. These attributes are retrieved from the user mapping with matching usernames from both Microsoft Entra and Workday.

For SOAP API set, the following custom report should be created and exposed as a web service (Reports as a Service) to retrieve these attributes:

1. **Create calculated fields**

The following calculated fields should be created at the report level (see definition in the next section) and not as global calculated fields to avoid any accidental notifications by admins:

- ISO 2 Country Code
- Level of Employee
- Worker Type
- CF LRV Sup Org Ref ID

**Abbreviations in the table**

CLRV= Calculation Lookup related value

|Field name |Business object |CLRV Lookup field |CLRV Related business object |CLRV return value |Additional Category |Additional authorized usage |
|----------------------------|----------------|---------------------------|--------|-------------|--------------|--------------|
|CF – ISO 2 Country Code LRV |Worker          |Location Address - Country/Region |Country/Region |Alpha-2 Code |Uncategorized |Default areas |
|CF – EE Level LRV |Worker |Supervisory Organization - Primary Position |Supervisory Organization |Organization on Level from Top |Uncategorized |Default Areas |
|CF – LRV Worker Type        |Workday Account |Worker                     |Worker  |Worker Type  |              |              |
|CF LRV Sup Org Ref ID       |Worker |Manager's Default Supervisory Organization |Supervisory Organization |Reference ID |  |  |

## List of reports

- [Workday User Context Custom Report](workday-reports-user-context.md)
- [Workday User Context Custom Report - SORT](workday-reports-context-sort.md)
- [Workday User Context Custom Report - FILTER](workday-reports-context-filter.md)
- [Workday User Context Custom Report - SUB-FILTER](workday-reports-context-subfilter.md)
- [Workday User Context Custom Report - PROMPTS](workday-reports-context-prompts.md)
- [Workday User Context Custom Report - OUTPUT](workday-reports-context-output.md)
- [Workday User Context Custom Report - SHARE](workday-reports-context-share.md)
- [Workday User Context Custom Report - ADVANCED](workday-reports-context-advanced.md)
