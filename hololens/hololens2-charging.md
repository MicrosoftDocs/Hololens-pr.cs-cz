---
title: HoloLens 2 baterie a zpoplatnění
description: jak účtovat HoloLens a používat externí balíčky baterie.
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
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035971"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 baterie a zpoplatnění

tato stránka obsahuje podrobné informace o zpoplatnění HoloLens 2 a použití externích balíčků s bateriemi.

## <a name="charging-the-device"></a>Zpoplatnění zařízení

použijte [nabíječku a kabel typu USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) , který byl dodán s HoloLens 2, jako je to nejlepší způsob, jak zařízení účtovat. nabíječka, která je součástí HoloLens 2, poskytuje až 9V @ 2a (18W). spolu s dodanou nabíječkou zdí můžou zařízení HoloLens 2 po dobu, kdy je zařízení v pohotovostním režimu, za méně než 65 minut navýšit baterii na plnou dobu. Pokud tato příslušenství nejsou k dispozici, zajistěte, aby nabíječka, která je k dispozici, mohla podporovat aspoň 15W napájení.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k navýšení kapacity zařízení přes USB, což je pomalé.

## <a name="checking-the-battery-charge-level"></a>Kontroluje se úroveň nabití baterie.
Pokud je zařízení správně spuštěno a běží, existují tři způsoby, jak ověřit úroveň nabití baterie:

- z hlavní nabídky uživatelského rozhraní HoloLens zařízení.
- Podívejte se, že indikátor LED blízko tlačítka napájení (pro poplatek 40 – Percent) by se měl zobrazit aspoň dva Solid diody LED.
    - Když se zařízení účtuje, indikátory baterie až do indikace aktuální úrovně zpoplatnění.  Poslední světlo zmizí a odznačí aktivní zpoplatnění.
    - když je vaše HoloLens zapnutá, indikátor baterie zobrazí úroveň baterie v pěti přírůstcích.
    - Pokud je zapnutá jenom jedna z pěti světel, úroveň baterie je nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, bude se krátce rozsvítit v jednom světle a pak se vrátí.
- na hostitelském počítači otevřete **průzkumníka souborů** a hledejte zařízení HoloLens 2 na levé straně **tohoto počítače**. Pravým tlačítkem myši klikněte na zařízení a vyberte **vlastnosti**. V dialogovém okně se zobrazí úroveň nabití baterie.

   ![na obrazovce vlastnosti HoloLens 2 se zobrazuje úroveň změny baterie.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternativní specifikace zpoplatnění

HoloLens 2 se můžou účtovat podle zdrojů [napájení USB](https://www.usb.org/usb-charger-pd) až do 27 wattů. pokud je zdrojem možné poskytnout aspoň 10 wattů, můžete HoloLens provozní čas prodloužit (pro některé úlohy může být neomezeně). 

> [!NOTE]
> Používání kabelů pro zpoplatnění USB-A USB-C za poplatek bude omezovat poplatky na 7,5 wattů. Provozní čas zůstane prodloužený, ale ne tak dlouho, dokud použijete USB-C do C.

pokud je HoloLens v pohotovostním režimu, je 18 wattů dostačující pro dosažení maximálního množství poplatků za interní baterii. když se HoloLens používá, může se snížit sazba, protože HoloLens při práci nad zpoplatněním určuje prioritu.

> [!IMPORTANT]
> doporučuje se HoloLens 2 účtovat minimálně na snímač 5v síťového/1,5. Nemusíte používat nabíječky, které nemůžou poskytovat aspoň snímač 5V síťového/1.5. 

### <a name="external-battery-packs"></a>Balíčky externích baterií

pro HoloLens 2 se dají použít balíčky baterií, které splňují výše uvedené specifikace. Upozorňujeme však, že se některé balíčky USB-C reúčtují a poskytují napájení stejnému portu USB-C. Je důležité, aby tyto balíčky pro baterii implementovaly [Try. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) , aby se zajistilo, že budou poplatky HoloLens spíše než poplatky. 

### <a name="managing-heat"></a>Správa tepla

stejně jako u libovolného zařízení vyúčtování HoloLens generuje teplo. Rychleji se účtuje náklady, tím je vygenerováno více tepla. Při spuštění nabití na nižší úrovni baterie se taky vygeneruje více tepla, než se začne účtovat, když je baterie většinou plná. zákazníci, kteří potřebují provozovat HoloLens po delší dobu v aktivních prostředích, mohou použít následující postupy:

- můžete se připojit HoloLens 2 k externímu zdroji napájení i v případě, že se interní baterie plně účtuje.
- když dojde k vyčerpání externí baterie, HoloLens bude pokračovat na vnitřní baterii.    
- Pokud je tepl stále problémem po následujících krocích výše, zvažte použití nabíječky nebo balíčku baterie, který omezí navýšení na 1,5 A. Všimněte si, že tato možnost nebude poskytovat tolik provozních času, protože interní baterie se pořád pomalu vystavuje.

## <a name="troubleshooting"></a>Řešení potíží


### <a name="hololens-charges-external-battery"></a>HoloLens Externí baterie poplatků
pokud HoloLens 2 účtuje externí baterii, a neúčtuje se jim, znamená to, že baterie neimplementuje metodu [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Pro vyřešení tohoto problému je doporučena možnost přechodu na novější verzi, ale můžete také zkusit přepnout na kabel USB-A na USB-C. Pamatujte na to, že se omezí sazba za zpoplatnění na 7,5 wattů.
