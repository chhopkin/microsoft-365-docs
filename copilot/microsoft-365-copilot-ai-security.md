---
title: AI security for Microsoft 365 Copilot
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.reviewer: georgerozo
ms.date: 08/26/2025
ms.update-cycle: 180-days
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- trust-pod
- magic-ai-copilot
description: Learn how Microsoft 365 Copilot integrates AI to enhance productivity while maintaining robust security and compliance measures.
appliesto:
- ✅ Microsoft 365 Copilot
---

# AI security for Microsoft 365 Copilot

AI security is foundational to our approach at Microsoft; it safeguards customer data, supports system integrity, and includes user safety features. This commitment aligns with our broader principles of privacy, compliance, and trust. This article outlines Microsoft's approach to securing Microsoft 365 Copilot and provides guidance you can use to strengthen your AI security posture.

## What Microsoft does to secure Microsoft 365 Copilot

Microsoft applies a multi-layered, defense-in-depth strategy to secure Microsoft 365 Copilot at every level, grounded in enterprise-grade security, privacy, and compliance standards. This means that if one layer is breached, others still provide protection. Microsoft's approach is guided by [Responsible AI principles](https://www.microsoft.com/en-us/ai/responsible-ai) and reinforced by the recently expanded [Secure Future Initiative](https://aka.ms/SFIwebsite).

Our comprehensive security posture for AI includes:

- Secure engineering and development practices
- Threat intelligence and risk mitigation
- Privacy and compliance by design

Each aspect of this foundation forms a safer digital ecosystem for you to confidently adopt AI features and tools.

In addition, Microsoft embeds its Responsible AI principle-based governance across the entire AI lifecycle to help ensure systems are developed and deployed ethically and securely. This strategy helps ensure AI behaves in ways that are trustworthy, responsible, and in alignment with user expectations. A core part of the Responsible AI program is designed to identify potential risks, measure their propensity to occur, and build mitigations to manage them, outlined in [Transparency note for Microsoft 365 Copilot: Mapping, measuring, and managing risks](/copilot/microsoft-365/microsoft-365-copilot-transparency-note#mapping-measuring-and-managing-risks).

### Secure engineering and development practices

Security is integrated from the ground up through our [Security Development Lifecycle](https://www.microsoft.com/en-us/securityengineering/sdl/) (SDL). This integration helps ensure that vulnerabilities are identified and mitigated early in the development process. Microsoft also provides tailored security guidance and best practices for developers, engineers, and security professionals working with Microsoft AI technologies. See [Build a strong security posture for AI](/security/security-for-ai/posture).

#### Assessments and testing

Microsoft conducts internal red teaming and commissions third-party assessments that include penetration testing. These assessments help evaluate Microsoft 365 Copilot implementations against traditional vulnerabilities and the [Open Web Application Security Project (OWASP) Top 10 for LLMs](https://owasp.org/www-project-top-10-for-large-language-model-applications/). To see the assessments, visit the [Service Trust Portal](https://servicetrust.microsoft.com/viewpage/PenTest). 

#### Execution controls

Microsoft 365 Copilot enforces secure coding and architectural safeguards to prevent misuse, including ransomware generation and remote code execution. Malicious patterns are blocked through prompt inspection and content filtering, while sandboxing ensures Microsoft 365 Copilot operates within constrained execution boundaries. For more information, see [Microsoft 365 Copilot architecture and how it works](/copilot/microsoft-365/microsoft-365-copilot-architecture).

### Threat intelligence and risk mitigation

Microsoft 365 Copilot is protected by a multi-layered defense strategy that combines global threat intelligence, AI-specific detection, and architectural containment. Microsoft uses global threat intelligence to monitor adversarial attacks, model manipulation, and data leakage.  

Key practices include:

- Internal red teaming and third-party penetration testing
- Proactive identification to block malicious inputs
- Machine learning classifiers
- Metaprompting
- Content filtering to detect prompt injection attempts, including jailbreaks, eXternalized Prompt Injection Attacks (XPIAs), and agentic vulnerabilities

Microsoft 365 Copilot mitigates XPIA and agentic vulnerabilities through layered defenses, including markdown sanitization, malicious prompt classifiers, session hardening, and content security policies. These protections prevent unauthorized actions and data exfiltration across Microsoft 365 Copilot surfaces, and are deployed automatically through Microsoft's cloud infrastructure without customer action required. This methodology also includes continuous testing and containment strategies.

#### Containment by design

In the event of a successful injection attempt, Microsoft 365 Copilot's architecture helps ensure containment by design. Microsoft 365 Copilot operates within the user's identity and access context, limiting the blast radius of any potential compromise. 

- Microsoft 365 Copilot operates within the user's identity and tenant context
- Microsoft 365 Copilot only accesses data the user is authorized to view
- All interactions are scoped to existing permissions, preventing lateral movement or unauthorized data access

#### Prompt injection defenses

Microsoft employs a multi-layered defense strategy across the Microsoft 365 Copilot prompt flow to mitigate risks of prompt injection. Here are some examples of protection features that are active by default and don't require setup:

- The user-in-the-loop design enables users to review, modify, or reject AI-generated content.
- Spam, scam, and suspicious content filtering help block malicious instructions, phishing attempts, and fraudulent material in prompts.
- Microsoft 365 Copilot ignores junk email and untrusted Microsoft Teams chats, including chats from external contacts.
- Microsoft 365 Copilot honors Bing web blocking to filter out adult, low-authority, and malicious sites during web search.

For more information about how Microsoft safeguards data, enforces privacy controls, and secures AI operations, see [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md).

<!---One bullet point isn't included yet: Microsoft 365 Copilot operates using a stateless LLM architecture. Requests are processed in real time using tenant-scoped semantic indexing to ensure data access and relevance are strictly limited to the user's organizational context. This point isn't included because it's not a prompt injection defense--->

#### Data exfiltration prevention

Microsoft 365 Copilot's layered security model addresses traditional and emerging threats, including scenarios with the potential for data exfiltration, like these:

- Unauthenticated image URLs, where a user generates an image containing sensitive data, extracts the URL using browser tools, and then shares the image externally. If the image is accessible without authentication, it could bypass enterprise controls, such as [Conditional Access](/entra/identity/conditional-access/overview) or [sensitivity labels](/purview/sensitivity-labels#sensitivity-labels-for-microsoft-365-copilot-and-microsoft-365-copilot-chat).
- Malicious images, such as QR codes, where a user in one tenant generates a malicious image and shares an anonymous URL with users in another tenant. If a URL isn't protected by authentication, access controls might not be enforced. 

To help mitigate such scenarios, Microsoft applies its defense-in-depth strategy. This strategy includes continuous monitoring for data leakage vectors, adversarial misuse, and unauthorized access patterns. 

Microsoft 365 Copilot generated content is governed by the same access controls and compliance policies as other Microsoft 365 content. This means that user permissions, sensitivity labels, and Conditional Access policies are enforced at the point of content generation and access.

### Privacy and compliance by design

Microsoft 365 Copilot adheres to enterprise-grade privacy and compliance standards, described in [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md). This section outlines some of those security-based approaches. 

Protections that are enforced through security controls include:

- Data access enforcement
- Encryption and isolation
- Compliance tooling
- Safeguarding data across the AI lifecycle
- EU data boundary
- Cross-cloud governance for AI workloads
- Policy integration and enforcement

#### Data access enforcement

Microsoft 365 Copilot respects [Microsoft Entra ID](/entra/fundamentals/what-is-entra) permissions and [Microsoft Purview policies](/purview/ai-m365-copilot). Microsoft 365 Copilot only surfaces organizational data to which individual users have at least view permissions. Policies are enforced by Microsoft Entra ID, Microsoft Purview, and [Microsoft Entra Conditional Access](/entra/identity/conditional-access/overview).

[Microsoft 365 Copilot connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector) enhance the value of Microsoft 365 Copilot while maintaining the same enterprise-grade protections.

#### Encryption and isolation

Data is encrypted in transit and at rest using FIPS 140-2–compliant technologies, with tenant-level isolation. [Double Key Encryption](/purview/double-key-encryption) (DKE) helps to ensure that Microsoft can't access protected content without the customer's key, and the content isn't accessible to Microsoft 365 Copilot.

When you have data that's encrypted by Microsoft Purview Information Protection, Microsoft 365 Copilot honors the usage rights granted to the user. This encryption can be applied by sensitivity labels or by restricted permissions in apps in Microsoft 365 by using Information Rights Management (IRM). For more information about using Purview with Microsoft 365 Copilot, see [Microsoft Purview data security and compliance protections for generative AI apps](/purview/ai-microsoft-purview).

#### Cross-cloud governance for AI workloads

Microsoft Purview and Security Copilot help organizations govern AI across hybrid and multicloud environments like Azure, AWS, and Google Cloud.

- [Purview](/purview/ai-microsoft-purview) enables consistent data classification, labeling, and policy enforcement across clouds, with visibility into how data flows into AI models and plugins.
- [Security Copilot](/copilot/security/microsoft-security-copilot) detects AI-related risks across platforms, correlates threats, and surfaces posture insights from [Cloud security posture management](/azure/defender-for-cloud/concept-cloud-security-posture-management).

#### Policy integration and enforcement

Microsoft 365 Copilot is part of Microsoft's enterprise compliance program and benefits from a range of certifications and assessments. These include (but are not limited to) 

- FedRAMP
- HiTrust
- SOC 2 Type 1
- ISO/IEC 27001, 27701, 22301, 27018, and 42001

Microsoft Entra ID, Microsoft Purview, and Microsoft 365 for business enforce Conditional Access, sensitivity labels, and information barriers. Microsoft 365 Copilot-generated responses are governed by the same controls as other Microsoft 365 content. 

For more information, see the following resources:

- [Microsoft Purview data security and compliance protections for generative AI apps](/purview/ai-microsoft-purview)
- [Use Microsoft Purview to manage data security & compliance for Microsoft 365 Copilot & Microsoft 365 Copilot Chat](/purview/ai-m365-copilot).
 
## What you can do to strengthen your organization's AI security

Organizations share responsibility for securing AI systems. Microsoft provides tools and guidance to help you manage risk and enforce compliance. 

- Define and apply [sensitivity labels](/purview/get-started-with-sensitivity-labels) by using [Microsoft Purview](/purview/get-started-with-sensitivity-labels) to classify confidential content across Microsoft 365. 
- Configure [DLP policies that restrict Microsoft 365 Copilot](/purview/dlp-microsoft365-copilot-location-learn-about) from accessing or processing labeled content, such as blocking summarization or rewriting of documents marked as sensitive. 
- When Microsoft 365 Copilot is restricted from accessing content, users are notified, and this interaction can be monitored. See [Data stored about user interactions with Microsoft 365 Copilot](microsoft-365-copilot-privacy.md#data-stored-about-user-interactions-with-microsoft-365-copilot)
- [Ensure users have appropriate permissions](/purview/information-protection-solution), such as *extract* or *view* rights, to allow Microsoft 365 Copilot to interact with content appropriately. 
- Extend DLP coverage across Microsoft 365 Copilot Chat and in-app experiences in Word, Excel, and PowerPoint for consistent protection. See [Learn about DLP](/purview/dlp-learn-about-dlp).

### Control access to data

You can apply [Purview sensitivity labels](/purview/default-sensitivity-labels-policies) to classify and protect content, and enforce [DLP policies](/purview/dlp-policy-reference) to block Microsoft 365 Copilot from accessing sensitive data. For highly confidential information, you can use [DKE](/purview/double-key-encryption) to retain exclusive control over encryption keys.

#### Use targeted Conditional Access policies for Microsoft 365 Copilot

Administrators can apply [Conditional Access policies](/entra/identity/conditional-access/policy-all-users-copilot-ai-security) directly to Microsoft 365 Copilot service principals to enforce granular, AI-specific access controls. These policies can be configured using [Microsoft Graph PowerShell](/powershell/microsoftgraph/) or the [Microsoft Entra admin center](/entra/fundamentals/entra-admin-center). Administrators can:

- Block access to Microsoft 365 Copilot for users with elevated insider risk levels
- Require phishing-resistant multifactor authentication (MFA) when users access Microsoft 365 Copilot from outside the corporate network
- Enforce device compliance and fall back to MFA if compliance can't be verified
- Use GPS-based or IP-based location data to restrict access to trusted geographic regions or networks

### Monitor and audit AI activity

Microsoft 365 Copilot interactions are logged and auditable through [auditing solutions in Microsoft Purview Audit (Standard and Premium)](/purview/audit-solutions-overview). These logs capture user prompts, system responses, and related activities, and can be retained for up to 10 years depending on licensing. This solution supports forensic investigations, compliance reviews, and anomaly detection.

Microsoft 365 Copilot interactions, such as prompts and responses, are stored in a hidden folder in the user's mailbox. This content is discoverable using [Microsoft Purview eDiscovery (Standard and Premium)](/purview/edisc) for legal and compliance teams to search, review, and export Microsoft 365 Copilot-related content as part of investigations or regulatory inquiries. The prompts and responses are also displayed in activity explorer for [DPSM for AI](/purview/dspm-for-ai). Administrators can also configure retention policies from Microsoft Purview Data Lifecycle Management to automatically retain or delete these Microsoft 365 Copilot messages.  

To help secure AI usage with Microsoft 365 Copilot, you can enable [audit logs for Microsoft 365 Copilot and AI applications](/purview/audit-copilot) to log user prompts, Microsoft 365 Copilot responses, and related activities for up to 10 years to remain in compliance. Purview eDiscovery can also be used to search and export Microsoft 365 Copilot-generated content, and to configure retention policies that specify how long AI-generated data is preserved or deleted, based on organizational and regulatory requirements.

To support compliance with regulations such as GDPR, DORA, HIPAA, and the EU AI Act, Microsoft provides structured tools for risk assessment and reporting. [Compliance Manager](/purview/compliance-manager) and [Microsoft Priva](/privacy/priva/priva-overview) offer templates for Data Protection Impact Assessments (DPIAs), helping organizations document data flows, processing purposes, and risk mitigations related to Microsoft 365 Copilot use.

Privacy assessments can be integrated into the AI development lifecycle to identify and mitigate risks early. You can also maintain AI risk registers by using Microsoft Purview and [Microsoft Defender for Cloud](/azure/defender-for-cloud/defender-for-cloud-introduction). These registers include model names, intended purposes, evaluation metrics, plugin scopes, and risk scores—supporting alignment with standards like ISO/IEC 42001 and the EU AI Act.

#### Compliance Tooling

Microsoft Purview Audit and eDiscovery log and surface Microsoft 365 Copilot interactions. [Compliance Manager](/purview/compliance-manager) maps controls to regulations, such as the EU Artificial Intelligence Act and NIST AI RMF 1.0. See [Audit logs for Copilot and AI applications](purview/audit-copilot).

[DSPM for AI](/purview/dspm-for-ai) provides centralized visibility and control over how sensitive data is accessed and used across Microsoft 365 Copilot and other AI services. It enables your organization to discover AI activity, classify and label sensitive content, enforce real-time data loss prevention (DLP), and govern usage through audit logs, retention policies, and compliance rules. 

#### Audit and eDiscovery

[Microsoft Purview](/purview/ai-microsoft-purview) captures Microsoft 365 Copilot interactions for auditing and eDiscovery. Compliance Manager provides regulatory templates to help your organization assess, implement, and strengthen compliance against AI regulations, such as the EU Artificial Intelligence Act, ISO/IEC 23894:2023, ISO/IEC 42001:2023, and NIST AI Risk Management Framework (RMF) 1.0. 

#### Be aware of shadow AI

When employees use unsanctioned AI apps or third-party LLMs, they may unknowingly upload sensitive data to services that aren't governed by your organization's security or compliance policies. This can lead to:

- Exposure of confidential or regulated information
- Violations of data residency or industry compliance rules
- Loss of visibility into how data is accessed, stored, or shared

To help reduce these risks, [Defender for Cloud Apps](/defender-cloud-apps/tutorial-shadow-it) and [Microsoft Purview](/purview/purview) can help detect and manage unauthorized AI usage. These tools help you:

- Discover which AI apps are being used across your environment
- Block or restrict access to high-risk tools
- Monitor and protect sensitive data in real time

Most importantly, educate your teams. Help them understand the risks of Shadow AI and encourage the use of approved, secure alternatives like Microsoft 365 Copilot.

#### Be aware of phishing

Microsoft 365 Copilot is designed to enhance productivity while respecting enterprise security boundaries. However, phishing simulation testing has revealed limitations in Microsoft 365 Copilot's ability to detect and flag malicious content embedded in user prompts or referenced files. These findings have informed Microsoft's roadmap for improving AI-driven threat awareness and integrating Microsoft 365 Copilot more deeply with existing security tools. 

To help address this gap, Microsoft recommends a layered defense approach that combines Microsoft 365 Copilot with [Microsoft Defender XDR](/defender-xdr/microsoft-365-defender) and Microsoft Purview:

- [DPSM for AI](/purview/ai-other-apps) helps you discover and protect AI apps.
- [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365?view=o365-worldwide) provides phishing protection at the email gateway, scanning messages before they reach the user's inbox.
- [Safe Links](/defender-office-365/safe-links-about) and [Safe Attachments](/defender-office-365/safe-attachments-about) policies remain active even when content is surfaced through Microsoft 365 Copilot, helping to block access to malicious URLs or files.
- [Microsoft Purview DLP policies](/purview/dlp-microsoft365-copilot-location-learn-about) can be configured to prevent Microsoft 365 Copilot from accessing or summarizing content that matches phishing indicators or sensitive data patterns.

Additionally, you can use [audit logs](/purview/audit-copilot) and [eDiscovery](/purview/edisc) to monitor Microsoft 365 Copilot interactions involving suspicious content, enabling security teams to investigate and respond to potential misuse.

### Manage plugins and web interactions

To help maintain control and security when using Microsoft 365 Copilot, Microsoft provides robust plugin governance capabilities. Administrators can configure plugins to be enabled or disabled, defined in allowlists or blocklists, and role-based access controls (RBAC) must be applied to ensure only authorized users can access specific plugins. 

You can enforce data protection policies by applying DLP rules and sensitivity labels to content generated through plugins. 

To monitor plugin behavior and detect potential risks, you can use Purview, Defender for Cloud, and Defender for Cloud Apps. For more information, see the following articles:

- [Discover AI apps and data](/security/security-for-ai/discover)
- [How to use DSPM for AI](/purview/dspm-for-ai#how-to-use-data-security-posture-management-for-ai)

#### Enterprise controls for custom AI agents

AI agents built with [Azure AI Foundry](https://techcommunity.microsoft.com/blog/microsoft-security-blog/enterprise-grade-controls-for-ai-apps-and-agents-built-with-azure-ai-foundry-and/4414757) or Microsoft 365 Copilot Studio can be assigned unique identities using Microsoft Entra Agent ID. Organizations can apply Conditional Access, monitor agent activity, and enforce governance policies independently from human users in this way. These agents can also integrate with Microsoft Purview to apply sensitivity labels and DLP policies to training data and outputs.

### Govern AI with Microsoft Purview

To help maintain a secure AI environment with Microsoft 365 Copilot, Microsoft provides customers with tools to monitor and manage plugin activity. Plugin interactions are logged through Microsoft Purview Audit, while Microsoft Defender for Cloud Apps and Defender for Endpoint offer visibility into plugin behavior and endpoint-level telemetry to detect anomalies or unauthorized use. These capabilities enable security teams to track third-party integrations and respond to potential threats effectively.

Microsoft Defender for Cloud includes AI Security Posture Management (AI-SPM), which evaluates plugin permissions, data access scopes, and usage patterns to generate risk scores and policy recommendations. These insights are integrated with Microsoft Purview, assisting organizations in proactively governing plugin-related risks and responsible use of extensibility features in Microsoft 365 Copilot.

For a list of all supported AI applications and Purview controls, see [Microsoft Purview data security and compliance protections for Microsoft 365 Copilot and other generative AI apps](/purview/ai-microsoft-purview).

### Use Microsoft Entra Agent ID

[Microsoft Entra Agent ID](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/announcing-microsoft-entra-agent-id-secure-and-manage-your-ai-agents/3827392) assigns a unique, managed identity to each AI agent, so that organizations can authenticate and authorize them using the same infrastructure as human users, apply Conditional Access policies, and audit their activity. This approach supports [Zero Trust principles](/security/zero-trust/zero-trust-overview) by isolating agent permissions, enforcing least privilege access, and enabling independent tracking for compliance. Future integrations allow distinct identities for Microsoft 365 Copilot plugins,

### Embed responsible AI practices

To use Microsoft 365 Copilot responsibly and meet regulatory expectations, conduct Data Protection Impact Assessments (DPIAs) using Compliance Manager and Microsoft Priva, which help to assess and mitigate privacy and AI-related risks. 

It's also important to educate users, raising awareness about AI risks and promoting safe usage practices across your organization. To support transparency and accountability, Microsoft offers detailed documentation such as the Microsoft 365 Copilot Transparency Note, which explains how Microsoft 365 Copilot works, what it can and can't do, and how it aligns with your compliance goals.

Using Compliance Manager as a centralized dashboard to monitor and manage Microsoft 365 Copilot-related controls and assessments helps to map controls to key regulatory frameworks, including GDPR, HIPAA, and DORA, and generate audit-ready evidence for both internal reviews and external regulators. 

To support AI-specific compliance needs, Microsoft is also adding Microsoft 365 Copilot-specific templates and control mappings, see [Assessments for AI regulations](/purview/compliance-manager-assessments#assessments-for-ai-regulations).

## See also

- [Data, Privacy, and Security for Microsoft 365 Copilot](microsoft-365-copilot-privacy.md)
- [Microsoft 365 Roadmap: Copilot](https://www.microsoft.com/en-us/microsoft-365/roadmap?msockid=08e18dc796b066bc12cd9bef979d67e4&filters=%5B%22Microsoft+Copilot+%28Microsoft+365%29%22%5D)