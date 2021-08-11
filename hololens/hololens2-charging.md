---
title: HoloLens 2 baterie a nabíjení
description: Jak naúčtovat HoloLens a používat externí balíčky baterie.
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
ms.openlocfilehash: b117542704968150639a47956a8142d7232fcc66d696feb61ec4fffdaa49df59
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660570"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 baterie a nabíjení

Tato stránka nabízí podrobnosti o tom, jak HoloLens 2 a použití externích sad baterie.

## <a name="charging-the-device"></a>Účtování zařízení

Použijte kabel [USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat. Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W). Spolu s dodanou zdí může HoloLens 2 zařízení naplno naplno za méně než 65 minut, když je zařízení v pohotovostním režimu. Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W napájení.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k nabílení zařízení přes USB, což je pomalé.

## <a name="checking-the-battery-charge-level"></a>Kontrola úrovně baterie
Pokud je zařízení správně spuštěné a spuštěné, existují tři způsoby, jak zkontrolovat úroveň baterie:

- V hlavní nabídce uživatelského rozhraní HoloLens zařízení.
- Prohlédněte si indikátor LED blízko tlačítka napájení (pro poplatek 40 procent byste měli vidět alespoň dvě plné LED diody).
    - Když se zařízení nabíjí, indikátor baterie se rozsvítí, aby indikuje aktuální úroveň poplatku.  Poslední světlo postupně zeslábne a bude indikovat aktivní zpoplatnění.
    - Když je HoloLens, indikátor baterie zobrazí stav baterie v pěti přírůstcích.
    - Když je jen jedna z pěti světel rozsvícená, je úroveň baterie nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, jedno světlo krátce blikne a pak vypadne.
- Na hostitelském počítači otevřete **Průzkumník souborů** a vyhledejte své zařízení HoloLens 2 na levé straně pod **položkou Tento počítač.** Klikněte pravým tlačítkem na zařízení a vyberte **Vlastnosti**. V dialogovém okně se zobrazí úroveň baterie.

   ![Obrazovka HoloLens 2 vlastností zobrazuje úroveň změny baterie.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternativní specifikace poplatků

HoloLens 2 může být účtována zdroji [napájení USB](https://www.usb.org/usb-charger-pd) do 27 W. Pokud zdroj dokáže dodat alespoň 10 W, HoloLens dobu provozu (u některých úloh potenciálně neomezenou dobu). 

> [!NOTE]
> Použitím usb-A-C usb-c se poplatek omezí na 7,5 W. Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.

Pokud HoloLens v pohotovostním režimu, stačí 18 W k dosažení maximální frekvence nabíjet interní baterie. Pokud HoloLens používáte, může se snížit poplatek, protože HoloLens má přednost před účtováním.

> [!IMPORTANT]
> Doporučujeme, aby se HoloLens 2 poplatky minimálně 5V/1,5A. Neměly by se používat sítě, které dodávají alespoň 5V/1,5A. 

### <a name="external-battery-packs"></a>Externí sady baterie

Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2. Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C. Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že HoloLens, a neúčtovat z něj poplatky. 

### <a name="managing-heat"></a>Správa heat služby

Stejně jako u jakéhokoli zařízení i HoloLens generuje teplo. Čím je poplatek rychlejší, tím více se generuje teplo. Při spuštění poplatek na nižší úrovni baterie se navíc vygeneruje větší teplo než při spuštění, když je baterie převážně plná. Zákazníci, kteří potřebují HoloLens delší dobu pracovat v horkých prostředích, mohou použít následující techniky:

- Je v pořádku připojit HoloLens 2 k externímu zdroji napájení, i když je interní baterie plně nabitá.
- Když je externí baterie vyčerpaná, HoloLens pokračovat v provozu na interním baterie.    
- Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A. Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.

## <a name="troubleshooting"></a>Poradce při potížích


### <a name="hololens-charges-external-battery"></a>HoloLens Poplatky za externí baterie
Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí se, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C. Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.
