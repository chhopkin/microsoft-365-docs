---
title: "Use the Coworker agent"
description: "Learn how to have conversations, manage files, approve actions, and organize projects with the Coworker agent in Microsoft 365 Copilot."
ms.date: 02/27/2026
ms.topic: how-to
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
appliesto:
- Microsoft 365 Copilot
---

# Use the Coworker agent

The Coworker agent in Microsoft 365 Copilot carries out tasks on your behalf, such as send emails, create documents, schedule meetings, and search across your organization. This article explains everything you can do with Coworker.

## Start a conversation

The Coworker home page has a chat input where you can type or speak your request. Below it, a list of your recent tasks appears, so you can resume a previous conversation.

### Type a message

1. Go to the Coworker home page.
1. Select the chat input field.
1. Type your message or instruction. You can enter up to 16,000 characters.
1. Submit your message by pressing **Enter** or selecting the **Send** button.

### Attach files

To give Coworker extra context, you can include files with your message.

1. Drag and drop files directly onto the chat input. Alternatively, select the file picker button to browse your device.
1. Wait for the upload to finish. An animated progress chip for each file displays.
1. Add your message text if needed, then send it.

### Select an agent

Coworker gives you access to specialized agents for different kinds of tasks. To direct your message to a specific agent:

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

## Follow along as Coworker works

After you send a message, Coworker begins processing your request. You can follow along in real time.

### What displays while Coworker is working

As Coworker works on your request, some things happen on screen:

- **Thinking indicator**: An animation lets you know Coworker is processing your message.
- **Step-by-step updates**: Updates show what Coworker is doing at each stage, such as *Composing your email* or *Searching OneDrive*.
- **Streaming response**: Coworker's reply appears word by word as it generates, so you don't have to wait for the entire response.

### Stay informed about your connection

A status indicator shows your connection state:

- **Connecting**: Coworker is getting ready.
- **Connected**: The connection is active.
- **Reconnecting**: The connection dropped briefly. Coworker is working to restore it automatically.
- **Failed**: Something went wrong. Select **Retry** to try connecting again.

### Send messages while Coworker is busy

If you think of something else while Coworker is still working, you can send another message. It's queued automatically. Your message appears above the input field. Coworker processes queued messages in order.

### If something goes wrong

If a message fails to send, Coworker shows you an error with an option to retry. To resend the message, select **Retry**.

## Approve actions

Before Coworker takes a sensitive action, like sending an email or posting a message in Teams, it asks for your approval first.

### Review and respond to an approval request

1. When you need an approval, a dialog appears with the details of the action Coworker wants to take. For some actions, a rich preview of the content appears (for example, a draft email or a Teams message). For other actions, a summary of what Coworker plans to  appears.
1. Choose one of the following options:

   | Option | What it does |
   |---|---|
   | Approve | Allows Coworker to proceed with the action this one time. |
   | Approve and remember | Allows Coworker to proceed and remembers your choice for similar actions in the future, so you aren't asked again. |
   | Cancel | Stops the action. Coworker skips it and moves on with the rest of your request. |

> [!IMPORTANT]
> Always review the details before you approve. Coworker shows you exactly what it plans to do. Check that the recipients, content, and other details are correct.

## Work with files

Coworker can work with a wide variety of files. You can upload files to provide context, and download files that Coworker creates for you.

### Upload files

1. Drag and drop files onto the chat input area, or select the file picker button to browse your device.
1. Watch the animated progress chips as each file uploads.
1. Once the upload finishes, Coworker can use the file in your conversation.

### Download output files

When Coworker creates or updates files during a conversation, you can grab them from the side panel.

1. Open the side panel if it isn't already visible.
1. Under the **Output** group in the **Files** section, find the file.
1. To save the file to your device, select **Download**.

### Supported file types

Coworker supports all the file types you're likely to work with:

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

You can preview many file types directly inside Coworker. You don't need to download them first. The preview opens alongside your conversation in a split view.

### Supported preview formats

The following file types can be previewed directly:

- **PDF**: Renders inline with page navigation.
- **CSV**: Displays as a formatted table.
- **Markdown**: Renders with full formatting.
- **Images**: Displays inline (png, jpg, jpeg, gif, webp, bmp, svg, ico).
- **HTML**: Renders in the preview pane.

### Preview a document

1. Select a file from the conversation or from the **Files** section in the side panel.

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
| Progress | The current status of your task and a progress indicator showing how far along Coworker is. |
| Files | All files in the conversation, organized into **Input** (files you uploaded) and **Output** (files Coworker created). Each file has **Download** and **Preview** buttons. |
| Skills | Skills that Coworker used during the conversation, shown as chips. |

> [!NOTE]
> The side panel updates in real time as Coworker works, so you always have a current view of progress, files, and skills.

## Control the conversation

Coworker provides controls to pause, resume, or stop work at any time.

### Pause

You have two ways to pause:

- **Pause (soft)**: Coworker finishes what it's currently doing, then pauses before starting the next step. Use this when you want to review progress so far.
- **Pause (hard)**: Coworker pauses immediately, including mid-step. Use this when you need to stop now.

### Resume

After pausing, select **Resume** to continue from where Coworker stopped.

### Cancel

To stop Coworker's current work entirely, select **Cancel**. Canceling clears the current task so you can send a new message without needing to resume.

> [!TIP]
> Use **Pause (soft)** when you want to check intermediate results before Coworker continues. Use **Cancel** when you want to change direction entirely.

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

### Track project status

Every project has a status that tells you where things stand:

| Status | Meaning |
|---|---|
| In progress | Work is actively underway. |
| Ready for review | The work is done and needs your review. |
| Done | The project is complete. |

### Create a new project

When you start a new project, Coworker walks you through setup with a step-by-step progress screen that shows each stage of initialization.

### Open a project or task

Select any project or task card to jump into its conversation and keep working.

## Browse OneDrive files

To pull in the files you need, you can browse your OneDrive files and folders directly from Coworker.

1. From the file selection interface, open the OneDrive file browser.
1. Browse your files and folders in the tree view.
1. Use the breadcrumb trail at the top to navigate, or select a folder to open it.
1. To include a file in your conversation, select it.

> [!NOTE]
> If your files don't load, Coworker shows a **Retry** button. To try again, select it.

## Coworker skills

Coworker comes with a set of built-in skills. These skills are specialized abilities that let it handle different types of tasks. When you ask Coworker to do something, it automatically picks the right skill for the job.

Here's what Coworker can do:

| Skill | What it does |
|---|---|
| Word | Create Word documents. |
| Excel | Create Excel spreadsheets. |
| PowerPoint | Create PowerPoint presentations. |
| PDF | Work with PDF documents. |
| Email | Compose and send emails. |
| Scheduling | Schedule meetings. |
| Calendar | Organize your calendar. |
| Meetings | Prepare meeting intelligence. |
| Daily briefing | Prepare your daily briefing. |
| Enterprise search | Search across your organization. |
| Communications | Draft stakeholder communications. |

You can display which skills Coworker used during a conversation in the **Skills** section of the side panel. They appear as chips.

## Provide feedback

Your feedback helps improve Coworker. You can share it in many ways.

### Rate responses

1. Hover over any response from Coworker in the conversation.
1. Select **thumbs up** if the response was helpful, or **thumbs down** if it wasn't.

### Rate documents

1. Open a document in the preview panel.
1. Use the **thumbs up** or **thumbs down** buttons to rate the quality of the document.

### Send general feedback

1. Open the header menu.
1. Select the feedback option.
1. Enter your feedback and submit.

## Keyboard shortcuts

Coworker supports keyboard shortcuts to help you work faster.

1. Select the **Settings** menu in the header.
1. Select **Keyboard shortcuts**.

    A dialog opens showing all available shortcuts and their key combinations.

> [!TIP]
> Take a moment to explore the keyboard shortcuts. They can save you time once you learn the ones you use most.

## Related content

- [Coworker overview](index.md)
- [Get started with Coworker](get-started.md)
- [Coworker agent FAQ](coworker-agent-faq.md)
