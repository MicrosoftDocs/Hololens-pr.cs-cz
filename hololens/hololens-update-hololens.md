---
title: Aktualizovat HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377637"
---
# <a name="update-hololens"></a>Aktualizovat HoloLens

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

## <a name="go-back-to-a-previous-version---hololens-2"></a>Přejít zpět na předchozí verzi – HoloLens 2

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. To můžete provést pomocí Průvodce pokročilým obnovením a resetovat svoji HoloLens na předchozí verzi.

> [!NOTE]
> Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.

Chcete-li se vrátit k předchozí verzi HoloLens 2, postupujte podle následujících kroků:

1. Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.
1. V počítači si stáhněte z Microsoft Store [Průvodce rozšířeným obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) .
1. Stáhněte si nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).
1. Po dokončení těchto souborů ke stažení otevřete **Průzkumníka souborů**  >  . Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
1. Připojte HoloLens k počítači pomocí USB-A k kabelu USB-C. (I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)
1. Průvodce pokročilým obnovením automaticky detekuje HoloLens. Vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte ruční výběr balíčku a potom vyberte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4. (Vyhledejte soubor s příponou. FFU.)
1. Vyberte **instalovat software** a postupujte podle pokynů.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Přejít zpět na předchozí verzi – HoloLens (1. generace)

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. To můžete provést pomocí nástroje pro obnovení zařízení systému Windows a resetovat svoji HoloLens na předchozí verzi.

> [!NOTE]
> Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.

Chcete-li se vrátit k předchozí verzi HoloLens 1, postupujte podle následujících kroků:

1. Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.
1. Na počítači stáhněte [Nástroj Windows Device Recovery (WDRT)](https://support.microsoft.com/help/12379).
1. Stáhněte si [balíček pro obnovení aktualizace HoloLens výročí](https://aka.ms/hololensrecovery).
1. Po dokončení stahování otevřete **Průzkumníka souborů**  >  . Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
1. Připojte HoloLens k počítači pomocí kabelu mikrosběrnice USB, ke kterému byl dodán. (I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)
1. WDRT automaticky detekuje HoloLens. Vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte ruční výběr balíčku a zvolte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4. (Vyhledejte soubor s příponou. FFU.)
1. Vyberte **instalovat software** a postupujte podle pokynů.

> [!NOTE]
> Pokud WDRT nerozpozná váš HoloLens, zkuste restartovat počítač. Pokud to nepomůže, vyberte **Moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="windows-insider-program-on-hololens"></a>Program Windows Insider na HoloLens

Chcete zobrazit nejnovější funkce v HoloLens?  Pokud ano, připojte se k programu Windows Insider. získáte přístup k buildům Preview pro aktualizace softwaru HoloLens předtím, než budou k dispozici všeobecně veřejnosti.

[Získejte Windows Insider Preview pro Microsoft HoloLens](hololens-insider.md).
