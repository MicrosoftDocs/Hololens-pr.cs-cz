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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379273"
---
# <a name="license-requirements"></a><span data-ttu-id="b410c-103">Licenční požadavky</span><span class="sxs-lookup"><span data-stu-id="b410c-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="b410c-104">Pokyny Správa zařízení k licencím pro Mobile Správa zařízení (MDM)</span><span class="sxs-lookup"><span data-stu-id="b410c-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="b410c-105">Pokud máte v plánu spravovat zařízení HoloLens, budete potřebovat Azure AD a MDM.</span><span class="sxs-lookup"><span data-stu-id="b410c-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="b410c-106">Active Director (AD) není možné použít ke správě zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b410c-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="b410c-107">Pokud plánujete používat jiný MDM než Intune, vyžaduje [se Azure Active Directory licence.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="b410c-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="b410c-108">Pokud máte v plánu používat Intune jako MDM, přečtěte si seznam sad, [které](https://docs.microsoft.com/intune/fundamentals/licenses) obsahují licence Intune.</span><span class="sxs-lookup"><span data-stu-id="b410c-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="b410c-109">**Upozorňujeme, že služba Azure AD je součástí většiny těchto sad.**</span><span class="sxs-lookup"><span data-stu-id="b410c-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="b410c-110">Identifikace licencí potřebných pro váš scénář a produkty</span><span class="sxs-lookup"><span data-stu-id="b410c-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="b410c-111">HoloLens (1. generace) – požadavky na licence</span><span class="sxs-lookup"><span data-stu-id="b410c-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="b410c-112">Možná budete muset upgradovat zařízení HoloLens (1. generace) na Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="b410c-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="b410c-113">(Pokud chcete zjistit, jestli potřebujete upgradovat, podívejte se na komerční funkce [HoloLens.](holoLens-commercial-features.md#feature-comparison-between-editions)</span><span class="sxs-lookup"><span data-stu-id="b410c-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="b410c-114">Pokud ano, budete muset provést následující:</span><span class="sxs-lookup"><span data-stu-id="b410c-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="b410c-115">Získání souboru XML s licencí HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="b410c-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="b410c-116">Použijte soubor XML na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b410c-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="b410c-117">Můžete to provést prostřednictvím [zřizovacího balíčku nebo](hololens-provisioning.md) přes [Mobile Správce zařízení](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="b410c-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="b410c-118">Licenční požadavky pro Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b410c-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="b410c-119">Ujistěte se, že máte požadované licence a zařízení, které můžete zkontrolovat v [dokumentaci k požadavkům.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)</span><span class="sxs-lookup"><span data-stu-id="b410c-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="b410c-120">Licence Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="b410c-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="b410c-121">Nebo zkuste zkušební [verzi vzdálené pomoci.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="b410c-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="b410c-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="b410c-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="b410c-123">Azure Active Directory (Azure AD) License</span><span class="sxs-lookup"><span data-stu-id="b410c-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="b410c-124">Pokud plánujete implementaci tohoto **[scénáře napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** možná budete potřebovat licenci Information Barriers.</span><span class="sxs-lookup"><span data-stu-id="b410c-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="b410c-125">Pokud chcete [zjistit, jestli](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) se vyžaduje licence Information Barrier, přečtěte si tento článek.</span><span class="sxs-lookup"><span data-stu-id="b410c-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="b410c-126">Průvodci licenčními požadavky</span><span class="sxs-lookup"><span data-stu-id="b410c-126">Guides License Requirements</span></span>

<span data-ttu-id="b410c-127">Podívejte se na [aktualizované licenční požadavky a požadavky na zařízení.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="b410c-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="b410c-128">Azure Active Directory (Azure AD) License</span><span class="sxs-lookup"><span data-stu-id="b410c-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="b410c-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="b410c-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="b410c-130">Příručky</span><span class="sxs-lookup"><span data-stu-id="b410c-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
