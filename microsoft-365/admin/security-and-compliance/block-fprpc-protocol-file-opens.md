---  
title: "Block FPRPC protocol for file opens"
description: FPRPC (FrontPage Server Extensions Remote Procedure Call) is an outdated protocol that poses security risks. It can be exploited by attackers to execute arbitrary commands or compromise systems through specially crafted files or network traffic. Due to these risks, Microsoft 365 apps block FPRPC by default. When FPRPC fallback is blocked, the app will attempt to open the file using HTTPS instead.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/25/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft  
ms.reviewer: kwekua
audience: Admin 
ai-usage: ai-assisted  
---  

# How to Block FrontPage Server Extensions Remote Procedure Call (FPRPC) for file opens in Microsoft 365

FrontPage Server Extensions Remote Procedure Call (FPRPC) is an outdated protocol that poses security risks. It can be exploited by attackers to execute arbitrary commands or compromise systems through specially crafted files or network traffic. Due to these risks, Microsoft 365 apps block FPRPC by default. When FPRPC fallback is blocked, the app will attempt to open the file using HTTPS instead.

When this setting is turned on, users in your environment won’t be able to override the default configuration using Trust Center.

If you have turned on this setting and you need to revert to the default behavior, allowing users to override FPRPC blocking using Trust Center, you can turn off the Restricted Mode setting directly in the Microsoft 365 admin center.

## Turn off default setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Restricted mode and find the Block Dynamic Data Exchange setting and switch the toggle to **Off**.

## Use Group Policy settings or Office cloud policy service

Alternatively, you can make changes to the Group Policy setting that supports this setting. These changes can be made in the Group Policy Editor or by using the [Office cloud policy service](https://config.office.com/).

The Group Policy setting **Restrict Apps from FPRPC Fallback** can be found in the following path:

- Group Policy path: `User Configuration > Administrative Templates > Microsoft Office 2016 > Security Settings > Restrict apps from FPRPC fallback`

To revert to the default behavior, set this policy as not configured.
