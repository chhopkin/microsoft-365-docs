---
title: "FAQ for the Coworker agent in Microsoft 365 Copilot"
description: "Get answers about how the Coworker agent in Microsoft 365 Copilot uses AI, including its capabilities, limitations, and safeguards."
ms.date: 03/03/2026
ms.topic: faq
ms.custom:
  - responsible-ai-faqs
author: microsoft-coworker-team
ms.author: microsoft-coworker-team
---

# FAQ for the Coworker agent in Microsoft 365 Copilot

An AI system includes not only the technology, but also the people who use it, the people affected by it, and the environment in which it's deployed. Microsoft's Responsible AI FAQs are intended to help you understand how AI technology works, the choices system owners and users can make that influence system performance and behavior, and the importance of thinking about the whole system, including the technology, the people, and the environment. You can use Responsible AI FAQs to better understand specific AI systems and features that Microsoft develops.

Responsible AI FAQs are part of a broader effort to put Microsoft's AI principles into practice. To find out more, see [Microsoft AI principles](https://www.microsoft.com/ai/responsible-ai).

## What is Coworker?

Coworker is an AI agent in Microsoft 365 Copilot that carries out tasks on your behalf across Microsoft 365. You describe what you need in natural language, and Coworker does the work. It takes your written instructions as input and produces concrete outcomes — emails sent through Outlook, meetings scheduled on your calendar, Word documents and PowerPoint presentations created, messages posted in Teams, and search results drawn from across your organization.

Every action Coworker takes is visible in the conversation. Before it performs a sensitive action, such as sending an email or posting a message, it asks for your approval and shows you a preview of the content.

## What are the capabilities of Coworker?

Coworker has 11 skills that cover the tasks information workers perform most often:

- **Calendar Management** — Create, update, and manage calendar events.
- **Daily Briefing** — Prepare a summary of your upcoming meetings, priorities, and action items.
- **Word** — Create and edit Word documents.
- **Email** — Draft, send, reply to, and forward emails through Outlook.
- **Enterprise Search** — Search across your organization for files, people, and information.
- **Meetings** — Generate meeting intelligence summaries, including notes and follow-ups.
- **PDF** — Create and work with PDF files.
- **PowerPoint** — Create PowerPoint presentations.
- **Scheduling** — Find available times and schedule meetings with other people.
- **Communications** — Draft stakeholder communications and status updates.
- **Excel** — Create Excel spreadsheets and work with data.

To carry out these skills, Coworker connects to your Microsoft 365 services:

- **Outlook** — Sends, receives, and manages email.
- **Calendar** — Creates and manages events and meeting invitations.
- **Teams** — Posts messages in channels and chats.
- **Work IQ** — Retrieves workplace intelligence, including information about people, documents, and organizational context.
- **Microsoft 365** — Accesses files, people, and organizational data across your Microsoft 365 environment.
- **Microsoft Learn** — References Microsoft Learn content to provide technical guidance.
- **Web browsing** — Searches the web and retrieves information from web pages to support your requests.

Coworker acquires the specific skills it needs during a conversation based on your request. You can guide the conversation at any point using the **Pause**, **Resume**, and **Cancel** controls.

You can also add work context to your messages. Type **@** to mention a person, or attach files, people, meetings, and channels to give Coworker the information it needs to complete your request. Coworker can browse the web to find current information when your request requires it.

When Coworker creates or modifies files, they appear in a side panel where you can preview and download them. PDF previews support vertical scrolling and in-document search (Ctrl+F). Each step Coworker takes shows its execution time so you can follow its progress.

Before performing an action that affects other people or modifies data, Coworker presents an approval dialog with three options:

- **Approve** — Allow the action this one time.
- **Approve & Remember** — Allow the action and skip the approval prompt for similar actions in the future.
- **Reject** — Block the action.

## What is the intended use of Coworker?

Coworker is designed to help information workers complete everyday tasks across Microsoft 365. Typical use cases include:

- Drafting and sending emails based on natural language instructions.
- Scheduling meetings and resolving calendar conflicts.
- Creating Word documents, Excel spreadsheets, and PowerPoint presentations from unstructured input.
- Posting status updates and messages in Teams channels and chats.
- Searching for files, people, and information across your organization.
- Preparing daily briefings and meeting summaries.

Coworker is designed for use within Microsoft 365 Copilot by licensed users in the Frontier program. It is not intended for use cases that require guaranteed accuracy without human review, such as legal filings, medical decisions, or financial transactions.

## How was Coworker evaluated? What metrics are used to measure performance?

Microsoft evaluates Coworker across the following areas:

- **Task completion accuracy** — Whether Coworker successfully carries out the requested action (for example, an email is sent to the correct recipients, a meeting is scheduled at the right time).
- **Content quality** — Whether the text, documents, and messages Coworker produces match your intent and are factually consistent with the source material.
- **Approval system reliability** — Whether the approval dialog appears correctly before sensitive actions, and whether the Approve, Approve & Remember, and Reject options function as expected.
- **Adherence to responsible AI principles** — Ongoing evaluation to verify that Coworker operates within Microsoft's responsible AI standards, including fairness, reliability, safety, privacy, and transparency.

Testing covers all 11 supported skills and all connected services. User feedback — including thumbs up/down ratings on individual responses, inline comments, and document feedback when previewing files — informs ongoing improvements to Coworker's quality and safety.

## What are the limitations of Coworker? How can users minimize the impact of limitations when using the system?

Coworker has the following known limitations:

1. **Ambiguous instructions** — Coworker may misinterpret ambiguous or overly broad instructions, leading to actions that don't match your intent. To minimize this, provide clear and specific instructions. Include details about recipients, formatting, deadlines, and expected outcomes.

2. **AI-generated content requires review** — All content Coworker produces — emails, documents, messages, and presentations — should be treated as drafts. Review every piece of generated content before you approve sending, posting, or sharing it.

3. **Incomplete search results** — Search results may be incomplete if the source data is outdated, not indexed, or outside the scope of your permissions. Verify important search results against the original source before acting on them.

4. **Complex multi-step tasks** — Tasks with many dependencies or branching conditions may not complete as expected. Break complex work into smaller, focused steps and review progress at each stage.

5. **Permission boundaries** — Coworker can only access data and services that your Microsoft 365 account is authorized to use. If you don't have access to a resource, Coworker can't access it on your behalf.

6. **Voice input** — Voice input is not currently available. Type your instructions directly in the text box.

## What operational factors and settings allow for effective and responsible use of Coworker?

### Approval system

Before Coworker performs a sensitive action, it presents an approval dialog. You have three options:

- **Approve** — Allow the action this one time.
- **Approve & Remember** — Allow the action and skip the prompt for similar actions in the future.
- **Reject** — Block the action.

Actions are classified into three risk levels — Low, Medium, and High — based on their potential impact. For actions that produce content visible to others (such as sending an email or posting a Teams message), Coworker displays a preview so you can review the content before approving.

### Conversation controls

You can manage Coworker's work during a conversation:

- **Pause** — Temporarily stop the agent's progress.
- **Resume** — Continue from where Coworker paused.
- **Cancel** — Stop the current task entirely.

### Data access

Coworker operates within the security and compliance boundaries of Microsoft 365. It uses your existing credentials and can only access services and data that your account is permitted to use. Your data is isolated to your organization's tenant. Coworker does not use your data to train AI models.

### Feedback mechanisms

Your feedback helps improve Coworker over time. For details on how to provide feedback, see [How do I provide feedback on Coworker?](#how-do-i-provide-feedback-on-coworker) below.

## How do I provide feedback on Coworker?

You can share feedback in several ways:

- **Thumbs up or thumbs down** — Rate individual AI responses directly in the conversation.
- **Inline comments** — Provide feedback on specific content within the conversation timeline.
- **Document feedback** — Provide feedback when previewing files that Coworker created or edited.
- **General feedback** — Use the feedback option in the menu to share broader observations about your experience.

Your feedback is used to evaluate and improve Coworker's quality and safety.

## Related content

- [Responsible AI FAQs for the Coworker agent](responsible-ai-overview.md)
- [Coworker overview](overview.md)
- [Get started with Coworker](getting-started.md)
- [Use the Coworker agent](using.md)
- [Coworker FAQ](faq.md)
