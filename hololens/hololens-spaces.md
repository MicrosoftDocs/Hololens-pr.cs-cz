---
title: Namapujte fyzické mezery pomocí HoloLens
description: HoloLens se dozvíte, co v průběhu času vypadá prostor. uživatelé můžou tento proces usnadnit přesunutím HoloLens určitým způsobem prostřednictvím prostoru.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, návrh, prostorové mapování, HoloLens, rekonstrukce povrchu, síť, sledování hlav, mapování
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640036"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="18a47-105">Namapujte fyzické mezery pomocí HoloLens</span><span class="sxs-lookup"><span data-stu-id="18a47-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="18a47-106">HoloLens blendy s vaším fyzickým světem.</span><span class="sxs-lookup"><span data-stu-id="18a47-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="18a47-107">aby to bylo možné, HoloLens se musí dozvědět o fyzickém světě kolem vás a zapamatovat si, kam umístíte hologramy v daném prostoru.</span><span class="sxs-lookup"><span data-stu-id="18a47-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="18a47-108">v průběhu času HoloLens vytvoří *prostorovou mapu* prostředí, které viděli.</span><span class="sxs-lookup"><span data-stu-id="18a47-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="18a47-109">HoloLens aktualizuje mapu jako změny prostředí.</span><span class="sxs-lookup"><span data-stu-id="18a47-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="18a47-110">pokud jste přihlášeni a zařízení je zapnuté, HoloLens vytvoří a aktualizuje vaše prostorové mapy.</span><span class="sxs-lookup"><span data-stu-id="18a47-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="18a47-111">pokud zařízení s kamerami v prostoru podržíte nebo ho chcete používat, HoloLens se pokusí tuto oblast namapovat.</span><span class="sxs-lookup"><span data-stu-id="18a47-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="18a47-112">i když se HoloLens učí prostor přirozeně v průběhu času, existují způsoby, jak můžete HoloLens lépe namapovat prostor rychleji a efektivně.</span><span class="sxs-lookup"><span data-stu-id="18a47-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="18a47-113">pokud vaše HoloLens nemůže namapovat váš prostor nebo se nejedná o kalibraci, HoloLens může vstoupit do omezeného režimu.</span><span class="sxs-lookup"><span data-stu-id="18a47-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="18a47-114">V omezeném režimu nebudete moci do okolí umístit hologramy.</span><span class="sxs-lookup"><span data-stu-id="18a47-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="18a47-115">tento článek vysvětluje, jak HoloLens mapuje prostory, jak vylepšit prostorové mapování a jak spravovat prostorová data, která HoloLens shromažďuje.</span><span class="sxs-lookup"><span data-stu-id="18a47-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="18a47-116">Výběr a nastavení prostoru</span><span class="sxs-lookup"><span data-stu-id="18a47-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="18a47-117">funkce ve vašem prostředí můžou ztížit HoloLens interpretovat místo.</span><span class="sxs-lookup"><span data-stu-id="18a47-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="18a47-118">světlé úrovně, materiály v prostoru, rozložení objektů a další mohou mít vliv na to, jak HoloLens mapují oblast.</span><span class="sxs-lookup"><span data-stu-id="18a47-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="18a47-119">HoloLens nejlépe funguje v určitých druzích prostředí.</span><span class="sxs-lookup"><span data-stu-id="18a47-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="18a47-120">Chcete-li vytvořit nejlepší prostorovou mapu, vyberte místnost, která má adekvátní světlo a dostatek místa.</span><span class="sxs-lookup"><span data-stu-id="18a47-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="18a47-121">Vyhněte se tmavém prostorům a místnostem, které mají hodně tmavé, lesklé nebo průsvitné povrchy (např. zrcadle nebo gauzy Curtains).</span><span class="sxs-lookup"><span data-stu-id="18a47-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="18a47-122">HoloLens je optimalizovaná pro použití v interiéru.</span><span class="sxs-lookup"><span data-stu-id="18a47-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="18a47-123">Prostorové mapování také funguje nejlépe, když je zapnuto Wi-Fi, i když není nutné ho připojit k síti.</span><span class="sxs-lookup"><span data-stu-id="18a47-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="18a47-124">HoloLens může získat Wi-Fi přístupových bodů i v případě, že není připojený nebo ověřený.</span><span class="sxs-lookup"><span data-stu-id="18a47-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="18a47-125">funkce HoloLens nemění, jestli jsou přístupové body jenom připojené k internetu nebo intranet/místní.</span><span class="sxs-lookup"><span data-stu-id="18a47-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="18a47-126">používejte HoloLens jenom na bezpečných místech bez nebezpečí tripí.</span><span class="sxs-lookup"><span data-stu-id="18a47-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="18a47-127">[Další informace o zabezpečení](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="18a47-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="18a47-128">Mapování prostoru</span><span class="sxs-lookup"><span data-stu-id="18a47-128">Mapping your space</span></span>

<span data-ttu-id="18a47-129">Teď jste připraveni začít s mapováním svého náhradního.</span><span class="sxs-lookup"><span data-stu-id="18a47-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="18a47-130">když HoloLens začne namapovat okolí, uvidíte, že se v prostoru rozprostře obrázek.</span><span class="sxs-lookup"><span data-stu-id="18a47-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="18a47-131">Na domovské stránce hybridní reality můžete aktivovat mapu, která se zobrazí, když vyberete namapovanou plochu.</span><span class="sxs-lookup"><span data-stu-id="18a47-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="18a47-132">Tady jsou pokyny pro vytvoření Skvělé prostorové mapy.</span><span class="sxs-lookup"><span data-stu-id="18a47-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="18a47-133">Pochopení scénářů oblasti</span><span class="sxs-lookup"><span data-stu-id="18a47-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="18a47-134">je důležité strávit to nejvíce času, kdy budete HoloLens používat, aby byla mapa relevantní a kompletní.</span><span class="sxs-lookup"><span data-stu-id="18a47-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="18a47-135">pokud například scénář pro uživatele pro HoloLens zahrnuje přesun z bodu a do bodu B, projde se cesta dvě až třikrát a při přesunu se hledají všechny směry.</span><span class="sxs-lookup"><span data-stu-id="18a47-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="18a47-136">Pomaleji kolem prostoru</span><span class="sxs-lookup"><span data-stu-id="18a47-136">Walk slowly around the space</span></span>

<span data-ttu-id="18a47-137">pokud procházíte příliš rychle kolem oblasti, je pravděpodobný, že HoloLens nepřijde o oblasti mapování.</span><span class="sxs-lookup"><span data-stu-id="18a47-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="18a47-138">Projděte si pomalu kolem prostoru a zastavte se každých 5-8 metrů, abyste se mohli podívat do okolí.</span><span class="sxs-lookup"><span data-stu-id="18a47-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="18a47-139">plynulé pohyby také pomůžou mapu HoloLens efektivněji.</span><span class="sxs-lookup"><span data-stu-id="18a47-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="18a47-140">Prohlédněte si všechny směry</span><span class="sxs-lookup"><span data-stu-id="18a47-140">Look in all directions</span></span>

<span data-ttu-id="18a47-141">při namapování prostoru je HoloLens více dat, kde jsou vzájemně relativní.</span><span class="sxs-lookup"><span data-stu-id="18a47-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="18a47-142">pokud nenajdete například HoloLens nemusí znát, kde je strop v místnosti.</span><span class="sxs-lookup"><span data-stu-id="18a47-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="18a47-143">Nezapomeňte se podívat na podlahu při mapování prostoru.</span><span class="sxs-lookup"><span data-stu-id="18a47-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="18a47-144">Přikrýt klíčové oblasti několikrát</span><span class="sxs-lookup"><span data-stu-id="18a47-144">Cover key areas multiple times</span></span>

<span data-ttu-id="18a47-145">Pohyb přes oblast několikrát pomůže vybrat funkce, které se vám v prvním návodu nemusely vystavit.</span><span class="sxs-lookup"><span data-stu-id="18a47-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="18a47-146">Chcete-li vytvořit ideální mapu, zkuste přesměrovat oblast dvě na třikrát.</span><span class="sxs-lookup"><span data-stu-id="18a47-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="18a47-147">Pokud je to možné, při opakování těchto přesunů tráví čas procházením oblasti v jednom směru a pak se přepíná a vrátí zpět způsob, jakým jste dostali.</span><span class="sxs-lookup"><span data-stu-id="18a47-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="18a47-148">Pořídit čas mapování oblasti</span><span class="sxs-lookup"><span data-stu-id="18a47-148">Take your time mapping the area</span></span>

<span data-ttu-id="18a47-149">může trvat 15 až 20 minut, než se HoloLens plně namapuje a upraví na jeho okolí.</span><span class="sxs-lookup"><span data-stu-id="18a47-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="18a47-150">pokud máte prostor, ve kterém plánujete použít HoloLens často, zajistěte, aby tento čas ještě před tím, než bude možné problémy, nedocházelo k problémům později.</span><span class="sxs-lookup"><span data-stu-id="18a47-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="18a47-151">Možné chyby v prostorové mapě</span><span class="sxs-lookup"><span data-stu-id="18a47-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="18a47-152">Chyby v prostorových mapováních dat spadají do několika kategorií:</span><span class="sxs-lookup"><span data-stu-id="18a47-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="18a47-153">*Díry*: reálné povrchy chybí v datech prostorového mapování.</span><span class="sxs-lookup"><span data-stu-id="18a47-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="18a47-154">*Hallucinations*: povrchy existují v datech prostorového mapování, která neexistují v reálném světě.</span><span class="sxs-lookup"><span data-stu-id="18a47-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="18a47-155">*červi děr*: HoloLens ztratí část prostorové mapy tím, že je v jiné části mapy, než je ve skutečnosti.</span><span class="sxs-lookup"><span data-stu-id="18a47-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="18a47-156">*Bias*: povrchy v datech mapování prostorových dat jsou nedokonalé zarovnané na reálné plochy, ať už jsou, nebo jsou připravené.</span><span class="sxs-lookup"><span data-stu-id="18a47-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="18a47-157">Pokud se zobrazí některá z těchto chyb, pošlete nám svůj názor pomocí [FeedbackHub](hololens-feedback.md) .</span><span class="sxs-lookup"><span data-stu-id="18a47-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="18a47-158">Zabezpečení a úložiště pro prostorová data</span><span class="sxs-lookup"><span data-stu-id="18a47-158">Security and storage for spatial data</span></span>

<span data-ttu-id="18a47-159">Windows 10 aktualizace verze 1803 pro Microsoft HoloLens a novější ukládá data mapování v místní databázi (v zařízení).</span><span class="sxs-lookup"><span data-stu-id="18a47-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="18a47-160">HoloLens uživatelé nemají přímý přístup k databázi map, i když je zařízení zapojené do počítače nebo při použití aplikace průzkumník souborů.</span><span class="sxs-lookup"><span data-stu-id="18a47-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="18a47-161">když je na HoloLens povolený BitLocker, uložená data mapy se taky šifrují spolu s celým svazkem.</span><span class="sxs-lookup"><span data-stu-id="18a47-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="18a47-162">Odebrat data mapy a známé mezery z HoloLens</span><span class="sxs-lookup"><span data-stu-id="18a47-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="18a47-163">existují dvě možnosti odstranění dat mapy v **Nastavení > systému > Hologramy**:</span><span class="sxs-lookup"><span data-stu-id="18a47-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="18a47-164">Pokud chcete odstranit okolní hologramy, vyberte **Odebrat okolní hologramy**.</span><span class="sxs-lookup"><span data-stu-id="18a47-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="18a47-165">Tento příkaz vymaže data mapy a ukotvené hologramy pro aktuální prostor.</span><span class="sxs-lookup"><span data-stu-id="18a47-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="18a47-166">Pokud zařízení budete nadále používat ve stejném prostoru, vytvoří a uloží značku nové mapy, která nahradí odstraněné informace.</span><span class="sxs-lookup"><span data-stu-id="18a47-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="18a47-167">"Okolní" hologramy jsou hologramy, které jsou ukotveny v rámci stejné části mapy v aktuálním prostoru.</span><span class="sxs-lookup"><span data-stu-id="18a47-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="18a47-168">Tuto možnost můžete například použít k vymazání dat mapy, která se vztahují k práci bez vlivu na data map v domácnosti.</span><span class="sxs-lookup"><span data-stu-id="18a47-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="18a47-169">Pokud chcete odstranit všechny hologramy, vyberte **Odebrat všechny hologramy**.</span><span class="sxs-lookup"><span data-stu-id="18a47-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="18a47-170">Tento příkaz vymaže všechna data mapy, která jsou uložená v zařízení, i všechny ukotvené hologramy.</span><span class="sxs-lookup"><span data-stu-id="18a47-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="18a47-171">Budete muset explicitně umístit všechny hologramy.</span><span class="sxs-lookup"><span data-stu-id="18a47-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="18a47-172">Nebudete moct znovu zjistit dříve umístěné hologramy.</span><span class="sxs-lookup"><span data-stu-id="18a47-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="18a47-173">po odebrání okolních nebo všech hologramů HoloLens hned spustit skenování a mapování aktuálního místa.</span><span class="sxs-lookup"><span data-stu-id="18a47-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="18a47-174">Data Wi-Fi v prostorových mapách</span><span class="sxs-lookup"><span data-stu-id="18a47-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="18a47-175">HoloLens ukládá Wi-Fi charakteristiky, které vám pomůžou korelovat umístění a mapy na hologramech, které jsou uložené v databázi HoloLens se známými prostory.</span><span class="sxs-lookup"><span data-stu-id="18a47-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="18a47-176">Informace o vlastnostech Wi-Fi nejsou dostupné pro uživatele a neodesílají se do Microsoftu pomocí cloudu nebo pomocí telemetrie.</span><span class="sxs-lookup"><span data-stu-id="18a47-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="18a47-177">pokud je povolená Wi-Fi, HoloLens koreluje data map s okolními Wi-Fi přístupovými body.</span><span class="sxs-lookup"><span data-stu-id="18a47-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="18a47-178">Neexistují žádné rozdíly v chování, ať už je síť připojená nebo jenom zjištěná v blízkosti.</span><span class="sxs-lookup"><span data-stu-id="18a47-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="18a47-179">pokud je Wi-Fi zakázané, HoloLens pořád vyhledává místo.</span><span class="sxs-lookup"><span data-stu-id="18a47-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="18a47-180">HoloLens ale musí vyhledat více dat mapy v rámci databáze prostorů a může pro hledání hologramů potřebovat více času.</span><span class="sxs-lookup"><span data-stu-id="18a47-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="18a47-181">bez Wi-Fi informací musí HoloLens porovnat aktivní kontroly se všemi hologramy na hologramech a mapovat oddíly, které jsou uložené na zařízení, aby bylo možné najít správnou část mapy.</span><span class="sxs-lookup"><span data-stu-id="18a47-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18a47-182">Související témata</span><span class="sxs-lookup"><span data-stu-id="18a47-182">Related topics</span></span>

- [<span data-ttu-id="18a47-183">Návrh prostorového mapování</span><span class="sxs-lookup"><span data-stu-id="18a47-183">Spatial mapping design</span></span>](/windows/mixed-reality/spatial-mapping)
