---
title: Copilot Tuning Optimization agent
author: lauragra
ms.author: lauragra
manager: calvind
ms.collection: operations-pod
ms.reviewer: riyazp
ms.date: 02/19/2026
ms.service: microsoft-365-copilot
ms.topic: how-to
ms.localizationpriority: medium
description: Learn how to use Copilot Tuning to build an AI model for optimization problems.
---

# Copilot Tuning Optimization agent

The **Optimization** agent for Microsoft 365 Copilot helps you model and solve business optimization problems that are specific to your organization. You can use the agent to make optimal decisions for scenarios such as organizing teams, assign work, or plan sales strategies.

Describe your optimization problem by specifying goals, constraints, and data. The Optimization agent computes an optimal solution based on those inputs, without requiring expertise in coding or mathematical modeling.

## Optimization agent overview

The Optimization agent enables you to solve decision-based business problems by defining:

- **Goals**, such as assigning people to projects based on skills or planning sales territories
- **Rules and preferences**, such as keeping existing teams together or staying within budget
- **Data**, such as lists of employees, projects, or territories

After you provide this information, the agent uses solver tools to compute an optimal solution that satisfies all constraints and objectives. Results are presented in an interactive experience and can be downloaded as a CSV file.

Common use cases include:

- Workforce and talent deployment
- Resource and task assignment
- Sales territory and account planning

The Optimization agent is designed for nontechnical users and produces **optimal, explainable decisions** with **guaranteed constraint satisfaction**.

The agent can also be customized to align with your organization’s policies, terminology, and data patterns so that it reflects how your organization operates.

At its core, the Optimization agent uses a customized large language model (LLM) designed for optimization tasks. The model translates your business goals, rules, and data into a solvable optimization problem and computes the optimal outcome in a way that's consistent with your organization’s preferences.

## Get started with the Optimization agent

### Describe your goal

Start by explaining the decision you want to optimize. Include context and details to help the agent understand the problem.

Examples include:

- Assign employees to open roles based on their skills.
- Allocate salespeople to territories.

:::image type="content" source="media/copilot-tuning-optimization-agent/image1.png" alt-text="":::

### Upload your data

Provide one or more CSV files that contain the data required for optimization, such as employees, projects, roles, or territories. Using separate files for different data entities improves accuracy and interpretability.

### Set rules and objectives

Define constraints and objectives that govern the solution.

- **Constraints** describe rules that must be followed, such as staying within budget, keeping teams in the same location, or ensuring required role coverage.
- **Objectives** describe what makes a solution optimal, such as maximizing skill alignment, minimizing travel distance, or reducing wait time.

You can add multiple constraints and objectives. For best results, add them one at a time and describe them clearly. The agent might ask clarifying questions if more detail is required.

:::image type="content" source="media/copilot-tuning-optimization-agent/image2.png" alt-text="":::

### Review the setup

As you interact with the agent, a side panel shows how your problem is interpreted, including:

- Goals
- Decision variables
- Constraints
- Objectives
- Uploaded data

You can ask the agent to edit or remove any part of the setup.

### Clarify as needed

If the agent detects ambiguity or missing information, it prompts you to clarify constraints or objectives to ensure the problem is feasible and solvable.

:::image type="content" source="media/copilot-tuning-optimization-agent/image3.png" alt-text="":::

### Get your solution

When you're ready, ask the agent to solve the problem using your data. The agent runs solver tools and presents the optimal solution based on your objectives and constraints. You can review the results interactively and download the full output as a CSV file.

:::image type="content" source="media/copilot-tuning-optimization-agent/image4.png" alt-text="":::

> **Tip**  
> Use clear, specific language and provide accurate, representative data to achieve the best results.

## Key capabilities

The Optimization agent:

- Interprets your business scenario to define the optimization goal
- Identifies decision variables that represent the choices to be optimized
- Translates objectives and constraints into a structured optimization problem
- Uses solver tools to compute an optimal solution

The resulting solution:

- Satisfies all defined constraints
- Represents the most optimal outcome for the provided data

## When to use the Optimization agent

Use the Optimization agent when you need to determine the best possible decision under constraints. Start by identifying the decision you want to optimize.

### Identify the decision

Determine what choice needs to be made, such as assigning resources, scheduling activities, or allocating territories. If no decision is required, the Optimization agent might not be the right tool.

### Define objectives

Specify criteria that define a good outcome. You can include one or more objectives.

Example: Minimizing travel costs across sales assignments.

### Define rules and limits

Identify constraints that must be followed, such as capacity limits, role requirements, or location policies.

### Prepare your data

Provide data that supports your objectives and constraints. For example, capacity limits require data about resource availability, and travel optimization requires location data.

### Break down complex problems

Large optimization problems can often be split into smaller, related decisions that are easier to model and solve.

The Optimization agent isn't intended for general data analysis or mathematical computation scenarios.

## Limitations

- Only CSV files are supported.
- You can upload multiple CSV files, subject to file count and size limits.
- You can define any number of constraints and objectives through chat.

## Tuned context agents

A **tuned context agent** lets you save a custom optimization problem for reuse across your organization. The agent remembers your problem structure, including goals, constraints, objectives, and data schema.

This approach is useful for recurring decisions, such as quarterly planning, annual reviews, or scenarios reused across teams or functions.

### When to use a tuned context agent

Use a tuned context agent when:

- You want to set up an optimization problem once and reuse it
- You need the agent to remember your rules, preferences, and data structure
- You want to share a customized agent with others in your organization

### What the agent remembers

A tuned context agent stores:

- The base optimization problem, including goals, objectives, and constraints
- The data schema, such as field names and data types

The agent does **not** store uploaded data files.

## Tune an Optimization agent

1. **Create a new agent**  
   Create a new agent by selecting the **Optimization** template.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image5.png" alt-text="":::

2. **Update agent details**  
   Provide a name, description, and suggested prompts. Default instructions are prefilled and optimized for the Optimization agent.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image6.png" alt-text="":::

   > **Important**  
   > - Leave the default instructions unchanged unless you have a specific reason to edit them.  
   > - Do not add capabilities or knowledge sources. The Optimization agent does not support them.

3. **Create the agent**  
   Select **Create** to finish setup and open the agent chat.

4. **Start tuning**  
   Select **Tune agent**, then choose **Tune context**.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image7.png" alt-text="":::

5. **Define the optimization problem**  
   Use chat to describe your goal, upload data, define constraints, and specify objectives. Review the setup in the side panel as you go.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image8.png" alt-text="":::
   :::image type="content" source="media/copilot-tuning-optimization-agent/image9.png" alt-text="":::

6. **Save the context**  
   After completing the setup, select **Update agent** to save the problem definition.

   > **Note**  
   > Uploaded data isn't saved. Only the problem structure is retained.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image10.png" alt-text="":::

7. **Share the agent**  
   Share the tuned agent with others in your organization.

   :::image type="content" source="media/copilot-tuning-optimization-agent/image11.png" alt-text="":::
   :::image type="content" source="media/copilot-tuning-optimization-agent/image12.png" alt-text="":::

### Sharing and security

- You control who can access the agent.
- Agent context stays within your organization.
- Uploaded data isn't stored.

### Best practices

- Use precise language for goals, constraints, and objectives.
- Test the agent with sample data before sharing it widely.
- Update the agent as business requirements change.

## Example: Sales strategy optimization

**Scenario**  
Plan a sales strategy for a fiscal year by assigning sales teams to territories while maintaining key account relationships, managing travel costs, and meeting sales targets.

**Goal**  
Assign sales personnel to sales territories.

**Data files**

Provide CSV files such as:

- *People.csv*: Salesperson details
- *Territories.csv*: Territory attributes
- *Roles.csv*: Role limits and coverage
- *States.csv*: Location data for travel calculations

**Objectives**

- Maximize continuity by preserving existing account assignments
- Maximize coverage of people-to-territory assignments
- Minimize total travel distance

**Constraints**

- Salespeople can be assigned only within a single industry vertical
- Role-specific limits on territory assignments must be respected
- Each territory must have required role coverage

Decision variables are generated automatically and represent assignment choices. The agent computes optimal values and presents the results in an easy-to-understand format.

## FAQ

### What is the Optimization agent?

The Optimization agent helps you solve decision-based business problems, such as resource allocation, scheduling, and planning, by computing optimal solutions based on goals, constraints, and data.

### Do I need technical skills to use it?

No. You describe the problem in plain language and provide data. The agent handles the optimization logic.

### What types of problems are supported?

Examples include:

- Assigning employees to roles or projects
- Planning sales territories
- Scheduling shifts
- Organizing resources

### How is my data handled?

Your data remains within your tenant and is used only during the conversation to compute solutions. Tuned context agents store only problem definitions and data schema, not data or results.

### Can I change rules later?

Yes. You can modify constraints and objectives. Significant changes that alter the problem structure might require creating a new agent.

### What file formats are supported?

Only CSV files are supported.

### What happens if the problem is infeasible?

The agent alerts you if constraints or data make the problem unsolvable and provides guidance to help you adjust the setup.

## Related content

- [Copilot Tuning overview](copilot-tuning-overview.md)