---
title: "Connect your domain by adding DNS records"
f1.keywords:
- CSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 01/29/2026
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
description: "Connect a domain from any DNS hosting provider in Microsoft 365 by verifying your domain and updating the DNS records in your registrar's account."
ms.custom:
- VSBFY23
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- business_assist
- admindeeplinkMAC
---

# Connect your domain by adding DNS records

If you purchased a domain from a non-Microsoft DNS hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your DNS registrar's account.

At the end of these steps, your domain stays registered with the host that you purchased the domain from, but Microsoft 365 can use it for its various services such as your domain email addresses.

If you don't add a domain to Microsoft 365, people in your organization instead use the `onmicrosoft.com` domain for their email addresses until the domain is added. It's important to add your domain before you add users so you don't have to set up the users twice.

If you want to change the email domain of existing user accounts, follow the steps described in [Change your email address to use your custom domain using the Microsoft 365 admin center](/microsoft-365/admin/email/change-email-address#change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center).

For more information on domains, see [Domains FAQ](../setup/domains-faq.yml).

[!INCLUDE [How to get tech support for SMB](../../includes/smb-how-to-get-tech-support.md)]

> [!TIP]
>
> - To find your DNS hosting provider, see [Find your domain registrar](find-your-domain-registrar.md).
>
> - For instructions on how to add DNS records to specific DNS hosting providers, see the following articles:
>
>   - [Connect your DNS records at IONOS to Microsoft 365](../dns/create-dns-records-at-ionos-com.md).
>   - [Connect your DNS records at 123-reg.co.uk to Microsoft 365](../dns/create-dns-records-at-123-reg-co-uk.md).
>   - [Connect your DNS records at Amazon Web Services (AWS) to Microsoft 365](../dns/create-dns-records-at-aws.md).
>   - [Connect your DNS records at Cloudflare to Microsoft 365](../dns/create-dns-records-at-cloudflare.md).
>   - [Connect your DNS records at GoDaddy to Microsoft 365](../dns/create-dns-records-at-godaddy.md).
>   - [Connect your DNS records at Namecheap to Microsoft 365](../dns/create-dns-records-at-namecheap.md).
>   - [Connect your DNS records at Network Solutions to Microsoft 365](../dns/create-dns-records-at-network-solutions.md).
>   - [Connect your DNS records at OVH to Microsoft 365](../dns/create-dns-records-at-ovh.md).
>   - [Connect your DNS records at web.com to Microsoft 365](../dns/create-dns-records-at-web-com.md).
>   - [Connect your DNS records at Wix to Microsoft 365](../dns/create-dns-records-at-wix.md).
>   - [Create DNS records for Microsoft using Windows-based DNS](../dns/create-dns-records-using-windows-based-dns.md).

## Step 1: Add a TXT or MX record to verify that you own the domain

### Recommended: Verify with a TXT record

First, you need to prove you own the domain you want to add to Microsoft 365.

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings.

    > [!NOTE]
    >
    > The name for managing DNS settings at your DNS hosting provider varies from provider to provider. It might be called something like:
    >
    > - **Zone File Settings**.
    > - **Manage Domains**.
    > - **Domain Manager**.
    > - **DNS Manager**.

1. Go to your provider's DNS Manager page and add the **TXT** record indicated in the Microsoft 365 admin center to your domain. For example:

   - TXT Name: `@`
   - TXT Value: MS=ms######## (unique ID from the Microsoft 365 admin center)
   - TTL: `3600`

    > [!NOTE]
    >
    > Adding the **TXT** record doesn't affect your existing email or other services. You can safely remove it once your domain is connected to Microsoft 365.

1. Save the record, go back to the Microsoft 365 admin center, and then select **Verify**. It typically takes around 15 minutes for DNS record changes to register, but sometimes it can take longer. Give it some time and a few tries to pick up the change.

1. When Microsoft finds the correct TXT record, your domain is verified.

### Verify with an MX record

If your registrar doesn't support adding TXT records, you can verify by adding an MX record.

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings.

    > [!NOTE]
    >
    > The name for managing DNS settings at your DNS hosting provider varies from provider to provider. It might be called something like:
    >
    > - **Zone File Settings**.
    > - **Manage Domains**.
    > - **Domain Manager**.
    > - **DNS Manager**.

1. Go to your provider's DNS Manager page and add the **MX** record indicated in the Microsoft 365 admin center to your domain. Make sure that the fields for the **MX** record are set to the following values:

   - Record Type: `MX`
   - Priority: Set to any large value not already being used.
   - Host Name: `@`
   - Points to address: Copy the value from the Microsoft 365 admin center and paste it here.
   - TTL: `3600`

    > [!IMPORTANT]
    >
    > This **MX** record's **Priority** must be the highest value with the lowest priority of all existing **MX** records for the domain. Otherwise, it can interfere with sending and receiving email.

1. When Microsoft finds the correct MX record, your domain is verified.

> [!IMPORTANT]
>
> You should delete this MX record as soon as domain verification completes.

## Step 2: Connect to Microsoft services by adding DNS records

In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings.

> [!NOTE]
>
> The name for managing DNS settings at your DNS hosting provider varies from provider to provider and might be called something else such as:
>
> - **Zone File Settings**.
> - **Manage Domains**.
> - **Domain Manager**.
> - **DNS Manager**.

You need to add several different types of DNS records depending on the services you want to enable.

### Add an MX record for email (Outlook, Exchange Online)

> [!IMPORTANT]
>
> Before beginning, if users already have email with your domain at another email provider other than Microsoft 365, create their accounts in the Microsoft 365 admin center first before you set up or update your MX records. That way, they continue to receive email. When you update your domain's MX record, all new email for anyone who uses your domain is sent to Microsoft 365. Any existing email stays at your previous email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md).

To add an MX record for use with email in Microsoft 365 (Outlook, Exchange Online), follow these steps.

1. Obtain the information needed for the MX record. Information for the MX record can be obtained from the Microsoft 365 admin center domain setup wizard.

1. On your DNS hosting provider's website, add a new MX record. Make sure that the fields are set to the following values:

   - Record Type: `MX`
   - Priority: Set to the highest value available, typically `0`.
   - Host Name: `@`
   - Points to address: Copy the value from the Microsoft 365 admin center and paste it here.
   - TTL: `3600`

    > [!NOTE]
    >
    > Exchange Online only supports TTL values less than 6 hours (21,600 seconds).

1. Save the record, and then remove any other MX records.

### Add CNAME records to connect other services (Teams, Exchange Online, MDM)

1. Obtain the information needed for the CNAME records. Information for the CNAME records can be obtained from the Microsoft 365 admin center domain setup wizard.

1. On your DNS hosting provider's website, add CNAME records for each service (Teams, Exchange Online, MDM) that you want to connect. Make sure that the fields are set to the following values for each:

   - Record Type: `CNAME (Alias)`
   - Host: Paste the values you copy from the Microsoft 365 admin center here.
   - Points to address: Copy the value from the Microsoft 365 admin center and paste it here.
   - TTL: `3600`

1. Save the records.

### Help prevent email spam (Outlook, Exchange Online) by adding or editing an SPF TXT record

> [!IMPORTANT]
>
> Before beginning, if you already have an SPF record for your domain, don't create a new one for Microsoft 365. Instead, add the required Microsoft 365 values to the current SPF record on your DNS hosting providers website so that you have a *single* SPF record that includes both sets of values.

To help prevent email spam in Outlook or Exchange Online, add or edit an SPF TXT record:

1. On your DNS hosting provider's website, edit the existing SPF record or create an SPF record. Make sure that the fields are set to the following values:

   - Record Type: `TXT (Text)`
   - Host: `@`
   - TXT Value: `v=spf1 include:spf.protection.outlook.com -all`
   - TTL: `3600`

1. Save the record.

1. Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against. To protect against these threats, after setting up the SPF record, you should also set up DomainKeys Identified Mail (DKIM) and Domain-based Message Authentication, Reporting, and Conformance (DMARC) for Microsoft 365. For more information, see the following two articles:

- [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/office-365-security/email-authentication-dkim-configure.md).
- [Use DMARC to validate email in Microsoft 365](../../security/office-365-security/email-authentication-dmarc-configure.md).

### Add SRV records for communications services (Teams)

To add SRV records for communication services such as Teams, follow these steps:

1. On your DNS hosting provider's website, add SRV records for each service you want to connect. Make sure that the fields are set to the following values for each:

   - Record Type: `SRV (Service)`
   - Name: `@`
   - Target: Copy the value from the Microsoft 365 admin center and paste it here.
   - Protocol: Copy the value from the Microsoft 365 admin center and paste it here.
   - Service: Copy the value from the Microsoft 365 admin center and paste it here.
   - Priority: `100`
   - Weight: `1`
   - Port: Copy the value from the Microsoft 365 admin center and paste it here.
   - TTL: `3600`

1. Save the record.

#### SRV record field restrictions and workarounds

Some DNS hosting providers impose restrictions on field values within SRV records. Here are some common workarounds for these restrictions:

- **Name**: If your DNS hosting provider doesn't allow setting this field to **@**, leave it blank. Use this approach *only* when your DNS hosting provider has separate fields for the Service and Protocol values. Otherwise, see the following Service and Protocol notes.

- **Service and Protocol**: If your DNS hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field. To add these values, you create a single string, separating the values with a dot. For example:

    `_sip._tls`

    > [!NOTE]
    >
    > Depending on your DNS hosting provider, the **Name** field might be called something else such as:
    >
    > - **Host**.
    > - **Hostname**.
    > - **Subdomain**.

- **Priority, Weight, and Port**: If your DNS hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field. To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot*. Check with your DNS hosting provider to verify if ending with a dot is required. The values must be included in this order:

  - Priority.
  - Weight.
  - Port.
  - Target.

    For example:

    - `100 1 443 sipdir.online.lync.com.`
    - `100 1 443 sipdir.online.lync.com`

    > [!NOTE]
    >
    > Depending on your DNS hosting provider, the **Target** field might be called something else such as:
    >
    > - **Content**.
    > - **IP Address**.
    > - **Target Host**.

## Related content

- [Help and learning for small business](https://go.microsoft.com/fwlink/?linkid=2224585).
- [Domains FAQ](/microsoft-365/admin/setup/domains-faq).
- [Change nameservers to set up Microsoft 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md) (article).
- [Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article).
- [Manage domains](/admin) (link page).
