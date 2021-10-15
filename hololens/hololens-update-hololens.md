---
title: Aktualizace HoloLens 2
description: Zjistěte, jak zkontrolovat HoloLens sestavení, udržovat si aktuální informace o aktualizacích zařízení, připojit se k programu Insiders a vracet aktualizace zpět.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, kontrola sestavení, číslo sestavení
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
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034259"
---
# <a name="update-hololens-2"></a>Aktualizace HoloLens 2

## <a name="overview"></a>Přehled

Vždy pracujeme na nových funkcích, opravách chyb a aktualizacích zabezpečení. Až budou tyto aktualizace připravené, budete upozorněni.

Na základě vašich preferencí bude váš HoloLens automaticky stahovat a instalovat aktualizace systému při každém připojení k napájení, připojení k internetu a dokonce i v pohotovostním režimu.

Aby se zajistilo HoloLens váš počítač vždy aktualizovaný, nechte ho připojený ke zdroji, který s ním přišel. Chcete také, aby HoloLens připojili k internetu. Tímto způsobem automaticky stáhne a nainstaluje aktualizace systému. 

S Windows Update budete řídit několik aspektů procesu aktualizace, například to, která zařízení chystá aktualizace v jaké době. Tento ovládací prvek je užitečný, protože pro účely testování můžete do podmnožiny zařízení HoloLens aktualizace. Pak zakašla aktualizace zbývajících aktualizací. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

## <a name="types-of-updates"></a>Typy aktualizací

Například HoloLens automaticky spravovat dva typy aktualizací.

- Aktualizace funkcí: vydaná dvakrát ročně.
- Aktualizace kvality: Zahrnují důležité aktualizace zabezpečení. Vydaná měsíčně nebo podle potřeby.

Pomocí **možnosti** / **Povolit aktualizaciAutoUpdate** můžete spravovat kontrolu, stahování a instalaci aktualizací. 

## <a name="scheduling-updates"></a>Plánování aktualizací

Můžete také nastavit plán aktualizace. Může to být v konkrétní den nebo každý den v konkrétním čase. Například v 17:00 nebo mimo aktivní dobu.

Nakonec pár slov o plánování strategie aktualizací. Podporujeme odložení aktualizací, takže se můžete rozhodnout, jak dlouho počkáte, než Microsoft uvolní aktualizaci pro instalaci této aktualizace na zařízeních.

Někdy má společnost ráda, když si nejprve vyzkoušejí všechny nové funkce, aby se ujistila, že všechno funguje, a jsou obeznámeni s novými aktualizacemi, aby byl jejich tým podpory připravený. Jakmile potvrdí, že je vše v pořádku, zak budou zasažovat aktualizace pro celou společnost. Když přidružíte podmnožiny zařízení k různým zásadám odložení, označované jako aktualizační okruhy, můžete koordinovat strategii pro zasouvání aktualizací pro vaši organizaci.

## <a name="hololens-update-tools"></a>HoloLens nástroje pro aktualizaci

Tato část vás provede těmito HoloLens pro:

- kontrola aktualizací
- ruční aktualizace HoloLens
- zobrazení aktuální verze operačního systému (číslo sestavení)
- Vrácení zpět ke starší aktualizaci

### <a name="check-for-updates-and-manually-update"></a>Kontrola aktualizací a ruční aktualizace

Aktualizace můžete vyhledat kdykoli v nastavení.  Zobrazení dostupných aktualizací a kontrola nových aktualizací:

1. Otevřete aplikaci **Nastavení**.
1. Přejděte na **Update & Security** Windows  >  **Update**.
1. Vyberte **Vyhledat aktualizace**.

Pokud je k dispozici aktualizace, začne stahovat novou verzi. Po dokončení stahování aktivujte  instalaci výběrem tlačítka Restartovat. Pokud je vaše zařízení nižší než 40 % a není zapojené do napájení, restartování se nespustí při instalaci aktualizace.

Zatímco HoloLens aktualizace instaluje, zobrazí se rotující ozubené kolo a indikátor průběhu. Během této doby nevy vypnutou HoloLens počítač. Po dokončení instalace se automaticky restartuje.

HoloLens aktualizace po jedné.  Pokud je HoloLens více než jedna verze za nejnovější verzí, možná budete muset proces aktualizace spustit vícekrát, abyste ji plně aktualizační.

### <a name="check-your-operating-system-version-build-number"></a>Kontrola verze operačního systému (číslo sestavení)

Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete **Nastavení** a **vyberete O**  >  **systému.**

### <a name="go-back-to-a-previous-version"></a>Zpět na předchozí verzi

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Doporučené kroky jsou následující:

1. Kontaktujte podporu a podívejte se, jestli váš problém vyřešit vyřešit.
    1. Ujistěte **se,** **že** je povolená volitelná nebo úplná telemetrie – díky tomu bude vaše chyba lépe itelná a pro techniky bude snazší ji diagnostikovat.
    1. V [části Zpětná vazba](hololens-feedback.md) k souborům musí být co nej popisnější. Poznamenejte si název nebo použijte funkci sdílení, abyste mohli chybu sdílet s podporou.
    1. Kontaktujte [podporu](https://aka.ms/hlsupport). Pokud je vaším problémem problém, který je potřeba vyřešit návratem k předchozí verzi, může vám poskytnout ffu pro flash disk vašeho zařízení.

1. Pokud to nefunguje, odmítnutí hesla [HoloLens 2 pomocí možnosti Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Kromě toho, pokud chcete zůstat v aktuálně nainstalované verzi, můžete aktualizace pozastavit [také ručně.](hololens-updates.md#pause-updates-via-device) Technický tým tak bude mít čas problém vyřešit.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program na HoloLens

Chcete se podívat na nejnovější funkce v HoloLens?  Pokud ano, připojte se k Windows Insider Program. Budete mít přístup k sestavením preview aktualizací HoloLens softwaru, než budou dostupné pro veřejnost.

[Získejte Windows Insider preview pro Microsoft HoloLens](hololens-insider.md).