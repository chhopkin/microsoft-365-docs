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

# Manage harmful content protection settings for Microsoft 365 Copilot Chat

Microsoft 365 Copilot uses content filtering to protect users from harmful content in user prompts and generated responses (see [How does Copilot block harmful content?](/copilot/microsoft-365/microsoft-365-copilot-privacy#how-does-copilot-block-harmful-content)). However, in certain use cases, such as in investigation, law enforcement, legal review, or social work scenarios, it's important to have the ability to adjust responsible harmful content protections appropriately. Microsoft is rolling out the ability to adjust harmful content protection settings so that Microsoft 365 Copilot Chat can respond to queries about harmful content when it's fit for purpose.

> [!IMPORTANT]
> Core responsible AI protections, such as prompt injection defense, copyright safeguards, and image protections are always enforced and can't be disabled.

## How harmful content protection settings work

When a harmful content protection policy is applied, users can adjust their harmful content protection settings in Microsoft 365 Copilot Chat. The menu includes a **Harmful content protection** setting, as shown in the following screenshot:

:::image type="content" source="media/harmful-content-protection-copilot-chat/copilot-chat-more-menu.png" alt-text="Screenshot showing the More menu in Microsoft 365 Copilot Chat." lightbox="media/harmful-content-protection-copilot-chat/copilot-chat-more-menu.png":::

- By default, the **Harmful content protection** setting is enabled at the beginning of each conversation. 
- When this setting is *enabled*, harmful content is blocked in Microsoft 365 Copilot Chat. 
- When this setting is *disabled*, the user can query on harmful content within the context of that conversation. In this case, the user might see sensitive or potentially offensive content related to their queries.
- Once harmful content protection is disabled in a conversation in Microsoft 365 Copilot Chat, it can't be re-enabled until a new conversation is started. 
- Regardless of whether harmful content protection is enabled or disabled, [Responsible AI governance](https://www.microsoft.com/en-us/ai/principles-and-approach), including prompt injection defense, copyright safeguards, and image protections continue to be enforced.
- Harmful content protection settings don't affect images or agents.

## How to configure harmful content protection settings

1. Set up a security group in Microsoft Entra ID. See [Learn about group types, membership types, and access management](/entra/fundamentals/concept-learn-about-groups).

2. As an AI Administrator, sign into the Microsoft 365 Apps admin center.

3. In the navigation pane, select **Customization**.

   :::image type="content" source="media/harmful-content-protection-copilot-chat/microsoft-365-apps-admin-center-customization.png" alt-text="Screenshot showing the Customization section in the Microsoft 365 App admin center." lightbox="media/harmful-content-protection-copilot-chat/microsoft-365-apps-admin-center-customization.png":::

4. Create or edit a policy configuration for **Adjust responsible AI protections for Microsoft 365 Copilot**. 

   :::image type="content" source="media/harmful-content-protection-copilot-chat/adjust-responsible-ai-protections.png" alt-text="Screenshot showing the Adjust responsible AI protections flyout pane." lightbox="media/harmful-content-protection-copilot-chat/adjust-responsible-ai-protections.png":::

4. In the flyout pane, specify your configuration settings as follows:

   :::image type="content" source="media/harmful-content-protection-copilot-chat/adjust-responsible-ai-protections-options.png" alt-text="Screenshot showing configuration options for the Adjust responsible AI protections policy." lightbox="media/harmful-content-protection-copilot-chat/adjust-responsible-ai-protections-options.png":::

   1. Under **Configuration setting**, select **Enabled**.

   2. Under **Options**, select an option, such as **Provide users with the option to adjust harmful content protection**.

   3. Select **Apply**.

5. Apply your policy to the security group you created in Step 1 and save your changes.

When the policy takes effect, users have the **Harmful content protection** toggle in Microsoft 365 Copilot Chat. [Learn more about the user experience](https://support.microsoft.com/en-us/topic/605db862-b859-4ec3-9327-d405cc164690).

> [!NOTE]
> Harmful content protection settings don't affect images or agents.

## Best practices and important points

- We recommend defining a security group in Microsoft Entra ID for your harmful content protection policies. Only include users who will use this feature when it's fit for purpose, such as when doing investigative work in law enforcement, legal, or social work scenarios. Not everyone in your organization needs to turn off harmful content protection.
- Let users know how the feature works and when to use it. For more information about the user experience, see [Using the harmful content protection toggle in Microsoft 365 Copilot Chat](https://support.microsoft.com/en-us/topic/605db862-b859-4ec3-9327-d405cc164690).

## Related articles

- [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md)
- [Security for Microsoft 365 Copilot](microsoft-365-copilot-ai-security.md)
- [Transparency Note for Microsoft 365 Copilot](microsoft-365-copilot-transparency-note.md)
