---
title: Restartování, resetování nebo obnovení HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Jak používat nástroj Windows Device Recovery Tool k flashování obrázku do HoloLens 1. generace
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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923512"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Restartování, resetování nebo obnovení HoloLens (1. generace)

Pokud dochází k problémům s HoloLens, můžete zkusit restartovat nebo resetovat zařízení nebo dokonce pomocí obnovení zařízení odkazovat. Tento článek vás provede doporučenými kroky obnovení v pořadí.

Pokud chcete obnovit HoloLens 2, podívejte se na obnovení [HoloLens 2,](hololens-recovery.md)protože se tento proces liší.

> [!NOTE]
> Tento článek se zaměřuje na zařízení a software HoloLens. Pokud vaše hologramy vypadají správně, najdete informace o faktorech, které zlepšují kvalitu hologramů, v části Aspekty prostředí **[HoloLens.](hololens-environment-considerations.md)**

## <a name="restart"></a>Restartovat

### <a name="do-a-safe-restart-by-using-cortana"></a>Bezpečné restartování pomocí Cortany

Nejbezpečnější způsob, jak restartovat HoloLens, je použití Cortany, což je obecně první věc, kterou byste si měli vyzkoušet, když nastane problém s HoloLens.

> [!NOTE] 
> Cortana není dostupná na všech zařízeních.
> - Cortana je dostupná na všech zařízeních HoloLens (1. generace). 
> - Cortana je na zařízeních HoloLens 2 dostupná na buildech před aktualizací Windows Holograpic verze 2004.

1. Zapněte HoloLens.
1. Ujistěte se, že je uživatel přihlášený a že zařízení nečeká na odemknutí hesla.
2. Řekněte "Ahoj Cortana, restartování" nebo "Ahoj Cortana, restartujte".
3. Cortana odpoví a vyzve vás k potvrzení. Počkejte, až se po otázce přehrá zvuk, a pak řekněte Ano. Zařízení se restartuje.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Bezpečné restartování pomocí tlačítka napájení

Pokud stále nemůžete zařízení restartovat, zkuste ho restartovat pomocí tlačítka **napájení:**

1. Stiskněte a podržte **tlačítko napájení** po dobu 5 sekund. Po 1 sekundě se všech pět LED diod rozzáří a pak postupně postupně jeden po druhém vypne zprava doleva. Po 5 sekundách budou všechny LED diody vypnuté, což značí úspěšné vypnutí.
      
   > [!IMPORTANT]
   > Okamžitě po vypnutí všech LED diod zastavte stisknutí tlačítka.
1. Počkejte 1 minutu, než se vypnutí dokončí. Vypnutí může stále probíhají, i když jsou displeje vypnuté.
2. Znovu zapněte zařízení stisknutím a podržením tlačítka **napájení** na 1 sekundu.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Proveďte bezpečné restartování pomocí Portál zařízení s Windows

> [!NOTE]
> Pro tento proces je třeba HoloLens nakonfigurovat jako vývojářské zařízení. Další informace najdete [na Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Pokud předchozí postup nefunguje, zkuste zařízení restartovat pomocí příkazu [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). V pravém horním rohu vyhledejte možnost restartování nebo vypnutí zařízení.

### <a name="do-an-unsafe-forced-restart"></a>Nebezpečné vynucené restartování

Pokud předchozí metody nerestartly HoloLens, vynutí restartování. Tato metoda je ekvivalentní k odebrání a opětovné instalaci baterie. Je to nebezpečné, protože by mohlo nechat zařízení v poškozeném stavu. Pokud k tomu dojde, budete muset holoLens blikat.  

> [!WARNING]
> Jedná se o potenciálně škodlivou metodu, která by se měla použít pouze v případě, že dříve citované metody nefungují.

1. Stiskněte a podržte **tlačítko** napájení alespoň 10 sekund.
   - Tlačítko můžete podržet déle než 10 sekund.
   - Každou aktivitu indikátoru LED můžete bezpečně ignorovat.
1. Uvolněte tlačítko a počkejte 2–3 sekundy.
1. Stiskněte a podržte **tlačítko** napájení po dobu 1 sekundy.
1. Pokud stále máte problémy,  stiskněte tlačítko napájení po dobu 4 sekund, dokud se všechny indikátory baterie neztlumí a obrazovka přestane zobrazovat hologramy. Počkejte 1 minutu a pak znovu stiskněte **tlačítko** napájení, aby se zařízení zapne.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Zpět na předchozí verzi – HoloLens (1. generace)

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. Můžete to provést pomocí nástroje pro obnovení zařízení ve Windows a resetovat HoloLens na starší verzi.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens 1, postupujte takto:

1. Ujistěte se, že nemáte k počítači připojené žádné telefony ani zařízení s Windows.
1. Na svém počítači stáhněte [nástroj WDRT (Windows Device Recovery Tool).](https://support.microsoft.com/help/12379)
1. Stáhněte [si balíček pro obnovení HoloLens Anniversary Update.](https://aka.ms/hololensrecovery)
1. Po dokončení stahování otevřete **Průzkumníka souborů Stažené**  >  **soubory.** Klikněte pravým tlačítkem na složku zip, kterou jste si právě stáhli, a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
1. Připojte HoloLens k počítači pomocí kabelu micro-USB, se který dodá. (I v případě, že k připojení HoloLens používáte jiné kabely, funguje to nejlépe.)
1. WDRT automaticky rozpozná holoLens. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr** balíčku a zvolte instalační soubor obsažený ve složce, kterou jste rozbalili v kroku 4. (Vyhledejte soubor s příponou .ffu.)
1. Vyberte **Nainstalovat software** a postupujte podle pokynů.

> [!NOTE]
> Pokud nástroj WDRT váš HoloLens nerozpozná, zkuste počítač restartovat. Pokud to nefunguje, vyberte **Moje zařízení** se nezjme, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="reset-to-factory-settings"></a>Obnovení továrního nastavení

> [!NOTE]
> Baterie potřebuje k resetování alespoň 40procentní poplatek.

Pokud má holoLens problém, zkuste ho resetovat do stavu továrního nastavení. Tento krok zachová verzi softwaru Windows Holographic, který je v ní nainstalovaný, a vrátí všechno ostatní do továrního nastavení.

>[!WARNING]
> Pokud zařízení resetujete, vymažou se všechny vaše osobní údaje, aplikace a nastavení včetně informací o resetování čipu TPM. Resetováním se nainstaluje jenom nejnovější nainstalovaná verze Windows Holographic. Budete muset znovu provést všechny inicializační kroky (nakalibrovat, připojit se k Wi-Fi, vytvořit uživatelský účet, stáhnout aplikace atd.).

1. Otevřete aplikaci Nastavení a pak vyberte **Aktualizovat**  >  **obnovení.**
1. Vyberte možnost **Resetovat** zařízení a přečtěte si potvrzovací zprávu.
1. Potvrďte resetování. Zařízení se restartuje a zobrazí se sada rotujícího ozubeného kola a indikátor průběhu.
1. Počkejte asi 30 minut, než se tento proces dokončí. Po dokončení se zařízení restartuje do prostředí, které je hotové.

## <a name="reinstall-the-operating-system"></a>Přeinstalujte operační systém.

Pokud má zařízení problém i po restartování a resetování, můžete k přeinstalaci operačního systému a firmwaru HoloLens použít nástroj pro obnovení v počítači.  

Data, která HoloLens potřebuje k resetování, jsou zabalená v úplné aktualizaci Flash Update (FFU), která se podobá souboru .iso, .wim nebo .vhd. [Přečtěte si o formátech souborů obrázků FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Nový operační systém můžete do HoloLens (1. generace) nainstalovat pomocí nástroje Windows Device Recovery Tool. Před použitím tohoto nástroje se podívejte, jestli restartování nebo resetování HoloLens tento problém vyřeší.

Proces obnovení může chvíli trvat. Až to bude hotové, nainstaluje se nejnovější verze softwaru Windows Holographic.

Pokud chcete nástroj používat, potřebujete počítač se systémem Windows 10 nebo novějším s alespoň 4 GB volného místa v úložišti. Tento nástroj nelze spustit na virtuálním počítači.

### <a name="recover-your-hololens"></a>Obnovení HoloLens

1. Stáhněte a nainstalujte do svého počítače nástroj Obnovení zařízení systému [Windows.](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
1. Připojte HoloLens (1. generace) k počítači pomocí kabelu Micro USB, který jste dodáli s holoLens.
1. Otevřete nástroj Windows Device Recovery Tool a postupujte podle pokynů.

Pokud se holoLens (1. generace) nezjistí automaticky, vyberte **Moje zařízení se nezjistě.** Pak postupujte podle pokynů a předejte zařízení do režimu obnovení.

### <a name="manual-flashing-mode"></a>Režim ručního blikajícího režimu

Pokud se vaše zařízení nezjme, postupujte podle těchto kroků a předejte ho do blikajícího režimu:

1. Odpojte zařízení od jakéhokoli zdroje napájení.
1. Pokud je zařízení vypnuté, podržte **stisknuté** tlačítko napájení, dokud se úplně nevypíná.
2. Podržte **tlačítko pro** zvýšení hlasitosti a krátce klepněte na tlačítko **napájení.** Zařízení by se mělo spustit a zobrazit pouze prostřední led diodu.
3. Připojte zařízení k počítači.
4. Otevřete Nástroj pro obnovení zařízení s Windows.
5. Vyberte **Moje zařízení se nezjtekuje** a pak **HoloLens**. 
6. Podle pokynů obnovte zařízení.
