---
title: "Cowork agent FAQ (Frontier)"
description: "Frequently asked questions about the Cowork agent in Microsoft 365 Copilot."
ms.date: 02/27/2026
ms.topic: article
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# Cowork agent FAQ (Frontier)

Find answers to frequently asked questions about the Cowork agent in Microsoft 365 Copilot.

## What is the Cowork agent?

Cowork is an AI agent available in Microsoft 365 Copilot. It carries out tasks on your behalf. For example, it can send emails, schedule meetings, create documents, post in Teams, and handle multi-step tasks across your Microsoft 365 environment.

## What can Cowork do for me?

Cowork can handle a wide range of everyday work tasks, including:

- Send emails and draft messages on your behalf.
- Schedule meetings and manage your calendar.
- Create documents in Word, Excel, PowerPoint, and PDF.
- Post in Teams channels and conversations.
- Organize your calendar and prepare daily briefings.
- Search across your organization for files, people, and information.
- Draft stakeholder communications and other professional content.

## What skills does Cowork have?

Cowork comes with a set of built-in skills, each designed for a specific type of task:

| Skill | What it does |
|---|---|
| Word | Creates and edits Word documents |
| Excel | Creates and edits spreadsheets |
| PowerPoint | Creates and edits presentations |
| PDF | Generates PDF files |
| Email | Sends and drafts emails on your behalf |
| Scheduling | Finds available times and proposes meetings |
| Calendar Management | Creates, updates, and manages calendar events |
| Meetings | Schedules meetings with attendees and agendas |
| Daily Briefing | Summarizes your upcoming day's meetings, priorities, and action items |
| Enterprise Search | Finds files, people, and information across your organization |
| Communications | Drafts professional messages for stakeholders and teams |

## How do I start using Cowork?

Getting started takes just a few steps.

1. Open  [Microsoft 365 Copilot](https://m365.cloud.microsoft).
2. Select the **Cowork agent** from the agent list (or use **@Cowork** to mention it).
3. Describe the task you want to accomplish. You can type up to 16,000 characters, and attach files by dragging them into the chat or using the file picker.
4. Send your message. Cowork begins processing your request.

## What file types does Cowork support?

You can attach a wide variety of files to your conversations. Cowork supports the following categories:

- **Word**: `.doc`, `.docx`, `.docm`, `.dot`, `.dotx`, `.odt`, `.rtf`
- **Excel**: `.csv`, `.xls`, `.xlsm`, `.xlsx`, `.ods`
- **PowerPoint**: `.odp`, `.ppt`, `.pptm`, `.pptx`
- **PDF**: `.pdf`
- **Markdown**: `.md`, `.markdown`, `.mdx`
- **Image**: `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.bmp`, `.svg`, `.ico`
- **Text**: `.txt`, `.log`
- **Code**: `.js`, `.ts`, `.py`, `.java`, `.c`, `.cpp`, `.go`, `.rb`, `.rs`, and others
- **Config**: `.json`, `.yaml`, `.yml`, `.toml`, `.ini`, `.xml`, `.env`
- **Notebook**: `.ipynb`
- **Audio**: `.mp3`, `.wav`, `.m4a`, `.ogg`, `.aac`, `.flac`
- **Video**: `.mp4`, `.mov`, `.avi`, `.mkv`, `.webm`, `.wmv`
- **Archive**: `.zip`, `.rar`, `.7z`, `.tar`, `.gz`, `.bz2`

## Can I preview files without downloading them?

Yes. You can preview the following file types directly in the conversation:

- PDF
- CSV
- Markdown
- Images
- HTML

Select a file to open an inline preview. You can also go full-screen or open the file in its native app.

## How does action approval work?

Before Cowork takes a sensitive action like sending an email or posting in Teams, it displays an approval prompt with the following choices:

- **Approve**: Let Cowork proceed with the action this one time.
- **Approve & Remember**: Allow the action now and skip the prompt for similar actions in the future.
- **Reject**: Stop Cowork from taking the action.

> [!NOTE]
> For some actions, such as sending an email or posting in Teams, Cowork shows you a native preview of the content so you can review it before approving.

## Can I pause or stop Cowork while it's working?

Yes. You have the following controls:

- **Pause**: Cowork waits for the current step to finish, then pauses. You can also do a hard pause that stops it immediately.
- **Resume**: Continue from where Cowork stopped.
- **Cancel**: End the current task entirely.

## What happens if I lose my connection?

Cowork automatically reconnects and picks up where it left off. Progress made while you were disconnected is preserved, so you don't lose any work.

## Can I use my voice to talk to Cowork?

Yes. Select the microphone button in the chat input to speak your message. Cowork transcribes your words and sends them as text.

> [!NOTE]
> Voice input availability depends on your browser. Not all browsers support this feature.

## How do I manage my projects and tasks?

Cowork gives you the following ways to stay organized:

- **Tasks view**: Show your tasks in a **list** or **kanban board** and track their progress.
- **Projects dashboard**: Browse your **highlights** and **all projects**. Switch between kanban, list, and grid views. Each project shows its current status so you always know where things stand.

Select a project to jump back into the conversation.

## Where are my files saved?

Files that Cowork creates are saved to your **OneDrive and SharePoint** workspace. You can browse them in the side panel during a conversation or access them directly in OneDrive at any time.

## Is Cowork secure?

Yes. Every action Cowork takes is authorized through your Microsoft 365 account. Cowork accesses only the services and data you're already permitted to use. The agent runs in a secure, isolated environment.

## How do I give feedback?

You can share feedback in the following ways:

- **Thumbs up / thumbs down**: Rate any response from Cowork directly in the conversation.
- **Document feedback**: When previewing a file Cowork created, use the feedback controls to rate it.
- **General feedback**: To share broader thoughts about your experience, open the menu and select the feedback option.

## Does Cowork ask me questions?

Yes. Sometimes Cowork needs more information to complete your request. When this happens, it presents a question with a set of choices for you to pick from. You can select an option, type your own answer, or select **Skip** to let Cowork continue without additional input. The task status shows **Needs user input** when Cowork is waiting for your answer.

## Related content

- [Cowork overview](index.md)
- [Get started with the Cowork agent](get-started.md)
- [Use the Cowork agent](use-cowork-agent.md)
