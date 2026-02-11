---
title: "Connect your domain by adding DNS records"
f1.keywords:
- CSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 02/11/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-domains
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- operations-pod
search.appverid:
- MET150
description: "Connect a domain from any registrar in Microsoft 365 by verifying your domain and updating the DNS records in your registrar's account."
ms.custom:
- VSBFY23
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
- admindeeplinkMAC
---

# Connect your domain by adding DNS records

If you purchased a domain from a non-Microsoft registrar, you can connect it to Microsoft 365 by updating the DNS records at your registrar. After DNS records are added at your registrar, your domain stays registered with the registrar that you purchased the domain from. However, Microsoft 365 can use the domain for its various services such as your domain email addresses.

> [!NOTE]
>
> A registrar is also known as a DNS hosting provider.

If you don't add a custom domain to Microsoft 365, your organization can instead use the **onmicrosoft.com** domain for email addresses until a custom domain is added. It's important to add your custom domain before you add users so you don't have to set up users twice.

If you want to change the email domain of existing user accounts, follow the steps described in [Change your email address to use your custom domain using the Microsoft 365 admin center](/microsoft-365/admin/email/change-email-address#change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center).

For more information on domains, see [Domains FAQ](../setup/domains-faq.yml).

## Registrars and Domain Connect

Before your domain is connected to Microsoft 365 by adding DNS records, the registrar that hosts your domain needs to be determined. Additionally, you need to determine if your registrar supports [**Domain Connect**](https://www.domainconnect.org/). **Domain Connect** allows the following tasks to be automatically performed by Microsoft 365:

- Confirming domain ownership.
- Adding DNS records required for Microsoft 365 services.

Without **Domain Connect**, domain ownership and adding DNS records need to be performed manually by signing into your registrar and manually adding the appropriate DNS records.

To find your registrar, see [Find your domain registrar](find-your-domain-registrar.md). Once your registrar is determined, consult with them to see if they support **Domain Connect**.

For instructions on how to manually add DNS records at specific registrars, see the following articles:

- [Connect your DNS records at IONOS to Microsoft 365](../dns/create-dns-records-at-ionos-com.md).
- [Connect your DNS records at 123-reg.co.uk to Microsoft 365](../dns/create-dns-records-at-123-reg-co-uk.md).
- [Connect your DNS records at Amazon Web Services (AWS) to Microsoft 365](../dns/create-dns-records-at-aws.md).
- [Connect your DNS records at Cloudflare to Microsoft 365](../dns/create-dns-records-at-cloudflare.md).
- [Connect your DNS records at GoDaddy to Microsoft 365](../dns/create-dns-records-at-godaddy.md).
- [Connect your DNS records at Namecheap to Microsoft 365](../dns/create-dns-records-at-namecheap.md).
- [Connect your DNS records at Network Solutions to Microsoft 365](../dns/create-dns-records-at-network-solutions.md).
- [Connect your DNS records at OVH to Microsoft 365](../dns/create-dns-records-at-ovh.md).
- [Connect your DNS records at web.com to Microsoft 365](../dns/create-dns-records-at-web-com.md).
- [Connect your DNS records at Wix to Microsoft 365](../dns/create-dns-records-at-wix.md).
- [Create DNS records for Microsoft using Windows-based DNS](../dns/create-dns-records-using-windows-based-dns.md).

## Step 1: Add a domain and verify domain ownership

You need to first add a custom domain to Microsoft 365 and verify domain ownership. For detailed instructions on how to add a custom domain to Microsoft 365, see [Add a domain to Microsoft 365](../setup/add-domain.md#add-a-domain).

## Step 2: Connect to Microsoft services by adding DNS records

When a custom domain is added as part of [Step 1: Add a domain and verify domain ownership](#step-1-add-a-domain-and-verify-domain-ownership), the wizard should prompt to add DNS entries for Microsoft 365 services including email. However, if adding DNS entries was skipped as part of adding the custom domain, they can be added at a later time after adding the custom domain.

The following sections go over how to add the various DNS records for some of the Microsoft 365 services.

### Add an MX record and DNS records for email (Outlook, Exchange Online)

> [!IMPORTANT]
>
> Before beginning, add users and set up mailboxes in Microsoft 365 for all email users on your domain before updating an MX record for Microsoft 365. Adding users before setting up the MX record ensures that email continues to work without interruption as the email moves from the previous email provider to Microsoft 365.
>
> When you update your domain's MX record, all new email for anyone who uses your domain is sent to Microsoft 365. Any existing email stays at your previous email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md).

To add the DNS records needed for Microsoft 365 email services, Select the tab based on your registrar's support for **Domain Connect**:

- **Domain Connect** - Registrar supports Domain Connect and DNS records are added automatically.
- **Manual** - Registrar doesn't support Domain Connect and DNS records need to be added manually.

#### [:::image type="icon" source="/autopilot/images/icons/software-18.svg"::: **Domain Connect**](#tab/domain-connect)

To add an MX record and other supporting email DNS records for use with email in Microsoft 365 (Outlook, Exchange Online), follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In the **Domains** page, select a domain.

1. In the page that displays your custom domain, select **DNS records**, and the select **Manage DNS**.

1. The **How do you want to connect your domain?** wizard starts. Select **Continue**.

1. In the **Add DNS records** page, make sure **Exchange and Exchange Online Protection** is selected.

1. For additional email spam protection, select **Advanced options**, and then select **DomainKeys Identified Mail (DKIM)**. DKIM DNS records are optional. For more information about **DKIM**, see [Help prevent email spam (Outlook, Exchange Online) by adding appropriate DNS records](#help-prevent-email-spam-outlook-exchange-online-by-adding-appropriate-dns-records) in this article.

1. Once the desired email services are selected, select **Add DNS records**.

1. A new window from your registrar opens showing the DNS records that are going to be added, including the MX record. Verify that the DNS records are correct, and then authorize the DNS records to be added.

    > [!IMPORTANT]
    >
    > If an MX record already exists for the previous email provider, one of the following two actions needs to be taken to ensure that email starts getting delivered to Microsoft 365:
    >
    > - Remove any existing MX records pointing to a previous email provider.
    > - Set the MX record priority for the previous email provider to a lower priority than the MX record for Microsoft 365.
    >
    > Depending on the registrar, the registrar might offer to automatically delete the existing MX record via **Domain Connect**. If you don't wish for the existing MX record to be automatically deleted, then the required email DNS records need to be added manually at your registrar. Select the **Manual** tab instead to add MX records manually.

1. Once the DNS records are added, you're returned back to the Microsoft 365 admin center window.

1. The **Domain setup is complete** page displays. Select **Done** to complete adding DNS records to Microsoft 365.

#### [:::image type="icon" source="/autopilot/images/icons/software-18.svg"::: **Manual**](#tab/manual)

To add an MX record and other supporting email DNS records for use with email in Microsoft 365 (Outlook, Exchange Online), follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In the **Domains** page, select a domain.

1. In the page that displays your custom domain, select **DNS records**, and the select **Manage DNS**.

1. The **How do you want to connect your domain?** wizard starts. Select **Continue**.

1. In the **Add DNS records** page, make sure **Exchange and Exchange Online Protection** is selected.

1. For additional email spam protection, select **Advanced options**, and then select **DomainKeys Identified Mail (DKIM)**. DKIM DNS records are optional. For more information about **DKIM**, see [Help prevent email spam (Outlook, Exchange Online) by adding appropriate DNS records](#help-prevent-email-spam-outlook-exchange-online-by-adding-appropriate-dns-records) in this article.

1. Select the **>** next to **MX Records**, **CNAME Records**, and **TXT Records** to expand them. If **DomainKeys Identified Mail (DKIM)** was also selected, make sure to also expand **CNAME Records** under **DomainKeys Identified Mail (DKIM)**. The DNS records that need to be added at your registrar are displayed under each DNS record type.

1. In a separate browser window or tab, sign into your registrar and then manually add the required DNS records shown in previous step. For detailed instructions on adding DNS records at your registrar, refer to the registrar's documentation and instructions.

    > [!TIP]
    >
    > The name for managing DNS settings at your registrar varies from registrar to registrar. It might have one of the following names:
    >
    > - **Zone File Settings**.
    > - **Manage Domains**.
    > - **Domain Manager**.
    > - **DNS Manager**.

    The following are the DNS records that need to be added for Microsoft 365 email services:

    - **MX record** - This DNS record is required and specifies where email for the domain should go to.<br><br>

      |  DNS record field            | Value                                                                                                            |
      |------------------------------|------------------------------------------------------------------------------------------------------------------|
      | *Type*                       | **MX**                                                                                                           |
      | *Priority*                   | Set to the highest value available, typically **0**.                                                             |
      | *Host Name*                  | **@**                                                                                                            |
      | *Points to address or value* | Copy the MX record value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
      | *TTL*                        | **3600** (1 hour)                                                                                                |

      > [!NOTE]
      >
      > Exchange Online only supports TTL values less than 6 hours (21,600 seconds).

    - **Autodiscover CNAME record** - This DNS record is optional but highly recommended. It allows automatic configuration of a user's email in products that support it, for example Microsoft Outlook.<br><br>

      |  DNS record field            | Value                                                                                                                            |
      |------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
      | *Type*                       | **CNAME (Alias)**                                                                                                                |
      | *Host*                       | **autodiscover**                                                                                                                 |
      | *Points to address or value* | Copy the autodiscover CNAME record value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
      | *TTL*                        | **3600** (1 hour)                                                                                                                |

    - **SPF TXT record** - This record is optional but highly recommended. The SPF TXT record helps prevent email spam. For more information on SPF TXT records, see [Help prevent email spam (Outlook, Exchange Online) by adding appropriate DNS records](#help-prevent-email-spam-outlook-exchange-online-by-adding-appropriate-dns-records) in this article.<br><br>

      |  DNS record field            | Value                                              |
      |------------------------------|----------------------------------------------------|
      | *Type*                       | **TXT (Text)**                                     |
      | *Host*                       | **@**                                              |
      | *Points to address or value* | **v=spf1 include:spf.protection.outlook.com -all** |
      | *TTL*                        | **3600** (1 hour)                                  |

      > [!IMPORTANT]
      >
      > If an SPF record already exists for the domain, don't create a new one for Microsoft 365. Don't delete the existing value already in the SPF TXT record for the previous email provider. Instead, add the required Microsoft 365 SPF TXT value to the current SPF TXT record. When complete, there should be a *single* SPF TXT record that includes the values for both the previous email provider and Microsoft 365.

    - **DomainKeys Identified Mail (DKIM) CNAME records** This record is optional. The DKIM record helps prevent email spam. For more information on DKIM records, see [Help prevent email spam (Outlook, Exchange Online) by adding appropriate DNS records](#help-prevent-email-spam-outlook-exchange-online-by-adding-appropriate-dns-records) in this article.<br><br>

      | DNS record field             | Value                    |
      |------------------------------|------------------------- |
      | *Type*                       | **CNAME (Alias)**        |
      | *Host*                       | **selector1._domainkey** |
      | *Points to address or value* | Copy the first value displayed under **DomainKeys Identified Mail (DKIM)** in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
      | *TTL*                        | **3600** (1 hour)        |

      |  DNS record field            | Value                    |
      |------------------------------|--------------------------|
      | *Type*                       | **CNAME (Alias)**        |
      | *Host*                       | **selector2._domainkey** |
      | *Points to address or value* | Copy the first value displayed under **DomainKeys Identified Mail (DKIM)** in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
      | *TTL*                        | **3600** (1 hour)        |

1. If MX records already exist for the previous email provider, one of the following two actions needs to be taken to ensure that email starts getting delivered to Microsoft 365:

   - Remove any existing MX records pointing to a previous email provider.
   - Set the MX record priority for the previous email provider to a lower priority than the MX record for Microsoft 365. The lower the number, the higher the priority, with **0** having the highest priority. If the priority for the Microsoft 365 MX record is **0**, then the priority for the previous email provider should be a value larger than **0**.

1. Once the DNS records are manually added at the registrar, switch back to th Microsoft 365 admin center web browser window or tab, and then select **Continue**.

1. Microsoft 365 verifies that the DNS records for email were added correctly. Once verification completes successfully, the **Domain setup is complete** page displays. Select **Done** to complete adding the email DNS records for Microsoft 365 email services.

---

### Add CNAME and SRV records to connect other Microsoft 365 services (Microsoft Teams, Exchange Online, Microsoft Intune)

Select the tab based on your registrar's support for **Domain Connect**:

- **Domain Connect** - Registrar supports Domain Connect and DNS records are added automatically.
- **Manual** - Registrar doesn't support Domain Connect and DNS records need to be added manually.

#### [:::image type="icon" source="/autopilot/images/icons/software-18.svg"::: **Domain Connect**](#tab/domain-connect)

To add CNAME and SRV records required by Microsoft 365 services such as Microsoft Teams, Exchange Online, or Microsoft Intune:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In the **Domains** page, select a domain.

1. In the page that displays your custom domain, select **DNS records**, and the select **Manage DNS**.

1. The **How do you want to connect your domain?** wizard starts. Select **Continue**.

1. In the **Add DNS records** page, select **Advanced options**. **Advanced options** displays all additional available Microsoft 365 services.

1. Select the desired Microsoft 365 services that DNS records need to be added for, and then select **Add DNS records**. For example:

   - For Microsoft Intune, select **Intune and Mobile Device Management for Microsoft 365**.
   - To add DKIM records to reduce email spam, select **DomainKeys Identified Mail (DKIM)**.

1. A new window from your registrar opens showing the DNS records that are going to be added. Verify that the DNS records are correct, and then authorize the DNS records to be added.

1. Once the DNS records are added, you're returned back to the Microsoft 365 admin center window.

1. The **Domain setup is complete** page displays. Select **Done** to complete adding the CNAME and SRV records to Microsoft 365.

#### [:::image type="icon" source="/autopilot/images/icons/software-18.svg"::: **Manual**](#tab/manual)

To add CNAME and SRV records required by Microsoft 365 services such as Microsoft Teams, Exchange Online, or Microsoft Intune:

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In the **Domains** page, select a domain.

1. In the page that displays your custom domain, select **DNS records**, and the select **Manage DNS**.

1. The **How do you want to connect your domain?** wizard starts. Select **Continue**.

1. In the **Add DNS records** page, select **Advanced options**. **Advanced options** displays all additional available Microsoft 365 services.

1. Select the desired Microsoft 365 services that DNS records need to be added for. For example, for Microsoft Intune, make sure to select **Intune and Mobile Device Management for Microsoft 365**.

1. For each Microsoft 365 service, select the **>** next to either **CNAME Records** or **SRV Records** to expand it. The CNAME records or SRV records that need to be added at your registrar are displayed.

1. In a separate browser window or tab, sign into your registrar and then manually add the required DNS records shown in previous step. For detailed instructions on adding DNS records at your registrar, refer to the registrar's documentation and instructions.

    > [!TIP]
    >
    > The name for managing DNS settings at your registrar varies from registrar to registrar. It might have one of the following names:
    >
    > - **Zone File Settings**.
    > - **Manage Domains**.
    > - **Domain Manager**.
    > - **DNS Manager**.

1. Once the CNAME and SRV records are manually added at the registrar, switch back to th Microsoft 365 admin center web browser window or tab, and then select **Continue**.

1. Microsoft 365 verifies that the CNAME and SRV records were added correctly. Once verification completes successfully, the **Domain setup is complete** page displays. Select **Done** to complete adding the CNAME and SRV records for Microsoft 365 services.

Examples of CNAME and SRV DNS records:

- **CNAME record**<br><br>

    |  DNS record field            | Value                                                                                                  |
    |------------------------------|--------------------------------------------------------------------------------------------------------|
    | *Type*                       | **CNAME (Alias)**                                                                                      |
    | *Host*                       | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *Points to address or value* | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *TTL*                        | **3600** (1 hour)                                                                                      |

    For example, to add the required CNAME records for Microsoft Intune, add the following CNAME records:

    |  DNS record field            | Value                                   |
    |------------------------------|-----------------------------------------|
    | *Type*                       | **CNAME (Alias)**                       |
    | *Host*                       | **enterpriseregistration**              |
    | *Points to address or value* | **enterpriseregistration.windows.net.** |
    | *TTL*                        | **3600** (1 hour)                       |

    |  DNS record field            | Value                                            |
    |------------------------------|--------------------------------------------------|
    | *Type*                       | **CNAME (Alias)**                                |
    | *Host*                       | **enterpriseenrollment**                         |
    | *Points to address or value* | **enterpriseenrollment-s.manage.microsoft.com.** |
    | *TTL*                        | **3600** (1 hour)                                |

- **SRV record**

    |  DNS record field            | Value                                                                                                  |
    |------------------------------|--------------------------------------------------------------------------------------------------------|
    | *Type*                       | **SRV (Service)**                                                                                      |
    | *Name*                       | **@**                                                                                                  |
    | *Target*                     | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *Protocol*                   | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *Service*                    | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *Priority*                   | **100**                                                                                                |
    | *Weight*                     | **1**                                                                                                  |
    | *Port*                       | Copy the value displayed in the Microsoft 365 admin center **Add DNS records** page and paste it here. |
    | *TTL*                        | **3600** (1 hour)                                                                                      |

    > [!NOTE]
    >
    > Some registrars might have restrictions on what can be added to an SRV record. For more information, including workarounds, see [SRV record field restrictions and workarounds](#srv-record-field-restrictions-and-workarounds) in this article.

---

### Help prevent email spam (Outlook, Exchange Online) by adding appropriate DNS records

Sender Policy Framework, better known as SPF, helps prevent email spam. SPF is designed to help prevent spoofing. SPF is activated on a domain by adding a TXT record to the domain's DNS. To set up an SPF TXT record for use with Microsoft 365 email services, see [Add an MX record and DNS records for email (Outlook, Exchange Online)](#add-an-mx-record-and-dns-records-for-email-outlook-exchange-online) in this article.

Although SPF is designed to help prevent spoofing, there are spoofing techniques that SPF can't protect against. To protect against these threats, after setting up the SPF record, you should also set up DomainKeys Identified Mail (DKIM) and Domain-based Message Authentication, Reporting, and Conformance (DMARC) for Microsoft 365. For more information on DKIM and DMARC, see the following two articles:

- [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/email-authentication-dkim-configure.md).
- [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/email-authentication-dmarc-configure.md).

To set up DKIM for use with Microsoft 365 email services, see [Add an MX record and DNS records for email (Outlook, Exchange Online)](#add-an-mx-record-and-dns-records-for-email-outlook-exchange-online) in this article.

### SRV record field restrictions and workarounds

Some registrars impose restrictions on field values within SRV records. Here are some common workarounds for these restrictions:

- **Name**: If your registrar doesn't allow setting this field to **@**, leave it blank. Use this approach *only* when your registrar has separate fields for the Service and Protocol values. Otherwise, see the following Service and Protocol notes.

- **Service and Protocol**: If your registrar doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field. To add these values, you create a single string, separating the values with a dot. For example:

    **_sip._tls**

    > [!NOTE]
    >
    > Depending on your registrar, the **Name** field might be called something else such as:
    >
    > - **Host**.
    > - **Hostname**.
    > - **Subdomain**.

- **Priority, Weight, and Port**: If your registrar doesn't provide these fields for SRV records, you must specify them in the record's **Target** field. To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot*. Check with your registrar to verify if ending with a dot is required. The values must be included in this order:

  - Priority.
  - Weight.
  - Port.
  - Target.

    For example:

    - **100 1 443 sipdir.online.lync.com.**
    - **100 1 443 sipdir.online.lync.com**

    > [!NOTE]
    >
    > Depending on your registrar, the **Target** field might be called something else such as:
    >
    > - **Content**.
    > - **IP Address**.
    > - **Target Host**.

## Support

[!INCLUDE [How to get tech support for SMB](../../includes/smb-how-to-get-tech-support.md)]

## Related content

- [Help and learning for small business](https://go.microsoft.com/fwlink/?linkid=2224585).
- [Domains FAQ](/microsoft-365/admin/setup/domains-faq).
- [Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article).
- [Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article).
- [Manage domains](/admin) (link page).
