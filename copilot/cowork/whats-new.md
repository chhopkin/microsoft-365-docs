---
title: "What's new in Copilot Cowork (Frontier)"
description: "Discover the latest features and improvements in Copilot Cowork in Microsoft 365 Copilot."
ms.date: 04/08/2026
ms.topic: whats-new
author: leeclontz
manager: KumarVivek
ms.author: leeclontz
ms.reviewer: angieandrews
ms.service: microsoft-365-copilot
ms.subservice: cowork
ai-usage: ai-assisted
ms.collection: bap-ai-copilot
appliesto:
- Microsoft 365 Copilot
---

# What's new in Copilot Cowork (Frontier)

[!INCLUDE [cowork-top-note](../includes/cowork-top-note.md)]
[!INCLUDE [cowork-preview](../includes/cowork-preview.md)]

This article lists recent features, improvements, and changes in Copilot Cowork. Entries are organized by month, with the most recent updates first. For a full guide to Cowork's capabilities, see [Use Copilot Cowork](use-cowork.md).

## April 2026

### Longer prompts

You can now enter up to **250,000 characters** in the chat input, up from the previous limit of 16,000. This makes it easier to include detailed instructions, long reference material, or large blocks of content in a single message.

### Expandable task list on the home page

The home page now shows an **expandable task list** that replaces the previous static five-item view. You can scroll through all your recent tasks, search for specific tasks by name, and filter by status (**In progress**, **Needs input**, or **Done**). Select **Show more tasks** to expand the list, or **Show fewer tasks** to collapse it.

### Inline file chips on task cards

Output files now appear as compact chips directly on your task cards in the home page task list. If a task produced several files, the first few display inline with a **+N** indicator for the rest. Select a chip to open the file preview.

### Inline email preview

When Cowork references an email in its response, you can select the email chip to open a rich preview in the side panel. The preview shows the sender, recipients, and email body without navigating away from Cowork. This feature works for emails that Cowork reads, drafts, or references while working on your request.

### Office document and code file previews

The file preview panel now supports additional formats:

- **Office documents** — Word, Excel, and PowerPoint files render inline through Office Online.
- **Code files** — JSON, JavaScript, TypeScript, Python, Java, C/C++, C#, Go, Rust, Ruby, PHP, and other languages display with syntax highlighting.

These join the existing preview support for PDFs, images, CSV files, HTML, Markdown, and SVG files. For a complete list, see [Preview files](use-cowork.md#preview-files).

### Improved paste handling

Pasting content from apps like Microsoft Teams, Outlook, or a web browser now works more reliably. When you paste content that includes both text and file attachments, Cowork correctly preserves the text instead of treating it as a file upload.

### Scheduled prompt activation

When you activate a paused scheduled prompt, Cowork now asks whether to **Activate & run now** or just **Activate** so it runs at the next scheduled time. This gives you more control over when the prompt starts. Learn more in [Scheduled prompts](use-cowork.md#scheduled-prompts).

### Richer Teams messages

When Cowork posts messages to Microsoft Teams on your behalf, those messages can now include structured content such as formatted cards with organized data. This results in cleaner, more readable posts compared to plain text.

### Smarter calendar management

Cowork now checks your calendar for existing events before creating new ones, which helps prevent duplicates. Calendar queries also include attendee information by default, so Cowork can give you better context about who's in a meeting when summarizing your schedule or preparing for upcoming events.

### Calendar timezone display

Calendar event times in Cowork's responses now show in your local timezone with a timezone abbreviation, making it easier to confirm timing at a glance.

### Reconnect and resume

If your browser connection drops while Cowork is working, you can return and pick up where you left off. Cowork preserves the session state, so it doesn't need to start over. Any work that was in progress continues, and completed steps aren't repeated.

### Bulk download limits

When you download multiple files that Cowork created, downloads are capped at **50 files** and **500 MB** (uncompressed) per batch. If your request exceeds these limits, Cowork lets you know so you can download files in smaller groups.

## Related content

- [Copilot Cowork overview](index.md)
- [Get started with Copilot Cowork](get-started.md)
- [Use Copilot Cowork](use-cowork.md)
- [Copilot Cowork common questions](cowork-faq.md)
