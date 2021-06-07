---
title: Přehled – Správa aplikací
description: Začínáme s přehledem správy aplikací hybridní reality pomocí správy mobilních zařízení, Microsoft Storu pro firmy a zřizovacích balíčků
keywords: HoloLens, user, account, app, application management,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377580"
---
# <a name="app-management-overview"></a><span data-ttu-id="0d8e9-104">Správa aplikací: Přehled</span><span class="sxs-lookup"><span data-stu-id="0d8e9-104">App Management: Overview</span></span>

<span data-ttu-id="0d8e9-105">Aplikace můžete nasadit do čtyř různých cest: **Mobile Správa zařízení (MDM),** **Microsoft Store pro firmy,** **Microsoft Store** nebo jejich instalací prostřednictvím **zřizování**.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="0d8e9-106">Správa mobilního zařízení (MDM)</span><span class="sxs-lookup"><span data-stu-id="0d8e9-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0d8e9-107">Řešení pro správu mobilních zařízení umožňuje správcům a správcům IT soukromě automaticky instalovat (nabízeně) své vlastní obchodní aplikace nebo nakupovat aplikace prostřednictvím Storu pro skupinu uživatelů.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="0d8e9-108">Zařízení HoloLens fungují nejlépe se službou Microsoft Endpoint Manager (Intune) pro [správu aplikací.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="0d8e9-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="0d8e9-109">Intune také nabízí uživatelům přesnější kontrolu nad aplikacemi spravovanými IT prostřednictvím Portál společnosti ke stažení.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="0d8e9-110">Následující pokyny jsou pro uživatele, kteří chtějí spravovat své aplikace pomocí Intune.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="0d8e9-111">Microsoft doporučuje ke správě aplikací a zařízení používat Intune.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="0d8e9-112">Mobilní Správa zařízení (MDM) se vztahuje na:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="0d8e9-113">Nasazená a Portál společnosti MDM</span><span class="sxs-lookup"><span data-stu-id="0d8e9-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="0d8e9-114">Obchodní aplikace (ne veřejné)</span><span class="sxs-lookup"><span data-stu-id="0d8e9-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="0d8e9-115">Ruční instalace dostupných aplikací prostřednictvím Portál společnosti</span><span class="sxs-lookup"><span data-stu-id="0d8e9-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="0d8e9-116">Nabízení správy prostřednictvím zásad MDM</span><span class="sxs-lookup"><span data-stu-id="0d8e9-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="0d8e9-117">Automatická aktualizace prostřednictvím MDM</span><span class="sxs-lookup"><span data-stu-id="0d8e9-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="0d8e9-118">Microsoft Store pro firmy</span><span class="sxs-lookup"><span data-stu-id="0d8e9-118">Microsoft Store for Business</span></span>

<span data-ttu-id="0d8e9-119">The [Microsoft Store pro firmy](app-deploy-store-business.md) poskytuje it decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="0d8e9-120">Správci IT můžou Microsoft Store aplikace a privátní obchodní aplikace v jednom inventáři a podle potřeby přiřazovat a opakovaně používat licence.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="0d8e9-121">Další informace najdete v tématu [Požadavky pro použití nástroje Microsoft Store pro firmy](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="0d8e9-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="0d8e9-122">Tento Microsoft Store pro firmy platí pro:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="0d8e9-123">Veřejné nebo obchodní aplikace</span><span class="sxs-lookup"><span data-stu-id="0d8e9-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="0d8e9-124">Automatická instalace požadovaných aplikací prostřednictvím přidružení MDM</span><span class="sxs-lookup"><span data-stu-id="0d8e9-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="0d8e9-125">Uživatel stáhne aplikace ručně.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-125">User manually downloads apps</span></span>
* <span data-ttu-id="0d8e9-126">Automatická aktualizace</span><span class="sxs-lookup"><span data-stu-id="0d8e9-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="0d8e9-127">Aplikace pro Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0d8e9-127">Microsoft Store apps</span></span>

<span data-ttu-id="0d8e9-128">Tento Microsoft Store poskytuje správcům a správcům IT ve firmách vyhledávání, získávání, správu a distribuci veřejných aplikací.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="0d8e9-129">Tato Microsoft Store platí pro:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="0d8e9-130">Jenom veřejné aplikace</span><span class="sxs-lookup"><span data-stu-id="0d8e9-130">Public apps only</span></span>
* <span data-ttu-id="0d8e9-131">Uživatel stáhne aplikace ručně.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-131">User manually downloads apps</span></span>
* <span data-ttu-id="0d8e9-132">Automatická aktualizace při připojení k internetu</span><span class="sxs-lookup"><span data-stu-id="0d8e9-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="0d8e9-133">Další informace najdete na webu [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="0d8e9-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="0d8e9-134">Instalace prostřednictvím zřizovací balíčky</span><span class="sxs-lookup"><span data-stu-id="0d8e9-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="0d8e9-135">[Zřizovací](app-deploy-provisioning-package.md) balíčky umožňují instalovat vlastní nebo obchodní aplikace, což IT profesionálům a správcům umožňuje rychle instalovat aplikace na místní zařízení přes USB.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="0d8e9-136">Tuto instalaci je možné provést bez připojení k internetu a libovolného typu identity.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="0d8e9-137">Instalace prostřednictvím zřizovací balíčky se vztahuje na:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="0d8e9-138">Obchodní / samoobslužné (ne veřejné) aplikace</span><span class="sxs-lookup"><span data-stu-id="0d8e9-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="0d8e9-139">Veřejné aplikace (pokud je k dispozici offline instalační program)</span><span class="sxs-lookup"><span data-stu-id="0d8e9-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="0d8e9-140">Jenom načítání bokem přes USB</span><span class="sxs-lookup"><span data-stu-id="0d8e9-140">USB side-loading only</span></span>
* <span data-ttu-id="0d8e9-141">Žádná automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím zřizovacího balíčku)</span><span class="sxs-lookup"><span data-stu-id="0d8e9-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="0d8e9-142">Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací</span><span class="sxs-lookup"><span data-stu-id="0d8e9-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="0d8e9-143">Uživatelé s [Instalační program aplikací](app-deploy-app-installer.md) mohou mít prostředí, které je jednoduché pro instalaci aplikací na místní zařízení nebo sdílení aplikace s někým jiným, kdo nemá zkušenosti s jinými metodami instalace aplikací na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="0d8e9-144">Můžete to udělat bez nutnosti povolit vývojářský režim nebo použít Portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="0d8e9-145">Jedná se o jednoduchou metodu distribuce plně sestavené aplikace.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="0d8e9-146">Bez ohledu na to, jestli chcete aplikaci jednoduše degradovat na jiného uživatele pomocí HoloLens, nebo chcete aplikaci nasadit, tato metoda funguje snadno.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="0d8e9-147">Instalace prostřednictvím Instalační program aplikací se vztahuje na:</span><span class="sxs-lookup"><span data-stu-id="0d8e9-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="0d8e9-148">Obchodní / samoobslužné (ne veřejné) aplikace</span><span class="sxs-lookup"><span data-stu-id="0d8e9-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="0d8e9-149">Pouze zkušební načtení</span><span class="sxs-lookup"><span data-stu-id="0d8e9-149">Side-load only</span></span>
* <span data-ttu-id="0d8e9-150">Nevyžaduje vývojářský režim ani portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="0d8e9-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="0d8e9-151">Snadná instalace pro koncového uživatele</span><span class="sxs-lookup"><span data-stu-id="0d8e9-151">Easy for end user to install</span></span>
