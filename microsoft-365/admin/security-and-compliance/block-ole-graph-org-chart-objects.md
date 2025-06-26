---  
title: "Block OLE Graph and OrgChart objects"  
description: Block basic authentication in Microsoft 365 apps
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/24/2025  
ms.topic: how-to
ms.service: microsoft-365-admin  
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
audience: admin
ai-usage: ai-assisted  
---

# Block OLE Graph and OrgChart objects

Basic authentication is an outdated authentication method that transmits user credentials in a way that can easily be intercepted and stolen. Blocking basic authentication helps protect users from credential theft, especially during phishing attacks or when accessing services over insecure networks. Because of these security risks, basic authentication is now blocked by default in Microsoft 365 apps.

When users attempt to open files on servers that only use basic authentication, they see a message indicating that the file has been blocked because it uses a sign-in method that might be insecure.

When this setting is turned on, users in your environment won't be able to override the default configuration using Trust Center.

If you have enabled this setting but need to revert to the default behavior (allow users to override the basic authentication blocking using Trust Center), you can turn this setting off directly in the Microsoft 365 admin center.  

## Turn off default setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Restricted mode and find the Block Dynamic Data Exchange setting and switch the toggle to **Off**.

## Use Group Policy settings, registry keys or Office cloud policy service

Alternatively, you can make changes to the Group Policy setting that supports this setting. These changes can be made in the Group Policy Editor, by registry key, or by using the [Office cloud policy service](https://config.office.com/).

The Group Policy setting **Allow Basic Authentication prompts from network proxies** can be found in the following path and registry key:

- **Group Policy path:** `User Configuration > Policies > Administrative Templates > Microsoft Office 2016 > Security settings`
- **Registry key path**: `HKCU\Software\Policies\Microsoft\Office\16.0\Common\Identity > BasicAuthProxyBehavior`

This policy setting controls whether network proxies are allowed to show basic authentication prompts. To revert to the default behavior, set this policy as not configured.

The Group Policy setting **Allow specified hosts to show basic authentication prompts to Office apps** can be found in the following path and registry key:

- **Group Policy path**:  `User Configuration > Administrative Templates > Microsoft Office 2016 > Security Settings`
- **Registry key path**: `HKCU\Software\Policies\Microsoft\Office\16.0\Common\identity > BasicHostAllowList`

This policy setting controls whether specific hosts can show Basic authentication sign-in prompts. To revert to the default behavior, set this policy as not configured.