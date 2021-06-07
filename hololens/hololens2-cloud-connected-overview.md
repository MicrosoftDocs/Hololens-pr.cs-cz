---
title: Přehled připojení HoloLens 2 ke cloudu s funkcí Remote Assist
description: Naučte se registrovat zařízení HoloLens 2 přes cloudovou propojenou síť pomocí programu Vzdálená pomoc pro Dynamics 365.
keywords: HoloLens, Správa, připojení k cloudu, Vzdálená pomoc, AAD, Azure AD, MDM, Správa mobilních zařízení
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377536"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="d2050-104">Průvodce nasazením – Cloud s připojením HoloLens 2 s funkcí Remote Assist – přehled</span><span class="sxs-lookup"><span data-stu-id="d2050-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="d2050-105">Tato příručka pomáhá odborníkům v oblasti IT plánovat a nasazovat zařízení Microsoft HoloLens 2 do své organizace s cílem zajistit, aby byla tato zařízení připojená k vaší organizaci pomocí programu Remote Assist služby Dynamics 365, který je připravený k použití.</span><span class="sxs-lookup"><span data-stu-id="d2050-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="d2050-106">Mějte na paměti, že tato akce bude sloužit jako model nasazení pro účely konceptu do vaší organizace v rámci nejrůznějších případů použití HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d2050-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="d2050-107">V této příručce se dozvíte, jak zaregistrovat vaše zařízení do správy zařízení, použít licence podle potřeby a ověřit, jestli koncoví uživatelé můžou hned po nastavení zařízení hned používat vzdálenou pomoc.</span><span class="sxs-lookup"><span data-stu-id="d2050-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="d2050-108">Pokud to chcete provést, přejdeme na důležité části infrastruktury potřebné k tomu, aby se daly nastavit a spustit – dosahování nasazení ve velkém měřítku s využitím HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d2050-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="d2050-109">[![Scénář ](./images/deployment-guides-revised-scenario-a.png) připojení ke cloudu](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2050-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="d2050-110">V této příručce</span><span class="sxs-lookup"><span data-stu-id="d2050-110">In this Guide</span></span>

<span data-ttu-id="d2050-111">Tato příručka má konkrétní cíl nastavení vzdáleného asistence v rámci vaší organizace na zařízeních HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d2050-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="d2050-112">Pokryjeme Necessities potřebný k dosažení tohoto cíle.</span><span class="sxs-lookup"><span data-stu-id="d2050-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="d2050-113">Aby se zajistilo zaměření na tento cíl, některá příprava a konfigurace se předem vybere, aby se optimalizoval pro toto nasazení, nebo aby se snížily položky potřebné ke konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="d2050-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="d2050-114">O těchto volbách budete informováni a můžete přizpůsobit nasazení na základě vašich obchodních potřeb.</span><span class="sxs-lookup"><span data-stu-id="d2050-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="d2050-115">Toto nastavení se podobá [scénáři a: nasazení do cloudových připojení](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), což je dobrá možnost pro spoustu nasazení konceptů, která budou zahrnovat:</span><span class="sxs-lookup"><span data-stu-id="d2050-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="d2050-116">Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.</span><span class="sxs-lookup"><span data-stu-id="d2050-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="d2050-117">Připojení Azure AD k automatické registraci MDM – spravovaná MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="d2050-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="d2050-118">Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d2050-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="d2050-119">Podporuje se jeden nebo víc uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="d2050-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="d2050-120">Na základě specifických případů použití se aplikují různé úrovně konfigurací uzamčení zařízení, od úplného otevření do veřejného terminálu s jednou aplikací.</span><span class="sxs-lookup"><span data-stu-id="d2050-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="d2050-121">V této příručce se nepoužijí žádná další omezení zařízení ani konfigurace, ale doporučujeme vám, abyste tyto možnosti prozkoumali po dokončení.</span><span class="sxs-lookup"><span data-stu-id="d2050-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="d2050-122">Další informace o funkci Remote Assist</span><span class="sxs-lookup"><span data-stu-id="d2050-122">Learn about Remote Assist</span></span>

<span data-ttu-id="d2050-123">Vzdálená pomoc umožňuje spolupráci a opravy, vzdálenou kontrolu a také sdílení a školení ve znalostní bázi.</span><span class="sxs-lookup"><span data-stu-id="d2050-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="d2050-124">Propojením lidí s různými rolemi a umístěním se technik, který používá vzdálenou pomoc, může připojit se vzdáleným spolupracovníka v Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2050-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="d2050-125">Můžou kombinovat video, snímky obrazovky a poznámky a vyřešit problémy v reálném čase, i když&#39;t ve stejném umístění.</span><span class="sxs-lookup"><span data-stu-id="d2050-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="d2050-126">Vzdálení spolupracovníci můžou vkládat referenční obrázky, schémata a další užitečné informace, které&#39;pracovník s fyzickým prostorem.</span><span class="sxs-lookup"><span data-stu-id="d2050-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="d2050-127">V této příručce budete:</span><span class="sxs-lookup"><span data-stu-id="d2050-127">In this guide you will:</span></span>

<span data-ttu-id="d2050-128">Systém</span><span class="sxs-lookup"><span data-stu-id="d2050-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d2050-129">Seznamte se se základy infrastruktury pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d2050-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="d2050-130">Přečtěte si další informace o službě Azure AD a nastavte ji, pokud ji&#39;t.</span><span class="sxs-lookup"><span data-stu-id="d2050-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="d2050-131">Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d2050-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="d2050-132">Přečtěte si další informace o MDM a nastavte Intune, pokud&#39;t už máte připravený.</span><span class="sxs-lookup"><span data-stu-id="d2050-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="d2050-133">Seznamte se s požadavky na síť pro vzdálenou pomoc.</span><span class="sxs-lookup"><span data-stu-id="d2050-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="d2050-134">Volitelně: připojení k prostředkům organizace pomocí sítě VPN</span><span class="sxs-lookup"><span data-stu-id="d2050-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="d2050-135">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="d2050-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d2050-136">Vytváření uživatelů a skupin.</span><span class="sxs-lookup"><span data-stu-id="d2050-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="d2050-137">Jak nastavit automatickou registraci v rámci služby Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d2050-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="d2050-138">Jak přiřadit licence k aplikacím.</span><span class="sxs-lookup"><span data-stu-id="d2050-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="d2050-139">Nasazení:</span><span class="sxs-lookup"><span data-stu-id="d2050-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d2050-140">Nastavte svůj HoloLens 2 a ověřte registraci.</span><span class="sxs-lookup"><span data-stu-id="d2050-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="d2050-141">Ověřte, že můžete provést volání vzdáleného asistence.</span><span class="sxs-lookup"><span data-stu-id="d2050-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="d2050-142">Vést</span><span class="sxs-lookup"><span data-stu-id="d2050-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d2050-143">Jak aktualizovat vzdálenou pomoc pomocí aplikace Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d2050-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="d2050-144">Vytváří se plán podpory.</span><span class="sxs-lookup"><span data-stu-id="d2050-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="d2050-145">Plán vývoje.</span><span class="sxs-lookup"><span data-stu-id="d2050-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="d2050-146">Další krok</span><span class="sxs-lookup"><span data-stu-id="d2050-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d2050-147">Nasazení připojené ke cloudu – Příprava</span><span class="sxs-lookup"><span data-stu-id="d2050-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

