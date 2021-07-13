---
title: Licenční požadavky
description: Udržujte si aktuální všechny licenční požadavky a pokyny, které potřebujete pro správu mobilních zařízení, HoloLens a Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635887"
---
# <a name="license-requirements"></a><span data-ttu-id="8bfc2-103">Licenční požadavky</span><span class="sxs-lookup"><span data-stu-id="8bfc2-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="8bfc2-104">HoloLens 2 Zařízení (spravované)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="8bfc2-105">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bfc2-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="8bfc2-106">Službu Active Directory (AD) nelze použít ke správě HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="8bfc2-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) nebo jiný MDM.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="8bfc2-108">[Windows Autopilot pro HoloLens 2](hololens2-autopilot.md)– zjednodušuje zřizování pro správce IT i koncové uživatele.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="8bfc2-109">Správci IT mohou předem HoloLens 2 zásady a při prvním spuštění se zařízení nasadí ve stavu připraveném pro firmy s nulovou interakcí koncových uživatelů.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="8bfc2-110">Windows Autopilot vyžaduje, aby [](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) [se azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) a automatická registrace nakonfigurovali jako první pro tok Autopilotu a nasazení zařízení s nízkými funkcemi.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="8bfc2-111">Případ obchodního použití:</span><span class="sxs-lookup"><span data-stu-id="8bfc2-111">Business Use Case:</span></span> 

- <span data-ttu-id="8bfc2-112">[Scénář nasazení A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – potvrzení konceptu nebo pilotní nasazení.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="8bfc2-113">[Scénář nasazení B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – nasazení ve velkém měřítku</span><span class="sxs-lookup"><span data-stu-id="8bfc2-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="8bfc2-114">HoloLens 2 Pouze zařízení (nespravovaná)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="8bfc2-115">Při použití účtu Microsoft (MSA) nebo místního účtu nejsou pro tyto účty vyžadovány žádné další licence.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="8bfc2-116">Místní účet</span><span class="sxs-lookup"><span data-stu-id="8bfc2-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="8bfc2-117">Tento účet je nutné [zřídit](hololens-provisioning.md#provisioning-package-hololens-wizard) předem pomocí Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="8bfc2-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="8bfc2-118">Účet Microsoft (MSA)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="8bfc2-119">Pro zařízení používající některý z těchto účtů není podporováno více uživatelů.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="8bfc2-120">Případ obchodního použití:</span><span class="sxs-lookup"><span data-stu-id="8bfc2-120">Business Use Case:</span></span> 

- <span data-ttu-id="8bfc2-121">[Scénář nasazení C –](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) offline nebo zabezpečené nasazení.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="8bfc2-122">Licencování a požadavky Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8bfc2-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="8bfc2-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="8bfc2-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="8bfc2-124">správce</span><span class="sxs-lookup"><span data-stu-id="8bfc2-124">Admin</span></span>

- <span data-ttu-id="8bfc2-125">Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="8bfc2-126">[Předplatné Remote Assistu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="8bfc2-127">Uživatel Dynamics 365 Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="8bfc2-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="8bfc2-128">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bfc2-128">Azure AD account</span></span>

- <span data-ttu-id="8bfc2-129">Licence Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="8bfc2-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="8bfc2-130">Microsoft Teams je součástí Remote Assistu.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="8bfc2-131">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="8bfc2-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="8bfc2-132">Microsoft Teams uživatele</span><span class="sxs-lookup"><span data-stu-id="8bfc2-132">Microsoft Teams user</span></span>

- <span data-ttu-id="8bfc2-133">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bfc2-133">Azure AD account</span></span>

- <span data-ttu-id="8bfc2-134">Microsoft Teams nebo [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="8bfc2-135">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="8bfc2-135">Network connectivity</span></span>

<span data-ttu-id="8bfc2-136">Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="8bfc2-137">Informace [o tom,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) jestli se vyžaduje licence Information Barrier, najdete v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="8bfc2-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="8bfc2-138">Průvodci Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8bfc2-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="8bfc2-139">správce</span><span class="sxs-lookup"><span data-stu-id="8bfc2-139">Admin</span></span>

- <span data-ttu-id="8bfc2-140">Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="8bfc2-141">Předplatné průvodců Dynamics 365 [nebo bezplatná zkušební verze](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="8bfc2-142">Autor příručky</span><span class="sxs-lookup"><span data-stu-id="8bfc2-142">Guides Author</span></span>

1. <span data-ttu-id="8bfc2-143">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bfc2-143">Azure AD account</span></span>
1. [<span data-ttu-id="8bfc2-144">Licence průvodců Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8bfc2-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="8bfc2-145">Aplikace Průvodci Dynamics 365 nainstalovanou na počítači nebo HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bfc2-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="8bfc2-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (slouží k zobrazení řídicího panelu Analýza)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="8bfc2-147">Role autora (pro vytváření průvodců)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="8bfc2-148">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="8bfc2-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="8bfc2-149">Návody – uživatel</span><span class="sxs-lookup"><span data-stu-id="8bfc2-149">Guides User</span></span>

1. <span data-ttu-id="8bfc2-150">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bfc2-150">Azure AD account</span></span>
1. [<span data-ttu-id="8bfc2-151">Licence průvodců Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8bfc2-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="8bfc2-152">Aplikace Průvodci Dynamics 365 nainstalovaná na HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bfc2-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="8bfc2-153">Role operátora (pro testování nebo používání průvodců)</span><span class="sxs-lookup"><span data-stu-id="8bfc2-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="8bfc2-154">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="8bfc2-154">Network Connectivity</span></span>
