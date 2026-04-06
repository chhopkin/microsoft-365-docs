---
title: Workflows agent privacy and data subject request (DSR) FAQ
description: Frequently asked questions about Workflows agent's privacy and data subject request (DSR) processes.
author: sbasi19
ms.author: kisubedi
ms.date: 01/23/2026
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.reviewer: v-aangie
ms.update-cycle: 180-days
---

# Workflows agent privacy and data subject request (DSR) FAQ

Workflows agent is a Microsoft 365 Copilot agent that helps users create automation flows using natural language. This FAQ explains how Workflows agent works, how it handles data, and what controls are available to users and administrators.

## What is Workflows agent?

Workflows agent is a Copilot agent that enables users to automate tasks by describing them in natural language. It generates flows using supported Microsoft connectors and displays them directly in the Microsoft 365 Copilot experience.

## How are flows stored, exported, or deleted?

Flows created with Workflows agent are stored in the user's Power Platform environment. These flows are visible within the Workflows agent interface in Microsoft 365 Copilot, but aren't surfaced in Power Automate.

Users can export or delete flows using standard Power Platform tools. Flows are subject to Microsoft’s Data Subject Request (DSR) processes.

# Prerequisites: Identify the Scope
Before performing a DSR, you must identify where the user’s "Workflows" data resides.
•	Locate the Environment: Navigate to the [Power Platform Admin Center (PPAC)](https://admin.powerplatform.microsoft.com/) Inventory.
•	Check Two Locations: Workflows artifacts will typically be in one of two places:
1.	The Default Environment of the tenant.
2.	The user's Personal Development Environment (PDE).
•	Action: Go to Inventory, filter by the user's email, and note the Environment ID where their Workflows agents are listed.
 

Each Workflows agents workflows are backed by specific Dataverse entities. Because these are not surfaced in the standard Power Automate UI, you must use the following methods to locate them:

# Method A: Web-Based Management (UI)
For a manual, UI-based approach, navigate to the environment identified in Step 1 and use the Tables view in Power Apps or the Maker Portal.

In the identified environment, refer to the following Dataverse entities on the environment to perform DSR Export/Delete. 

| Target Data | Dataverse Table |
| :--- | :--- |
| **Process** | Workflows (Category 5: Modern Flow AND ModernFlowType: M365CopilotFlow) |
| **Process** | AI Flows (Category 7: AI Flow) |
| **ConnectionReference** | Connections |
| **AI Model** | AI Prompts - AI Model |
| **AI Configurations** | AI Prompt Prompt Data |
| **WorkflowMetadata** | WorkflowMetadata |
| **FlowRun** | Flow Run (If Flow Run Ingestion is enabled) |
| **AI FlowRun** | Flow Run |
| **Approvals** | Approvals (Subject to a 28-day automatic deletion retention policy) |

# Method B: API-Based Management (Bulk/Automation)
If you are handling multiple requests, use the Environment-scoped APIs.

| API | Notes |
| :--- | :--- |
| [**Get Conversation Transcripts With Environment**](https://learn.microsoft.com/en-us/rest/api/power-platform/workflowsagent/dsr-compliance/get-conversation-transcripts-with-environment) | Get conversation transcripts for DSR export (environment-scoped). |
| [**Get Flow Run Actions With Environment**](https://learn.microsoft.com/en-us/rest/api/power-platform/workflowsagent/dsr-compliance/get-flow-run-actions-with-environment) | Get flow run actions for DSR export (environment-scoped). |
| [**Get Flow Runs (Default/PDE)**](https://learn.microsoft.com/en-us/rest/api/power-platform/workflowsagent/dsr-compliance/get-flow-runs-non-singleton) | Get flow runs for DSR export (environment-scoped). |
| [**Get Run History Data (Default/PDE)**](https://learn.microsoft.com/en-us/rest/api/power-platform/workflowsagent/dsr-compliance/get-run-history-data-non-singleton) | Get run history customer data for DSR export (environment-scoped). |

Api Permissions setup: Please visit [RBAC Permissions](https://learn.microsoft.com/en-us/power-platform/admin/security/role-based-access-control) to learn more about permissions needed for API access.
Specific permissions table for Worflows Agent DSR:

| Role Name | Role ID | Description | Assignable Scope |
| :--- | :--- | :--- | :--- |
| **Workflows Agent Data Subject Rights Environment Reader** | `38a014c1-0485-4e5e-b784-782ea373b34b` | Grants full access to perform read operations for Data Subject Rights requests for Workflows Agent Flows for a given environment. | `/tenants/{0}/environments/{1}` |

Here is the link with the tutorial for customers: [RBAC Tutorial](https://review.learn.microsoft.com/en-us/power-platform/admin/programmability-tutorial-rbac-role-assignment)

**Export**: Admins can export all data pertaining to a user's usage on Workflows agents. Learn more here:
[List flows for a user](/connectors/flowmanagement/#list-flows-as-admin-(v2)), 
[Get flow definition](/connectors/flowmanagement/#get-flow-as-admin) 

**Delete/Reassign**: Admins can delete/reassign Workflows agents created by a user. [Learn More](/power-automate/privacy-dsr-delete#reassign-and-copy-the-users-flows)

Here are some resources about DSR requests:

- [Responding to DSR delete requests for Microsoft Dataverse customer data](/power-platform/admin/dataverse-privacy-dsr-guide)
- [Responding to DSR delete requests to delete Power Apps customer data](/power-platform/admin/powerapps-privacy-delete-dsr)

## Is conversation history stored or exportable?

Yes. Conversations with _Workflows agent_ are retained in the Microsoft 365 conversation history.

Learn more about how Microsoft 365 Copilot handles data in [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md).

## How is Workflows agent managed by administrators?

Administrators can manage Workflows agent in the Microsoft 365 admin center under **Copilot > Agents**. Available controls include:

- Enable or disable the agent
- Assign, block, or remove access
- Control visibility using “Allow users access to agents”

Workflows agent respects tenant-level settings configured in the Microsoft 365 admin center and Power Platform Admin Center (PPAC). These settings determine:

- Whether Workflows agent is enabled
- Whether feedback collection is allowed
- Whether analytics and telemetry are collected
- Which Copilot features are available to users

Learn more about managing Copilot agents and tenant settings in [Manage Copilot Agents](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide&preserve-view=true).

## What connectors are supported?

Workflows agent currently supports the following connectors:

- Recurrence
- Outlook
- Microsoft Teams
- Approvals
- Run a prompt
- SharePoint

Connector availability may vary depending on tenant policies and data loss prevention (DLP) configurations.

## How is user feedback handled and controlled?

Users can submit thumbs-up or thumbs-down ratings and optional comments.

Here are some important points about feedback collection. Feedback data:

- Isn't used to train foundation models
- Isn't linked to individual identities
- Doesn't include content samples
- Can be enabled or disabled by administrators at the tenant level

Feedback collection settings apply consistently across all Workflows agent surfaces. If Workflows agent is embedded in an iframe or accessed through other Microsoft 365 interfaces, feedback controls configured at the tenant level apply to both entry points.

Here's some additional information about feedback collection:

- [Providing feedback about Microsoft Copilot with Microsoft 365 apps](https://support.microsoft.com/topic/providing-feedback-about-microsoft-copilot-with-microsoft-365-apps-c481c26a-e01a-4be3-bdd0-aee0b0b2a423)
- [Manage feedback for Microsoft 365 apps](/microsoft-365/admin/manage/manage-feedback-ms-org?view=o365-worldwide&preserve-view=true)

## Can usage be audited?

Yes. Organizations can use Microsoft 365 audit logs and Power Platform analytics to monitor usage of Workflows agent.

## Related articles

- [Learn about the new Microsoft Purview portal](/purview/purview-portal)
- [Power Platform Admin Center](https://aka.ms/ppac)
