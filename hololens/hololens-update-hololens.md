---
title: Aktualizace HoloLens 2
description: Naučte se kontrolovat číslo sestavení HoloLens, udržovat aktuální informace o aktualizacích zařízení, zapojit se do programu Insiders a vracet aktualizace.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, ověření sestavení, číslo sestavení
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924107"
---
# <a name="update-hololens-2"></a>Aktualizace HoloLens 2

HoloLens používá web Windows Update stejně jako jiná zařízení s Windows 10. Vaše HoloLens automaticky stáhne a nainstaluje aktualizace systému, kdykoli se připojí k Internetu, a to i v případě, že je v pohotovostním režimu.

Tento článek vás provede nástroji HoloLens pro:

- zobrazení aktuální verze operačního systému (číslo sestavení)
- hledají se aktualizace.
- Ruční aktualizace HoloLens
- vrácení zpět se starší aktualizací

## <a name="check-your-operating-system-version-build-number"></a>Ověřit verzi operačního systému (číslo sestavení)

Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete aplikaci nastavení a vyberete **systém**  >  .

## <a name="check-for-updates-and-manually-update"></a>Vyhledat aktualizace a ručně aktualizovat

Aktualizace můžete vyhledat kdykoli v nastavení.  Chcete-li zobrazit dostupné aktualizace a vyhledat nové aktualizace:

1. Otevřete aplikaci **Nastavení**.
1. Přejděte k **aktualizaci web Windows Update zabezpečení &**  >  .
1. Vyberte **Vyhledat aktualizace**.

Pokud je k dispozici aktualizace, začne se stahovat nová verze. Po dokončení stahování spusťte instalaci kliknutím na tlačítko **restartovat** . Pokud je vaše zařízení pod 40% a není napájené z elektrické sítě, při restartování se nespustí instalace aktualizace.

I když váš HoloLens instaluje aktualizaci, zobrazí se ozubené kolečka a indikátor průběhu. Během této doby nepínejte HoloLens. Po dokončení instalace se automaticky restartuje.

HoloLens používá vždy jednu aktualizaci.  Pokud máte více než jednu verzi, kterou máte v poslední době, možná budete muset projít proces aktualizace několikrát, abyste ho mohli plně aktualizovat.

## <a name="go-back-to-a-previous-version"></a>Přejít zpět na předchozí verzi

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. Doporučené kroky jsou tyto:

1. Pokud chcete zjistit, jestli můžou problém vyřešit, obraťte se na podporu.
    1. Zajistěte, aby byla povolená **volitelná** nebo **plná** telemetrie – díky tomu je vaše chyba více užitečná a snazší pro inženýry diagnostikovat.
    1. [Zpětná vazba](hololens-feedback.md) je co nejsrozumitelnější. Poznamenejte si název nebo použijte funkci sdílení, abyste mohli svoji chybu sdílet s podporou.
    1. Obraťte se na [podporu](https://aka.ms/hlsupport). Pokud je váš problém takový, který je potřeba vyřešit vrácením do předchozí verze, může vám dodávat FFU k tomu, aby vaše zařízení bylo možné zablikat.

1. Pokud to nefunguje, [resetujte nebo znovu zablikají svůj HoloLens 2 s pokročilým pomocníkem pro obnovení](hololens-recovery.md).
    1. V počítači si stáhněte z Microsoft Store [Průvodce rozšířeným obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) .
    1. Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.
    1. Vyberte verzi, kterou chcete zablikat:
        1. Můžete si stáhnout nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).
        1. Můžete použít výchozí sestavení, které jsou hostiteli ARC. (Pokud zvolíte tuto možnost, přejděte k dalšímu kroku.)
        1. Můžete použít podporu sestavení, která vám poskytne.
    1. Po dokončení těchto souborů ke stažení otevřete **Průzkumníka souborů**  >  . Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
    1. Připojte HoloLens k počítači pomocí USB-A k kabelu USB-C. (I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)
    1. Průvodce pokročilým obnovením automaticky detekuje HoloLens. Vyberte dlaždici **Microsoft HoloLens** .
    1. Na další obrazovce vyberte ruční výběr balíčku a potom vyberte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4. (Vyhledejte soubor s příponou. FFU.)
    1. Vyberte **instalovat software** a postupujte podle pokynů.

> [!NOTE]
> Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.

Pokud budete chtít zůstat v aktuálně nainstalované verzi, můžete také ručně [pozastavit aktualizace](hololens-updates.md#pause-updates-via-device). To poskytne technickému týmu čas k vyřešení problému.

## <a name="windows-insider-program-on-hololens"></a>Program Windows Insider na HoloLens

Chcete zobrazit nejnovější funkce v HoloLens?  Pokud ano, připojte se k programu Windows Insider. získáte přístup k buildům Preview pro aktualizace softwaru HoloLens předtím, než budou k dispozici všeobecně veřejnosti.

[Získejte Windows Insider Preview pro Microsoft HoloLens](hololens-insider.md).
