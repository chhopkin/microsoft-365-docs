---
title: AI security for Microsoft 365 Copilot
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/05/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
description: Learn how Microsoft 365 Copilot integrates AI to enhance productivity while maintaining robust security and compliance measures.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# AI security for Microsoft 365 Copilot

AI security is foundational to our approach at Microsoft; it safeguards sensitive data, supports system integrity, and supports responsible AI use. This commitment aligns with our broader principles of privacy, compliance, and trust. This article outlines Microsoft's approach to securing Copilot and provides guidance for customers to strengthen their own AI security posture.

## What Microsoft does to secure Microsoft 365 Copilot

Microsoft applies a multi-layered, defense-in-depth strategy to secure Microsoft 365 Copilot at every level, grounded in enterprise-grade security, privacy, and compliance standards. This means that if one layer is breached, others still provide protection. Our approach is guided by the Office of Responsible AI and reinforced by our recently expanded Secure Future Initiative.

### Four key pillars

Our comprehensive security posture for AI has the following pillars:

- Responsible AI development
- Secure engineering and development practices
- Threat intelligence and risk mitigation
- Privacy and compliance by design

Each aspect of this foundation forms a safer digital ecosystem for our customers to confidently adopt AI features and tools.

#### Responsible AI Development

Microsoft embeds its Responsible AI principle-based governance across the entire AI lifecycle to ensure systems are developed and deployed ethically and securely. This strategy helps ensure AI behaves in ways that are trustworthy, responsible, and in alignment with user expectations. These principles are reflected in our transparency documentation. 

To prevent harmful or inappropriate outputs, Microsoft 365 Copilot uses classifiers and metaprompting to detect unsafe prompts and responses to keep behavior in alignment with Microsoft's Responsible AI principles and remains within intended use cases.

Microsoft provides development tools such as content filters, prompt evaluation frameworks, and risk templates to help engineers build secure, trustworthy Copilot experiences aligned with Responsible AI principles.

#### Secure Engineering and Development Practices

Security is integrated from the ground up through our Security Development Lifecycle (SDL). This ensures that vulnerabilities are identified and mitigated early in the development process. We also provide tailored security guidance and best practices for developers, engineers, and security professionals working with Microsoft AI technologies.

Microsoft conducts internal red teaming and commissions third-party assessments that include penetration testing to evaluate Copilot implementations against traditional vulnerabilities and the Open Web Application Security Project (OWASP) Top 10 for LLMs. 

##### Execution Controls

Microsoft 365 Copilot enforces secure coding and architectural safeguards to prevent misuse, including ransomware generation and remote code execution. Malicious patterns are blocked through prompt inspection and content filtering, while sandboxing ensures Copilot operates within constrained execution boundaries.

#### Threat Intelligence and Risk Mitigation

Microsoft 365 Copilot is protected by a multi-layered defense strategy that combines global threat intelligence, AI-specific detection, and architectural containment. Microsoft leverages global threat intelligence to monitor adversarial attacks, model manipulation, and data leakage.  

Key practices include internal red teaming and third-party penetration testing, proactive identification to block malicious inputs, machine learning classifiers, metaprompting, and content filtering to detect prompt injection attempts, including jailbreaks, eXternalized Prompt Injection Attacks (XPIAs), and agentic vulnerabilities. Microsoft 365 Copilot mitigates XPIA and agentic vulnerabilities through layered defenses, including markdown sanitization, malicious prompt classifiers, session hardening, and content security policies. These protections prevent unauthorized actions and data exfiltration across Copilot surfaces and are deployed automatically through Microsoft's cloud infrastructure without customer action required. This also includes continuous testing and containment strategies.

##### Containment by Design

Even in the event of a successful injection attempt, Copilot's architecture ensures containment by design. Copilot operates within the user's identity and access context, limiting the blast radius of any potential compromise. 

- Copilot operates within the user's identity and tenant context
- Copilot only accesses data the user is authorized to view
- All interactions are scoped to existing permissions, preventing lateral movement or unauthorized data access.

##### Audit and eDiscovery

Microsoft Purview captures Copilot interactions for auditing and eDiscovery. Defender for Cloud and AI-SPM provides visibility into AI workloads, plugin usage, and risk scoring. Compliance Manager maps Copilot controls to regulatory frameworks such as GDPR, HIPAA, and the EU AI Act.

##### Prompt Injection Defenses

Multi-layered protections include [classifiers](/ai-services/content-safety/) for jailbreak detection, input/output filtering, and containment strategies. These also defend against encoding-based prompt injection (e.g., ROT13, Base64) through:

- Detection of obfuscated input patterns
- Runtime filters that decode and inspect content before LLM processing
- Regular red teaming to simulate and mitigate encoding-based attacks

##### Data Exfiltration Prevention

Copilot's layered security model addresses traditional and emerging threats, including scenarios with potential for data exfiltration through unauthenticated image URLS where users generate an image containing sensitive data, extract the URL using browser tools and share externally. If the image is accessible without authentication, it may bypass enterprise controls such as Conditional Access or sensitivity labels. Another scenario may include a user from one tenant who generates a malicious image (e.g., QR code) and shares an anonymous URL with users in different tenant. If such a URL is not protected by authentication, access controls may not be enforced. To mitigate this, Microsoft applies its defense-in-depth strategy. This includes continuous monitoring for data leakage vectors, adversarial misuse, and unauthorized access patterns. Microsoft 365 Copilot-generated content is governed by the same access controls and compliance policies as other Microsoft 365 content. This means that user permissions, sensitivity labels, and Conditional Access policies are enforced at the point of content generation and access.

#### Privacy and Compliance by Design

Microsoft 365 Copilot adheres to enterprise-grade privacy and compliance standards. Key safeguards are described in the following sections.

##### Data access enforcement

Copilot respects Microsoft Entra ID permissions and Microsoft Purview policies. This includes strict access controls and sensitivity label inheritance. Policies are enforced via [Microsoft Entra ID](/entra/fundamentals/whatis), [Microsoft Purview](/purview/purview), and [Conditional Access](/entra/identity/conditional-access/overview).

Copilot connectors enhance the value of Copilot while maintaining the same enterprise-grade protections.

##### Access is user-centric

Copilot only accesses data the user is authorized to view and cannot retrieve or act on content the user cannot access directly. 

##### Encryption and isolation

Data is encrypted in transit and at rest using FIPS 140-2–compliant technologies, with tenant-level isolation. Double Key Encryption (DKE) ensures Microsoft cannot access protected content without the customer's key.

##### Compliance tooling

Microsoft Purview Audit and eDiscovery log and surface Copilot interactions. Compliance Manager maps controls to GDPR, HIPAA, DORA, and the EU AI Act. 

Microsoft Purview's Data Security Posture Management (DSPM) for AI provides centralized visibility and control over how sensitive data is accessed and used across Microsoft 365 Copilot and other AI services. It enables organizations to discover AI activity, classify and label sensitive content, enforce real-time data loss prevention (DLP), and govern usage through audit logs, retention policies, and one-click compliance rules. Integrated with Microsoft Purview and Defender, DSPM for AI delivers built-in analytics, risk scoring, and policy enforcement to help organizations manage AI data risks and maintain regulatory readiness. Copilot uses stateless processing and tenant-scoped semantic indexing.

Microsoft 365 Copilot is part of Microsoft's enterprise compliance program and benefits from a range of certifications and assessments. These include (but are not limited to) FedRAMP, HiTrust, SOC 2 Type 1, ISO/IEC 27001, 27701, 22301, 27018, and 42001. Penetration testing summaries are available through the Microsoft Service Trust Portal, helping customers demonstrate due diligence and satisfy third-party audit requirements.

##### Data residency and sovereignty

Advanced Data Residency (ADR) and Multi-Geo capabilities help meet regional requirements. Customers who have purchased ADR or Multi-Geo add-ons can control where certain Microsoft 365 data is stored in accordance with regulatory requirements.

When a user interacts with Copilot, their prompt is processed through a secure orchestration layer that coordinates between Microsoft 365 apps, Microsoft Graph, and the Azure OpenAI Service. The data flow follows these principles: Tenant-aware orchestration: Copilot uses Microsoft Graph to retrieve only the data the user is authorized to access. This includes emails, documents, calendar events, and chats. Regional routing: LLM calls are routed to the nearest Azure region based on the user's Microsoft Entra ID (formerly Azure AD) tenant geography. For example, EU-based tenants have their LLM calls processed within the EU Data Boundary.

Prompts, responses, and data accessed through Microsoft Graph are not used to train foundation LLM. Microsoft's Azure OpenAI Service hosts the LLMs privately and securely. Copilot uses a [stateless LLM architecture](/copilot/microsoft-365/microsoft-365-copilot-privacy#data-stored-about-user-interactions-with-microsoft-365-copilot).

For more information, see the following resources:

- [How Copilot works and how data is protected across its architecture](/copilot/microsoft-365/microsoft-365-copilot-architecture-data-protection-auditing)
- [Microsoft 365 blog: Data residency in the AI era: New capabilities to manage your data](https://www.microsoft.com/en-us/microsoft-365/blog/2024/03/07/data-residency-in-the-ai-era-new-capabilities-to-manage-your-data/)

##### EU data boundary

For eligible EU customers, prompts and responses are processed within the EU, maintaining the same enterprise-grade protections.

> [!NOTE]
> Customers with Multi Geo configurations are not eligible for EUDB commitments. 
> 

For more information, see [What is the EU Data Boundary](/privacy/eudb/eu-data-boundary-learn#how-to-configure-services-for-use-in-the-eu-data-boundary)?

##### Cross-cloud governance for AI workloads

Microsoft Purview and Security Copilot help organizations govern AI across hybrid and multicloud environments like Azure, AWS, and Google Cloud.

- Purview enables consistent data classification, labeling, and policy enforcement across clouds, with visibility into how data flows into AI models and plugins.
- Security Copilot detects AI-related risks across platforms, correlates threats, and surfaces posture insights from [AI-SPM](/azure/defender-for-cloud/concept-cloud-security-posture-management).

##### Policy integration and enforcement

Microsoft Entra ID, Microsoft Purview, and Microsoft 365 for business enforce Conditional Access, sensitivity labels, and information barriers. Copilot-generated responses are governed by the same controls as other Microsoft 365 content. For a list of all supported AI applications and Purview controls, see [Microsoft Purview data security and compliance protections for Microsoft 365 Copilot and other generative AI apps](/purview/ai-microsoft-purview).

[Learn how to Use Microsoft Purview to manage data security & compliance and about sensitivity labels](/purview/ai-m365-copilot).
 
## What you can do to strengthen your organization's AI security

Organizations share responsibility for securing AI systems. Microsoft provides tools and guidance to help customers manage risk and enforce compliance. 

1. Define and apply sensitivity labels in Microsoft Purview to classify confidential content across Microsoft 365.

2. Configure DLP policies that restrict Copilot from accessing or processing labeled content, such as blocking summarization or rewriting of documents marked as sensitive.

3. Ensure users have appropriate permissions (e.g., EXTRACT or VIEW rights) to allow Copilot to interact with content appropriately.

4. When Copilot is restricted from accessing content, users are notified, this interaction can be monitored.

5. Extend DLP coverage across Copilot Chat and in-app experiences in Word, Excel, and PowerPoint for consistent protection.

### Control access to data

Customers and Organizations should apply Microsoft Purview sensitivity labels to classify and protect content, enforce Data Loss Prevention (DLP) policies to block Copilot from accessing sensitive data, and use Double Key Encryption (DKE) to retain exclusive control over encryption keys for highly confidential information.

### Use targeted Conditional Access policies for Copilot

Admins can apply Conditional Access policies directly to Microsoft 365 Copilot and Security Copilot service principals to enforce granular, AI-specific access controls. These policies can be configured using Microsoft Graph PowerShell or the Entra admin center. Administrators can:

- Block access to Copilot for users with elevated insider risk levels
- Require phishing-resistant multifactor authentication (MFA) when users access Copilot from outside the corporate network
- Enforce device compliance and fall back to MFA if compliance cannot be verified
- Use GPS-based or IP-based location data to restrict access to trusted geographic regions or networks


## Frequently asked questions

### Are the results of Microsoft 365 Copilot reliable?  

While Microsoft safeguards provide strong threat mitigation against misinformation and compromise, as with any AI application, Microsoft 365 Copilot's responses might not always be accurate. You should still apply human judgment to check these responses.

### How does Microsoft treat my prompts and responses? 

Microsoft treats prompts and responses as we treat other more traditional forms of content like emails, documents, and chats, and our contractual commitments are the same.

### Does Microsoft 365 Copilot use my data to train AI models? 

Prompts, responses, and Customer Data accessed through Microsoft Graph aren't used to train foundation LLMs, including those used by Microsoft 365 Copilot. Product improvements are driven through techniques such as customer-reported incidents and synthetic prompt generation.

### What should I do if I see unexpected or offensive content?  

Report any disturbing or suspicious content immediately by selecting the downvote (thumbs down) button beside the prompt response.

### How can I access the Microsoft 365 Copilot vulnerability assessment report?  

The third-party vulnerability assessment of Microsoft 365 Copilot can be downloaded from [Service Trust Portal](https://servicetrust.microsoft.com/DocumentPage/67d59873-b315-4768-a057-8583cd84680a).

### Can Microsoft help me find risks in my AI applications?  

Microsoft has released Python Risk Identification Toolkit for generative AI ([PyRIT](https://github.com/Azure/PyRIT)), an open access automation framework that aims to empower security professionals and machine learning engineers to proactively [find risks](https://www.microsoft.com/security/blog/2024/02/22/announcing-microsofts-open-automation-framework-to-red-team-generative-ai-systems/) in their own generative AI systems. 

### Does Microsoft 365 Copilot have access to data I don't have when grounding content? 

Microsoft 365 Copilot accesses resources on behalf of the user, so it can only access resources you already have permission to access.  

Grounding occurs within the context of your identity, and the semantic index and graph queries are "security trimmed" based on your permissions for the underlying content. This process ensures that only authorized content is included in the grounding process.

### How can I limit data that Microsoft 365 Copilot can use?

The following steps can help administrators control user access and therefore limit what data Microsoft 365 Copilot can use:

- [Restrict SharePoint site access](/sharepoint/restricted-access-control) and [OneDrive content access](/sharepoint/onedrive-site-access-restriction) to specific groups, even after content has been overshared.
- [Use Restricted SharePoint Search](/sharepoint/restricted-sharepoint-search) to limit the websites from which Microsoft 365 Copilot is permitted to reference content.
- [Use Microsoft SharePoint Premium - SharePoint Advanced Management](/sharepoint/advanced-management), which offers reports and tools to analyze and manage overly permissive access-control lists and sharing links across the environment.
- [Review information protection considerations](/purview/ai-microsoft-purview-considerations#information-protection-considerations-for-copilot) for Copilot. Microsoft 365 Copilot honors EXTRACT permissions and automatically [inherits sensitivity labels](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-purview-service-description#microsoft-purview-information-protection-sensitivity-labeling) from referenced content to Copilot-generated responses and files.
- [Apply sensitivity labels](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) to your Microsoft 365 files and email. For Microsoft Purview customers, administrators can [create and configure sensitivity labels](/purview/create-sensitivity-labels) that they want to make available for apps and other services.
- [Use Microsoft Purview Data Security Posture Management for AI](/purview/ai-microsoft-purview) (currently in preview) to discover sensitive data shared with Copilot, see files referenced in Copilot responses, and discover unlabeled files referenced by Copilot and associated SharePoint sites, thereby letting you identify and protect files at risk of overexposure.
- Set up policies that remove old and unused data and limit data sprawl due to data oversharing with [Microsoft Purview Data Lifecycle Management](/purview/data-lifecycle-management).

### How can I use Microsoft security solutions to protect data and AI application interactions?

Microsoft always recommends that you build a strong security foundation for your enterprise. The [Zero Trust](/security/zero-trust/copilots/zero-trust-microsoft-365-copilot) security strategy provides guidance for such a foundation because it treats each connection and resource request as though it originated from an uncontrolled network and a threat actor. Regardless of where the request originates or what resource it accesses, use Zero Trust principles.  

Our comprehensive security solutions—including Microsoft Defender, Entra, Purview, and Intune—work together to help secure your data and interactions in Microsoft 365 Copilot and other AI applications. These products have capabilities that empower you and your teams to: 

- **Identify potential risks related to AI use,** such as sensitive data leaks and unauthorized access to high-risk applications

- **Secure the AI applications** and the sensitive data they process or generate, including prompts and responses

- **Govern AI use responsibly** by retaining and logging interactions, detecting policy violations, and investigating incidents  

For example, we recently introduced new Microsoft Defender and Purview capabilities that provide purpose-built tools for robust security and governance of generative AI applications and their data. In addition, the seamless integration of [Microsoft Security Copilot](/copilot/security/microsoft-security-copilot) across our products streamlines the overall process and experience for security analysts. By prioritizing security and offering these advanced features, Microsoft empowers organizations to confidently apply the benefits and opportunities AI applications provide.

### Where should I report vulnerabilities in Microsoft 365 Copilot and other AI applications? 

If you discover new vulnerabilities in any AI platform, we encourage you to follow responsible disclosure practices for the platform owner. Microsoft's own procedure (for Copilot) is explained in this page: [Microsoft AI Bounty Program](https://www.microsoft.com/msrc/bounty-ai).
