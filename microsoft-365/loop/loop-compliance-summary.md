---
ms.date: 01/26/2026
ms.update-cycle: 180-days
title: "Summary of governance, lifecycle, and compliance capabilities for Loop experiences"
ms.reviewer: dancost, tonchan
ms.author: odocspr
author: officedocspr5
manager: jtremper
recommendations: true
audience: Admin
f1.keywords:
- NOCSH
ms.service: loop
ms.localizationpriority: medium
ms.topic: concept-article
ms.collection:
- Strat_SP_admin
- Microsoft 365-collaboration
- Tier3
- essentials-compliance
- magic-ai-copilot
search.appverid:
- SPO160
- MET150
description: "Learn about the governance, data lifecycle management, and compliance capabilities for Loop experiences."
---

# Summary of governance, lifecycle, and compliance capabilities for Loop

> [!NOTE]
> The Copilot Pages and Copilot Notebooks content can now be found in a [dedicated article](cpcn-compliance-summary.md).

As a Compliance Manager or IT administrator, it's crucial to stay up-to-date on the latest governance, data lifecycle, and compliance posture for the software solutions being used in your organization. This article details the capabilities available and not available yet for [Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop).

## At a glance

| Capability | Status |
|------------|--------|
| **Admin policies** | ✅ Available - [Cloud Policy + SharePoint PowerShell](loop-admin-configuration.md) |
| **GDPR / EUDB** | ✅ Supported |
| **Conditional Access** | ✅ Supported |
| **Information Barriers** | ◐ OneDrive/SharePoint only (not SharePoint Embedded) |
| **Customer Lockbox** | ✅ Supported |
| **eDiscovery** | ✅ Supported (full-text search in review sets not available) |
| **Legal Hold** | ◐ SharePoint Embedded content is Manual - My workspace container must be added per user |
| **Retention policies** | ✅ Supported |
| **Retention labels** | ◐ Limited manual application |
| **Sensitivity labels** | ✅ Pages, components, and workspaces |
| **DLP** | ✅ Supported with policy tips |
| **Recycle bin** | ✅ Components and pages; ❌ Workspaces |

## SharePoint Embedded

Loop content storage varies based on creation method. For detailed information about storage locations, see [storage](loop-storage.md). Content stored in SharePoint Embedded containers follows the [SharePoint Embedded security and compliance documentation](/sharepoint/dev/embedded/compliance/security-and-compliance).

The sections below outline governance, lifecycle, and compliance capabilities applicable to all Loop storage types. Where capabilities vary by storage location—OneDrive, SharePoint sites, or SharePoint Embedded containers—specific details are provided.

## Foundations

- **Admin policies**: Use [Cloud Policy and SharePoint PowerShell](loop-admin-configuration.md) to control creation of Loop components, pages, and workspaces. When creation is disabled, existing content renders as hyperlinks instead of interactive components.
  - Primary policy controls most apps (excluding Teams); secondary policies control Outlook, Teams, and collaborative meeting notes separately.
- **GDPR**: Data subject requests can be serviced through the [Microsoft Purview portal](/compliance/regulatory/gdpr-data-subject-requests#data-subject-request-admin-tools) and [Purview eDiscovery workflows](/purview/ediscovery).
- **EUDB**: Compliance is supported. See [What is the EU Data Boundary?](/privacy/eudb/eu-data-boundary-learn)

## Data Security, Devices

- **Intune**: [Device Management Support](/mem/intune/remote-actions/device-management) is available for Microsoft 365 app, Teams app, and Loop app on iOS and Android.
- **Conditional Access**: [Supported](/sharepoint/control-access-from-unmanaged-devices).
- **Information Barriers**: [Enforced](/purview/information-barriers-sharepoint) for content in SharePoint sites or OneDrive. See [storage](loop-storage.md#storage) for what's stored where, and [admin policies](loop-admin-configuration.md#storage-based-view-of-the-admin-policy-settings) to configure.

> [!IMPORTANT]
> Information Barriers are **not supported** for content stored in SharePoint Embedded containers (Loop workspaces and My workspace). If your organization requires Information Barriers, consider using [admin policies](loop-admin-configuration.md) to restrict Loop workspace creation.

- **Customer Lockbox**: [Supported](/purview/customer-lockbox-requests).
- **Guest app access**: Available for Loop workspace containers. Enables third-party export/eDiscovery tools, migration tools, and developer APIs. Use PowerShell to [Get](/powershell/module/microsoft.online.sharepoint.powershell/get-spoapplication) and [Set](/powershell/module/microsoft.online.sharepoint.powershell/set-spoapplicationpermission) guest app permissions.

## Data Lifecycle

- **Storage**: Loop content is stored in SharePoint Embedded (My workspace, shared workspaces), SharePoint sites, or OneDrive depending on where it was created. Storage counts against your organization's SharePoint quota. See [Managing SharePoint Embedded containers](cpcn-loop-spe-management.md).
  - **Limitation**: Unlike OneDrive, there's no user workflow for My workspace content after user departure. The container is deleted on the same schedule as OneDrive defaults. See [storage management after user departure](loop-storage.md).
- **Multi-Geo**: [Supported](/microsoft-365/enterprise/microsoft-365-multi-geo).
  - OneDrive/SharePoint content: Follows standard multi-geo capabilities.
  - Workspaces: Created in geo matching user's [preferred data location](/microsoft-365/enterprise/plan-for-multi-geo#best-practices).
  - **Known issue**: Some operations may not work correctly after moving containers across geos. Microsoft is working on a fix.
- **Recycle bin**: Available for deleted components and pages within Loop workspaces, OneDrive, or SharePoint.
  - **Limitation**: No recycle bin for Loop workspaces themselves (Roadmap ID 421615).
- **Version History**: [Export in Purview](/purview/ediscovery-export-search-results#step-1-prepare-search-results-for-export) or via [Graph API](/graph/api/driveitem-get-content-format). SharePoint Embedded content: 50 versions (not configurable). OneDrive/SharePoint content: Standard versioning settings apply.
- **Audit logs**: Available for all events. See [Purview management](cpcn-loop-purview-management.md#searching-the-audit-logs).

## eDiscovery

- **Purview eDiscovery**: [Supported](/purview/ediscovery-premium-get-started) for search/collection, review (Premium license required), and export as HTML (Premium license required) or original format. Download and reupload files to OneDrive to view in native format.
  - **Limitation**: Full-text search within `.loop` files in Purview review sets isn't available.
- **Graph API export**: [Supported](/graph/api/driveitem-get-content-format) for third-party tools. Use PowerShell to [Get](/powershell/module/microsoft.online.sharepoint.powershell/get-spoapplication) and [Set](/powershell/module/microsoft.online.sharepoint.powershell/set-spoapplicationpermission) guest application permissions.
- **Legal Hold**: Supported. Content is stored in the [Preservation Hold Library](/sharepoint/governance/ediscovery-and-in-place-holds-in-sharepoint-server).
  - **Known Issue**: Unlike OneDrive, Loop's My workspace isn't automatically included when a user is placed on Litigation Hold. You must manually add the My workspace container for each user when placing the user on Litigation Hold.

## Microsoft 365 retention and deletion

- **Retention policies**: [Policies](/purview/create-retention-policies?tabs=other-retention) configured for "All SharePoint sites" apply to all `.loop` files. You can also [configure per workspace](cpcn-loop-purview-management.md#retrieving-the-container-url-for-purview). For container-specific configuration, see [Purview management](cpcn-loop-purview-management.md).
- **Retention labels**: [Supported](/purview/retention#retention-labels) for Loop components through [published labels](/purview/create-apply-retention-labels?tabs=spo-onedrive) or [auto-apply](/purview/apply-retention-labels-automatically). Manual application has limitations:
  - Labels can't be viewed or applied directly from a Loop component. Users must [navigate via the Loop app](/purview/create-apply-retention-labels?tabs=loop%2Cdefault-label-for-sharepoint#manually-apply-retention-labels).
  - Record or regulatory record labels can't be manually applied. If content is auto-labeled as a record, locking/unlocking isn't yet available.
  - **Note**: Retention labels apply to files, not containers. Use retention policies for containers like workspaces. See [retention](/purview/retention).

## Information Protection

- **Sensitivity labels**: [Available](/purview/sensitivity-labels-loop) for Loop pages and components. Workspace sensitivity labels are configurable per workspace (at container level) via SharePoint Admin Center and PowerShell. See [configuring sensitivity labels](/sharepoint/dev/embedded/concepts/security-and-compliance#security-features).
  - **Note**: There's no admin setting to configure guest sharing of specific Loop workspaces. Use container sensitivity labeling for per-workspace external sharing configuration.
- **Data Loss Prevention (DLP)**: [Rules enforced](/purview/dlp-learn-about-dlp) with end-user policy tip support.

## Related articles

- [Requirements](loop-requirements.md)
- [Storage](loop-storage.md)
- [Permissions](loop-permission.md)
- [Admin policies](loop-admin-configuration.md)
- [UX examples for admin policy states](loop-ux-examples.md)
- [Managing SharePoint Embedded containers](cpcn-loop-spe-management.md)
- [Purview management](cpcn-loop-purview-management.md)
- [Overview of Loop components in Microsoft 365](loop-components-teams.md)
