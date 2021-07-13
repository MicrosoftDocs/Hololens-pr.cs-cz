---
title: Běžné scénáře nasazení
description: přečtěte si další informace o nasazení a správě HoloLens v podnikovém prostředí, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
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
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635462"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="0ba3d-103">Běžné scénáře nasazení</span><span class="sxs-lookup"><span data-stu-id="0ba3d-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="0ba3d-104">Přehled</span><span class="sxs-lookup"><span data-stu-id="0ba3d-104">Overview</span></span>

<span data-ttu-id="0ba3d-105">tato stránka poskytuje přehled architektury vysoké úrovně pro tři běžné scénáře při nasazení a správě zařízení Microsoft HoloLens 2 v rámci podniku.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="0ba3d-106">Správa zařízení a přístup k prostředkům vaší organizace je často určována podle faktorů, které jsou už na místě.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="0ba3d-107">v závislosti na vaší stávající infrastruktuře vás vyzveme ke kontrole společného stylu správy zařízení (MDM) v následujících scénářích a potom si můžete přečíst téma [plánování nasazení HoloLens 2 v komerčním prostředí](hololens-core-components.md) , abyste zjistili, který scénář vyhovuje vašim potřebám.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="0ba3d-108">K dispozici jsou také tři odpovídající příručky pro použití během nasazování.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="0ba3d-109">Průvodce nasazením propojeného prostředí v cloudu</span><span class="sxs-lookup"><span data-stu-id="0ba3d-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="0ba3d-110">Příručka pro nasazení prostředí připojeného k cloudu (externí klienti)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="0ba3d-111">Průvodce nasazením podnikové sítě</span><span class="sxs-lookup"><span data-stu-id="0ba3d-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="0ba3d-112">Průvodce nasazením zabezpečeného prostředí offline</span><span class="sxs-lookup"><span data-stu-id="0ba3d-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="0ba3d-113">Scénář A: nasazení na zařízení připojená do cloudu</span><span class="sxs-lookup"><span data-stu-id="0ba3d-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="0ba3d-114">Tento scénář je porovnatelný z důvodů nasazení spravovaných mobilních zařízení v rámci společnosti.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="0ba3d-115">HoloLens 2 je nasazená pro použití primárně v prostředích, která jsou externí pro podnikovou síť.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="0ba3d-116">Firemní prostředky nejsou dostupné nebo můžou být omezené prostřednictvím sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="0ba3d-117">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="0ba3d-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="0ba3d-118">Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="0ba3d-119">Připojení k Azure AD pomocí automatického zápisu správy mobilních zařízení (MDM) – spravovaná MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="0ba3d-120">Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0ba3d-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="0ba3d-121">Podporuje se jeden nebo víc uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="0ba3d-122">Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="0ba3d-123">Jedna nebo víc aplikací se nasazuje přes MDM.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="0ba3d-124">Běžné výzvy</span><span class="sxs-lookup"><span data-stu-id="0ba3d-124">Common Challenges</span></span>
   * <span data-ttu-id="0ba3d-125">určení, které konfigurace MDM se mají použít na HoloLens 2 na základě požadavků na scénář</span><span class="sxs-lookup"><span data-stu-id="0ba3d-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="0ba3d-126">[![Scénář A diagram ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="0ba3d-127">odpovídající průvodce připojeným ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, použít licence podle potřeby a ověřit, že koncoví uživatelé můžou hned používat funkci vzdálená pomoc při instalaci zařízení.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="0ba3d-128">Pomocí Průvodce externími klienty nasaďte zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0ba3d-129">Průvodce nasazením propojeného prostředí v cloudu</span><span class="sxs-lookup"><span data-stu-id="0ba3d-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="0ba3d-130">Příručka pro nasazení prostředí připojeného k cloudu (externí klienti)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="0ba3d-131">Scénář B: nasazení v síti vaší organizace</span><span class="sxs-lookup"><span data-stu-id="0ba3d-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="0ba3d-132">tento scénář je stejný jako klasický vývoj pro většinu Windows 10 počítačů.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="0ba3d-133">HoloLens 2 je nasazená pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="0ba3d-134">Internetové a cloudové služby můžou být omezené.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="0ba3d-135">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="0ba3d-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="0ba3d-136">Wi-Fi síť je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetovým nebo cloudovým službám.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="0ba3d-137">Připojení k Azure AD s automatickým zápisem MDM</span><span class="sxs-lookup"><span data-stu-id="0ba3d-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="0ba3d-138">Spravovaná MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="0ba3d-139">Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0ba3d-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="0ba3d-140">Podporuje se jeden nebo víc uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="0ba3d-141">Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="0ba3d-142">Jedna nebo víc aplikací se nasazuje přes MDM.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="0ba3d-143">Běžné výzvy</span><span class="sxs-lookup"><span data-stu-id="0ba3d-143">Common Challenges</span></span>
   * <span data-ttu-id="0ba3d-144">HoloLens 2 nepodporuje místní službu AD join ani SCCM.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="0ba3d-145">Jenom Azure AD JOIN s MDM.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="0ba3d-146">mnoho společností dnes ještě v tomto scénáři nasazuje Windows 10 počítače, jako jsou místní zařízení připojená k AD, spravovaná pomocí System Center Configuration Manager (SCCM) a nemusí mít nasazenou a nakonfigurovanou infrastrukturu pro správu interních Windows 10 zařízení přes cloudová řešení MDM.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="0ba3d-147">jak HoloLens 2 je první cloudové zařízení, spoléhá se na internetovou a cloudovou službu připojenou pro ověřování uživatelů, aktualizace operačního systému, správu MDM a tak dále.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="0ba3d-148">při připojování k podnikové síti bude pravděpodobně nutné upravit pravidla Proxy serveru nebo brány Firewall tak, aby povolovala přístup pro HoloLens 2 a aplikace, které na něm běží.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="0ba3d-149">Připojení k podnikovému Wi-Fi obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="0ba3d-150">požadovaná infrastruktura nebo nastavení pro nasazení certifikátů do zařízení Windows 10 prostřednictvím MDM může být náročná na konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="0ba3d-151">[![Diagram ](images/deployment-guides-revised-scenario-b-01-1.png) scénáře B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="0ba3d-152">[![Diagram ](images/deployment-guides-revised-scenario-b-02-1.png) scénáře v B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="0ba3d-153">odpovídající příručka k podnikové síti obsahuje pokyny k tomu, jak zaregistrovat HoloLens 2 do vaší stávající správy zařízení, použít licence podle potřeby a ověřit, že koncoví uživatelé můžou pracovat s průvodcem Dynamics 365 a také používat vlastní obchodní aplikace po nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0ba3d-154">Průvodce nasazením podnikové sítě</span><span class="sxs-lookup"><span data-stu-id="0ba3d-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="0ba3d-155">Scénář C: nasazení v zabezpečeném prostředí offline</span><span class="sxs-lookup"><span data-stu-id="0ba3d-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="0ba3d-156">Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná místa.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="0ba3d-157">HoloLens 2 je nasazen pro použití primárně v režimu offline bez přístupu k síti nebo internetu.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="0ba3d-158">Základní běžné konfigurace</span><span class="sxs-lookup"><span data-stu-id="0ba3d-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="0ba3d-159">Připojení Wi-Fi je zakázané.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="0ba3d-160">V případě potřeby může být v případě potřeby povolená síť Ethernet přes USB.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="0ba3d-161">Nespravováno</span><span class="sxs-lookup"><span data-stu-id="0ba3d-161">Not Managed.</span></span>
   * <span data-ttu-id="0ba3d-162">Místní uživatelský účet pro přihlášení zařízení.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="0ba3d-163">HoloLens 2 podporuje pouze jeden místní účet.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="0ba3d-164">Různé úrovně konfigurace uzamčení zařízení se používají prostřednictvím zřizovacích balíčků na základě konkrétních případů použití.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="0ba3d-165">Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečení prostředí.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="0ba3d-166">Jedna nebo víc aplikací se nasazuje prostřednictvím zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="0ba3d-167">Běžné výzvy</span><span class="sxs-lookup"><span data-stu-id="0ba3d-167">Common Challenges</span></span>
   * <span data-ttu-id="0ba3d-168">Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="0ba3d-169">cloudové služby se nedají použít, proto omezení možností HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="0ba3d-170">Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="0ba3d-171">[![Offline zabezpečený diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0ba3d-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="0ba3d-172">odpovídající průvodce zabezpečenou nápovědou poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který bude uzamknout HoloLens 2 pro použití v zabezpečených prostředích.</span><span class="sxs-lookup"><span data-stu-id="0ba3d-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0ba3d-173">Průvodce nasazením zabezpečeného prostředí offline</span><span class="sxs-lookup"><span data-stu-id="0ba3d-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


