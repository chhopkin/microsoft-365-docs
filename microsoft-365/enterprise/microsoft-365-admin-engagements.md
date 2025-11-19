---
title: "Engagements in the Microsoft 365 Admin Center Enhanced engagements section"
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
manager: dansimp
ms.date: 11/19/2025
audience: Admin
ms.reviewer: dansimp
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: 
- m365admin
description: The Engagements pivot in Enhanced engagements offers a centralized overview of all customer-specific engagements with Microsoft.
ai-usage: ai-assisted  
---

# Engagements in Enhanced Engagements

The Engagements pivot in Enhanced engagements offers a centralized overview of all customer-specific engagements with Microsoft. This section allows users to request and track engineering-led escalations, post-incident analyses, Business Process Awareness (BPAs), and Customer Advisory Board (CAB) discussions. Each engagement type provides detailed insights, status updates, and filtering options to help manage support efficiently.

:::image type="content" source="../enterprise/media/enhanced-engagements/enhanced-engagements-mcs.png" alt-text="Screenshot of engagemnts landing page in enhanced engagements portal." lightbox="../enterprise/media/enhanced-engagements/enhanced-engagements-mcs.png":::

## Engineering Escalations

The Engineering Escalations view under Enhanced Engagements provides visibility into all engineering-level support escalations raised for your tenant. These include cases submitted directly by your organization through the _Escalate to Engineering_ feature, and issues elevated by Microsoft Support when advanced troubleshooting is required.
This view helps monitor escalation activity, review trends, and gain insights into how issues are distributed across products, severity levels, and sources.

### Overview of Engineering Escalations

At the top of the page, several visual summaries provide quick insights into your tenant’s escalation activity:

- **Total escalations** – The total number of escalations associated with your tenant.
- **Open escalations** – The number of currently active or unresolved escalations.
- **Escalations by product** – A workload-based view that shows how many escalations relate to services such as Microsoft Exchange, SharePoint, or Teams.
- **Customer raised escalations** – Displays the number of escalations initiated directly by your organization.
- **Distribution by escalation source** – A chart showing whether escalations were raised by your organization or Microsoft Support.
- **Distribution by severity** – Summarizes escalations by severity level (Severity 1, A, B, or C).
- **Escalations per week by status** – A trend chart showing how many escalations were created and closed each week.

> [!NOTE]
> These insights update automatically as new escalations are raised or resolved.

### Escalation report

Below the overview section, the Escalation report provides a detailed, filterable table of all active and historical escalations for your tenant. You can use this table to review case progress, assigned severity, and escalation sources.

You can:

- **Search** by title, ticket number, or keywords.
- **Filter** by status, product, severity, or escalation source.
- **Refresh** the data to view the most recent updates.
- **Export** the results for reporting or analysis.

| Column | Description |
|---------|---------|
| **Title** | The name or brief summary of the escalation.|
| **Created by** | The user who initiated the escalation. |
| **Ticket** | The unique escalation identifier.|
| **Severity** | Indicates the escalation’s priority (for example, _A_, _B_, _C_, or _1_).|
| **Escalation date** | When the escalation was created.|
| **Status** | The current state of the escalation (_Open_, _Closed_, _In Progress_). |
| **Escalation source** | Identifies whether the escalation originated from your organization or from Microsoft Support.|

> [!TIP]
> Combine filters and charts to spot recurring escalation trends or identify products that require the most attention.

### Benefits of Engineering Escalations

The Engineering Escalations view helps your organization:

- Maintain visibility into engineering-level escalations.
- Understand patterns across products and severity levels.
- Identify and manage high-impact issues efficiently.
- Improve collaboration with Microsoft support and engineering teams.

## Customer Advisory Board (CAB)

The Customer Advisory Board offers you a prioritized voice into the evolution of Microsoft 365 through various virtual and in-person engagements with engineering, designed to facilitate roadmap discussions and feedback loops into all in-scope product teams.

:::image type="content" source="../enterprise/media/enhanced-engagements/customer-advisory-board.png" alt-text="Screenshot of customer advisory board in enhanced engagements portal." lightbox="../enterprise/media/enhanced-engagements/customer-advisory-board.png":::

### CAB overview

The CAB overview section provides quick access to recent and upcoming engagement details.

- **Last completed event** – Displays the most recent in-person CAB event and links to its feedback form.
- **Upcoming CAB event** – Shows the next scheduled in-person CAB session.
- **Last completed community call** – Displays the most recent virtual community call and provides a feedback link.
- **Upcoming community call** – Highlights the next scheduled community call.

If a CAB event or call hasn’t been scheduled yet, the corresponding date and details won't be displayed. These fields automatically update once new schedule information becomes available.
If a CAB event or call hasn’t been scheduled yet, the corresponding date and details won't be displayed. These fields automatically update once new schedule information becomes available.

> [!NOTE]
> CAB event and call details are refreshed periodically. When no upcoming events are listed, it means the schedule is still being finalized and will appear once available.

### Upcoming CAB schedule

The **Upcoming CAB schedule** lists all planned engagements with Microsoft 365 engineering teams. Each entry provides event details, topics, audience, and registration information.
You can:

- **View** upcoming and past CAB sessions.
- **Export** the schedule for tracking and internal coordination.
- **Register** for upcoming sessions directly from the portal.

Each schedule entry includes:

| Column | Description |
|---------|---------|
| **Column** | Start and end dates for the CAB engagement |
| **Dates** | Title of the CAB session or community call |
| **Event** | Microsoft 365 workload impacted |
| **Topic** | Key discussion areas (for example, product roadmap updates, feature deep dives)|
| **Audience** | Recommended participants (for example, CIOs, CTOs, IT Admins) |
| **Registration Info** | Direct registration links or invitation details |

> [!TIP]
> If registration details aren’t available for an upcoming event, check back later. The information will appear automatically once registration links are available.

### Benefits of CAB

The Customer Advisory Board program allows you to:

- Engage directly with Microsoft engineering teams.
- Preview and provide feedback on Microsoft 365 roadmap plans.
- Network with peers across industries facing similar challenges.
- Influence future product and service enhancements.

### OIA Overview

The OIA Overview section provides a snapshot of the current state of your post-incident analysis requests:

- **Total OIAs**: Displays the total number of open post-incident analysis requests.
- **Active OIAs**: Shows the number of active requests that are being worked on.

### Active OIAs by Workload

This section breaks down your active post-incident analysis requests by workload type:

- **Exchange**: The number of active analysis requests related to Exchange incidents.
- **SharePoint**: The number of active analysis requests related to SharePoint incidents.
- **Teams**: The number of active analysis requests related to Teams incidents.

### Incident analysis filters

You can refine your view of the incident analysis requests by using the following filters:

- **Status**: Filter by the current status of the request (for example, _Submitted_, _Completed_).
- **Created By**: Filter by the user who created the request.
- **Product**: Filter by the product associated with the incident (for example, _Exchange_, _SharePoint_, _Teams_).

### Request Report

The **Request Report** section displays a table with all the post-incident analysis requests that have been submitted. For each request, you can see the following details:

- **Ticket #**: The unique identifier for the incident.
- **Case Title**: The title of the incident request.
- **Status**: The current status of the request (for example, _Submitted_, _Completed_).
- **Created By**: The user who created the request.
- **Date Created**: The date when the request was created.
- **Product**: The product associated with the incident (for example, _Exchange_, _SharePoint_, _Teams_).

### Navigation and Pagination

The request report is displayed in a paginated table format. You can navigate through the pages of requests by using the pagination controls at the bottom of the table:

- **Next** and **Previous** arrows allow you to move between pages.
- The **Items per page** selector lets you adjust how many requests are displayed on each page.
