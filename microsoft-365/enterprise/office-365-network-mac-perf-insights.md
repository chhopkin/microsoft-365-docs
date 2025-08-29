---
title: "Microsoft 365 Network Insights"
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/24/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.subservice: network
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
- Strat_O365_Enterprise
- must-keep
description: "Microsoft 365 Network Insights"
---

# Microsoft 365 Network Insights

Network insights are actionable issues that might affect user experience, performance or interoperability when using Microsoft 365 apps, we detect insights based on network optics received from Microsoft 365 apps for your tenant users. Insights are available to view only by administrative users in your tenant. Insights can be viewed from [Network Connectivity](https://admin.cloud.microsoft/#/networkperformance) in Microsoft 365 Admin Center. 

The insights are designed to help identify and resolve network infrastructure issues that are managed either by your organization or your network provider. This infrastructure includes the systems your tenant users rely on to connect to Microsoft 365 services from various office locations. Each insight highlights a specific connectivity issue tied to the geographic location from which users are accessing Microsoft 365.

> [!TIP]
> Admins can now view Service health notifications in Microsoft 365 admin center for Network insights detected for their tenant. You may also receive an email if you opted to receive email notifications. The service health notification has a deep link that takes you directly to the detected network insight for your tenant. You receive one notification per insight detected. 

The following are the network insights that might be shown for each office location:

| No. | Network Insight                                                                                             | Description                                                                                                                                                                                                            | Impact                                                                                                                                                                                                             | Protocol  | Scope of impacted services or scenarios                                                | What action should I take?                                                                                                                                                                                                        |
| --- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------- | -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Your connectivity to critical Microsoft 365 domains is failing                                              | We are detecting connectivity (HTTPS) failures to the following domains: `*.cloud.microsoft`, `*.static.microsoft`, `*.usercontent.microsoft`.                                                                         | Some or all users are unable to connect using HTTPS to subdomains or hosts within the specified wildcard domains due to network issues in infrastructure managed by your organization or your network provider.    | HTTPS     | All or any service part of Microsoft 365                                               | Check your network devices or web proxy infrastructure to ensure HTTPS connectivity is allowed to hosts in the wildcard domains `*.cloud.microsoft`, `*.static.microsoft`, `*.usercontent.microsoft` or any of their subdomains.  |
| 2   | WebSocket connection to critical Microsoft 365 domains is failing                                           | We are detecting WebSocket (WSS) connection failures to the domain: `*.cloud.microsoft`, which his cause Copilot to not work correctly for your users.                                                                 | Some or all users are unable to connect using WebSocket to subdomains or hosts within the specified wildcard domain due to network issues in infrastructure managed by your organization or your network provider. | WebSocket | All or any Microsoft 365 Copilot scenario, Real-time collaboration using Office apps.  | Check your network devices or web proxy infrastructure to ensure WebSocket protocol is allowed for connections to hosts in the wildcard domain `*.cloud.microsoft` or its subdomains.                                             |
| 3   | User connections to Microsoft 365 domains are being TLS intercepted and decrypted by a network intermediary | We detected the use of non-Microsoft 365 issued certificates for connections to Microsoft 365 services, indicating decryption and potential alteration of data connections between clients and Microsoft 365 services. | Some or all users maybe experiencing TLS break and inspect for connections to Microsoft 365 domains or hosts due to network configuration in infrastructure managed by your organization or your network provider. | HTTPS     | All or any service part of Microsoft 365                                               | We recommend working with your network team or solution provider to update network configurations and ensure that traffic to Microsoft 365 domains is exempt from TLS interception and decryption at the network layer.           |

## 🌐 FAQ: Microsoft 365 Unified domains and Network Connectivity

### 1. What is the unified domains for Microsoft 365 apps and services?
Microsoft announced the transition to a unified domain—**`cloud.microsoft`**—for Microsoft 365 apps and services over two years ago. This change simplifies domain management and improves connectivity across Microsoft 365.

- Learn more:  
https://learn.microsoft.com/en-us/microsoft-365/enterprise/cloud-microsoft-domain-overview  
https://techcommunity.microsoft.com/t5/microsoft-365-blog/introducing-cloud-microsoft-a-unified-domain-for-microsoft-365/ba-p/3826287

---

### 2. What happens if connections to unified domains are blocked?
Blocking connectivity to unified domains such as:
- `*.cloud.microsoft`
- `*.static.microsoft`
- `*.usercontent.microsoft`

...can impact **any or all Microsoft 365 applications and services**. These domains are essential for proper functionality, including features like Microsoft Copilot.

---

### 3. What does the location “Singapore” mean in the connectivity report?
The location label (e.g., “Singapore”) typically refers to either:
- The **office location** of the user, or
- The **network egress point** (i.e., where traffic exits your network to reach Microsoft services)

This helps identify where connectivity issues are occurring.

---

### 4. Where can I find more details about network connectivity issues?
Visit the **Network Connectivity page in the Microsoft 365 Admin Center**. It provides:
- Egress IP address ranges per office location
- Insights into where connection blocks were detected

---

### 5. What is meant by “egress IP address ranges”?
These are the **public IP addresses** from which Microsoft 365 sees your network traffic. They help you understand:
- How connections are NATed (Network Address Translated)
- The path your traffic takes to reach Microsoft services

---

### 6. What does Microsoft test for in connectivity checks?
Microsoft tests:
- **TCP 443 and HTTPS** connectivity to key domains
- **WebSocket protocol** readiness (required for Microsoft Copilot)

If these tests fail, issues are flagged in the Service Health Dashboard (SHD).

---

### 7. Does Microsoft’s connectivity insight include user or device context?
No. The insights are **network-focused only**. They do not include:
- User identities
- Device details
- Licensing information

---

## Related articles

[Network connectivity in the Microsoft 365 Admin Center](office-365-network-mac-perf-overview.md)

[Microsoft 365 network assessment](office-365-network-mac-perf-score.md)

[Microsoft 365 network connectivity test tool](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location Services](office-365-network-mac-location-services.md)
