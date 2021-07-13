---
title: Restartování, resetování nebo obnovení HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: jak použít pokročilého průvodce obnovením k blikání obrázku na HoloLens 2.
keywords: postupy, restartování, resetování, obnovení, vynucené resetování, tiché resetování, cyklus napájení, HoloLens, vypnutí, oblouk, pokročilý průvodce obnovením
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635938"
---
# <a name="restart-reset-or-recover-hololens-2"></a>restartování, resetování nebo obnovení HoloLens 2

>[!IMPORTANT]
> Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné. [Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.

použijte [nabíječku a kabel typu USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) , který byl dodán s HoloLens 2, jako je to nejlepší způsob, jak zařízení účtovat. Nabíječka dodá 18W výkonu (9V v 2A). když použijete dodanou nabíječku zdí, zařízení HoloLens 2 můžou baterii navýšit na plnou dobu během méně než 65 minut, když je zařízení v pohotovostním režimu. Pokud tato příslušenství nejsou k dispozici, zajistěte, aby nabíječka, která je k dispozici, mohla podporovat aspoň 15W napájení.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k navýšení kapacity zařízení přes USB, což je pomalé.

Pokud je zařízení správně spuštěno a běží, existují tři způsoby, jak ověřit úroveň nabití baterie:

- z hlavní nabídky uživatelského rozhraní HoloLens zařízení.
- Podívejte se, že indikátor LED blízko tlačítka napájení (pro poplatek 40 – Percent) by se měl zobrazit aspoň dva Solid diody LED.
    - Když se zařízení účtuje, indikátory baterie až do indikace aktuální úrovně zpoplatnění.  Poslední světlo zmizí a odznačí aktivní zpoplatnění.
    - když je vaše HoloLens zapnutá, indikátor baterie zobrazí úroveň baterie v pěti přírůstcích.
    - Pokud je zapnutá jenom jedna z pěti světel, úroveň baterie je nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, bude se krátce rozsvítit v jednom světle a pak se vrátí.
- na hostitelském počítači otevřete **průzkumníka souborů** a hledejte zařízení HoloLens 2 na levé straně **tohoto počítače**. Pravým tlačítkem myši klikněte na zařízení a vyberte **vlastnosti**. V dialogovém okně se zobrazí úroveň nabití baterie.

   ![obrazovka vlastností HoloLens 2 zobrazuje úroveň změny baterie](images/ResetRecovery2.png)

Pokud se zařízení nedá spustit do nabídky po spuštění, poznamenejte si vzhled INDIKÁTORu a výčet zařízení na hostitelském počítači. Pak postupujte podle pokynů [Průvodce odstraňováním potíží](hololens-troubleshooting.md). Pokud se stav zařízení neshoduje s žádným ze stavů uvedených v Průvodci odstraňováním potíží, proveďte [postupnou operaci resetování](hololens-recovery.md#hard-reset-procedure) u zařízení připojeného k napájení, ne do hostitelského počítače. Počkejte alespoň jednu hodinu, než se zařízení doúčtuje.

## <a name="reset-the-device"></a>Resetování zařízení

Za určitých okolností může být nutné ručně resetovat zařízení bez použití uživatelského rozhraní softwaru.

### <a name="standard-procedure"></a>Standardní postup

1. Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.

2. Stiskněte a držte tlačítko **napájení** po dobu 15 sekund. Všechny diody LED by měly být vypnuté.

3. Počkejte 2-3 sekund a potom stiskněte tlačítko **napájení** . Indikátory LED, které se blíží tlačítku napájení, se budou rozsvítit a zařízení se začne spouštět.

4. Připojení zařízení na hostitelském počítači a pak otevřete Správce zařízení. (pro Windows 10 stiskněte klávesu **Windows** a pak klíč **X** a potom vyberte **Správce zařízení**.) ujistěte se, že se zařízení správně zobrazuje tak, jak *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:

   ![MicrosoftHoloLensRecovery 2 devive manager HoloLens](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Postup pevného resetu

Pokud standardní procedura resetování nefungovala, použijte postup pevného resetování:

1. Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.

2. U 15 sekund podržíte tlačítka **hlasitosti dolů**  +   . Zařízení se automaticky restartuje.

4. Připojení zařízení na hostitelský počítač.


5. otevřete Správce zařízení (pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a potom vyberte **Správce zařízení**). ujistěte se, že se zařízení správně zobrazuje tak, jak *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 MicrosoftHoloLensRecovery zařízení správce 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Vyčistit a znovu zablikat zařízení

v mimořádných situacích možná budete muset "vyčistit-bliknutí" HoloLens 2. Upozorňujeme, že příkaz vyčistit-reflash se neočekává vlivem na následující problémy:
- [Zobrazit sjednocení barev](hololens2-display.md)
- Spouštění se zvukem, ale bez zobrazení výstupu
- [vzor LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Přehřívání](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Selhání operačního systému (které se liší od selhání aplikace)

Existují dva způsoby, jak zařízení znovu zablikat. pro obojí musíte nejdřív [nainstalovat rozšířeného průvodce obnovením z Windows storu](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Pokud vaše zařízení budete znovu zablikat, budou smazána všechna vaše osobní data, aplikace a nastavení, včetně informací o resetování čipu TPM.

Ve výchozím nastavení je průvodce pokročilým obnovením nastaven na stažení nejnovějšího buildu pro vydání funkce. Přečtěte si zde [poznámky k verzi](hololens-release-notes.md#) , kde najdete další informace o nejnovější verzi funkce. pokud chcete získat nejnovější HoloLens 2 úplný balíček Flash Update (FFU), abyste mohli svoje zařízení znovu zablikat prostřednictvím pokročilého průvodce obnovením, [klikněte sem a stáhněte si nejnovější měsíční obrázek HoloLens 2](https://aka.ms/hololens2download). Tato verze je nejnovější všeobecně dostupná sestavení.

než začnete s postupem přeblesku, ujistěte se, že je aplikace nainstalovaná a spuštěná na počítači s Windows 10 a připravená k detekci zařízení. také se ujistěte, že se HoloLens účtuje minimálně 40%.

![snímek obrazovky HoloLens 2 pro vyčištění paměti](images/ARC1.png)

### <a name="normal-procedure"></a>Běžný postup

1. když je zařízení HoloLens spuštěné, připojte ho k počítači Windows 10, kde jste předtím otevřeli rozšířenou aplikaci pro obnovení.
 
   Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:

   ![úvodní obrazovka HoloLens 2 pro vyčištění](images/ARC2.png)

3. vyberte zařízení HoloLens 2 v rozšířeném uživatelském rozhraní aplikace Companion pro obnovení a podle pokynů dokončete znovu blesk.

### <a name="manual-procedure"></a>Ruční procedura

pokud se HoloLens 2 nespustila správně nebo pokud průvodce pokročilým obnovením nemůže zařízení rozpoznat, bude pravděpodobně nutné toto zařízení umístit do režimu obnovení:

1. Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.

2. Stiskněte a držte tlačítko **napájení** po dobu 15 sekund. Všechny diody LED by se měly vypnout.

3. Při stisknutí tlačítka **hlasitosti** stiskněte a uvolněte tlačítko **napájení** a spusťte zařízení. Počkejte 15 sekund a pak uvolněte tlačítko **hlasitosti** . Rozsvítí se jenom střední LED z pěti diod LED.

4. Připojení zařízení na hostitelský počítač a otevřete Správce zařízení. (pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a potom vyberte **Správce zařízení**.) ujistěte se, že se zařízení správně zobrazuje tak, jak Microsoft HoloLens, jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:

   ![HoloLens 2 – vyčistit obrazovku](images/ARC2.png)

6. vyberte zařízení HoloLens 2 v uživatelském rozhraní pomocníka pro zotavení po obnovení a podle pokynů dokončete znovu blesk.

## <a name="troubleshoot-advanced-recovery-companion"></a>Poradce při potížích s pokročilým obnovením

1. Před pokusem o spuštění aplikace Flash se ujistěte, že se na zařízení účtuje 40% nebo víc.

2. Ověřte, že je zařízení odemknuté.

1. Ověřte, že je zařízení zapojené přímo do hostitelského počítače, ne z rozbočovače.

1. pokud se zařízení nezobrazuje jako zařízení pro obnovení HoloLens/HoloLens v části ovladače Universal Serial Bus, zaškrtněte:
    1. **Porty** jako zařízení s rozhraním Qualcomm HS – USB
    1.   **Jiná zařízení**, jako QUSB_BULK zařízení – v hostitelském počítači chybí ovladače potřebné k detekci HoloLens. klikněte pravým tlačítkem a vyberte aktualizovat ovladač a vyhledejte ovladače online nebo [zaškrtněte volitelné aktualizace v nastaveních web Windows Update](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Po stažení ovladače by měl být oblouk schopný ho detekovat.
 
1. Pokud ARC zařízení nerozpozná, ujistěte se, že se k němu můžete připojit pomocí Průzkumníka souborů na svém počítači. Pokud nemůžete;

    1.  Je možné, že vaše zařízení může mít zásady USB, které toto připojení zakáže. V takovém případě zkuste použít [režim ručního blikání](hololens-recovery.md#manual-procedure).
    2.  Pokud neexistují žádné zásady, zkuste použít jiný kabel USB.

1. Ověřte, že zařízení nezobrazuje [vzorek LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Stáhnout oblouk bez použití App Storu

pokud it prostředí zabraňuje použití aplikace Windows storu nebo omezuje přístup k prodejnímu obchodu, může správce IT tuto aplikaci zpřístupnit prostřednictvím cesty nasazení offline.

 >[!NOTE]
 > - Správci IT můžou tuto aplikaci také distribuovat prostřednictvím System Center Configuration Manager (SCCM) nebo Intune.
 > - Tato příručka se zaměřuje na Advanced Recovery Companion, ale tento proces je možné použít i pro jiné "offline" aplikace.

Pokud chcete povolit cestu nasazení, postupujte takto:

1. Přejděte na [Microsoft Store pro firmy](https://businessstore.microsoft.com) a přihlaste se pomocí Azure Active Directory identity.

1. Přejděte na **Spravovat – Nastavení**. V části **Nákupní prostředí zapněte Zobrazit offline** **aplikace.**

1. Přejděte do **obchodu pro moji skupinu a** vyhledejte Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Změňte **Typ licence na** **_offline_ a vyberte *_* Spravovat.**

1. V **části Stáhnout balíček pro offline použití** vyberte druhé modré **tlačítko** Stáhnout. Ujistěte se, že je přípona *souboru .appxbundle*.

    - Pokud má stolní počítač v této fázi přístup k internetu, poklikejte na balíček a nainstalujte aplikaci.

    - Pokud cílový počítač nemá připojení k internetu, postupujte následovně:
       1. Vyberte nekódované licence a pak vyberte **Vygenerovat licenci.**
       2. V **části Požadované architektury** vyberte **Stáhnout.**
       3. Pomocí nástroje DISM použijte balíček se závislostí a licencí. Z příkazového řádku správce spusťte následující příkaz:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Číslo verze v tomto příkladu kódu nemusí odpovídat aktuálně dostupné verzi. Možná jste také zvolili jiné umístění pro stahování než v tomto příkladu. Proveďte všechny změny příkazu podle potřeby.

> [!TIP]
> Pokud máte v plánu použít Advanced Recovery Companion k offline instalaci FFU, může být užitečné stáhnout si flash image. [**Stáhněte si aktuální image pro HoloLens 2.**](https://aka.ms/hololens2download)


Další zdroje informací:
- [Distribuce offline aplikací](/microsoft-store/distribute-offline-apps) 
- [Možnosti příkazového řádku pro údržbu balíčku aplikace DISM (.appx nebo .appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
