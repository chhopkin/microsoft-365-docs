---
title: Security for Microsoft 365 Copilot
description: Learn how Microsoft secures Microsoft 365 Copilot and how Copilot inherits Microsoft 365 security, compliance, and privacy protections.
ms.service: copilot-m365
ms.topic: conceptual
ms.date: 03/02/2026
---

# Security for Microsoft 365 Copilot

Security is foundational to Microsoft's approach to Microsoft 365 Copilot. This article outlines Microsoft's approach to securing Microsoft 365 Copilot and provides guidance you can use to strengthen your AI security posture. [1](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-ai-security)

> [!NOTE]
> This article describes Microsoft's security approach for Microsoft 365 Copilot. It does not provide deployment or data‑readiness steps.
>
> For rollout planning and readiness guidance, see **Prepare and deploy Microsoft 365 Copilot in E3 and E5 environments** (your consolidated deployment article).
>
> For deep technical details about data flow, protections, and auditing, see:
> - [Microsoft 365 Copilot data protection architecture](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing) [2](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing)
> - [How does Microsoft 365 Copilot work?](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture) [3](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture)

## Microsoft's defense‑in‑depth approach

Microsoft applies a multi‑layered, defense‑in‑depth strategy to secure Microsoft 365 Copilot at every level, grounded in enterprise security, privacy, and compliance standards. [1](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-ai-security)

## Identity and access protection

Microsoft 365 Copilot is built on Microsoft 365 identity and access controls. To apply a structured approach to identity and access protections for Copilot, use Zero Trust guidance:

- [Apply principles of Zero Trust to Microsoft 365 Copilot](https://learn.microsoft.com/en-us/security/zero-trust/copilots/zero-trust-microsoft-365-copilot) [4](https://learn.microsoft.com/en-us/security/zero-trust/copilots/zero-trust-microsoft-365-copilot)

## Data protection and compliance

Microsoft 365 Copilot honors your security and data protection controls, and your organization can use Microsoft 365 capabilities to protect data Copilot references and creates. [2](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing)[5](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-minimum-requirements-data-compliance)

### Enterprise data protection

Enterprise data protection (EDP) describes controls and commitments that apply to customer data for Microsoft 365 Copilot and Microsoft 365 Copilot Chat under Microsoft Product Terms and the Data Protection Addendum. For details, see:

- [Enterprise data protection in Microsoft 365 Copilot and Microsoft 365 Copilot Chat](https://learn.microsoft.com/en-us/copilot/microsoft-365/enterprise-data-protection) [6](https://learn.microsoft.com/en-us/copilot/microsoft-365/enterprise-data-protection)
- [Data, Privacy, and Security for Microsoft 365 Copilot](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-privacy) [7](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-privacy)

### Microsoft Purview protections

Microsoft Purview provides data security and compliance capabilities that help you monitor and manage AI interactions and apply data protection controls across Microsoft 365.

- [Use Microsoft Purview to manage data security & compliance for Microsoft 365 Copilot & Microsoft 365 Copilot Chat](https://learn.microsoft.com/en-us/purview/ai-m365-copilot) [8](https://learn.microsoft.com/en-us/purview/ai-m365-copilot)
- [Considerations for protecting and managing Microsoft 365 Copilot interactions with Microsoft Purview](https://learn.microsoft.com/en-us/purview/ai-m365-copilot-considerations) [9](https://learn.microsoft.com/en-us/purview/ai-m365-copilot-considerations)

### Auditing and investigation

You can use Microsoft Purview auditing to investigate activity related to Copilot and AI applications. For details on audit records and audit‑related concepts, see:

- [Audit logs for Copilot and AI applications](https://learn.microsoft.com/en-us/purview/audit-copilot) [10](https://learn.microsoft.com/en-us/purview/audit-copilot)
- [Microsoft 365 Copilot data protection architecture](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing) [2](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing)

## Threat protection and monitoring

To help monitor usage and adoption signals associated with Microsoft 365 Copilot, use Microsoft 365 Copilot reporting options for admins:

- [Microsoft 365 Copilot reports for IT admins](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-reports-for-admins) [11](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-reports-for-admins)

For a broader governance framework across Copilot and agents, see:

- [Copilot Control System security and governance](https://learn.microsoft.com/en-us/copilot/microsoft-365/copilot-control-system/security-governance) [12](https://learn.microsoft.com/en-us/copilot/microsoft-365/copilot-control-system/security-governance)

## Preventing oversharing

Microsoft 365 Copilot works within existing permissions and access controls. Overshared or poorly governed content can affect Copilot results and increase risk.

For a prescriptive, phased approach to reducing oversharing risk, see:

- [Microsoft 365 Copilot blueprint for oversharing](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-blueprint-oversharing) [13](https://learn.microsoft.com/en-us/microsoftsearch/github-cloud-issues-deployment)

## Related guidance

Use these articles for deeper coverage of related topics:

- **Deployment and readiness:** Minimum prerequisites and planning resources  
  - [Minimum requirements to deploy Microsoft 365 Copilot in your organization](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-minimum-requirements) [14](https://learn.microsoft.com/en-us/microsoft-365-copilot/extensibility/declarative-agent-tool-comparison)  
  - [License options for Microsoft 365 Copilot](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-licensing) [7](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-privacy)  

- **Architecture and data handling:**  
  - [How does Microsoft 365 Copilot work?](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture) [3](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture)  
  - [Microsoft 365 Copilot data protection architecture](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing) [2](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing)  

- **Oversharing remediation:**  
  - [Microsoft 365 Copilot blueprint for oversharing](https://learn.microsoft.com/en-us/copilot/microsoft-365/microsoft-365-copilot-blueprint-oversharing) [13](https://learn.microsoft.com/en-us/microsoftsearch/github-cloud-issues-deployment)  