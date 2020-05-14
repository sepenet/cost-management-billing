---
title: View and download your Azure invoice
description: Describes how to view and download your Azure invoice.
keywords: billing invoice,invoice download,azure invoice,azure usage
author: bandersmsft
ms.reviewer: amberb
tags: billing
ms.service: cost-management-billing
ms.topic: conceptual
ms.date: 03/27/2020
ms.author: banders
---

# View and download your Microsoft Azure invoice

You can download your invoice in the [Azure portal](https://portal.azure.com/) or have it sent in email. If you're an Azure customer with an Enterprise Agreement (EA customer), you can't download your organization's invoice. Instead, invoices are sent to the person set to receive invoices for the enrollment.

[!INCLUDE [GDPR-related guidance](../../../includes/gdpr-intro-sentence.md)]

## When invoices are generated

An invoice is generated based on your billing account type. Invoices are created for Microsoft Online Service Program (MOSP), Microsoft Customer Agreement (MCA), and Microsoft Partner Agreement (MPA) billing accounts. Invoices are also generated for Enterprise Agreement (EA) billing accounts. However, invoices for EA billing accounts aren't shown in the Azure portal.

To learn more about billing accounts and identify your billing account type, see [View billing accounts in Azure portal](../manage/view-all-accounts.md).

## Invoices for MOSP billing accounts

An MOSP billing account is created when you sign up for Azure through the Azure website. For example, when you sign up for an [Azure Free Account](https://azure.microsoft.com/offers/ms-azr-0044p/), [account with pay-as-you-go rates](https://azure.microsoft.com/offers/ms-azr-0003p/) or as a [Visual studio subscriber](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/).

Customers in select regions, who sign up through the Azure website for an [account with pay-as-you-go rates](https://azure.microsoft.com/offers/ms-azr-0003p/) or an [Azure Free Account](https://azure.microsoft.com/offers/ms-azr-0044p/) can have a billing account for an MCA.

If you're unsure of your billing account type, see [Check your billing account type](../manage/view-all-accounts.md#check-the-type-of-your-account) before following the instructions in this article. 

An MOSP billing account can have the following invoices:

**Azure service charges** - An invoice is generated for each Azure subscription that contains Azure resources used by the subscription. The invoice contains charges for a billing period. The billing period is determined by the day of the month when the subscription is created.

For example, John creates *Azure sub 01* on 5 March and *Azure sub 02* on 10 March. The invoice for *Azure sub 01* will have charges from the fifth day of a month to the fourth day of next month. The invoice for *Azure sub 02* will have charges from the tenth day of a month to the ninth day of next month. The invoices for all Azure subscriptions are normally generated on the day of the month that the account was created but can be up to two days later. In this example, if John created his account on 2 February, the invoices for both *Azure sub 01* and *Azure sub 02* will normally be generated on the second day of each month but could be up to two days later.

**Azure marketplace, reservations, and spot VMs** - An invoice is generated for reservations, marketplace products, and spot VMs purchased using a subscription. The invoice shows respective charges from the previous month. For example, John purchased a reservation on 1 March and another reservation on 30 March. A single invoice will be generated for both the reservations in April. The invoice for Azure marketplace, reservations, and spot VMs are always generated around the ninth day of the month.

If you pay for Azure with a credit card and you buy reservation, Azure generates an immediate invoice. However, when billed by an invoice, you are charged for the reservation on your next monthly invoice.

**Azure support plan** - An invoice is generated each month for your support plan subscription. The first invoice is generated on the day of purchase or up to two days later. Subsequent support plan invoices are normally generated on the same day of the month that the account was created but could be generated up to two days later.

## Download your MOSP Azure subscription invoice

An invoice is only generated for a subscription that belongs to a billing account for an MOSP. [Check your access to an MOSP account](../manage/view-all-accounts.md#check-the-type-of-your-account). 

You must have an account admin role for a subscription to download its invoice. Users with owner, contributor, or reader roles can download its invoice, if the account admin has given them permission. For more information, see [Allow users to download invoices](../manage/manage-billing-access.md#opt-in).

1. Select your subscription from the [Subscriptions page](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade) in the Azure portal.
1. Select **Invoices** from the billing section.  
    ![Screenshot that shows a user selecting invoices option for a subscription](./media/download-azure-invoice/select-subscription-invoice.png)
1. Select **Download** to download a PDF version of your invoice and then select **Download** under the invoice section.  
    [![Screenshot that shows billing periods, the download option, and total charges for each billing period](./media/download-azure-invoice/download-invoice-subscription.png)](./media/download-azure-invoice/download-invoice-subscription-zoomed.png#lightbox)
1. You can also download a daily breakdown of consumed quantities and charges by selecting **Download** under the usage details section. It may take a few minutes to prepare the CSV file.  
    ![Screenshot that shows Download invoice and usage page](./media/download-azure-invoice/usage-and-invoice-subscription.png)

For more information about your invoice, see [Understand your bill for Microsoft Azure](../understand/review-individual-bill.md). For help with managing your costs, see [Prevent unexpected costs with Azure billing and cost management](../manage/getting-started.md).

## Download your MOSP support plan invoice

An invoice is only generated for a support plan subscription that belongs to an MOSP billing account. [Check your access to an MOSP account](../manage/view-all-accounts.md#check-the-type-of-your-account). 

You must have an account admin role on the support plan subscription to download its invoice.

1.  Sign in to the [Azure portal](https://portal.azure.com).
1.  Search for **Cost Management + Billing**.  
    ![Screenshot that shows search in portal for cost management + billing](./media/download-azure-invoice/search-cmb.png)
1.  Select **Invoices** from the left-hand side.
1.  Select your support plan subscription and then select **Download**.  
    [![Screenshot that shows billing profile list](./media/download-azure-invoice/cmb-invoices.png)](./media/download-azure-invoice/cmb-invoices-zoomed-in.png#lightbox)
1.  Select **Download** to download a PDF version of your invoice.  
    ![Screenshot that shows billing periods, the download option, and total charges for each billing period](./media/download-azure-invoice/download-invoice-support-plan.png)

## Allow others to download an MOSP subscription invoice

The PDF version of the invoice contains personal information about the account admin, so the account administrator for this subscription must grant other users permission to download the invoice. After permission is granted, the following people and users with appropriate roles can download subscription invoices:

- Users
- Groups
- Service principals with an owner
- Contributor
- Reader
- User access administrator
- Billing reader
- Co-Administrator
- Service Administrator

To download an invoice:

1.  Sign in to the [Azure portal](https://portal.azure.com) as an account admin for the subscription.
1.  Search for **Cost Management + Billing**.  
1.  Select **Invoices** from the left-hand side.
1.  Select your Azure subscription and then select **Access to invoice**.  
    [![Screenshot that shows selecting access to invoice](./media/download-azure-invoice/cmb-select-access-to-invoice.png)](./media/download-azure-invoice/cmb-select-access-to-invoice-zoomed-in.png#lightbox)
1.  Select **On** and then **Save** at the top of the page.  
    ![Screenshot that shows selecting on for access to invoice](./media/download-azure-invoice/cmb-access-to-invoice.png)

## Get MOSP subscription invoice in email

You must have an account admin role on a subscription or a support plan to opt in to receive its invoice by email. Email invoices are available only for subscriptions and support plans, not for reservations or Azure Marketplace purchases. Once you've opted-in you can add additional recipients, who receive the invoice by email as well.

1.  Sign in to the [Azure portal](https://portal.azure.com).
1.  Search for **Cost Management + Billing**.  
1.  Select **Invoices** from the left-hand side.
1.  Select your Azure subscription or support plan subscription and then select **Email invoice**.  
    [![Screenshot that shows billing profile list](./media/download-azure-invoice/cmb-email-invoice.png)](./media/download-azure-invoice/cmb-email-invoice-zoomed-in.png#lightbox)
1. Select **Opt in** and accept the terms.  
    ![Screenshot that shows the opt-in flow step 2](./media/download-azure-invoice/invoice-article-step02.png)
1. The invoice is sent to your preferred communication email address. You can update the email address in the [contact info of your billing account](https://portal.azure.com/#blade/Microsoft_Azure_GTM/ModernBillingMenuBlade/Properties).  
    ![Screenshot that shows the opt-in flow step 3](./media/download-azure-invoice/invoice-article-step03-verify-email.png)

## Share your MOSP invoices with others by email

You may want to share the invoices for your subscription and support plan every month with your accounting team or send them to one of your other email addresses.

1. Follow the steps in [Get your subscription's and support plan's invoices in email](#get-mosp-subscription-invoice-in-email) and select **Configure recipients**.  
    ![Screenshot that shows a user selecting configure recipients](./media/download-azure-invoice/invoice-article-step03.png)
1. Enter an email address, and then select **Add recipient**. You can add multiple email addresses.  
    ![Screenshot that shows a user adding additional recipients](./media/download-azure-invoice/invoice-article-step04.png)
1. Once you've added all the email addresses, select **Done** from the bottom of the screen.

## Invoices for MCA and MPA billing accounts

An MCA billing account is created when your organization works with a Microsoft representative to sign an MCA. Some customers in select regions, who sign up through the Azure website for an [account with pay-as-you-go rates](https://azure.microsoft.com/offers/ms-azr-0003p/) or an [Azure Free Account](https://azure.microsoft.com/offers/ms-azr-0044p/) may have a billing account for an MCA as well. For more information, see [Get started with your MCA billing account](../understand/mca-overview.md).

An MPA billing account is created for Cloud Solution Provider (CSP) partners to manage their customers in the new commerce experience. Partners need to have at least one customer with an [Azure plan](https://docs.microsoft.com/partner-center/purchase-azure-plan) to manage their billing account in the Azure portal. For more information, see [Get started with your MPA billing account](../understand/mpa-overview.md).

A monthly invoice is generated at the beginning of the month for each billing profile in your account. The invoice contains respective charges for all Azure subscriptions and other purchases from the previous month. For example, John created *Azure sub 01* on 5 March, *Azure sub 02* on 10 March. He purchased *Azure support 01* subscription on 28 March using *Billing profile 01*. John will get a single invoice in the beginning of April that will contain charges for both Azure subscriptions and the support plan.

##  Download an MCA or MPA billing profile invoice

You must have an owner, contributor, reader, or an invoice manager role on a billing profile to download its invoice in the Azure portal. Users with an owner, contributor, or a reader role on a billing account can download invoices for all the billing profiles in the account.

1.  Sign in to the [Azure portal](https://portal.azure.com).
1.  Search for **Cost Management + Billing**.  
1. Select **Invoices** from the left-hand side.
    [![Screenshot that shows invoices page for an MCA billing account](./media/download-azure-invoice/mca-billing-profile-invoices.png)](./media/download-azure-invoice/mca-billing-profile-invoices-zoomed.png#lightbox)
1. In the invoices table, select the invoice that you want to download.
1. Select **Download invoice pdf** at the top of the page.  
    ![Screenshot that shows downloading invoice pdf](./media/download-azure-invoice/mca-billing-profile-download-invoice.png)
1. You can also download a CSV file containing your daily breakdown of consumed quantities and estimated charges by selecting **Download Azure usage**. It might take a few minutes to prepare the CSV file.

## Get your billing profile's invoice in email

You must have an owner or a contributor role on the billing profile or its billing account to update its email invoice preference. Once you have opted-in, all users with an owner, contributor, readers, and invoice manager roles on a billing profile will get its invoice in email. 

1.  Sign in to the [Azure portal](https://portal.azure.com).
1.  Search for **Cost Management + Billing**.  
1.  Select **Invoices** from the left-hand side and then select **Email Invoice** from the top of the page.  
    [![Screenshot that shows invoices page for an MCA billing account](./media/download-azure-invoice/mca-billing-profile-select-email-invoice.png)](./media/download-azure-invoice/mca-billing-profile-select-email-invoice-zoomed.png#lightbox)
1.  If you have multiple billing profiles, select a billing profile and then select **Opt in**.  
    ![Screenshot that shows invoices page for an MCA billing account](./media/download-azure-invoice/mca-billing-profile-email-invoice.png)
1.  Select **Update**.

## Give others access to MCA or MPA invoices

You give others access to view, download, and pay invoices by assigning them the invoice manager role for an MCA or MPA billing profile. If you've opted in to get your invoice in email, users also get the invoices in email.

1. Sign in to the [Azure portal](https://portal.azure.com).
1. Search for **Cost Management + Billing**.  
1. Select **Billing profiles** from the left-hand side. From the billing profiles list, select a billing profile for which you want to assign an invoice manager role.  
   ![Screenshot that shows billing profile list](./media/download-azure-invoice/mca-select-profile-zoomed-in.png)
1. Select **Access Control (IAM)** from the left-hand side and then select **Add** from the top of the page.  
    ![Screenshot that shows access control page](./media/download-azure-invoice/mca-select-access-control-zoomed-in.png)
1. In the Role drop-down list, select **Invoice Manager**. Enter the email address of the user to give access. Select **Save** to assign the role.  
   ![Screenshot that shows adding a user as an invoice manager](./media/download-azure-invoice/mca-added-invoice-manager.png)

## <a name="noinvoice"></a> Why you might not see an invoice

There could be several reasons that you don't see an invoice:

- It's less than 30 days from the day you subscribed to Azure. 
- Azure bills you a few days after the end of your billing period. So, an invoice might not have been generated yet.
- You don't have permission to view invoices.
    If you have an MCA or MPA billing account, you must have an Owner, Contributor, Reader, or Invoice manager role on a billing profile or an Owner, Contributor, or Reader role on the billing account to view invoices. For other subscriptions, you might not see the invoices if you aren't the Account Administrator. To learn more about getting access to billing information, see [Manage access to Azure billing using roles](../manage/manage-billing-access.md).
- If you have an MOSP billing account and you signed up for an Azure Free Account or a subscription with a monthly credit amount, you only get an invoice when you exceed the monthly credit amount. If you have a billing account for an MCA or an MPA, you always receive an invoice.

## Need help? Contact us.

If you have questions or need help, [create a support request](https://go.microsoft.com/fwlink/?linkid=2083458).

## Next steps

To learn more about your invoice and charges, see:

- [View and download your Microsoft Azure usage and charges](download-azure-daily-usage.md)
- [Understand your bill for Microsoft Azure](review-individual-bill.md)
- [Understand terms on your Azure invoice](understand-invoice.md)

If you have an MCA, see:

- [Understand the charges on the invoice for your billing profile](review-customer-agreement-bill.md)
- [Understand terms on the invoice for your billing profile](mca-understand-your-invoice.md)
- [Understand the Azure usage and charges file for your billing profile](mca-understand-your-usage.md)


