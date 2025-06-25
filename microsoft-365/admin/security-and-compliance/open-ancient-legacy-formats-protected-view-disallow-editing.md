---  
title: "Open legacy formats in Protected View and disallow editing"  
description: Use Office Group policy to disallow editing of legacy formats in Microsoft 365 apps, like Word, Excel, PowerPoint.
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/24/2025  
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
audience: Admin
ai-usage: ai-assisted  
---

# Open ancient legacy formats in Protected View and disallow editing

Ancient legacy file formats in Microsoft 365 apps are vulnerable to memory corruption-related security issues. To mitigate these risks, administrators can configure settings to open these outdated formats in **Protected View** with editing disabled. This approach prevents potential exploits while still allowing users to view the content without risk.

## Setting up protected view for legacy file formats

When the Restricted Mode setting is enabled, legacy file formats will open in **Protected View**, and users will be unable to edit them, even if the file is saved in a trusted location. Users can save files to a modern format but will be blocked from saving them as legacy formats.

### Ancient legacy formats

- Word 2 and earlier binary documents
- Word 6.0 binary documents
- Word 95 binary documents
- Excel 2, 3, 4 Macrosheets and add-in files
- Excel 2, 3, 4 worksheets
- Excel 4 workbooks

## Modifying Group Policy settings

If you have enabled this setting but need to revert to the default behavior of allowing trusted files to bypass Protected View, or allow users to override the editing block using Trust Center, you can modify this setting by making changes to the Group Policy settings that support this Restricted Mode setting. These changes can be made in the Group Policy Editor, by registry key, or by using the [Office cloud policy service](https://config.office.com/).

The Group Policy setting “File block includes trusted files” can be found in the following path and registry key:

- Group Policy path
- Registry key path

To revert to the default behavior, set this policy as not configured for each app (Word, Excel, PowerPoint, and Visio).

The Group Policy settings for opening a given file format in Protected View and disallowing editing can be found in the following paths and registry keys:

Group Policy Path:

- `User Configuration > Administrative templates > Microsoft {App} 2016 > {App} Options > Security > Trust Center`

Registry Key Path:

- `Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\{App}\security`

To revert to the default behavior, set these policies as not configured.
