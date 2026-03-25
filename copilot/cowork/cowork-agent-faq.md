---
title: "Copilot Cowork agent common questions (Frontier)"
description: "Frequently asked questions about Copilot Cowork agent in Microsoft 365 Copilot."
ms.date: 03/30/2026
ms.topic: faq
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# Copilot Cowork agent common questions (Frontier)
[!INCLUDE [cowork-top-note](../includes/cowork-top-note.md)]
[!INCLUDE [cowork-preview](../includes/cowork-preview.md)]

Find answers to common questions about Copilot Cowork agent in Microsoft 365 Copilot.

## What is Copilot Cowork agent?

Copilot Cowork is an AI agent available in Microsoft 365 Copilot. It carries out tasks on your behalf. For example, it can send emails, schedule meetings, create documents, post in Teams, and handle multi-step tasks across your Microsoft 365 environment.

## What can Copilot Cowork do for me?

Copilot Cowork can send emails, schedule meetings, create documents (Word, Excel, PowerPoint, PDF), post in Teams, manage your calendar, prepare daily briefings, search across your organization, conduct deep research, and draft stakeholder communications. You can also schedule prompts to run automatically.

For a full breakdown by category, see [What can Copilot Cowork do for you?](index.md#what-can-copilot-cowork-do-for-you)

## What skills does Copilot Cowork have?

Copilot Cowork has 13 built-in skills: Word, Excel, PowerPoint, PDF, Email, Scheduling, Calendar Management, Meetings, Daily Briefing, Enterprise Search, Communications, Deep Research, and Adaptive Cards. You can also create your own custom skills by placing a `SKILL.md` file in a subfolder of your OneDrive `/Cowork/.skills/` folder (for example, `/Cowork/.skills/weekly-report/SKILL.md`).

For a detailed description of each skill, see [Copilot Cowork skills](use-cowork-agent.md#copilot-cowork-skills).

## Can I create my own custom skills?

Yes. You can create up to 20 custom skills by placing `SKILL.md` files in your OneDrive `/Cowork/.skills/` folder. Each file contains a YAML frontmatter block with a name and description, followed by the skill instructions. Copilot Cowork discovers your custom skills automatically at the start of each conversation.

For step-by-step instructions, see [Create custom skills](use-cowork-agent.md#create-custom-skills).

## How do I start using Copilot Cowork?

Getting started takes just a few steps.

1. Open  [Microsoft 365 Copilot](https://m365.cloud.microsoft).
2. Select the **Copilot Cowork agent** from the agent list (or use **@Cowork** to mention it).
3. Describe the task you want to accomplish. You can type up to 16,000 characters, and attach files by dragging them into the chat or using the file picker.
4. Send your message. Copilot Cowork begins processing your request.

## Does Copilot Cowork work on mobile devices?

Yes. Copilot Cowork is available in your browser at [m365.cloud.microsoft](https://m365.cloud.microsoft), in the Microsoft 365 Copilot desktop app for Windows and Mac, and in the mobile app for iOS (17.4 and later) and Android. On smaller screens, panels collapse to overlays and the layout adapts to fit the available space.

## What file types does Copilot Cowork support?

You can attach a wide variety of files to your conversations. Copilot Cowork supports the following categories:

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

Before Copilot Cowork takes a sensitive action like sending an email or posting in Teams, it displays an approval prompt. Each prompt includes a risk level (**Low Risk**, **Medium Risk**, or **High Risk**) so you can gauge the impact. Your choices are:

- **Approve**: Let Copilot Cowork proceed with the action this one time.
- **Approve & Remember**: Allow the action now and skip the prompt for similar actions in the current conversation.
- **Reject**: Stop Copilot Cowork from taking the action.

You can also select **Show parameters** to see the technical details of the action before deciding.

> [!NOTE]
> For some actions, such as sending an email or posting in Teams, Copilot Cowork shows you a native preview of the content so you can review it before approving.

## Can I pause or stop Copilot Cowork while it's working?

Yes. You have the following controls:

- **Pause**: Copilot Cowork waits for the current step to finish, then pauses. You can also do a hard pause that stops it immediately.
- **Resume**: Continue from where Copilot Cowork stopped.
- **Cancel**: End the current task entirely.

## What happens if I lose my connection?

Copilot Cowork automatically reconnects and picks up where it left off. Progress made while you were disconnected is preserved, so you don't lose any work.

## Can I use my voice to talk to Copilot Cowork?

Yes. Select the microphone button in the chat input to speak your message. Copilot Cowork transcribes your words and sends them as text.

> [!NOTE]
> Voice input availability depends on your browser. Not all browsers support this feature.

## How do I manage my projects and tasks?

Copilot Cowork gives you the following ways to stay organized:

- **Tasks view**: Show your tasks in a **list** or **kanban board** and track their progress.
- **Projects dashboard**: Browse your **highlights** and **all projects**. Switch between kanban, list, and grid views. Each project shows its current status so you always know where things stand.

Select a project to jump back into the conversation.

## Can I schedule recurring prompts?

Yes. You can schedule a prompt to run at a set time or on a recurring basis — daily, weekly, or as a one-time event. Scheduled prompts are useful for tasks like daily briefings or weekly status reports. You can manage, pause, or cancel scheduled prompts from your task list.

## Where are my files saved?

Files that Copilot Cowork creates are saved to your **OneDrive and SharePoint** workspace. You can browse them in the side panel during a conversation or access them directly in OneDrive at any time.

## Can I download all output files at once?

Yes. When Copilot Cowork produces multiple files, select **Download All** at the top of the output file list to download everything as a single zip archive.

## Can an administrator disable Copilot Cowork?

Yes. Administrators can manage access to Copilot Cowork through the Microsoft 365 admin center:

- **Disable for specific users**: Add users to a security group configured to exclude them from the Copilot experience.
- **Control deployment**: In the Microsoft 365 Apps admin center, administrators can disable automatic installation of the Microsoft 365 Copilot app or manage distribution through Microsoft Intune, Configuration Manager, or Group Policy.
- **Manage agent availability**: Administrators can manage which agents are available to users in their organization through the Copilot settings in the admin center.

For more information, see [Microsoft 365 Copilot admin settings](/microsoft-365-copilot/copilot-for-microsoft-365-admin).

## Is Copilot Cowork secure?

Yes. Every action Copilot Cowork takes is authorized through your Microsoft 365 account. Copilot Cowork accesses only the services and data you're already permitted to use. The agent runs in a secure, isolated environment.

## How do I give feedback?

You can share feedback in the following ways:

- **Thumbs up / thumbs down**: Rate any response from Copilot Cowork directly in the conversation.
- **Document feedback**: When previewing a file Copilot Cowork created, use the feedback controls to rate it.
- **Inline comments**: Leave comments directly on messages in the conversation to provide targeted feedback on specific parts of a response.
- **General feedback**: To share broader thoughts about your experience, open the menu and select the feedback option.

## Can I see where Copilot Cowork gets its information?

Yes. When Copilot Cowork references information in a response, you can open the **Sources** panel to view citations. The panel lists the sources Copilot Cowork used so you can verify the information or explore the original content.

## Does Copilot Cowork ask me questions?

Yes. Sometimes Copilot Cowork needs more information to complete your request. When this happens, it presents a question with a set of choices for you to pick from. You can select an option, type your own answer, or select **Skip** to let Copilot Cowork continue without additional input. The task status shows **Needs user input** when Copilot Cowork is waiting for your answer.

## Does Copilot Cowork connect to external models for processing?

Yes. Copilot Cowork uses Anthropic models as a subprocessor to ensure secure and responsible use of Anthropic models within your organization. Details about the integration can be found at [Anthropic as a subprocessor for Microsoft Online Services](/copilot/microsoft-365/connect-to-ai-subprocessor).

## Related content

- [Copilot Cowork overview](index.md)
- [Get started with Copilot Cowork agent](get-started.md)
- [Use Copilot Cowork agent](use-cowork-agent.md)
