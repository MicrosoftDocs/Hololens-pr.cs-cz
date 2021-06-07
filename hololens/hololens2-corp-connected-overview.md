---
title: Průvodce nasazením – Firemní zařízení HoloLens 2 s Dynamics 365 – přehled
description: Zjistěte, jak zaregistrovat zařízení HoloLens 2 pomocí průvodců Dynamics 365 přes podnikovou připojenou síť.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Správa zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ee6c24f65e5990f1e84a71d86b24dd782cf9f4cc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377692"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="0790b-104">Průvodce nasazením – Průvodci pro Zařízení HoloLens 2 s Dynamics 365 – přehled</span><span class="sxs-lookup"><span data-stu-id="0790b-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="0790b-105">Tato příručka pomůže IT specialistům plánovat a nasazovat Microsoft HoloLens 2 pomocí průvodců Dynamics 365 (průvodci) pro jejich organizaci.</span><span class="sxs-lookup"><span data-stu-id="0790b-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="0790b-106">Tato příručka je skvělá pro pilotní i produkční nasazení a podobá se scénáři [B: Nasazení](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) v síti vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="0790b-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="0790b-107">Po otestování testování konceptu můžete pomocí tohoto průvodce pokračovat v integraci HoloLens do vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="0790b-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="0790b-108">V této příručce se budeme řídit tím, jak zaregistrovat zařízení do stávající správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé po nastavení zařízení budou moct používat příručku k Dynamics 365 a používat vlastní obchodní aplikace.</span><span class="sxs-lookup"><span data-stu-id="0790b-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0790b-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0790b-109">Prerequisites</span></span>

<span data-ttu-id="0790b-110">Už by měla být k dispozici následující infrastruktura:</span><span class="sxs-lookup"><span data-stu-id="0790b-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="0790b-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0790b-111">Wi-Fi</span></span>
    - <span data-ttu-id="0790b-112">Interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetu nebo cloudovým službám</span><span class="sxs-lookup"><span data-stu-id="0790b-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="0790b-113">Ověřování pomocí certifikátu na základě zařízení.</span><span class="sxs-lookup"><span data-stu-id="0790b-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="0790b-114">Azure Active Directory (Azure AD) Join s automatickou registrací MDM[(je potřeba předplatné Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="0790b-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="0790b-115">Správa MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="0790b-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="0790b-116">Jedna nebo více aplikací se nasadí prostřednictvím MDM.</span><span class="sxs-lookup"><span data-stu-id="0790b-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="0790b-117">Síť</span><span class="sxs-lookup"><span data-stu-id="0790b-117">Network</span></span> 
    - <span data-ttu-id="0790b-118">Certifikáty (SCEP nebo PKCS)</span><span class="sxs-lookup"><span data-stu-id="0790b-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="0790b-119">Konfigurace proxy serveru</span><span class="sxs-lookup"><span data-stu-id="0790b-119">Proxy configuration</span></span>
- <span data-ttu-id="0790b-120">Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0790b-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="0790b-121">Podporuje se jeden nebo více uživatelů na zařízení.</span><span class="sxs-lookup"><span data-stu-id="0790b-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="0790b-122">Různé úrovně konfigurace uzamčení zařízení použité na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací</span><span class="sxs-lookup"><span data-stu-id="0790b-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="0790b-123">Průvodci licencování a požadavky</span><span class="sxs-lookup"><span data-stu-id="0790b-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="0790b-124">Účet Azure AD</span><span class="sxs-lookup"><span data-stu-id="0790b-124">Azure AD account</span></span>
- <span data-ttu-id="0790b-125">Dynamics 365 Guides applications PC and HoloLens</span><span class="sxs-lookup"><span data-stu-id="0790b-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="0790b-126">Předplatné průvodců Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0790b-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="0790b-127">Microsoft Dataverse (zahrnuto)</span><span class="sxs-lookup"><span data-stu-id="0790b-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="0790b-128">Power Apps (zahrnuto)</span><span class="sxs-lookup"><span data-stu-id="0790b-128">Power Apps (included)</span></span>
- <span data-ttu-id="0790b-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="0790b-129">Power BI Desktop</span></span>
- <span data-ttu-id="0790b-130">Připojení k síti</span><span class="sxs-lookup"><span data-stu-id="0790b-130">Network Connectivity</span></span>

<span data-ttu-id="0790b-131">[![Diagram propojené sítě společnosti, fáze 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0790b-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="0790b-132">[![Diagram propojené sítě společnosti, fáze 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="0790b-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="0790b-133">V této příručce:</span><span class="sxs-lookup"><span data-stu-id="0790b-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="0790b-134">Příprava</span><span class="sxs-lookup"><span data-stu-id="0790b-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="0790b-135">Seznamte se se základy infrastruktury pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0790b-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="0790b-136">Přečtěte si další informace o Službě Azure AD a nastavte si ji, pokud ji nemáte.</span><span class="sxs-lookup"><span data-stu-id="0790b-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="0790b-137">Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0790b-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="0790b-138">Přečtěte si další informace o MDM a nastavení s Intune, pokud ho ještě nemáte připravený.</span><span class="sxs-lookup"><span data-stu-id="0790b-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="0790b-139">Seznamte se s Wi-Fi založenou na certifikátech.</span><span class="sxs-lookup"><span data-stu-id="0790b-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="0790b-140">Seznamte se s proxy serverem.</span><span class="sxs-lookup"><span data-stu-id="0790b-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="0790b-141">Seznamte se s používáním obchodních aplikací.</span><span class="sxs-lookup"><span data-stu-id="0790b-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="0790b-142">Přečtěte si další informace o tom, jak můžete používat příručky pro vaši organizaci.</span><span class="sxs-lookup"><span data-stu-id="0790b-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="0790b-143">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="0790b-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="0790b-144">Jak vytvářet uživatele a skupiny</span><span class="sxs-lookup"><span data-stu-id="0790b-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="0790b-145">Jak nastavit automatickou registraci</span><span class="sxs-lookup"><span data-stu-id="0790b-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="0790b-146">Jak nastavit Wi-Fi a profily pro připojení Wi-Fi podnikové sítě</span><span class="sxs-lookup"><span data-stu-id="0790b-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="0790b-147">Nahrání a přiřazení balíčků obchodních aplikací</span><span class="sxs-lookup"><span data-stu-id="0790b-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="0790b-148">Nastavení průvodců Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0790b-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="0790b-149">Konfigurace bezobrazovkového režimu (volitelné)</span><span class="sxs-lookup"><span data-stu-id="0790b-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="0790b-150">Postup konfigurace nástroje WDAC (volitelné)</span><span class="sxs-lookup"><span data-stu-id="0790b-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="0790b-151">Nasadit</span><span class="sxs-lookup"><span data-stu-id="0790b-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="0790b-152">Ověření registrace přes zařízení a MDM</span><span class="sxs-lookup"><span data-stu-id="0790b-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="0790b-153">Ověřte Wi-Fi certifikáty.</span><span class="sxs-lookup"><span data-stu-id="0790b-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="0790b-154">Ověřte instalaci obchodní aplikace.</span><span class="sxs-lookup"><span data-stu-id="0790b-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="0790b-155">Ověřte příručky prostřednictvím vytváření a provozu.</span><span class="sxs-lookup"><span data-stu-id="0790b-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="0790b-156">Údržba</span><span class="sxs-lookup"><span data-stu-id="0790b-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="0790b-157">Aktualizujte HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0790b-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="0790b-158">Jak aktualizovat příručky (aplikace pro Store).</span><span class="sxs-lookup"><span data-stu-id="0790b-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="0790b-159">Jak aktualizovat obchodní aplikace</span><span class="sxs-lookup"><span data-stu-id="0790b-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="0790b-160">Plán vývoje.</span><span class="sxs-lookup"><span data-stu-id="0790b-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="0790b-161">Vytvoření plánu podpory</span><span class="sxs-lookup"><span data-stu-id="0790b-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="0790b-162">Možnosti správy zařízení.</span><span class="sxs-lookup"><span data-stu-id="0790b-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="0790b-163">Další krok</span><span class="sxs-lookup"><span data-stu-id="0790b-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="0790b-164">Nasazení připojené k podnikové síti – Příprava</span><span class="sxs-lookup"><span data-stu-id="0790b-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
