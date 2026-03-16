---
title: Secure & Governed Data Foundation for Microsoft 365 Copilot - A deployment blueprint
description: Use this deployment blueprint to help prevent oversharing when using Microsoft 365 Copilot.
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/27/2026
ms.update-cycle: 180-days
ms.reviewer:
audience: Admin
ms.topic: get-started
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
- trust-pod
- M365-sam
- MCAT
ms.custom: [copilot-learning-hub]
customer-intent: As an admin, I want to use a blueprint to help set up a secure and governed foundation for Microsoft 365 Copilot.
appliesto:
- ✅ Microsoft 365 Copilot
---

# Secure & governed data foundation for Microsoft 365 Copilot: A deployment blueprint

Microsoft 365 Copilot can accelerate how people find information, summarize content, and get work done—by grounding responses in the data users already have permission to access. To realize that value confidently, organizations need a foundation that is secure and governed, equipped with robust guardrails, and aligned with AI regulations. Common challenges like content sprawl, stale sites, and overly broad sharing can reduce answer quality and increase the likelihood that Copilot surfaces information more widely than intended. By implementing reliable guardrails and ensuring compliance with regulatory obligations, organizations can further minimize risks and help ensure that Copilot delivers accurate, responsible results within a trusted environment.

This deployment blueprint outlines the essential steps for establishing a secure and governed foundation for Copilot by remediating oversharing, implementing reliable guardrails, and fulfilling AI-related regulatory obligations, delivering a straightforward, approachable path to help every organization get started with confidence.

This blueprint is organized into three pillars:
- Remediate oversharing
- Set up guardrails
- Meet regulations

The blueprint covers the following areas:
- A practical framework to reduce Copilot exposure quickly, then harden your environment with enforceable defaults
- Guidance powered by:
   - Microsoft Purview, which enables secure and governed Copilot deployment by providing tools to prevent data loass, mitigate insider risk, and ensure compliance with organizational and regulatory requirements for both Copilot at runtime and Microsoft 365 data referenced by Copilot
   - SharePoint Advanced Management (SAM), which is included wiht your Microsoft 365 Copilot license. SAM provides capabilities for managing sharing, access, and governance across SharePoint.
- Recommended admin actions to identify high-risk sites and files, apply interim access restrictions if needed, fix access issues, and continuously enforce secure guardrails.
- Identifying and closing gaps in AI regulatory requirements, defining audit and legal requirements, and enhancing data hygiene for sites and files. 

*IMAGE TO BE UPDATED*

:::image type="content" source="media/microsoft-365-copilot-blueprint-oversharing/blueprint-oversharing-copilot.png" alt-text="Diagram that shows oversharing remediation phases for Microsoft 365 Copilot." lightbox="media/microsoft-365-copilot-blueprint-oversharing/blueprint-oversharing-copilot.png":::

## Download the blueprint and documentation

| Deployment model | Description |
|---|---|
| [![Address oversharing concerns in Microsoft 365 Copilot](media/microsoft-365-copilot-blueprint-oversharing/blueprint-oversharing-copilot.png)](https://aka.ms/Copilot/OversharingBlueprintPDF) | Use this blueprint to remediate oversharing, enforce guardrails, and meet AI regulations for a Microsoft 365 Copilot deployment.<br/><br/>**Includes:**<br/>- Blueprint overview and activities: [PDF](https://aka.ms/Copilot/OversharingBlueprintPDF) \| [PowerPoint](https://aka.ms/Copilot/OversharingBlueprintPPT) |

## Related guidance

- [Microsoft Purview blueprint: Secure by default](/purview/deploymentmodels/depmod-securebydefault-intro)
