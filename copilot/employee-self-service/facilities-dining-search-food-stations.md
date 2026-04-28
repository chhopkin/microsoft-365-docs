---
title: "Extend Employee Self-Service agent: Search Dining feed stations"
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
description: Learn about extending the Employee Self-Service tailored to your organization. This article describes the steps to search food by category (Dining) via Employee Self-Service. Example - "Where can I find Chinese food?".
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Extend Employee Self-Service agent: Search Dining feed stations

The Employee Self-Service Copilot Agent allows employees to get their queries answered from admin-configured knowledge sources, HCM, and IT systems, directly within Microsoft 365 Copilot.

An organization may seek to enhance Employee Self-Service Copilot Agent by integrating extra capabilities. These capabilities enable organizations to maximize the benefits of Employee Self-Service and support work-related activities.

To support these needs, Employee Self-Service Copilot Agent is designed to be extensible. You can create and publish your own topics that work seamlessly alongside the built-in ones. This article explains the steps to extend Employee Self-Service by adding new one tailored to your organization.

At Microsoft, we extended Employee Self-Service Copilot Agent to bring in Real Estate and Facilities related experiences. Some scenarios that this extensibility to Employee Self-Service is helping us power are:

- Create a Facilities Ticket (Facilities), for example, "I want to report a water leak"
- Register a Vehicle (Parking), for example, "I want to register my vehicle Tesla Model 3"
- View food stations or counters by cuisine (Dining), for example, Where can I find Chinese food?
- Invite a Guest (Lobby), for example "I want to invite my spouse to Building 32".

The following section shows how a maker in Copilot Studio can extend Employee Self-Service to support Dining related scenarios.

## Real Estate & Facilities

Real Estate and Facilities (RE&F) play a pivotal role in shaping the overall employee experience within an organization. By integrating Real Estate and Facilities services into Employee Self-Service platforms, companies can streamline access to essential workplace amenities and administrative tasks, making daily operations more efficient and user-friendly for employees.

For instance, features like - vehicle registration, facilities tickets for maintenance requests, access to café menus, and streamlined guest invitation processes empower employees to manage their work environment proactively. These capabilities reduce administrative overhead, minimize wait times, and improve satisfaction by giving employees greater control and visibility over their workplace needs.

Moreover, such integrated experiences foster a sense of belonging and engagement, as employees feel supported by systems that anticipate and address their requirements. These integrated experiences not only enhance productivity, but also contribute to a positive organizational culture where employees can focus more on their core responsibilities rather than logistical hassles.

Ultimately, the seamless blend of real estate and facilities management with employee-centric digital solutions helps organizations attract, retain, and motivate talent by prioritizing their day-to-day comfort and efficiency.

Now that we covered the fundamentals, let’s walk through a practical example. In the following sections, we extend the Employee Self-Service Copilot Agent to allow employees to view food stations or counter by cuisine through the Employee Self-Service Copilot Agent.

## Prerequisites

To extend the Employee Self-Service Copilot Agent with a custom topic for your Real Estate integration, ensure the following prerequisites are met:

- Employee Self-Service Copilot agent is installed in Copilot Studio.
- Maker access to a sandbox or preproduction environment in Copilot Studio.
- Access to [Copilot Samples](https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Facilities/EmployeeSearchDiningStations/topic.yaml) in GitHub.
- Need access to the Dining API that is used to view food stations by cuisine.
- For this example, assume Dining service is built as an independent service on Azure platform.

## Fundamentals

Extending Employee Self-Service for Real Estate and Facilities experiences requires an understanding of a few key building blocks: **topics, adaptive cards, and connectors**. Together, these building blocks define how conversational scenarios are designed and how they interact with Real Estate and Facilities services.

### Topics

In Copilot Studio, a topic is defined as a workflow of a conversation. Microsoft 365 Copilot topics are used to:

- Define trigger phrases that determine when the Dining Search Stations topic should be activated based on user’s natural language input.
- Ask questions and capture necessary inputs from the user, such as cuisine type.
- Trigger an HTTP API call to the backend Dining APIs.
- Interpret the backend API response and return the relevant outcome to the user in natural language.

In the following section, we demonstrate how a maker in Copilot Studio can extend the Employee Self-Service Copilot Agent to support Dining related scenarios.

### Adaptive Cards

Adaptive cards are platform-agnostic UI snippets authored in JSON. They help create interactive and visually appealing cards to capture user inputs while maintaining the conversational flow.

### Connectors

Connectors enable you to connect the agent with other apps, data, and devices in the cloud.

For this example of viewing food stations by cuisines, we assume the Dining service is a custom solution built on Azure. The HTTP connector is used to connect to backend APIs for viewing food stations.

For supported connectors, see: [Connector reference overview](/connectors/connector-reference/)

HTTP request action reference: [HTTP with Microsoft Entra ID (preauthorized) - Connectors](/connectors/webcontents/)

## Example: Search Food Stations by Category

Every café is comprised of multiple stations, and each station is a dedicated area serving a specific type of food or beverage (for example. Espresso, Deli, Dim Sum). These stations give employees choices within the same café.

With the **“Search stations by category”** feature in the Employee Self-Service Copilot Agent, employees can easily find stations serving their preferred cuisine across the office campus. Employees can mention the cuisine (for example. Where can I find Chinese food?) and get stations serving that cuisine.

The employees save time, skip the hassle, and make every meal a choice they love.

### Create a Topic

1. Create a new Topic named **“Dining Search Stations”**.

   a. In Copilot Studio, select **\*Add a topic > From blank**.

   :::image type="content" source="media/facilities-dining-create-new-topic.png" alt-text="Screenshot showing how create a new topic in Copilot Studio.":::

   b. Once inside the topic, select Open code editor.

   c. Copy the topic YAML from the sample repository and paste it into the code editor: [topic.yaml](https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Facilities/EmployeeSearchDiningStations/topic.yaml), and close the editor

   d. Update the HTTP API URL in the code sample. Search for kind: HttpRequestAction. You see a code that sets a value to a variable named SearchStationsApiUrl, as in the screenshot. Update the variable value as per your backend system.

   :::image type="content" source="media/facilities-dining-update-api-url.png" alt-text="Screenshot showing how to update API url in the topic.":::

   e. Resolve any validation errors, and then select Save.

2. Validate

   a. Open the visual representation of the topic and verify the end-to-end flow.

   b. To identify any static issues, run Topic checker

   c. Optionally, follow the next section (Review the topic workflow) for a guided walkthrough of what to verify.

3. Test

   a. In Copilot Studio, select Test to open the test chat.

   b. Ask a question such as Where can I find Chinese food?

   c. After submission, the Employee Self-Service Copilot Agent displays Chinese food options.

### Review the topic workflow

1. Review the Trigger node text (the description shown to users). Adjust it as needed for your scenario.

:::image type="content" source="media/facilities-dining-validate-topic-file-start.png" alt-text="Screenshot showing the model description in the file.":::

2. Confirm that the input variable named `StationCategory` is created. Click on the Details -> Input to check that your topic has input variable named StationCategory as per the screenshot.

:::image type="content" source="media/facilities-dining-validate-topic-details-input.png" alt-text="Screenshot showing the input section of the details.":::

3. Validate that the output variable named SearchStationsApiResponse is created. Click on the Details -> Output to check that your topic has input variable named SearchStationResponse as per the screenshot below.

:::image type="content" source="media/facilities-dining-validate-topic-details-output.png" alt-text="Screenshot showing the output section of the details.":::

4. Validate the conditional block exists that checks user’s input in the input variable.

:::image type="content" source="media/facilities-dining-validate-condition-block-category.png" alt-text="Screenshot showing the conditional block section of the topic details.":::

5. Next node assigns the station category value, cuisine in our case, if the user enters value in your input variable. For example, if the user mentions “Where can I find Italian food?”. The value Italian gets assigned to the input variable.

6. Validate that the HttpConnector is calling appropriate API that belongs to your platform. Also check that the results from the API are captured in the output variable named SearchStationsApiResponse. We're collecting the response in a variable called SearchStationsApiResponse. This response has properties CafeId, CafeName, StationName, CanPurchaseonline etc. You should create a schema per your API response for this topic variable. Your API response may have a different structure, and you should make sure that structure is taken into consideration.

:::image type="content" source="media/facilities-dining-validate-http-request.png" alt-text="Screenshot showing http request block.":::

7. Validate that the conditional block checks if the response is non-empty before the topic ends.

8. Final step is to display the result. You don't need to add any adaptive card here. In the topic description, we mention extracting information from SearchStationApiResponse output variable. LLM follows those instructions and displays well formatted output.

## FAQs

### In the sample, what happens if the API fails to return results?

If the API fails, it returns an empty response. In this case, the conditional block shows an error message telling the user it was unable to find dining information for the cuisine entered, and points them to a link. You should tailor error responses based on your system.

### When I save my topic, it shows errors saying it can't find certain variables. What do I do?

Go to the **Variables** tab and verify all variables (topic and environment) are declared.

### How are error conditions handled?

Conditional branching is used to handle errors and send the appropriate messages to the user.

:::image type="content" source="media/facilities-dining-faq-error-conditions.png" alt-text="Screenshot showing the way to check error conditions.":::

## Additional tips

- Before testing, to identify static issues in your topic definition, use the Topic Checker in Copilot Studio.

- Test your topic using the built-in chat window and review the workflow visually to catch any misconfigurations early.
