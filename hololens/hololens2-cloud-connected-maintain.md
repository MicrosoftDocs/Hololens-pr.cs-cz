---
title: Průvodce nasazením – nasazení HoloLens 2 ve velkém měřítku pomocí nástroje Remote Assist – údržba
description: Udržujte si aktuální informace o našich tipech pro údržbu a HoloLens zařízení přes síť připojenou ke cloudu.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635156"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="7e6bb-104">Údržba – Průvodce připojeným ke cloudu</span><span class="sxs-lookup"><span data-stu-id="7e6bb-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="7e6bb-105">Aktualizace</span><span class="sxs-lookup"><span data-stu-id="7e6bb-105">Updates</span></span>

<span data-ttu-id="7e6bb-106">Společnost Microsoft navrhla službu Windows Update pro firmy, aby správcům IT poskytovala další funkce správy zaměřené na aktualizaci Windows, jako je například možnost nasazovat aktualizace do skupin zařízení a definovat intervaly pro správu a údržbu pro instalaci aktualizací.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="7e6bb-107">Zjistěte, [jak spravovat HoloLens,](/hololens/hololens-updates) včetně plánovaných dnů, naplánovaného času a nastavení aktivních hodin v zařízení, aby se aktualizace chytá mimo pracovní dobu.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="7e6bb-108">Remote Assist je In-Box aplikace a je možné ji aktualizovat prostřednictvím Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="7e6bb-109">Pro všechny aplikace, které jsou staženy prostřednictvím Microsoft Store, je možné je [aktualizovat prostřednictvím Microsoft Store](/hololens/holographic-store-apps#update-apps) aplikace ručně.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="7e6bb-110">Plán podpory</span><span class="sxs-lookup"><span data-stu-id="7e6bb-110">Support Plan</span></span>

<span data-ttu-id="7e6bb-111">Plán podpory je skvělá věc, kterou je třeba mít.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="7e6bb-112">Je užitečné mít někoho nebo skupinu natrénované na řešení potíží s procesem registrace na HoloLens zařízeních a také obecné použití HoloLens zařízení ve vaší organizaci.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="7e6bb-113">Pokud chcete uživatelům umožnit rychlejší řešení problémů, doporučujeme, aby se proces eskalace zpracovával podobným způsobem jako v tomto pořadí:</span><span class="sxs-lookup"><span data-stu-id="7e6bb-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="7e6bb-114">Váš tým podpory.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-114">Your Support desk.</span></span>
2. <span data-ttu-id="7e6bb-115">Váš tým HoloLens Expert</span><span class="sxs-lookup"><span data-stu-id="7e6bb-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="7e6bb-116">[HoloLens Docs](/hololens/)  /  [HoloLens dokumentace k řešení potíží](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="7e6bb-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="7e6bb-117">Kontaktovat podporu</span><span class="sxs-lookup"><span data-stu-id="7e6bb-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="7e6bb-118">Plán vývoje</span><span class="sxs-lookup"><span data-stu-id="7e6bb-118">Development Plan</span></span>

<span data-ttu-id="7e6bb-119">Když je zařízení úspěšně zaregistrované, jste připraveni na zařízení nasadit obchodní aplikace (obchodní aplikace).</span><span class="sxs-lookup"><span data-stu-id="7e6bb-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="7e6bb-120">Jedná se o vlastní aplikace vytvořené pro vaši organizaci&#39;potřebám.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="7e6bb-121">Pokud už máte obchodní aplikaci, můžete&#39;k nasazení aplikace [prostřednictvím MDM.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="7e6bb-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="7e6bb-122">Pokud chcete&#39;jinou metodu, přečtěte si přehled nasazení aplikace pro [HoloLens 2,](/hololens/app-deploy-overview) abyste se dozvěděli více o metodách nasazení obchodní aplikace do zařízení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="7e6bb-123">Pokud jste&#39;vytvořili vlastní obchodní aplikaci nebo jste stále v procesu vytváření, přečtěte si naše dokumenty k vývoji pro hybridní realitu, kde můžete začít s navrhováním a [vytvářením prototypů,](/windows/mixed-reality/design/design) nebo se seznamte se základními koncepty a začněte s vývojem hybridní [reality.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="7e6bb-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="7e6bb-124">Správa zařízení</span><span class="sxs-lookup"><span data-stu-id="7e6bb-124">Device Management</span></span> 

<span data-ttu-id="7e6bb-125">I když tento průvodce mluvil o nastavení Mobile Správa zařízení (MDM), nebyl použit k použití omezení zařízení nebo zásad, které se použily na zařízení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="7e6bb-126">Pomocí správy zařízení je možné povolit přístup pomocí certifikátů nebo omezit přístup s různými omezeními zařízení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="7e6bb-127">V mnoha případech mohou mít zařízení omezení připojení, jako Bluetooth, VPN nebo USB, nebo dokonce vypnout přístup k fotoaparátu nebo mikrofonu.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="7e6bb-128">Pokud vás některý z těchto zájmů zajímá, doporučujeme, abyste si přečetli naši běžnou [stránku omezení zařízení.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="7e6bb-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="7e6bb-129">Existují i další složitější omezení zařízení, která můžete použít.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="7e6bb-130">Například:</span><span class="sxs-lookup"><span data-stu-id="7e6bb-130">Such as:</span></span>

- <span data-ttu-id="7e6bb-131">Omezení stránek, které lze zobrazit v aplikaci Nastavení, pomocí [NastaveníStránkaVisibility,](settings-uri-list.md)což uživatelům umožňuje přístup jenom k nastavením, která potřebují upravit, například ke změně Wi-Fi připojení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="7e6bb-132">Pomocí [bezobrazovkového režimu](hololens-kiosk.md) omezte uživatelské rozhraní, které se zobrazí uživatelům na zařízení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="7e6bb-133">Bezobrazovkové terminály můžete nastavit tak, aby se jedna aplikace nebo několik aplikací s vlastní úvodní stránkou zobrazují.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="7e6bb-134">Kiosky mohou také různým uživatelům prezentovat různá prostředí.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="7e6bb-135">[Windows řízení aplikací (WDAC), aby](windows-defender-application-control-wdac.md) se určité aplikace nebo procesy úplně nespouštěl.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="7e6bb-136">Pokud se chcete dozvědět více o různých metodách správy zařízení nebo omezeních zařízení, udělejte další krok a přečtěte si naše Správa zařízení zařízení.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="7e6bb-137">Další krok</span><span class="sxs-lookup"><span data-stu-id="7e6bb-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7e6bb-138">Přečtěte si informace o zprostředkovateli csP a Správa zařízení o funkcích.</span><span class="sxs-lookup"><span data-stu-id="7e6bb-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)