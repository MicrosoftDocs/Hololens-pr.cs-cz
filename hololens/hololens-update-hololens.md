---
title: aktualizace HoloLens 2
description: naučte se kontrolovat číslo buildu HoloLens, udržovat aktuální informace o aktualizacích zařízení, zapojit se do programu insiders a vracet aktualizace.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, kontroly sestavení, číslo sestavení
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151698"
---
# <a name="update-hololens-2"></a>aktualizace HoloLens 2

## <a name="overview"></a>Přehled

Pořád pracujeme na nových funkcích, opravách chyb a aktualizacích zabezpečení. Až budou tyto aktualizace připravené, budete upozorněni.

na základě vaší předvolby budou HoloLens automaticky stahovat a instalovat aktualizace systému, kdykoliv je napájen z elektrické sítě, připojen k internetu a dokonce i v pohotovostním režimu.

aby se zajistilo, že se vaše HoloLens vždycky aktualizují, nechte je zapojená spolu s nabíječkou, která s ním byla. budete také chtít HoloLens připojit k internetu. Tímto způsobem budou automaticky staženy a nainstalovány aktualizace systému. 

pomocí web Windows Update služby budete řídit více aspektů procesu aktualizace, například která zařízení získávají aktualizace v daném čase. tento ovládací prvek je užitečný, protože můžete zavádět aktualizace do podmnožiny HoloLensch zařízení pro účely testování. Pak naveďte aktualizace na zbývající. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

## <a name="types-of-updates"></a>Typy aktualizací

pro HoloLens můžete automaticky spravovat dva typy aktualizací.

- Aktualizace funkcí: vydány dvakrát ročně.
- Aktualizace kvality: zahrnuje důležité aktualizace zabezpečení. Jsou vydávány měsíčně nebo podle potřeby.

Pomocí **Update** / **AllowAutoUpdate** můžete spravovat kontrolu, stahování a instalaci aktualizací. 

## <a name="scheduling-updates"></a>Plánování aktualizací

Můžete také nastavit plán aktualizací. Může to být konkrétní den nebo každý den v určitou dobu. Například v rozmezí 5 hodin nebo mimo aktivní hodiny.

Nakonec pár slov o plánování vaší strategie aktualizace. Podporujeme aktualizace pro odložení, takže se můžete rozhodnout, jak dlouho se má čekat, až Microsoft uvolní aktualizaci pro instalaci této aktualizace na zařízení.

Někdy společnost, jako je třeba vyzkoušet nejprve všechny nové funkce, zajistí, že vše bude fungovat a že jsou obeznámeni s novými aktualizacemi, takže tým podpory je připravený. Jakmile ověříte, že všechno je dobré, zavedou aktualizace celé společnosti. Tím, že přidružíte podmnožiny svých zařízení k různým zásadám odložení označovaným jako aktualizační kanály, můžete koordinovat strategii zavedení aktualizací pro vaši organizaci.

## <a name="hololens-update-tools"></a>nástroje HoloLens update

tato část vás provede nástroji pro HoloLens:

- hledají se aktualizace.
- Ruční aktualizace HoloLens
- zobrazení aktuální verze operačního systému (číslo sestavení)
- vrácení zpět se starší aktualizací

### <a name="check-for-updates-and-manually-update"></a>Vyhledat aktualizace a ručně aktualizovat

Aktualizace můžete kdykoli vyhledat v nastavení.  Chcete-li zobrazit dostupné aktualizace a vyhledat nové aktualizace:

1. Otevřete aplikaci **Nastavení**.
1. přejděte k **aktualizaci web Windows Update zabezpečení &**  >  .
1. Vyberte **Vyhledat aktualizace**.

Pokud je k dispozici aktualizace, začne se stahovat nová verze. Po dokončení stahování spusťte instalaci kliknutím na tlačítko **restartovat** . Pokud je vaše zařízení pod 40% a není napájené z elektrické sítě, při restartování se nespustí instalace aktualizace.

i když HoloLens instaluje aktualizaci, zobrazí se ozubené kolečka a indikátor průběhu. během této doby nepínejte HoloLens. Po dokončení instalace se automaticky restartuje.

HoloLens aplikuje jednu aktualizaci na jednu chvíli.  pokud je vaše HoloLens více než jedna verze, může být nutné spustit proces aktualizace několikrát, aby se plně aktualizovaly.

### <a name="check-your-operating-system-version-build-number"></a>Ověřit verzi operačního systému (číslo sestavení)

číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete **Nastavení** a vyberete **systém**  >  .

### <a name="go-back-to-a-previous-version"></a>Přejít zpět na předchozí verzi

v některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Doporučené kroky jsou tyto:

1. Pokud chcete zjistit, jestli můžou problém vyřešit, obraťte se na podporu.
    1. Zajistěte, aby byla povolená **volitelná** nebo **plná** telemetrie – díky tomu je vaše chyba více užitečná a snazší pro inženýry diagnostikovat.
    1. V případě [názoru na soubor](hololens-feedback.md) je co nejsrozumitelnější. Poznamenejte si název nebo použijte funkci sdílení, abyste mohli svoji chybu sdílet s podporou.
    1. Obraťte se na [podporu](https://aka.ms/hlsupport). Pokud je váš problém takový, který je potřeba vyřešit vrácením do předchozí verze, může vám dodávat FFU k tomu, aby vaše zařízení bylo možné zablikat.

1. alternativně můžete [HoloLens 2 přeblikat s pokročilým průvodcem obnovením](hololens-recovery.md#clean-reflash-the-device).
    1.  Vyberte verzi, kterou chcete zablikat: 
        1.  můžete si stáhnout nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).
        1.  Můžete použít výchozí sestavení, které jsou hostiteli ARC.
        1.  Můžete použít podporu sestavení, která vám poskytne.

> [!NOTE]
> Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.

Pokud budete chtít zůstat v aktuálně nainstalované verzi, můžete také ručně [pozastavit aktualizace](hololens-updates.md#pause-updates-via-device). To poskytne technickému týmu čas k vyřešení problému.

## <a name="windows-insider-program-on-hololens"></a>Windows Program Insider v HoloLens

Chcete zobrazit nejnovější funkce v HoloLens?  pokud ano, připojte se k programu Windows Insider. získáte přístup k buildům preview HoloLens aktualizací softwaru předtím, než jsou k dispozici obecné veřejnosti.

[získejte Windows Insider preview pro Microsoft HoloLens](hololens-insider.md).