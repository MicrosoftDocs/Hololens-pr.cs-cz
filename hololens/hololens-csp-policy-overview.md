---
title: Konfigurace CSP a Správa zařízení služby
description: Zjistěte, jak nakonfigurovat CSP, zásady a správu zařízení pomocí mobile Správa zařízení a zřizovací balíčky.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377681"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="c669e-103">Konfigurace CSP a Správa zařízení služby</span><span class="sxs-lookup"><span data-stu-id="c669e-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="c669e-104">Správci IT můžou definovat a implementovat nastavení zásad na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c669e-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="c669e-105">Nastavení konfigurace, která použijete, se budou lišit v závislosti na scénáři nasazení a podniková zařízení budou nabízet IT co nejširší možnosti kontroly.</span><span class="sxs-lookup"><span data-stu-id="c669e-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="c669e-106">V Windows 10 jsou poskytovatelé konfiguračních služeb (CSP) rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení.</span><span class="sxs-lookup"><span data-stu-id="c669e-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="c669e-107">Tato nastavení se mapovat na klíče nebo soubory registru.</span><span class="sxs-lookup"><span data-stu-id="c669e-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="c669e-108">Někteří poskytovatelé konfiguračních služeb podporují formát WAP, někteří podporují SyncML a někteří podporují obojí.</span><span class="sxs-lookup"><span data-stu-id="c669e-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="c669e-109">Další informace o zprostředkovatelích Windows 10 Holographic správy zařízení najdete v úplném seznamu csP podporovaných [v zařízeních HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="c669e-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="c669e-110">Správci IT můžou také spravovat poskytovatele CSP zásad na zařízeních. Úplný seznam csP zásad [podporovaných aplikací HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="c669e-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="c669e-111">Metody konfigurace</span><span class="sxs-lookup"><span data-stu-id="c669e-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="c669e-112">Konfigurace pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="c669e-112">Configure with MDM</span></span>

<span data-ttu-id="c669e-113">CsP a zásady je možné snadno spravovat na libovolném osobním nebo podnikovém zařízení zaregistrované v systému MDM.</span><span class="sxs-lookup"><span data-stu-id="c669e-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="c669e-114">Jakmile je zařízení zaregistrované v řešení MDM, budete moct toto zařízení nebo sadu zařízení spravovat pomocí konfigurací zařízení.</span><span class="sxs-lookup"><span data-stu-id="c669e-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="c669e-115">Přečtěte si další informace [o správě zařízení HoloLens prostřednictvím MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="c669e-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="c669e-116">Konfigurace se zřizovacími balíčky</span><span class="sxs-lookup"><span data-stu-id="c669e-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="c669e-117">HoloLens 2 také podporuje nastavení omezené sady konfigurací CSP pro zařízení HoloLens 2 prostřednictvím vlastních zřizovacích balíčků.</span><span class="sxs-lookup"><span data-stu-id="c669e-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="c669e-118">Zřizovací balíčky se obvykle využívají pro zařízení nespravovaná pomocí MDM a vyžadují ruční použití na každé zařízení.</span><span class="sxs-lookup"><span data-stu-id="c669e-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="c669e-119">Přečtěte si informace o vytváření [vlastních zřizovacích balíčků pro HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="c669e-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="c669e-120">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="c669e-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="c669e-121">Běžná omezení zařízení</span><span class="sxs-lookup"><span data-stu-id="c669e-121">Common device restrictions</span></span>

<span data-ttu-id="c669e-122">Některá omezení zařízení jsou jednoduchá a zakují funkce nebo připojení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="c669e-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="c669e-123">Další informace o těchto omezeních najdete v [běžných omezeních zařízení.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="c669e-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="c669e-124">Bezobrazovkové režimy</span><span class="sxs-lookup"><span data-stu-id="c669e-124">Kiosk modes</span></span>

<span data-ttu-id="c669e-125">Pomocí bezobrazovkového režimu můžete řídit, které identity mají ve výchozím nastavení přístup ke kterým aplikacím.</span><span class="sxs-lookup"><span data-stu-id="c669e-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="c669e-126">Kiosky je možné použít pro jednu aplikaci nebo více prostředí uživatelského rozhraní aplikace.</span><span class="sxs-lookup"><span data-stu-id="c669e-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="c669e-127">Konfigurace veřejného terminálů jsou v rozsahu od jedné aplikace pro každého, kdo zařízení používá, až po různé výběry aplikací pro různé skupiny.</span><span class="sxs-lookup"><span data-stu-id="c669e-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="c669e-128">Bezobrazovkové režim nezabývání "povoleným aplikacím" ve spouštění jiných aplikací a nebyl nikdy zamýšlen.</span><span class="sxs-lookup"><span data-stu-id="c669e-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="c669e-129">Další informace najdete [v článku o režimech veřejného terminálů](hololens-kiosk.md)a o tom, jak je používat.</span><span class="sxs-lookup"><span data-stu-id="c669e-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="c669e-130">Nastavení viditelnosti stránky</span><span class="sxs-lookup"><span data-stu-id="c669e-130">Settings Page Visibility</span></span>

<span data-ttu-id="c669e-131">Pomocí zásad aplikace Nastavení můžete řídit, které identity mají ve výchozím nastavení přístup k nastavení.</span><span class="sxs-lookup"><span data-stu-id="c669e-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="c669e-132">Pomocí této zásady je možné aplikaci Nastavení nakonfigurovat tak, aby buď zobrazovat jenom vybrané stránky, nebo skrýt všechny vybrané stránky.</span><span class="sxs-lookup"><span data-stu-id="c669e-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="c669e-133">[Přečtěte si, jak nakonfigurovat stránky, které jsou k dispozici.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="c669e-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="c669e-134">Tato funkce je aktuálně dostupná pouze [v Windows Insider sestaveních](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="c669e-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="c669e-135">Ujistěte se, že zařízení, pro která chcete tuto funkci používat, jsou ve verzi 19041.1349 nebo více.</span><span class="sxs-lookup"><span data-stu-id="c669e-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="c669e-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="c669e-136">WDAC</span></span>

<span data-ttu-id="c669e-137">Pomocí konfigurace WDAC můžete řídit, které aplikace nebo procesy se mají povolit nebo zakázat spuštění bez ohledu na to, jestli je systém v beznastavovém režimu.</span><span class="sxs-lookup"><span data-stu-id="c669e-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="c669e-138">Podívejte se na náš přehled nástroje WDAC.</span><span class="sxs-lookup"><span data-stu-id="c669e-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
