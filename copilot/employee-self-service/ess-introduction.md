---
title: An introduction to Employee Self-Service
f1.keywords: NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 10/29/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn what Employee Self-Service Agent is, what the HR and IT templates are, and why your organization should use them.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Employee Self-Service

The Employee Self-Service (ESS) Agent is designed as a unified, customer-facing, AI-powered interface for handling employee requests and automating routine tasks within enterprise environments. Built on Copilot Studio, ESS Agent is intended to be customized by you. Once it's customized for your organization's needs, the ESS Agent streamlines access to HR, IT, and operational systems, reducing manual intervention and improving process efficiency.

## Technical Architecture

ESS Agent operates as a custom agent within **Copilot Studio**, leveraging **Microsoft's AI infrastructure** and **Power Platform**. The agent is constructed on a modular architecture, enabling integration with enterprise data sources using RESTful APIs, connectors, and secure authentication mechanisms (for example, OAuth 2.0, Azure AD). The solution supports multi-tenant deployments and is adaptable to on-premises, hybrid, or fully cloud-based environments, depending on organizational requirements.

## Integration Capabilities

Integration with existing enterprise systems is achieved through a library of pre-built and custom connectors available in **Copilot Studio** and **Power Platform**. These connectors facilitate data exchange with:

- HRIS
- ITSM
- Identity management
- Knowledge base platforms

The ESS Agent supports:

- Webhook-based event handling
- API orchestration
- Can be extended to interface with legacy systems through middleware or custom connectors

Data security and compliance are enforced through:

- Role-based access control
- Encrypted data transmission

## Core features

- **End User Capabilities**: The ESS Agent enables users to execute tasks such as querying HR policies, initiating IT support tickets, and updating personal information through conversational interfaces. All interactions are logged for auditability.
  - **ESS templates are separate to focus on domains - HR and IT**. Each template offers slightly different functionality to focus on the core jobs to be done of the domain and can be infinitely customized and extended.
    - **HR template**: Empowers employees to self-serve HR needs by delivering clear, policy-based answers and guidance. Core features include easy navigation of benefits, policy lookups, and access to organizational resources. The agent maintains an empathetic, professional tone and enforces boundaries by escalating complex or sensitive requests (such as legal or personnel decisions) to HR specialists.
    - **IT template**: Enables employees to resolve IT issues efficiently through step-by-step troubleshooting and automated support flows. Key features include guided device setup, secure account management, and instant access to IT resources. The agent prioritizes clarity and patience, automatically escalates time-sensitive or security-related concerns, and ensures safe practices to protect data and systems.
- **Handoff Mechanism**: The agent includes a configurable handoff feature, allowing seamless escalation to specialized first-party agents or human operators within predefined workflows. This is implemented using session context management and secure credential delegation.
- **Telemetry and Insights**: Integrated telemetry provides granular analytics on agent interactions, task completion rates, and user satisfaction. Data is available through Power Platform dashboards and can be exported for further analysis.

## Customization and scaleability

Copilot Studio and Power Platform provide extensive customization options, including low-code and pro-code development environments. Organizations can modify agent behavior, extend dialog flows, and integrate additional data sources using Power Automate, custom APIs, and Azure Logic Apps. The platform supports scaling across regions and business units, with centralized management and version control for agent configurations. 

Each template comes with default content and accelerators to get you started like:

- Agent name, logo, and description.
- Instructions that help shape agent personality and behaviors.
- Topics that help you manage specific kinds of conversations and requests.
- Connectors to other services like ServiceNow and Workday.

## Implementation considerations

Consider which ESS template is right for your organization to start with – HR or IT. Both ESS templates can be deployed into a single ESS agent experience. Learn more about how to get started customizing ESS where you can review common roles and responsibilities, basic building blocks of ESS, and more.

- **Deployment**: ESS Agent can be provisioned in sandbox or production environments through the Power Platform Admin Center. Deployment pipelines support continuous integration and delivery, with environment isolation for testing and validation.
- **Configuration**: Initial setup involves defining integration endpoints, mapping user roles, and configuring dialog flows. Templates and accelerators are available to expedite common scenarios.
- **Security**: The solution adheres to enterprise-grade security standards, including identity federation, least-privilege access, and encrypted storage. Compliance with regulatory frameworks (for example., GDPR, HIPAA) is supported through built-in auditing and data retention policies.

By consolidating employee self-service tasks within a secure, extensible, and scalable architecture, the ESS Agent and Copilot Studio deliver operational efficiencies and integration flexibility tailored for enterprise IT environments.
