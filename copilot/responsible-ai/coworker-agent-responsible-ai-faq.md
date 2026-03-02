---
title: "FAQ for the Coworker agent"
description: "Get answers to frequently asked questions about responsible AI and the Coworker agent in Microsoft 365 Copilot."
ms.date: 02/27/2026
ms.topic: faq
ms.custom:
  - transparency-note
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# FAQ for the Coworker agent

These frequently asked questions (FAQ) describe the AI impact of the Coworker agent in Microsoft 365 Copilot.

## What is the Coworker agent?

The Coworker agent is an AI-powered assistant in Microsoft 365 Copilot that carries out tasks on your behalf across Microsoft 365. You describe what you need in natural language, and Coworker performs the work. For example, it can send emails, schedule meetings, create documents, post in Teams, and manage files. Each action the agent takes is visible in the conversation. Sensitive actions require your explicit approval before they're executed.

## What are the Coworker agent's capabilities?

Coworker can:

- Draft and send emails, reply to messages, and forward messages with attachments through Outlook.
- Create and manage calendar events and schedule meetings.
- Post messages in Teams channels and chats.
- Create Word documents, Excel spreadsheets, PowerPoint presentations, and PDFs.
- Search across your organization for files, people, and information.
- Browse and manage files in OneDrive and SharePoint.
- Execute Python and Bash scripts to process data, generate reports, or automate calculations.
- Prepare daily briefings and meeting intelligence summaries.
- Draft stakeholder communications.

During a conversation, Coworker acquires specialized skills as needed, such as the following: Word, Excel, PowerPoint, PDF, Email, Scheduling, Calendar, Meetings, Daily Briefing, Enterprise Search, and Communications.

## What is the Coworker agent's intended use?

Coworker is designed for information workers who use Microsoft 365 and want to delegate multi-step tasks to an AI agent. Typical use cases include:

- Draft and send emails based on verbal or written instructions.
- Create structured documents from unstructured input (for example, turn meeting notes into a formatted report).
- Schedule meetings and manage calendar conflicts.
- Post status updates in Teams channels.
- Search for and organize files across OneDrive and SharePoint.

Coworker isn't intended for use cases that require guaranteed accuracy without human review. Examples are legal filings, medical decisions, or financial transactions that bypass approval processes.

## How is the Coworker agent evaluated, and what metrics are used to measure performance?

Microsoft evaluates Coworker across several areas:

- **Task completion**: Whether the agent successfully carries out the requested action (for example, it sends an email or creates a document).
- **Response quality**: Whether the agent's output meets the user's intent based on the natural language instruction.
- **User feedback**: Thumbs up and thumbs down ratings on individual responses and generated documents, collected directly in the conversation.
- **Safety and compliance**: Ongoing evaluation to ensure the agent operates within Microsoft's responsible AI principles.

## What are the limitations of the Coworker agent, and how can users minimize the impact of these limitations?

Current limitations include:

- Coworker might misinterpret ambiguous or overly broad instructions, leading to actions that don't match your intent.
- AI-generated documents and messages should be treated as drafts. Always review content before sending or sharing.
- The agent might produce inaccurate information when searching across your organization, particularly when source data is incomplete or outdated.
- Complex, multi-step tasks with many dependencies might not always complete as expected.
- Coworker is dependent on your existing Microsoft 365 permissions. It can't access data or services that your account isn't authorized to use.

To minimize these limitations:

- Provide clear, specific instructions. Include details about recipients, formatting, and expected outcomes.
- Review all generated content such as emails, documents, and messages, before approving actions.
- Use the pause and cancel controls to stop work if the agent is heading in the wrong direction.
- Provide thumbs up or thumbs down feedback to help improve future responses.

## How does the Coworker agent handle action approval?

Before Coworker performs a sensitive action such as sending an email, posting in Teams, or modifying a file, it presents an approval dialog. You have the following options:

- **Approve**: Allow the action to proceed this one time.
- **Approve and remember**: Allow the action and skip the approval prompt for similar actions in the future.
- **Cancel**: Block the action.

For certain actions, such as sending an email, Coworker displays a preview of the content so you can review it before approving. The agent doesn't execute sensitive actions without your explicit consent.

## How does the Coworker agent handle my data?

Coworker operates within the security and compliance boundaries of Microsoft 365.

- **Authentication**: Coworker uses your existing Microsoft 365 credentials. It accesses only services and data that your account is permitted to use.
- **Tenant isolation**: Your data is isolated to your organization's tenant. Coworker can't access data from other tenants.
- **Data subject rights**: Access, deletion, rectification, and portability requests are supported in accordance with Microsoft's privacy standards.
- **File storage**: Files that Coworker creates are stored in your OneDrive and SharePoint workspace.

Coworker doesn't use your data to train AI models. Your organizational data remains within Microsoft 365 and is subject to your organization's existing data governance policies.

## What operational factors and settings allow for effective and responsible use?

- Coworker is available within Microsoft 365 Copilot and is subject to your organization's access policies and licensing.
- Always review AI-generated content before approving actions that send, post, or share information externally.
- Use the conversation controls (pause, resume, cancel) to manage the agent's work if it goes off track.
- Administrators manage Coworker access through the Microsoft 365 admin center.
- Provide regular feedback through the thumbs up/down controls and the general feedback option to help improve the agent's performance over time.

## How do I provide feedback on the Coworker agent?

You can provide feedback in the following ways:

- **Thumbs up or thumbs down**: On individual AI responses in the conversation.
- **Document feedback**: When previewing files that Coworker created.
- **General feedback**: Through the feedback option in the header menu.

Your feedback is used to evaluate and improve the Coworker agent's quality and safety.

## Related content

- [Coworker overview](../coworker/index.md)
- [Get started with the Coworker agent](../coworker/get-started.md)
- [Use the Coworker agent](../coworker/use-coworker-agent.md)
- [Coworker agent FAQ](../coworker/coworker-agent-faq.md)
- [Microsoft AI principles](https://www.microsoft.com/ai/responsible-ai)
