---
title: User context custom report - PROMPTS for Workday integration
f1.keywords:
- NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 10/29/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.custom: ess-agent
description: "Learn about the user context custom report - PROMPTS for your Workday integration with the Employee Self-Service (ESS) agent."
---

# Workday User Context Custom Report - PROMPTS

|Report Name                        |WD User Context              |
|-----------------------------------|-----------------------------|
|Report Type                        |Advanced                     |
|Data Source                        |All Workday Accounts         |
|Data Source Type                   |Standard                     |
|Primary Business Object            |Workday Account              |
|Report Definition Usages           |0                            |
|Saved Filter Usages                |0                            |
|**Additional Info**                |                             |
|Data Source Description            |Accesses the Workday Account object and returns one row per Workday account. Includes all Workday accounts ever created, either currently enabled or not. Doesn't contain built-in prompts. This data source shows settings of a user's sign in information and preferences in Workday.          |
|Brief Description                  |                             |
|Passes Report Column Toggles       |                             |
|**Prompts**                        |                             |
|Specify the prompt defaults to use |                             |
|**Prompt instructions**            |                             |
|Instructions                       |                             |
|**Runtime data prompts**           |                             |
|Effective date                     |Use date and time at runtime |
|Entry date                         |Use date and time at runtime |
|Display prompt values in subtitle  |Yes                          |

**Prompt Defaults**

|Field |Prompt qualifier |Label for prompt |label for prompt XML alias |Default type |Default value |Required |Don't prompt at runtime |Don't include in subtitle |
|------|-----------------|-----------------|---------------------------|-------------|--------------|---------|---------------|-----------------------------------|
|User Name |Default prompt |  |User_Name |No default value |  |Yes |  |  |
|Employee Type | |  |Employee_Type |No default value |  |  |Yes |  |
|Non-Employee Type | |  |Employee_Type |No default value |  |  |Yes |  |
|Include managers of employees |  |  |Include_managers_of_employees |Specialty default value |Yes |  |Yes |  |
|Include managers of nonemployees |  |  |Include_managers_of_non_employees |No default value |  |  |Yes |  |
|Include managers of unfilled positions only |  |  |Include_managers_of_unfilled_positions_only |No default value |  |  |Yes |  |
