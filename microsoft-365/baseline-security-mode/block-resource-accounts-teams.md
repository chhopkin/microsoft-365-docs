---  
title: "Block resource accounts on Teams Rooms devices from accessing Microsoft 365 apps"  
description: Use the Microsoft 365 admin center, to prevent unmanaged devices and resource accounts to sign in to Microsoft 365 apps.
author: vpattnai
ms.author: vpattnaik
manager: dansimp
ms.date: 02/09/2026
ms.topic: how-to
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: RestrictedMode
ms.custom: QuickDraft
ms.reviewer: dansimp
audience: admin
ai-usage: ai-assisted 
ROBOTS: NOINDEX, NOFOLLOW
---

# Overview

This setting prevents shared resource accounts on Teams Rooms devices from accessing Microsoft 365 files- such as those stored in OneDrive or SharePoint- outside of their intended meeting scenarios. Without this restriction, a Teams Rooms device could retain access before or after meetings, increasing the risk of unauthorized data exposure.

## Why this setting matters

Teams Rooms devices typically use resource accounts that aren't tied to a single user and may not be governed by the same controls as standard user accounts. When these accounts can access Microsoft 365 files, they might unintentionally retain access to documents beyond a meeting, or gain access to files not meant for shared devices. This creates data leakage risks, especially in environments where multiple users interact with the same meeting room device. Enforcing this setting ensures that Teams Rooms devices have only the access required for their meeting functionality and nothing more.

For more information, see Block resource accounts on Teams Rooms devices from accessing Microsoft 365 files.
