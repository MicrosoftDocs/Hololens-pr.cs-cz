---
title: HoloLens 2 Battery and Charging
description: Jak naúčtovat zařízení HoloLens a jak používat externí balíčky baterie
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923580"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="cd395-103">HoloLens 2 Battery and Charging</span><span class="sxs-lookup"><span data-stu-id="cd395-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="cd395-104">Tato stránka nabízí podrobnosti o účtování HoloLens 2 a používání externích sad baterie.</span><span class="sxs-lookup"><span data-stu-id="cd395-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="cd395-105">Účtování zařízení</span><span class="sxs-lookup"><span data-stu-id="cd395-105">Charging the device</span></span>

<span data-ttu-id="cd395-106">Použijte kabel USB typu [C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat.</span><span class="sxs-lookup"><span data-stu-id="cd395-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="cd395-107">Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W).</span><span class="sxs-lookup"><span data-stu-id="cd395-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="cd395-108">Zařízení HoloLens 2 mohou společně se dodanou zdi naplno nabít za méně než 65 minut, když je zařízení v pohotovostním režimu.</span><span class="sxs-lookup"><span data-stu-id="cd395-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="cd395-109">Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W energie.</span><span class="sxs-lookup"><span data-stu-id="cd395-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="cd395-110">Pokud je to možné, nepoužívejte počítač k nabílení zařízení přes USB, což je pomalé.</span><span class="sxs-lookup"><span data-stu-id="cd395-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="cd395-111">Kontrola úrovně baterie</span><span class="sxs-lookup"><span data-stu-id="cd395-111">Checking the battery charge level</span></span>
<span data-ttu-id="cd395-112">Pokud je zařízení správně spuštěné a spuštěné, existují tři způsoby, jak zkontrolovat úroveň baterie:</span><span class="sxs-lookup"><span data-stu-id="cd395-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="cd395-113">V hlavní nabídce uživatelského rozhraní zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cd395-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="cd395-114">Led diodu si prohlédněte blízko tlačítka napájení (při 40procentní poplatek byste měli vidět alespoň dvě plné LED diody).</span><span class="sxs-lookup"><span data-stu-id="cd395-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="cd395-115">Když se zařízení nabíjí, indikátor baterie se rozsvítí, aby indikuje aktuální úroveň poplatku.</span><span class="sxs-lookup"><span data-stu-id="cd395-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="cd395-116">Poslední světlo postupně zeslábne a bude indikovat aktivní zpoplatnění.</span><span class="sxs-lookup"><span data-stu-id="cd395-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="cd395-117">Když je holoLens v systému, indikátor baterie zobrazí stav baterie v pěti přírůstcích.</span><span class="sxs-lookup"><span data-stu-id="cd395-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="cd395-118">Když je jen jedna z pěti světel rozsvícená, je úroveň baterie nižší než 20 procent.</span><span class="sxs-lookup"><span data-stu-id="cd395-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="cd395-119">Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, jedno světlo krátce blikne a pak vypadne.</span><span class="sxs-lookup"><span data-stu-id="cd395-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="cd395-120">Na hostitelském počítači otevřete **Průzkumník souborů** vyhledejte zařízení HoloLens 2 na levé straně pod **položkou Tento počítač.**</span><span class="sxs-lookup"><span data-stu-id="cd395-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="cd395-121">Klikněte pravým tlačítkem na zařízení a vyberte **Vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="cd395-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="cd395-122">V dialogovém okně se zobrazí úroveň baterie.</span><span class="sxs-lookup"><span data-stu-id="cd395-122">A dialog box will show the battery charge level.</span></span>

   ![Obrazovka vlastností HoloLens 2 zobrazuje úroveň změny baterie](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="cd395-124">Alternativní specifikace poplatků</span><span class="sxs-lookup"><span data-stu-id="cd395-124">Alternative charging specifications</span></span>

<span data-ttu-id="cd395-125">HoloLens 2 se může účtovat pomocí [zdrojů NAPÁJENÍ USB](https://www.usb.org/usb-charger-pd) do 27 wattů.</span><span class="sxs-lookup"><span data-stu-id="cd395-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="cd395-126">Pokud zdroj dokáže dodat alespoň 10 wattů, může být doba provozu HoloLens delší (u některých úloh potenciálně po neomezenou dobu).</span><span class="sxs-lookup"><span data-stu-id="cd395-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="cd395-127">Použitím usb-A-C usb-c se poplatek omezí na 7,5 W.</span><span class="sxs-lookup"><span data-stu-id="cd395-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="cd395-128">Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.</span><span class="sxs-lookup"><span data-stu-id="cd395-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="cd395-129">Když je HoloLens v pohotovostním režimu, stačí 18 wattů k dosažení maximální frekvence nabíjet interní baterie.</span><span class="sxs-lookup"><span data-stu-id="cd395-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="cd395-130">Když se HoloLens používá, může být sazba za poplatek snížená, protože HoloLens upřednostňuje provoz před účtováním.</span><span class="sxs-lookup"><span data-stu-id="cd395-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd395-131">Doporučuje se, aby se HoloLens 2 účtuje minimálně při 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="cd395-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="cd395-132">Neměly by se používat sítě, které dodávají alespoň 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="cd395-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="cd395-133">Externí sady baterie</span><span class="sxs-lookup"><span data-stu-id="cd395-133">External Battery Packs</span></span>

<span data-ttu-id="cd395-134">Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="cd395-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="cd395-135">Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="cd395-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="cd395-136">Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že místo poplatků z ní účtují HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cd395-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="cd395-137">Správa heat služby</span><span class="sxs-lookup"><span data-stu-id="cd395-137">Managing Heat</span></span>

<span data-ttu-id="cd395-138">Stejně jako u jakéhokoli zařízení i při účtování HoloLens generuje teplo.</span><span class="sxs-lookup"><span data-stu-id="cd395-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="cd395-139">Čím je poplatek rychlejší, tím více se generuje teplo.</span><span class="sxs-lookup"><span data-stu-id="cd395-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="cd395-140">Při spuštění poplatek na nižší úrovni baterie se navíc vygeneruje větší teplo než při spuštění, když je baterie převážně plná.</span><span class="sxs-lookup"><span data-stu-id="cd395-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="cd395-141">Zákazníci, kteří potřebují provozovat HoloLens po delší dobu v horkých prostředích, mohou používat následující techniky:</span><span class="sxs-lookup"><span data-stu-id="cd395-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="cd395-142">HoloLens 2 můžete připojit k externímu zdroji napájení i v případě, že je interní baterie plně nabitá.</span><span class="sxs-lookup"><span data-stu-id="cd395-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="cd395-143">Při vyčerpání externí baterie bude HoloLens pokračovat v práci s interním bateriem.</span><span class="sxs-lookup"><span data-stu-id="cd395-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="cd395-144">Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A.</span><span class="sxs-lookup"><span data-stu-id="cd395-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="cd395-145">Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.</span><span class="sxs-lookup"><span data-stu-id="cd395-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cd395-146">Řešení potíží</span><span class="sxs-lookup"><span data-stu-id="cd395-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="cd395-147">HoloLens účtuje externí baterie</span><span class="sxs-lookup"><span data-stu-id="cd395-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="cd395-148">Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí ji, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="cd395-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="cd395-149">Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C.</span><span class="sxs-lookup"><span data-stu-id="cd395-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="cd395-150">Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.</span><span class="sxs-lookup"><span data-stu-id="cd395-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
