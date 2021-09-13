---
title: Aktualizace HoloLens 2
description: Zjistěte, jak zkontrolovat HoloLens sestavení, udržovat si aktuální informace o aktualizacích zařízení, připojit se k programu Insiders a vracet aktualizace zpět.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, kontrola sestavení, číslo sestavení
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032384"
---
# <a name="update-hololens-2"></a>Aktualizace HoloLens 2

## <a name="overview"></a>Přehled

Vždy pracujeme na nových funkcích, opravách chyb a aktualizacích zabezpečení. Až budou tyto aktualizace připravené, budete upozorněni.

Na základě vašich preferencí bude váš HoloLens automaticky stahovat a instalovat aktualizace systému při každém připojení k napájení, připojení k internetu a dokonce i v pohotovostním režimu.

Pokud chcete mít HoloLens, že je vždy aktualizovaný, nechejte ho připojený ke zdroji, který s ním přišel. Chcete také, aby HoloLens připojili k internetu. Tímto způsobem automaticky stáhne a nainstaluje aktualizace systému. 

S Windows Update budete řídit několik aspektů procesu aktualizace, například to, která zařízení chystá aktualizace v jaké době. Tento ovládací prvek je užitečný, protože můžete pro účely testování HoloLens aktualizace podmnožiny zařízení. Pak zakašla aktualizace zbývajících aktualizací. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

## <a name="types-of-updates"></a>Typy aktualizací

Například HoloLens automaticky spravovat dva typy aktualizací. 

- Aktualizace funkcí: vydaná dvakrát ročně.
- Aktualizace kvality: Zahrnují důležité aktualizace zabezpečení. Vydaná měsíčně nebo podle potřeby.

Pomocí **možnosti** / **Povolit aktualizaciAutoUpdate** můžete spravovat kontrolu, stahování a instalaci aktualizací. 

## <a name="scheduling-updates"></a>Plánování aktualizací

Můžete také nastavit plán aktualizace. Může to být v konkrétní den nebo každý den v konkrétním čase. Například v 17:00 nebo mimo aktivní dobu.

Nakonec pár slov o plánování strategie aktualizací. Podporujeme odložení aktualizací. Můžete se tedy rozhodnout, jak dlouho počkáte, než Microsoft uvolní aktualizaci, aby se tato aktualizace na zařízeních instaluje.

Někdy má společnost rádi, když si nejprve vyzkoušejí všechny nové funkce, aby se ujistila, že všechno funguje, a jsou obeznámeni s novými aktualizacemi, aby byl jejich tým podpory připravený. Jakmile potvrdí, že je vše v pořádku, zak budou zasažovat aktualizace pro celou společnost. Když přidružíte podmnožiny zařízení k různým zásadám odložení, označované jako aktualizační okruhy, můžete koordinovat strategii pro zasouvání aktualizací pro vaši organizaci.

## <a name="hololens-update-tools"></a>HoloLens nástroje pro aktualizaci

Tato část vás provede těmito HoloLens nástroje pro:

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

Zatímco HoloLens aktualizace instaluje, zobrazí se rotující ozubené kolo a indikátor průběhu. Během této doby nevynulová HoloLens nevypnout. Po dokončení instalace se automaticky restartuje.

HoloLens aktualizace po jedné.  Pokud je HoloLens více než jedna verze za nejnovější verzí, možná budete muset proces aktualizace spustit vícekrát, abyste ji mohli plně aktualizovat.

### <a name="check-your-operating-system-version-build-number"></a>Kontrola verze operačního systému (číslo sestavení)

Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete **Nastavení** a **vyberete O**  >  **systému.**

### <a name="go-back-to-a-previous-version"></a>Zpět na předchozí verzi

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Doporučené kroky jsou následující:

1. Kontaktujte podporu a podívejte se, jestli váš problém vyřešit vyřešit.
    1. Ujistěte **se,** **že** je povolená volitelná nebo úplná telemetrie – díky tomu bude vaše chyba lépe itelná a pro techniky bude snazší ji diagnostikovat.
    1. [Zpětná vazba](hololens-feedback.md) k souborům je co nejvíce popisná. Poznamenejte si název nebo použijte funkci sdílení, abyste mohli chybu sdílet s podporou.
    1. Kontaktujte [podporu](https://aka.ms/hlsupport). Pokud je vaším problémem problém, který je potřeba vyřešit návratem k předchozí verzi, může vám poskytnout ffu pro flash disk vašeho zařízení.

1. Pokud to nefunguje, obnovte nebo navracení proti HoloLens [2 pomocí možnosti Advanced Recovery Companion.](hololens-recovery.md)
    1. Na svém počítači si z webu [stáhněte](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) doprovodný průvodce pokročilým obnovením Microsoft Store.
    1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k počítači.
    1. Zvolte verzi, na kterou chcete flash disk použít:
        1. Můžete si stáhnout [nejnovější verzi HoloLens 2.](https://aka.ms/hololens2download)
        1. Můžete použít výchozí sestavení, které arc hostuje. (Pokud zvolíte tuto možnost, přeskočte další krok.)
        1. Můžete použít podporu sestavení, kterou máte k dispozici.
    1. Po dokončení těchto stahování otevřete soubor **Průzkumník souborů**  >  **ke stažení.** Klikněte pravým tlačítkem na staženou složku zip a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
    1. Připojení připojte HoloLens k počítači pomocí kabelu USB-A na USB-C. (I v případě, že pro připojení svého zařízení používáte HoloLens kabely, funguje to nejlépe.)
    1. Advanced Recovery Companion automaticky rozpozná vaše HoloLens. Vyberte **dlaždici Microsoft HoloLens.**
    1. Na další obrazovce vyberte **Ruční výběr** balíčku a pak vyberte instalační soubor obsažený ve složce, kterou jste rozbalili v kroku 4. (Vyhledejte soubor s `.ffu` příponou .)
    1. Vyberte **Nainstalovat software** a postupujte podle pokynů.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Kromě toho, pokud chcete zůstat v aktuálně nainstalované verzi, můžete aktualizace pozastavit [také ručně.](hololens-updates.md#pause-updates-via-device) Technický tým tak bude mít čas problém vyřešit.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program na HoloLens

Chcete se podívat na nejnovější funkce v HoloLens?  Pokud ano, připojte se k Windows Insider Program. Budete mít přístup k sestavením preview aktualizací HoloLens softwaru, než budou dostupné pro veřejnost.

[Získejte Windows Insider preview pro Microsoft HoloLens](hololens-insider.md).