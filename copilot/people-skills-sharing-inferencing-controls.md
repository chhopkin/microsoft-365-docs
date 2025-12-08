---
title: Manage admin controls in People Skills
description: Learn how to set privacy, access and skill sharing controls for users, groups, or the entire tenant to meet your organization's needs and comply with local or business requirements.
author: kwekuako
ms.author: kwekua
manager: scotv
ms.service: microsoft-365-copilot
ms.collection: 
- trust-pod
- operations-pod
ms.topic: how-to
ms.date: 07/22/2025
---

# Manage admin controls in People Skills

People Skills offers a variety of controls for Admin users to configure privacy settings, skill visibility, and access management within the Microsoft 365 Admin Center. By using these controls, you can meet your organization's needs and comply with local regulatory or business requirements. These settings can also be used to selectively deploy People Skills to a small group of pilot users, while restricting functionality to the rest of your tenant. People Skills provides access controls using [Feature Access Management](/viva/feature-access-management). By understanding these controls, you can deploy People Skills in a compliant, flexible manner—whether to your entire tenant, specific groups, or a small set of pilot users.


#### Example use-cases for when these controls may be valuable:

- __Workers Council or Regional Compliance Requirements__

  If your organization operates in a region with Workers Council requirements and needs to disable People Skills for users in that area (for example, users in Germany), you have several options for configuring compliance‑appropriate access controls. For example, you can use the **AI Inferencing control** to disable AI‑generated skill inferences while still allowing users to opt in if they choose. Alternatively, you can use the **People Skills user experiences control**, which fully disables all People Skills experiences for the selected user group; this higher-level control removes all People Skills user experiences for those users and is commonly used to meet regional compliance needs.
  
- __Piloting People Skills with a Test Group__

  If you want to roll out People Skills gradually, you can enable it only for a small pilot group while keeping it turned off for the rest of your tenant. The __People Skills user experiences control__ lets you turn the experience on for the pilot group and off for everyone else.
  
- __Limiting Skill Visibility for Privacy or Data Boundaries__

  If you need to restrict how widely Skills data is shared within your organization, you can adjust the default sharing behavior using the **Skills** __Profile Visibility Control__ to disable skill sharing. Individual users can still choose to opt in if they prefer.
  
- __Blocking AI from Automatically Adding Skills__

  If you do not want AI to infer or add skills to users’ profiles, you can use the __AI Inferencing Control__ to fully disable AI-generated skills across the selected users.
  
## Overview of People Skills Admin Controls

As an admin, you may manage People Skills through the following controls:


| Feature Control| What it does|Access Settings|Default setting|Relationships to other controls|
| -------- | -------- | -------- | -------- | -------- |
|People Skills user experiences|Turns all People Skills user experiences on or off for selected users. |On (hard enable); or Off (hard disable) |On|This is a parent control to all other admin controls. If this is turned off, then all other controls will be turned off. |
|Skills AI Inferencing|Determines whether AI can infer Skills for users and add them to their M365 profiles on their behalf.  |On, users can opt out (soft enable); or Off, users can opt in (soft disable); or Off (hard disable) |On, users can opt out (soft enabled) |This is a parent to the **Show AI Inferred Skills** control. This is a child to the **People Skills user experiences** control. |
|Skills Profile Visibility |Controls whether any of a user's skills (AI-inferred, Confirmed, or Imported) are shown on the user's M365 Profile Card or shared with other M365 applications.|On, users can opt out (soft enable); or Off, users can opt in (soft disable); or Off (hard disable) |On, users can opt out (soft enabled) |This is a parent to the **Show AI Inferred Skills** control and the **Show Imported Skills** control. This is a child to the **People Skills user experiences** control. |
|Show AI-Inferred skills|Controls whether AI-Inferred Skills are shown on the user's M365 Profile Card or shared with other M365 applications. |On, users can opt out (soft enable); Off, users can opt in (soft disable); or Off (hard disable) |On, users can opt out (soft enabled) |This is a child to the **Skills Profile Visibility** control, and the **People Skills user experiences** control. |
|Show Imported Skills|Controls whether imported (also known as organization-added) skills are shown on the user's M365 Profile Card or shared with other M365 applications.|On, users can opt out (soft enable); Off, users can opt in (soft disable); or Off (hard disable) |On, users can opt out (soft enabled) |This is a child to the **Skills Profile Visibility** control, and the **People Skills user experiences** control.|

All controls can be scoped at either the entire tenant level, to specific user groups, or to individual users. You configure these controls using [Feature access management](/viva/feature-access-management), available in:

- Microsoft Admin Center, or

- PowerShell

Admins can set controls at any time: before, during, or after deployment.  To view your admin settings, you can navigate to the People Skills setup page and select **Settings**.

> [!IMPORTANT]
> Changes in Feature access management take up to 24 hours to complete, and end-to-end changes may take up to 72 hours to fully propagate across all experiences. 

#### **Key terminology**

When managing these Admin Controls, please refer to the below table for important definitions of terms referenced throughout this page.  

| Term| What it means|
| -------- | -------- |
|Hard disable| Feature is fully disabled (turned off) and users cannot opt in|
| Soft disable|Feature is available but default off, and users may opt in |
|Soft enable|Feature is available and default on, and users may opt out|
|Parent control|A parent control determines the access settings of its child controls. When the parent it turned off, all child controls automatically inherit that setting and are also turned off. For example, the **People Skills user experiences** control is a parent for all other admin controls; if the People Skills user experiences is turned off, every related control beneath it is disabled as well. |
|Child control|A child control are controls that sit beneath a parent feature and depend on the parent's access state. A child control can only be applied if its parent feature is turned on. When the parent is disabled, all associated child controls automatically became disabled (they inherit their parent's access setting). |

See below visual diagram for an illustration of the relationships between the controls. 

![User's image](media/people-skills-sharing-inferencing-controls/image1.png)

## Managing the People Skills user experiences control



## Skills AI inferencing control overview

Skills inferencing controls are enabled by default, but you can let users opt in or out or disable inferencing entirely either before or after setting up People Skills.

- Admins can turn skills inferencing auto-on. Individual users can opt out. 
- Admins can turn skills inferencing auto-off. Individual users can opt in.  
- Admins can disable skills inferencing for their tenant.

## Skills visibility controls overview

Skills visibility controls whether users can see their colleagues' skills on surfaces like the people card or in Copilot. All skills in a user's profile are shared and visible by default once you set up People Skills in your tenant. You can also change these visibility controls before or after setting up People Skills.

- Admins can turn skills visibility auto-on. Individual users can opt out.
- Admins can turn skills visibility auto-off. Individual users can opt in.
- Admins can disable skills visibility of some skills (AI-generated or imported skills) for their tenant.


We offer three levels of controls to control skill visibility. Each of these controls can be enabled or disabled using their own access policy.

- **(Parent control) Visibility of entire skills profile:** An individual's skills profile consists of AI-generated skills, user-confirmed skills, and imported skills (if applicable). If sharing is disabled, all user skills are private and not shared in any user, leader, or organizational analyst experiences.

- **(Child control) Visibility of AI-generated skills:** AI-generated skills are skills based on AI inferencing that are relevant to a user's role. These skills can only be shown if the skills profile (parent) is also set to visible. Separate controls for both admins and for users to allow them to share skills, even if the user's profile is set to visible.

- **(Child control) Visibility of imported skills:** User skills from third-party applications can be imported by your organization. Skills from these apps might need to be confirmed by users before they're shown in experiences as skills. A user might need to confirm these skills, similar to AI-generated skills. These skills can only be shown if the skills profile (parent) is also set to visible. Separate controls for both admins and for users to share skills, even if the user's profile is set to visible.

> [!IMPORTANT]
> When multiple policies apply to the same user, the [most restrictive policy takes precedence](/viva/feature-access-management#which-policy-takes-precedence). User/Group policies override organization-wide policies.
>
> **Example:** If you create two policies - one that disables a feature for everyone in your organization, and another that enables the feature for people in a specific group - the feature will be enabled for group members because the group policy takes precedence over the organization-wide policy.

The following sections will walk you through on how to set up each of the controls in detail, and the expected functionality when they're enabled or disabled.


## People Skills Controls to Feature Access Policies Overview

The four features for People Skills described above map to the below, and are all available to be set for the **tenant**, **group**, and **user** scopes.

| ModuleId | FeatureId | Policy Modes | Parent Feature | 
| --- | ---- | ------ | ---- |
| PeopleSkills |  SkillsInferencing | HardDisable, SoftDisable, SoftEnable | None
| PeopleSkills |  SkillsProfileVisibility |  SoftDisable, SoftEnable | None
| PeopleSkills |  ShowAISkills |  HardDisable, SoftDisable, SoftEnable | SkillsProfileVisibility
| PeopleSkills |  ShowOrgAddedSkills |  HardDisable, SoftDisable, SoftEnable | SkillsProfileVisibility


The Policy Modes supported for each feature map to the following PowerShell commands.

- **HardDisable**: The feature is disabled, users do not have the ability to opt-in or opt-out. This is controlled by setting the PowerShell property **-IsFeatureEnabled $false**. 

- **SoftDisable**: The user is opted-out by default. This is controlled by setting the PowerShell properties **-IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false**. 

- **SoftEnable**: The user is opted-in by default. This is controlled by setting the PowerShell properties **-IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $true**.

> [!IMPORTANT]
> Make sure you have Exchange PowerShell version 3.8.0 or later if you plan to SoftDisable or SoftEnable, as property IsUserOptedInByDefault is only available on the newer module versions.

## Manage skills AI inferencing

Select **Skill inferencing by AI** under **Settings** to see details about the AI inferencing settings. People Skills provides access controls using [Feature Access Management](/viva/feature-access-management) to ensure you comply with user privacy and local regulations.

When inferencing is enabled, users receive AI-generated skills relevant to their role. When skills AI inferencing is turned off, no AI computation is processed for that user. The user can still create a skill profile by manually searching to add skills from your taxonomy. They can also confirm any imported skills that an admin in your organization adds for them.

Create an access control policy if you need to disable skill suggestions for specific users, groups, or your entire tenant. For more information on how to create and manage policies, see [control access to features](/viva/feature-access-management) and [Add-VivaModuleFeaturePolicy PowerShell command details](/powershell/module/exchangepowershell/add-vivamodulefeaturepolicy).

> [!NOTE]
> Policies for People Skills can only be created in PowerShell at this time. You can't create or manage policies through the interface in Admin center.

You have the following options for creating an access control policy in PowerShell to manage skills inferencing:  

- **Enable skills inferencing (Default):** When inferencing is enabled, users receive skill suggestions relevant to their role. Users have the option to turn it off for themselves in the Microsoft 365 profile editor, on the Data and privacy tab.

- **Keep skills inferencing enabled but default off:** Skills inferencing is available in your tenant, but users in this access policy will be "opted-out," and won't receive inferencing suggestions. Users have the option to turn it on for themselves in the Microsoft 365 profile editor, on the Data and privacy tab.

  To create this policy, run the following PowerShell cmdlet.

  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsInferencing -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false -Everyone
  ```

  > [!IMPORTANT]
  > The Feature Access Policy name values have to be unique, so make sure you are editing **-Name** in the PowerShell commands to names descriptive to your policy.

- **Completely disable skills inferencing:** With this policy, skills inferencing is disabled for your tenant and users can't opt in to receiving skill inferencing suggestions.

  To create this policy, run the following PowerShell cmdlet:
  
  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsInferencing -Name HardDisable -IsFeatureEnabled $false -Everyone
  ```

  > [!NOTE]
  > In the PowerShell script, the **ModuleId** is *PeopleSkills*, and the **featureId** is *SkillsInferencing*. Replace `-Everyone` with your desired scope:
  > - `-Everyone` (entire organization)
  >
  > - `-GroupIds "group1@contoso.com","group2@contoso.com"` (specific groups)
  >
  > - `-UserIds "user1@contoso.com","user2@contoso.com"` (specific users)

For more details on PowerShell syntax, refer to **[our Feature Access Management documentation](/viva/manage-access-policies)**.
  
### Control visibility of entire user skills profile (Parent control)

This control can be used to control visibility of a user's entire skills profile. An individual's skills profile consists of AI-generated skills, user-confirmed skills, and imported skills.

By default, a user's skills profile is shown to others in their organizations and shared with other Microsoft 365 experience. If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy.

> [!NOTE]
> If sharing is disabled or "opted-out" by a user, all user skills will be private and won't be shown to other users or shared with any Microsoft 365 experiences.

You have the following options for creating an access control policy in PowerShell to manage visibility of entire user skills profile:  

- **Enable profile visibility (Default):** When visibility is enabled, users skills profile is shared across Microsoft 365. Users have the option to turn it off for themselves in their skill settings.

- **Keep profile visibility default off:** Users in this access policy will be "opted-out," and their skills won't be shared across Microsoft 365. Users have the option to turn it on for themselves in their skill settings.

  To create this policy, run the following PowerShell cmdlet:

  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsProfileVisibility -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false -Everyone
  
  ```

> [!NOTE]
> In the PowerShell script, the **ModuleId** is *PeopleSkills*, and the **featureId** is *SkillsProfileVisibility*. Replace `-Everyone` with your desired scope:
> - `-Everyone` (entire organization)
>
> - `-GroupIds "group1@contoso.com","group2@contoso.com"` (specific groups)
>
> - `-UserIds "user1@contoso.com","user2@contoso.com"` (specific users)
>
> For more details on PowerShell syntax, refer to **[our Feature Access Management documentation](/viva/manage-access-policies)**.
>
> We don't offer the option to completely disable skills profile visibility. A user can always opt in to sharing their skills profile from their personal skills settings in Profile Editor. Admins can disable sharing of some skills such as AI-generated, or org. added skills 

### Control visibility of AI-generated skills

AI-generated skills are provided to users based on their role and Microsoft 365 activity.

By default, a user's AI-generated skills are shown to others in their organizations and shared with other Microsoft 365 experiences. People Skills provides access controls using [Feature Access Management](/viva/feature-access-management) to ensure you comply with user privacy and local regulations.

> [!NOTE]
> These skills are only shared if Skills Profile visibility is also enabled or shared. If sharing is disabled, AI-generated skills won't be shown to other users or shared with any Microsoft 365 experiences.

If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy.

You have the following options for creating an access control policy in PowerShell to manage the visibility of AI-generated skill:  

- **Enable sharing of AI-generated skills (Default):** When visibility is enabled, AI-generated skills are shared across Microsoft 365. Users have the option to turn it off for themselves in their settings. Users can also manage how they can share AI-generated skills for themselves in the Microsoft 365 profile editor on the Data and privacy tab.

- **Keep the default sharing off for AI-generated skills**: Users in this access policy will be "opted-out," and their AI-generated skills won't be shared across Microsoft 365. Users have the option to turn it on for themselves in their skill settings.

  To create this policy, run the following PowerShell cmdlet:

  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowAISkills -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false -Everyone
  ```

- **Completely disable sharing of AI-generated skills**: With this policy, AI-generated skills aren't shared with anyone but themselves and users can't opt in to sharing their AI skill suggestions before confirming them those skills.  

  To create this policy, run the following PowerShell cmdlet:

  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowAISkills -Name  HardDisable -IsFeatureEnabled $false -Everyone
  ```

  > [!NOTE]
  > In the PowerShell script, the **ModuleId** is *PeopleSkills*, and the **featureId** is *ShowAISkills*. Replace `-Everyone` with your desired scope:
  > - `-Everyone` (entire organization)
  >
  > - `-GroupIds "group1@contoso.com","group2@contoso.com"` (specific groups)
  >
  > - `-UserIds "user1@contoso.com","user2@contoso.com"` (specific users)
  >
  > For more details on PowerShell syntax, refer to **[our Feature Access Management documentation](/viva/manage-access-policies)**.

### Control visibility of third-party imported skills

Imported skills added by an admin in your organization from external systems display in a user's skills profile alongside AI-generated skills. Like AI-generated skills, these skills are available for the user to confirm in the Microsoft 365 profile editor. By default, third-party skills are displayed to others in their organizations and shared with other Microsoft 365 experiences. If sharing is disabled, imported skills won't display to others in the organization.

> [!NOTE]
> These skills are only shared if Skills Profile visibility is also enabled or shared. If sharing is disabled, third-party skills won't display to other users or get shared with any Microsoft 365 experiences.

If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy. For more information, see [Feature Access Management](/viva/feature-access-management).

You have the following options for creating an access control policy in PowerShell to manage third-party skills visibility imported by your organization:  

- **Enable third-party skills visibility (Default):** When visibility is enabled, third-party skills are shared across Microsoft 365. Users have the option to turn it off for themselves in their settings.

- **Keep imported skill sharing default off:** Users in this access policy will be "opted-out," and their third-party skills won't be shared across Microsoft 365. Users have the option to turn it on for themselves in their skill settings.

  To create this policy, run the following PowerShell cmdlet:
  
  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowOrgAddedSkills -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false -Everyone
  ```

- **Completely disable imported skill sharing:** With this policy, third-party skills aren't shared with Microsoft 365 experience in your tenant and users can't opt in to sharing their third-party skills.

  To create this policy, run the following PowerShell cmdlet:
  
  ```powershell
  Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowOrgAddedSkills -Name HardDisable -IsFeatureEnabled $false -Everyone
  ```
  
  > [!NOTE]
  > In the PowerShell script, the **ModuleId** is *PeopleSkills*, and the **featureId** is *ShowOrgAddedSkills*. Replace `-Everyone` with your desired scope:
  > - `-Everyone` (entire organization)
  >
  > - `-GroupIds "group1@contoso.com","group2@contoso.com"` (specific groups)
  >
  > - `-UserIds "user1@contoso.com","user2@contoso.com"` (specific users)
  >
  > For more details on PowerShell syntax, refer to **[our Feature Access Management documentation](/viva/manage-access-policies)**.
  
## Manage skills data sharing with Viva Insights

When checked, skills data is passed on to Viva Insights. Skills in Viva Insights allows organizations and leaders to discover skills within their workforce and assess skill distribution across groups. Learn more about [People Skills in Viva Insights](/viva/insights/advanced/analyst/templates/skills-landscape).

You can stop skills data from being shared with Viva Insights by unchecking this setting.
