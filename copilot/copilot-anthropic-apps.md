---
title: "Copilot in Microsoft 365 apps with Anthropic models"
ms.author: kwekua
author: kwekuako
ms.update-cycle: 180-days
manager: scotv
ms.date: 03/27/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
- operations-pod
- OtherAILLMs
appliesto:
- ✅ Microsoft 365 Copilot
description: "Learn about the new toggle for Microsoft 365 apps for Anthropic in Europe."
---

# Copilot in Microsoft 365 apps with Anthropic models

To provide additional flexibility in model choice for customers in the European Union (EU), European Free Trade Association (EFTA), and United Kingdom (UK), Microsoft 365 Copilot includes an admin setting that enables the use of Anthropic models in Copilot experiences across Word, Excel, and PowerPoint.

This setting allows Microsoft 365 Copilot in supported Microsoft 365 apps to use Anthropic models by default when generating or refining content.

## Anthropic model availability in Microsoft 365 apps

As the admin, you can manage the Anthropic model setting in the Microsoft 365 admin center. When this setting is turned on, Anthropic models are available for use in Copilot experiences across:

- Microsoft Excel  
- Microsoft PowerPoint  
- Microsoft Word *(support for Anthropic models will be added in summer, 2026)*

This setting applies only to Copilot experiences within these apps and does not affect Anthropic model usage in other Microsoft 365 Copilot features or services. It is separate from the [global Anthropic subprocessor setting in Microsoft 365](connect-to-ai-subprocessor.md). Changes to this setting do not modify global subprocessor configurations.

## Data processing and the EU Data Boundary

When Anthropic models are used in Copilot experiences in Word, Excel, or PowerPoint, data processing for these models occurs outside of the Microsoft EU Data Boundary (EUDB).

[Anthropic operates as a Microsoft subprocessor](connect-to-ai-subprocessor.md) and is subject to Microsoft Product Terms and the Microsoft Data Protection Addendum (DPA).

## Manage the setting in the Microsoft 365 admin center

1. Sign in to the Microsoft 365 admin center as an administrator assigned the **AI Administrator** role.  
2. Go to **Copilot** -> **Settings** -> **View All** -> **AI providers operating as Microsoft Subprocessor**.
3. Confirm the correct setting for your organization.
