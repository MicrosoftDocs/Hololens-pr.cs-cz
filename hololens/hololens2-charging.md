---
title: Baterie a dobíjení
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379336"
---
# <a name="battery-and-charging"></a><span data-ttu-id="0cdbe-103">Baterie a dobíjení</span><span class="sxs-lookup"><span data-stu-id="0cdbe-103">Battery and Charging</span></span>

<span data-ttu-id="0cdbe-104">Tato stránka nabízí podrobnosti o účtování HoloLens 2 a používání externích sad baterie.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="0cdbe-105">Included Neschádka</span><span class="sxs-lookup"><span data-stu-id="0cdbe-105">Included Charger</span></span>

<span data-ttu-id="0cdbe-106">Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W).</span><span class="sxs-lookup"><span data-stu-id="0cdbe-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="0cdbe-107">Pokud je to možné, důrazně doporučujeme účtovat pomocí zahrnutých poplatků.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="0cdbe-108">Specifikace</span><span class="sxs-lookup"><span data-stu-id="0cdbe-108">Specifications</span></span>

<span data-ttu-id="0cdbe-109">HoloLens 2 se může naúčtovat pomocí [zdrojů NAPÁJENÍ USB](https://www.usb.org/usb-charger-pd) o výkonu až 27 wattů.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="0cdbe-110">Pokud zdroj dokáže dodat alespoň 10 wattů, může být doba provozu HoloLens delší (u některých úloh potenciálně po neomezenou dobu).</span><span class="sxs-lookup"><span data-stu-id="0cdbe-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="0cdbe-111">Použitím usb-A-C a usb-c se tento poplatek omezí na 7,5 W.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="0cdbe-112">Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="0cdbe-113">Když je HoloLens v pohotovostním režimu, stačí 18 wattů k dosažení maximální frekvence nabíjet interní baterie.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="0cdbe-114">Když se HoloLens používá, může se snížit sazba za poplatky, protože HoloLens upřednostňuje provoz před účtováním.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cdbe-115">Doporučuje se, aby se HoloLens 2 účtuje minimálně při 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="0cdbe-116">Neměly by se používat adaptéry, které dodávají alespoň 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="0cdbe-117">Externí sady baterie</span><span class="sxs-lookup"><span data-stu-id="0cdbe-117">External Battery Packs</span></span>

<span data-ttu-id="0cdbe-118">Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="0cdbe-119">Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="0cdbe-120">Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že místo poplatků z ní účtují HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="0cdbe-121">Správa heat služby</span><span class="sxs-lookup"><span data-stu-id="0cdbe-121">Managing Heat</span></span>

<span data-ttu-id="0cdbe-122">Stejně jako u jakéhokoli zařízení i při účtování HoloLens generuje teplo.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="0cdbe-123">Čím je poplatek rychlejší, tím více se generuje teplo.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="0cdbe-124">Při spuštění poplatku na nižší úrovni baterie se navíc vygeneruje více teplo než při spuštění, když je baterie většinou plná.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="0cdbe-125">Zákazníci, kteří potřebují provozovat HoloLens po delší dobu v horkých prostředích, mohou používat následující techniky:</span><span class="sxs-lookup"><span data-stu-id="0cdbe-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="0cdbe-126">HoloLens 2 můžete připojit k externímu zdroji napájení i v případě, že je interní baterie plně nabitá.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="0cdbe-127">Při vyčerpání externí baterie bude HoloLens pokračovat v práci s interním bateriem.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="0cdbe-128">Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="0cdbe-129">Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0cdbe-130">Řešení potíží</span><span class="sxs-lookup"><span data-stu-id="0cdbe-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="0cdbe-131">HoloLens účtuje externí baterie</span><span class="sxs-lookup"><span data-stu-id="0cdbe-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="0cdbe-132">Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí ji, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="0cdbe-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="0cdbe-133">Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="0cdbe-134">Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.</span><span class="sxs-lookup"><span data-stu-id="0cdbe-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
