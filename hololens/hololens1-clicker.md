---
title: Použití kliknutí HoloLens
description: Tento článek popisuje, jak používat kliknutí HoloLens, včetně párování kliknutí, účtování a obnovení.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377737"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>Použití kliknutí HoloLens (1. generace)

Kliknutí bylo navrženo speciálně pro HoloLens (1. generace) a nabízí další způsob interakce s hologramy. Dodává se s HoloLens (1. generace) v samostatném rámečku.

Použijte ho místo ručních gest k výběru, posouvání, přesouvání a změně velikosti aplikací.

## <a name="clicker-hardware-and-pairing"></a>Hardware a párování klikání

Kliknutí HoloLens (1. generace) má smyčku prstu, která usnadňuje podržení, a indikátorové světlo.

![The HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Indikátory clickeru

Toto znamenají světla na klikateli.

- **Blikající bílé .** Kliknutí je v režimu párování.
- **Rychle blikající bílé .** Párování bylo úspěšné.
- **Plnou bílou .** Kliknutí se načítá.
- **Blikající žlutoho.** Baterie je málo.
- **Solidní žlutohnědé**. Při kliknutí došlo k chybě a budete ji muset restartovat. Při stisknutí tlačítka pro párování klikněte a podržte na 15 sekund.

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>Spárování kliknutí s HoloLens (1. generace)

1. Pomocí gesta bloom přejděte na **Start (Spustit),** vyberte Settings Devices   >  **(Nastavení) Devices (Nastavení) Devices (Zařízení)** a ověřte, že je zapnuté Bluetooth.
1. Na klikání stiskněte a podržte tlačítko párování, dokud stavové světlo nebude blikat bíle.
1. Na obrazovce párování vyberte **Pár kliknutí**  >  .

### <a name="charge-the-clicker"></a>Poplatek za kliknutí

Když je klikatel vybídne, indikátor baterie bude blikat žlutou. Připojte kabel Micro USB k napájecímu zdroji USB pro nabíjíní zařízení.

## <a name="use-the-clicker-with-hololens-1st-gen"></a>Použití kliknutí s HoloLens (1. generace)

### <a name="hold-the-clicker"></a>Podržení klikače

Pokud chcete zaklikat, posuňte smyčku přes kruh nebo prostřední prst tak, aby port Micro USB směřil k vašemu okruhu. Čekací kolečko odsazení.

![Jak podržet clicker](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Gesta kliknutí

Gesta klikacích zařízení jsou malá otočení, nikoli větší pohyby používané pro gesta rukou HoloLens. A HoloLens rozpozná vaše gesta a klikne, i když je kliknutí mimo rámec [gesta,](hololens1-basic-usage.md)takže můžete podržet kliknutí na pozici, která je pro vás nejpohodlnější.

- **Vyberte**. Pokud chcete vybrat hologram, tlačítko nebo jiný prvek, upřete na něj pohled a klikněte na něj.

- **Klikněte na a podržte .** Kliknutím a podržením palce dolů na tlačítku můžete klepnutím a podržením provést některé z věcí, jako je přesunutí nebo změna velikosti hologramu.

- **Posuňte se na**. Na panelu aplikace vyberte Scroll **Tool (Nástroj pro posouvání).** Klikněte a podržte a pak klikejte nahoru, dolů, doleva nebo doprava. Pokud se chcete posouvat rychleji, přesuňte svou rukou dál od středu nástroje pro posouvání.

- **Zoom (Přiblížit).** Na panelu aplikace vyberte Nástroj **lupy.** Kliknutím a podržením a otočením klikače nahoru můžete zobrazení přiblížit nebo oddálit.

> [!TIP]
> Pokud chcete zobrazení přiblížit nebo oddálit Microsoft Edge, nahlédněte na stránku a poklikejte na něj.

## <a name="restart-or-recover-the-clicker"></a>Restartování nebo obnovení kliknutí

Tady je několik věcí, které můžete vyzkoušet, pokud kliknutí na HoloLens nereaguje nebo nefunguje dobře.

### <a name="restart-the-clicker"></a>Restartujte kliknutí.

Pomocí špičky pera stiskněte a podržte tlačítko párování. Současně klikněte a podržte na 15 sekund kliknutí. Pokud už kliknutí bylo spárované s holoLens, zůstane spárované i po restartování.

Pokud se kliknutí nezačne zapnout nebo restartovat, zkuste ho zapnout pomocí zařízení HoloLens. Pokud je baterie velmi nízká, může trvat několik minut, než se světlo bílého indikátoru zapne.

### <a name="re-pair-the-clicker"></a>Opětovné spárování klikače

Vyberte **Nastavení**  >  **Zařízení** a klikněte na něj. Vyberte **Odebrat,** počkejte několik sekund a pak znovu spárujte kliknutí.

### <a name="recover-the-clicker"></a>Obnovení klikače

Pokud restartováním a znovu spárováním klikacího nástroje problém nevyřešíte, může vám s jeho obnovením pomoct nástroj Windows Device Recovery. Proces obnovení může nějakou dobu trvat a nainstaluje nejnovější verzi softwaru klikače. K použití tohoto nástroje budete potřebovat počítač se systémem Windows 10 nebo novějším, který má alespoň 4 GB volného místa v úložišti.

Obnovení klikače:

1. Stáhněte a nainstalujte do svého počítače nástroj Obnovení zařízení systému [Windows.](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)
1. Ke svému počítači připojte klikače pomocí kabelu Micro USB, který jste dodáli s holoLens.
1. Spusťte nástroj Windows Device Recovery Tool a postupujte podle pokynů.

Pokud se kliknutí nezjistne  automaticky, vyberte Moje zařízení nebylo zjištěno a postupujte podle pokynů k nastavení zařízení do režimu obnovení.
