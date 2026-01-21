---
title: Set up or disconnect pay-as-you-go billing in the Billing node of the Microsoft 365 admin center
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: clalissayi
audience: admin
ms.topic: install-set-up-deploy
ms.service: microsoft-365-business
ms.subservice: m365-commerce-payasyougo
search.appverid: MET150
ms.custom: 
ms.localizationpriority:  medium
description: "Learn how to set up or disconnect pay-as-you-go billing in the Billing node of the  Microsoft 365 admin center."
ms.date: 11/25/2025
---

# Set up or disconnect pay-as-you-go in the Billing node of the Microsoft 365 admin center

This article explains how to set up or disconnect pay-as-you-go billing in the **Billing** node of the Microsoft 365 admin center  for the following services:

- Copilot
- Microsoft 365 Backup (GCC and new Backup customers. Existing backup customers continue in the Set up node).

## Before you begin

- To access the Microsoft 365 admin center, you must have either the [SharePoint Administrator](/entra/identity/role-based-access-control/permissions-reference) or [Global Administrator](/entra/identity/role-based-access-control/permissions-reference) role.

  [!INCLUDE [ga-roles-limitation](../../includes/ga-roles-limitation.md)]

- You must have Owner or Contributor rights to the Azure subscription and resource group.
- The tenant must have at least one SharePoint license, or a license that includes SharePoint.
- You must have an Azure subscription in the same tenant as Microsoft 365.
- You must have an Azure resource group in that subscription.

## Set up pay-as-you-go billing in the Billing node

To set up pay-as-you-go billing in the **Billing** node, first set up a billing policy, and then connect it to a pay-as-you-go service.

### Step 1: Create a billing policy

1. Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.
1. Go to **Billing** > **Pay-as-you-go**.
1. Select **Add a billing policy**.
1. On the **Billing details** page, fill in the required information, including:

   - Policy name
   - Azure subscription
   - Resource group
   - Region (determines where tenant ID and usage data are stored)

1. Read and accept the pay-as-you-go terms of service, and then select **Next**.
1. On the **Users** page, choose **All users** or a **Specific group** (search for and add a single group). Select **Next**.

    > [!NOTE]
    > When you select a group, only the first 1,000 groups are displayed in alphabetical order.

1. On the **Review and finish** page, double-check all the details you entered. If everything is correct, select **Create policy**.

You created your billing policy and now must connect it to a service. Proceed to [Step 2: Connect the billing policy to a service](#step-2-connect-the-billing-policy-to-a-service).

### Step 2: Connect the billing policy to a service

1. On the **Services** page, select the service you want to connect, and then select **Connect a policy**.
1. Select the new billing policy and link it to a pay-as-you-go service, like **Microsoft 365 Backup**.

    > [!NOTE]
    > For any Copilot services, when you select **Connect a policy**, the page directs you to the Copilot **Billing & Usage** page. Select **Go to Copilot Billing & usage** to be redirected.

## Monitor usage and costs

After setup, monitor your pay-as-you-go usage and costs in [Microsoft Cost Management for Azure](https://portal.azure.com/#blade/Microsoft_Azure_CostManagement/Menu/costanalysis). Ensure you have at least read access to the billing resource group.

## Disconnect pay-as-you-go billing

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>, and then go to **Billing** > **Pay-as-you-go**.
1. On the **Services** page, select the service you want to disconnect.
1. Under **Billing Policies**, select the toggle to turn it off.
1. Select **Save**.

After you disconnect the service, review your billing and usage to ensure no further charges are applied.
