---
title: Manage harmful content protection settings for Microsoft 365 Copilot Chat
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.reviewer: nsiu
ms.date: 09/23/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
- magic-ai-copilot
description: Learn how to set up a policy that enables users to disable harmful content protection in Microsoft 365 Copilot Chat as appropriate.
appliesto:
- ✅ Microsoft 365 Copilot
---

# Mange harmful content protection settings for Microsoft 365 Copilot Chat

Microsoft 365 Copilot uses content filtering to protect users from harmful content in user prompts and generated responses (see [How does Copilot block harmful content?](/copilot/microsoft-365/microsoft-365-copilot-privacy#how-does-copilot-block-harmful-content)). However, in certain use cases, such as in investigation, law enforcement, legal review, or social work scenarios, it's important to have the ability to adjust responsible harmful content protections appropriately. Microsoft is rolling out the ability to adjust harmful content protection settings so that Microsoft 365 Copilot Chat can respond to queries about harmful content when it is fit for purpose.

> [!IMPORTANT]
> Core responsible AI protections, such as prompt injection defense and copyright safeguards are always enforced and cannot be disabled.

## How harmful content protection settings work

When a harmful content protection policy is applied, users have the option to adjust their harmful content protection settings in Microsoft 365 Copilot Chat. The menu includes a **Harmful content protection** setting, as shown in the following screenshot:

:::image type="content" source="media/harmful-content-protection-copilot-chat/copilot-chat-more-menu.png" alt-text="Screenshot showing the More menu in Microsoft 365 Copilot Chat." lightbox="media/harmful-content-protection-copilot-chat/copilot-chat-more-menu.png":::

- By default, the **Harmful content protection** setting is enabled at the beginning of each conversation. 
- When this setting is *enabled*, harmful content is blocked in Microsoft 365 Copilot Chat. 
- When this setting is *disabled*, the user can query on harmful content within the context of that conversation. In this case, the user might see sensitive or potentially offensive content related to their queries.
- Once harmful content protection is disabled in a conversation in Microsoft 365 Copilot Chat, it can't be re-enabled until a new conversation is started. 
- Regardless of whether harmful content protection is enabled or disabled, [Responsible AI governance](https://www.microsoft.com/en-us/ai/principles-and-approach), including prompt injection defense, copyright safeguards, and image protections continue to be enforced.
