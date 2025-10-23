---
title: How to do advanced filtering in SharePoint for Employee Self-Service
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
description: Learn how to do advanced filering in SharePoint for Employee Self-Service agents that align with your organization's needs.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# SharePoint Advanced Filtering (CPS) How-To

When employees ask Employee Self-Service (ESS) questions like "What is my holiday policy?", the system sometimes shows policies for multiple countries (for example, US, India, France) instead of just the one that applies to the employee. This happens because ESS retrieves all matching SharePoint documents but doesn't apply user-specific filters (like country, region, or company code) during the search.

We can personalize results by telling ESS to only return SharePoint documents that match the employee's profile, such as their location or company code.

This works in two parts: 

1. ESS collects user information, like location, and stores it as a variable.
1. SharePoint Knowledge Sources are updated to use that variable when searching, so results are filtered to what's relevant.

XXX WHY ARE KNOWLEDGE SOURCES CAPITALIZED? ARE THEY BRANDED TERMS? IS THIS THE KS THAT WE NEED DEFINED?

## Step-by-step configuration

### Prerequisites

1. Decide the attributes to filter on (some examples include Company_Code, Country, Location, Department).
1. Verify SharePoint metadata exists on the target content (site columns filled on pages/docs).
1. Find the managed property that maps to that column: **SharePoint Admin Center** > **More features** > **Search** > Manage Search Schema.
    1. Confirm the property you'll use (such as RefinableString100) is Searchable/Queryable/Refinable.
    1. If you just changed mappings, Reindex the library or site and allow time for crawl.
1. Identify where you'll source the user attribute at runtime, like Workday, SuccessFactors, Graph, or a custom API.

### Capture the user contect in the agent (Copilot Studio)

1. In your ESS solution, open **Admin** > **User Context** > **Setup**.
2. Make sure this topic runs before any retrieval topics (keep/enable the redirect pattern).
3. Fetch attributes and set global variables, such as:
    1. Global.ESS_UserContext_Company_Code
    1. Global.ESS_UserContext_Country
    1. Global.ESS_UserContext_Location
  **NOTE**: Use your connector/action to get these values. For a quick smoke test, you can temporarily hardcode a value.
4. Save and publish.

###  Add KQL filters to SharePoint knowledge sources

For **each** SharePoint knowledge source that must respect filtering:

1. Open the **knowledge source** > **Advanced settings**. XXX WHERE ARE WE OPENING THIS? IS IT A FORMAL THING? IS IT CALLED KS HERE
1. In **Additional search** terms, add KQL that references your **managed property** and **global variable**.

   **Examples**
   XXX I CAN'T SPECIFY KQL IN GITHUB AT THIS TIME AND SO AM LEAVING BLANK

   - **Company code**

   ```
   additionalSearchTerms: (NOT HIDEFROMSEARCH:1)
   AND (RefinableString100:All OR RefinableString100:{Global.ESS_UserContext_Company_Code})
   ```

   - **Country/Region**

   ```
   additionalSearchTerms: (NOT HIDEFROMSEARCH:1)
   AND (RefinableString101:{Global.ESS_UserContext_Country})
   ```

   - **Location**

   ```
   additionalSearchTerms: (NOT HIDEFROMSEARCH:1)  
   AND (RefinableString102:{Global.ESS_UserContext_Location})
   ```

   - **Multiple attributes (AND)**

   ```
   additionalSearchTerms: (NOT HIDEFROMSEARCH:1)
   AND (RefinableString100:{Global.ESS_UserContext_Company_Code})
   AND (RefinableString101:{Global.ESS_UserContext_Country})
   ```

   > [!TIP]
   > All is a useful fallback value when content is intentionally global or applicable to everyone.

3. Save and publish.

XXX THERE IS A VALIDATE SECTION WITH ALMOST NOTHING IN IT.
