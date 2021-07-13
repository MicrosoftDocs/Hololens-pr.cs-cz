---
title: Přehled připojení ke cloudu HoloLens 2 pomocí vzdálené pomoci
description: Zjistěte, jak zaregistrovat HoloLens 2 přes síť připojenou ke cloudu pomocí Dynamics 365 Remote Assistu.
keywords: HoloLens, správa, připojení ke cloudu, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639756"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="ba5f4-104">Průvodce nasazením – Cloud connected HoloLens 2 with Remote Assist – Přehled</span><span class="sxs-lookup"><span data-stu-id="ba5f4-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="ba5f4-105">Tato příručka pomůže IT specialistům plánovat a nasazovat Microsoft HoloLens 2 zařízení s Remote Assistem v organizaci.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="ba5f4-106">To bude sloužit jako model pro nasazení do vaší organizace v rámci různých scénářů HoloLens 2 případy použití.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="ba5f4-107">Nastavení se podobá [scénáři A: Nasazení do zařízení s připojením ke cloudu.](common-scenarios.md#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="ba5f4-108">V této příručce se budeme řídit tím, jak zaregistrovat zařízení do správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="ba5f4-109">Za tímto účelem si projdeme důležité části infrastruktury, které jsou potřeba k nastavení a z provozu – k dosažení nasazení ve velkém měřítku s HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="ba5f4-110">V tomto průvodci se nebudou používat žádná další omezení ani konfigurace zařízení, ale doporučujeme vám tyto možnosti prozkoumat po dokončení.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba5f4-111">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba5f4-111">Prerequisites</span></span>

<span data-ttu-id="ba5f4-112">Aby bylo možné nasadit HoloLens 2, měla by být zavedena následující infrastruktura.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="ba5f4-113">Pokud ne, nastavení Azure a Intune je součástí tohoto průvodce:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="ba5f4-114">Jedná se o nastavení podobné scénáři [A:](/hololens/common-scenarios#scenario-a)Nasazení do zařízení s připojením ke cloudu, což je dobrá možnost pro mnoho nasazení s potvrzením konceptu, které bude zahrnovat:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="ba5f4-115">Wi-Fi sítě jsou obvykle plně otevřené pro internet a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="ba5f4-116">Připojení ke službě Azure AD s automatickou registrací MDM – spravované pomocí MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="ba5f4-117">Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="ba5f4-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="ba5f4-118">Podporuje se jeden nebo více uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="Scénář připojení ke cloudu" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="ba5f4-120">Další informace o vzdálené pomoci</span><span class="sxs-lookup"><span data-stu-id="ba5f4-120">Learn about Remote Assist</span></span>

<span data-ttu-id="ba5f4-121">Remote Assist umožňuje spolupráci s údržbou a opravami, vzdálenou kontrolu a také sdílení znalostí a školení.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="ba5f4-122">Technik, který používá vzdálenou pomoc, se může spojit se vzdáleným spolupracovníkem v různých rolích a umístěních a může se spojit se vzdáleným spolupracovníkem Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="ba5f4-123">Mohou kombinovat video, snímky obrazovky a poznámky k řešení problémů v reálném čase, i když nejsou na stejném místě.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="ba5f4-124">Vzdálení spolupracovníci mohou vkládat referenční obrázky, schémata a další užitečné informace o fyzickém prostoru technika, aby mohli odkazovat na schéma při práci s hlavičkou a bez rukou na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="ba5f4-125">Licencování a požadavky služby Remote Assist</span><span class="sxs-lookup"><span data-stu-id="ba5f4-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="ba5f4-126">Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="ba5f4-127">[Předplatné Remote Assistu](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="ba5f4-128">Uživatel Dynamics 365 Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="ba5f4-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="ba5f4-129">Licence Remote Assistu</span><span class="sxs-lookup"><span data-stu-id="ba5f4-129">Remote Assist license</span></span>
- <span data-ttu-id="ba5f4-130">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="ba5f4-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="ba5f4-131">Microsoft Teams uživatele</span><span class="sxs-lookup"><span data-stu-id="ba5f4-131">Microsoft Teams user</span></span>

- <span data-ttu-id="ba5f4-132">Microsoft Teams nebo [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="ba5f4-133">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="ba5f4-133">Network connectivity</span></span>

<span data-ttu-id="ba5f4-134">Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="ba5f4-135">Pokud chcete zjistit, jestli se vyžaduje licence Information Barrier, podívejte se na článek Dodavatelé a zákazníci používají úplné funkce [Dynamics 365 Remote Assistu.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)</span><span class="sxs-lookup"><span data-stu-id="ba5f4-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="ba5f4-136">V této příručce:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-136">In this guide you will:</span></span>

<span data-ttu-id="ba5f4-137">Připravit:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ba5f4-138">Seznamte se se základy infrastruktury pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="ba5f4-139">Přečtěte si další informace o Službě Azure AD a nastavte ji,&#39;ji nemáte.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="ba5f4-140">Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="ba5f4-141">Přečtěte si další informace o MDM a nastavte intune, pokud&#39;ještě nemáte připravenou.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="ba5f4-142">Seznamte se s požadavky funkce Remote Assist na síť.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="ba5f4-143">Volitelně: Síť VPN pro připojení k prostředkům organizace</span><span class="sxs-lookup"><span data-stu-id="ba5f4-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="ba5f4-144">Konfigurace:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ba5f4-145">Vytvoření uživatelů a skupin</span><span class="sxs-lookup"><span data-stu-id="ba5f4-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="ba5f4-146">Jak nastavit automatickou registraci v rámci Azure AD</span><span class="sxs-lookup"><span data-stu-id="ba5f4-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="ba5f4-147">Postup přiřazení licencí aplikace</span><span class="sxs-lookup"><span data-stu-id="ba5f4-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="ba5f4-148">Nasazení:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ba5f4-149">Nastavte svou registraci HoloLens 2 a ověřte registraci.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="ba5f4-150">Ověřte, že můžete provést volání vzdálené pomoci.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="ba5f4-151">Udržovat:</span><span class="sxs-lookup"><span data-stu-id="ba5f4-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="ba5f4-152">Jak aktualizovat remote assist pomocí Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="ba5f4-153">Vytvoření plánu podpory</span><span class="sxs-lookup"><span data-stu-id="ba5f4-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="ba5f4-154">Plán vývoje.</span><span class="sxs-lookup"><span data-stu-id="ba5f4-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="ba5f4-155">Další krok</span><span class="sxs-lookup"><span data-stu-id="ba5f4-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba5f4-156">Nasazení připojené ke cloudu – Příprava</span><span class="sxs-lookup"><span data-stu-id="ba5f4-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

