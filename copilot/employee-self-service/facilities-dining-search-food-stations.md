---
title: Make Employee Self-Service agent dining
f1.keywords: NOCSH
ms.author: heidip
author: prsarnaik
manager: baradhak
ms.reviewer: MicrosoftHeidi
ms.date: 04/20/2026
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.subservice: ess-agent
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about creating a Dining related topic in Employee Self-Service agent
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Extending Employee Self-Service Agent

An organization may seek to enhance ESS by integrating additional capabilities that enable employees to maximize the benefits of ESS and support their work-related activities.

To support these needs, ESS is designed to be extensible. You can create and publish your own topics that work seamlessly alongside the built-in ones. This article explains the steps to extend ESS by adding new topics tailored to your organization.

At Microsoft, we have extended ESS to bring in Real Estate and Facilities related experiences like allowing employees to register their vehicle (Parking), create a facilities ticket (Facilities), view available food stations by cuisine (Dining), or invite guests to offices (Lobby) via ESS.

Some scenarios that this extensibility to ESS is helping us power:

- Create a Facilities Ticket, e.g. “I want to report a water leak”
- Register a Vehicle, e.g. “I want to register my vehicle Tesla Model 3”
- View food stations or counters by cuisine, e.g. “Where can I find Chinese food?”
- Invite a Guest, e.g. “I want to invite my spouse to Building 32”

In the following section, we will see how a maker in Copilot Studio can extend ESS to support Dining related scenarios.

## Real Estate & Facilities

Real Estate and Facilities (RE&F) play a pivotal role in shaping the overall employee experience within an organisation. By integrating RE&F services into Employee Self-Service (ESS) platforms, companies can streamline access to essential workplace amenities and administrative tasks, making daily operations more efficient and user-friendly for employees.

For instance, features like vehicle registration for parking, facilities ticketing for maintenance requests, access to café menus, and streamlined guest invitation processes empower employees to manage their work environment proactively. These capabilities reduce administrative overhead, minimise wait times, and improve satisfaction by giving employees greater control and visibility over their workplace needs.

Moreover, such integrated experiences foster a sense of belonging and engagement, as employees feel supported by systems that anticipate and address their requirements. This not only enhances productivity but also contributes to a positive organisational culture. Ultimately, the seamless blend of real estate and facilities management with employee-centric digital solutions helps organisations attract, retain, and motivate talent.

Now that we have covered the fundamentals, let’s walk through a practical example. In the following sections, we will extend the ESS Agent to allow employees to view food stations or counter by cuisine through the ESS Copilot Agent.

## Prerequisites

Before extending the Employee Self-Service (ESS) Copilot Agent with custom topics for your Real Estate integration, ensure:

- ESS agent is installed in Copilot Studio.
- Maker access to a sandbox or pre-production environment in Copilot Studio.
- Access to Copilot Samples in GitHub:  
  https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Facilities/EmployeeSearchDiningStations/topic.yaml
- Need access to the Dining API that will be used to view food stations by cuisine.
- For this example, assume Dining service is built as an independent service on Azure platform.

## Fundamentals

Extending ESS for RE&S experiences requires an understanding of a few key building blocks: **topics, adaptive cards and connectors**. Together, these define how conversational scenarios are designed and how they interact with RE&S services.

### Topics

In Copilot Studio, a topic represents the workflow of a conversation. M365 Copilot Topics are used to:

- Define trigger prompts that determine when a topic should be activated based on an employee’s natural language input.
- Ask questions and capture necessary inputs from the employee.
- Process user input through power function formulas to extract relevant parameters for upcoming steps in the workflow.
- Trigger HTTP API calls to backend APIs to complete the workflow action.
- Interpret backend API responses and return outcomes to the employee in natural language.

Some scenarios that this extensibility to ESS is helping us power:

- Create a Facilities Ticket, e.g. “I want to report a water leak”
- Register a Vehicle, e.g. “I want to register my vehicle Tesla Model 3”
- View food stations or counters by cuisine, e.g. “Where can I find Chinese food?” 【1-f2c7ff|5】
- Invite a Guest, e.g. “I want to invite my spouse to Building 32”

In the following section, we will see how a maker in Copilot Studio can extend ESS to support Dining related scenarios.

## Fundamentals

Extending ESS for RE&S experiences requires an understanding of a few key building blocks: **topics, adaptive cards and connectors**. Together, these define how conversational scenarios are designed and how they interact with RE&S services.

### Topics

In Copilot Studio, a topic represents the workflow of a conversation. M365 Copilot Topics are used to:

- Define trigger prompts that determine when a topic should be activated based on an employee’s natural language input.
- Ask questions and capture necessary inputs from the employee.
- Process user input through power function formulas to extract relevant parameters for upcoming steps in the workflow.
- Trigger HTTP API calls to backend APIs to complete the workflow action.
- Interpret backend API responses and return outcomes to the employee in natural language.

### Adaptive Cards

Adaptive cards are platform-agnostic UI snippets authored in JSON and help create interactive cards to capture user inputs while maintaining the conversational flavour of the workflow.

### Connectors

Connectors enable you to connect your agent with your data in the cloud.

For this example of viewing food stations by cuisines, we assume Dining service is built as an independent service on Azure platform. We use the HTTP connector to connect to the backend API for viewing food stations.

Check out the list of available connectors:  
https://learn.microsoft.com/en-us/connectors/connector-reference/

Refer to HTTP request action:  
https://learn.microsoft.com/en-us/microsoft-copilot-studio/authoring-http-node

## Example: Search Food Stations by Category

Every café is comprised of multiple stations, and each station is a dedicated area serving a specific type of food or beverage (e.g., Espresso, Deli, Dim Sum). These stations give employees a variety of choices within the same café.

With the **“Search stations by category”** feature in the Employee Self-Service (ESS) Copilot Agent, employees can easily find stations serving their preferred cuisine across the office campus. Employees can mention the cuisine in their prompt (e.g., _“Where can I find Chinese food?”_) and get stations serving that cuisine.

The employees save time, skip the hassle, and make every meal a choice they will love.

This process involves only one step: define and implement the topic end-to-end, including variables, API call, validation, and user feedback.

### Create a Topic

- Create a new Topic as **“Dining Search Stations”**.
- Navigate to Copilot Studio and select **Add a topic → From blank → Open Code Editor**

  :::image type="content" source="media/facilities-dining-create-new-topic.png" alt-text="Screenshot showing how create a new topic in Copilot Studio.":::

  :::image type="content" source="media/facilities-dining-add-topic-trigger.png" alt-text="Screenshot showing how add a topic trigger.":::

- Use the code from the Copilot Samples repo file:  
  https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Facilities/EmployeeSearchDiningStations/topic.yaml

- Update the HTTP API URL in the code sample. Search for “kind: HttpRequestAction”. You will see a code that sets a value to a topic variable named SearchStationsApiUrl, as in the screenshot below. Update the variable value as per your backend system.

  :::image type="content" source="media/facilities-dining-update-api-url.png" alt-text="Screenshot showing how to update api url in the topic.":::

- Save.
- Open the visual representation of the topic definition and validate the workflow of the topic.
- Click on Topic Checker for any static issues with the definition.
- Optionally, follow the section Validate the Topic to understand and validate the steps
- Using the “Test” button in Copilot studio, open the test chat window.
- Ask using the prompt “Where can I find Chinese food?”
- The Employee Self-Service (ESS) system will display Chinese food options.

  :::image type="content" source="media/facilities-dining-where-is-food.png" alt-text="Screenshot showing results of the topic that searches for food.":::

### Validate the Topic

Validate the following in the topic definition:

- Trigger node contains the topic description used by the UI.

  :::image type="content" source="media/facilities-dining-validate-trigger-node.png" alt-text="Screenshot showing validation that the trigger node exists in the topic.":::

  :::image type="content" source="media/facilities-dining-validate-topic-file-start.png" alt-text="Screenshot showing the model description in the file.":::

- Input variable named `StationCategory` is created. Click on the Details -> Input to check that your topic has input variable named StationCategory as per the screenshot below.

  :::image type="content" source="media/facilities-dining-validate-topic-details-input.png" alt-text="Screenshot showing the input section of the topic details.":::

- Validate that the output variable named ‘SearchStationsApiResponse’ is created. Click on the Details -> Output to check that your topic has input variable named SearchStationResponse as per the screenshot below.

  :::image type="content" source="media/facilities-dining-validate-topic-details-output.png" alt-text="Screenshot showing the output section of the topic details.":::

- Post this, Validate the conditional block exists that checks user’s input in the input variable..

  :::image type="content" source="media/facilities-dining-validate-condition-block-category.png" alt-text="Screenshot showing the conditional block section of the topic details.":::

- Next node assigns the station category value, cuisine in our case, if the user has entered value in your input variable through their prompt. For example, if the user mentions “Where can I find Italian food?”. The value “Italian” will get assigned to the input variable.

  :::image type="content" source="media/facilities-dining-validate-set-variable-value.png" alt-text="Screenshot showing the set variable value.":::

- Post this, the next node makes the API call. Validate that the HttpConnector is calling appropriate API that belongs to your platform.Also check that the results from the API are captured in the output variable named SearchStationsApiResponse. We are collecting the response in a variable called SearchStationsApiResponse. This response has properties CafeId, CafeName, StationName, CanPurchaseonline etc. You should create a schema per your API response for this topic variable. Your API response may have a completely different structure, and you should make sure that structure is taken into consideration.

  :::image type="content" source="media/facilities-dining-validate-http-request.png" alt-text="Screenshot showing http request block.":::

- Validate that the conditional block checks if the response is non-empty before the topic ends.

  :::image type="content" source="media/facilities-dining-validate-condition-block-response.png" alt-text="Screenshot showing conditional block.":::

- Final step is to display the result. You do not need to add any adaptive card here. In the topic description, we have mentioned to extract information from SearchStationApiResponse output variable. LLM follows those instructions and displays well formatted output.

  :::image type="content" source="media/facilities-dining-validate-display-results-description.png" alt-text="Screenshot showing topic trigger description block.":::

## FAQs

### In the sample, what happens if the API fails to return results?

If the API fails, it returns an empty response. In this case, the conditional block shows an error message telling the user it was unable to find dining information for the cuisine entered, and points them to a link. You should tailor error responses based on your system.

### When I save my topic, it shows errors saying it cannot find certain variables. What do I do?

Go to the **Variables** tab and verify all variables (topic and environment) are declared.

:::image type="content" source="media/facilities-dining-faq-variables.png" alt-text="Screenshot showing the way to check all the variables.":::

### How are error conditions handled?

You will see conditional branching like the one shown below.Those are used to handle errors and send the appropriate messages to the user..

:::image type="content" source="media/facilities-dining-faq-error-conditions.png" alt-text="Screenshot showing the way to check error conditions.":::
