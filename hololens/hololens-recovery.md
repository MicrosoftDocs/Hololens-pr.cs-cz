---
title: Restartování, resetování nebo obnovení HoloLens 2
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Jak použít Advanced Recovery Companion k zobrazení flash obrázku HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: v-beehanson
ms.date: 10/15/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f8969d018059a3b38d2b3001f8bc983b72d58c7
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151652"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Restartování, resetování nebo obnovení HoloLens 2

>[!IMPORTANT]
> Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné. Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.

Použijte kabel [USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) který se dodá s HoloLens 2, protože to je nejlepší způsob, jak zařízení naúčtovat. 18 W energie (9V při 2A) dosáhnou 18 W energie. Pokud je zařízení v pohotovostním režimu, HoloLens 2 zařízení naplno naplno za méně než 65 minut. Pokud tyto příslušenství není k dispozici, ujistěte se, že dostupné příslušenství podporuje alespoň 15 W energie.

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

Pokud se zařízení nemůže spustit do spouštěcí nabídky, všimněte si vzhledu indikátoru LED a výčtu zařízení na hostitelském počítači. Pak postupujte podle průvodce [odstraňováním potíží.](hololens-troubleshooting.md) Pokud stav zařízení neodpovídá žádnému stavu uvedenému v průvodci odstraňováním potíží, proveďte postup pevného restartování se zařízením připojeným k napájení, ne s hostitelským počítačem. [](hololens-recovery.md#hard-restart-procedure) Počkejte alespoň jednu hodinu, než se zařízení bude účtovat.

> [!NOTE]
> Začáteč tím, že definujeme pojmy.\
> "Restart" jednoduše znamená vypnout a zapnout zařízení.\
> "Resetovat" znamená obnovit zařízení do výchozího nastavení Nastavení uživatelského rozhraní a znovu nainstalovat aktuální image.\
> "Odkazovat" znamená, že zařízení je připojené k počítači a nainstaluje se nový obrázek (volitelně jiný).

## <a name="restart-the-device"></a>Restartujte zařízení.

Za určitých okolností může být nutné zařízení restartovat ručně bez použití softwarového uživatelského rozhraní. To vám může pomoct vyřešit váš problém, aniž byste museli zařízení resetovat nebo reflashovat.

### <a name="standard-restart-procedure"></a>Standardní postup restartování

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

2. Stiskněte a podržte **tlačítko** napájení po dobu 15 sekund. Všechny LED diody by měly být vypnuté.

3. Počkejte 2–3 sekundy a pak krátce stiskněte **tlačítko napájení.** Led diody blízko tlačítka napájení se rozsvítí a zařízení se začne svítit.

4. Připojení zařízení k hostitelskému počítači a pak otevřete Správce zařízení. (Například Windows 10 stiskněte klávesu **Windows,** pak klávesu **X** a pak **vyberte Správce zařízení**.) Ujistěte se, že se zařízení správně *Microsoft HoloLens,* jak je znázorněno na následujícím obrázku:

   ![HoloLens 2: Správce zařízení MicrosoftHoloLensRecovery.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-restart-procedure"></a>Postup pevného restartování

Pokud standardní postup resetování nefunguje, použijte postup pevného restartování:

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

1. Podržte **stisknutá**  +  **tlačítka** napájení po dobu 15 sekund. Zařízení se automaticky restartuje.

1. Připojení zařízení k hostitelskému počítači.

1. Otevřete Správce zařízení (Windows 10 stiskněte klávesu **Windows** a potom klávesu **X** a pak **vyberte Správce zařízení**). Ujistěte se, že se zařízení správně *Microsoft HoloLens,* jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 Správce zařízení MicrosoftHoloLensRecovery 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="reset-the-device"></a>Resetování zařízení

Zařízení můžete resetovat přímo z náhlavní soupravy. Vyberte **Nastavení** a pak vyberte **Aktualizovat & Security > Resetovat & obnovení > Resetovat toto zařízení.**

   ![HoloLens náhlavní soupravy resetujte.](images/headset-reset-recovery.png)

Při resetování tímto způsobem se odstraní všechny uživatelské účty a vymažou se všechna data.

## <a name="clean-reflash-the-device"></a>Vyčištění zařízení před reflash

V mimořádných situacích možná budete muset "vyčistit blesk" HoloLens 2. Upozorňujeme, že neočekává se, že čisté lomítko ovlivní následující problémy:

- [Jednotnost barev zobrazení](hololens2-display.md)
- Spouštění se zvukem, ale bez výstupu zobrazení
- [Vzor 1-3-5-LED](hololens2-setup.md#lights-to-indicate-problems)
- [Přehřátí](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Selhání operačního systému (která se liší od selhání aplikací)

Existují dva způsoby, jak zařízení odkazovat. V obou případech musíte nejdřív z úložiště úložiště Windows [Advanced Recovery Companion.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Pokud zařízení přemítáte, vymažou se všechny vaše osobní údaje, aplikace a nastavení včetně informací o resetování čipu TPM.

Ve výchozím nastavení je možnost Advanced Recovery Companion nastavená tak, aby stáhla nejnovější sestavení vydání funkce. Další informace o nejnovější verzi funkcí najdete v [poznámkách k verzi HoloLens 2.](hololens-release-notes.md) Pokud chcete získat nejnovější HoloLens 2 Full Flash Update (FFU) pro srovnání vašeho zařízení prostřednictvím Advanced Recovery Companion, stáhněte si nejnovější měsíční HoloLens 2 image: [https://aka.ms/hololens2download](https://aka.ms/hololens2download) . Tato verze je nejnovějším obecně dostupným buildem.

Před zahájením postupu zpětného lomítka se ujistěte, že je aplikace nainstalovaná a spuštěná na počítači Windows 10 počítači a připravená k rozpoznání zařízení. Také se ujistěte, HoloLens účtují minimálně 40 %.

![HoloLens obrazovky se 2 čistými zpětnými lomítky.](images/ARC1.png)

### <a name="normal-flashing-procedure"></a>Normální blikající postup

1. Zatímco je HoloLens spuštěné, připojte ho k počítači Windows 10, na kterém jste předtím otevřeli doprovodnou aplikaci advanced recovery.

   Zařízení se automaticky detekuje a uživatelské rozhraní aplikace Advanced Recovery Companion spustí proces aktualizace:

   ![HoloLens úvodní obrazovku 2 čistého lomítka.](images/ARC2.png)

1. Vyberte zařízení HoloLens 2 v uživatelském rozhraní aplikace Advanced Recovery Companion a postupujte podle pokynů a dokončete lomítko.

### <a name="manual-flashing-mode-procedure"></a>Postup v režimu ručního blikajícího režimu

Zařízení možná budete muset přetát do režimu obnovení v případě, že:

- Název HoloLens 2 se nespustí správně.
- Advanced Recovery Companion nemůže zjistit zařízení.
- Už nevíte heslo nebo PIN kód pro zařízení, které má jenom jednoho uživatele.

1. Odpojte kabel typu C a odpojte zařízení od napájení nebo hostitelského počítače.

2. Stiskněte a podržte **tlačítko** napájení po dobu 15 sekund. Všechny LED diody by měly být vypnuté.

3. Při stisknutí **tlačítka pro zvýšení** hlasitosti stiskněte a uvolněte tlačítko **napájení,** aby se zařízení spouštěl. Počkejte 15 sekund a pak uvolněte **tlačítko pro zvýšení** hlasitosti. Rozsvítí se pouze prostřední led dioda pěti indikátorů LED.

4. Připojení zařízení k hostitelskému počítači a otevřete Správce zařízení. (Windows 10 stiskněte klávesu **Windows,** pak **klávesu X** a pak **vyberte Správce zařízení**.) Ujistěte se, že se zařízení správně Microsoft HoloLens, jak je znázorněno na následujícím obrázku:

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Zařízení se automaticky detekuje a uživatelské rozhraní aplikace Advanced Recovery Companion spustí proces aktualizace:

   ![HoloLens 2 obrazovky čistého lomítka.](images/ARC2.png)

6. Vyberte zařízení HoloLens 2 v uživatelském rozhraní aplikace Advanced Recovery Companion a pak postupujte podle pokynů a dokončete lomítko.

## <a name="troubleshoot-advanced-recovery-companion"></a>Řešení potíží s Advanced Recovery Companion

1. Před pokusem o flash disk se ujistěte, že se zařízení účtuje na 40 % nebo více.

1. Zkontrolujte, že je zařízení odemčené.

1. Ověřte, že je zařízení zapojené přímo do hostitelského počítače, ne z rozbočovače.

1. pokud se zařízení nezobrazuje jako zařízení pro obnovení HoloLens/HoloLens v části ovladače Universal Serial Bus, zaškrtněte:
    1. **Porty** jako zařízení s rozhraním Qualcomm HS – USB
    1. **Jiná zařízení**, jako QUSB_BULK zařízení – v hostitelském počítači chybí ovladače potřebné k detekci HoloLens. klikněte pravým tlačítkem a vyberte aktualizovat ovladač a vyhledejte ovladače online nebo [zaškrtněte volitelné aktualizace v nastaveních web Windows Update](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Po stažení ovladače by měl být oblouk schopný ho detekovat.

1. Pokud ARC zařízení nerozpozná, ujistěte se, že se k němu můžete připojit pomocí Průzkumníka souborů na svém počítači. Pokud nemůžete;

    1. Je možné, že vaše zařízení může mít zásady USB, které toto připojení zakáže. V takovém případě zkuste použít [režim ručního blikání](hololens-recovery.md#manual-flashing-mode-procedure).
    2. Pokud neexistují žádné zásady, zkuste použít jiný kabel USB.

1. Ověřte, že zařízení nezobrazuje [vzorek LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Stáhnout oblouk bez použití App Storu

pokud it prostředí zabraňuje použití aplikace Windows storu nebo omezuje přístup k prodejnímu obchodu, může správce IT tuto aplikaci zpřístupnit prostřednictvím cesty nasazení offline.

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
