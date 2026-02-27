---
title: "FAQ for the Coworker agent"
description: "Get answers to frequently asked questions about responsible AI and the Coworker agent in Microsoft 365 Copilot."
ms.date: 02/27/2026
ms.topic: faq
ms.custom:
  - transparency-note
author: copilot-docs
ms.author: copilot-docs
---

# FAQ for the Coworker agent

These frequently asked questions (FAQ) describe the AI impact of the Coworker agent in Microsoft 365 Copilot.

## What is the Coworker agent?

The Coworker agent is an AI-powered assistant in Microsoft 365 Copilot that carries out tasks on your behalf across Microsoft 365. You describe what you need in natural language, and Coworker performs the work — sending emails, scheduling meetings, creating documents, posting in Teams, and managing files. Each action the agent takes is visible in the conversation, and sensitive actions require your explicit approval before they're executed.

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

During a conversation, Coworker acquires specialized skills as needed, such as Word, Excel, PowerPoint, PDF, Email, Scheduling, Calendar, Meetings, Daily Briefing, Enterprise Search, and Communications.

## What is the Coworker agent's intended use?

Coworker is designed for information workers who use Microsoft 365 and want to delegate multi-step tasks to an AI agent. Typical use cases include:

- Drafting and sending emails based on verbal or written instructions.
- Creating structured documents from unstructured input (for example, turning meeting notes into a formatted report).
- Scheduling meetings and managing calendar conflicts.
- Posting status updates in Teams channels.
- Searching for and organizing files across OneDrive and SharePoint.

Coworker is not intended for use cases that require guaranteed accuracy without human review, such as legal filings, medical decisions, or financial transactions that bypass approval processes.

## How is the Coworker agent evaluated? What metrics are used to measure performance?

Microsoft evaluates Coworker across several areas:

- **Task completion** — Whether the agent successfully carries out the requested action (for example, an email is sent, a document is created).
- **Response quality** — Whether the agent's output meets the user's intent based on the natural language instruction.
- **User feedback** — Thumbs up and thumbs down ratings on individual responses and generated documents, collected directly in the conversation.
- **Safety and compliance** — Ongoing evaluation to ensure the agent operates within Microsoft's responsible AI principles.

## What are the limitations of the Coworker agent? How can users minimize the impact of these limitations?

Current limitations include:

- Coworker may misinterpret ambiguous or overly broad instructions, leading to actions that don't match your intent.
- AI-generated documents and messages should be treated as drafts. Always review content before sending or sharing.
- The agent may produce inaccurate information when searching across your organization, particularly when source data is incomplete or outdated.
- Complex, multi-step tasks with many dependencies may not always complete as expected.
- Coworker is dependent on your existing Microsoft 365 permissions — it cannot access data or services that your account is not authorized to use.

To minimize these limitations:

- Provide clear, specific instructions. Include details about recipients, formatting, and expected outcomes.
- Review all generated content — emails, documents, and messages — before approving actions.
- Use the pause and cancel controls to stop work if the agent is heading in the wrong direction.
- Provide thumbs up or thumbs down feedback to help improve future responses.

## How does the Coworker agent handle action approval?

Before Coworker performs a sensitive action — such as sending an email, posting in Teams, or modifying a file — it presents an approval dialog. You have three options:

- **Approve** — Allow the action to proceed this one time.
- **Approve and remember** — Allow the action and skip the approval prompt for similar actions in the future.
- **Cancel** — Block the action.

For certain actions, such as sending an email, Coworker displays a preview of the content so you can review it before approving. The agent does not execute sensitive actions without your explicit consent.

## How does the Coworker agent handle my data?

Coworker operates within the security and compliance boundaries of Microsoft 365:

- **Authentication** — Coworker uses your existing Microsoft 365 credentials. It only accesses services and data that your account is permitted to use.
- **Tenant isolation** — Your data is isolated to your organization's tenant. Coworker cannot access data from other tenants.
- **Data subject rights** — Access, deletion, rectification, and portability requests are supported in accordance with Microsoft's privacy standards.
- **File storage** — Files that Coworker creates are stored in your OneDrive and SharePoint workspace.

Coworker does not use your data to train AI models. Your organizational data remains within Microsoft 365 and is subject to your organization's existing data governance policies.

## What operational factors and settings allow for effective and responsible use?

- Coworker is available within Microsoft 365 Copilot and is subject to your organization's access policies and licensing.
- Always review AI-generated content before approving actions that send, post, or share information externally.
- Use the conversation controls (pause, resume, cancel) to manage the agent's work if it goes off track.
- Administrators manage Coworker access through the Microsoft 365 admin center.
- Providing regular feedback through the thumbs up/down controls and the general feedback option helps improve the agent's performance over time.

## How do I provide feedback on the Coworker agent?

You can provide feedback in several ways:

- **Thumbs up or thumbs down** on individual AI responses in the conversation.
- **Document feedback** when previewing files that Coworker created.
- **General feedback** through the feedback option in the header menu.

Your feedback is used to evaluate and improve the Coworker agent's quality and safety.

## Related content

- [Coworker overview](overview.md)
- [Get started with Coworker](getting-started.md)
- [Use the Coworker agent](using.md)
- [Coworker FAQ](faq.md)
- [Microsoft AI principles](https://www.microsoft.com/ai/responsible-ai)
