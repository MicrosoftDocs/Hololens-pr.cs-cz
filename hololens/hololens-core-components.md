---
title: plánování nasazení HoloLens 2 v komerčním prostředí
description: přečtěte si o základních potřebách pro nasazení a správu HoloLens v podnikových prostředích, včetně infrastruktury, azure active directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635785"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="61a08-103">plánování nasazení HoloLens 2 v komerčním prostředí</span><span class="sxs-lookup"><span data-stu-id="61a08-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="61a08-104">Přehled</span><span class="sxs-lookup"><span data-stu-id="61a08-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="61a08-105">tento přehled je určený k tomu, aby odborníci v oblasti IT pochopili důležité informace o nasazení a správě zařízení Microsoft HoloLens 2 v rámci organizace.</span><span class="sxs-lookup"><span data-stu-id="61a08-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="61a08-106">informace o koncových uživatelích zařízení najdete v článku o tom, jak začít [používat HoloLens 2](hololens2-setup.md) .</span><span class="sxs-lookup"><span data-stu-id="61a08-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="61a08-107">HoloLens 2 se spouští na Windows 10 Holographic, která poskytuje organizacím robustní, flexibilní a integrované technologie pro správu mobilních zařízení a aplikací.</span><span class="sxs-lookup"><span data-stu-id="61a08-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="61a08-108">Windows 10 Holographic podporuje komplexní správu životního cyklu zařízení, aby společnosti poskytovaly kontrolu nad svými zařízeními, daty a aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="61a08-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="61a08-109">HoloLens 2 je možné snadno začlenit do standardních postupů životního cyklu, od registrace zařízení, konfigurace a správy aplikací až po údržbu a vyřazení z provozu pomocí komplexního řešení pro správu mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="61a08-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="61a08-110">následující kroky a videa vám pomůžou s postupem HoloLens 2 při přijímání v rámci vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="61a08-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> <span data-ttu-id="61a08-112">**[obvyklé scénáře nasazení](hololens-requirements.md)**: pochopení scénářů nasazení a zkoumání základních součástí potřebných k nasazení zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61a08-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Krok 2](images/2green.png)| <br/> <span data-ttu-id="61a08-114">**[příprava](#prepare)**: seznámení se základy infrastruktury potřebnými pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61a08-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Krok 3](images/3green.png) | <br/> <span data-ttu-id="61a08-116">**[Konfigurace](#configure)**: Naučte se konfigurovat základní komponenty pro cloudové nasazení.</span><span class="sxs-lookup"><span data-stu-id="61a08-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Krok 4](images/4green.png) | <br/> <span data-ttu-id="61a08-118">**[Nasazení](#deploy)**: Zjistěte, jak vaše zařízení nasadit a jak bezpečně a efektivně distribuovat aplikace.</span><span class="sxs-lookup"><span data-stu-id="61a08-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Krok 5](images/5green.png) | <br/> <span data-ttu-id="61a08-120">**[údržba](#maintain)**: zjistěte, co je potřeba pro správné udržování stavu zařízení HoloLens 2 a zajištění souladu s podnikovými zásadami.</span><span class="sxs-lookup"><span data-stu-id="61a08-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="61a08-121">Příprava</span><span class="sxs-lookup"><span data-stu-id="61a08-121">Prepare</span></span>

<span data-ttu-id="61a08-122">seznamte se se základními službami infrastruktury potřebnými k podpoře plné sady možností HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61a08-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="61a08-123">Komponenta</span><span class="sxs-lookup"><span data-stu-id="61a08-123">Component</span></span> | <span data-ttu-id="61a08-124">Popis</span><span class="sxs-lookup"><span data-stu-id="61a08-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="61a08-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="61a08-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="61a08-126">poskytuje správu identit a přístupu pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61a08-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="61a08-127">Správa mobilních zařízení</span><span class="sxs-lookup"><span data-stu-id="61a08-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="61a08-128">spravuje HoloLens 2 zařízení připojená k vašemu tenantovi.</span><span class="sxs-lookup"><span data-stu-id="61a08-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="61a08-129">Síť Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="61a08-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="61a08-130">Wi-Fi je k dispozici a zařízení je možné připojit k Internetu</span><span class="sxs-lookup"><span data-stu-id="61a08-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="61a08-131">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="61a08-131">Configure</span></span>

<span data-ttu-id="61a08-132">používejte intune a autopilot jako řešení s nízkým dotykem pro registraci a konfiguraci HoloLens 2 pro tenanta Azure AD vaší organizace a MDM.</span><span class="sxs-lookup"><span data-stu-id="61a08-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="61a08-133">Komponenta</span><span class="sxs-lookup"><span data-stu-id="61a08-133">Component</span></span> | <span data-ttu-id="61a08-134">Popis</span><span class="sxs-lookup"><span data-stu-id="61a08-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="61a08-135">Automatický zápis</span><span class="sxs-lookup"><span data-stu-id="61a08-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="61a08-136">Po počátečním přihlášení se zařízení automaticky registrují ve službě Azure AD a zaregistrují se do MDM.</span><span class="sxs-lookup"><span data-stu-id="61a08-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="61a08-137">Licence k aplikacím</span><span class="sxs-lookup"><span data-stu-id="61a08-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="61a08-138">Dá se použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.</span><span class="sxs-lookup"><span data-stu-id="61a08-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="61a08-139">Uživatelé a skupiny Azure</span><span class="sxs-lookup"><span data-stu-id="61a08-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="61a08-140">pomáhá přiřadit konfigurace a licence pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="61a08-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="61a08-141">Nasadit</span><span class="sxs-lookup"><span data-stu-id="61a08-141">Deploy</span></span>

<span data-ttu-id="61a08-142">distribuujte zařízení HoloLens 2 a ověřte jejich konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="61a08-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="61a08-143">Komponenta</span><span class="sxs-lookup"><span data-stu-id="61a08-143">Component</span></span> | <span data-ttu-id="61a08-144">Popis</span><span class="sxs-lookup"><span data-stu-id="61a08-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="61a08-145">Ověřování registrace</span><span class="sxs-lookup"><span data-stu-id="61a08-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="61a08-146">ověřte, jestli je zařízení připojené k azure AD, Nastavení nebo azure Portal.</span><span class="sxs-lookup"><span data-stu-id="61a08-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="61a08-147">Ověření certifikátu</span><span class="sxs-lookup"><span data-stu-id="61a08-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="61a08-148">Zkontrolujte nastavení a ověřte, zda byly správně distribuovány.</span><span class="sxs-lookup"><span data-stu-id="61a08-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="61a08-149">Ověřit instalace aplikace</span><span class="sxs-lookup"><span data-stu-id="61a08-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="61a08-150">potvrďte, že je aplikace přítomná a funguje na vašem HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="61a08-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="61a08-151">Údržba</span><span class="sxs-lookup"><span data-stu-id="61a08-151">Maintain</span></span>

<span data-ttu-id="61a08-152">použijte web Windows Update pro firmy společně s vaším systémem MDM nebo Microsoft Store, aby se zajistilo, že se vaše flotila HoloLens 2 a aplikace aktualizovala.</span><span class="sxs-lookup"><span data-stu-id="61a08-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="61a08-153">Komponenta</span><span class="sxs-lookup"><span data-stu-id="61a08-153">Component</span></span> | <span data-ttu-id="61a08-154">Popis</span><span class="sxs-lookup"><span data-stu-id="61a08-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="61a08-155">aktualizace HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="61a08-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="61a08-156">konfigurace aktualizací podle potřeby prostřednictvím Windows aktualizací pro firmy</span><span class="sxs-lookup"><span data-stu-id="61a08-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="61a08-157">Aktualizace aplikací</span><span class="sxs-lookup"><span data-stu-id="61a08-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="61a08-158">Konfigurace prostřednictvím systému MDM nebo Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="61a08-158">Configure through your MDM system or the Microsoft Store</span></span>
