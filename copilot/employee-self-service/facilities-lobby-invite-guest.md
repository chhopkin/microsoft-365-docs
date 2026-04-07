---
title: Invite a Guest to Campus
f1.keywords: NOCSH
ms.author: heidip
author: apoorvg
manager: sudhakarms
ms.reviewer: MicrosoftHeidi
ms.date: 11/05/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.subservice: ess-agent
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about extending the Employee Self-Service tailored to your organization. This article describes the steps to invite a guest to offices (Lobby) via ESS. Example - "I want to invite my spouse to Building 32"
appliesto:
- ✅ Microsoft 365 Copilot
---
# Extending Employee Self-Service Agent

The Employee Self-Service (ESS) Copilot Agent allows employees to get their queries answered from admin-configured knowledge sources, HCM and IT systems, directly within Microsoft 365 Copilot.

An organization may seek to enhance ESS by integrating additional capabilities that enable employees to maximize the benefits of ESS and support their work-related activities.

To support these needs, ESS is designed to be extensible. You can create and publish your own topics that work seamlessly alongside the built-in ones. This article explains the steps to extend ESS by adding new topics tailored to your organization.

At Microsoft, we have extended ESS to bring in Real Estate and Facilities related experiences like allowing employees to register their vehicle (Parking), create a facilities ticket (Facilities), view available food stations by cuisine (Dining), or invite their guest to offices (Lobby) via ESS.

Some scenarios that this extensibility to ESS is helping us power:

- Create a Facilities Ticket, for example, “I want to report a water leak”
- Register a Vehicle, for example, “I want to register my vehicle Tesla Model 3”
- View food stations or counters by cuisine, for example, “Where can I find Chinese food?”
- Invite a Guest, e.g. "I want to invite my spouse to Building 32".

In the following section, we will see how a maker in Copilot Studio can extend ESS to support the above scenarios. But before we dive into the maker experience, let’s understand what real estate and facilities are and how they support employees.

## Real Estate & Facilities

Real Estate and Facilities (RE&F) play a pivotal role in shaping the overall employee experience within an organisation. By integrating RE&F services into Employee Self-Service (ESS) platforms, companies can streamline access to essential workplace amenities and administrative tasks, making daily operations more efficient and user-friendly for employees.

For instance, features like vehicle registration for parking, facilities ticketing for maintenance requests, access to café menus, and streamlined guest invitation processes empower employees to manage their work environment proactively. These capabilities reduce administrative overhead, minimise wait times, and improve satisfaction by giving employees greater control and visibility over their workplace needs.

Moreover, such integrated experiences foster a sense of belonging and engagement, as employees feel supported by systems that anticipate and address their requirements. This not only enhances productivity but also contributes to a positive organisational culture where employees can focus more on their core responsibilities rather than logistical hassles.

Ultimately, the seamless blend of real estate and facilities management with employee-centric digital solutions helps organisations attract, retain, and motivate talent by prioritising their day-to-day comfort and efficiency.

Now that we have covered the fundamentals, let’s walk through a practical example. In the following sections, we will extend the ESS Agent to allow employees to perform various operations through the ESS Copilot Agent.

## Pre-requisites

To extend the ESS Copilot Agent with a custom *Invite a guest* topic, ensure the following prerequisites are met:

- ESS agent is installed in Copilot Studio.
- Access to Copilot Samples in GitHub:  
  https://github.com/microsoft/CopilotStudioSamples/tree/main/EmployeeSelfServiceAgent/Facilities/EmployeeInviteGuest
- Maker access to a sandbox or pre-production environment in Copilot Studio.
- Access to the Guest Management APIs that will be used to fetch the list of buildings and create guest invitations.
    - For this example of inviting a guest to office, we assume the Guest Management system is a custom solution built on the Azure platform.

## Fundamentals

Extending ESS for RE&F experiences requires an understanding of a few key building blocks: **topics, adaptive cards, and connectors**. Together, these define how conversational scenarios are designed and how they interact with RE&F services.

### Topics

In Copilot Studio, a topic is defined as a workflow of a conversation. Microsoft 365 Copilot topics are used to:

- Define trigger prompts that determine when the *Invite a guest* topic should be activated based on user’s natural language input.
- Ask questions and capture necessary inputs from the user, such as building information and guest details like name, email, and purpose of visit.
- Present a guest registration form where users can fill in required details.
- Trigger an HTTP API call to the backend Guest Management APIs.
- Interpret the backend API response and return the relevant outcome to the user in natural language.

### Adaptive Cards

Adaptive cards are platform-agnostic UI snippets authored in JSON. They help create interactive and visually appealing cards to capture user inputs while maintaining the conversational flow.

### Connectors

Connectors enable you to connect the agent with other apps, data, and devices in the cloud.

For this example of inviting a guest to office, we assume the Guest Management system is a custom solution built on Azure. The HTTP connector is used to connect to backend APIs for creating a guest invitation.

Available connectors:  
https://learn.microsoft.com/connectors/connector-reference/

HTTP request action reference:  
https://learn.microsoft.com/microsoft-copilot-studio/authoring-http-node

## Example: Invite a Guest

In the **Invite a Guest** scenario, an employee can pre-register a visitor such as a business partner, vendor, interview candidate, or personal guest.

hrough the Employee Self-Service (ESS) platform, the employee can initiate a guest invitation by providing essential details like the guest’s name, contact information, visit date, time, and purpose. The system validates the request and registers the guest with visitor management system, sends an invitation mail with arrival instructions to the guest, and notifies the reception team about their arrival. This ensures a smooth check-in experience for the guest while maintaining workplace security and operational efficiency. 

This process involves only one step: 

- **Creating a topic**: Define the workflow, trigger prompts, and instructions for the guest invite scenario.
  - Design an Adaptive card to capture guest visit details, and to build binding inputs to state variables for API requests.
  - Validate API responses, handle errors, and provide user feedback.

### Create a Topic

- Create a topic named **Invite a guest**
  - In Copilot Studio, select **Add a topic > From blank > Open code editor**
        :::image type="content" source="media/facilities-lobby-invite-guest-create-topic.png" alt-text="Screenshot showing how to create a topic in Copilot Studio.":::

        :::image type="content" source="media/facilities-lobby-invite-guest-create-topic-code-editor.png" alt-text="Screenshot showing how to open a code editor for a topic in Copilot Studio.":::

    - Use the code from the Copilot Samples repository and paste in the code editor:  
      <https://github.com/microsoft/CopilotStudioSamples/blob/main/EmployeeSelfServiceAgent/Facilities/EmployeeInviteGuest/topic.yaml>
    - Update the HTTP API URL in the code sample. Search for “kind: HttpRequestAction” and update the URL property as per your backend system.
    - Save the topic
- Validate
  - Open the visual representation of the topic definition and validate the workflow of the topic.
    - Click on Topic Checker for any static issues with the definition.
    - Optionally, follow the below section "Validate the Topic" to understand and validate the steps.
- Now, let's test the newly added topic
  - Using the **Test** button in Copilot studio, open the test chat window.
    - Invite guest using the prompt “Invite my guest to the office”
    :::image type="content" source="media/facilities-lobby-invite-guest-form.png" alt-text="Screenshot showing the guest invitation form in the ESS agent.":::
    - Upon successful submission, ESS displays a confirmation message.
    :::image type="content" source="media/facilities-lobby-invite-guest-response.png" alt-text="Screenshot showing the guest invited confirmation message in the ESS agent.":::

### Validate the Topic

- The Trigger node will capture the topic description, which is visible from the user interface. You can use M365 copilot to fine-tune as per your requirements.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-trigger.png" alt-text="Screenshot showing the trigger node configuration for the Invite a guest topic.":::

- In the subsequent nodes, we enforce certain limitations - like supporting only single guest visits and supporting only new visits and not edit/cancellation of existing visits.
  - This is optional step and to implement this, few variables are maintained based on the user query and then used in a group of conditional statements as shown in screenshot below. 
  - If these restrictions are not required, remove them by deleting the corresponding variables and condition nodes (shown in the pictures below).

- The subsequent node makes an HTTP call to the backend API to fetch all buildings; these buildings are prepopulated in the guest registration form that gets rendered in the upcoming steps. We have used HttpRequestAction component for making the HTTP call. This can be alternatively configured in several other ways described in the connectors section above.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-Buildings.png" alt-text="Screenshot showing the HTTP request node that fetches all buildings.":::

- In the next node, we use a bunch of Customize Response nodes to determine the guest visit purpose and location from the user query to auto-populate in the guest invite form. This is added for an enriched user experience; however, this is optional and the corresponding nodes can be omitted as per requirements.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-response-instructions.png" alt-text="Screenshot showing the Customize Response nodes for visit purpose and location.":::

- Verify the guest invite adaptive card with action buttons. Currently the required input parameters for creating a guest visit are - guest first name, last name, email, meeting purpose and meeting location (name of the building). Users can add or modify input fields as needed.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-adative-card.png" alt-text="Screenshot showing the adaptive card fields for the guest invitation form.":::

- In the next step, an HTTP call is made to the backend create invite API with all the collected information forwarded with the request.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-httpnode-create.png" alt-text="Screenshot showing the HTTP request node that creates the guest invite.":::

- The following steps determine if the visit creation was successful and display a message to the user accordingly. 
  - Upon successful submission, the Employee Self-Service (ESS) system will display a confirmation of the visit creation for the user’s guest.
  - In case the request failed due to any reason, a failure message is sent to the user. These messages can be customized by modifying the corresponding SendActivity components.

:::image type="content" source="media/facilities-lobby-invite-guest-validate-topic-error-handling.png" alt-text="Screenshot showing the success and failure handling nodes in the topic.":::

## FAQs

### I need to configure the API call as per my requirement. What should I do?

We have used *HttpRequestAction* component for making the HTTP calls. As a start, you can use the same and modify it as per your needs. (There are also several other ways to configure this as described in the connectors section above)

- Expand the *HttpRequestAction* node, and in the URL section click on Select variable -> Formula to update your backend API URL. Click Insert to save the URL.

:::image type="content" source="media/facilities-lobby-invite-guest-HttpRequestAction.png" alt-text="Screenshot showing the HttpRequestAction component configuration.":::

- Select the appropriate http request method from the method dropdown
:::image type="content" source="media/facilities-lobby-invite-guest-HttpRequestAction-method.png" alt-text="Screenshot showing the HTTP method configuration in HttpRequestAction.":::

- Now, add the required headers, request body and error handling as per your backend API definition
:::image type="content" source="media/facilities-lobby-invite-guest-HttpRequestAction-headers-body.png" alt-text="Screenshot showing the headers and body configuration in HttpRequestAction.":::

- Set the appropriate Response type as per your backend contracts
:::image type="content" source="media/facilities-lobby-invite-guest-HttpRequestAction-contract.png" alt-text="Screenshot showing the response data type configuration in HttpRequestAction.":::

- Save the response in a state variable to access it in the later steps
:::image type="content" source="media/facilities-lobby-invite-guest-HttpRequestAction-variable.png" alt-text="Screenshot showing how to save the API response to a state variable.":::

### How are error conditions handled?

Towards the end of the topic, you will see conditional branching as shown in the image below, which is used to handle errors and send the appropriate messages to the user. These can be customized, and any additional conditions can be added to the same condition group.

:::image type="content" source="media/facilities-lobby-invite-guest-conditional-branching.png" alt-text="Screenshot showing conditional branching for error handling in the topic.":::

### What should I do if I get an error message?

Depending on the error message, check the following:

- **API configuration**: Ensure the HTTP API URL in your topic definition is correct and points to the intended backend system. Double-check for typos or outdated endpoints.
- **Request method**: Verify that the HTTP request method (GET, POST, PUT) matches the expected operation for your backend API.
- **Headers and body**: Confirm that all required headers (for example, authentication scope, content type) and request body parameters are correctly set as per your backend API specification.
- **Response data type**: Make sure the response data type in your topic matches what your backend API returns (for example, Record, Table, String).
- **State variables**: Check that responses from API calls are being saved to the correct state variables for use in subsequent steps.
- **Error handling logic**: Review the conditional nodes at the end of your topic to ensure error conditions are properly handled and user-friendly messages are displayed.

### The guest registration form isn't showing the list of buildings. Why?

- Confirm that the API call to fetch buildings is correctly configured and the response is being saved to the appropriate variable.
- Check for any changes in the backend API contract or endpoint.

### My API call returns a blank or unexpected response. What could be wrong?

- Validate the request headers and body parameters.
- Ensure the response data type matches the backend API output.
- Review the backend API logs for errors or contract mismatches.

### Additional tips

- Use the Topic Checker in Copilot Studio to identify static issues in your topic definition before testing
- Test your topic using the built-in chat window and review the workflow visually to catch any misconfigurations early.