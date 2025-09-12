---
title: Requirements and considerations for Microsoft 365 Copilot Chat admins
f1.keywords:
- NOCSH
ms.author: efrene 
author: efrene
manager: scotv
ms.date: 09/15/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- scotvorg
- m365copilot
- magic-ai-copilot
- operations-pod
description: Microsoft 365 admins can learn about the requirements and considerations for Microsoft 365 Copilot Chat. 
ms.custom: [copilot-learning-hub]
appliesto:
- ✅ Microsoft 365 Copilot
---

# Requirements and considerations for Microsoft 365 Copilot Chat admins

[Microsoft 365 Copilot Chat](https://learn.microsoft.com/copilot/overview) is an AI chat tool that is included in your Microsoft 365 subscription and is integrated into Microsoft 365 apps such as Word, Excel, Outlook, and Teams. It uses the latest AI models and data from the web to answer your questions, generate content and ideas, and find information. Since it is included in your Microsoft 365 subscription, it is the entry point into the Microsoft 365 Copilot experience.

This document outlines the minimum technical and licensing requirements for using Microsoft 365 Copilot Chat in your organization. It additionally includes considerations admins need to be aware of, such as security, management, and resoures to help train your users.

For information on minimum requirements for the Microsoft 365 Copilot add-on license, see Microsoft 365 Copilot min requirements.

## Licensing requirements
Copilot Chat is available at no additional cost for Microsoft Entra account users with one of the following licenses:
- Microsoft 365 A1/A3/A5 (including MA3/MA5 for students, MA3/MA5 for faculty, and MA3/MA5 student-use benefit)
- Microsoft 365 Business Basic/Business Standard/Business Premium
- Microsoft 365 E3/E5
- Microsoft 365 F1/F3
- Microsoft Teams/Teams Enterprise/Teams Essentials/Teams Rooms
- Office 365 A1/A1 Plus/A3/A5
- Office 365 E1/E1 Plus/E3/E5
- Office 365 F3
- US government GCC M and DoD customers with one of the following licenses:
    - Microsoft 365 F1, F3, G3, or G5
    - Office 365 F1, F3, G3, or G5

For more detailed information about licenses that include Copilot Chat, see [Microsoft 365 Copilot Chat eligibility](https://learn.microsoft.com/copilot/manage#microsoft-365--chat-eligibility).

## Network requirements
Microsoft 365 Copilot enables AI scenarios that access the web, so it may need to connect to specific network endpoints (domains). See the [full documentation of network requirements for Microsoft 365 Copilot](https://learn.microsoft.com/copilot/microsoft-365/microsoft-365-copilot-requirements#network-requirements), which provides a complete list of domains and WebSockets (WSS) that an organization's network shouldn't block.  

### Operating system requirements
- Windows 11
- Windows 10 with 
- macOS 14.0 (Sonoma) or later 

### Mobile device requirements 
- iPhone: iOS 16.0 or later 
- iPad: iPadOS 16.0 or later 
- Android: Android 8.0 (API level 26) or higher.

### Browser requirements 
Any modern browser with third-party cookies enabled for online apps. Recommended browsers are:
- Microsoft Edge (recommended for best compatibility and performance) 
- Google Chrome 
- Mozilla Firefox 
- Apple Safari 

For more information about recommended browsers, see [Which browsers work with Microsoft 365 for the web and Microsoft 365 Add-ins](https://support.microsoft.com/office/which-browsers-work-with-microsoft-365-for-the-web-and-microsoft-365-add-ins-ad1303e0-a318-47aa-b409-d3a5eb44e452).


## How do user access Copilot Chat

Microsoft 365 users can access Copilot Chat from:

- Web: [m365copilot.com](https://m365copilot.com/)
  - Users with Copilot Chat pinned in the Microsoft 365 Copilot app are redirected to m365.cloud.microsoft/chat. If not, they're redirected to copilot.cloud.microsoft. Get more details on how to pin Copilot Chat.
- App: Microsoft 365 Copilot app (formerly the Microsoft 365 app), Teams, and Outlook
  - Available for web, desktop, iOS, and Android
  - To access Copilot Chat in the Microsoft 365 Copilot app, Teams, and Outlook, ensure that it's pinned to the navigation bar. Get more details on [how to pin Copilot Chat](https://learn.microsoft.com/copilot/microsoft-365/pin-copilot).
- Browser: Copilot in Microsoft Edge 
  - Users can access Copilot Chat through the Copilot icon in the Edge browser UI when they're signed in with their Entra account.
  - Users can [modify this permission](https://learn.microsoft.com/copilot/manage#manage--chat-in-edge) by going to **Microsoft Edge > Settings > Sidebar > Copilot**, and then turning on or off the **Allow Microsoft to access page content** toggle. 
- Word, Excel, and PowerPoint
  - In Word, Excel, and PowerPoint, Copilot Chat is automatically pinned in the toolbar.

## Security and Trust

Security and privacy for organizational data is always a top-of-mind concern for our customers. Uncertainty about how Copilot Chat uses their data may be a reason that some customers are hesitant to use it.

Admins do not need to do any additional configuration in regards to security when using Copilot Chat.  But an understanding of what the following might be helpful for them to know.

- **Enterprise Data Protection (EDP)** - Microsoft 365 Copilot Chat is protected by Enterprise Data Protection (EDP). With EDP, [prompts and responses are protected](https://learn.microsoft.com/copilot/microsoft-365/enterprise-data-protection#enterprise-data-protection-for-prompts-and-responses) by the same contractual terms and commitments widely trusted by our customers for their emails in Exchange and files in SharePoint.
- **Responses grounded in web data**- Copilot Chat is a generative AI service grounded in data from the public web in the Bing search index only. Unlike Microsoft 365 Copilot, Copilot Chat cannot invoke organizational content like files, emails, or chats when interacting in Copilot Chat.
- **Users can choose to provide organizational data** - Copilot Chat users can provide organizational content as part of their prompt, manually uploading a file directly, or use an agent that is given access to organizational content. Learn more about [organizational data and Copilot Chat](https://learn.microsoft.com/copilot/privacy-and-protections#organizational-data).
- **European Union Data Boundary (EUDB)** - Microsoft 365 Copilot Chat calls to the LLM are routed to the closest data centers in the region, but can also call into other regions where greater capacity is available when utilization is especially high. For European Union (EU) users, Copilot Chat has additional safeguards to comply with the EU Data Boundary. EU traffic stays within the [EU Data Boundary](https://learn.microsoft.com/privacy/eudb/eu-data-boundary-learn), while worldwide traffic can be sent to the EU and other countries or regions for LLM processing.

## Agents in Copilot Chat

An [agent in Copilot Chat](https://learn.microsoft.com/copilot/agents) is an AI assistant that can perform tasks, automate workflows, or operate independently to help you get work done. Agents vary in complexity — from simple helpers that retrieve information to advanced ones that act on your behalf.

Agents you create in Copilot Chat are billed based on metered consumption.  

For more detailed information, see “Deploy Microsoft 365 Copilot Agents”.  

## Train your users
Copilot Chat is available to users in many of the key Microsoft 365 apps in which they do their work. Admins can help them to understand how to use Copilot Chat to assist them with work tasks by pointing them to the following resources:
- [Microsoft 365 Copilot Chat, your AI assistant for work](https://support.microsoft.com/copilot-microsoft365-chat) - Guidance on how to get started, use different prompts, and understand the differences between Copilot Chat and other Copilot offerings.
- [Microsoft Copilot Chat video tutorial](https://support.microsoft.com/topic/microsoft-365-copilot-chat-video-tutorial-e54fb679-9554-435a-8418-d0e0ce2646c6) – Short, easy-to-understand videos on getting started and tasks you can do with Copilot Chat.
- [Copilot Prompt Gallery](https://copilot.cloud.microsoft/prompts?products%2Fname=CWC&createdBy=CreatedByAll) – Example prompts for your user to help them do their work (for example, ”How can I more concisely describe change management?”). 
- [Copilot Chat Success Kit](https://adoption.microsoft.com/copilot-chat/success-kit/) – Use it to prepare your tenant for Copilot Chat and to enable your users to create and use agents. The kit includes information on admin controls, licensing and payment methods, training materials, onboarding email templates, and more.
- [Copilot Chat Trainer Kit](https://aka.ms/CopilotChat/TrainerKit) – Downloadable PowerPoint training presentation to help businesses get started with Copilot Chat.
- [Copilot user tools and templates](https://adoption.microsoft.com/copilot/user-engagement-tools-and-templates/) – A collection of user-facing tools and templates for you to quickly onboard your organization. See the section for Copilot Chat tools and templates.

## Track Copilot Chat usage
Microsoft 365 admins can also track Copilot Chat usage in their Microsoft 365 environments. The [Microsoft 365 Copilot Chat usage dashboard](https://learn.microsoft.com/microsoft-365/admin/activity-reports/microsoft-copilot-usage?view=o365-worldwide) provides insights into active usage of Copilot Chat. This can be helpful in helping to track adoption over time.

## Manage Copilot Chat

Microsoft 365 admins can manage Copilot Chat in the admin center through the Copilot Control System settings. In it, an admin can configure how user interact with Copilot, such as:

- Choose whether users have Copilot Chat pinned across their experiences.
- Manage whether users can generate images with Copilot Chat.
- Control how users can create and use agents.
- Manage web search capabilities by using the Allow web search in Copilot policy.


## Need more? Add a Microsoft 365 Copilot license

Microsoft 365 gives you a path to greater productivity for your users by adding a Microsoft 365 Copilot license to your Microsoft 365 subscription. Adding it will provide you with:
- **Deeper integration with Microsoft 365 Apps** – Embedded directly in the apps you use, it enables in-context assistance like summarizing meetings, drafting documents, analyzing spreadsheets, and generating presentations—all grounded in your work content.
- **Enterprise-Grade Data Grounding** - While Copilot Chat is grounded in public web data, Microsoft 365 Copilot adds secure access to your organization’s internal data—emails, chats, files, meetings—via Microsoft Graph. This unlocks more relevant, personalized, and actionable responses.
- **Advanced Agents** - Gives you access to powerful agents like Researcher and Analyst that can automate complex, multi-step workflows. 
- **Advanced controls and analytics** - Microsoft 365 Copilot includes the Copilot Control System and Copilot Analytics, giving IT admins tools to manage access, enforce data governance, and measure usage and ROI—capabilities not available in the Copilot Chat experience.

If you need help determining if you need to add a Microsoft 365 Copilot license, see [Decide which Copilot is right for you](https://learn.microsoft.com/copilot/microsoft-365/which-copilot-for-your-organization).







## Prerequisites

- Users must have a Microsoft 365 license assigned to them. You can find the list of eligible base licenses in [Microsoft 365 Copilot license options](microsoft-365-copilot-licensing.md) or in the [Microsoft 365 Copilot service description guide](/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-copilot).

- Users must have [Microsoft Entra ID](/microsoft-365/admin/add-users/add-users) accounts. You can add or sync users using the [onboarding wizard in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home?Q=m365setup#/modernonboarding/identitywizard).

- Microsoft 365 Copilot is only supported on primary mailboxes that are hosted on Exchange Online.

## App requirements

- **[Microsoft 365 Apps](/deployoffice/about-microsoft-365-apps)** - The apps must be deployed. You can use the [Microsoft 365 Apps setup guide in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home?Q=learndocs#/modernonboarding/microsoft365copilotsetupguide) to deploy to your users.

  > [!NOTE]
  >
  > - For Copilot to work in Word Online, Excel Online, and PowerPoint Online, you must enable third-party cookies.
  > - Review your privacy settings for Microsoft 365 Apps. These settings might affect the availability of Microsoft 365 Copilot features. For more information, see [Microsoft 365 Copilot and privacy controls for connected experiences](microsoft-365-copilot-privacy.md#microsoft-365-copilot-and-privacy-controls-for-connected-experiences).
  > - Copilot isn't available when using device-based licensing for Microsoft 365 Apps for enterprise.

- **Microsoft OneDrive** - Some features in Microsoft 365 Copilot, such as file restore and OneDrive management, require that users have a [OneDrive account](/sharepoint/introduction). You can use the [OneDrive setup guide in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home?Q=m365setup#/modernonboarding/onedrivequickstartguide) to enable OneDrive for your users.

- **Microsoft Outlook** - Microsoft 365 Copilot works with classic Outlook and new Outlook (for [Windows](https://support.microsoft.com/office/getting-started-with-the-new-outlook-for-windows-656bb8d9-5a60-49b2-a98b-ba7822bc7627) and [Mac](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)). Users can switch to the new Outlook by selecting **Try the new Outlook** in their existing Outlook client.

  > [!IMPORTANT]
  > Microsoft 365 Copilot is only supported on primary mailboxes that are hosted on Exchange Online. It isn't available on a user's archive mailbox, group mailboxes, or shared and delegate mailboxes that they have access to.

- **Microsoft Teams** - You can use the [Microsoft Teams setup guide in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home?Q=m365setup#/modernonboarding/microsoftteamssetupguide) to configure popular Teams settings, including external access, guest access, team creation permissions, and more. Copilot in Teams is available on Windows, Mac, web, Android, and iOS.

  To enable Copilot in Teams to reference meeting content after the meeting ends, enable transcription or meeting recording. To learn more about configuring transcription and recording, see [Configure transcription and captions for Teams meetings](/microsoftteams/meeting-transcription-captions) and [Teams meeting recording](/microsoftteams/meeting-recording).

- **Microsoft Teams Phone** - Copilot in [Teams Phone](/microsoftteams/what-is-phone-system-in-office-365) supports voice over Internet Protocol (VOIP) and public switched telephone network (PSTN) calls.

  - For support across VoIP calls, you need a Microsoft 365 Copilot license.
  - To use Copilot for PSTN calls, you need a Teams Phone license, a calling plan, and a Microsoft 365 Copilot license.
  - To enable Copilot in Teams Phone, you need to turn on transcription or recording.

  For VoIP callers, all participants see a notification that the call is being transcribed or recorded. For PSTN callers, all participants hear an announcement that the call is being recorded.

- **Microsoft Loop** - To use Microsoft 365 Copilot with Microsoft Loop, you must have Loop enabled for your tenant. You enable Loop in the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Settings/Services/:/Settings/L1/Loop) or the [Microsoft 365 Apps admin center](https://config.office.com) under **Customization** \| **Policy Management**.

  To learn more, see:

  - [Manage Loop workspaces in Syntex repository services](/microsoft-365/loop/loop-workspaces-configuration)
  - [Learn how to enable the Microsoft Loop app](https://techcommunity.microsoft.com/t5/microsoft-365-blog/learn-how-to-enable-the-microsoft-loop-app-now-in-public-preview/ba-p/3769013).

- **Microsoft Whiteboard** - To use Microsoft 365 Copilot with Microsoft Whiteboard, you must have Whiteboard enabled for your tenant. To learn more about Microsoft Whiteboard, see [Manage access to Microsoft Whiteboard for your organization](/microsoft-365/whiteboard/manage-whiteboard-access-organizations).

## Review app privacy

Review your Microsoft 365 apps privacy settings. The privacy settings in your Microsoft 365 apps can affect the availability of Microsoft 365 Copilot features. To ensure that users can access Copilot features, review the privacy settings in your Microsoft 365 apps.

To learn more, see [Microsoft 365 Copilot and privacy controls for connected experiences](microsoft-365-copilot-privacy.md#microsoft-365-copilot-and-privacy-controls-for-connected-experiences).

## Run the Office Feature Updates task

The Office Feature Updates task is required for core Copilot experiences in apps such as Word, PowerPoint, Excel, and OneNote, to work properly. This task should be allowed to run on its regular schedule, and allowed to access the required network resources.

For more information about the Office Feature Updates task, see [Office Feature Updates task description and FAQ](/microsoft-365/troubleshoot/updates/office-feature-updates-task-faq).

For more information about the network resources that should be allowed, see [Network requirements](#network-requirements) (in this article).

## Network requirements

Configure your network for Microsoft 365 Copilot. Copilot experiences are deeply integrated with Microsoft 365 applications and often use the same [network connections and endpoints that Microsoft 365 apps](/microsoft-365/enterprise/urls-and-ip-address-ranges) use.

Baseline network configuration customers should:

- Make sure that the Microsoft 365 endpoints listed in this section aren't blocked within their environment.
- Verify that their network setup follows [Microsoft 365 network connectivity principles and best practices](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

✅ **Network endpoint requirements**:

- Allow the [worldwide Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).
- Allow traffic to the following domains:

  - `copilot.microsoft.com`, `*.copilot.microsoft.com`
  - `*.bing.com`, `*.bingapis.com`

  These network endpoints (domains) allow some Copilot scenarios to enable richer integrations, like Copilot experiences for the Web.

- Allow the [Copilot Chat network requirements](/copilot/manage#network-requirements).

✅ **WebSockets (WSS) protocol requirements**:

Verify that your network supports full WSS connectivity from user devices running Microsoft 365 applications to the following domains:

- Microsoft 365 Copilot enterprise experiences: `*.cloud.microsoft`, `*.office.com`
- Other Copilot experiences, including consumer: `*.bing.com`, `copilot.microsoft.com`, `*.copilot.microsoft.com`

Several Copilot integrations rely on WebSockets (WSS) to deliver a streamlined user experience. Some customer networks might not be configured to handle WSS connections properly, which can result in Copilot application failures. Typical network configurations that affect WSS include:

- The network perimeter blocks the WSS protocol
- Network devices attempting to perform Transport Layer Security (TLS) inspection of connections
- Proxy servers enforcing aggressive connection timeouts

✅ **FQDNs and subdomains**:

Some organization might prefer to use granular definitions of endpoints, like individual FQDNs, instead of wildcards to configure their network settings. Due to hyperscale and the dynamic nature of its services, Microsoft 365 can't provide specific FQDNs used by individual features and scenarios. Doing so would result in unmanageable configuration surface, constant customer network changes, and connectivity incidents.

When you review and implement the recommended network configurations, consider all the FQDNs and subdomains where wildcards are specified. These wildcards include functionally that the referenced scenarios require.

✅ **cloud.microsoft domain**:

Microsoft plans to consolidate Copilot experiences for Microsoft 365 under the `*.cloud.microsoft` domain. And, Copilot network requirements and associated required customer network configurations can be further simplified.

To learn more, see [Unified cloud.microsoft domain for Microsoft 365 apps](/microsoft-365/enterprise/cloud-microsoft-domain).

## Related content

- [Microsoft 365 Copilot setup guide in the Microsoft admin center](https://admin.microsoft.com/Adminportal/Home?Q=learndocs#/modernonboarding/microsoft365copilotsetupguide)
- [Copilot Prompt Gallery](https://copilot.cloud.microsoft/prompts)
- [Microsoft 365 Copilot - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/microsoft-365-copilot/ct-p/Microsoft365Copilot)
- [Microsoft 365 Copilot adoption guide and overview for IT admins](microsoft-365-copilot-reports-for-admins.md)
