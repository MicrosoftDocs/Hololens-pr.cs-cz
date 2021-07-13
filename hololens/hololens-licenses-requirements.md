---
title: Licenční požadavky
description: udržujte si aktuální informace o licenčních požadavcích a pokynech, které potřebujete ke správě mobilních zařízení, HoloLens a vzdálené pomoci.
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
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640270"
---
# <a name="license-requirements"></a><span data-ttu-id="962ba-103">Licenční požadavky</span><span class="sxs-lookup"><span data-stu-id="962ba-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="962ba-104">zařízení HoloLens 2 (spravované)</span><span class="sxs-lookup"><span data-stu-id="962ba-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="962ba-105">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="962ba-105">Azure AD Account</span></span>](/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="962ba-106">službu Active Directory (AD) nelze použít ke správě HoloLensch zařízení.</span><span class="sxs-lookup"><span data-stu-id="962ba-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="962ba-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) nebo jiné MDM.</span><span class="sxs-lookup"><span data-stu-id="962ba-107">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="962ba-108">[Windows autopilot pro HoloLens 2](hololens2-autopilot.md)– usnadňuje zřizování správců IT i koncovým uživatelům.</span><span class="sxs-lookup"><span data-stu-id="962ba-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="962ba-109">správci IT můžou předem nakonfigurovat zásady HoloLens 2 a při prvním spuštění budou zařízení nasazená ve stavu připraveném pro práci s nulovými interakcemi koncových uživatelů.</span><span class="sxs-lookup"><span data-stu-id="962ba-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="962ba-110">Windows Pro automatický pilotní vývoj a nasazování zařízení s nízkou dotykovou instalací vyžaduje autopilotování [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) a [automatické registrace](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) .</span><span class="sxs-lookup"><span data-stu-id="962ba-110">Windows Autopilot requires [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="962ba-111">Případ použití firmy:</span><span class="sxs-lookup"><span data-stu-id="962ba-111">Business Use Case:</span></span> 

- <span data-ttu-id="962ba-112">[Scénář nasazení a](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – zkušební nasazení v konceptu nebo pilotní nasazení.</span><span class="sxs-lookup"><span data-stu-id="962ba-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="962ba-113">[Scénář nasazení B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – nasazení ve velkém měřítku.</span><span class="sxs-lookup"><span data-stu-id="962ba-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="962ba-114">pouze zařízení HoloLens 2 (bez správy)</span><span class="sxs-lookup"><span data-stu-id="962ba-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="962ba-115">Při použití účtu Microsoft (MSA) nebo místního účtu se pro tyto účty nevyžadují žádné další licence.</span><span class="sxs-lookup"><span data-stu-id="962ba-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="962ba-116">Místní účet</span><span class="sxs-lookup"><span data-stu-id="962ba-116">Local Account</span></span>](/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="962ba-117">tento účet musí být [zřízen](hololens-provisioning.md#provisioning-package-hololens-wizard) před časem pomocí nástroje Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="962ba-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="962ba-118">Účet Microsoft (MSA)</span><span class="sxs-lookup"><span data-stu-id="962ba-118">Microsoft Account (MSA)</span></span>](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="962ba-119">U zařízení s některým z těchto účtů se nepodporuje více uživatelů.</span><span class="sxs-lookup"><span data-stu-id="962ba-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="962ba-120">Případ použití firmy:</span><span class="sxs-lookup"><span data-stu-id="962ba-120">Business Use Case:</span></span> 

- <span data-ttu-id="962ba-121">[Scénář nasazení C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -offline nebo zabezpečené nasazení.</span><span class="sxs-lookup"><span data-stu-id="962ba-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="962ba-122">Licencování a požadavky Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="962ba-123">Vzdálená pomoc pro Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="962ba-124">správce</span><span class="sxs-lookup"><span data-stu-id="962ba-124">Admin</span></span>

- <span data-ttu-id="962ba-125">Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)</span><span class="sxs-lookup"><span data-stu-id="962ba-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="962ba-126">[Předplatné vzdálené pomoci](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze vzdáleného asistence](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="962ba-126">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="962ba-127">Uživatel funkce Remote Assist pro uživatele Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="962ba-128">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="962ba-128">Azure AD account</span></span>

- <span data-ttu-id="962ba-129">Licence pro vzdálenou pomoc</span><span class="sxs-lookup"><span data-stu-id="962ba-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="962ba-130">Microsoft Teams je součástí sady Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="962ba-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="962ba-131">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="962ba-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="962ba-132">Microsoft Teams uživatel</span><span class="sxs-lookup"><span data-stu-id="962ba-132">Microsoft Teams user</span></span>

- <span data-ttu-id="962ba-133">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="962ba-133">Azure AD account</span></span>

- <span data-ttu-id="962ba-134">Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="962ba-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="962ba-135">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="962ba-135">Network connectivity</span></span>

<span data-ttu-id="962ba-136">Pokud plánujete implementaci tohoto [scénáře mezi klienty](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), budete možná potřebovat licenci na informace o bariérách.</span><span class="sxs-lookup"><span data-stu-id="962ba-136">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="962ba-137">V [tomto článku](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) zjistíte, jestli je nutná licence k informační bariérě.</span><span class="sxs-lookup"><span data-stu-id="962ba-137">See [this article](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="962ba-138">Příručky k Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="962ba-139">správce</span><span class="sxs-lookup"><span data-stu-id="962ba-139">Admin</span></span>

- <span data-ttu-id="962ba-140">Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)</span><span class="sxs-lookup"><span data-stu-id="962ba-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="962ba-141">Předplatné produktu Dynamics 365 [vás předplatným nebo bezplatnou zkušební verzí](/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="962ba-141">Dynamics 365 [Guides subscription or free trial](/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="962ba-142">Autoré vodítek</span><span class="sxs-lookup"><span data-stu-id="962ba-142">Guides Author</span></span>

1. <span data-ttu-id="962ba-143">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="962ba-143">Azure AD account</span></span>
1. [<span data-ttu-id="962ba-144">Licence pro Příručky k Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="962ba-145">Příručka k aplikaci Dynamics 365, která je nainstalovaná na počítači nebo HoloLens</span><span class="sxs-lookup"><span data-stu-id="962ba-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="962ba-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (slouží k zobrazení řídicího panelu analýzy)</span><span class="sxs-lookup"><span data-stu-id="962ba-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="962ba-147">Role autora (pro vytváření průvodců)</span><span class="sxs-lookup"><span data-stu-id="962ba-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="962ba-148">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="962ba-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="962ba-149">Průvodce uživatelem</span><span class="sxs-lookup"><span data-stu-id="962ba-149">Guides User</span></span>

1. <span data-ttu-id="962ba-150">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="962ba-150">Azure AD account</span></span>
1. [<span data-ttu-id="962ba-151">Licence pro Příručky k Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="962ba-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="962ba-152">Aplikace vodítek pro Dynamics 365 je nainstalovaná na HoloLens</span><span class="sxs-lookup"><span data-stu-id="962ba-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="962ba-153">Role operátora (pro testování nebo použití průvodců)</span><span class="sxs-lookup"><span data-stu-id="962ba-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="962ba-154">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="962ba-154">Network Connectivity</span></span>
