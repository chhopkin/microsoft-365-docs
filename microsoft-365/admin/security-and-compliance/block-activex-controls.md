---  
title: "Block ActiveX controls in Microsoft 365 apps documents"  
description: Use the Microsoft 365 admin center, Office Group policies or registry keys to block ActiveX controls from running in your Microsoft 365 organization.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/24/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
ms.reviewer: kwekua
audience: admin
ai-usage: ai-assisted  
---

# Block ActiveX controls in Microsoft 365 apps documents

ActiveX controls are small programs used to add interactive features to Microsoft 365 documents and web pages. Due to their history of security vulnerabilities, ActiveX controls are highly susceptible to exploitation by malicious actors. These controls can be used to run harmful code, install malware, or take control of a system when users open compromised files or visit unsafe websites. Consequently, ActiveX is now blocked by default in Microsoft 365 apps.

When this setting is turned on, users in your environment won’t be able to override the default configuration using Trust Center.

If you have turned on this setting but need to revert to the default behavior (allow users to override ActiveX blocking using Trust Center), you can turn this setting off directly in the Microsoft 365 admin center.

## Turn off default setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Restricted mode and find the ActiveX controls setting and switch the toggle to **Off**.

## Use Group Policy settings, registry keys or Office cloud policy service

Alternatively, you can make changes to the Group Policy setting that supports this setting. These changes can be made in the Group Policy Editor, by registry key, or by using the [Office cloud policy service](https://config.office.com/).  

The Group Policy setting “Disable All ActiveX” can be found in the following path and registry key:

- Group Policy path:  
- Registry key path:

To revert to the default behavior, set this policy as not configured.
