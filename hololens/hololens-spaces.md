---
title: Mapování fyzických prostorů pomocí HoloLens
description: HoloLens zjistí, jak prostor v průběhu času vypadá. Uživatelé mohou tento proces usnadnit přesunutím HoloLens určitým způsobem přes prostor.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, spatial mapping, HoloLens, surface reconstruction, mesh, head tracking, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379259"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="aaa32-105">Mapování fyzických prostorů pomocí HoloLens</span><span class="sxs-lookup"><span data-stu-id="aaa32-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="aaa32-106">HoloLens spojuje hologramy s fyzickým světem.</span><span class="sxs-lookup"><span data-stu-id="aaa32-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="aaa32-107">K tomu musí HoloLens získat informace o fyzickém světě kolem vás a pamatovat si, kam do tohoto prostoru umístit hologramy.</span><span class="sxs-lookup"><span data-stu-id="aaa32-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="aaa32-108">V průběhu času holoLens vytvoří prostorovou *mapu* prostředí, které viděl.</span><span class="sxs-lookup"><span data-stu-id="aaa32-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="aaa32-109">HoloLens aktualizuje mapu při změně prostředí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="aaa32-110">Dokud jste přihlášeni a zařízení je zapnuté, HoloLens vytvoří a aktualizuje prostorové mapy.</span><span class="sxs-lookup"><span data-stu-id="aaa32-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="aaa32-111">Pokud zařízení držíte nebo opotřebováte fotoaparáty, které jsou v prostoru, holoLens se pokusí oblast mapovat.</span><span class="sxs-lookup"><span data-stu-id="aaa32-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="aaa32-112">I když se HoloLens naučí prostor přirozeně v průběhu času, existují způsoby, jak můžete holoLens pomoct mapovat prostor rychleji a efektivněji.</span><span class="sxs-lookup"><span data-stu-id="aaa32-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="aaa32-113">Pokud holoLens nemůže mapovat prostor nebo je mimo prostor, může HoloLens vstoupit do omezeného režimu.</span><span class="sxs-lookup"><span data-stu-id="aaa32-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="aaa32-114">V omezeném režimu nebudete moct hologramy umístit do svého okolí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="aaa32-115">Tento článek vysvětluje, jak HoloLens mapuje prostory, jak vylepšit prostorové mapování a jak spravovat prostorová data, která HoloLens shromažďuje.</span><span class="sxs-lookup"><span data-stu-id="aaa32-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="aaa32-116">Volba a nastavení a prostor</span><span class="sxs-lookup"><span data-stu-id="aaa32-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="aaa32-117">Funkce ve vašem prostředí mohou ztížovat interpretaci prostoru pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="aaa32-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="aaa32-118">Úrovně světla, materiály v prostoru, rozložení objektů a další mohou ovlivnit, jak HoloLens mapuje oblast.</span><span class="sxs-lookup"><span data-stu-id="aaa32-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="aaa32-119">HoloLens funguje nejlépe v určitých typech prostředí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="aaa32-120">Pokud chcete vytvořit nejlepší prostorovou mapu, zvolte místnost, která má dostatečné světlo a dostatek místa.</span><span class="sxs-lookup"><span data-stu-id="aaa32-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="aaa32-121">Vyhněte se tmavým prostorům a místnostem, které mají spoustu tmavých, šišitých nebo průsvitných povrchů (například zrcadla nebo vousy).</span><span class="sxs-lookup"><span data-stu-id="aaa32-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="aaa32-122">HoloLens je optimalizovaný pro použití v interiérech.</span><span class="sxs-lookup"><span data-stu-id="aaa32-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="aaa32-123">Prostorové mapování také funguje nejlépe Wi-Fi je zapnuté, i když nemusí být připojené k síti.</span><span class="sxs-lookup"><span data-stu-id="aaa32-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="aaa32-124">HoloLens může získat Wi-Fi přístupové body, i když není připojený nebo ověřený.</span><span class="sxs-lookup"><span data-stu-id="aaa32-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="aaa32-125">Funkce HoloLens nemění, jestli jsou přístupové body připojené k internetu, nebo jenom k intranetu nebo místnímu prostředí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="aaa32-126">HoloLens používejte jenom na bezpečných místech bez rizika při vyjetí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="aaa32-127">[Další informace o bezpečnosti](https://support.microsoft.com/help/4023454/safety-information)</span><span class="sxs-lookup"><span data-stu-id="aaa32-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="aaa32-128">Mapování prostoru</span><span class="sxs-lookup"><span data-stu-id="aaa32-128">Mapping your space</span></span>

<span data-ttu-id="aaa32-129">Teď jste připraveni začít mapovat náhradní.</span><span class="sxs-lookup"><span data-stu-id="aaa32-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="aaa32-130">Když HoloLens začne mapovat vaše okolí, uvidíte grafické rozložení sítě po prostoru.</span><span class="sxs-lookup"><span data-stu-id="aaa32-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="aaa32-131">V domovském prostředí hybridní reality můžete aktivovat zobrazení mapy výběrem na mapované ploše.</span><span class="sxs-lookup"><span data-stu-id="aaa32-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="aaa32-132">Tady jsou pokyny pro vytvoření skvělé prostorové mapy.</span><span class="sxs-lookup"><span data-stu-id="aaa32-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="aaa32-133">Pochopení scénářů pro oblast</span><span class="sxs-lookup"><span data-stu-id="aaa32-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="aaa32-134">Je důležité strávený co nejvíce času používáním HoloLens, aby mapa byla relevantní a kompletní.</span><span class="sxs-lookup"><span data-stu-id="aaa32-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="aaa32-135">Pokud například uživatelský scénář pro HoloLens zahrnuje přechod z bodu A na bod B, projděte si cestu dvakrát až třikrát a při pohybu se díváte ve všech směrech.</span><span class="sxs-lookup"><span data-stu-id="aaa32-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="aaa32-136">Pomalu procházte prostor</span><span class="sxs-lookup"><span data-stu-id="aaa32-136">Walk slowly around the space</span></span>

<span data-ttu-id="aaa32-137">Pokud se po této oblasti budete projít příliš rychle, je pravděpodobné, že HoloLens nebude mít k dispozici mapové oblasti.</span><span class="sxs-lookup"><span data-stu-id="aaa32-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="aaa32-138">Pomalu si projděte prostor a každých 5 až 8 stop se zastavujte, abyste se podívali na okolí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="aaa32-139">Hladké pohyby také pomáhají mapu HoloLens efektivněji.</span><span class="sxs-lookup"><span data-stu-id="aaa32-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="aaa32-140">Hledejte ve všech směrech.</span><span class="sxs-lookup"><span data-stu-id="aaa32-140">Look in all directions</span></span>

<span data-ttu-id="aaa32-141">Při pohledu na mapu prostoru dává HoloLens více dat o tom, kde jsou body vzájemně relativní.</span><span class="sxs-lookup"><span data-stu-id="aaa32-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="aaa32-142">Pokud například nevyhledáte holoLens, nemusí vědět, kde je strop v místnosti.</span><span class="sxs-lookup"><span data-stu-id="aaa32-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="aaa32-143">Při mapování prostoru se nezapomeňte podívat dolů na podlaží.</span><span class="sxs-lookup"><span data-stu-id="aaa32-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="aaa32-144">Vícenásobné pokrytí klíčových oblastí</span><span class="sxs-lookup"><span data-stu-id="aaa32-144">Cover key areas multiple times</span></span>

<span data-ttu-id="aaa32-145">Vícenásobný přesun oblasti vám pomůže vybrat funkce, které jste v prvním názorném postupu vynechali.</span><span class="sxs-lookup"><span data-stu-id="aaa32-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="aaa32-146">Pokud chcete vytvořit ideální mapu, zkuste dvakrát až třikrát pro procházení oblasti.</span><span class="sxs-lookup"><span data-stu-id="aaa32-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="aaa32-147">Pokud je to možné, při opakování těchto pohybů věnujte čas tomu, abyste procházeli oblastí v jednom směru, pak se otočíte a vrátíte se zpět.</span><span class="sxs-lookup"><span data-stu-id="aaa32-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="aaa32-148">Udělejte si čas namapování oblasti</span><span class="sxs-lookup"><span data-stu-id="aaa32-148">Take your time mapping the area</span></span>

<span data-ttu-id="aaa32-149">Může trvat 15 až 20 minut, než se HoloLens plně namapuje a přizpůsobí svému okolí.</span><span class="sxs-lookup"><span data-stu-id="aaa32-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="aaa32-150">Pokud máte prostor, ve kterém plánujete holoLens často používat, může pozdějšímu namapování prostoru zabraňovat problémům.</span><span class="sxs-lookup"><span data-stu-id="aaa32-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="aaa32-151">Možné chyby v prostorové mapě</span><span class="sxs-lookup"><span data-stu-id="aaa32-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="aaa32-152">Chyby v datech prostorového mapování spadají do několika kategorií:</span><span class="sxs-lookup"><span data-stu-id="aaa32-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="aaa32-153">*Otvory:* V datech prostorového mapování chybí povrchy z reálného světa.</span><span class="sxs-lookup"><span data-stu-id="aaa32-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="aaa32-154">*Halukuna:* Povrchy existují v datech prostorového mapování, která neexistují ve skutečném světě.</span><span class="sxs-lookup"><span data-stu-id="aaa32-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="aaa32-155">*Wormholes*: HoloLens "ztratí" část prostorové mapy tím, že si myslí, že je v jiné části mapy než ve skutečnosti.</span><span class="sxs-lookup"><span data-stu-id="aaa32-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="aaa32-156">*Předsudky:* Povrchy v datech prostorového mapování jsou nedokonalě zarovnané s reálnými povrchy, buď nasazované, nebo vytahované.</span><span class="sxs-lookup"><span data-stu-id="aaa32-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="aaa32-157">Pokud se zobrazí jakákoli z těchto chyb, pošlete nám svůj názor na [FeedbackHub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="aaa32-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="aaa32-158">Zabezpečení a úložiště prostorových dat</span><span class="sxs-lookup"><span data-stu-id="aaa32-158">Security and storage for spatial data</span></span>

<span data-ttu-id="aaa32-159">Windows 10 verze 1803 pro Microsoft HoloLens a novější ukládá data mapování v místní databázi (na zařízení).</span><span class="sxs-lookup"><span data-stu-id="aaa32-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="aaa32-160">Uživatelé HoloLens nemohou získat přímý přístup k databázi mapy, a to ani v případě, že je zařízení připojené k počítači nebo Průzkumník souborů aplikaci.</span><span class="sxs-lookup"><span data-stu-id="aaa32-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="aaa32-161">Když je na HoloLens povolený BitLocker, zašifrují se také uložená data mapy společně s celým svazkem.</span><span class="sxs-lookup"><span data-stu-id="aaa32-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="aaa32-162">Odebrání dat mapy a známých prostorů z HoloLens</span><span class="sxs-lookup"><span data-stu-id="aaa32-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="aaa32-163">Existují dvě možnosti odstranění dat mapy v **Nastavení > System > Hologramy:**</span><span class="sxs-lookup"><span data-stu-id="aaa32-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="aaa32-164">Pokud chcete odstranit hologramy v okolí, vyberte **Odebrat hologramy v okolí.**</span><span class="sxs-lookup"><span data-stu-id="aaa32-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="aaa32-165">Tento příkaz vymaže data mapy a ukotvené hologramy pro aktuální prostor.</span><span class="sxs-lookup"><span data-stu-id="aaa32-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="aaa32-166">Pokud budete zařízení dál používat ve stejném prostoru, vytvoří a uloží zcela novou sekci mapy, která nahradí odstraněné informace.</span><span class="sxs-lookup"><span data-stu-id="aaa32-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="aaa32-167">Hologramy "blízkých" jsou hologramy ukotvené v rámci stejného oddílu mapy v aktuálním prostoru.</span><span class="sxs-lookup"><span data-stu-id="aaa32-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="aaa32-168">Tuto možnost můžete například použít k vymazání dat map souvisejících s prací, aniž by to ovlivnilo jakákoli data mapy související s domovskou stránku.</span><span class="sxs-lookup"><span data-stu-id="aaa32-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="aaa32-169">Pokud chcete odstranit všechny hologramy, vyberte **Odebrat všechny hologramy.**</span><span class="sxs-lookup"><span data-stu-id="aaa32-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="aaa32-170">Tento příkaz vymaže všechna mapová data uložená v zařízení i všechny ukotvené hologramy.</span><span class="sxs-lookup"><span data-stu-id="aaa32-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="aaa32-171">Všechny hologramy budete muset explicitně umístit.</span><span class="sxs-lookup"><span data-stu-id="aaa32-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="aaa32-172">Dříve umístěné hologramy nebudete moct znovu najít.</span><span class="sxs-lookup"><span data-stu-id="aaa32-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="aaa32-173">Po odebrání blízkých nebo všech hologramů začne HoloLens okamžitě skenovat a mapovat aktuální prostor.</span><span class="sxs-lookup"><span data-stu-id="aaa32-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="aaa32-174">Wi-Fi dat v prostorových mapách</span><span class="sxs-lookup"><span data-stu-id="aaa32-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="aaa32-175">HoloLens ukládá Wi-Fi, které pomáhají korelovat umístění hologramů a oddíly map, které jsou uložené v databázi HoloLens známých prostorů.</span><span class="sxs-lookup"><span data-stu-id="aaa32-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="aaa32-176">Informace o Wi-Fi charakteristiky nejsou uživatelům přístupné a neposílané Microsoftu pomocí cloudu nebo telemetrie.</span><span class="sxs-lookup"><span data-stu-id="aaa32-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="aaa32-177">Pokud je Wi-Fi povoleno, HoloLens koreluje data map s blízkými Wi-Fi přístupových bodů.</span><span class="sxs-lookup"><span data-stu-id="aaa32-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="aaa32-178">Bez ohledu na to, jestli je síť připojená nebo detekována blízko, není v chování žádný rozdíl.</span><span class="sxs-lookup"><span data-stu-id="aaa32-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="aaa32-179">Pokud Wi-Fi zakázaná, HoloLens stále prohledá prostor.</span><span class="sxs-lookup"><span data-stu-id="aaa32-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="aaa32-180">HoloLens ale musí prohledávat více dat mapy v rámci databáze prostorů a může potřebovat více času na nalezení hologramů.</span><span class="sxs-lookup"><span data-stu-id="aaa32-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="aaa32-181">Bez Wi-Fi musí HoloLens porovnat aktivní kontroly se všemi kotvami hologramů a oddíly mapy, které jsou uložené v zařízení, aby bylo možné najít správnou část mapy.</span><span class="sxs-lookup"><span data-stu-id="aaa32-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aaa32-182">Související témata</span><span class="sxs-lookup"><span data-stu-id="aaa32-182">Related topics</span></span>

- [<span data-ttu-id="aaa32-183">Návrh prostorového mapování</span><span class="sxs-lookup"><span data-stu-id="aaa32-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
