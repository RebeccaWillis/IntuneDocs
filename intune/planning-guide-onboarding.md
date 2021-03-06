---
# required metadata

title: Intune onboarding process
description: This article helps you with all details that need to be considered when on-boarding Intune cloud-only solution into your environment.
keywords:
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffbu, cgerth
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: intune-classic

---

# Implement your Intune plan

During the onboarding phase, you deploy Intune into your production environment. The implementation process consists of setting up and configuring Intune and external dependencies (if required) based on your [use-case requirements](planning-guide-requirements.md).

The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.

## Intune requirements

The main Intune standalone requirements are:

-   Enterprise Mobility + Security (EMS)/Intune subscription

-   Office 365 subscription (for Office apps and app-protection-policy managed apps)

-   Apple APNs Certificate (to enable iOS device platform management)

-   Azure AD Connect (for directory synchronization)

-   Intune On-Premises Connector for Exchange (for conditional access for Exchange On-Premises, if needed)

-   Intune Certificate Connector (for SCEP certificate deployment, if needed)

>[!TIP]
> See the list of [supported devices](supported-devices-browsers.md) for a complete list of devices you can manage with Intune.

## Intune implementation process

We've identified 13 discrete tasks for implementing an Intune deployment. Depending on your business requirements, existing infrastructure, and device management strategy, some of these tasks may already be finished. Others may not apply to your plan.

### Task 1: Get an Intune subscription

As indicated in the Intune requirements section above, you need an EMS or Intune subscription. If your organization does not have one, contact Microsoft or your Microsoft account team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.

-   Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

### Task 2: Add Office 365 subscription

This step is optional. You need an Office 365 subscription if you plan to use Exchange Online and manage Office mobile apps with app protection policies. If your organization does not have an Office 365 subscription, contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.

-   Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

### Task 3: Add users groups in Azure AD

You may need to add users or security groups in Active Directory or Azure Active Directory based on your Intune deployment use-case scenarios and requirements. Review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs. When adding new users and security groups, we recommend adding them in Active Directory and synchronizing with Azure Active Directory using Azure AD Connect.


-   Learn more about [how to add users/groups in Intune](users-permissions-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### Task 4: Assign Intune and Office 365 user licenses

All users you target for EMS/Intune and Office 365 rollout need to have a license assigned to them. You can assign EMS/Intune and Office 365 licenses in the Office 365 Admin Center Portal.

-   Learn more about [how to assign Intune licenses](licenses-assign.md).

### Task 5: Set mobile device management authority to Intune

Before you can begin to set up, configure, manage and enroll devices using Intune, you must set the device management authority to Intune.

-   Learn more about [how to set the device management authority](mdm-authority-set.md).

### Task 6: Enable device platforms

By default, most device platforms are enabled except for Apple devices (iOS and Mac). Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled. To do so, you need to create an MDM Push certificate, and add it to Intune.

-   Learn more about [how to enable Apple devices for enrollment](apple-mdm-push-certificate-get.md).

### Task 7: Add and deploy terms and conditions policies

Intune supports terms and conditions policies. Add terms and conditions policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [how to add and deploy terms and condition policies](terms-and-conditions-create.md).

### Task 8: Add and deploy configuration policies

Intune supports two types of configuration policies, general and custom. Add the configuration policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [how to add and deploy configuration policies](device-profiles.md).

### Task 9: Add and deploy resource profiles

Intune supports email, Wi-Fi, and VPN profiles. Add these profiles as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [how to enable access to company resources with Intune](device-profiles.md).

### Task 10: Add and deploy apps

Intune supports the deployment of web, line-of-business, and public Store apps. You can also manage apps that have integrated the Intune SDK by associating them with app protection policies. Add apps as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [adding and deploying apps](app-management.md).

### Task 11: Add and deploy compliance policies

Intune supports compliance policies. Add compliance policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.

-   Learn more about [compliance policies](device-compliance.md).

### Task 12: Enable conditional access policies

Intune supports conditional access for Exchange Online, Exchange on-premises, SharePoint Online, Skype for Business Online, and Dynamics CRM Online. Enable and configure conditional access as appropriate based on your Intune deployment use cases and requirements.

-   Learn more about [conditional access](conditional-access.md).

### Task 13: Enroll devices

Intune supports iOS, Mac OS, Android, Windows desktop, and Windows mobile device platforms. Enroll mobile device platforms as appropriate based on your Intune deployment use cases and requirements.

-   Learn more about [how to enroll devices](device-enrollment.md).


## Next steps

Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) for more information on the Intune implementation process.


See guidance on [testing and validating your Intune deployment](planning-guide-test-validation.md).
