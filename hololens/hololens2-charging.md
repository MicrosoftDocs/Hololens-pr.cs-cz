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
# <a name="battery-and-charging"></a>Baterie a dobíjení

Tato stránka nabízí podrobnosti o účtování HoloLens 2 a používání externích sad baterie.

## <a name="included-charger"></a>Included Neschádka

Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W). Pokud je to možné, důrazně doporučujeme účtovat pomocí zahrnutých poplatků.  

## <a name="specifications"></a>Specifikace

HoloLens 2 se může naúčtovat pomocí [zdrojů NAPÁJENÍ USB](https://www.usb.org/usb-charger-pd) o výkonu až 27 wattů. Pokud zdroj dokáže dodat alespoň 10 wattů, může být doba provozu HoloLens delší (u některých úloh potenciálně po neomezenou dobu). 

> [!NOTE]
> Použitím usb-A-C a usb-c se tento poplatek omezí na 7,5 W. Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.

Když je HoloLens v pohotovostním režimu, stačí 18 wattů k dosažení maximální frekvence nabíjet interní baterie. Když se HoloLens používá, může se snížit sazba za poplatky, protože HoloLens upřednostňuje provoz před účtováním.

> [!IMPORTANT]
> Doporučuje se, aby se HoloLens 2 účtuje minimálně při 5V/1,5A. Neměly by se používat adaptéry, které dodávají alespoň 5V/1,5A. 

## <a name="external-battery-packs"></a>Externí sady baterie

Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2. Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C. Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že místo poplatků z ní účtují HoloLens. 

## <a name="managing-heat"></a>Správa heat služby

Stejně jako u jakéhokoli zařízení i při účtování HoloLens generuje teplo. Čím je poplatek rychlejší, tím více se generuje teplo. Při spuštění poplatku na nižší úrovni baterie se navíc vygeneruje více teplo než při spuštění, když je baterie většinou plná. Zákazníci, kteří potřebují provozovat HoloLens po delší dobu v horkých prostředích, mohou používat následující techniky:

- HoloLens 2 můžete připojit k externímu zdroji napájení i v případě, že je interní baterie plně nabitá.
- Při vyčerpání externí baterie bude HoloLens pokračovat v práci s interním bateriem.    
- Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A. Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.

## <a name="troubleshooting"></a>Řešení potíží


### <a name="hololens-charges-external-battery"></a>HoloLens účtuje externí baterie
Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí ji, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C. Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.
