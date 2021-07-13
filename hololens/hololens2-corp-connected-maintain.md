---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – údržba
description: přečtěte si, jak spravovat zařízení HoloLens 2 přes podnikovou propojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, správa, připojení k podnikové síti, příručky k Dynamics 365, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636992"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="496b4-104">Údržba – Příručka propojená s podnikem</span><span class="sxs-lookup"><span data-stu-id="496b4-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="496b4-105">Aktualizovat HoloLens</span><span class="sxs-lookup"><span data-stu-id="496b4-105">Update HoloLens</span></span>

<span data-ttu-id="496b4-106">společnost Microsoft navrhla web Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na web Windows Update, jako je například možnost nasazení aktualizací do skupin zařízení a definování oken údržby pro instalaci aktualizací.</span><span class="sxs-lookup"><span data-stu-id="496b4-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="496b4-107">Jednou z oblíbených metod správy aktualizací je odložení funkce po dobu 30 dnů.</span><span class="sxs-lookup"><span data-stu-id="496b4-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="496b4-108">To správcům umožňuje aktualizovat a zobrazovat náhled nových funkcí a získat tak první znalosti a informovat vaši technickou podporu o jakýchkoli nových změnách.</span><span class="sxs-lookup"><span data-stu-id="496b4-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="496b4-109">naučte se [spravovat HoloLens aktualizace](/hololens/hololens-updates), včetně plánovaných dnů, naplánovaných časů a nastavení aktivních hodin v zařízení, takže se aktualizuje mimo pracovní dobu.</span><span class="sxs-lookup"><span data-stu-id="496b4-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="496b4-110">Aktualizace průvodců Dynamics 365 (a dalších aplikací ze Storu)</span><span class="sxs-lookup"><span data-stu-id="496b4-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="496b4-111">příručky k Dynamics 365 jsou aplikace In-Box a dají se aktualizovat prostřednictvím Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="496b4-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="496b4-112">pro všechny aplikace, které jsou stažené prostřednictvím Microsoft Store, je možné je ručně [aktualizovat přímo pomocí aplikace Microsoft Store](/hololens/holographic-store-apps#update-apps) .</span><span class="sxs-lookup"><span data-stu-id="496b4-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="496b4-113">Jak aktualizovat obchodní aplikace</span><span class="sxs-lookup"><span data-stu-id="496b4-113">How to update LOB apps</span></span>

<span data-ttu-id="496b4-114">Obchodní aplikace je možné aktualizovat stejným způsobem jako přidaným do Intune.</span><span class="sxs-lookup"><span data-stu-id="496b4-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="496b4-115">Aplikace se dají v Intune aktualizovat tak, že se do existující konfigurace aplikace nahraje nová aplikace s vyšším číslem verze.</span><span class="sxs-lookup"><span data-stu-id="496b4-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="496b4-116">Když se zařízení synchronizuje s Intune, bude to mít za to, že existuje novější verze aplikace a stáhne se novější aplikace a nahradí starou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="496b4-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="496b4-117">Pokud chcete nahrát novější aplikaci, přejděte do části aplikace pro aplikaci [mem Portal](https://endpoint.microsoft.com/#home)  ->   – > všech   ->  *TheNameOfYourApp*  ->  **Vlastnosti aplikace.**</span><span class="sxs-lookup"><span data-stu-id="496b4-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="496b4-118">Vedle pole informace o aplikaci vyberte **Upravit.**</span><span class="sxs-lookup"><span data-stu-id="496b4-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="496b4-119">Pro hodnotu &quot; Vybrat soubor, který se má aktualizovat &quot; , vyberte soubor.</span><span class="sxs-lookup"><span data-stu-id="496b4-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="496b4-120">Odsud pomocí místní nabídky otevřete Průzkumníka souborů a nahrajte novější verzi obchodní aplikace.</span><span class="sxs-lookup"><span data-stu-id="496b4-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="496b4-121">Zajistěte, aby v případě potřeby zahrnovaly závislosti.</span><span class="sxs-lookup"><span data-stu-id="496b4-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="496b4-122">Další informace: [nasazení aplikace Intune pro HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="496b4-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="496b4-123">Plán vývoje</span><span class="sxs-lookup"><span data-stu-id="496b4-123">Development Plan</span></span>

<span data-ttu-id="496b4-124">Vaše zařízení se úspěšně zaregistrovalo, teď jste připraveni nasadit do svých zařízení další obchodní aplikace.</span><span class="sxs-lookup"><span data-stu-id="496b4-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="496b4-125">Po dobu trvání tohoto průvodce používáme ukázkovou aplikaci, ale je pravděpodobnější, že budete chtít používat vlastní aplikace vytvořené pro potřeby vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="496b4-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="496b4-126">Pokud už máte obchodní aplikaci, budete připraveni ji [nasadit prostřednictvím MDM](/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="496b4-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="496b4-127">pokud dáváte přednost jiné metodě, přečtěte si téma [přehled nasazení aplikace HoloLens 2](/hololens/app-deploy-overview) a získejte další informace o nasazení vaší obchodní aplikace do svých zařízení.</span><span class="sxs-lookup"><span data-stu-id="496b4-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="496b4-128">Pokud jste ještě vytvořili svoji vlastní obchodní aplikaci nebo stále probíhá vytváření, Projděte si naše dokumenty pro vývoj hybridních realit, kde můžete [začít navrhovat a vytvářet prototypy](/windows/mixed-reality/design/design) nebo se naučit základní koncepty, které [vám pomůžou začít se smíšeným vývojem realit.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="496b4-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="496b4-129">Plán podpory</span><span class="sxs-lookup"><span data-stu-id="496b4-129">Support Plan</span></span>

<span data-ttu-id="496b4-130">Plán podpory je vynikajícím krokem.</span><span class="sxs-lookup"><span data-stu-id="496b4-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="496b4-131">při řešení potíží s procesem registrace na zařízeních HoloLens a také při obecném použití HoloLensho zařízení v rámci vaší organizace je užitečná podpora uživatele nebo skupiny.</span><span class="sxs-lookup"><span data-stu-id="496b4-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="496b4-132">Abychom uživatelům umožnili rychlejší řešení jejich problémů, doporučujeme, aby proces eskalace byl zpracován podobným způsobem jako v tomto pořadí:</span><span class="sxs-lookup"><span data-stu-id="496b4-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="496b4-133">Vaše oddělení podpory.</span><span class="sxs-lookup"><span data-stu-id="496b4-133">Your Support desk.</span></span>
2. <span data-ttu-id="496b4-134">váš tým odborníka na HoloLens</span><span class="sxs-lookup"><span data-stu-id="496b4-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="496b4-135">[HoloLens Docs](/hololens/)  /  [HoloLens řešení potíží s dokumenty](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="496b4-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="496b4-136">Kontaktujte podporu</span><span class="sxs-lookup"><span data-stu-id="496b4-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="496b4-137">Správa zařízení</span><span class="sxs-lookup"><span data-stu-id="496b4-137">Device Management</span></span>

<span data-ttu-id="496b4-138">Tento průvodce mluvili o nastavení správy mobilních zařízení (MDM) a používá ho k nastavení některých konfigurací zařízení a nastavení, která umožňují přístup z pohledu Wi-Fi certifikátů a proxy serveru.</span><span class="sxs-lookup"><span data-stu-id="496b4-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="496b4-139">MDM se ale taky dá použít k použití omezení zařízení prostřednictvím CSP a zásad.</span><span class="sxs-lookup"><span data-stu-id="496b4-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="496b4-140">v mnoha případech můžou mít zařízení omezení připojení, například Bluetooth, VPN, USB nebo vypnutí přístupu ke kameře nebo mikrofonu.</span><span class="sxs-lookup"><span data-stu-id="496b4-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="496b4-141">Pokud vás nějaký z těchto zájmů zajímá, doporučujeme, abyste si přečetli [Nejčastější stránku omezení pro zařízení](/hololens/hololens-common-device-restrictions).</span><span class="sxs-lookup"><span data-stu-id="496b4-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="496b4-142">Existují další složitější omezení zařízení, která můžete použít.</span><span class="sxs-lookup"><span data-stu-id="496b4-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="496b4-143">Například:</span><span class="sxs-lookup"><span data-stu-id="496b4-143">Such as:</span></span>

- <span data-ttu-id="496b4-144">omezení stránek, které se dají zobrazit v aplikaci Nastavení, pomocí [SettingsPageVisibility](/hololens/settings-uri-list), takže uživatelé budou mít přístup jenom k nastavením, které je potřeba upravit, jako je třeba změna připojení Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="496b4-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="496b4-145">Používejte [celoobrazovkový režim](/hololens/hololens-kiosk) k omezení uživatelského rozhraní prezentovaného uživatelům na zařízení.</span><span class="sxs-lookup"><span data-stu-id="496b4-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="496b4-146">Veřejné terminály můžete nastavit tak, aby zobrazovaly jednu aplikaci nebo více aplikací s vlastní úvodní stránkou.</span><span class="sxs-lookup"><span data-stu-id="496b4-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="496b4-147">Veřejné terminály můžou také prezentovat různá prostředí různým uživatelům.</span><span class="sxs-lookup"><span data-stu-id="496b4-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="496b4-148">[Windows řízení aplikací (WDAC)](/hololens/windows-defender-application-control-wdac) , aby se zajistilo, že konkrétní aplikace nebo procesy budou zcela spouštěny.</span><span class="sxs-lookup"><span data-stu-id="496b4-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="496b4-149">Pokud se chcete dozvědět více o dalších metodách správy zařízení nebo omezení zařízení, proveďte další krok a přečtěte si [Přehled správy zařízení](/hololens/hololens-csp-policy-overview).</span><span class="sxs-lookup"><span data-stu-id="496b4-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





