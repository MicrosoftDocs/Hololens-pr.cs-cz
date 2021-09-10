---
title: Restartování, resetování nebo obnovení HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Použití nástroje Windows Device Recovery k zobrazení flash obrázku do HoloLens 1. generace
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427881"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Restartování, resetování nebo obnovení HoloLens (1. generace)

Pokud dochází k problémům s vaší HoloLens, můžete zkusit restartovat nebo resetovat zařízení nebo dokonce pomocí obnovení zařízení odkazovat. Tento článek vás provede doporučenými kroky obnovení v pořadí.

Pokud chcete obnovit novou HoloLens 2, podívejte se na HoloLens [2,](hololens-recovery.md)protože se tento proces liší.

> [!NOTE]
> Tento článek se zaměřuje na HoloLens zařízení a software. Pokud hologramy vypadají správně, najdete informace o faktorech, které zlepšují kvalitu hologramů, **[HoloLens](hololens-environment-considerations.md)** v části Důležité informace o prostředí.

## <a name="restart"></a>Restartovat

### <a name="do-a-safe-restart-by-using-cortana"></a>Proveďte bezpečné restartování pomocí Cortana

Nejbezpečnější způsob, jak restartovat HoloLens, je použít Cortana, což je obecně první věc, kterou je třeba vyzkoušet, když nastane problém s HoloLens.

> [!NOTE] 
> Cortana není k dispozici na všech zařízeních.
> - Cortana dostupná na všech HoloLens (1. generace). 
> - Cortana je k dispozici na HoloLens 2 sestaveních před aktualizací Windows Holograpic verze 2004.

1. Zapněte si HoloLens.
1. Ujistěte se, že je uživatel přihlášený a že zařízení nečeká na odemknutí hesla.
2. Řekněte "Na Cortana, restartování" nebo "Cortana, restartování".
3. Cortana odpoví a vyzve vás k potvrzení. Počkejte, až se po otázce přehrá zvuk, a pak řekněte Ano. Zařízení se restartuje.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Bezpečné restartování pomocí tlačítka napájení

Pokud stále nemůžete zařízení restartovat, zkuste ho restartovat pomocí tlačítka **napájení:**

1. Stiskněte a podržte **tlačítko napájení** po dobu 5 sekund. Po 1 sekundě se všech pět LED diod zprava doleva postupně zprava doleva rozzáří a postupně ho vypne. Po 5 sekundách budou všechny LED diody vypnuté, což značí úspěšné vypnutí.
      
   > [!IMPORTANT]
   > Okamžitě po vypnutí všech LED diod zastavte stisknutí tlačítka.
1. Počkejte 1 minutu, než se vypnutí dokončí. Vypnutí může stále probíhají, i když jsou displeje vypnuté.
2. Znovu zapněte zařízení stisknutím a podržením tlačítka **napájení** na 1 sekundu.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Proveďte bezpečné restartování pomocí Windows Portál zařízení

> [!NOTE]
> Pro tento proces HoloLens nakonfigurovat jako vývojářské zařízení. Další informace najdete [na Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal).

Pokud předchozí postup nefunguje, zkuste zařízení restartovat pomocí příkazu [Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal). V pravém horním rohu vyhledejte možnost restartování nebo vypnutí zařízení.

### <a name="do-an-unsafe-forced-restart"></a>Nebezpečné vynucené restartování

Pokud předchozí metody nerestartuje váš HoloLens, vynutí restartování. Tato metoda je ekvivalentní k odebrání a opětovné instalaci baterie. Je to nebezpečné, protože by mohlo nechat zařízení v poškozeném stavu. Pokud k tomu dojde, budete muset soubor flash HoloLens.  

> [!WARNING]
> Jedná se o potenciálně škodlivou metodu, která by se měla použít pouze v případě, že dříve citované metody nefungují.

1. Stiskněte a podržte **tlačítko** napájení alespoň 10 sekund.
   - Tlačítko můžete podržet déle než 10 sekund.
   - Každou aktivitu indikátoru LED můžete bezpečně ignorovat.
1. Uvolněte tlačítko a počkejte 2–3 sekundy.
1. Stiskněte a podržte **tlačítko** napájení po dobu 1 sekundy.
1. Pokud stále máte problémy,  stiskněte tlačítko napájení po dobu 4 sekund, dokud se všechny indikátory baterie neztlumí a obrazovka přestane zobrazovat hologramy. Počkejte 1 minutu a pak znovu stiskněte **tlačítko** napájení, aby se zařízení zapne.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Zpět na předchozí verzi – HoloLens (1. generace)

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Můžete to provést pomocí nástroje Windows Device Recovery Tool a obnovit HoloLens na starší verzi.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens 1, postupujte takto:

1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k počítači.
1. Na svém počítači si stáhněte [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Stáhněte [si balíček HoloLens Anniversary Update recovery.](https://aka.ms/hololensrecovery)
1. Po dokončení stahování otevřete **Průzkumníka souborů Stažené**  >  **soubory.** Klikněte pravým tlačítkem na složku zip, kterou jste si právě stáhli, a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
1. Připojení připojte HoloLens k počítači pomocí kabelu mikro USB, se který dodá. (I v případě, že pro připojení svého zařízení používáte HoloLens kabely, funguje to nejlépe.)
1. WDRT automaticky zjistí vaše HoloLens. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr** balíčku a zvolte instalační soubor obsažený ve složce, kterou jste rozbalili v kroku 4. (Vyhledejte soubor s příponou .ffu.)
1. Vyberte **Nainstalovat software** a postupujte podle pokynů.

> [!NOTE]
> Pokud nástroj WDRT váš počítač HoloLens, zkuste počítač restartovat. Pokud to nefunguje, vyberte **Moje zařízení** se nezjme, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="reset-to-factory-settings"></a>Obnovení továrního nastavení

> [!NOTE]
> Baterie potřebuje k resetování alespoň 40procentní poplatek.

Pokud váš HoloLens potíže, zkuste ho resetovat do stavu továrního nastavení. Tento krok zachová verzi softwaru Windows Holographic, který je v ní nainstalovaný, a vrátí všechno ostatní do továrního nastavení.

>[!WARNING]
> Pokud zařízení resetujete, vymažou se všechny vaše osobní údaje, aplikace a nastavení včetně informací o resetování čipu TPM. Resetováním se nainstaluje jenom nejnovější nainstalovaná verze Windows Holographic. Budete muset znovu provést všechny kroky inicializace (nakalibrovat, připojit se k Wi-Fi, vytvořit uživatelský účet, stáhnout aplikace atd.).

1. Otevřete aplikaci Nastavení a pak vyberte **Aktualizovat**  >  **obnovení.**
1. Vyberte možnost **Resetovat** zařízení a přečtěte si potvrzovací zprávu.
1. Potvrďte resetování. Zařízení se restartuje a zobrazí se sada rotujícího ozubeného kola a indikátor průběhu.
1. Počkejte asi 30 minut, než se tento proces dokončí. Po dokončení se zařízení restartuje do prostředí, které je hotové.

## <a name="reinstall-the-operating-system"></a>Přeinstalujte operační systém.

Pokud má zařízení po restartování a resetování problém, můžete v počítači použít nástroj pro obnovení a znovu nainstalovat HoloLens operační systém a firmware.  

Data, která HoloLens pro resetování, jsou zabalená v úplné aktualizaci Flash Update (FFU), která se podobá souboru .iso, .wim nebo .vhd. [Přečtěte si o formátech souborů obrázků FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Nový operační systém můžete do svého HoloLens (1. generace) nainstalovat pomocí Windows Device Recovery Tool. Před použitím tohoto nástroje se podívejte, jestli se problém vyřeší restartováním nebo resetováním HoloLens počítače.

Proces obnovení může chvíli trvat. Po jeho provedení se nainstaluje nejnovější verze Windows Holographic.

Pokud chcete nástroj použít, potřebujete počítač se systémem Windows 10 nebo novějším s alespoň 4 GB volného místa v úložišti. Tento nástroj nelze spustit na virtuálním počítači.

### <a name="recover-your-hololens"></a>Obnovení HoloLens

1. Stáhněte a [nainstalujte Windows Device Recovery Do](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) počítače.
1. Připojení HoloLens k počítači připojte kabel Micro USB, který jste HoloLens.
1. Otevřete nástroj Windows Device Recovery a postupujte podle pokynů.

Pokud se HoloLens (1. generace) automaticky, vyberte Moje zařízení **se nezjistěno.** Pak postupujte podle pokynů a předejte zařízení do režimu obnovení.

### <a name="manual-flashing-mode"></a>Režim ručního blikajícího režimu

Pokud se vaše zařízení nezjme, postupujte podle těchto kroků a předejte ho do blikajícího režimu:

1. Odpojte zařízení od jakéhokoli zdroje napájení.
1. Pokud je zařízení vypnuté, podržte **stisknuté** tlačítko napájení, dokud se úplně nevypíná.
2. Podržte **tlačítko pro** zvýšení hlasitosti a krátce klepněte na tlačítko **napájení.** Zařízení by se mělo spustit a zobrazit pouze prostřední led diodu.
3. Připojte zařízení k počítači.
4. Otevřete nástroj Windows Device Recovery.
5. Vyberte **Moje zařízení se nezjtekuje** a potom **HoloLens**. 
6. Podle pokynů obnovte zařízení.
