---
title: Aktualizace HoloLens 2
description: Zjistěte, jak zkontrolovat HoloLens sestavení, udržovat si aktuální informace o aktualizacích zařízení, připojit se k programu Insiders a vrátit aktualizace zpět.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, kontrola sestavení, číslo sestavení
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662829"
---
# <a name="update-hololens-2"></a>Aktualizace HoloLens 2

HoloLens používá Windows Update, stejně jako ostatní Windows 10 zařízení. Váš HoloLens automaticky stahuje a instaluje aktualizace systému pokaždé, když je zapojený do napájení a připojený k internetu, i když je v pohotovostním režimu.

Tento článek vás provede následujícími HoloLens nástroje pro:

- zobrazení aktuální verze operačního systému (číslo sestavení)
- kontrola aktualizací
- ruční aktualizace HoloLens
- Vrácení zpět ke starší aktualizaci

## <a name="check-your-operating-system-version-build-number"></a>Kontrola verze operačního systému (číslo sestavení)

Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete aplikaci Nastavení a vyberete **O**  >  **systému.**

## <a name="check-for-updates-and-manually-update"></a>Kontrola aktualizací a ruční aktualizace

Aktualizace můžete kdykoli zkontrolovat v nastavení.  Zobrazení dostupných aktualizací a kontrola nových aktualizací:

1. Otevřete aplikaci **Nastavení**.
1. Přejděte na **Update & Security** Windows  >  **Update**.
1. Vyberte **Vyhledat aktualizace**.

Pokud je k dispozici aktualizace, začne stahovat novou verzi. Po dokončení stahování aktivujte  instalaci výběrem tlačítka Restartovat. Pokud je vaše zařízení nižší než 40 % a není zapojené do napájení, restartování aktualizace se nespustí.

Zatímco HoloLens aktualizace instaluje, zobrazí se rotující ozubené kolo a indikátor průběhu. Během této doby nevy vypnutou HoloLens počítač. Po dokončení instalace se automaticky restartuje.

HoloLens se používá jedna aktualizace najednou.  Pokud je HoloLens víc než jedna verze za nejnovější verzí, možná budete muset proces aktualizace projít vícekrát, abyste ji mohli plně aktualizovat.

## <a name="go-back-to-a-previous-version"></a>Zpět na předchozí verzi

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Doporučené kroky jsou následující:

1. Kontaktujte podporu a podívejte se, jestli váš problém vyřešit vyřešit.
    1. Ujistěte **se,** **že** je povolená volitelná nebo úplná telemetrie – díky tomu bude vaše chyba lépe itelná a pro techniky bude snazší ji diagnostikovat.
    1. [Zpětná vazba](hololens-feedback.md) k souborům je co nejvíce popisná. Poznamenejte si název nebo použijte funkci sdílení, abyste mohli chybu sdílet s podporou.
    1. Kontaktujte [podporu](https://aka.ms/hlsupport). Pokud je vaším problémem problém, který je potřeba vyřešit návratem k předchozí verzi, může vám poskytnout ffu pro flash disk vašeho zařízení.

1. Pokud to nefunguje, obnovte nebo znovu napomátujte [HoloLens 2 pomocí možnosti Advanced Recovery Companion](hololens-recovery.md).
    1. Na svém počítači si z [webu stáhněte](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) doprovodný software pro pokročilé Microsoft Store.
    1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k počítači.
    1. Zvolte verzi, na kterou chcete flash disk použít:
        1. Můžete si stáhnout [nejnovější verzi HoloLens 2.](https://aka.ms/hololens2download)
        1. Můžete použít výchozí sestavení, které arc hostuje. (Pokud zvolíte tuto možnost, přeskočte další krok.)
        1. Můžete použít podporu sestavení, kterou máte k dispozici.
    1. Po dokončení těchto stahování otevřete soubor **Průzkumník souborů**  >  **ke stažení.** Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
    1. Připojení připojte HoloLens k počítači pomocí kabelu USB-A na USB-C. (I v případě, že pro připojení svého zařízení používáte HoloLens kabely, funguje to nejlépe.)
    1. Advanced Recovery Companion automaticky rozpozná váš HoloLens. Vyberte **dlaždici Microsoft HoloLens.**
    1. Na další obrazovce vyberte **Ruční výběr** balíčku a pak vyberte instalační soubor obsažený ve složce, kterou jste rozbalili v kroku 4. (Vyhledejte soubor s příponou .ffu.)
    1. Vyberte **Nainstalovat software** a postupujte podle pokynů.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Kromě toho, pokud chcete zůstat v aktuálně nainstalované verzi, můžete aktualizace pozastavit [také ručně.](hololens-updates.md#pause-updates-via-device) Technický tým tak bude mít čas problém vyřešit.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program na HoloLens

Chcete se podívat na nejnovější funkce v HoloLens?  Pokud ano, připojte se k Windows Insider Program. Budete mít přístup k sestavením preview aktualizací HoloLens softwaru, než budou dostupné pro veřejnost.

[Získejte Windows Insider preview pro Microsoft HoloLens](hololens-insider.md).
