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
ms.openlocfilehash: a0ae0ccade01d7df520cd6cb142a9b51e63a2b05
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/28/2021
ms.locfileid: "129163977"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 baterie a nabíjení

Tato stránka nabízí podrobnosti o účtování HoloLens 2 a používání externích sad baterie.

## <a name="charging-the-device"></a>Účtování zařízení

Použijte kabel [USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat. Zařízení, které je součástí HoloLens 2, poskytuje až 9V @ 2A (18 W). Pokud je zařízení v pohotovostním režimu, HoloLens dodaná zeď dodaná zdí, mohou 2 zařízení nabít naplno za méně než 65 minut. Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W energie.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k nabílení zařízení přes USB, což je pomalé.

## <a name="checking-the-battery-charge-level"></a>Kontrola úrovně baterie
Pokud je zařízení správně spuštěné a spuštěné, existují tři způsoby, jak zkontrolovat úroveň baterie:

- V hlavní nabídce uživatelského rozhraní HoloLens zařízení.
- Led diodu si prohlédněte blízko tlačítka napájení (při 40procentní poplatek byste měli vidět alespoň dvě plné LED diody).
    - Když se zařízení nabíjí, indikátor baterie se rozsvítí, aby indikuje aktuální úroveň poplatku.  Poslední světlo postupně zeslábne a bude indikovat aktivní zpoplatnění.
    - Když je HoloLens, indikátor baterie zobrazí stav baterie v pěti přírůstcích.
    - Když je jen jedna z pěti světel rozsvícená, úroveň baterie je nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, jedno světlo krátce blikne a pak vypadne.
- Na hostitelském počítači otevřete **Průzkumník souborů** a vyhledejte své zařízení HoloLens 2 na levé straně pod **položkou Tento počítač.** Klikněte pravým tlačítkem na zařízení a vyberte **Vlastnosti**. V dialogovém okně se zobrazí úroveň baterie.

   ![Obrazovka HoloLens 2 vlastností zobrazuje úroveň změny baterie.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternativní specifikace poplatků

HoloLens 2 se 2 může účtovat pomocí [zdrojů napájení USB](https://www.usb.org/usb-charger-pd) s příkonem až 27 W. Pokud zdroj dokáže dodat alespoň 10 W, HoloLens dobu provozu (u některých úloh potenciálně neomezenou dobu). 

> [!NOTE]
> Použitím usb-A-C usb-c se poplatek omezí na 7,5 W. Doba provozu bude stále delší, ale ne tak dlouho, dokud se USB-C až C bude používat.

Pokud HoloLens v pohotovostním režimu, stačí 18 W, aby dosáhlo maximálního dobíjetí interní baterie. Pokud HoloLens používáte, může se snížit poplatek, protože HoloLens má přednost před účtováním.

> [!IMPORTANT]
> Doporučujeme, aby se HoloLens 2 poplatky minimálně 5V/1,5A. Neměly by se používat sítě, které dodávají alespoň 5V/1,5A. 

### <a name="external-battery-packs"></a>Externí sady baterie

Sady baterie, které splňují výše uvedené specifikace, je možné použít s HoloLens 2. Všimněte si ale, že některé baterie USB-C se dobíjejí a poskytují napájení prostřednictvím stejného portu USB-C. Je důležité, aby tyto sady baterie implementují [TRY. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby se zajistilo, že HoloLens, a neúčtovat z něj poplatky. 

### <a name="managing-heat"></a>Správa heat služby

Stejně jako u všech zařízení i HoloLens generuje teplo. Čím je poplatek rychlejší, tím více se generuje teplo. Při spuštění poplatek na nižší úrovni baterie se navíc vygeneruje větší teplo než při spuštění, když je baterie převážně plná. Zákazníci, kteří potřebují HoloLens delší dobu pracovat v horkých prostředích, mohou používat následující techniky:

- Je v pořádku připojit HoloLens 2 k externímu zdroji napájení, i když je interní baterie plně nabitá.
- Když vyčerpáte externí baterie, HoloLens bude pokračovat v provozu na interní baterie.    
- Pokud i po provedení výše uvedených kroků stále dochází k problému s teplou, zvažte použití baterie nebo baterie, která omezuje účtování na 1,5A. Všimněte si, že tato možnost neposkytuje tolik doby provozu, protože interní baterie se stále pomalu vyčerpá.

## <a name="troubleshooting"></a>Řešení potíží


### <a name="hololens-charges-external-battery"></a>HoloLens Poplatky za externí baterie
Pokud HoloLens 2 nenabíjí externí baterie, ale nenabíjí ji, znamená to, že baterie neimplementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Tento problém můžete vyřešit přepnutím na novější sadu baterie, ale alternativně můžete zkusit přepnout na kabel USB-A na USB-C. Mějte na paměti, že tím se rychlost zpoplatnění omezí na 7,5 W.
