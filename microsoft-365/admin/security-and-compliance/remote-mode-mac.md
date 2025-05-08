---
title: "Restricted mode settings in the Microsoft 365 admin center"
ms.author: kwekua
author: kwekuako
manager: scotv
ms.date: 05/05/2025
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection: 
- Tier1
- scotvorg
description: "Learn about restricted mode admin settings that will help protect and secure your organization from external threats."
---

# Restricted mode settings

As a Microsoft 365 admin, you want to protect and secure your business environment.

Restricted mode helps you:

- protect business data
- prevent business disruption
- block unsafe end user practices
- secure internal accounts
- ensure secure collaboration

Restricted mode is designed for enterprise customers who want stronger security measures. Restricted Mode covers key Microsoft 365 services, including Microsoft 365 apps, OneDrive, SharePoint, Teams, Exchange and the Microsoft Entra identity platform.

With the addition of Restricted Mode in the Microsoft 365 admin center, you can now set certain security settings that were previously unavailable in the admin center and had to be configured using PowerShell or following customer documentation.

Now that these configurations are available in the admin center, your organization can carefully evaluate each of the settings before deployment.

This article gives you more information about the restricted settings that you turn on and links to content that helps you understand what the setting does and why we recommend that you turn on the setting.

## Before you begin

You must be a global administrator the appropriate admin for the feature area.

## How to get to Restricted mode settings

1. To get to the Restricted mode settings feature, go to the Microsoft 365 admin center and select Org Settings.

1. Select...

## Available Restricted mode settings

### Office settings

|Setting     |More information  |
|---------|---------|
| Open ancient legacy formats in Protected View and disallow editing |When you configure this setting, you...<br/><br/> Learn more. |
|Open old legacy formats in Protected View and allow editing     |<br/><br/> Learn more. |
|Block ActiveX controls (WXPV)     | <br/><br/> Learn more.   |
|Dynamic Data Exchange (DDE) server launch is blocked in Excel |   <br/><br/> Learn more.  |
|Block basic authentication     |   <br/><br/> Learn more.|
|Block FTP protocol for file opens    |   <br/><br/> Learn more. |
|Block HTTP protocol for file opens     |   <br/><br/> Learn more.|
|Block FPRPC protocol for file opens     |   <br/><br/> Learn more.|

### OneDrive and SharePoint settings

|Setting     |More information  |
|---------|---------|
| Block users and apps connecting to ODSP in browser with legacy RPS protocol | <br/><br/> Learn more.|
|Block clients and scripts connecting to ODSP with legacy IDCRL protocol     |   <br/><br/> Learn more.|
|Don't allow new custom scripts in SharePoint sites     |   <br/><br/> Learn more.|
|Disable Access to Microsoft Store for SharePoint     |   <br/><br/> Learn more.|

### Exchange settings

|Setting     |More information  |
|---------|---------|
| Disable tenant-wide access to Exchange web services (EWS) | <br/><br/> Learn more.|

### Identity settings

|Setting     |More information  |
|---------|---------|
| Protect admin access to Microsoft admin portals with phishing resistant authentication | Accounts that are assigned privileged administrative roles are frequent targets of attackers. Requiring phishing-resistant multifactor authentication (MFA) on those accounts is an easy way to reduce the risk of those accounts being compromised.<br/><br/> Learn more.|
|Block legacy authentication flows     | We recommend that organizations block authentication requests that use legacy protocols that don't support multifactor authentication. Based on analysis most of credential stuffing attacks use legacy authentication and the majority of password spray attacks use legacy authentication protocols. You can help stop these attacks with basic authentication disabled or blocked.  <br/><br/> Learn more.|
|Block addition of new password credentials to apps    |   <br/><br/> Learn more.|
|Restrict end-user consent to Microsoft 365 certified and single tenant apps with low risk perms     | Configure user consent settings in Microsoft Entra ID to control when and how users grant permissions to applications. This guidance helps admins reduce security risks by restricting or disabling user consent for apps in Microsoft 365.  <br/><br/> Learn more.|

### Teams devices settings

|Setting     |More information  |
|---------|---------|
| Remove RA access to M365 assets post meeting/collaboration | <br/><br/> Learn more.|
|Only allow endpoint managed, compliant devices to sign in     |   <br/><br/> Learn more.|
|Block resource account sign in to M365 clients     |   <br/><br/> Learn more.|
