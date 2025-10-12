---
title: Manage generative AI apps for your organization
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.reviewer: 
ms.date: 10/10/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
- magic-ai-copilot
description: Learn how to discover, monitor, and manage the generative AI apps your organization uses. 
appliesto:
- ✅ Microsoft 365 Copilot
---

# Manage generative AI apps for your organization

As people embrace and incorporate [generative AI apps](/ai/playbook/technology-guidance/generative-ai/), such as Microsoft 365 Copilot and non-Microsoft AI apps into daily work, it's important for your security team to be able to manage those apps. Discovering, monitoring, and managing AI apps is essential to prevent data leaks, maintain compliance, enforce governance, and uphold trust in enterprise AI adoption.

Using capabilities in Microsoft Entra, [Microsoft Purview](/purview/purview), [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps), and Microsoft Defender for Endpoint, your security team can enable people in your organization to use generative AI apps more securely.

## Quick reference table: AI app risk mitigation and Microsoft solutions

| Risk of unmanaged AI apps | Recommended controls | Microsoft solutions |
|--|--|--|
| Data leakage and intellecutal property (IP) exposure | Discover unscanctioned AI apps <br/><br/>Apply DLP policies | Defender for Cloud Apps <br/><br/> Purview DLP |
| Compliance vioiations | Monitor AI interactions<br/><br/>Log prompts and outputs<br/><br/>Enforce governance | Purview Audit & eDiscovery <br/><br/>Compliance Manager |
| Prompt injection and model abuse | Apply Zero Trust principles<br/><br/>Restrict permissions | Microsoft Entra Conditional Access<br/><br/> Defender for Cloud Apps |
| Shadow AI and blind spots | Continuous discovery<br/><br/>Block risky apps | Defender for Cloud Apps App Governance<br/><br/>Purview DSPM for AI |
| Untracked AI agent identities | Identity lifecycle management<br/><br/>Multifactor authentication (MFA) and Just-in-Time (JIT) access | Microsoft Entra ID Governance<br/><br/>Azure AI Foundry |
| Incident response gaps | Real-time alerts<br/><br/>Anomaly detection | Microsoft Sentinel<br/><br/>Defender for Cloud Apps |


## Before you begin

PREREQS

Defender for Cloud Apps

Purview

Nice to have: Defender for Endpoint

## Discover generative AI apps that are in use in your organization

PROCEDURE

## Set up a policy to create an alert for new generative AI apps

PROCEDURE

## Block specific generative AI apps

PROCEDURE

## See also

- [Tech Community blog: Discover, monitor and protect the use of Generative AI apps](https://techcommunity.microsoft.com/blog/microsoftthreatprotectionblog/discover-monitor-and-protect-the-use-of-generative-ai-apps/3999228)

