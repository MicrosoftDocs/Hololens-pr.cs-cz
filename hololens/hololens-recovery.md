---
title: Restartování, resetování nebo obnovení HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Jak použít Advanced Recovery Companion k zobrazení flash obrázku HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
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
ms.openlocfilehash: 9547545fee4b1e0c8bacf258fa9bea081dec2445
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189711"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Restartování, resetování nebo obnovení HoloLens 2

>[!IMPORTANT]
> Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné. Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.

Použijte kabel [USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat. 18 W energie (9V při 2A) dosáhnou 18 W energie. Pokud je zařízení v pohotovostním režimu, HoloLens dodávají 2 zařízení naplno za méně než 65 minut. Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W energie.

> [!NOTE]
> Pokud je to možné, nepoužívejte počítač k nabílení zařízení přes USB, což je pomalé.

Pokud je zařízení správně spuštěné a spuštěné, existují tři způsoby, jak zkontrolovat úroveň baterie:

- V hlavní nabídce uživatelského rozhraní HoloLens zařízení.
- Led diodu si prohlédněte blízko tlačítka napájení (při 40procentní poplatek byste měli vidět alespoň dvě plné LED diody).
    - Když se zařízení nabíjí, indikátor baterie se rozsvítí, aby indikuje aktuální úroveň poplatku.  Poslední světlo postupně zeslábne a bude indikovat aktivní zpoplatnění.
    - Když je HoloLens, indikátor baterie zobrazí stav baterie v pěti přírůstcích.
    - Když je jen jedna z pěti světel rozsvícená, úroveň baterie je nižší než 20 procent.
    - Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, jedno světlo krátce blikne a pak vypadne.
- Na hostitelském počítači otevřete **Průzkumník souborů** a vyhledejte své zařízení HoloLens 2 na levé straně pod **položkou Tento počítač.** Klikněte pravým tlačítkem na zařízení a vyberte **Vlastnosti**. V dialogovém okně se zobrazí úroveň baterie.

   ![Obrazovka HoloLens 2 vlastností zobrazuje úroveň změny baterie.](images/ResetRecovery2.png)

Pokud se zařízení nemůže spustit do spouštěcí nabídky, všimněte si vzhledu indikátoru LED a výčtu zařízení na hostitelském počítači. Pak postupujte podle průvodce [odstraňováním potíží.](hololens-troubleshooting.md) Pokud stav zařízení neodpovídá žádnému stavu uvedenému v průvodci odstraňováním potíží, proveďte postup pevného resetování se zařízením připojeným k napájecímu zdroji, ne s hostitelským počítačem. [](hololens-recovery.md#hard-reset-procedure) Počkejte alespoň jednu hodinu, než se zařízení bude účtovat.

## <a name="reset-the-device"></a>Resetování zařízení

Za určitých okolností může být nutné zařízení resetovat ručně bez použití softwarového uživatelského rozhraní.

### <a name="standard-procedure"></a>Standardní postup

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

2. Stiskněte a podržte **tlačítko** napájení po dobu 15 sekund. Všechny LED diody by měly být vypnuté.

3. Počkejte 2–3 sekundy a pak krátce stiskněte **tlačítko napájení.** Led diody blízko tlačítka napájení se rozsvítí a zařízení se začne svítit.

4. Připojení zařízení na hostitelský počítač a pak otevřete Správce zařízení. (Například Windows 10 stiskněte klávesu **Windows,** pak **klávesu X** a pak **vyberte Správce zařízení**.) Ujistěte se, že se zařízení správně *Microsoft HoloLens,* jak je znázorněno na následujícím obrázku:

   ![HoloLens 2: MicrosoftHoloLensRecovery Devive Manager.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Postup pevného resetování

Pokud standardní postup resetování nefunguje, použijte tento postup:

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

2. Podržte **stisknutá**  +  **tlačítka** napájení po dobu 15 sekund. Zařízení se automaticky restartuje.

4. Připojení zařízení k hostitelskému počítači.


5. Otevřete Správce zařízení (Windows 10 stiskněte klávesu **Windows** a potom klávesu **X** a pak **vyberte Správce zařízení**). Ujistěte se, že se zařízení správně *Microsoft HoloLens,* jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 MicrosoftHoloLensRecovery device maanger 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Vyčištění zařízení před reflash

V mimořádných situacích možná budete muset "vyčistit flash" HoloLens 2. Upozorňujeme, že neočekává se, že čisté lomítko ovlivní následující problémy:
- [Jednotnost barev zobrazení](hololens2-display.md)
- Spouštění se zvukem, ale bez výstupu zobrazení
- [Vzor 1-3-5-LED](hololens2-setup.md#lights-to-indicate-problems)
- [Přehřátí](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Selhání operačního systému (která se liší od selhání aplikací)

Existují dva způsoby, jak zařízení odkazovat. V obou případech musíte nejdřív z úložiště úložiště Windows [Advanced Recovery Companion.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Pokud zařízení přemítáte, vymažou se všechny vaše osobní údaje, aplikace a nastavení včetně informací o resetování čipu TPM.

Ve výchozím nastavení je možnost Advanced Recovery Companion nastavená tak, [](hololens-release-notes.md#) aby stahuje nejnovější sestavení vydání funkcí. Tady si můžete přečíst poznámky k verzi, abyste se dozvěděli o nejnovější verzi funkcí. Pokud chcete získat nejnovější HoloLens 2 Full Flash Update (FFU) pro srovnání vašeho zařízení přes Advanced Recovery Companion, klikněte sem a stáhněte si nejnovější měsíční HoloLens [2 image](https://aka.ms/hololens2download). Tato verze je nejnovějším obecně dostupným buildem.

Před zahájením postupu zpětného lomítka se ujistěte, že je aplikace nainstalovaná a spuštěná na Windows 10 počítači a připravená k rozpoznání zařízení. Také se ujistěte, HoloLens vaše zařízení naúčtované minimálně na 40 %.

![HoloLens obrazovky se 2 čistými zpětnými lomítky.](images/ARC1.png)

### <a name="normal-procedure"></a>Normální postup

1. Když je HoloLens spuštěné, připojte ho k počítači Windows 10, na kterém jste předtím otevřeli doprovodnou aplikaci advanced recovery.
 
   Zařízení se automaticky detekuje a uživatelské rozhraní aplikace Advanced Recovery Companion spustí proces aktualizace:

   ![HoloLens 2 úvodní obrazovky čistého lomítka.](images/ARC2.png)

3. Vyberte zařízení HoloLens 2 v uživatelském rozhraní aplikace Advanced Recovery Companion a postupujte podle pokynů a dokončete lomítko.

### <a name="manual-procedure"></a>Ruční postup

Pokud se HoloLens 2 nespustí správně nebo pokud Advanced Recovery Companion zařízení nedokáže rozpoznat, možná budete muset zařízení přetát do režimu obnovení:

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

2. Stiskněte a podržte **tlačítko** napájení po dobu 15 sekund. Všechny LED diody by měly být vypnuté.

3. Při stisknutí **tlačítka pro zvýšení** hlasitosti stiskněte a uvolněte tlačítko **napájení,** aby se zařízení spouštěl. Počkejte 15 sekund a pak uvolněte **tlačítko pro zvýšení** hlasitosti. Rozsvítí se pouze prostřední led dioda pěti indikátorů LED.

4. Připojení zařízení na hostitelský počítač a otevřete Správce zařízení. (Windows 10 stiskněte klávesu **Windows,** pak **klávesu X** a pak **vyberte Správce zařízení**.) Ujistěte se, že se zařízení správně Microsoft HoloLens, jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Zařízení se automaticky detekuje a uživatelské rozhraní aplikace Advanced Recovery Companion spustí proces aktualizace:

   ![HoloLens 2 obrazovky čistého lomítka.](images/ARC2.png)

6. Vyberte zařízení HoloLens 2 v uživatelském rozhraní aplikace Advanced Recovery Companion a pak postupujte podle pokynů a dokončete lomítko.

## <a name="troubleshoot-advanced-recovery-companion"></a>Řešení potíží s Advanced Recovery Companion

1. Před pokusem o flash disk se ujistěte, že se zařízení účtuje na 40 % nebo více.

2. Zkontrolujte, že je zařízení odemčené.

1. Zkontrolujte, že je zařízení přímo připojené k hostitelskému počítači, a ne k rozbočovači.

1. Pokud se vaše zařízení nezobrazuje jako zařízení HoloLens/HoloLens Recovery v části Ovladače universal serial bus, zkontrolujte:
    1. **Porty** jako zařízení Qualcomm HS-USB
    1.   **Jiná zařízení**, jako QUSB_BULK zařízení – na hostitelském počítači chybí potřebné ovladače pro detekci HoloLens. Klikněte pravým tlačítkem a vyberte Update Driver (Aktualizovat ovladač) a vyhledejte ovladače online nebo zaškrtněte [políčko Optional Updates (Volitelné aktualizace) Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)(Nastavení aktualizace). Po stažení ovladače by ho měl být arc schopný rozpoznat.
 
1. Pokud ARC vaše zařízení nerozpozná, ujistěte se, že se k zařízení můžete připojit Průzkumník souborů počítači. Pokud nemůžete,

    1.  Je možné, že vaše zařízení má zásady USB, které toto připojení zaknuly. Pokud ano, zkuste [režim ručního blikajícího režimu](hololens-recovery.md#manual-procedure).
    2.  Pokud žádné zásady neexistují, zkuste jiný kabel USB.

1. Zkontrolujte, že vaše zařízení nemá vzor [1-3-5-LED.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Stažení ARC bez použití App Storu

Pokud IT prostředí brání použití aplikace Windows Storu nebo omezuje přístup k maloobchodnímu obchodu, správce IT může tuto aplikaci z dostupného offline nasazení.

 >[!NOTE]
 > - správci IT mohou tuto aplikaci také distribuovat prostřednictvím System Center Configuration Manager (SCCM) nebo intune.
 > - Tato příručka se zaměřuje na pokročilého Průvodce obnovením, ale tento postup je možné použít i pro jiné aplikace v režimu offline.

Pokud chcete povolit cestu nasazení, postupujte podle těchto kroků:

1. přejít na [Microsoft Store pro firmy](https://businessstore.microsoft.com) a přihlaste se pomocí Azure Active Directory identity.

1. přejít na **správa – Nastavení**. Zapnutí možnosti **Zobrazit offline aplikace** v rámci **nakupování**

1. Přejít na **skupinu nákup pro moji skupinu** a vyhledat [**_pokročilého Průvodce obnovením_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Změňte **typ licence** na **_offline_*_ a vyberte _* spravovat**.

1. V části **Stáhnout balíček pro použití v režimu offline** vyberte druhý modrý tlačítko pro **stažení** . Ujistěte se, že je přípona souboru *. appxbundle*.

    - V této fázi, pokud má stolní počítač přístup k Internetu, poklikejte na balíček pro instalaci aplikace.

    - Pokud cílový počítač nemá připojení k Internetu, použijte následující postup:
       1. Vyberte nekódované licence a pak vyberte **generovat licenci**.
       2. V části **požadovaná rozhraní** vyberte **Stáhnout**.
       3. Pomocí nástroje DISM nainstalujte balíček se závislostí a licencí. Z příkazového řádku správce spusťte následující příkaz:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Číslo verze v tomto příkladu kódu nemusí odpovídat aktuálně dostupné verzi. Možná jste si také vybrali jiné umístění pro stahování než v příkladu. V případě potřeby proveďte v příkazu jakékoli změny.

> [!TIP]
> Když plánujete použít pokročilého Průvodce obnovením pro instalaci FFU do offline režimu, může být užitečné stáhnout si image Flash. [**stáhněte si aktuální image pro HoloLens 2**](https://aka.ms/hololens2download).


Další zdroje informací:
- [Distribuce offline aplikací](/microsoft-store/distribute-offline-apps) 
- [Možnosti příkazového řádku pro údržbu balíčku aplikace DISM (. appx nebo. appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
