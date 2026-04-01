---
author: cmcatee-MSFT
ms.author: cmcatee
ms.collection: 
manager: scotv
ms.service: microsoft-365-business
ms.topic: include
description: Procedure to dispay user-specific data in usage reports. Used in multiple articles. 
ms.date: 03/31/2026
---

## Display user-specific data

Reports provide information about your organization's usage data. By default, usernames and display names in usage reports are anonymous. Global administrators can update the settings to reveal usernames and display names if their organization's privacy practices allow it.

[!INCLUDE [global-administrator-note](global-administrator-note.md)]

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, go to **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Org Settings</a>. 
1. Select the **Services** tab, then select **Reports**.
1. In the **Reports** panel, select the checkbox next to **Display Concealed user, group, and site names in all reports**. 
1. Select **Save**. 
  
It takes a few minutes for these changes to take effect. Showing identifiable user information is a logged event in the Microsoft Purview portal audit log.
