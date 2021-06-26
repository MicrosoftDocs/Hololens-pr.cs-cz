---
title: Přehled HoloLens 2 připojeného ke cloudu s remote assistem
description: Zjistěte, jak zaregistrovat zařízení HoloLens 2 přes síť připojenou ke cloudu pomocí Dynamics 365 Remote Assistu.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923529"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="e75d7-104">Průvodce nasazením – HoloLens 2 připojený ke cloudu se vzdáleným asistencí – přehled</span><span class="sxs-lookup"><span data-stu-id="e75d7-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="e75d7-105">Tato příručka pomůže IT specialistům plánovat a nasazovat Microsoft HoloLens 2 zařízení s Remote Assistem v organizaci.</span><span class="sxs-lookup"><span data-stu-id="e75d7-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="e75d7-106">To bude sloužit jako model pro nasazení do vaší organizace v rámci různých případů použití HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e75d7-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="e75d7-107">Nastavení se podobá [scénáři A: Nasazení do zařízení s připojením ke cloudu.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="e75d7-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="e75d7-108">V této příručce se budeme řídit tím, jak zaregistrovat zařízení do správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat.</span><span class="sxs-lookup"><span data-stu-id="e75d7-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="e75d7-109">Za tímto účelem si projdeme důležité části infrastruktury potřebné k nastavení a z provozu – k dosažení nasazení ve velkém měřítku pomocí HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e75d7-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="e75d7-110">V tomto průvodci se nebudou používat žádná další omezení ani konfigurace zařízení, ale doporučujeme vám tyto možnosti prozkoumat po dokončení.</span><span class="sxs-lookup"><span data-stu-id="e75d7-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e75d7-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e75d7-111">Prerequisites</span></span>

<span data-ttu-id="e75d7-112">Aby bylo možné nasadit HoloLens 2, měla by být zavedena následující infrastruktura.</span><span class="sxs-lookup"><span data-stu-id="e75d7-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="e75d7-113">Pokud ne, nastavení Azure a Intune je součástí tohoto průvodce:</span><span class="sxs-lookup"><span data-stu-id="e75d7-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="e75d7-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e75d7-114">Wi-Fi</span></span>
    - <span data-ttu-id="e75d7-115">Sítě jsou obvykle otevřené pro internet a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="e75d7-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="e75d7-116">Azure Active Directory (Azure AD) Join s automatickou registrací MDM[(je potřeba předplatné Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="e75d7-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="e75d7-117">Správa MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="e75d7-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="e75d7-118">Jedna nebo více aplikací se nasadí přes MDM.</span><span class="sxs-lookup"><span data-stu-id="e75d7-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="e75d7-119">Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e75d7-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="e75d7-120">Podporuje se jeden nebo více uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="e75d7-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scénář připojení ke cloudu" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="e75d7-122">Další informace o vzdálené pomoci</span><span class="sxs-lookup"><span data-stu-id="e75d7-122">Learn about Remote Assist</span></span>

<span data-ttu-id="e75d7-123">Remote Assist umožňuje spolupráci s údržbou a opravami, vzdálenou kontrolu a také sdílení znalostí a školení.</span><span class="sxs-lookup"><span data-stu-id="e75d7-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="e75d7-124">Propojením lidí v různých rolích a umístěních se technik pomocí vzdálené pomoci může spojit se vzdáleným spolupracovníkem v Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e75d7-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="e75d7-125">Mohou kombinovat video, snímky obrazovky a poznámky k řešení problémů v reálném čase, i když&#39;nejsou na stejném místě.</span><span class="sxs-lookup"><span data-stu-id="e75d7-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="e75d7-126">Vzdálení spolupracovníci mohou vkládat referenční obrázky, schémata&#39;další užitečné informace technikovi fyzický prostor, aby mohli při práci na HoloLensu bez rukou odkazovat na schéma.</span><span class="sxs-lookup"><span data-stu-id="e75d7-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="e75d7-127">Licencování a požadavky služby Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e75d7-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="e75d7-128">Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)</span><span class="sxs-lookup"><span data-stu-id="e75d7-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="e75d7-129">[Předplatné Remote Assistu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="e75d7-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="e75d7-130">Uživatel Dynamics 365 Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="e75d7-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="e75d7-131">Licence Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="e75d7-131">Remote Assist license</span></span>
- <span data-ttu-id="e75d7-132">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="e75d7-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="e75d7-133">Uživatel Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e75d7-133">Microsoft Teams user</span></span>

- <span data-ttu-id="e75d7-134">Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="e75d7-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="e75d7-135">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="e75d7-135">Network connectivity</span></span>

<span data-ttu-id="e75d7-136">Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers.</span><span class="sxs-lookup"><span data-stu-id="e75d7-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="e75d7-137">Informace [o tom,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) jestli se vyžaduje licence Information Barrier, najdete v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="e75d7-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="e75d7-138">V této příručce:</span><span class="sxs-lookup"><span data-stu-id="e75d7-138">In this guide you will:</span></span>

<span data-ttu-id="e75d7-139">Připravit:</span><span class="sxs-lookup"><span data-stu-id="e75d7-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e75d7-140">Seznamte se se základy infrastruktury pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e75d7-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="e75d7-141">Přečtěte si další informace o Službě Azure AD a nastavte ji,&#39;ji nemáte.</span><span class="sxs-lookup"><span data-stu-id="e75d7-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="e75d7-142">Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e75d7-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="e75d7-143">Přečtěte si další informace o MDM a nastavte intune, pokud&#39;ještě nemáte připravenou.</span><span class="sxs-lookup"><span data-stu-id="e75d7-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="e75d7-144">Seznamte se s požadavky funkce Remote Assist na síť.</span><span class="sxs-lookup"><span data-stu-id="e75d7-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="e75d7-145">Volitelně: Síť VPN pro připojení k prostředkům organizace</span><span class="sxs-lookup"><span data-stu-id="e75d7-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="e75d7-146">Konfigurace:</span><span class="sxs-lookup"><span data-stu-id="e75d7-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e75d7-147">Vytvoření uživatelů a skupin</span><span class="sxs-lookup"><span data-stu-id="e75d7-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="e75d7-148">Jak nastavit automatickou registraci v rámci Azure AD</span><span class="sxs-lookup"><span data-stu-id="e75d7-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="e75d7-149">Postup přiřazení licencí aplikace</span><span class="sxs-lookup"><span data-stu-id="e75d7-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="e75d7-150">Nasazení:</span><span class="sxs-lookup"><span data-stu-id="e75d7-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e75d7-151">Nastavte holoLens 2 a ověřte registraci.</span><span class="sxs-lookup"><span data-stu-id="e75d7-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="e75d7-152">Ověřte, že můžete provést volání vzdálené pomoci.</span><span class="sxs-lookup"><span data-stu-id="e75d7-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="e75d7-153">Udržovat:</span><span class="sxs-lookup"><span data-stu-id="e75d7-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e75d7-154">Jak aktualizovat remote assist pomocí Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="e75d7-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="e75d7-155">Vytvoření plánu podpory</span><span class="sxs-lookup"><span data-stu-id="e75d7-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="e75d7-156">Plán vývoje.</span><span class="sxs-lookup"><span data-stu-id="e75d7-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="e75d7-157">Další krok</span><span class="sxs-lookup"><span data-stu-id="e75d7-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e75d7-158">Nasazení připojené ke cloudu – Příprava</span><span class="sxs-lookup"><span data-stu-id="e75d7-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

