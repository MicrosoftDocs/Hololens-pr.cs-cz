---
title: Plánování nasazení HoloLens 2 v komerčním prostředí
description: Přečtěte si další informace o nasazení a správě HoloLens v podnikových prostředích, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924600"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="05346-103">Běžné scénáře nasazení</span><span class="sxs-lookup"><span data-stu-id="05346-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="05346-104">Přehled</span><span class="sxs-lookup"><span data-stu-id="05346-104">Overview</span></span>

<span data-ttu-id="05346-105">Tato stránka poskytuje základní přehled architektury pro tři běžné scénáře nasazení a správy Microsoft HoloLens 2 v rámci podniku.</span><span class="sxs-lookup"><span data-stu-id="05346-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="05346-106">Způsob správy zařízení a přístupu k prostředkům vaší organizace je často určován z velké části faktory, které už jsou na místě.</span><span class="sxs-lookup"><span data-stu-id="05346-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="05346-107">V závislosti na vaší stávající infrastruktuře si prohlédněte běžný styl správy zařízení (MDM) v následujících scénářích a pak si v článku Plánování [nasazení HoloLens 2](hololens-core-components.md) v komerčním prostředí zjistěte, který scénář vyhovuje vašim potřebám.</span><span class="sxs-lookup"><span data-stu-id="05346-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="05346-108">K dispozici jsou také tři odpovídající příručky, které můžete použít během nasazení.</span><span class="sxs-lookup"><span data-stu-id="05346-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="05346-109">Průvodce nasazením prostředí připojeného ke cloudu</span><span class="sxs-lookup"><span data-stu-id="05346-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="05346-110">Průvodce nasazením prostředí připojeného ke cloudu (externí klienti)</span><span class="sxs-lookup"><span data-stu-id="05346-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="05346-111">Průvodce nasazením podnikové sítě</span><span class="sxs-lookup"><span data-stu-id="05346-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="05346-112">Průvodce nasazením zabezpečeného prostředí offline</span><span class="sxs-lookup"><span data-stu-id="05346-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="05346-113">Scénář A: Nasazení do zařízení připojených ke cloudu</span><span class="sxs-lookup"><span data-stu-id="05346-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="05346-114">Tento scénář je srovnatelný s nasazením spravovaných mobilních zařízení v rámci společnosti.</span><span class="sxs-lookup"><span data-stu-id="05346-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="05346-115">HoloLens 2 se nasazovat pro použití primárně v prostředích externích pro podnikovou síť.</span><span class="sxs-lookup"><span data-stu-id="05346-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="05346-116">K podnikovým prostředkům se přistupuje nebo je možné, že budou omezené prostřednictvím sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="05346-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="05346-117">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="05346-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="05346-118">Wi-Fi sítě jsou obvykle plně otevřené pro internet a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="05346-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="05346-119">Připojení ke službě Azure AD s Správa zařízení mobilních zařízení (MDM) – spravovaná pomocí MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="05346-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="05346-120">Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="05346-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="05346-121">Podpora jednoho nebo více uživatelů na zařízení</span><span class="sxs-lookup"><span data-stu-id="05346-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="05346-122">Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.</span><span class="sxs-lookup"><span data-stu-id="05346-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="05346-123">Jedna nebo více aplikací se nasadí přes MDM.</span><span class="sxs-lookup"><span data-stu-id="05346-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="05346-124">Běžné problémy</span><span class="sxs-lookup"><span data-stu-id="05346-124">Common Challenges</span></span>
   * <span data-ttu-id="05346-125">Určení konfigurací MDM, které se mají použít pro HoloLens 2, na základě požadavků scénáře</span><span class="sxs-lookup"><span data-stu-id="05346-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="05346-126">[![Diagram scénáře ](images/deployment-guides-revised-scenario-a.png) A](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="05346-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="05346-127">Odpovídající příručka připojená ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, jak podle potřeby používat licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat.</span><span class="sxs-lookup"><span data-stu-id="05346-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="05346-128">Pomocí příručky Externí klienti nasaďte zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.</span><span class="sxs-lookup"><span data-stu-id="05346-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05346-129">Průvodce nasazením prostředí připojeného ke cloudu</span><span class="sxs-lookup"><span data-stu-id="05346-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="05346-130">Průvodce nasazením prostředí připojeného ke cloudu (externí klienti)</span><span class="sxs-lookup"><span data-stu-id="05346-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="05346-131">Scénář B: Nasazení v síti vaší organizace</span><span class="sxs-lookup"><span data-stu-id="05346-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="05346-132">Tento scénář je stejný jako u klasického nasazení pro většinu Windows 10 počítačů.</span><span class="sxs-lookup"><span data-stu-id="05346-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="05346-133">HoloLens 2 se nasazovat pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům.</span><span class="sxs-lookup"><span data-stu-id="05346-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="05346-134">Internet a cloudové služby mohou být omezené.</span><span class="sxs-lookup"><span data-stu-id="05346-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="05346-135">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="05346-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="05346-136">Wi-Fi je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetu nebo cloudovým službám.</span><span class="sxs-lookup"><span data-stu-id="05346-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="05346-137">Připojení ke službě Azure AD s automatickou registrací MDM</span><span class="sxs-lookup"><span data-stu-id="05346-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="05346-138">Správa MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="05346-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="05346-139">Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="05346-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="05346-140">Podpora jednoho nebo více uživatelů na zařízení</span><span class="sxs-lookup"><span data-stu-id="05346-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="05346-141">Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.</span><span class="sxs-lookup"><span data-stu-id="05346-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="05346-142">Jedna nebo více aplikací se nasadí přes MDM.</span><span class="sxs-lookup"><span data-stu-id="05346-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="05346-143">Běžné problémy</span><span class="sxs-lookup"><span data-stu-id="05346-143">Common Challenges</span></span>
   * <span data-ttu-id="05346-144">HoloLens 2 nepodporuje místní připojení k AD ani SCCM.</span><span class="sxs-lookup"><span data-stu-id="05346-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="05346-145">K MDM se připojuje jenom Azure AD.</span><span class="sxs-lookup"><span data-stu-id="05346-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="05346-146">Mnoho společností v tomto scénáři stále nasazovat počítače Windows 10 jako místní zařízení připojená k AD spravovaná přes System Center Správce konfigurace (SCCM) a nemusí mít nasazenou nebo nakonfigurovanou infrastrukturu pro správu interních zařízení Windows 10 prostřednictvím cloudových řešení MDM.</span><span class="sxs-lookup"><span data-stu-id="05346-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="05346-147">HoloLens 2 je první cloudové zařízení, a proto při ověřování uživatelů, aktualizacích operačního systému, správě MDM atd. spoléhá do značné míry na internetové a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="05346-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="05346-148">Při připojování k podnikové síti bude pravděpodobně potřeba upravit pravidla proxy serveru nebo brány firewall, aby byl povolen přístup pro HoloLens 2 a aplikace, které na ní běží.</span><span class="sxs-lookup"><span data-stu-id="05346-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="05346-149">Připojení Wi-Fi podnikové sítě obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti.</span><span class="sxs-lookup"><span data-stu-id="05346-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="05346-150">Konfigurace požadované infrastruktury nebo nastavení pro nasazení certifikátů Windows 10 zařízení prostřednictvím MDM může být náročná.</span><span class="sxs-lookup"><span data-stu-id="05346-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="05346-151">[![Diagram scénáře B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="05346-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="05346-152">[![Diagram scénáře B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="05346-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="05346-153">Odpovídající příručka k podnikové síti instruuje, jak zaregistrovat HoloLens 2 do stávající správy zařízení, jak podle potřeby použít licence a ověřit, jestli koncoví uživatelé po nastavení zařízení mohou používat příručku Dynamics 365 a také používat vlastní obchodní aplikace.</span><span class="sxs-lookup"><span data-stu-id="05346-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05346-154">Průvodce nasazením podnikové sítě</span><span class="sxs-lookup"><span data-stu-id="05346-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="05346-155">Scénář C: Nasazení v zabezpečeném offline prostředí</span><span class="sxs-lookup"><span data-stu-id="05346-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="05346-156">Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná umístění.</span><span class="sxs-lookup"><span data-stu-id="05346-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="05346-157">HoloLens 2 se nasazovat pro použití primárně offline bez přístupu k síti nebo internetu.</span><span class="sxs-lookup"><span data-stu-id="05346-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="05346-158">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="05346-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="05346-159">Wi-Fi připojení je zakázané.</span><span class="sxs-lookup"><span data-stu-id="05346-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="05346-160">Ethernet přes USB může být v případě potřeby povolený pro připojení k síti LAN.</span><span class="sxs-lookup"><span data-stu-id="05346-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="05346-161">Nespravovaná.</span><span class="sxs-lookup"><span data-stu-id="05346-161">Not Managed.</span></span>
   * <span data-ttu-id="05346-162">Místní uživatelský účet pro přihlášení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="05346-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="05346-163">HoloLens 2 podporuje pouze jeden místní účet.</span><span class="sxs-lookup"><span data-stu-id="05346-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="05346-164">Prostřednictvím zřizovací balíčky se na základě konkrétních případů použití používají různé úrovně konfigurací uzamčení zařízení.</span><span class="sxs-lookup"><span data-stu-id="05346-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="05346-165">Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečené prostředí.</span><span class="sxs-lookup"><span data-stu-id="05346-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="05346-166">Jedna nebo více aplikací se nasadí prostřednictvím zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="05346-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="05346-167">Běžné problémy</span><span class="sxs-lookup"><span data-stu-id="05346-167">Common Challenges</span></span>
   * <span data-ttu-id="05346-168">Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.</span><span class="sxs-lookup"><span data-stu-id="05346-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="05346-169">Cloudové služby není možné použít, a proto omezte možnosti HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="05346-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="05346-170">Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.</span><span class="sxs-lookup"><span data-stu-id="05346-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="05346-171">[![Offline zabezpečený diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="05346-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="05346-172">Odpovídající průvodce zabezpečením offline poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který uzamkne HoloLens 2 pro použití v zabezpečených prostředích.</span><span class="sxs-lookup"><span data-stu-id="05346-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05346-173">Průvodce nasazením zabezpečeného prostředí offline</span><span class="sxs-lookup"><span data-stu-id="05346-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


