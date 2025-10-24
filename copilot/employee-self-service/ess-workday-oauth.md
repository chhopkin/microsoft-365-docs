---
title: Set up Workday OAuth with API management
f1.keywords: NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 10/29/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn how to configure Workday OAuth with API management.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Setting Up Workday OAuth with API Management (APIM)

XXX DO NOT PUBLISH AS-IS.

This article provides a comprehensive guide to configuring OAuth authentication for ESS Workday package.

## Prerequisites

- Administrator access to both Workday and your APIM instance (for example, Azure API Management). XXX WHAT KIND OF ADMIN? WE NEED A WARNING IF GLOBAL ADMIN.
- Access to Workday's API documentation and integration system.
- Basic understanding of OAuth 2.0 concepts.
- Network connectivity between APIM and Workday endpoints.

## Authentication workflow with APIM in-place XXX OR IS IT AUTHORIZATION? WE CAN'T JUST SAY AUTH HERE

XXX WE NEED A VERBAL WALKTHROUGH OF THIS IMAGE. WE CAN'T JUST HAVE THE IMAGE. NO.

## Step 1: Register an API client in Workday

1. Log in to Workday: Use your administrator credentials to access the Workday tenant.
1. Go to the **Register API Client** section. XXX IS THIS ON THE MAIN WORKDAY PAGE? WHAT IS THE ACTUAL NAV?
1. Create a New API Client:
    1. Specify a name and description for your integration (for example, "APIM Integration").
    1. Choose **Authorization Code Grant** for the client grant type.
    1. Set appropriate scopes:
      - Contract information
      - Core compensation
      - Integration
      - Jobs and positions
      - Personal data
      - Staffing
      - System
      - Tenant non-configurable
    1. Enter redirect URL `https://global.consent.azure-apim.net/redirect/workdaysoap`.
1. Save and note credentials. When saving, Workday generates a client ID, client secret, token endpoint and authorization endpoint. Store these securely, as they're required for APIM configuration.

> [!IMPORTANT]
> The client secret is only visible here. If you lose this secret, you need to create a new one.

## Step 2: Configure OAuth 2.0 in APIM

For more information: [Add API manually](/azure/api-management/add-api-manually).
XXX WHY DO WE HAVE THIS REFERENCE? ARE THE STEPS HERE JUST TAKEN FROM THIS ARTICLE? THEN WE SHOULD JUST REFER THEM AND NOT DUPE THE STEPS.

XXX THIS WALKTHROUGH IS VERY PROBLEMATIC AND ALSO DEPENDS ON SCREENSHOTS. WE MUST DOCUMENT IN WORDS EVERY ELEMENT OF THIS.

1. Log in to APIM Portal: Access your API Management portal (portal.azure.com).
1. Go to **Named Values** to add workday-client-id and workday-client-secret. XXX HOW AM I GOING THERE? WHAT IS THE NAV?
1. Note: Set client-secret as secret to avoid exposing it or read it from key vault. XXX WHERE AM I SETTING THIS?
1. Go to APIs to declare paths for authentication. XXX WHERE? WHAT IS THE PATH?
1. Create two endpoints authorize and token.
1. Authorise endpoint definition. XXX THIS LOOKS TO BE IN A COMMAND WINDOW. WHEN DID WE OPEN IT? HAS THIS BEEN COMMAND THE WHOLE TIME?
1. Token endpoint definition.
1. Copy base url of APIM instance. For example: `https://apim-test.azure-api.net/workday`.
1. Make sure to turn off subscription required option. XXX WHERE?

XXX THIS SECTION IS NO-GO.
XXX DO NOT PUBLISH THIS ARTICLE WITH THIS SECTION IN IT.

## Step 3: Consuming APIM in workday configuration

1. Update API Policies: In APIM XXX WHERE IN APIM? WHAT IS THE NAV, edit the policies for your relevant APIs to enforce OAuth 2.0 authentication. Typically, this involves validating the bearer token in the authorization header.
1. Choose **OAuth 2.0 via APIM** as the connection as the **Authentication type**.
1. Fill in the **APIM base URL** without /authorize or /token.
1. Select the **Sign in** button to open a popup window for authentication to Workday. Provider your Workday credentials to authenticate with Workday.

## Limitations

SSO isn't supported by Oauth 2.0. New users need to create a connection explicitly to use ESS.
XXX WHAT DOES EXPLICITLY MEAN HERE?

We've added this section to give you a support option for your existing OAuth 2.0 until your connector changes are published. Don't use once OAuth 2.0 with APIM is published:

1. During Workday installation choose OAuth 2.0 as the connection type. XXX WHERE IN THE INSTALLATION? WHAT IF YOU'RE READING THIS AFTER INSTALL?
1. Provide an authorization URL from APIM. For example: `https://apim.azure.com/workday/authorize`.
1. Provide a token URL from APIM. For example: `https://apim.azure.com/workday/token`.
1. Provide interim values for Client ID and Client secret. APIM fetches the correct values during the connection establishment
1. Provide your base url and tenant name to complete signin.
