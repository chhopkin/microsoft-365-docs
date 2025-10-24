---
title: User context custom report for Workday integration
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
description: "Learn about the user context custom report for your Workday integration with the Employee Self-Service (ESS) agent."
---

# Workday User Context Custom Report

This report is used for retrieving the required user context attributes from Workday. Refer to the tables to create a custom report following each of the tables as different configuration sections in the Workday custom report.

**View Custom Report: WD User Context - COLUMNS**

|Report Name                  |WD User Context      |
|-----------------------------|---------------------|
|Report Name                  |WD User Context      |
|Report Type                  |Advanced             |
|Data Source                  |All Workday Accounts |
|Data Source Type             |Standard             |
|Primary Business Object      |Workday Account      |
|Report Definition Usages     |0                    |
|Saved Filter Usages          |0                    |
|Data Source Description      |Accesses the Workday Account object and returns one row per Workday account. Includes all Workday accounts ever created, either currently enabled or not. Doesn't contain built-in prompts. This data source shows settings of a user's sign in information and preferences in Workday.     |
|Brief Description            |                     |
|Passes Report Column Toggles |                     |

**Columns**

|Business Object |Field                            |Column Heading Override XML Alias |Format |Options |
|----------------|---------------------------------|----------------------------------|-------|--------|
|Worker          | Preferred Name - First Name     |First_Name                        |       |        |
|Worker          |Preferred Name - Last Name       |Last_Name                         |       |        |
|Worker          |Email - Primary Work             |Work_Email                        |       |        |
|Workday Account |User Name                        |User_Name                         |       |        |
|Worker          |Employee ID                      |Employee_ID                       |       |        |
|Worker          |CF - ISO 2 Country Code LRV      |Country_Code                      |       |        |
|Worker          |Company - ID                     |Company_Code                      |       |        |
|Worker          |Is Manager                       |Is_Manager                        |       |        |
|Worker          |Is People Manager (with prompts) |Is_People_Manager                 |       |        |
|Worker          |CF - EE Level LRV                |Level                             |       |        |
|Workday Account |Display Language                 |Display_Language                  |       |        |
|Workday Account |Locale                           |Locale                            |       |        |
|Worker          |CF LRV Sup Org Ref ID            |Mgr_Sup_Org_Id                    |       |        |

**Group Column Headings**

|Business Object |Group Column Heading XML Alias |
|----------------|-------------------------------|
|Worker          |Worker_group                   |
