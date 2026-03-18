---
title: "Use Cowork agent (Frontier)"
description: "Learn how to have conversations, manage files, approve actions, and organize projects with Cowork agent in Microsoft 365 Copilot."
ms.date: 03/30/2026
ms.topic: how-to
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# Use Cowork agent (Frontier)

[!INCLUDE [preview](../includes/preview.md)]

Cowork agent in Microsoft 365 Copilot carries out tasks on your behalf, such as send emails, create documents, schedule meetings, and search across your organization. This article explains everything you can do with Cowork.

## Start a conversation

The Cowork home page has a chat input where you can type or speak your request. Below it, a list of your recent tasks appears, so you can resume a previous conversation.

### Type a message

1. Go to the Cowork home page. You see a set of suggested prompts such as **Catch me up**, **Organize my inbox**, **Organize my week**, **Prep for a meeting**, **Plan an event**, **Prepare for my 1:1**, and **Research a company**. Select one to get started quickly, or continue with the steps below.
1. Select the chat input field.
1. Type your message or instruction. You can enter up to 16,000 characters.
1. Submit your message by pressing **Enter** or selecting the **Send** button.

### Attach files

To give Cowork extra context, you can include files with your message.

1. Choose how to add files:
   - **Drag and drop** files directly onto the chat input.
   - Select **Upload images and files** to browse your device.
   - Select **Attach cloud files** to pick files from OneDrive, SharePoint, or Teams.
1. Wait for the upload to finish. An animated progress chip for each file displays.
1. Add your message text if needed, then send it.

### Select an agent

Cowork gives you access to specialized agents for different kinds of tasks. To direct your message to a specific agent:

1. Type **@** in the chat input. A list of available agents appears.
1. Select the agent you want. It appears in the input field so you know who you're talking to.
1. Type your message and send it.

### Use voice input

You can also use speech-to-text to dictate your message.

1. Select the microphone button in the chat input area.
1. Speak your message clearly.
1. Review the transcribed text in the input field.
1. Edit the text if needed, then send it.

> [!TIP]
> Check the home page for your recent tasks. Select any task to jump back into that conversation without starting over.

## Follow along as Cowork works

After you send a message, Cowork begins processing your request. You can follow along in real time.

### What displays while Cowork is working

As Cowork works on your request, some things happen on screen:

- **Thinking indicator**: An animation lets you know Cowork is processing your message.
- **Step-by-step updates**: Updates show what Cowork is doing at each stage, such as *Composing your email* or *Searching OneDrive*.
- **Streaming response**: Cowork's reply appears word by word as it generates, so you don't have to wait for the entire response.
- **Interactive cards**: Some responses include interactive cards with structured layouts, buttons, and data displays directly in the conversation.

> [!NOTE]
> Some background operations, like script execution, run without displaying individual steps. This keeps the conversation focused on results.

### Stay informed about your connection

A status indicator shows your connection state:

- **Connecting**: Cowork is getting ready.
- **Connected**: The connection is active.
- **Reconnecting**: The connection dropped briefly. Cowork is working to restore it automatically.
- **Failed**: Something went wrong. Select **Retry** to try connecting again.

### Send messages while Cowork is busy

If you think of something else while Cowork is still working, you can send another message. It's queued automatically. Your message appears above the input field. Cowork processes queued messages in order.

### Answer questions from Cowork

Sometimes Cowork needs more information to complete your request. When this happens, it presents a set of choices for you to pick from.

1. Review the question and the available options.
1. Use the arrow keys to navigate, then press **Space** to select your choice.
1. Select **Submit** to send your answer.

If you'd rather not answer, select **Skip**. Cowork continues with the information it already has.

### If something goes wrong

If a message fails to send, Cowork shows you an error with an option to retry. To resend the message, select **Retry**.

## Approve actions

Before Cowork takes a sensitive action, like sending an email or posting a message in Teams, it asks for your approval first.

### Review and respond to an approval request

1. When you need an approval, a dialog appears with the details of the action Cowork wants to take. For some actions, a rich preview of the content appears (for example, a draft email or a Teams message). For other actions, a summary of what Cowork plans to do appears. Each approval prompt includes a risk level (**Low Risk**, **Medium Risk**, or **High Risk**) so you can gauge the impact before deciding.
1. Choose one of the following options:

   | Option | What it does |
   |---|---|
   | Approve | Allows Cowork to proceed with the action this one time. |
   | Approve & Remember | Allows Cowork to proceed and remembers your choice for similar actions in the current conversation, so you aren't asked again. |
   | Reject | Stops the action. Cowork skips it and moves on with the rest of your request. |

   To see the technical details of the action, select **Show parameters**. Select **Hide parameters** to collapse the view.

> [!IMPORTANT]
> Always review the details before you approve. Cowork shows you exactly what it plans to do. Check that the recipients, content, and other details are correct.

> [!NOTE]
> For certain actions like Outlook mail rules, Cowork presents a detailed approval card that shows exactly what the rule will do before you approve.

## Work with files

Cowork can work with a wide variety of files. You can upload files to provide context, and download files that Cowork creates for you.

### Upload files

1. Drag and drop files onto the chat input area, or select the file picker button to browse your device.
1. Watch the animated progress chips as each file uploads.
1. Once the upload finishes, Cowork can use the file in your conversation.

### Download output files

When Cowork creates or updates files during a conversation, you can grab them from the side panel.

1. Open the side panel if it isn't already visible.
1. Under the **Output folder** section, find the file.
1. To save the file to your device, select **Download**.

> [!TIP]
> When Cowork produces multiple output files, select **Download All** at the top of the output file list to download every file as a single zip archive.

### Supported file types

Cowork supports all the file types you're likely to work with:

| Category | Supported extensions |
|---|---|
| Word | doc, docx, docm, dot, dotx, odt, rtf |
| Excel | csv, xls, xlsm, xlsx, ods |
| PowerPoint | odp, ppt, pptm, pptx |
| PDF | pdf |
| Markdown | md, markdown, mdx |
| Image | png, jpg, jpeg, gif, webp, bmp, svg, ico |
| Text | txt, log |
| Code | js, ts, py, java, c, cpp, go, rb, rs, and others |
| Config | json, yaml, yml, toml, ini, xml, env |
| Notebook | ipynb |
| Audio | mp3, wav, m4a, ogg, aac, flac |
| Video | mp4, mov, avi, mkv, webm, wmv |
| Archive | zip, rar, 7z, tar, gz, bz2 |

## Preview documents

You can preview many file types directly inside Cowork. You don't need to download them first. The preview opens alongside your conversation in a split view.

### Supported preview formats

The following file types can be previewed directly:

- **PDF**: Renders inline with page navigation.
- **CSV**: Displays as a formatted table.
- **Markdown**: Renders with full formatting.
- **Images**: Displays inline (png, jpg, jpeg, gif, webp, bmp, svg, ico).
- **HTML**: Renders in the preview pane.

### Preview a document

1. Select a file from the conversation or from the side panel.

    The preview opens in a split view next to your chat.

1. Use the controls to get the most out of the preview:

   - **Full-screen toggle**: Expand the preview to fill the entire window for a closer look.
   - **Open in native app**: Open the file in its default application on your device.
   - **Feedback buttons**: Rate the document with thumbs up or thumbs down.

## Use the side panel

The side panel is a collapsible sidebar on the right side of your conversation. It gives you a quick overview of what's happening without interrupting your chat.

To open or close it, select the side panel toggle in the conversation view.

### What's in the side panel

| Section | What you find |
|---|---|
| Progress | A progress bar showing the percentage of tasks complete, plus a step-by-step log of what Cowork is doing. |
| Input folder | Files you provided as context for the conversation. |
| Output folder | Files Cowork created. Each file has **Download** and **Preview** buttons. |
| Skills | Skills that Cowork used during the conversation, shown as chips. |

> [!NOTE]
> The side panel updates in real time as Cowork works, so you always have a current view of progress, files, and skills.

### View sources

When Cowork references information in a response, you can open the **Sources** panel to view citations. The panel lists the sources Cowork used so you can verify the information or explore the original content.

1. Select the **Sources** link on a response that includes citations.
1. The **Sources** panel opens alongside the conversation.
1. Select **Close** to dismiss the panel.

## Control the conversation

Cowork provides controls to pause, resume, or stop work at any time.

### Pause

You have two ways to pause:

- **Pause (soft)**: Cowork finishes what it's currently doing, then pauses before starting the next step. Use this when you want to review progress so far.
- **Pause (hard)**: Cowork pauses immediately, including mid-step. Use this when you need to stop now.

### Resume

After pausing, select **Resume** to continue from where Cowork stopped.

### Cancel

To stop Cowork's current work entirely, select **Cancel**. Canceling clears the current task so you can send a new message without needing to resume.

> [!TIP]
> Use **Pause (soft)** when you want to check intermediate results before Cowork continues. Use **Cancel** when you want to change direction entirely.

## Browse and manage projects

The **Projects dashboard** helps you organize and track work across multiple conversations.

### Access the dashboard

1. Select **Tasks** from the main navigation.
1. The dashboard opens with two tabs:
   - **Highlights**: Shows recommended actions and your most recent projects.
   - **All Projects**: Shows every project you have access to.

### Switch between views

Choose the view that works best for you:

| View | Description |
|---|---|
| Kanban board | Organizes projects into columns by status. Drag and drop projects between columns to update their status. |
| List | Shows projects in a vertical list with key details. |
| Grid | Displays projects as cards in a grid layout. |

### Track project and task status

Every project has a status that tells you where things stand:

| Status | Meaning |
|---|---|
| In progress | Work is actively underway. |
| Ready for review | The work is done and needs your review. |
| Done | The project is complete. |

Individual tasks within a project can also show these statuses:

| Status | Meaning |
|---|---|
| In progress | Cowork is actively working on the task. |
| Needs user input | Cowork is waiting for your response before it can continue. |
| Done | The task is finished. |
| Failed | The task didn't complete. Review the conversation for details. |

### Create a new project

When you start a new project, Cowork walks you through setup with a step-by-step progress screen that shows each stage of initialization.

### Open a project or task

Select any project or task card to jump into its conversation and keep working.

## Browse OneDrive files

To pull in the files you need, you can browse your OneDrive files and folders directly from Cowork.

1. From the file selection interface, open the OneDrive file browser.
1. Browse your files and folders in the tree view.
1. Use the breadcrumb trail at the top to navigate, or select a folder to open it.
1. To include a file in your conversation, select it.

> [!NOTE]
> If your files don't load, Cowork shows a **Retry** button. To try again, select it.

## Cowork skills

Cowork comes with a set of built-in skills. These skills are specialized abilities that let it handle different types of tasks. When you ask Cowork to do something, it automatically picks the right skill for the job.

Here's what Cowork can do:

| Skill | What it does |
|---|---|
| Word | Create and edit Word documents. |
| Excel | Create and edit Excel spreadsheets. |
| PowerPoint | Create and edit PowerPoint presentations. |
| PDF | Work with PDF documents. |
| Email | Compose, reply, forward, and send emails. Save drafts and manage attachments. |
| Scheduling | Schedule meetings. |
| Calendar Management | Create events using natural language, add Teams meeting links, and manage your calendar. |
| Meetings | Prepare meeting intelligence. |
| Daily Briefing | Prepare your daily briefing. |
| Enterprise Search | Search across your organization. |
| Deep Research | Conducts in-depth research across multiple sources to compile comprehensive answers and analysis on complex topics. |
| Communications | Draft stakeholder communications. |
| Adaptive Cards | Generates interactive card-based responses with structured layouts, buttons, and data displays in the conversation. |

You can display which skills Cowork used during a conversation in the **Skills** section of the side panel. They appear as chips.

## Schedule prompts

You can schedule a prompt to run automatically at a set time or on a recurring basis. Scheduled prompts are useful for tasks you want Cowork to handle regularly, such as a daily briefing or a weekly status report.

To create a scheduled prompt:

1. Enter your prompt in the message box.
1. Select the **Schedule** option instead of sending the prompt immediately.
1. Choose the frequency (one-time, daily, weekly) and the time.
1. Select **Save** to activate the schedule.

Scheduled prompts appear in the side panel and in your task list with a schedule indicator. You can edit, pause, or cancel a scheduled prompt at any time from the task list.

## Provide feedback

Your feedback helps improve Cowork. You can share it in many ways.

### Rate responses

1. Hover over any response from Cowork in the conversation.
1. Select **thumbs up** if the response was helpful, or **thumbs down** if it wasn't.

### Rate documents

1. Open a document in the preview panel.
1. Use the **thumbs up** or **thumbs down** buttons to rate the quality of the document.

### Leave inline comments

You can leave inline comments directly on messages in the conversation to provide targeted feedback on specific parts of Cowork's response.

### Send general feedback

1. Open the header menu.
1. Select the feedback option.
1. Enter your feedback and submit.

## Keyboard shortcuts

Cowork supports keyboard shortcuts to help you work faster.

1. Select the **Settings** menu in the header.
1. Select **Keyboard shortcuts**.

    A dialog opens showing all available shortcuts and their key combinations.

> [!TIP]
> Take a moment to explore the keyboard shortcuts. They can save you time once you learn the ones you use most.

## Related content

- [Cowork overview](index.md)
- [Get started with Cowork](get-started.md)
- [Cowork agent common questions](cowork-agent-faq.md)
