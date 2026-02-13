---
title: Considerations for Microsoft 365 Copilot Chat admins
f1.keywords:
- NOCSH
ms.author: efrene 
author: efrene
manager: scotv
ms.date: 01/28/2026
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
description: Microsoft 365 admins can learn important considerations for Microsoft 365 Copilot Chat. 
ms.custom: [copilot-learning-hub]
appliesto:
- ✅ Microsoft 365 Copilot
---

# Considerations for Microsoft 365 Copilot Chat admins

This document outlines the minimum technical and licensing requirements for using Microsoft 365 Copilot Chat in your organization.

[Microsoft 365 Copilot Chat](/copilot/overview) is an AI chat tool that is included in your Microsoft 365 subscription and is integrated into Microsoft 365 apps such as Word, Excel, Outlook, and Teams. It uses the latest AI models and data from the web to answer your questions, generate content and ideas, and find information. Since it is included in your Microsoft 365 subscription, it is the entry point into the Microsoft 365 Copilot experience.

## Considerations for admins


|  | Copilot license | Microsoft 365 subscription |
|---|---|---|
| Search | ✅ | ✅ |
| Chat | ✅ <br><br> Work-based and web-grounded chat <br/><br/>Automatically enabled in the Copilot app and is the Copilot app's default landing page | ✅ <br><br> Web-grounded chat only; No work-based chat <br/><br/>Can pin the Chat app to the Copilot app. |
| Agents | ✅ | ✅ <br/><br/> Agents are metered. |
| Pages | ✅ | ✅ |
| Notebooks | ✅ | ❌ |
| Create | ✅ <br/><br/> Use AI and templates to create and edit images, posters, banners, videos, and more. | ✅ <br><br> Use templates to create and edit images, posters, banners, videos, and more. |
| Apps | ✅ <br/><br/>Users can get and pin apps. | ✅ <br/><br/>Users can get and pin apps. |

## Is my data secure?
Security and privacy for organizational data is always a top-of-mind concern for our customers. Uncertainty about how Copilot Chat uses their data may be a reason that some customers are hesitant to use it.

Admins do not need to do any additional configuration in regards to security when using Copilot Chat.  But an understanding of what the following might be helpful for them to know.

- **Enterprise Data Protection (EDP)** - Microsoft 365 Copilot Chat is protected by Enterprise Data Protection (EDP). With EDP, [prompts and responses are protected](/copilot/microsoft-365/enterprise-data-protection#enterprise-data-protection-for-prompts-and-responses) by the same contractual terms and commitments widely trusted by our customers for their emails in Exchange and files in SharePoint.
- **Responses grounded in web data**- Copilot Chat is a generative AI service grounded in data from the public web in the Bing search index only. Unlike Microsoft 365 Copilot, Copilot Chat cannot invoke organizational content like files, emails, or chats when interacting in Copilot Chat.
- **Users can choose to provide organizational data** - Copilot Chat users can provide organizational content as part of their prompt, manually uploading a file directly, or use an agent that is given access to organizational content. Learn more about [organizational data and Copilot Chat](/copilot/privacy-and-protections#organizational-data).
- **European Union Data Boundary (EUDB)** - Microsoft 365 Copilot Chat calls to the LLM are routed to the closest data centers in the region, but can also call into other regions where greater capacity is available when utilization is especially high. For European Union (EU) users, Copilot Chat has additional safeguards to comply with the EU Data Boundary. EU traffic stays within the [EU Data Boundary](/privacy/eudb/eu-data-boundary-learn), while worldwide traffic can be sent to the EU and other countries or regions for LLM processing.


## Track Copilot Chat adoption
The [Microsoft 365 Copilot Chat usage report](/microsoft-365/admin/activity-reports/microsoft-copilot-usage) helps admins understand how users are engaging with Copilot Chat and can be useful in tracking adoption over time and in which Microsoft 365 app (for example, Teams, Outlook, and Word). It shows key metrics such as total active users, average daily active users, total prompts submitted, average prompts per user. You can review usage totals and trends over the past 7, 30, 90, or 180 days. The report also includes per‑user activity details—such as last activity date, number of prompts, and active days—which are anonymized by default.

Admins can also use the [Organizational messages](/copilot/microsoft-365/microsoft-365-copilot-enable-users) feature to act on adoption trends they are seeing. It lets you reach your users in the flow of their daily work with targeted, actionable guidance. 

For example, in the Copilot Chat usage report, an admin might discover that Copilot Chat usage is unexpectedly low, where a number of users have not used Copilot Chat for an extended period of time (for example, the past 28 days). Through organizational messaging, the admin can send notifications directly to these specific users. The notification could be to drive adoption by providing relateable examples about how Copilot Chat could be useful to complete common work tasks and links to article or video resources. And if your users mostly work in Microsoft Teams, you can have the notication display in Teams and on a scheduled basis to increase awareness.


## Manage Copilot Chat
Microsoft 365 admins can manage Copilot Chat in the admin center through the Copilot Control System settings. In it, an admin can configure how user interact with Copilot Chat such as:

- Choose whether users have Copilot Chat pinned across their experiences.
- Manage whether users can generate images with Copilot Chat.
- Control how users can create and use agents.
- Manage web search capabilities by using the Allow web search in Copilot policy.
- [Remove access to Copilot Chat](/copilot/manage#remove-access-to--chat)

And you can assign the [AI Administrator role](/microsoft-365/admin/whats-new-in-preview?view=o365-worldwide#january-2025) to manage all settings related to Copilot and AI features. It provdes least‑privilege access, without requiring Global Administrator permissions.



## Agents in Copilot Chat

An [agent in Copilot Chat](/copilot/agents) is an AI assistant that can perform tasks, automate workflows, or operate independently to help you get work done. Agents vary in complexity — from simple helpers that retrieve information to advanced ones that act on your behalf.

Microsoft 365 Copilot Chat has agents that can be used at no additional cost as well as agents that are billed based on metered consumption. 

## Train your users
Copilot Chat is available to users in many of the key Microsoft 365 apps in which they do their work. Admins can help them to understand how to use Copilot Chat to assist them with work tasks by pointing them to the following resources:
- [Microsoft 365 Copilot Chat, your AI assistant for work](https://support.microsoft.com/copilot-microsoft365-chat) - Guidance on how to get started, use different prompts, and understand the differences between Copilot Chat and other Copilot offerings.
- [Microsoft Copilot Chat video tutorial](https://support.microsoft.com/topic/microsoft-365-copilot-chat-video-tutorial-e54fb679-9554-435a-8418-d0e0ce2646c6) – Short, easy-to-understand videos on getting started and tasks you can do with Copilot Chat.
- [Copilot Prompt Gallery](https://copilot.cloud.microsoft/prompts?products%2Fname=CWC&createdBy=CreatedByAll) – Example prompts for your user to help them do their work (for example, ”How can I more concisely describe change management?”). 
- [Copilot Chat Success Kit](https://adoption.microsoft.com/copilot-chat/success-kit/) – Use it to prepare your tenant for Copilot Chat and to enable your users to create and use agents. The kit includes information on admin controls, licensing and payment methods, training materials, onboarding email templates, and more.
- [Copilot Chat Trainer Kit](https://aka.ms/CopilotChat/TrainerKit) – Downloadable PowerPoint training presentation to help businesses get started with Copilot Chat.
- [Copilot user tools and templates](https://adoption.microsoft.com/copilot/user-engagement-tools-and-templates/) – A collection of user-facing tools and templates for you to quickly onboard your organization. See the section for Copilot Chat tools and templates.
- [Transform ideas into action with Copilot Chat](/training/paths/explore-microsoft-365-copilot-business-chat) - This course teaches learners how to get started with Microsoft 365 Copilot Chat, craft effective prompts, and use its AI-powered features to enhance productivity, streamline work, and collaborate securely in real-time.



## Need more? Add a Microsoft 365 Copilot license

Microsoft 365 gives you a path to greater productivity for your users by adding a Microsoft 365 Copilot license to your Microsoft 365 subscription. Adding it will provide you with:
- **Deeper integration with Microsoft 365 Apps** – Embedded directly in the apps you use, it enables in-context assistance like summarizing meetings, drafting documents, analyzing spreadsheets, and generating presentations—all grounded in your work content.
- **Enterprise-Grade Data Grounding** - While Copilot Chat is grounded in public web data, Microsoft 365 Copilot adds secure access to your organization’s internal data—emails, chats, files, meetings—via Microsoft Graph. This unlocks more relevant, personalized, and actionable responses.
- **Advanced Agents** - Gives you access to powerful agents like Researcher and Analyst that can automate complex, multi-step workflows. 
- **Advanced controls and analytics** - Microsoft 365 Copilot includes the Copilot Control System and Copilot Analytics, giving IT admins tools to manage access, enforce data governance, and measure usage and ROI—capabilities not available in the Copilot Chat experience.

If you need help determining if you need to add a Microsoft 365 Copilot license, see [Decide which Copilot is right for you](/copilot/microsoft-365/which-copilot-for-your-organization).










