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
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Battery and Charging

Tato stránka nabízí podrobnosti o účtování HoloLens 2 a používání externích sad baterie.

## <a name="charging-the-device"></a>Účtování zařízení

Použijte kabel USB typu [C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat. Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W). Zařízení HoloLens 2 mohou společně se dodanou zdi naplno nabít za méně než 65 minut, když je zařízení v pohotovostním režimu. Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W energie.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k nabílení zařízení přes USB, což je pomalé.

## <a name="checking-the-battery-charge-level"></a>Kontrola úrovně baterie
Pokud je zařízení správně spuštěné a spuštěné, existují tři způsoby, jak zkontrolovat úroveň baterie:

- V hlavní nabídce uživatelského rozhraní zařízení HoloLens.
- Led diodu si prohlédněte blízko tlačítka napájení (při 40procentní poplatek byste měli vidět alespoň dvě plné LED diody).
    - Když se zařízení nabíjí, indikátor baterie se rozsvítí, aby indikuje aktuální úroveň poplatku.  Poslední světlo postupně zeslábne a bude indikovat aktivní zpoplatnění.
    - Když je holoLens v systému, indikátor baterie zobrazí stav baterie v pěti přírůstcích.
    - Když je jen jedna z pěti světel rozsvícená, je úroveň baterie nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, jedno světlo krátce blikne a pak vypadne.
- Na hostitelském počítači otevřete **Průzkumník souborů** vyhledejte zařízení HoloLens 2 na levé straně pod **položkou Tento počítač.** Klikněte pravým tlačítkem na zařízení a vyberte **Vlastnosti**. V dialogovém okně se zobrazí úroveň baterie.

   ![Obrazovka vlastností HoloLens 2 zobrazuje úroveň změny baterie](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternativní specifikace poplatků

HoloLens 2 se může účtovat pomocí [zdrojů NAPÁJENÍ USB](https://www.usb.org/usb-charger-pd) do 27 wattů. Pokud zdroj dokáže dodat alespoň 10 wattů, může být doba provozu HoloLens delší (u některých úloh potenciálně po neomezenou dobu). 

> [!NOTE]
> Použitím usb-A-C usb-c se poplatek omezí na 7,5 W. Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.

Když je HoloLens v pohotovostním režimu, stačí 18 wattů k dosažení maximální frekvence nabíjet interní baterie. Když se HoloLens používá, může být sazba za poplatek snížená, protože HoloLens upřednostňuje provoz před účtováním.

> [!IMPORTANT]
> Doporučuje se, aby se HoloLens 2 účtuje minimálně při 5V/1,5A. Neměly by se používat sítě, které dodávají alespoň 5V/1,5A. 

### <a name="external-battery-packs"></a>Externí sady baterie

Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2. Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C. Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že místo poplatků z ní účtují HoloLens. 

### <a name="managing-heat"></a>Správa heat služby

Stejně jako u jakéhokoli zařízení i při účtování HoloLens generuje teplo. Čím je poplatek rychlejší, tím více se generuje teplo. Při spuštění poplatek na nižší úrovni baterie se navíc vygeneruje větší teplo než při spuštění, když je baterie převážně plná. Zákazníci, kteří potřebují provozovat HoloLens po delší dobu v horkých prostředích, mohou používat následující techniky:

- HoloLens 2 můžete připojit k externímu zdroji napájení i v případě, že je interní baterie plně nabitá.
- Při vyčerpání externí baterie bude HoloLens pokračovat v práci s interním bateriem.    
- Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A. Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.

## <a name="troubleshooting"></a>Řešení potíží


### <a name="hololens-charges-external-battery"></a>HoloLens účtuje externí baterie
Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí ji, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C. Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.
