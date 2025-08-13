---  
title: "Minimum versions numbers for Restricted Mode in Office"  
description: Learn about minimum version numbers for restricted mode settings
author: kwekuako 
ms.author: kwekua  
manager:  dansimp
ms.date: 08/13/2025  
ms.topic: overview
ms.service: microsoft-365-admin  
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft  
ms.reviewer: kwekua
audience: admin
ai-usage: ai-assisted  
---

# Minimum Version Requirements for Restricted Mode in Microsoft 365 for Windows

As an admin, it's essential to ensure that your organization is using the correct version of Microsoft 365 apps to fully leverage Restricted Mode functionality. Restricted Mode settings in Office apps are implemented using Cloud Policy settings. This article provides information on the minimum version requirements for Restricted Mode functionality in Microsoft 365 for Windows. For more information, see [Restricted settings mode](restricted-mode-mac.md).

## Minimum version requirements

The recommended minimum version for Restricted Mode functionality in Microsoft 365 for Windows is version 2508. Earlier versions do not support sending telemetry signals from Office clients to the Microsoft 365 admin center to display simulation mode data.

### Restricted settings mode and minimum required versions

| Setting  | Minimum required version  |
|-------------------------------------------------------------------------|----------------------------------------------------------------------------|
| Open ancient legacy formats in Protected View and disallow editing  | 2502 |
| Open old legacy formats in Protected View and save as modern format| 2502 |
|Block ActiveX controls in the Microsoft 365 apps | Available in all currently supported versions of Microsoft 365 for Windows |
| Block OLE Graph and OrgChart objects  | 2503  |
| Block Dynamic Data Exchange (DDE) server launches in Excel | 2503 |
| Block Microsoft Publisher | 2504 |
| Block Basic authentication prompts | Available in all currently supported versions of Microsoft 365 for Windows |
| Block insecure protocols for file opens | 2507 |
| Block FPRPC protocol for file opens | 2507 |

The [Restricted settings mode](restricted-mode-mac.md) topic has details on which Cloud Policy settings support the Restricted Mode setting. Individual Cloud Policy settings can be used to modify Restricted Mode behavior. For example, allowing trusted files in old legacy formats to bypass Protected View while continuing to open all other old legacy format files in Protected View, without turning off the entire Restricted Mode policy.

> [!NOTE]
> If you are managing Microsoft 365 apps using the Group Policy Editor, it is strongly recommended that you migrate to Cloud Policy service. When a policy is configured in both Group Policy and Cloud Policy, the Cloud Policy configuration will take precedence.
