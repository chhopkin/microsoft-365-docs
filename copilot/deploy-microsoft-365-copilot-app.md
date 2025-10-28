---
title: Deployment overview for the Microsoft 365 Copilot app
description: Enterprise and company IT Admins can use this guide to manage the deployment of the Microsoft 365 Copilot app to devices in their organization.
author:      efrene
ms.author:   efrene
ms.service: microsoft-365-copilot
ms.topic: how-to
ms.date:     09/05/2025
manager: scotv
---

# Deployment overview for the Microsoft 365 Copilot app

The Microsoft 365 Copilot app helps Microsoft 365 users be more productive by providing a single place to access [Microsoft 365 Copilot](microsoft-365-copilot-overview.md) features and capabilities, including search, chat, agents, and more.

## Download and install the app on a single device

The app is available as a [web app](https://m365.cloud.microsoft/), as a desktop app that can be installed on [Windows and Mac Devices](https://www.microsoft.com/microsoft-365/copilot/download-copilot-app), and a mobile app for [Android](https://support.microsoft.com/office/microsoft-365-copilot-app-for-android-0383d031-a1c6-46c9-b734-53cd1d22765b) and [iOS](https://support.microsoft.com/office/microsoft-365-copilot-app-for-ios-c8880c05-883a-46b6-ad32-9bffa31228d0) devices.

For organizations that disable access to the Windows Store, the installer can be directly accessed from the Microsoft 365 Content Delivery Network (CDN).

To install on a single computer with many users, follow these steps:

1. Download the [.exe installer](https://go.microsoft.com/fwlink/?linkid=2325486).
2. Launch PowerShell 7 as an administrator: Right-click the PowerShell icon and choose Run as Administrator.
3. Navigate to where the Setup.exe file is located.
4. Run the following command:

   ```powershell
   .\M365CopilotDesktopInstaller.exe --provision true --quiet --start-
   ```

## Deploy the app across your organization using software management tools

To deploy the Microsoft 365 Copilot app to a group of computers, or your entire organization:

1. Download the [.exe installer](https://go.microsoft.com/fwlink/?linkid=2325486).
2. Distribute the installer to your target computers using [Intune](/mem/intune/fundamentals/what-is-intune), [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction), [Group Policy](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software), or non-Microsoft distribution software.
3. Run the installer on each computer.

## Deploy the app automatically with Microsoft 365 Apps

Windows devices with the Microsoft 365 desktop apps will automatically install the Microsoft 365 Copilot app. This app installation takes place in the background and would not disrupt the user. This app installation will start in Fall 2025.
> [!NOTE]
> The installation of the Microsoft 365 Copilot app to devices with Microsoft 365 Apps is not enabled for customers in the European Economic Area (EEA).
> Also, devices on the Semi-Annual Enterprise Channel will not automatically install the Microsoft 365 Copilot app.

### Prevent automatic installation
To prevent the app from installing to devices with existing installations of Microsoft 365 Apps:
1. Sign in to the [Microsoft 365 Apps admin center](https://config.office.com/deploymentsettings) with an admin account.
2. Go to **Customization** > **Device Configuration** > **Modern App Settings**.
3. Select **Microsoft 365 Copilot app**, then clear the **Enable automatic installation of Microsoft 365 Copilot app** check box.



## Updating the Microsoft 365 Copilot app
The Microsoft 365 Copilot app can update automatically through the Microsoft Store as well as its own built-in updater. To ensure reliable app installation and delivery of updates, administrators should allow access to the Microsoft 365 Content Delivery Network (CDN) on the `*.office.net` domain. This domain is used by Microsoft to distribute updates and content more efficiently. For a comprehensive list of Microsoft 365 URLs and IP address ranges, see [Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges). 
