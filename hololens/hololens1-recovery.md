---
title: restartování, resetování nebo obnovení HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: jak použít nástroj pro obnovení zařízení Windows k zablikání obrázku HoloLens 1. generace
keywords: postupy, restartování, resetování, obnovení, vynucené resetování, obnovitelné resetování, cyklus napájení, HoloLens, vypnutí, wdrt, nástroj pro obnovení zařízení systému windows
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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635224"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>restartování, resetování nebo obnovení HoloLens (1. generace)

pokud máte problémy s HoloLens, můžete zkusit restartovat nebo resetovat nebo dokonce zařízení znovu zablikat pomocí obnovení zařízení. Tento článek vás provede doporučenými kroky obnovení v uvedeném pořadí.

pokud hledáte HoloLens 2, přečtěte si téma obnovení [HoloLens 2](hololens-recovery.md), protože se tento proces liší.

> [!NOTE]
> tento článek se zaměřuje na HoloLens zařízení a software. pokud vaše hologramy nevypadají správně, přečtěte si téma **[aspekty HoloLens prostředí](hololens-environment-considerations.md)** , kde najdete informace o faktorech, které zlepšují kvalitu hologramů.

## <a name="restart"></a>Restartovat

### <a name="do-a-safe-restart-by-using-cortana"></a>Bezpečné restartování pomocí Cortana

nejbezpečnější způsob, jak restartovat HoloLens, je použití Cortana, což je obecně první věc, kterou můžete vyzkoušet v případě potíží s HoloLens.

> [!NOTE] 
> Cortana není k dispozici na všech zařízeních.
> - Cortana je k dispozici na všech HoloLensch (1. Gen) zařízeních. 
> - Cortana je k dispozici na zařízeních HoloLens 2 v sestavách před Windows Holograpic verze 2004 aktualizace.

1. Zapněte HoloLens.
1. Ujistěte se, že je uživatel přihlášený a že zařízení nečeká na jeho odemknutí heslem.
2. vyslovte "hey Cortana, restart" nebo "Hey Cortana, restarter."
3. Cortana odpoví a zobrazí se výzva k potvrzení. Počkejte, až se zvuk dohraje, a pak řekněte "Ano". Zařízení se restartuje.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>K bezpečnému restartování použijte tlačítko napájení.

Pokud stále nemůžete restartovat vaše zařízení, zkuste ho restartovat pomocí tlačítka **napájení** :

1. Stiskněte a držte tlačítko **napájení** po dobu 5 sekund. Po 1 sekundách se všechna pět diod LED rozsvítí a pak pomalu vypnou od sebe od zprava doleva. Po 5 sekundách dojde k vypnutí všech diod LED, což znamená úspěšné vypnutí.
      
   > [!IMPORTANT]
   > Zastaví stisknutí tlačítka ihned po vypnutí všech diod LED.
1. Počkejte 1 minutu na dokončení vypnutí. Vypnutí může stále probíhat i po vypnutí displeje.
2. Znovu zapněte zařízení stisknutím a podržením tlačítka **napájení** po dobu 1 sekundy.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>bezpečné restartování pomocí Windows portálu zařízení

> [!NOTE]
> pro tento proces musí být HoloLens nakonfigurovaný jako vývojářské zařízení. další informace najdete na [Windows portálu zařízení](/windows/mixed-reality/using-the-windows-device-portal).

pokud předchozí postup nefunguje, zkuste zařízení restartovat pomocí [portálu Windows zařízení](/windows/mixed-reality/using-the-windows-device-portal). V pravém horním rohu Najděte možnost pro restartování nebo vypnutí zařízení.

### <a name="do-an-unsafe-forced-restart"></a>Provedení nebezpečného vynuceného restartování

pokud předchozí metody nerestartoval váš HoloLens, vynuťte restart. Tato metoda je ekvivalentní k odebrání a přeinstalaci baterie. Je nebezpečný, protože může opustit vaše zařízení v poškozeném stavu. Pokud k tomu dojde, budete muset svůj HoloLens Flash.  

> [!WARNING]
> Toto je potenciálně škodlivá metoda a měla by se používat jenom v případě, že dříve citované metody nefungovaly.

1. Stiskněte a držte tlačítko **napájení** alespoň 10 sekund.
   - Tlačítko je v pořádku po dobu delší než 10 sekund.
   - Je bezpečné ignorovat aktivitu LED.
1. Uvolněte tlačítko a počkejte na 2-3 sekund.
1. Stiskněte a držte tlačítko **napájení** po dobu 1 sekundy.
1. Pokud stále máte problémy, stiskněte tlačítko **napájení** po dobu 4 sekund, dokud se všechny indikátory baterie nezobrazují, a obrazovka přestane zobrazovat hologramy. Počkejte 1 minutu a potom znovu stiskněte tlačítko **napájení** a zapněte zařízení.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>přejít zpět na předchozí verzi HoloLens (1. generace)

v některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. to můžete provést pomocí nástroje pro obnovení Windows zařízení a resetovat HoloLens na předchozí verzi.

> [!NOTE]
> Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.

chcete-li se vrátit k předchozí verzi HoloLens 1, postupujte podle následujících kroků:

1. ujistěte se, že nemáte k počítači připojené žádné telefony ani zařízení Windows.
1. na počítači stáhněte [nástroj Windows pro obnovení zařízení (WDRT)](https://support.microsoft.com/help/12379).
1. stáhněte si [balíček pro obnovení aktualizace pro HoloLens výročí](https://aka.ms/hololensrecovery).
1. Po dokončení stahování otevřete **Průzkumníka souborů**  >  . Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
1. Připojení své HoloLens k počítači pomocí kabelu mikrosběrnice USB, na který byl dodán. (i když používáte k připojení HoloLens jiné kabely, tato funkce funguje nejlépe.)
1. WDRT automaticky detekuje vaše HoloLens. vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte ruční výběr balíčku a zvolte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4. (Vyhledejte soubor s příponou. FFU.)
1. Vyberte **instalovat software** a postupujte podle pokynů.

> [!NOTE]
> pokud WDRT nezjistí váš HoloLens, zkuste restartovat počítač. pokud to nepomůže, vyberte **moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="reset-to-factory-settings"></a>Resetovat do továrního nastavení

> [!NOTE]
> Pro resetování baterie musí být vyplněna minimální sazba 40 až procent.

pokud má HoloLens stále problém, zkuste ho obnovit do stavu tovární nastavení. v tomto kroku se zachová verze Windows holografického softwaru, který je na něm nainstalovaný, a vrátí všechno ostatní k továrnímu nastavení.

>[!WARNING]
> Pokud resetujete zařízení, budou smazána všechna vaše osobní data, aplikace a nastavení, včetně informací o resetování čipu TPM. při obnovení se nainstaluje jenom nejnovější nainstalovaná verze Windows holografické. Budete muset znovu provést všechny kroky inicializace (kalibraci, připojit se k Wi-Fi, vytvořit uživatelský účet, stáhnout aplikace atd.).

1. otevřete aplikaci Nastavení a pak vyberte **aktualizovat**  >  **obnovení**.
1. Vyberte možnost **resetovat zařízení** a přečtěte si potvrzovací zprávu.
1. Potvrďte resetování. Zařízení se restartuje a zobrazí se sada rotujících ozubených kolečk a indikátor průběhu.
1. Počkejte přibližně 30 minut, než se tento proces dokončí. Až se zařízení dokončí, zařízení se restartuje do předpřipraveného prostředí.

## <a name="reinstall-the-operating-system"></a>Opětovná instalace operačního systému

pokud má zařízení stále problém po restartování a obnovení, můžete použít nástroj pro obnovení na počítači k přeinstalování HoloLens operační systém a firmware.  

data, která HoloLens potřebuje pro obnovení, se zabalí do úplné aktualizace Flash (FFU), která je podobná souboru. iso,. wim nebo. vhd. [Přečtěte si o formátech souborů obrázků FFU.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

nový operační systém můžete nainstalovat do HoloLens (1. generace) pomocí nástroje Windows pro obnovení zařízení. než tento nástroj použijete, přečtěte si článek o restartování nebo resetování HoloLens problém vyřeší.

Proces obnovení může chvíli trvat. až to bude hotové, nainstaluje se nejnovější verze Windows holografického softwaru.

chcete-li použít nástroj, potřebujete počítač se systémem Windows 10 nebo novějším s alespoň 4 GB volného místa v úložišti. Tento nástroj nemůžete spustit na virtuálním počítači.

### <a name="recover-your-hololens"></a>Obnovení HoloLens

1. stáhněte a nainstalujte [nástroj Windows recovery zařízení](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) do počítače.
1. Připojení HoloLens (1. generace) do vašeho počítače pomocí kabelu mikrosběrnice USB, který byl dodán s vaším HoloLens.
1. otevřete nástroj Windows recovery zařízení a postupujte podle pokynů.

pokud se nezjistí automaticky HoloLens (1. generace), vyberte **moje zařízení se nezjistilo**. Pak postupujte podle pokynů a vložte zařízení do režimu obnovení.

### <a name="manual-flashing-mode"></a>Režim ručního blikání

Pokud zařízení není zjištěné, postupujte podle těchto kroků a přepněte do režimu blikání:

1. Odpojte zařízení od libovolného zdroje napájení.
1. Pokud je zařízení zapnuté, stiskněte tlačítko **napájení** , dokud se úplně nevypne.
2. Podržte **tlačítko pro** zvýšení hlasitosti a krátce klepněte na tlačítko **napájení.** Zařízení by se mělo spustit a zobrazit pouze prostřední led diodu.
3. Připojte zařízení k počítači.
4. Otevřete nástroj Windows Device Recovery.
5. Vyberte **Moje zařízení se nezjme a** potom **HoloLens**. 
6. Podle pokynů obnovte zařízení.
