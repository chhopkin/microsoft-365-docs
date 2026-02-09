---  
title: "Block unmanaged devices and resource account sign-ins to Microsoft 365 apps"  
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

This setting prevents unmanaged devices and resource accounts- such as Teams Rooms devices- from signing in to other Microsoft 365 apps. These devices are intended to be used only with the Teams Rooms experience. Allowing them to authenticate to additional apps increases the risk of unauthorized data access and broadens your organization's attack surface.

## Why this setting matters

Teams Rooms devices rely on resource accounts that typically aren't fully managed or monitored like standard user identities. While device compliance policies restrict how these devices access Teams Rooms, users might still attempt to sign in to other Microsoft 365 apps if those apps aren't explicitly blocked. This can expose sensitive data and create an unintended path for unauthorized access. Enforcing this setting ensures that Teams Rooms devices can only sign in to the Teams Rooms app, helping reduce data exposure risks.
For more information, see Block non-compliant Teams rooms devices.
