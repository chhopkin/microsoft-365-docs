---
title: Extending Employee Self-Service Copilot Agents
f1.keywords: NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 11/05/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about extending Employee Self-Service Copilot Agents.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Extending Employee Self-Service Copilot Agent

The Employee Self-Service agent allows employees to get their queries answered from admin-configured knowledge sources, HCM and IT systems. Employee Self-Service agent, along with accelerator packages for connecting external systems, unleashes a powerful set of ready-to-use Topics that cover common HR and IT scenarios.

However, every organization has unique processes and policies where each vertical owners may want to include a few other self-serve scenarios as part of Employee Self-Service agent, such as:

- Apply for leave or request for leave balance using Copilot.
- View job details for their direct reports.
- Move or transfer an employee.

Employee Self-Service agent is built with the core principles of extensibility. These principles allow each business vertical owners to enhance the out-of-the-box Topics with their own additional custom Topics. This article explains the steps to extend ESS by explaining how Employee Self-Service agent works from first principles and walking through all the different ways you can build upon and extend Employee Self-Service agent to fit your organization's needs.

Who this is for:

- Business vertical owners such as HR and IT who need to deliver employee services.
- Application integration or service owners who manage the business vertical systems like Workday, SAP SuccessFactors, ServiceNow, and so on.
- Agent makers who configure and customize Employee Self-Service agent.

## Understand Employee Self-Service agent

XXX WE CAN'T JUST CONTINUE TO DEFINE ESS IN EVERY ARTICLE. YES, IT'S NEW TODAY, BUT THAT WON'T BE THE CASE FOREVER.

Employee Self-Service agent is a Copilot Studio custom agent that offers a flexible, extensible starting point for automating business support services.  Understanding Employee Self-Service agent at a fundamental level empowers both business & technology stakeholders to:

- Customize the agent's behavior and responses.
- Integrate with your own systems and data sources.
- Extend Employee Self-Service agent to support new scenarios as your organization evolves.

## Employee Self-Service agent architecture: the building blocks

1. **The Employee Self-Service agent**: At its core, the Employee Self-Service agent is a conversational agent built on Microsoft 365 Copilot and Copilot Studio. It acts as the interface between employees and organization's knowledge, workflows, and systems.
1. **Topic**: Employee Self-Service agent comes with prebuilt "accelerator packages" from Workday, ServiceNow, and SAP SuccessFactors for common HR and IT scenarios (like checking PTO balance or submitting an IT ticket). These topics define how the agent understands and responds to user requests.
1. **Connectors and Actions**: Connectors allow the Employee Self-Service agent to interact with external systems (for example, Workday, ServiceNow, SAP SuccessFactors). Actions inside topics are the building blocks that let the agent retrieve data, trigger workflows, or update records.
1. **Knowledge Sources**: The Employee Self-Service agent can pull information from knowledge sources such as SharePoint, ServiceNow KBs, Workday KBs, internal wikis, or other knowledge bases to answer employee questions. The Employee Self-Service agent is continuously being evolved to keep up at par with the industry requirements and trends.

## Extendable parts of the Employee Self-Service agent

The Employee Self-Service agent is designed for extensibility at every layer:

|Component          |What you can extend or customize                                                                 |
|-------------------|-------------------------------------------------------------------------------------------------|
|Topics             |Add new topics or create templates for repeated scenarios.                                       |
|Connectors         |Integrate with external systems (HR, IT, facilities, and so on) using Power Platform connectors. |
|Knowledge sources  |Add or update SharePoint sites, wikis, or other content repositories.                            |
|Agent response     |Adjust how the agent responds, handles sensitive queries, or routes requests.                    |
|UI/Chat experience |Customize prompts, escalation flows, and disclaimers.                                            |

## How the Employee Self-Service agent works

XXX WHY SO MARKETING? AND WHY IS THIS HERE? WHY NOT THE INTRO OR OVERVIEW TOPICS?

## Ways to customize and extend the Employee Self-Service agent XXX THIS IS AWFUL. APART FROM STEP 1 THAT LINKS OUT TO COGENT INFO, THIS ISN'T TECHNICALLY HELPFUL AT ALL.

### 1. Create custom topics

- Use Copilot Studio to author new topics for scenarios unique to your organization.
- For example: "Request ergonomic equipment" or "Find local office amenities."
- Start with a template or build from scratch, defining trigger phrases and response flows.

Learn more in the [sample scenario Topics library](https://github.com/microsoft/CopilotStudioSamples/tree/main/EmployeeSelfServiceAgent) in GitHub.

### 2. Add or update knowledge sources

- Point the Employee Self-Service agent to new SharePoint sites, policy documents, SNOW KB articles, or FAQs.
- Use filters to ensure employees get role- and region-specific answers.

### 3. Customize agent behavior

- Adjust how the Employee Self-Service agent handles sensitive queries, such as payroll or medical leave.
- Set up escalation paths for complex or confidential requests.

### Test and validate

- Use scenario-based "golden prompts" to ensure your customizations work as intended.
- Validate with pilot users before rolling out broadly.

## Checkpoint

At this point, you should have:

- Identified the scenarios you want to support.
- Access to Copilot Studio and Power Platform admin tools.
- A list of systems and knowledge sources to integrate.

You'll know you're ready to move on when:

- You've created and tested at least one custom topic or connector.
- Employees can access new capabilities in Teams or Copilot Chat.

## Extensibility in Action: Example Use Cases

Here are some example use cases for extending the Employee Self-Service agent that aren't part of the out of box template packages:

- HR: Add a topic for "Requesting a visa letter" that triggers a custom workflow.
- IT: Integrate with your asset management system to automate device requests.
- Facilities: Enable employees to book wellness rooms or report maintenance issues.

## Common Challenges and Troubleshooting

- Custom topic not triggering? Check trigger phrases and test with sample queries.
- Connector errors? Validate authentication and permissions.
- Knowledge not surfacing? Ensure sources are indexed and access is configured.
