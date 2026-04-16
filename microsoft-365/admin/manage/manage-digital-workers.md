---
title: Manage digital workers in Microsoft 365 admin center
description: Manage digital workers in Microsoft 365 admin center.
#customer intent: As an IT admin, I want to manage digital workers so that I can control their availability and functionality within my organization.
f1.keywords:
- NOCSH
ms.author: erikre
author: ErikRe
manager: scotv
ms.date: 04/14/2026
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

# Manage digital workers in Microsoft 365 admin center

AI Teammates are Digital Workers. Digital Workers are AI-powered agents built on AI Teammate templates that your organization can deploy to automate business processes. As a **Global Administrator** or an **AI Administrator**, you can *hire* Digital Workers on behalf of a Hiring Manager directly from the Microsoft 365 Admin Center. Hiring Managers are business owners of the Digital Worker. This process gives your organization full governance and control over agent deployment.

AI Teammate agent is a prebuilt AI agent template published in your tenant. The AI Teammate agent must be activated before any instances can be created from them. Instances are created by the members of your organization. A deployed instance of an AI Teammate agent can be assigned to a specific Hiring Manager and configured for your organization's needs. When a member of your organization creates an instance of an agent, they create the instance from an activated AI Teammate. The owner is the person in your organization responsible for the instance. They appear as its manager in the directory and interact with the instance via Microsoft Teams.

Agent 365 provisions the instance identity, validates licenses, enforces governance policies, and maintains a complete audit log of all actions.

## Roles & Responsibilities

| Role  | Responsibilities in the Hire Flow  |
|---|---|
| Global Administrator / AI Administrator  | Activates AI Teammate agents, initiates instances hiring, assigns licenses and policies, and governs the deployment on behalf of the organization.  |
| Hiring Manager  | The designated business owner of instance. Appears as the Ditial Workers's manager in Microsoft Entra ID. The administrator hires the instance on Hiring Manager's behalf.  |

For more information about agent management roles, see [Agent management roles and permissions](agent-365-overview.md#agent-management-roles-and-permissions).

## Prerequisites

Ensure the following prerequisites are in place before starting the instance creation flow:

- You're signed in to the Microsoft 365 Admin Center as a Global Administrator or AI Administrator.
- The AI Teammate agent you want to deploy has already been activated (published) in your tenant.
- You have identified the Hiring Manager as the person who will be the business owner of this instance.
- Sufficient licenses are available to assign to the new instance.
- You have confirmed the Hiring Manager has an active user account in Microsoft Entra ID.

> [!NOTE]
> AI teammate activation and instance creation are separate, decoupled actions. Your organization can activate an AI Teammate agent when it's ready technically, then create instance from it at any time when the business is ready. This guide covers the hiring step only.

## Create a Digital Worker instance

You can create a Digital Worker instance from an activated AI Teammate agent in the Microsoft 365 Admin Center.

The following the steps show you how to hire an instance from an activated AI Teammate agent.
 
### Step 1: Navigate to the Agent Registry

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. In the left navigation pane, select **Agents** > **All Agents** > **Registry**.
1. Select the **AI teammate** filter within the Agent Registry. Here you'll see all AI teammate Agents that have been activated in your tenant.
1. Select an agent with the **AI teammate** tag to open the Agent Details flyout panel.
   An **AI teammate** agent with the **Published status** of **Published** or **Ready for dev** are eligible for instance creation.

### Step 2: Review AI teammate Agent Details

The Agent Details panel provides a full overview of the agent, including its description, capabilities, supported scenarios, availability settings, data connections, and security configuration. Review these details to confirm this is the correct **AI teammate** agent for your intended use case.

The panel includes several tabs you may wish to review before *hiring*. For more information about agent details, see [Sections provided within agent details](agent-details.md#sections-provided-within-agent-details).

### Step 3: Initiate the Hire Flow

From the Agent Details pane, select **Create instance** to launch the **Hire Wizard**, a guided multi-step experience that takes you through all required configurations before the **Instance** is provisioned.

## The Hire Wizard

The Hire Wizard guides you through four stages to configure and provision the agent **Instance**. 

### Step 1: Select a Hiring Manager

1. Search for and select the person who will be the business owner of this Instance.

   The Hiring Manager appears as DW’s manager in Microsoft Entra ID and will interact with the agent via Microsoft Teams. Only users with valid accounts in your directory can be selected. You can perform this action on behalf of the Hiring Manager.

### Step 2: Confirm license validation

1. Confirm that the requiredlicense is avable to provision the agent **Instance**.

   The system automatically checks whether the required licenses are available to provision this Instance. If a valid license is found, you can proceed. If licenses are insufficient, you'll see a warning and must resolve the licensing gap before continuing. This step ensures compliance with your organization's subscription and governance policies.

### Step 3: Instance Customization

1. Configure the Instance identity and behavior for this specific instance. 

   This may include the DW's display name, organizational placement, and any instance-specific settings supported by the AI teammate. These settings determine how the Instance appears to the owner and their team.

### Step 4: Review & Confirm

1. Review a complete summary of all configuration choices before the agent **Instance** is created. 

   This includes the selected Hiring Manager, license assignment, customization settings, and access scope. Once you confirm, the system provisions the Instance by creating its identity in Entra ID, applying the manager attribute, and making it available to the Hiring Manager in Teams. 

### What Happens After the Instance is Created?

Once you confirm in the **Hire Wizard**, the system performs the following actions automatically:

- An Instance identity is provisioned in Microsoft Entra ID, with the selected Hiring Manager set as the directory manager. 
- The required license is assigned to the instance. 
- The Instance is placed within the organizational structure based on the Hiring Manager's position. 
- The Hiring Manager can access and interact with their Instance via Microsoft Teams. 
- All provisioning actions are recorded in the audit log for compliance and traceability. 

After the you complete the hire flow, the **Hiring Manager(()) will find their new Instance available in Microsoft Teams. From there, they can begin working with the agent, delegating tasks, and managing its activity from Microsoft Teams. 

## Governance, Compliance, and Auditing

All instance deployments through the Microsoft 365 Admin Center are governed by Microsoft's enterprise compliance framework. Key governance controls include: 

- License enforcement: Instance can't be provisioned without a valid, available license. 
- Permission scoping: You control which **Hiring Managers** can be assigned and which data sources the agent can access. 
- Audit logging: Every action in the hire flow. This includes who initiated it, when it was configured, and what was configured. This is captured in the Microsoft 365 audit log. 
- Entra ID integration: All Instances are first-class directory objects, subject to the same identity governance policies as human users. 
- Decoupled activation and hiring: You can activate AI teammates independently of hiring, enabling staged rollouts and business-readiness gating.