---
title: Průvodce nasazením – nasazení HoloLens 2 připojené ke cloudu ve velkém měřítku pomocí nástroje Remote Assist – údržba
description: Naše tipy pro údržbu a podporu zařízení HoloLens přes síť připojenou ke cloudu vám posluchnou.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377694"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="3bedf-104">Údržba – Průvodce připojeným ke cloudu</span><span class="sxs-lookup"><span data-stu-id="3bedf-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="3bedf-105">Aktualizace</span><span class="sxs-lookup"><span data-stu-id="3bedf-105">Updates</span></span>

<span data-ttu-id="3bedf-106">Společnost Microsoft navrhla Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na služba Windows Update, jako je například možnost nasazovat aktualizace do skupin zařízení a definovat intervaly údržby pro instalaci aktualizací.</span><span class="sxs-lookup"><span data-stu-id="3bedf-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="3bedf-107">Zjistěte, jak [spravovat aktualizace HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) včetně plánovaných dnů, naplánovaného času a nastavení aktivních hodin v zařízení, aby se aktualizace řešly mimo pracovní dobu.</span><span class="sxs-lookup"><span data-stu-id="3bedf-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="3bedf-108">Remote Assist je In-Box aplikace a je možné ji aktualizovat prostřednictvím Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="3bedf-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="3bedf-109">Pro všechny aplikace, které jsou staženy prostřednictvím Microsoft Store, je možné je aktualizovat [prostřednictvím Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) aplikace ručně.</span><span class="sxs-lookup"><span data-stu-id="3bedf-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="3bedf-110">Plán podpory</span><span class="sxs-lookup"><span data-stu-id="3bedf-110">Support Plan</span></span>

<span data-ttu-id="3bedf-111">Plán podpory je skvělá věc, kterou je třeba mít.</span><span class="sxs-lookup"><span data-stu-id="3bedf-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="3bedf-112">Je užitečné mít někoho nebo skupinu vytrénované na řešení potíží s procesem registrace na zařízeních HoloLens a také obecné použití zařízení HoloLens ve vaší organizaci.</span><span class="sxs-lookup"><span data-stu-id="3bedf-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="3bedf-113">Pokud chcete uživatelům umožnit rychlejší řešení problémů, doporučujeme, aby se proces eskalace zpracovával podobným způsobem jako v tomto pořadí:</span><span class="sxs-lookup"><span data-stu-id="3bedf-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="3bedf-114">Váš tým podpory.</span><span class="sxs-lookup"><span data-stu-id="3bedf-114">Your Support desk.</span></span>
2. <span data-ttu-id="3bedf-115">Váš tým HoloLens Expert</span><span class="sxs-lookup"><span data-stu-id="3bedf-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="3bedf-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumentace k řešení potíží s HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3bedf-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="3bedf-117">Kontaktovat podporu</span><span class="sxs-lookup"><span data-stu-id="3bedf-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="3bedf-118">Plán vývoje</span><span class="sxs-lookup"><span data-stu-id="3bedf-118">Development Plan</span></span>

<span data-ttu-id="3bedf-119">Když je zařízení úspěšně zaregistrované, jste připraveni na zařízení nasadit obchodní aplikace (obchodní aplikace).</span><span class="sxs-lookup"><span data-stu-id="3bedf-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="3bedf-120">Jedná se o vlastní aplikace vytvořené pro vaši organizaci&#39;potřebám.</span><span class="sxs-lookup"><span data-stu-id="3bedf-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="3bedf-121">Pokud už máte obchodní aplikaci, můžete&#39;k nasazení aplikace [prostřednictvím MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="3bedf-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="3bedf-122">Pokud&#39;jinou metodu, přečtěte si přehled nasazení aplikace pro [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) abyste se dozvěděli další metody nasazení obchodní aplikace do zařízení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="3bedf-123">Pokud jste&#39;vytvořili vlastní obchodní aplikaci nebo jste stále v procesu vytváření, přečtěte si naše dokumenty k vývoji pro hybridní realitu, kde můžete začít s navrhováním a [vytvářením prototypů,](https://docs.microsoft.com/windows/mixed-reality/design/design) nebo se seznamte se základními koncepty a začněte s vývojem hybridní [reality.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="3bedf-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="3bedf-124">Správa zařízení</span><span class="sxs-lookup"><span data-stu-id="3bedf-124">Device Management</span></span> 

<span data-ttu-id="3bedf-125">I když tento průvodce mluvil o nastavení Mobile Správa zařízení (MDM), nebyl použit k použití omezení zařízení nebo zásad, které se použily na zařízení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="3bedf-126">Pomocí správy zařízení je možné povolit přístup pomocí certifikátů nebo omezit přístup s různými omezeními zařízení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="3bedf-127">V mnoha případech mohou mít zařízení omezení připojení, jako je Bluetooth, VPN nebo USB, nebo dokonce vypnout přístup k fotoaparátu nebo mikrofonu.</span><span class="sxs-lookup"><span data-stu-id="3bedf-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="3bedf-128">Pokud vás některý z těchto zájmů zajímá, doporučujeme přečíst si naši stránku [běžných omezení zařízení.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="3bedf-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="3bedf-129">Existují i další složitější omezení zařízení, která můžete použít.</span><span class="sxs-lookup"><span data-stu-id="3bedf-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="3bedf-130">Například:</span><span class="sxs-lookup"><span data-stu-id="3bedf-130">Such as:</span></span>

- <span data-ttu-id="3bedf-131">Omezení stránek, které lze zobrazit v aplikaci Nastavení, pomocí [NastaveníStránkaVisibility,](settings-uri-list.md)což uživatelům umožňuje přístup jenom k nastavením, která potřebují upravit, jako je například změna Wi-Fi připojení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="3bedf-132">Pomocí [bezobrazovkového režimu](hololens-kiosk.md) omezte uživatelské rozhraní, které se zobrazí uživatelům na zařízení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="3bedf-133">Kiosky můžete nastavit tak, aby se jedna aplikace nebo několik aplikací s vlastní úvodní stránkou zobrazují.</span><span class="sxs-lookup"><span data-stu-id="3bedf-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="3bedf-134">Kiosky mohou také různým uživatelům prezentovat různá prostředí.</span><span class="sxs-lookup"><span data-stu-id="3bedf-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="3bedf-135">[Řízení aplikací systému Windows (WDAC), aby](windows-defender-application-control-wdac.md) se určité aplikace nebo procesy zcela nespouštěl.</span><span class="sxs-lookup"><span data-stu-id="3bedf-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="3bedf-136">Pokud se chcete dozvědět více o různých metodách správy zařízení nebo omezeních zařízení, udělejte další krok a přečtěte si naše Správa zařízení zařízení.</span><span class="sxs-lookup"><span data-stu-id="3bedf-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="3bedf-137">Další krok</span><span class="sxs-lookup"><span data-stu-id="3bedf-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3bedf-138">Přečtěte si informace o zprostředkovateli csP a Správa zařízení o funkcích.</span><span class="sxs-lookup"><span data-stu-id="3bedf-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)