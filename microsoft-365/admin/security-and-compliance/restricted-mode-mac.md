---
title: "Baseline Security Mode settings"
ms.author: kwekua
author: kwekuako
manager: scotv
ms.date: 06/25/2025
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection: RestrictedMode
description: "Learn about Baseline Security Mode settings that will help protect and secure your organization from external threats."
ROBOTS: NOINDEX, NOFOLLOW
---

# Baseline Security Mode settings in the Microsoft 365 admin center

As a Microsoft 365 admin, you want to protect and secure your business environment.

Baseline Security Mode helps you:

- protect business data
- prevent business disruption
- block unsafe end user practices
- secure internal accounts
- ensure secure collaboration

Baseline Security Mode covers key Microsoft 365 services, including Microsoft 365 apps, OneDrive, SharePoint, Teams, Exchange and the Microsoft Entra identity platform.

With the addition of Baseline Security Mode in the Microsoft 365 admin center, you can now set certain security settings that were previously unavailable in the admin center and had to be configured using PowerShell or following customer documentation.

Now that these settings are available in the admin center, your organization can carefully evaluate each of the Baseline Security Mode settings before deployment.

This article gives you information about the Baseline Security Mode settings that you can turn on. It also has links to content that helps you understand what the setting does and why we recommend you turn on the setting.

## Before you begin

You must be the appropriate admin for the feature area. For more information, see [About admin roles in the Microsoft 365 admin center](../add-users/about-admin-roles.md).

## How to get to Baseline Security Mode settings

1. To get to Baseline Security Mode settings, go to the Microsoft 365 admin center and select **Settings** > **Org Settings**, then go to the **Security & privacy** tab.
1. Select **Baseline Security Mode**.

## Available Baseline Security Mode settings

### Microsoft 365 apps settings

This section outlines the options available within Microsoft 365 Apps to apply Baseline Security Mode settings in the Microsoft 365 admin center.

You must be a member of the [Office Apps administrator role](/entra/identity/role-based-access-control/permissions-reference) to perform these tasks.

> [!NOTE]
> The version number for Microsoft 365 apps client support for Baseline Security Mode settings will be 2508. For more information, see [Minimum Version Requirements for Baseline Security Mode](minimum-version-numbers-office.md).

|Setting     |More information  |
|---------|---------|
| Open ancient legacy formats in Protected View and disallow editing |Ancient legacy file formats in Microsoft 365 apps (formerly Office) are particularly vulnerable to memory corruption. When users open these outdated formats in Protected View with editing disabled, you prevent potential exploits while still allowing users to view the content without risk. <br/><br/> For more information, see [Open ancient legacy formats in Protected View and disallow editing](open-ancient-legacy-formats-protected-view-disallow-editing.md). |
|Open old legacy formats in Protected View and allow editing     |Many legacy file formats in Microsoft 365 apps (such as older Word, Excel, and PowerPoint files) are prone to memory corruption vulnerabilities. By opening legacy formats in Protected View, you can minimize the risk of malicious code execution, while still allowing users to edit their content safely. <br/><br/> For more information, see [Open old legacy formats in Protected View and disallow editing](open-old-legacy-formats-protected-view-disallow-editing.md). |
|Block ActiveX controls |ActiveX controls are small programs used to add interactive features to Microsoft 365 documents and web pages. They are highly vulnerable to exploitation. Malicious actors often use ActiveX to run harmful code, install malware, or take control of a system, especially when users open compromised files or visit unsafe websites. Because of their history of security issues and declining usage, ActiveX is now blocked by default in Microsoft 365 apps. Enforcing this setting ensures users in your environment can't override the default configuration. <br/><br/> For more information, see [Block ActiveX controls in Microsoft 365 apps documents](block-activex-controls.md).   |
|Dynamic Data Exchange (DDE) server launches are blocked in Excel | Dynamic Data Exchange (DDE) allows Excel to pull data from external sources in real time. However, if the source is malicious, it can send harmful code to Excel and potentially compromise the system—without requiring macros or other active content. Attackers have used this technique in targeted phishing attacks to execute arbitrary commands. Blocking DDE server launch reduces this risk. When you enable this setting, Excel will block DDE server launches, helping prevent malicious external sources from injecting harmful code into spreadsheets.  <br/><br/> For more information, see [Block Dynamic Data Exchange (DDE) server launches in Excel](block-dde-server-launches-excel.md). |
|Block OLE graph and OrgChart objects | Block OLE Graph and OrgChart objects. When you turn on this setting, Microsoft 365 apps will block loading OLE Graph and OrgChart objects to protect users from known exploitation techniques.  <br/><br/> For more information, see [Block OLE Graph and OrgChart objects](block-ole-graph-org-chart-objects.md). |
|Block Microsoft Publisher | Publisher has a large attack surface and will no longer be included in Microsoft 365 starting in October 2026. Blocking Publisher now reduces security risk and aligns with Microsoft’s support strategy. When you enable this setting, Microsoft Publisher will not launch.  <br/><br/> For more information, see [Block Microsoft Publisher](block-microsoft-publisher.md). |
|Block basic authentication     | Basic authentication is an outdated and insecure method that transmits user credentials in a way that can easily be intercepted and stolen. Whey you block basic authentication prompts, this helps protect your users from credential theft, especially during phishing attacks or when accessing services over insecure networks. When you enable this setting, users will no longer see prompts for basic authentication. This reduces the risk of credential theft and enforces more secure authentication methods. <br/><br/> For more information, see [Block basic authentication in Microsoft 365 apps](block-basic-authentication.md).|
|Block insecure protocols for file opens    | When users open files from locations using insecure protocols like HTTP or FTP, sensitive data can be exposed because these protocols transmit information in plain text. Blocking these protocols helps prevent attackers from intercepting credentials or other confidential data during file access. When you enable this setting, users will be prevented from opening files from locations that use HTTP or FTP. This helps enforce secure data transmission practices and reduces exposure to man-in-the-middle attacks. <br/><br/> For more information, see [Block insecure protocols for file opens](block-insecure-protocols-file-opens.md). |
|Block FrontPage Remote Procedure Call (FPRPC) protocol for file opens     | FrontPage Remote Procedure Call (FPRPC) is an outdated protocol that was used for remote web page authoring. While no longer widely used, FPRPC can still be exploited by attackers to execute arbitrary commands or compromise a system through specially crafted files or network traffic. FPRPC is now blocked by default in Microsoft 365 apps in favor of HTTPS. Enabling this setting ensures users in your environment can't override the default configuration.   <br/><br/> For more information, see [Block FrontPage Server Extensions Remote Procedure Call (FPRPC) for file opens in Microsoft 365](block-fprpc-protocol-file-opens.md).|

### OneDrive and SharePoint settings

This section outlines the options available within OneDrive and SharePoint to turn off Baseline Security Mode settings in the Microsoft 365 admin center.

You must be a member of the [SharePoint administrator role](/sharepoint/sharepoint-admin-role) to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Block legacy browser authentication connections to SharePoint with legacy Relying Party suite (RPS) protocol | Legacy protocols are more susceptible to brute-force and phishing attacks because they use non-modern authentication methods. Microsoft reports that organizations that disable legacy authentication experience fewer account compromises. Enforcing this setting prevents applications, (including third party applications) using non-modern authentication protocols from accessing SharePoint and OneDrive resources in a browser. <br/><br/> Reporting on this setting shows which users are accessing SharePoint or OneDrive with RPS authentication. The report also lets you know the date and time, and which SharePoint site or OneDrive file or folder they accessed.  <br/><br/>**Note** The change isn't instant. It might take up to 24 hours to be applied. <br/><br/> For more information, see [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps)|
|Block legacy client authentication connections to SharePoint and OneDrive with legacy Identity Client Runtime Library (IDCRL) protocol     | Legacy protocols are more susceptible to brute-force and phishing attacks because they non-modern authentication methods. Microsoft reports that organizations that disable legacy authentication experience fewer account compromises. Enforcing this setting prevents clients using non-modern authentication protocols from accessing SharePoint Online and OneDrive resources.  <br/><br/>Reporting on this setting shows which users are accessing SharePoint with IDCRL authentication. The reports also lets you know the date and time, and which SharePoint site or OneDrive file or folder they accessed. <br/><br/>**Note** The change isn't instant. It might take up to 24 hours to be applied. <br/><br/>  For more information, see [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps).|
|Don't allow new custom scripts in SharePoint sites | Custom scripts are used to modify SharePoint site behaviors. When you allow users to run custom script, you can no longer enforce governance, scope the capabilities of inserted code, block specific parts of code, or block all custom code that has been deployed. This setting permanently removes the ability to add new custom scripts in OneDrive and SharePoint sites. Instead of allowing custom script, we recommend using the [SharePoint Framework](/sharepoint/dev/spfx/sharepoint-framework-overview). <br/><br/>  For more information, see [Allow or prevent custom script](/sharepoint/allow-or-prevent-custom-script). |
|Disable Access to Microsoft Store for SharePoint     | Certain applications from the Microsoft Store can be installed by end users. Sometimes, this can go against organizational policies and can increase governance costs. This setting will remove the ability for end users to install applications directly from the Microsoft Store.  <br/><br/> For more information, see [Configure settings for the SharePoint store](/sharepoint/configure-sharepoint-store-settings)|

### Exchange settings

This section outlines the options available within Exchange to turn off Baseline Security Mode settings in the Exchange admin center.

You must be a member of the [Exchange online administrator role](../add-users/about-exchange-online-admin-role.md) to perform this task.

|Setting     |More information  |
|---------|---------|
| Disable tenant-wide access to Exchange web services (EWS) |Exchange web services (EWS) provides cross-platform API access to sensitive Exchange Online data like emails, meetings, and contacts. If compromised, attackers can access confidential data, send phishing emails, spoof identities and potentially gain system control. When you disable access to EWS, you also reduce legacy app usage and minimize the number of endpoints that attackers can target.  <br/><br/> For more information, see [Control access to EWS](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)|

#### Requirements

Before you can disable EWS, make sure that you meet these requirements:

- Current Channel (CC): will require the CC July 2025 Fork. This will be shipped end of August 2025.
- For Monthly Enterprise Channel (MEC): will require the MEC July 2025  Fork. This will be shipped in November 2025.
- For Semi Annual Channel (SAC): will require the SAC July 2025 Fork. This will be shipped on January 2026.

> [!NOTE]
> These statements and build requirements are Win32 only.

#### Impact of Baseline Security Mode settings on cross-tenant features

Currently the following features will not work when Baseline Security Mode settings are enabled:

- Calendar sharing and Free/Busy (cross-tenant/cloud)
- MailTips (cross-tenant/cloud)
- User photo and profile (cross-tenant/cloud)

### Identity settings

This section outlines the options available within Identity to turn off Baseline Security Mode settings in the Microsoft 365 admin center.

|Setting     |More information  |
|---------|---------|
| Protect admin access to Microsoft admin portals with phishing resistant authentication | Accounts that are assigned privileged administrative roles are frequent targets of attackers. Requiring phishing-resistant multifactor authentication (MFA) on those accounts is an easy way to reduce the risk of those accounts being compromised.<br/><br/> For more information, see [Require phishing-resistant multifactor authentication for administrators](/entra/identity/conditional-access/policy-admin-phish-resistant-mfa) <br/><br/> You must be a member of the [Security administrator](/entra/identity/role-based-access-control/permissions-reference) or the [Conditional access administrator](/entra/identity/role-based-access-control/permissions-reference) roles to perform this task.|
|Block legacy authentication flows     | We recommend that organizations block authentication requests that use legacy protocols that don't support multifactor authentication. Based on analysis, most credential stuffing attacks use legacy authentication and the majority of password spray attacks use legacy authentication protocols. You can help stop these attacks with basic authentication disabled or blocked.  <br/><br/> For more information, see [Block legacy authentication with Conditional Access](/entra/identity/conditional-access/policy-block-legacy-authentication) <br/><br/> You must be a member of the [Security administrator](/entra/identity/role-based-access-control/permissions-reference) or the [Conditional access administrator](/entra/identity/role-based-access-control/permissions-reference) roles to perform this task.|
|Block addition of new password credentials to apps    | To increase security, we recommend that organizations block the addition of password credentials on their applications.  Passwords are one of the weakest methods of service authentication and are vulnerable to compromise by bad actors. Switching to a more secure method improves security and reduces management overhead.  <br/><br/> For more information, see [Restrict password usage on Microsoft Entra apps](/entra/identity/enterprise-apps/block-password-addition?branch=pr-en-us-9434). <br/><br/> You must be a member of the [Security administrator](/entra/identity/role-based-access-control/permissions-reference), [Application administrator](/entra/identity/role-based-access-control/permissions-reference) or the [Cloud Application administrator](/entra/identity/role-based-access-control/permissions-reference) roles to perform this task.|
|Restrict end-user consent to Microsoft 365 certified and single tenant apps with low risk permissions     | Update your Entra user consent settings to restrict users to grant access to applications created in your tenant or from the [Microsoft 365 certified list](/microsoft-365-app-certification/saas/saas-apps). Microsoft works with our Microsoft 365 developer partners to provide this information so organizations can expedite and inform decisions about apps and add-ins their users can use. <br/><br/> For more information, see [Configure how users consent to applications](/entra/identity/enterprise-apps/configure-user-consent?pivots=portal) <br/><br/> You must be a member of the [Security administrator](/entra/identity/role-based-access-control/permissions-reference) or the [Privileged role administrator](/entra/identity/role-based-access-control/permissions-reference) roles to perform this task.|

### Teams devices settings

This section outlines the options available within Teams to turn off Baseline Security Mode settings in the Microsoft 365 admin center.

You must be a member of the [Teams administrator role](/entra/identity/role-based-access-control/permissions-reference) to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Restrict resource account access to Microsoft 365 assets post meeting and collaboration | To increase security, we recommend you remove resource accounts access that are used by Teams Rooms and devices to access Microsoft 365 assets used for meeting and collaboration. <br/><br/> For more information, see [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant).|
|Only allow endpoint managed, compliant devices to sign in     |To increase security, we recommend that only compliant, organization-managed Teams Room devices can sign in to Microsoft 365 applications and that resource accounts can't be misused to authenticate from unmanaged devices. <br/><br/> For more information, see [Block Teams resource account sign in to Microsoft 365 clients](/MicrosoftTeams/rooms/block-non-compliant-teams-rooms-devices?branch=kwekua-restricted-mode-teams).|
|Block resource account sign in to Microsoft 365 clients     |To increase security, resource accounts used for Teams devices must be blocked from being used to sign in or used by Microsoft 365 clients. <br/><br/> For more information, see [Block Teams resource account sign in to Microsoft 365 clients](/MicrosoftTeams/rooms/block-non-compliant-teams-rooms-devices?branch=kwekua-restricted-mode-teams).|
