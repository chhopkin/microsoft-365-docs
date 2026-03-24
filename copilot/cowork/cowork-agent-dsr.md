---
title: "Data Subject Rights requests for Copilot Cowork agent"
description: "Learn how to respond to Data Subject Rights requests for personal data processed by Copilot Cowork agent in Microsoft 365 Copilot."
ms.date: 03/30/2026
ms.topic: reference
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# Data Subject Rights requests for Copilot Cowork agent

Privacy regulations such as the General Data Protection Regulation (GDPR) and the California Consumer Privacy Act (CCPA) grant individuals—referred to as *data subjects*—specific rights over their personal data. These rights include the ability to discover, access, rectify, restrict, delete, and export personal data that an organization processes.

This article helps you, as a controller, respond to Data Subject Rights (DSR) requests for personal data that Copilot Cowork agent processes within Microsoft 365 Copilot. It covers the types of personal data the agent stores, where that data resides, and the tools available to fulfill each type of request.

> [!NOTE]
> This article applies to personal data processed by Copilot Cowork agent. For broader guidance on Microsoft 365 Copilot privacy and data handling, see [Data, Privacy, and Security for Microsoft 365 Copilot](../microsoft-365-copilot-privacy.md).

## Understand personal data in Copilot Cowork

Copilot Cowork processes and stores several categories of personal data. The following table summarizes each category and where the data resides.

| Data category | Description | Storage location |
|---|---|---|
| Conversation messages | User inputs and agent responses within a Copilot Cowork conversation. | Copilot Cowork service, associated with the user's Microsoft 365 tenant. |
| Output files | Documents, spreadsheets, presentations, and other files created during conversations. | User's OneDrive (in the Cowork folder) and/or SharePoint. |
| Custom skill definitions | User-created `SKILL.md` files that extend agent capabilities. | User's OneDrive in the `/Cowork/.skills/` folder. |
| Scheduled prompt configurations | Prompts the user configures to run on a recurring schedule. | Copilot Cowork service, associated with the user. |
| Feedback data | Thumbs-up/thumbs-down ratings and inline comments that users submit. | Microsoft feedback infrastructure. |
| Usage and diagnostic data | System-generated logs that capture service events and telemetry. | Microsoft internal logging systems. |

> [!IMPORTANT]
> Data in Copilot Cowork is isolated per tenant. There is no cross-tenant access to conversations, files, or configurations.

## Discover

The first step in responding to a DSR request is to find the personal data that is the subject of the request. You can use the following approaches to locate personal data in Copilot Cowork.

- **Conversation history**: Users can view their conversation history in the Copilot Cowork **Tasks** view. Each task displays the full conversation, including user inputs and agent responses.
- **Output files**: Files that Copilot Cowork creates are stored in the user's OneDrive under the **Cowork** folder. Shared files may also reside in SharePoint.
- **Custom skills**: User-created skill definitions are stored as `SKILL.md` files in the user's OneDrive `/Cowork/.skills/` folder.
- **Scheduled prompts**: Scheduled prompt configurations are accessible through the user's task list in Copilot Cowork.
- **eDiscovery and Content Search**: Administrators can use eDiscovery and Content Search in the Microsoft Purview compliance portal to search for personal data across conversations and files associated with a specific user.

> [!NOTE]
> eDiscovery and Content Search capabilities for Copilot Cowork conversation data depend on your organization's Microsoft 365 licensing and compliance configuration.

## Access

After you locate personal data related to a DSR request, you can provide the data subject with a copy. You can use the following methods.

- **User self-service**: Users can view their conversation history in the Copilot Cowork **Tasks** view and download output files directly from the conversation or from OneDrive.
- **Administrator export via eDiscovery**: Administrators can use eDiscovery in the Microsoft Purview compliance portal to search for and export conversation data associated with a specific user.
- **OneDrive and SharePoint export**: Files stored in OneDrive and SharePoint can be accessed and exported through standard Microsoft 365 tools available to the user or administrator.

## Rectify

If a data subject asks you to correct personal data that Copilot Cowork processes, you must determine whether it is appropriate to honor the request. You can use the following approaches.

- **Edit files directly**: Users can edit output files (documents, spreadsheets, presentations) stored in OneDrive or SharePoint using the standard Microsoft 365 applications.
- **Edit custom skills**: Users can modify their custom skill definitions by editing the `SKILL.md` files in OneDrive.
- **Conversation history**: Conversation messages reflect the original interaction as it occurred and can't be modified after the fact. If a conversation contains inaccurate personal data, you can note the correction and, if appropriate, delete the conversation (see [Delete](#delete)).

> [!NOTE]
> System-generated logs reflect factual activities and constitute a historical record of events within the service. These logs can't be rectified.

## Restrict

You can restrict the processing of personal data in Copilot Cowork through the following methods.

- **Disable access for specific users**: Administrators can disable Copilot Cowork access for specific users through the Microsoft 365 admin center under **Copilot** > **Agents**.
- **Remove scheduled prompts**: Users can delete their scheduled prompts to stop recurring processing of personal data.
- **Conditional Access policies**: Administrators can use Conditional Access policies to restrict access to Copilot Cowork based on conditions such as user location, device compliance, or risk level.

## Delete

You can remove personal data from Copilot Cowork through the following methods.

### Conversations

Users can delete individual conversations from the Copilot Cowork **Tasks** view. Deleting a conversation removes the user inputs and agent responses associated with that task.

### Output files

Files stored in OneDrive and SharePoint can be deleted by the user or by an administrator:

- Users can delete files from the **Cowork** folder in their OneDrive or from the relevant SharePoint location.
- Administrators can delete files on behalf of a user through the Microsoft 365 admin center or SharePoint admin center.

### Custom skills

Users can delete custom skill definitions by removing the `SKILL.md` files from the `/Cowork/.skills/` folder in their OneDrive.

### Scheduled prompts

Users can delete scheduled prompts from their task list in Copilot Cowork.

### User data removal

Administrators can use the Microsoft 365 admin center to manage and delete user accounts and associated data in accordance with your organization's data retention policies.

### System-generated logs

System-generated logs are retained and deleted per Microsoft 365 data retention policies. These logs are automatically removed according to the applicable retention schedule and don't require manual deletion.

> [!NOTE]
> Removing personal data includes removing all personal data and system-generated logs, except audit log information that is required for regulatory compliance.

## Export (Portability)

Data portability is the right of a data subject to request a copy of their personal data in a structured, commonly used format. You can use the following methods to export personal data from Copilot Cowork.

- **Download output files**: Users can download files created during conversations directly from the conversation view or from their OneDrive **Cowork** folder.
- **Export conversation data**: Administrators can use eDiscovery in the Microsoft Purview compliance portal to search for and export conversation data in standard formats.
- **Export OneDrive and SharePoint files**: Files stored in OneDrive and SharePoint can be exported through standard Microsoft 365 tools.
- **Copy custom skills**: Custom skill definitions are Markdown files (`SKILL.md`) stored in the user's OneDrive and can be copied or downloaded directly.

## Related content

- [Copilot Cowork overview](index.md)
- [Responsible AI FAQ for Copilot Cowork agent](../responsible-ai/cowork-agent-responsible-ai-faq.md)
- [Microsoft 365 Copilot privacy](../microsoft-365-copilot-privacy.md)
