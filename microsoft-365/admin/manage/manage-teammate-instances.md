---
title: Manage AI teammate instances in Microsoft 365 admin center
description: Manage AI teammate instances in Microsoft 365 admin center.
#customer intent: As an IT admin, I want to manage AI teammate instances so that I can control their availability and functionality within my organization.
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/17/2026
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.subservice: agent-management
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
- operations-pod
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
---

# Manage AI teammate instances in Microsoft 365 admin center

> [!IMPORTANT]
>
> You need to be part of the [Frontier preview program](https://adoption.microsoft.com/copilot/frontier-program/) to get **early access** to this feature. Frontier connects you directly with Microsoft's latest AI innovations. Frontier previews are subject to the existing preview terms of your customer agreements. As these features are still in development, their availability and capabilities might change over time.

AI teammate instances are AI-powered agents built on AI teammate templates that your organization can deploy to automate business processes. As a **Global Administrator**, you can create Instances  on behalf of an owner  directly from the Microsoft 365 Admin Center.  This process gives your organization full governance and control over agent deployment.

AI teammate agent is a prebuilt AI agent template published in your tenant. The AI teammate agent must be activated before any instances can be created from them. Instances are created by the members of your organization. A deployed instance of an AI Teammate can be assigned to a specific owner and configured for their needs. When a member of your organization creates an instance of an agent, they create the instance from an activated AI Teammate. The owner is the person in your organization responsible for instance. They appear as the instance's manager in the directory and interact with the instance via Microsoft Teams and other office productivity surfaces.

Agent 365 provisions the instance with identity, validates licenses, enforces governance policies, and maintains a complete audit log of all actions.

## Roles & Responsibilities

| Role  | Responsibilities in the Instance creation flow  |
|---|---|
| Global Administrator | Activates AI teammate agents, initiates instance creation, assigns licenses and policies, and governs the deployment on behalf of the organization.  |
| Owner | The designated business owner of instance. Appears as the instance (agent) manager in Microsoft Entra ID. |

For more information about agent management roles, see [Agent management roles and permissions](agent-365-overview.md#agent-management-roles-and-permissions).

## Prerequisites

Ensure the following prerequisites are in place before starting the AI teammate instance creation flow:
- You're signed in to the Microsoft 365 Admin Center as a Global Administrator or AI Administrator.
- The AI teammate agent you want to create an instance from has already been activated  in your tenant.
- You have identified the owner on whose behalf you're going to create the instance. 
- Sufficient licenses are available to assign to the new instance.
- You haveonfirmed that the owner has an active user account in Microsoft Entra ID.

> [!NOTE]
> AI teammate activation and instance creation are separate, decoupled actions. Your organization can activate an AI teammate agent when it's ready technically, then create instances from it at any time when the business is ready. This guide covers the instance creation  step only.

## Create an instance

You can create an instance from an activated AI Teammate agent in the Microsoft 365 Admin Center.

The following steps show you how to create an instance from an activated AI teammate agent.
 
### Step 1: Navigate to the Agent Registry

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents** > **Registry**.
1. Select the **AI teammate** filter within the Agent Registry. Here you'll see all AI teammate agents that have been activated in your tenant.
1. Select an agent with the **AI teammate** tag to open the Agent Details flyout panel.
   An **AI teammate** agent with the **Published status** of **Available** are eligible for instance creation.

### Step 2: Review AI teammate Agent Details

The Agent Details pane provides a full overview of the agent, including its description, capabilities, supported scenarios, availability settings, data connections, and security configuration.

1. Review these details to confirm that this is the correct **AI teammate** agent for your intended use case.

The panel includes several tabs you can review before creating an instance. For more information about agent details, see [Tabs provided within agent details](agent-details.md#tabs-provided-within-agent-details).

### Step 3: Initiate the creation flow

1. From the Agent Details pane, select **Create instance** to launch the **Instance Creation Wizard**, a guided multi-step experience that takes you through all required configurations before the **Instance** is provisioned.

## The Instance Creation Wizard

The **Instance Creation Wizard** guides you through four stages to configure and provision the agent **Instance**. 

### Step 1: Select an Owner

1. Search for and select the person who will be the business owner of this Instance.

   The owner appears as an AI teammate’s instance owner in Microsoft Entra ID and will onboard the agent via Microsoft Teams. Only users with valid accounts in your directory can be selected. 

### Step 2: Confirm license validation

1. Confirm that the required license is available to provision the agent **Instance**.

   The system automatically checks whether the required licenses are available to provision this Instance. If a valid license is found, you can proceed. If licenses are insufficient, you'll see a warning and must resolve the licensing gap before continuing. This step ensures compliance with your organization's subscription and governance policies.

### Step 3: Instance Customization

1. Configure the Instance of identity and behavior for this specific instance.

   This may include the instance display name, organizational placement, and any instance-specific settings supported by the AI teammate. These settings determine how the Instance appears to the owner and their team.

### Step 4: Review & Confirm

1. Review a complete summary of all configuration choices before the agent **Instance** is created. 

   This includes the owner license assignment, customization settings, and access scope. Once you confirm, the system provisions the Instance by creating its identity in Entra ID.

### What Happens After the Instance is Created?

Once you confirm the configuration summary in the **Instance Creation Wizard**, the system performs the following actions automatically:

- An Instance identity is provisioned in Microsoft Entra ID, with the selected owner set as the directory manager.
- The required license is assigned to the instance.
- The Instance is placed within the organizational structure based on the instance owner position, hierarchically under the owner in the org structure.
- The owner can access and interact with their Instance via Microsoft Teams and other productivity surfaces like Word, Excel, PowerPoint, and Outlook.
- All provisioning actions are recorded in the audit log for compliance and traceability. The owner can also see their interactions and the agent activities on Teams and in Microsoft 365.

After you have completed the instance creation flow, the owner will find their new Instance available in Microsoft Teams. From there, they can begin working with the agent, delegating tasks, and managing its activity.

## Governance, Compliance, and Auditing

All instance deployments through the Microsoft 365 Admin Center are governed by Microsoft's enterprise compliance framework. Key governance controls include:

- **License enforcement**: Instance can't be provisioned without a valid, available license.
- **Permission scoping**: You control which owner can be assigned an instance and which data sources the agent can access.
- **Audit logging**: Every action in the instance creation flow. This includes who initiated it, when it was configured, and what was configured. This is captured in the Microsoft 365 audit log.
- **Entra ID integration**: All Instances are first-class directory objects, subject to the same identity governance policies as human users.
- **Decoupled activation and instance creation**: You can activate AI teammates independently and post successful activation you can create instances, enabling staged rollouts and business-readiness gating.
