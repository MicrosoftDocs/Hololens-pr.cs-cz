---
title: Konfigurace CSP a Přehled správy zařízení
description: Naučte se konfigurovat správu CSP, zásad a zařízení pomocí správy mobilních zařízení a zřizovacích balíčků.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640453"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="3768f-103">Konfigurace CSP a Přehled správy zařízení</span><span class="sxs-lookup"><span data-stu-id="3768f-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="3768f-104">správci IT můžou definovat a implementovat nastavení zásad na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3768f-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="3768f-105">Nastavení konfigurace, která použijete, se budou lišit v závislosti na scénáři nasazení a podniková zařízení budou nabízet nejširší škálu ovládacích prvků.</span><span class="sxs-lookup"><span data-stu-id="3768f-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="3768f-106">v Windows 10 jsou poskytovatelé konfiguračních služeb (CSP) s rozhraním pro čtení, nastavení, úpravu nebo odstranění nastavení konfigurace na zařízení.</span><span class="sxs-lookup"><span data-stu-id="3768f-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="3768f-107">Tato nastavení se mapují na klíče registru nebo soubory.</span><span class="sxs-lookup"><span data-stu-id="3768f-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="3768f-108">Někteří poskytovatelé konfigurační služby podporují formát WAP, některé podporují SyncML a některé podporují.</span><span class="sxs-lookup"><span data-stu-id="3768f-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="3768f-109">další informace o zprostředkovatelích Windows 10 Holographic pro správu zařízení najdete v tématu úplný seznam [csp podporovaných v HoloLens zařízeních](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span><span class="sxs-lookup"><span data-stu-id="3768f-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="3768f-110">správci IT taky můžou na zařízeních spravovat zprostředkovatele csp v úplném seznamu [csp zásad, které podporuje HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span><span class="sxs-lookup"><span data-stu-id="3768f-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="3768f-111">Metody konfigurace</span><span class="sxs-lookup"><span data-stu-id="3768f-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="3768f-112">Konfigurace pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="3768f-112">Configure with MDM</span></span>

<span data-ttu-id="3768f-113">Zprostředkovatele CSP a zásady je možné snadno spravovat na jakémkoli osobním nebo podnikovém zařízení zaregistrovaném v systému MDM.</span><span class="sxs-lookup"><span data-stu-id="3768f-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="3768f-114">Jakmile je zařízení zaregistrované v řešení MDM, budete moct spravovat toto zařízení nebo sadu zařízení pomocí konfigurací zařízení.</span><span class="sxs-lookup"><span data-stu-id="3768f-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="3768f-115">přečtěte si další informace o tom, jak [spravovat zařízení HoloLens prostřednictvím MDM](hololens-mdm-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3768f-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="3768f-116">Konfigurace pomocí zřizovacích balíčků</span><span class="sxs-lookup"><span data-stu-id="3768f-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="3768f-117">HoloLens 2 taky podporuje nastavení omezené sady konfigurací CSP pro zařízení HoloLens 2 prostřednictvím vlastních zřizovacích balíčků.</span><span class="sxs-lookup"><span data-stu-id="3768f-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="3768f-118">Zřizovací balíčky se typicky využívají pro zařízení spravovaná bez MDM a vyžadují ruční použití na každé zařízení.</span><span class="sxs-lookup"><span data-stu-id="3768f-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="3768f-119">Přečtěte si informace o vytváření vlastních [zřizovacích balíčků pro HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="3768f-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="3768f-120">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="3768f-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="3768f-121">Běžná omezení zařízení</span><span class="sxs-lookup"><span data-stu-id="3768f-121">Common device restrictions</span></span>

<span data-ttu-id="3768f-122">Některá omezení zařízení jsou jednoduchá a zakázaná funkce nebo připojení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="3768f-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="3768f-123">Další informace o těchto možnostech najdete v tématu o [běžných omezeních zařízení.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="3768f-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="3768f-124">Celoobrazovkový režimy</span><span class="sxs-lookup"><span data-stu-id="3768f-124">Kiosk modes</span></span>

<span data-ttu-id="3768f-125">Celoobrazovkový režim použijte k řízení, které identity mají přístup k aplikacím, které jsou ve výchozím nastavení k dispozici.</span><span class="sxs-lookup"><span data-stu-id="3768f-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="3768f-126">Veřejné terminály je možné použít pro jednu aplikaci nebo více možností uživatelského rozhraní aplikace.</span><span class="sxs-lookup"><span data-stu-id="3768f-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="3768f-127">Konfigurace veřejného terminálu jsou v rozsahu od jediné aplikace pro kohokoli, kdo zařízení používá, k různým výběrům aplikací pro různé skupiny.</span><span class="sxs-lookup"><span data-stu-id="3768f-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="3768f-128">Beznabídkový režim nezastaví spouštěním jiných aplikací povolené aplikace a nebylo zamýšleno pro minulosti.</span><span class="sxs-lookup"><span data-stu-id="3768f-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="3768f-129">Přečtěte si další informace [o beznabídkovém režimu a o tom, jak je používat](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="3768f-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="3768f-130">Nastavení Viditelnost stránky</span><span class="sxs-lookup"><span data-stu-id="3768f-130">Settings Page Visibility</span></span>

<span data-ttu-id="3768f-131">pomocí Nastavení zásady aplikace můžete řídit, které identity mají ve výchozím nastavení přístup k nastavením.</span><span class="sxs-lookup"><span data-stu-id="3768f-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="3768f-132">pomocí této zásady můžete Nastavení aplikaci nakonfigurovat tak, aby buď zobrazovala jenom stránky pro výběr, nebo aby se skryly všechny vybrané stránky.</span><span class="sxs-lookup"><span data-stu-id="3768f-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="3768f-133">[Přečtěte si o tom, jak konfigurovat dostupné stránky](settings-uri-list.md).</span><span class="sxs-lookup"><span data-stu-id="3768f-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="3768f-134">tato funkce je v tuto chvíli dostupná jenom v [Windows buildy Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="3768f-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="3768f-135">Ujistěte se, že zařízení, pro která chcete tuto funkci používat, jsou na 19041.1349 sestavení +.</span><span class="sxs-lookup"><span data-stu-id="3768f-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="3768f-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="3768f-136">WDAC</span></span>

<span data-ttu-id="3768f-137">Pomocí konfigurace WDAC můžete řídit, které aplikace a procesy jsou povolené nebo Nepovolit, aby se spustily bez ohledu na to, jestli je systém v celoobrazovkovém režimu nebo ne.</span><span class="sxs-lookup"><span data-stu-id="3768f-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="3768f-138">Podívejte se na náš přehled pro WDAC.</span><span class="sxs-lookup"><span data-stu-id="3768f-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
