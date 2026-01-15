---
title: Set up or disconnect pay-as-you-go billing for services in the Billing node of the Microsoft 365 admin center
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: clalissayi
audience: admin
ms.topic: install-set-up-deploy
ms.service: microsoft-365-admin
ms.subservice:
search.appverid: MET150
ms.collection: 
ms.custom: 
ms.localizationpriority:  medium
description: "Learn how to set up or disconnect pay-as-you-go billing in the Billing node of the  Microsoft 365 admin center."
ms.date: 11/25/2025
---

# Set up or disconnect pay-as-you-go in the Billing node of the Microsoft 365 admin center

This article explains how to set up or disconnect pay-as-you-go billing in the Microsoft 365 admin center **Billing** node for the following services:

- Copilot
- Microsoft 365 Backup (GCC and new Backup customers. Existing backup customers continue in the Set up node).

## Before you begin

- You must have the [SharePoint Administrator](/entra/identity/role-based-access-control/permissions-reference) or [Global Administrator](/entra/identity/role-based-access-control/permissions-reference) role to access the Microsoft 365 admin center.
- You must have Owner or Contributor rights to the Azure subscription and resource group.
- The tenant must have at least one SharePoint license, or a license that includes SharePoint.
- You must have an Azure subscription in the same tenant as Microsoft 365.
- You must have an Azure resource group in that subscription.

## Set up pay-as-you-go billing

### Step 1: Activate pay-as-you-go services

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, then go to **Billing** > **Pay-as-you-go**.
1. Select **Add a billing policy**.
1. On the **Billing details** page, fill in the required information, including:

   - Policy name
   - Azure subscription
   - Resource group
   - Region (determines where tenant ID and usage data are stored)

1. Read and accept the pay-as-you-go terms of service, then select **Next**.
1. On the **Users** page, choose **All users** or a **Specific group** (search for and add a single group). Select **Next**.

    > [!NOTE]
    > When selecting a group, only the first 1,000 groups are displayed in alphabetical order.

1. On the **Review and finish** page, double-check all the details you've entered. If everything is correct, select **Create polic**.

Your billing policy is now created but not yet connected to a service.

### Step 2: Connect the billing policy to a service

1. On the **Services** page, select the service you want to connect, then select **Connect a policy**.
2. Select the new billing policy and link it to a pay-as-you-go service.

    > [!NOTE]
    > For any Copilot services, when you select **Connect a policy,** the page directs you to the Copilot **Billing & Usage** page. Select **Go to Copilot Billing & usage** to be redirected.

## Monitor usage and costs

After setup, monitor your pay-as-you-go usage and costs in [Microsoft Cost Management for Azure](https://portal.azure.com/#blade/Microsoft_Azure_CostManagement/Menu/costanalysis). Ensure you have at least read access to the billing resource group.

## Disconnect pay-as-you-go billing

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, then go to **Billing** > **Pay-as-you-go**.
2. On the **Services** page, select the service you want to disconnect.
3. Under **Billing Policies**, select the toggle to turn it off.
4. Select **Save**.

After you disconnect the service, review your billing and usage to ensure no further charges are applied.
