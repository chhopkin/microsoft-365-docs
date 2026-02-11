---
title: "Add a domain to Microsoft 365"
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 02/11/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-domains
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
- operations-pod
ms.custom:
- VSBFY23
- adminvideo
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- business_assist
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: "Use the setup wizard to add your domain to Microsoft 365 in the Microsoft 365 admin center by adding a DNS record at your DNS host."
---

# Add a domain to Microsoft 365

Microsoft recommends using a custom domain name for your organization. A custom domain improves brand recognition, email deliverability, and user trust. Many organizations also add multiple domains to support alternate company names or common variations.

This article goes over the following tasks:

- Adding a custom domain in Microsoft 365.
- Configuring the required DNS records for Microsoft 365 services.

This article goes over performing these tasks either manually or using **Domain Connect**.

## Domain Connect

Microsoft 365 supports registrars that are [**Domain Connect**](https://www.domainconnect.org/) enabled when adding a custom domain. With **Domain Connect**, the following tasks are automatically handled by Microsoft 365:

- Confirming domain ownership.
- Adding DNS records required for Microsoft 365 services.

Microsoft 365 services begin to work once these two tasks are completed. Examples of Microsoft 365 services include:

- Email through Microsoft 365.
- Microsoft Teams.

For examples of registrars that support **Domain Connect**, see [Domain Connect registrars integrating with Microsoft 365](#domain-connect-registrars-integrated-with-microsoft-365).

## Requirements

- To add, modify, or remove domains, you **must** be a **Domain Name Administrator** of a [business or enterprise plan](https://products.office.com/business/office). Because these changes affect the whole tenant, *customized administrators* or *regular users* can't make these changes.

- If using Microsoft 365 for email, add users and set up mailboxes in Microsoft 365 for all email users on your domain before adding an MX record for Microsoft 365. Adding users before setting up the MX record ensures that email continues to work without interruption as the email moves from the previous email provider to Microsoft 365.

- Determine if your registrar supports [**Domain Connect**](#domain-connect).

## Watch: Add a domain

Check out this video and others on our [YouTube channel](https://go.microsoft.com/fwlink/?linkid=2198213).

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=23594aee-6bbd-45d0-8e89-f00fc78ca495]

## Add a domain

To add a custom domain name to Microsoft 365, follow these steps:

1. Sign into [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. In the Microsoft 365 admin center there are two different ways to start the process of adding a custom domain to Microsoft 365:

    - First time adding a custom domain to Microsoft 365:

      1. From the left navigation bar, select **… Show all**, and then select [**Setup**](https://go.microsoft.com/fwlink/p/?linkid=2171997).

      1. In the **Setup** page, under **Sign-in and security**, select **Get your custom domain set up**.

      1. In the **Get your custom domain set up** page, select **Get Started**.

    - Add a custom domain, add additional custom domains, or continue setting up a domain:

      1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

      1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

      1. In the **Domains** page, select **+ Add domain**.

1. In the **Domain name** textbox of the **Add a domain** page, enter the new domain name that you want to add, and then select **Use this domain**.

1. In the **Verify you own your domain** page, different options are displayed depending if your registrar supports **Domain Connect**:

   - **Option 1: Registrar supports [Domain Connect](#domain-connect)**.

       If the registrar supports **Domain Connect**, **Sign in to *registrar*** is displayed where ***registrar*** is the name of the registrar where your domain is registered.

        >[!NOTE]
        >
        > If your registrar supports **Domain Connect** but you prefer to manually verify domain ownership and manually add DNS records needed by Microsoft 365, then select **More options**, and then follow **Option 2: Registrar doesn't support Domain Connect**. If you decide to manually add DNS records, make sure you're familiar with how to properly add DNS records at your registrar. Incorrect DNS records can cause email and service outages. For detailed instructions on adding DNS records at your registrar, refer to the registrar's documentation and instructions.

       To use **Domain Connect**, follow these steps:

        1. Make sure the name of the displayed registrar is correct and then select **Verify**. If your domain is registered at a different registrar than what is displayed, select **choose a different domain host**. After selecting the proper registrar, select **Verify**.

        1. A new window from your registrar opens. Sign into the registrar and then authorize for TXT DNS record to be added.

            > [!NOTE]
            >
            > In order for the new window from the registrar to appear, make sure of one of the following two items:
            >
            > - Pop-up blockers are disabled
            > - The registrar's URL is added to the pop-up blocker's allow list. For more information on allowing pop-ups with Microsoft Edge, see [Block pop-ups in Microsoft Edge](https://support.microsoft.com/microsoft-edge/1d8ba4f8-f385-9a0b-e944-aa47339b6bb5).

        1. Once the TXT DNS record is added and domain ownership is verified, you're returned back to the Microsoft 365 admin center window.

        1. In the **How do you want to connect your domain** page, select **Continue**.

        1. In the **Add DNS records** page, select the Microsoft 365 services that you want DNS records added for, and then select **Add DNS records**. Make sure to also expand **Advanced options** to view additional Microsoft 365 services that might need DNS records.

        1. A new window from your registrar opens showing the DNS records that are going to be added. Verify that the DNS records are correct, and then authorize the DNS records to be added.

        1. Once the DNS records are added, you're returned back to the Microsoft 365 admin center window.

        1. The **Domain setup is complete** page displays. Select **Done** to complete adding your custom domain and DNS records to Microsoft 365.

   - **Option 2: Registrar doesn't support [Domain Connect](#domain-connect)**.

       If a registrar doesn't support **Domain Connect**, the following tasks need to be manually performed:

       - Verification of domain ownership verification via either DNS records or a file downloaded from Microsoft 365 added to your website.
       - DNS records for Microsoft 365 services need to be manually added.

        To manually verify domain ownership and manually add DNS records, follow these steps:

        1. In the **Verify you own your domain** page, select one of the following options to verify domain ownership:

           - **Add a TXT record to the domain's DNS records** - Uses a TXT record manually added to the domain's DNS at the registrar to verify domain ownership. It can take up to 10 minutes to verify domain ownership after adding the TXT record. Some registrars might require additional time up to 48 hours.

           - **If you can't add a TXT record, add an MX record to the domain's DNS records** - Uses an MX record manually added to the domain's DNS at the registrar to verify domain ownership. It can take up to 10 minutes to verify domain ownership after adding the MX record. Some registrars might require additional time up to 48 hours.

           - **Add a text file to the domain's website** - Uses a file download from this wizard and then uploaded to the domain's website top-level folder to verify domain ownership. The path to the file should look similar to the following example:

                `http://mydomain.com/ms39978200.txt`

            Microsoft confirms you own the domain by finding the file on your website.

        1. After an option is selected, select **Continue**:

        1. Instructions specific to the selected option appear:

            - The **Add a record to verify ownership** page appears if one of the first two options is selected. The page contains instructions on what DNS records to add at your registrar to verify domain ownership. For detailed instructions on adding DNS records at your registrar, refer to the registrar's documentation and instructions.

                > [!WARNING]
                >
                > If using the option **If you can't add a TXT record, add an MX record to the domain's DNS records**, make sure to set the **Priority** field of the MX record to high value so that it doesn't break email with your current email provider.

            - If the **Add a text file to the domain's website** is selected, instructions appear on the **Verify you own this domain** page that explains how to add a file to your website to verify domain ownership. For detailed instructions on adding files to your website, refer to the web hosting provider's documentation and instructions.

        1. Once the selected option is completed, select **Verify**. Domain ownership verification occurs.

        1. Once domain ownership verification completes, the **How do you want to connect your domain** appears. Select **Continue**.

            > [!NOTE]
            >
            > If you select **More options** instead of **Continue**, select **Add your own DNS records**, and then select **Continue**.

        1. The **Add DNS records** page contains instructions on what DNS records need to be added at your registrar. Select the Microsoft 365 services that you need DNS records for and then expand each DNS record type for detailed information on the format of the DNS record. Make sure to also expand **Advanced options** to view additional Microsoft 365 services that might need DNS records.

        1. In a separate browser window or tab, sign into your registrar and then manually add the required DNS records from the previous step. For detailed instructions on adding DNS records at your registrar, refer to the registrar's documentation and instructions.

            > [!TIP]
            >
            > The name for managing DNS settings at your registrar varies from registrar to registrar. It might be called something like:
            >
            > - **Zone File Settings**.
            > - **Manage Domains**.
            > - **Domain Manager**.
            > - **DNS Manager**.

        1. Once the DNS records are manually added at the registrar, switch back to th Microsoft 365 admin center web browser window or tab, and then select **Continue**.

        1. The **Domain setup is complete** page displays. Select **Done** to complete adding your custom domain and DNS records to Microsoft 365.

## What happens to my email and website?

After you finish setting up a custom domain, the MX record for your domain is updated to point to Microsoft 365. All email for your domain starts coming to Microsoft 365.

> [!IMPORTANT]
>
> As described in the [Requirements](#requirements) section, make sure you add users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain before adding an MX record. Adding users before setting up the MX record ensures that when email moves from the previous email provider to Microsoft 365, users continue to receive their emails.

If you have a website that you use with your business, it keeps working where it is. The Domain Connect setup steps don't affect your website.

## Add or edit DNS records

If Microsoft 365 hosts the domain instead of a non-Microsoft registrar, the following steps can be used to add DNS record for items such as a website or non-Microsoft services. If the domain is hosted at a non-Microsoft registrar, consult with the registrar's documentation and instructions on how to add DNS records.

1. Sign in to the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://go.microsoft.com/fwlink/p/?linkid=834818).

1. In the **Domains** page, select a domain.

1. In the page that displays your custom domain, select **DNS records**.

1. Select **+ Add records**.

    > [!NOTE]
    >
    > If **+ Add records** isn't available, the domain is hosted at a non-Microsoft registrar. The page displays what registrar the domain is hosted at next to **To manage DNS records for *domain*, go to your DNS hosting provider:**. Consult with the non-Microsoft registrar's documentation and instructions on how to add DNS records.

1. In the **Add a custom DNS record** pane that opens, select the type of DNS record to add (A, CNAME, MX, TXT, etc.), and then fill out the related fields for the selected type of DNS record. Once all of the fields are properly filled out, select **Save** to create the DNS record.

1. The newly created record should appear under **Custom records**.

## Domain Connect registrars integrated with Microsoft 365

- [**Aruba.it**](https://www.aruba.it/).
- [**IONOS**](https://www.1and1.com/).
- [**EuroDNS**](https://www.eurodns.com/).
- [**Cloudflare**](https://www.cloudflare.com/).
- [**GoDaddy (_Media Temple_)**](https://www.godaddy.com/).
- [**WordPress.com**](https://wordpress.com/).
- [**Plesk**](https://www.plesk.com/).
- **SecureServer** or **WildWestDomains** (**GoDaddy** resellers using **SecureServer DNS** hosting)
  - Examples:
    - [**DomainsPricedRight**](https://www.domainspricedright.com/products/domain-registration)
    - [**DomainRightNow**](https://www.domainrightnow.com/)

## Add an onmicrosoft.com domain

To add an onmicrosoft.com domain, see [Add or replace your onmicrosoft.com fallback domain in Microsoft 365](add-or-replace-your-onmicrosoftcom-domain.md).

## Support

[!INCLUDE [How to get tech support for SMB](../../includes/smb-how-to-get-tech-support.md)]

## Related content

- [Domains FAQ](domains-faq.yml).
- [What is a domain?](../get-help-with-domains/what-is-a-domain.md).
- [Domain Connect](https://www.domainconnect.org/).
- [Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md).
- [Connect your domain by adding DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
- [Change nameservers to set up Microsoft 365 with any registrar](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md).
- [Add or replace your onmicrosoft.com fallback domain in Microsoft 365](add-or-replace-your-onmicrosoftcom-domain.md).
- [Small business help & learning](https://go.microsoft.com/fwlink/?linkid=2224585).
- [Microsoft 365 small business help](https://go.microsoft.com/fwlink/?linkid=2197659).
