---
title: Extending Employee Self-Service Copilot Agents with Workday
f1.keywords: NOCSH
ms.author: heidip
author: MicrosoftHeidi
manager: dansimp
ms.reviewer: semani
ms.date: 11/05/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about extending Employee Self-Service Copilot Agents.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Extending Employee Self-Service Copilot Agent with Workday

The Employee Self-Service agent allows employees to get their queries answered from admin-configured knowledge sources, HCM and IT systems. The Employee Self-Service agent, along with accelerator packages for connecting external systems, unleashes a powerful set of ready-to-use Topics that cover common HR & IT scenarios.

However, every organization has unique processes and policies where each vertical owners may want to include a few other self-serve scenarios as part of the Employee Self-Service agent, such as:

- Apply for leave or request for leave balance using Copilot.
- View job details for their direct reports.
- Move or transfer an employee.

XXX IS TOPICS BRANDED AND THEREFORE TO BE CAPITALIZED, OR LOW-CAPS? I AM LOW-CAPS HERE BECAUSE YOU'VE DONE BOTH.

To support these needs, the Employee Self-Service agent is designed to be extensible, so custom Topics can be created to work seamlessly alongside with out-of-the-box (OOB) topics. This article explains the steps to extend the Employee Self-Service agent by adding new topics tailored to your organization.

> [!NOTE]
> This article is for Copilot Studio makers looking to extend the Employee Self-Service agent with custom topics for Workday.

## Prerequisites

Before extending the Employee Self-Service agent with custom topics in your Workday integration, make sure:

- The Employee Self-Service agent's installed in Copilot Studio.
- The Employee Self-Service agent's Workday package is installed and configured in Copilot Studio. Follow [these steps](workday.md) to complete the integration between the Employee Self-Service agent and Workday's official guidance.
- Maker access to a sandbox or pre-production environment in Copilot Studio.
- Admin access to Workday to configure additional permissions if required.

## Fundamentals

Extending the Employee Self-Service agent with Workday requires an understanding of two key building blocks: topics and template configurations. Together, these building blocks define how conversational scenarios are designed and how they interact with Workday services.

### Topics

In Copilot Studio, a topic represents the workflow of a conversation. M365 Copilot Topics are used to:

- Defining triggers prompts to determine when a topic should be triggered based on an employee's natural language input.
- Ask questions and capture input, such as dates, employee details, or policy selections.
- Call the API request for Workday, based on the scenario using the Power Automate Flow.
- Interpret the Workday response and return the relevant outcome back to the employee in a conversational format.

### Template configurations

When adding new Workday scenarios to the Employee Self-Service agent, it needs to know the format of the request, its inputs and outputs, and all the options available in the corresponding Workday operation. Templates are used to define that.

[Learn more](workday.md#template-structure-overview) about template configurations.

## Templates included in the solution

The Employee Self-Service agent comes with a set of [pre-built template configurations](workday.md#templates-included-in-the-solution) that help employees find answers to common Workday scenarios. Reviewing these configurations can help you understand the structure and guide you when authoring your own.

1. Navigate to your environment in Copilot studio: `https://copilotstudio.microsoft.com/`
1. Select **Solutions** on the left navigation panel.
1. Open the **Default Solution** under the unmanaged section.
1. Use the search box to look for **Employee Self-Service Template Configuration**.
1. Select a Workday template configuration, such as:
   - HRWorkdayHCMEmployeeGetCompanyCode 
1. Review the details of the configuration, including request definitions, parameters, and response mappings.

## Sample scenario: Applying for time off

Let's walk through a practical example. In this section, we extend the Workday setup to allow employees to apply for leave through the Employee Self-Service agent.

This process involves 3 steps:

1. **Create the Employee Self-Service agent's template configuration**: Define the request and response mapping for the Workday service, save it in your Copilot environment, and validate its correctness.
1. **Create a new topic**: Build a Copilot topic that uses the template configuration to apply leave on behalf of the employee.
1. **Workday permissions**: Assign all the required permissions to employee account in Workday to enable the Employee Self-Service agent to apply for leave on their behalf.

### Create the Employee Self-Service agent's template configuration

Before diving into the detailed steps for creating your own Employee Self-Service agent template configuration, explore the ready-to-use [sample scenarios](workday.md#templates-included-in-the-solution) provided by Microsoft. These samples cover common employee and manager use cases, such as applying for leave, viewing vacation balances, and so on.

1. Go to the Copilot Studio Samples repository and copy the [template for requesting time off](https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Workday/EmployeeScenarios/WorkdayEmployeeRequestTimeOff/msdyn_HRWorkdayAbsenceEnterTimeOff_EnterTimeOffInfo.xml).
1. Save the new template into the Employee Self-Service template configurations.
    1. Go to **Copilot studio** and navigate to **Solutions** > **Default Solution**.
    2. Search and Select **Employee Self Service Template Configuration** from the left side navigation pane.
    3. Go to **New** > **More** > **Other** > **Employee Self Service Template Configuration**.
    4. Enter details for the required fields (enter a Description optionally):
        1. Name
        2. Owner
        3. Unique name (Use the requestTemplateName from the xml as the unique name of the template.)
        4. Value
    5. Copy the **unique name** of the template for the next steps in the process.
    6. Save and close the template configuration.
2. Validate the generated file using cloud flows.
    1. Navigate to Copilot Studio and select **Flows** in the left navigation bar.
    2. Select **Workday** from the listed flows.
    3. Select **Run** on the top panel. This action opens a dialog on the right side of the screen with two fields: **scenarioName** and **parameters**.
    4. Use the **unique name** from step 1e as the scenario name.
    5. Use the following format for the **parameters** textbox for tje time off request. Update the values of the parameters for your environment, focusing on the **Employee_ID** and **Reason_ID** parameters.

    ```
    {
      "params": [
        {  "key": "{Employee_ID}", "value": "21510"  }
        {  "key": "{Time_Off_Date}", "value": "2025-01-31"  }
        {  "key": "{Hours}", "value": "8"  }
        {  "key": "{Reason_ID}", "value": "Paid_Time_Off_Adjustment_Hours"  }
        {  "key": "{Comment}", "value": "Personal"  }
      ]
    }
    ```

    6. Run the flow and go to the **Flow runs** page.
    7. Select your flow and validate if all steps run successfully.
    8. A successful run flow shows a green checkmark on the last step of the Workday flow on the upper right-hand side, next to the seconds run.
    9. A run fails if it doesn't show success.
    10. This instance fails, as permissions aren't set on Workday's system. We add permissions in our final step.
    11. When the template is successful, it can be used in the Copilot topic definition.

XXX I FIND US DESCRIBING SUCCESS HERE WHEN IT LITERALLY CAN'T SUCCEED BECAUSE OF PERMISSIONS PROBLEMATIC.

Starting with the sample template and topic definition allows you to quickly deploy a working solution. Once you're comfortable with the process, you can move on to creating and customizing your own templates for additional scenarios.

You can follow the steps in the next section to create your own templates using Microsoft's Copilot. Feel free to skip these steps for now and refer to these steps later when you want to add your own scenarios.

1. Find the Right Workday Service and Operation.
    1. Use Workday's official docs to locate the correct service and operation. We use **Service: Absence Management Service** and **Operation: Enter_TimeOff** for applying leave.
    1. Download the sample request and response format files from the documentation.
        1. Sample Request: Enter_Time_Off_Request.xml
        1. Sample Response: Time_Off_Event_Response.xml
1. Download the existing Employee Self-Service agent template files from the Copilot solution as a reference for the new scenario to be generated.
    1. Follow the steps mentioned above and select **HRWorkdayHCMEmployeeUpdatePersonalEmail**.
    1. Copy the contents of the XML in a file named, **sample_configuration_template.xml**.
1. Use M365 Copilot to generate the XML Templates.
    1. Attach all the files downloaded in the previous steps to your chat. You need to change their extensions to **.txt** because Ccopilot doesn't allow xml.
    1. These files serve as reference inputs for Copilot to learn the correct format and structure of the SOAP Request.
1. Prompt M365 Copilot with GPT-5 On to generate the xml template using the following prompt: XXX WILL WE BE CHANGING THIS CONTENT WHEN THE GPT-5 BECOMES SOMETHING ELSE? WHY MENTION THAT SPECIFICALLY?

```
You're an integration specialist creating a configuration for a Copilot Studio bot to call a Workday SOAP API. Your task is to create a complete XML configuration file for a 'Request Time Off' scenario.

Follow these specific instructions:

1. Overall Structure: The final XML must follow the exact structure of the provided sample_configuration_template.txt, including the <scenario>,<apiRequests > and <requestTemplates> sections.
1. API Request Payload: The <requestTemplates> section must contain the body of an Enter_Time_Off_Request API call.
    1. Use the Enter_Time_Off_Request.txt file as the definitive source for the payload's structure.
    1. Simplify the payload to only include the elements necessary for this request.
1. Dynamic Inputs: The request payload must be parameterized with placeholders for the following dynamic inputs from the employee:
    1. {Date}
    1. {Reason} (This is the ID for the time off reason)
    1. {Comment}
    1. {Employee_ID}
1. Response Handling: The section must be configured to extract the Time Off Event ID from the API response.
    1. Use the Time_Off_Event_Response.txt file to determine the correct XPath for extracting the ID from the element.
    1. The key for the extracted property should be TimeOffEventID.

Generate a single, complete XML file based on these instructions and the attached reference files.
```

5. We use the generated XML in the topic definition in later steps.
1. Follow the same steps as before to save your template into the Employee Self-Service agent. XXX AS BEFORE WHAT? LET'S REFERENCE THE SECTION HERE.

### Create a new topic

1. Go to the Copilot Studio Samples repository and copy the [topic definition for requesting time off](https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Workday/EmployeeScenarios/WorkdayEmployeeRequestTimeOff/topic.yaml).
1. You may need to adjust the **Time_Off_Type_Id** in the sample topic definition. Log in to Workday and search for ""View Time Off Types"". Adjust the drop-down in the topic definition and replace the time off types for your organization.
1. Create a new topic: **Workday Apply Time Off**.
    1. Navigate to Copilot studio and Select **+ Add a topic** > **From blank** to open the Code Editor.
    1. Paste the topic definition you copied from step 1. into the Code Editor.
    1. Validate:
        1. Open the visual representation of the topic definition and validate the workflow of the topic.
        1. Select the Topic Checker for any static issues with the definition.
    1. Test your newly added topic:
        1. Using the **Test** button in Copilot studio, open the test chat window.
        1. Apply for leave using the prompt.
           *"Apply full day leave on 21th February 2026, Reason: Sick. Comment: Feeling unwell."*
        1. Add any necessary details and submit the request.
        1. A successful leave application submission should have a response similar to:
           *"Your time off request has been submitted for 2026-02-1 & 8 hours. Reason: Paid Leave, Comment: Personal Leave""
        1. This might fail with an unauthorized error, as we need to allow employees to request leave on Workday using a SOAP request. We can implement and check this as the last step of the process. XXX AGAIN, THIS MEANS NONE OF THIS IS HELPFUL.

Next learn how you can generate the topic definition ourselves instead of relying on the provided samples. Feel free to skip these for now and jump to Workday Permissions directly, refer to these instructions when you want to add your own scenarios into the Employee Self-Service agent.

XXX THIS IS VERY PROBLEMATIC, CONTENT-WISE. WHY ARE WE PUTTING THIS IN THE ARTICLE AND TELLING PEOPLE TO SKIP IT. PROBLEMATIC.

XXX I'M ALSO SKIPPING THE APPLYING LEAVE EXAMPLE. WE AREN'T PUTTING IN MULTIPLES OF THIS.

’
”
