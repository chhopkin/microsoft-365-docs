---  
title: "Block insecure protocols for file opens"  
description: Hypertext Transfer Protocol (HTTP) and File Transfer Protocol (FTP) are outdated protocols that can expose sensitive data because they transmit information in plain text. Blocking file opens using these protocols helps prevent attackers from intercepting credentials or other confidential data during file access.
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

# Block insecure protocols for file opens in Microsoft 365

Hypertext Transfer Protocol (HTTP) and File Transfer Protocol (FTP) are outdated protocols that can expose sensitive data because they transmit information in plain text. Blocking file opens using these protocols helps prevent attackers from intercepting credentials or other confidential data during file access.

When this setting is turned on, users will be prevented from opening files from locations that use HTTP or FTP. Users will not be able to override this configuration in **Trust Center**. This helps enforce secure data transmission practices and reduces exposure to man-in-the-middle attacks. If you need to revert to the default behavior, you can turn off this setting directly in the Microsoft 365 admin center.

## Turn off default setting in the Microsoft 365 admin center

1. Go to the admin center and select Org settings.
1. Select Restricted mode and find the Block Dynamic Data Exchange setting and switch the toggle to **Off**.

## Use Group Policy settings or Office cloud policy service

Alternatively, you can make changes to the Group Policy setting that supports this setting. These changes can be made in the Group Policy Editor or by using the [Office cloud policy service](https://config.office.com/).

The Group Policy setting **Block insecure protocols** can be found in the following path:

- Group Policy path: `User Configuration > Administrative Templates > Microsoft Office 2016 > Security Settings`

To revert to the default behavior, set this policy as not configured.
