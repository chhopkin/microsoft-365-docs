---
title: "Copilot Cowork overview (Frontier)"
description: "Learn about Copilot Cowork in Microsoft 365 Copilot, which is an AI agent that takes action on your behalf."
ms.date: 03/30/2026
ms.topic: overview
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
ms.subservice: cowork
appliesto:
- Microsoft 365 Copilot
---

# Copilot Cowork overview (Frontier)
[!INCLUDE [cowork-top-note](../includes/cowork-top-note.md)]
[!INCLUDE [cowork-preview](../includes/cowork-preview.md)]

Copilot Cowork in Microsoft 365 Copilot can carry out tasks on your behalf. You describe what you need, and Copilot Cowork sends emails, schedules meetings, creates documents, posts in Teams, and manages your calendar. You approve each action before it happens.

## What is Copilot Cowork agent?

Copilot Cowork is an AI agent available in Microsoft 365 Copilot. It carries out tasks across your Microsoft 365 environment. Rather than describing what you could do, it does the work.

- **Sends emails**: Drafts, replies, forwards, and sends messages through Outlook, complete with attachments.
- **Schedules meetings**: Creates calendar events, adds attendees, and helps you organize your day.
- **Creates documents**: Builds Word documents, Excel spreadsheets, PowerPoint presentations, and PDFs.
- **Posts in Teams**: Sends messages to channels and chats.
- **Searches your organization**: Finds the information you need across your company's resources and your OneDrive files.

Copilot Cowork shows each step in your conversation, so you can follow along as it works.

## What can Copilot Cowork do for you?

The following sections describe what you can ask Copilot Cowork to do.

### Communication

- Draft and send emails, reply to messages, and forward entire email threads to the right people.
- Save email drafts and manage attachments before sending.
- Post updates in Teams channels or send direct messages in Teams chats.
- Prepare polished stakeholder communications such as status updates, announcements, and follow-ups.

### Documents and files

- Create Word documents, Excel spreadsheets, PowerPoint presentations, and PDFs from scratch.
- Edit and refine existing documents you share in the conversation.
- Browse your OneDrive files and pull in the content you need.

### Calendar and meetings

- Schedule meetings using natural language, such as "set up a 30-minute check-in with Alex tomorrow at 2 PM."
- Create all-day events or add a Teams meeting link automatically.
- Manage your calendar&mdash;add events, move things around, or clean up conflicts.
- Get meeting intelligence and insights to help you prepare for upcoming conversations.
- Start your day with a daily briefing that highlights what's ahead.

### Research and search

- Search across your organization to find documents, messages, and information.
- Perform deep research that synthesizes information from multiple sources into comprehensive reports.
- Browse your OneDrive folders and select files to work with.

### Automation

- Run prompts on a schedule, so recurring tasks happen automatically.

## Skills

Copilot Cowork uses specialized skills as it works. When the agent loads a new skill during your conversation, a message such as "Preparing to compose emails" appears, and the skill shows up in the side panel. Each skill corresponds to a specific type of task.

Copilot Cowork has 13 built-in skills, including Word, Excel, PowerPoint, PDF, Email, Scheduling, Calendar Management, Meetings, Daily Briefing, Enterprise Search, Communications, Deep Research, and Adaptive Cards. You can also create your own custom skills.

For a detailed description of each skill, see [Copilot Cowork skills](use-cowork-agent.md#copilot-cowork-skills).

You can extend Copilot Cowork with custom skills stored in your OneDrive. Create a subfolder in `/Cowork/.skills/` and place a `SKILL.md` file inside it (for example, `/Cowork/.skills/weekly-report/SKILL.md`). Copilot Cowork discovers your custom skills automatically at the start of each conversation. You can create up to 20 custom skills.

As Copilot Cowork loads skills during a conversation, the side panel updates to show which skills are active.

## How you work with Copilot Cowork

Here's how a typical interaction works:

1. **Describe your task**: Tell Copilot Cowork what you need. For example, "Send a meeting recap to my team" or "Create a slide deck summarizing Q3 results." You can also attach files by dragging them into the chat.
1. **Watch Copilot Cowork work**: The agent breaks your request into steps and works through them one by one. You can follow along as each step appears in the conversation.
1. **Approve actions when asked**: Before Copilot Cowork takes an important action, like sending an email or scheduling a meeting, it pauses and asks for your go-ahead. You decide whether to proceed.
1. **Review the results**: When Copilot Cowork finishes, review what it produced. Download documents, check sent messages, or ask Copilot Cowork to make changes.

## Stay in control

You control what Copilot Cowork does throughout a conversation.

- **Approve actions**: Copilot Cowork asks for your permission before taking sensitive actions, with a risk level indicator for medium and high risk actions. You can **Approve**, **Approve & Remember** (for the current conversation), or **Reject**.
- **Pause, resume, and cancel**: Pause the agent at any time, resume when ready, or cancel the current task.
- **Give feedback**: Rate responses, leave comments on documents, or share general feedback.

For details on each option, see [Approve actions](use-cowork-agent.md#approve-actions) and [Control the conversation](use-cowork-agent.md#control-the-conversation).

## Manage your work

Copilot Cowork helps you stay organized with built-in project and task management.

- **Task views**: Display your tasks in a sortable **list view**, a visual **kanban board**, or the **Scheduled** tab to manage your scheduled prompts. Each task shows a status: **In progress**, **Needs user input**, **Done**, or **Failed**.

## Data protection and privacy

Copilot Cowork adheres to the data protection policies detailed in [Microsoft 365 Copilot Privacy](/copilot/microsoft-365/microsoft-365-copilot-privacy) and [Microsoft Privacy Statement](https://www.microsoft.com/en-us/privacy/privacystatement?msockid=02283d33f3b26a153db42c6af7b26c18).

## Get started

Copilot Cowork is available in your browser at [m365.cloud.microsoft](https://m365.cloud.microsoft) and in the Microsoft 365 Copilot desktop app for Windows and Mac.

Learn more in [Get started with Copilot Cowork](get-started.md).

## Related content

- [Use Copilot Cowork agent](use-cowork-agent.md)
- [Copilot Cowork agent common questions](cowork-agent-faq.md)
