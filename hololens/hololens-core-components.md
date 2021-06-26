---
title: Plánování nasazení HoloLens 2 v komerčním prostředí
description: Seznamte se se základními potřebami pro nasazení a správu HoloLens v podnikových prostředích, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961401"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="ab9c6-103">Plánování nasazení HoloLens 2 v komerčním prostředí</span><span class="sxs-lookup"><span data-stu-id="ab9c6-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="ab9c6-104">Přehled</span><span class="sxs-lookup"><span data-stu-id="ab9c6-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="ab9c6-105">Tento přehled pomáhá IT specialistům pochopit aspekty nasazení a správy Microsoft HoloLens 2 v rámci organizace.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="ab9c6-106">Pokud chcete začít, podívejte se [na základní informace pro](hololens2-setup.md) koncové uživatele zařízení.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="ab9c6-107">HoloLens 2 běží na Windows 10 Holographic, který organizacím poskytuje robustní, flexibilní integrované technologie správy mobilních zařízení a aplikací.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="ab9c6-108">Windows 10 Holographic podporuje správu životního cyklu zařízení od konce, aby společnosti nad svými zařízeními, daty a aplikacemi kontrolul.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="ab9c6-109">HoloLens 2 je možné snadno začlenit do standardních postupů životního cyklu, od registrace zařízení, konfigurace a správy aplikací až po údržbu a vyřazení pomocí komplexního řešení pro správu mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="ab9c6-110">Následující kroky vás pomůžou provést procesem přijetí HoloLens 2 v rámci vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> <span data-ttu-id="ab9c6-112">**[Běžné scénáře nasazení:](hololens-requirements.md)** Seznamte se se scénáři nasazení a prozkoumejte základní komponenty potřebné k nasazení zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Krok 2](images/2green.png)| <br/> <span data-ttu-id="ab9c6-114">**[Příprava:](#prepare)** Seznamte se se základy infrastruktury, které holoLens 2 potřebuje.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Krok 3](images/3green.png) | <br/> <span data-ttu-id="ab9c6-116">**[Konfigurace:](#configure)** Zjistěte, jak nakonfigurovat základní komponenty pro cloudové nasazení.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Krok 4](images/4green.png) | <br/> <span data-ttu-id="ab9c6-118">**[Nasazení:](#deploy)** Zjistěte, jak bezpečně a efektivně nasadit zařízení a distribuovat aplikace.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Krok 5](images/5green.png) | <br/> <span data-ttu-id="ab9c6-120">**[Údržba:](#maintain)** Zjistěte, co je potřeba ke správné údržbě stavu zařízení HoloLens 2 a zajištění dodržování firemních zásad.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="ab9c6-121">Příprava</span><span class="sxs-lookup"><span data-stu-id="ab9c6-121">Prepare</span></span>

<span data-ttu-id="ab9c6-122">Seznamte se se základními službami infrastruktury potřebnými k podpoře celé sady funkcí HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="ab9c6-123">Komponenta</span><span class="sxs-lookup"><span data-stu-id="ab9c6-123">Component</span></span> | <span data-ttu-id="ab9c6-124">Popis</span><span class="sxs-lookup"><span data-stu-id="ab9c6-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ab9c6-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ab9c6-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="ab9c6-126">Poskytuje správu identit a přístupu pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="ab9c6-127">Správa mobilních zařízení</span><span class="sxs-lookup"><span data-stu-id="ab9c6-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="ab9c6-128">Spravuje zařízení HoloLens 2 připojená k vašemu tenantovi.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="ab9c6-129">Síť Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ab9c6-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="ab9c6-130">Wi-Fi je k dispozici a zařízení je možné připojit k internetu.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="ab9c6-131">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="ab9c6-131">Configure</span></span>

<span data-ttu-id="ab9c6-132">Intune a Autopilot můžete použít jako nízko dotyková řešení pro registraci a konfiguraci HoloLens 2 v tenantovi Azure AD a MDM vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="ab9c6-133">Komponenta</span><span class="sxs-lookup"><span data-stu-id="ab9c6-133">Component</span></span> | <span data-ttu-id="ab9c6-134">Popis</span><span class="sxs-lookup"><span data-stu-id="ab9c6-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ab9c6-135">Automatická registrace</span><span class="sxs-lookup"><span data-stu-id="ab9c6-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="ab9c6-136">Po počátečním přihlášení se zařízení automaticky zaregistrují v Azure AD a zaregistrují se do MDM.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="ab9c6-137">Licence aplikací</span><span class="sxs-lookup"><span data-stu-id="ab9c6-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="ab9c6-138">Lze použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="ab9c6-139">Uživatelé a skupiny Azure</span><span class="sxs-lookup"><span data-stu-id="ab9c6-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="ab9c6-140">Pomáhá přiřazovat konfigurace a licence pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="ab9c6-141">Nasadit</span><span class="sxs-lookup"><span data-stu-id="ab9c6-141">Deploy</span></span>

<span data-ttu-id="ab9c6-142">Distribuujte zařízení HoloLens 2 a ověřte jejich konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="ab9c6-143">Komponenta</span><span class="sxs-lookup"><span data-stu-id="ab9c6-143">Component</span></span> | <span data-ttu-id="ab9c6-144">Popis</span><span class="sxs-lookup"><span data-stu-id="ab9c6-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ab9c6-145">Ověření registrace</span><span class="sxs-lookup"><span data-stu-id="ab9c6-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="ab9c6-146">V nastavení nebo na webu Azure Portal ověřte, že je zařízení připojené k Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="ab9c6-147">Ověření certifikátu</span><span class="sxs-lookup"><span data-stu-id="ab9c6-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="ab9c6-148">Zkontrolujte nastavení a ověřte, že se správně distribuují.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="ab9c6-149">Ověření instalací aplikace</span><span class="sxs-lookup"><span data-stu-id="ab9c6-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="ab9c6-150">Ověření přítomnosti aplikace a práce na HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ab9c6-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="ab9c6-151">Údržba</span><span class="sxs-lookup"><span data-stu-id="ab9c6-151">Maintain</span></span>

<span data-ttu-id="ab9c6-152">K Windows Update pro firmy vozového parku HoloLens 2 a aplikací používejte Microsoft Store správu mobilních zařízení a správu mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="ab9c6-153">Komponenta</span><span class="sxs-lookup"><span data-stu-id="ab9c6-153">Component</span></span> | <span data-ttu-id="ab9c6-154">Popis</span><span class="sxs-lookup"><span data-stu-id="ab9c6-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="ab9c6-155">Aktualizace HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ab9c6-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="ab9c6-156">Podle potřeby nakonfigurujte aktualizace prostřednictvím aktualizací Windows pro firmy.</span><span class="sxs-lookup"><span data-stu-id="ab9c6-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="ab9c6-157">Aktualizace aplikací</span><span class="sxs-lookup"><span data-stu-id="ab9c6-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="ab9c6-158">Konfigurace prostřednictvím systému MDM nebo Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ab9c6-158">Configure through your MDM system or the Microsoft Store</span></span>
