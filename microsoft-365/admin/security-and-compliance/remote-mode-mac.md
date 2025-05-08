---
title: "Remote management settings in the Microsoft 365 admin center"
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
description: "Learn about admin settings that will help protect and secure your organization from external threats."
---

# Remote mode settings

As a Microsoft 365 admin, you want to protect and secure your business environment.

Restricted mode helps you:

- protect business data
- prevent business disruption
- block unsafe end user practices
- ensure secure collaboration

Restricted mode is designed for enterprise customers who want stronger security measures. Restricted Mode covers key Microsoft 365 services, including Microsoft 365 apps, OneDrive, SharePoint, Teams, Exchange and the Microsoft Entra identity platform.

With the addition of Restricted Mode in the Microsoft 365 admin center, you can now set certain security settings that were previously unavailable in the admin center and had to be configured using PowerShell or following customer documetation.

Now that these configurations are available in the admin center, your organization can carefully evaluate each of the settings before deployment.

## Before you begin

You must be a global administrator the appropriate admin for the feature area.

## How to get to Remote Settings

1. To get to the Remote Settings feature, go to the Microsoft 365 admin center and select Org Settings.

1. Select...

## Available Remote Settings configurations

### Office settings

|Setting     |More information  |
|---------|---------|
| Open ancient legacy formats in Protected View and disallow editin | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|
|Open old legacy formats in Protected View and allow editing     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Block ActiveX controls (WXPV)     |   Assign the Exchange admin role to users who need to view and manage your user's email mailboxes, Microsoft 365 groups, and Exchange Online. <br><br> Exchange admins can also:<br> &bull; Recover deleted items in a user's mailbox <br> &bull; Set up "Send As" and "Send on behalf" delegates <br>  |
|Dynamic Data Exchange (DDE) server launch is blocked in Excel |   Assign the Fabric admin role to users who need to do the following: <br> &bull; Manage all admin features for Microsoft Fabric and Power BI <br> &bull; Report on usage and performance <br> &bull; Review and manage auditing  |
|Block basic authentication     |   Giving too many users global access is a security risk and we recommend that you have as few global admins as possible. <br/><br/> Only global admins can:<br> &bull; Reset passwords for all users <br> &bull; Add and manage domains <br> &bull; Unblock another global admin <br/><br/> **Note:**   The person who signed up for Microsoft online services automatically becomes a Global admin. Additionally, only Global admins can view and manage subscriptions purchased through a Partner.|
|Block FTP protocol for file opens    |   Assign the global reader role to users who need to view admin features and settings in admin centers that the global admin can view. The global reader admin can't edit any settings.  <br/><br/> **Note:**   For subscriptions purchased through a partner, global reader role isn't available. |
|Block HTTP protocol for file opens     |   Assign the Graph data connect admin role to users who need to do the following tasks: <br>&bull; Access the full set of administrative capabilities of Microsoft Graph Data Connect <br> &bull; Manage Microsoft Graph Data Connect settings in a tenant <br> &bull; Enable or disable the Microsoft Graph Data Connect service <br> &bull; Configure dataset workload selections in Microsoft Graph Data Connect <br> &bull; Configure cross-tenant data movement settings in Microsoft Graph Data Connect <br> &bull; View, approve, or deny application authorization requests for Microsoft Graph Data Connect <br> &bull; View, create, update, or delete application registrations for Microsoft Graph Data Connect|
|Block FPRPC protocol for file opens     |   Assign the groups admin role to users who need to manage all groups settings across admin centers, including the Microsoft 365 admin center and Microsoft Entra admin center. <br><br> Groups admins can:<br> &bull; Create, edit, delete, and restore Microsoft 365 groups<br> &bull; Create and update group creation, expiration, and naming policies<br> &bull; Create, edit, delete, and restore Microsoft Entra security groups|

### OneDrive and SharePoint settings

|Setting     |More information  |
|---------|---------|
| Block users and apps connecting to ODSP in browser with legacy RPS protocol | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|
|Block clients and scripts connecting to ODSP with legacy IDCRL protocol     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Don't allow new custom scripts in SharePoint sites     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Disable Access to Microsoft Store for SharePoint     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|

### Exchange settings

|Setting     |More information  |
|---------|---------|
| Disable tenant-wide access to Exchange web services (EWS) | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|

### Identity settings

|Setting     |More information  |
|---------|---------|
| Protect admin access to Microsoft admin portals with Phishing Resistant authentication | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|
|Block legacy authentication flows     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Block addition of new password credentials to apps    |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Restrict end-user consent to M365 certified and single tenant apps with low risk perms     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|

### Teams devices settings

|Setting     |More information  |
|---------|---------|
| Remove RA access to M365 assets post meeting/collaboration | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|
|Only allow endpoint managed, compliant devices to sign in     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Block resource account sign in to M365 clients     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
