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

You must be a global administrator or the appropriate admin for the feature area.

## How to get to Restricted mode settings

1. To get to the Restricted mode settings feature, go to the Microsoft 365 admin center and select Org Settings.

1. Select...

## Available Restricted mode settings

### Microsoft 365 apps settings

You must be the appropriate admin to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Open legacy formats in Protected View and disallow editing |Ancient legacy file formats in Microsoft 365 apps (formerly Office) are particularly vulnerable to memory corruption. When users open these outdated formats in Protected View with editing disabled, you prevent potential exploits while still allowing users to view the content without risk. <br/><br/> Learn more |
|Open legacy formats in Protected View and allow editing     |Many legacy file formats in Microsoft 365 apps (such as older Word, Excel, and PowerPoint files) are prone to memory corruption vulnerabilities. By opening legacy formats in Protected View, you can minimize the risk of malicious code execution, while still allowing users to edit their content safely. <br/><br/> Learn more |
|Block ActiveX controls (WXPV)     |ActiveX controls are small programs used to add interactive features to Microsoft 365 documents and web pages. They are highly vulnerable to exploitation. Malicious actors often use ActiveX to run harmful code, install malware, or take control of a system, especially when users open compromised files or visit unsafe websites. Because of their history of security issues and declining usage, ActiveX is now blocked by default in Microsoft 365 apps. Enforcing this setting ensures users in your environment can't override the default configuration. <br/><br/> [Learn more](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/activex-disabled-by-default-in-microsoft-365/4403157)   |
|Dynamic Data Exchange (DDE) server launch is blocked in Excel | Dynamic Data Exchange (DDE) allows Excel to pull data from external sources in real time. However, if the source is malicious, it can send harmful code to Excel and potentially compromise the system—without requiring macros or other active content. Attackers have used this technique in targeted phishing attacks to execute arbitrary commands. Blocking DDE server launch reduces this risk. When you enable this setting, Excel will block DDE server launches, helping prevent malicious external sources from injecting harmful code into spreadsheets.  <br/><br/> [Learn more](/office/troubleshoot/excel/security-settings)  |
|Block basic authentication     | Basic authentication is an outdated and insecure method that transmits user credentials in a way that can easily be intercepted and stolen. Whey you block basic authentication prompts, this helps protect your users from credential theft, especially during phishing attacks or when accessing services over insecure networks. When you enable this setting, users will no longer see prompts for basic authentication. This reduces the risk of credential theft and enforces more secure authentication methods. <br/><br/> [Learn more](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)|
|Block insecure protocols for file opens    | When users open files from locations using insecure protocols like HTTP or FTP, sensitive data can be exposed because these protocols transmit information in plain text. Blocking these protocols helps prevent attackers from intercepting credentials or other confidential data during file access. When you enable this setting, users will be prevented from opening files from locations that use HTTP or FTP. This helps enforce secure data transmission practices and reduces exposure to man-in-the-middle attacks. <br/><br/> [Learn more](/defender-office-365/tenant-allow-block-list-urls-configure) |
|Block FPRPC protocol for file opens     | FrontPage Remote Procedure Call (FPRPC) is an outdated protocol once used for remote web page authoring. While no longer widely used, FPRPC can still be exploited by attackers to execute arbitrary commands or compromise a system through specially crafted files or network traffic. Blocking FPRPC helps reduce exposure to these types of vulnerabilities. When you enable this setting, FPRPC will be blocked for opening files, preventing the use of this outdated and insecure protocol. This helps secure your environment from potential attacks targeting legacy protocols.  <br/><br/> [Learn more](/defender-endpoint/web-content-filtering)|

### OneDrive and SharePoint settings

You must be the appropriate admin to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Block users and apps connecting to ODSP in browser with legacy RPS protocol | <br/><br/> Learn more|
|Block clients and scripts connecting to ODSP with legacy IDCRL protocol     |   <br/><br/> Learn more.|
|Don't allow new custom scripts in SharePoint sites | Custom scripts are used to modify SharePoint site behaviors. When you allow users to run custom script, you can no longer enforce governance, scope the capabilities of inserted code, block specific parts of code, or block all custom code that has been deployed. This setting permanently removes the ability to add new custom scripts in OneDrive and SharePoint sites. Instead of allowing custom script, we recommend using the SharePoint Framework. <br/><br/>  [Learn more](/sharepoint/security-considerations-of-allowing-custom-script)|
|Disable Access to Microsoft Store for SharePoint     | When users install unsupported or unauthorized apps from the Microsoft Store for SharePoint, they could install apps that bypass your organization's policies or introduce security vulnerabilities. There could also be costs associated with these apps. When you enable this setting, users will be prevented from installing apps from the Microsoft Store for SharePoint unless you allow them access.  <br/><br/> Learn more|

### Exchange settings

You must be the appropriate admin to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Disable tenant-wide access to Exchange web services (EWS) |Exchange web services (EWS) provides cross-platform API access to sensitive Exchange Online data like emails, meetings, and contacts. If compromised, attackers can access confidential data, send phishing emails, spoof identities and potentially gain system control. When you disable access to EWS, you enforce modern authentication and conditional access policies. You also reduce legacy app usage and minimize the number of endpoints that attackers can target.  <br/><br/> [Learn more](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)|

### Identity settings

You must be the appropriate admin to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Protect admin access to Microsoft admin portals with phishing resistant authentication | Accounts that are assigned privileged administrative roles are frequent targets of attackers. Requiring phishing-resistant multifactor authentication (MFA) on those accounts is an easy way to reduce the risk of those accounts being compromised.<br/><br/> [Learn more](/entra/identity/conditional-access/policy-admin-phish-resistant-mfa)|
|Block legacy authentication flows     | We recommend that organizations block authentication requests that use legacy protocols that don't support multifactor authentication. Based on analysis most of credential stuffing attacks use legacy authentication and the majority of password spray attacks use legacy authentication protocols. You can help stop these attacks with basic authentication disabled or blocked.  <br/><br/> [Learn more](/entra/identity/conditional-access/policy-block-legacy-authentication)|
|Block addition of new password credentials to apps    |   <br/><br/> Learn more.|
|Restrict end-user consent to Microsoft 365 certified and single tenant apps with low risk perms     | Configure user consent settings in Microsoft Entra ID to control when and how users grant permissions to applications. This guidance helps admins reduce security risks by restricting or disabling user consent for apps in Microsoft 365.  <br/><br/> [Learn more](/entra/identity/enterprise-apps/configure-user-consent?pivots=portal)|

### Teams devices settings

You must be the appropriate admin to perform these tasks.

|Setting     |More information  |
|---------|---------|
| Remove RA access to Microsoft 365 assets post meeting/collaboration | To increase security, we recommend you remove resource accounts access that are used by Teams Rooms and devices to access Microsoft 365 assets used for meeting and collaboration. <br/><br/> Learn more|
|Only allow endpoint managed, compliant devices to sign in     |To increase security, we recommend that only compliant, organization-managed Teams Room devices can sign in to Microsoft 365 applications and that resource accounts can't be misused to authenticate from unmanaged devices.   <br/><br/> Learn more|
|Block resource account sign in to M365 clients     |To increase security, resource accounts used for Teams devices must be blocked from being used to sign in or used by Microsoft 365 clients.   <br/><br/> Learn more|
