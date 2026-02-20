---
title: "Connect your DNS records at Namecheap to Microsoft 365"
f1.keywords:
- CSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 02/20/2026
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-domains
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
- operations-pod
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: "Learn to verify your domain and set up DNS records for email, Teams, and other services at Namecheap."
---

# Connect your DNS records at Namecheap to Microsoft 365

If Namecheap is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Microsoft Teams, and so on.

After you add these records at Namecheap, your domain will be set up to work with Microsoft services.

> [!NOTE]
>
> Namecheap is a non-Microsoft site. Microsoft doesn't control the Namecheap site. Additionally, Namecheap might change their website and tools so that the steps in this article are no longer valid. For support with Namecheap's site and tools, contact Namecheap support.

## Add a TXT record for domain ownership verification

Before you can use your domain with Microsoft 365, you need to prove you own the domain. Your ability to sign in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain. This process involves creating a TXT record at your domain registrar with a specific value that Microsoft can look for. When Microsoft finds the record with the correct value, your domain is verified. The TXT record is used only to verify that you own your domain. It doesn't affect anything else and can be deleted once domain verification is complete.

> [!NOTE]
>
> The procedures in this section assume that the process of [adding a domain](/admin/setup/add-domain#add-a-domain) is started, but that domain ownership isn't verified yet.

To add the TXT record for domain verification at Namecheap, follow these steps:

1. Make sure a domain is added in the Microsoft 365 Admin Center using the steps in [Add a domain](/admin/setup/add-domain#add-a-domain).

1. Obtain and copy the **TXT value** for your domain from the Microsoft 365 admin center. For help on finding your TXT record in the the Microsoft 365 admin center, see [Gather the information you need to create DNS records](../get-help-with-domains/information-for-dns-records.md#step-1-find-the-txt-record-value-and-verify).

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Sign in to Namecheap.":::

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Select Domain List from the drop-down list.":::

1. On the Domain List page, select the domain you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Advanced DNS.":::

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW RECORD.":::

1. In the **Type** drop-down, select **TXT Record**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="Select TXT Record for the domain verification TXT record.":::

1. In the boxes for the new record, enter in or copy and paste the values from the following table. Use the TXT value you copied earlier (MS=ms*XXXXXXXX*) from the Microsoft 365 admin center.

    (Choose the **TTL** value from the drop-down list.)

    |Type|Host|Value|TTL|
    |---|---|---|---|
    |TXT|@|MS=ms *XXXXXXXX*  <br/>**Note:** This entry is an example. Use your specific TXT record obtained from the Microsoft 365 admin center.|30 min|

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="Copy and paste the values from the table for the domain verification TXT record.":::

1. Select the **Save Changes** (check mark) control, or select the **Save All Changes** button located just below the record you just added.

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="Screenshot of the Save Changes control for the domain verification TXT record.":::

1. Wait a few minutes before continuing so that the TXT record you created can update across the Internet.

Now that the TXT record is added at your domain registrar's site, go back to the Microsoft 365 admin center and complete the domain ownership verification process. When Microsoft 365finds the correct TXT record, your domain is verified.

To verify the record in the Microsoft 365 admin center, follow these steps:

1. Sign in to the [Microsoft 365 admin center](https://admin.cloud.microsoft/).

1. From the left navigation bar, select **… Show all**, and then select **Settings** to expand it.

1. Under **Settings**, select [**Domains**](https://admin.cloud.microsoft/?#/Domains).

1. In the **Domains** page, select ⋮ next to the domain that you're verifying, and select **Start setup**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Select Start setup.":::

1. In the **Verify you own your domain** page, make sure **Add a TXT record to the domain's DNS records** is selected, and then select **Continue**.

1. On the **Add a record to verify domain ownership** page, select **Verify**.

1. Once domain ownership is verified, the **How do you want to connect your domain?** page appears. The rest of wizard walks you through adding additional DNS records to connect your domain to Microsoft 365 services. For more information, see the following article or the following sections in this article:

    - [Connect to Microsoft services by adding DNS records](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?&tabs=manual#step-2-connect-to-microsoft-services-by-adding-dns-records).
    - [Add an MX record so email starts going to Microsoft 365 email services](#add-an-mx-record-so-email-starts-going-to-microsoft-365-email-services).
    - [Add a CNAME record so email accounts are automatically set up in Outlook and other email clients](#add-a-cname-record-so-email-accounts-are-automatically-set-up-in-outlook-and-other-email-clients).
    - [Add an SPF TXT record to help prevent email spam](#add-an-spf-txt-record-to-help-prevent-email-spam).
    - [DNS records for Microsoft Teams](#dns-records-for-microsoft-teams).
    - [DNS records for Intune and Mobile Device Management for Microsoft 365](#dns-records-for-intune-and-mobile-device-management-for-microsoft-365).

[!INCLUDE [Domain propagation note](../../includes/global-administrator-note.md)]

## Add an MX record so email starts going to Microsoft 365 email services

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Sign in to Namecheap.":::

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Choose Domain List from the drop-down list.":::

1. On the **Domain List** page, select the domain that you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Advanced DNS.":::

1. In the **MAIL SETTINGS** section, select **Custom MX** from the **Email Forwarding** drop-down list. You might have to scroll down the drop-down list to find it.

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="Select Custom MX.":::

1. Select **Add New Record**.

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="ADD NEW RECORD.":::

1. In the boxes for the new record, enter in or copy and paste the values, from the following table.

    (The **Priority** box is the unnamed box to the right of the **Value** box. Choose the **TTL** value from the drop-down list.)

    |Type|Host|Value|Priority|TTL|
    |---|---|---|---|---|
    |MX Record|@|\<*domain-key*>.mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Note:** Get your <*domain-key*> from the Microsoft 365 admin center. For help on finding your <*domain-key*>, see [Gather the information you need to create DNS records](../get-help-with-domains/information-for-dns-records.md#step-2-find-the-mx-record-value-for-email-and-more).|0  <br/> For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)|30 min|

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="Copy and paste the values from the table for the MX record.":::

1. Select the **Save Changes** (check mark) control.

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="Screenshot of the Save Changes control for the MX record.":::

1. If there are any other MX records, use the following two-step process to remove each of them:

    First, select **Delete** (trash can) for the record that you want to remove.

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="Select Delete.":::

    Second, select **Yes** to confirm the deletion.

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="Select Yes.":::

    Remove all MX records except for the one that you added earlier in this procedure.

## Add a CNAME record so email accounts are automatically set up in Outlook and other email clients

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Sign in to Namecheap.":::

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Select Domain List.":::

1. On the **Domain List** page, select the domain that you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Advanced DNS.":::

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW RECORD.":::

1. In the **Type** drop-down, select **CNAME Record**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="Select CNAME Record.":::

1. In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then enter in or copy and paste the values from the first row in the following table.

    |Type|Host|Value|TTL|
    |---|---|---|---|
    |CNAME|autodiscover|autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)**|Automatic|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Copy and paste the values from the table for the CNAME record.":::

1. Select the **Save Changes** (check mark) control.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Screenshot of the Save Changes control for the CNAME record.":::

## Add an SPF TXT record to help prevent email spam

> [!IMPORTANT]
>
> You can't have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, email errors and delivery and spam classification issues occur. If you already have an SPF record for your domain, don't create a new one for Microsoft. Instead, add the required Microsoft values to the current record so that you have a *single*  SPF record that includes both sets of values.

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Select Domain List.":::

1. On the **Domain List** page, select the domain that you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Advanced DNS.":::

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW RECORD.":::

1. In the **Type** drop-down, select **TXT Record**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="Select TXT Record for the SPF TXT record.":::

1. In the boxes for the new record, enter in or copy and paste the following values from the following table.

    (Choose the **TTL** value from the drop-down list.)

    |Type|Host|Value|TTL|
    |---|---|---|---|
    |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.|30 min|

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="Copy and paste the values from the table for the SPF TXT record.":::

1. Select the **Save Changes** (check mark) control.

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="Screenshot of the Save Changes control for the SPF TXT record.":::

## DNS records for Microsoft Teams

Only add these DNS records if your organization uses Microsoft Teams. Microsoft Teams needs four records:

- Two SRV records for user-to-user communication.
- Two CNAME records to sign-in and connect users to the service.

### Add the two required SRV records for Microsoft Teams

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Sign in to Namecheap.":::

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Choose Domain List.":::

1. On the **Domain List** page, select the domain that you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Advanced DNS.":::

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW RECORD.":::

1. In the **Type** drop-down, select **SRV Record**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="Select the SRV Record type.":::

1. In the empty boxes for the new records, enter in or copy and paste the values from the first row in the following table.

    |Service|Protocol|Priority|Weight|Port|Target|TTL|
    |---|---|---|---|---|---|---|
    |_sip|_tls|100|1|443|sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)**|Automatic|
    |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)**|Automatic|

     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="Copy and paste the values from the table for the SRV records.":::

1. Select the **Save Changes** (check mark) control.

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="Screenshot of the Save Changes control for the SRV records for Microsoft Teams.":::

1. Add the other SRV record by choosing the values from the second row of the table.

[!INCLUDE [Domain propagation note](../../includes/global-administrator-note.md)]

### Add the two required CNAME records for Microsoft Teams

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW NAME.":::

1. In the **Type** drop-down, select **CNAME**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="Select CNAME.":::

1. In the empty boxes for the new records, enter in or copy and paste the values from the first row in the table.

    |Type|Host|Value|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)**|Automatic|
    |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **This value MUST end with a period (.)**|Automatic|

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Copy and paste the CNAME values from the table.":::

1. Select the **Save Changes** (check mark) control.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Screenshot of the Save Changes control for the CNAME records for Microsoft Teams.":::

1. Add the other CNAME record by choosing the values from the second row of the table.

[!INCLUDE [Domain propagation note](../../includes/global-administrator-note.md)]

## DNS records for Microsoft Intune and Mobile Device Management for Microsoft 365

 Microsoft Intune and Mobile Device Management for Microsoft 365 helps you secure and remotely manage mobile devices that connect to your domain. Mobile Device Management needs two CNAME records so that users can enroll devices to the service.

### Add the two required CNAME records for Mobile Device Management

1. Sign in to your Namecheap domains page going to the Namecheap [Log in to your account](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) page.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Sign in to Namecheap.":::

1. On the landing page, under **Account**, choose **Domain List** from the drop-down list.

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="Select Domain List.":::

1. On the **Domain List** page, select the domain that you want to edit, and then select **Manage**.

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="Select Manage.":::

1. Select **Advanced DNS**.

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="Select Manage DNS Records from the drop-down list.":::

1. In the **HOST RECORDS** section, select **ADD NEW RECORD**.

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="Select ADD NEW RECORD.":::

1. In the **Type** drop-down, select **CNAME Record**.

    > [!NOTE]
    >
    > The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="Select CNAME Record.":::

1. In the empty boxes for the new records, enter in or copy and paste the values from the first row in the table.

    |Type|Host|Value|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)**|Automatic|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)**|Automatic|

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="Copy and paste the values from the table for the CNAME records for Mobile Device Management.":::

1. Select the **Save Changes** control.

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="Screenshot of the Save Changes control for the CNAME records for Mobile Device Management.":::

1. Add the other CNAME record by choosing the values from the second row of the table.

[!INCLUDE [How to get tech support for SMB](../../includes/smb-how-to-get-tech-support.md)]

## Support

 **[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.
