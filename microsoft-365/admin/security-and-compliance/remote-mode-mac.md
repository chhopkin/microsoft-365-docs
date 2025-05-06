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

Overview of RM settings

## Before you begin

Prereqs

Perms needed

## How to set RM

Go to the MAC

## RM settings

In the Microsoft 365 admin center, you can go to <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">**Role assignments**</a>, and then select any role to open its detail pane. Select the **Permissions** tab to view the detailed list of what admins assigned that role have permissions to do. Select the **Assigned** or **Assigned admins** tab to add users to roles.


|Setting     |More information  |
|---------|---------|
| AI administrator | Assign the AI Administrator role to users who need to do the following tasks:<br> &bull; Allow users to install an app or install an app for users in the organization if the app does not require permission <br> &bull; Read and configure Azure and Microsoft 365 service health dashboards <br> &bull; View usage reports, adoption insights, and organizational insight <br> &bull; Create and manage support tickets in Azure and the Microsoft 365 admin center<br/> <br/> **Note**: The AI Administrator role is currently limited. For full administrative capabilities, it's recommended to use the Global Admin role until the AI Administrator role is fully functional. We're continuously expanding support for more functionalities to enhance the AI Administrator role.|
|Billing admin     |   Assign the Billing admin role to users who make purchases, manage subscriptions and service requests, and monitor service health. Billing admins cannot assign licenses; If a Billing admin is also a License or User Administrator, visit [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) to assign licenses.<br><br> Billing admins also can:<br> &bull; Manage all aspects of billing<br> &bull; Create and manage support tickets in the Azure portal <br/><br/>|
|Exchange admin     |   Assign the Exchange admin role to users who need to view and manage your user's email mailboxes, Microsoft 365 groups, and Exchange Online. <br><br> Exchange admins can also:<br> &bull; Recover deleted items in a user's mailbox <br> &bull; Set up "Send As" and "Send on behalf" delegates <br>  |
|Fabric admin |   Assign the Fabric admin role to users who need to do the following: <br> &bull; Manage all admin features for Microsoft Fabric and Power BI <br> &bull; Report on usage and performance <br> &bull; Review and manage auditing  |
|Global admin     |   Giving too many users global access is a security risk and we recommend that you have as few global admins as possible. <br/><br/> Only global admins can:<br> &bull; Reset passwords for all users <br> &bull; Add and manage domains <br> &bull; Unblock another global admin <br/><br/> **Note:**   The person who signed up for Microsoft online services automatically becomes a Global admin. Additionally, only Global admins can view and manage subscriptions purchased through a Partner.|
|Global reader    |   Assign the global reader role to users who need to view admin features and settings in admin centers that the global admin can view. The global reader admin can't edit any settings.  <br/><br/> **Note:**   For subscriptions purchased through a partner, global reader role isn't available. |
|Graph data connect admin     |   Assign the Graph data connect admin role to users who need to do the following tasks: <br>&bull; Access the full set of administrative capabilities of Microsoft Graph Data Connect <br> &bull; Manage Microsoft Graph Data Connect settings in a tenant <br> &bull; Enable or disable the Microsoft Graph Data Connect service <br> &bull; Configure dataset workload selections in Microsoft Graph Data Connect <br> &bull; Configure cross-tenant data movement settings in Microsoft Graph Data Connect <br> &bull; View, approve, or deny application authorization requests for Microsoft Graph Data Connect <br> &bull; View, create, update, or delete application registrations for Microsoft Graph Data Connect|
|Groups admin     |   Assign the groups admin role to users who need to manage all groups settings across admin centers, including the Microsoft 365 admin center and Microsoft Entra admin center. <br><br> Groups admins can:<br> &bull; Create, edit, delete, and restore Microsoft 365 groups<br> &bull; Create and update group creation, expiration, and naming policies<br> &bull; Create, edit, delete, and restore Microsoft Entra security groups|
|Helpdesk admin     |   Assign the Helpdesk admin role to users who need to do the following:<br> &bull; Reset passwords <br> &bull; Force users to sign out<br> &bull; Manage service requests<br> &bull; Monitor service health<br/><br/> **Note**: The Helpdesk admin can only help non-admin users and users assigned these roles: Directory reader, Guest inviter, Helpdesk admin, Message center reader, and Reports reader.      |
|License admin    |   Assign the License admin role to users who need to assign and remove licenses from users and edit their usage location. <br/><br/> License admins also can: <br> &bull; Reprocess license assignments for group-based licensing <br> &bull; Assign product licenses to groups for group-based licensing  |
|Message center privacy reader    |   Assign the Message center privacy reader role to users who need to read privacy and security messages and updates in the Microsoft 365 Message center. Message center privacy readers may get email notifications related to data privacy, depending on their preferences, and they can unsubscribe using Message center preferences. Only global administrators and Message center privacy readers can read data privacy messages. This role has no permission to view, create, or manage service requests. <br><br>Message center privacy readers can also: <br> &bull; Monitor all notifications in the Message Center, including data privacy messages<br> &bull; View groups, domains, and subscriptions   |
|Message center reader |   Assign the Message center reader role to users who need to do the following: <br> &bull; Monitor message center notifications<br> &bull; Get weekly email digests of message center posts and updates<br> &bull; Share message center posts<br> &bull; Have read-only access to Microsoft Entra services, such as users and groups|
|Migration admin |   Assign the Microsoft 365 Migration Administrator role to users who need to do the following tasks: <br> &bull; Use Migration Manager in the Microsoft 365 admin center to manage content migration to Microsoft 365, including Teams, OneDrive for Business, and SharePoint sites, from various sources such as Google Drive, Dropbox, and Box.<br> &bull; Select migration sources, create migration inventories (such as Google Drive user lists), schedule and execute migrations, and download reports.<br> &bull; Create new SharePoint sites if the destination sites don't already exist, create SharePoint lists under the SharePoint admin sites, and create and update items in SharePoint lists.<br> &bull; Manage migration project settings and migration lifecycle for tasks as well as manage permission mappings from source to destination.<br><br>**Note:** With this role, you can only migrate from Google Drive, Box, Dropbox and Egnyte. This role doesn't allow you to migrate from file share sources from the SharePoint admin center. Use the SharePoint admin to migrate from file share sources.|
|Office Apps admin    |   Assign the Office Apps admin role to users who need to do the following: <br> &bull; Use the Cloud Policy service for Microsoft 365 to create and manage cloud-based policies.<br> &bull; Create and manage service requests<br> &bull; Manage the What's New content that users see in their apps in Microsoft 365<br> &bull; Monitor service health<br> &bull; Manage Office Scripts settings  |
|Organizational Message Writer    |    Assign the Organizational Message Writer role to users who need to write, publish, manage, and review the organizational messages for end-users through Microsoft product surfaces.   |
|Organizational Messages Approver   |    Assign the Organizational Messages Approver role to users who need to review, approve, or reject new organizational messages for delivery in the Microsoft 365 admin center before they are sent to users through Microsoft product surfaces.  |
|Password admin  |   Assign the Password admin role to a user who needs to reset passwords for non-administrators and Password Administrators.   |
|People admin |   Assign the People administrator role to users who need to do the following tasks: <br> &bull; Update profile photos for all users including administrators<br> &bull; Update people settings for all users (pronouns, name pronunciation, and profile card settings)|
|Power Platform admin |   Assign the Power Platform admin role to users who need to do the following: <br> &bull; Manage all admin features for Power Apps, Power Automate, Power BI, Microsoft Fabric, and Microsoft Purview Data Loss Prevention<br> &bull; Create and manage service requests<br> &bull; Monitor service health  |
|Reports reader |   Assign the Reports reader role to users who need to do the following: <br> &bull; View usage data and the activity reports in the Microsoft 365 admin center<br> &bull; Get access to the Power BI adoption content pack<br> &bull; Get access to sign-in reports and activity in Microsoft Entra ID<br> &bull; View data returned by Microsoft Graph reporting API|
|Search admin |  Assign the Search admin role to users who need to create and manage search result content and define query settings for improved search results within the organization. The Search admin manages the Microsoft search configuration and can perform all the content-management tasks that a Search editor can.|
|Service Support admin   |   Assign the Service Support admin role as an additional role to admins or users who need to do the following in addition to their usual admin role: <br> &bull; Open and manage service requests<br> &bull; View and share message center posts<br> &bull; Monitor service health   |
|SharePoint admin    |   Assign the SharePoint admin role to users who need to access and manage the SharePoint Online admin center. <br><br>SharePoint admins can also: <br> &bull; Create and delete sites<br> &bull; Manage site collections and global SharePoint settings   |
|Teams administrator    |   Assign the Teams administrator role to users who need to access and manage the Teams admin center. <br><br>Teams administrator can also: <br> &bull; Manage meetings<br> &bull; Manage conference bridges<br> &bull; Manage all org-wide settings, including federation, teams upgrade, and teams client settings   |
|User admin     |    Assign the User admin role to users who need to do the following for all users: <br> &bull; Add users and groups<br> &bull; Assign licenses<br> &bull; Manage most users properties<br> &bull; Create and manage user views<br> &bull; Update password expiration policies<br> &bull; Manage service requests<br> &bull; Monitor service health <br><br>  The user admin can also do the following actions for users who aren't admins and for users assigned the following roles: Directory reader, Guest inviter, Helpdesk admin, Message center reader, Reports reader: <br> &bull; Manage usernames<br> &bull; Delete and restore users<br> &bull; Reset passwords<br> &bull; Force users to sign out<br> &bull; Update (FIDO) device keys   |
|User Experience Success Manager     |    Assign the User Experience Success Manager role to users who need to access Experience Insights, Adoption Score, and the Message Center in the Microsoft 365 admin center. This role includes the permissions of the Usage Summary Reports Reader role.    |
