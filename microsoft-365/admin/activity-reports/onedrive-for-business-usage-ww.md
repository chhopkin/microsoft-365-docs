---
title: "OneDrive usage report - Microsoft 365 admin center"
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: hlu
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminTemplateSet
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ai-usage: ai-assisted
description: "Get the OneDrive Usage Report to learn more about the total number of files and storage used across your organization."
ms.date: 04/17/2026
---

# OneDrive usage report - Microsoft 365 admin center

The OneDrive usage report provides a high-level view of the value you get from OneDrive. The report includes details about the total number of files and storage used across your organization. You can drill into it to understand the trends of active OneDrive accounts, how many files are users interacting with as well as the storage used. It also gives you details for each user's OneDrive.

[!INCLUDE [microsoft-365-usage-reports-generic-intro](../../includes/microsoft-365-usage-reports-generic-intro.md)]

## View the OneDrive usage report

For information about the roles needed to view usage reports, see [Microsoft 365 admin center usage reports overview](activity-reports.md).

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.
1. In the navigation menu, select **Reports**. If you don't see **Reports**, select **Show all**, and then select **Reports**.
1. Select <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a>.
1. On the **Usage** page, under **Reports**, select **OneDrive**.
1. On the report page, select the **Usage** tab. 
  
## Interpret the OneDrive usage report

:::image type="content" source="../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png" alt-text="Microsoft 365 reports - Microsoft OneDrive usage report." lightbox="../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png":::

To add or remove columns from the report, select **Choose columns**.  

:::image type="content" source="../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png" alt-text="OneDrive usage report - choose columns." lightbox="../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png":::

To export the report data into an Excel .csv file, select the **Export** link. This exports data of all users and lets you do simple sorting and filtering for further analysis.

The OneDrive usage report displays trends over the last 7, 30, 90, or 180 days. However, if you select a particular day in the report, the table shows data for up to 28 days from the current date (not the date the report was generated).
  
|Metric|Definition|
|:-----|:-----|
|URL |The web address for the user's OneDrive. Note: URL will be empty temporarily. |
|Deleted  |The deletion status of the OneDrive. It takes at least seven days for accounts to be marked as deleted. |
|Owner |The username of the primary administrator of the OneDrive. |
|Owner principal name |The email address of the owner of the OneDrive. |
|Last activity date (UTC) | The latest date a file activity was performed in the OneDrive. If the OneDrive has had no file activity, the value will be blank. |
|Files |The number of files in the OneDrive. |
|Active files | The number of active files within the time period. NOTE: If files were removed during the specified time period for the report, the number of active files shown in the report may be larger than the current number of files in the OneDrive. >  Deleted users will continue to appear in reports for 180 days. |
|Storage used (MB) |The amount of storage the OneDrive uses in MB. |
| Site ID | The site ID of the site. |

[!INCLUDE [display-user-specific-data](../../includes/display-user-specific-data.md)]

> [!IMPORTANT]
> The report only includes users who have a valid OneDrive license.

>[!NOTE]
> The OneDrive site URL might not be displayed in related usage reports. To display the site URL, you can use PowerShell. To follow the steps, see [Use PowerShell to resolve site URLs](resolve-site-urls.md).
