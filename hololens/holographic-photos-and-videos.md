---
title: Zachycení, záznam a sdílení fotek a videí hybridní reality
description: Naučte se zaznamenávat, zaznamenávat a prohlížet fotky a videa hybridní reality pomocí HoloLens zařízení hybridní reality. Zjistěte, jak sdílet prostřednictvím Miracast nebo shromážděných souborů.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032263"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Vytváření fotek a videí hybridní reality

HoloLens uživatelům prostředí pro kombinaci skutečného světa s digitálním světem.  Zachycení hybridní reality (MRC) umožňuje zachytit toto prostředí jako fotku nebo video nebo sdílet to, co vidíte s ostatními, v reálném čase.

Zachycení hybridní reality používá z pohledu první osoby, aby ostatní viděli hologramy podle toho, jak je vidíte. Z pohledu třetí osoby použijte [zobrazení spectator .](/windows/mixed-reality/spectator-view) Zobrazení Spectator je užitečné zejména pro ukázky.

Je sice zábavné sdílet videa mezi přáteli a kolegy, ale videa můžou také pomoct naučit ostatní uživatele používat aplikaci nebo komunikovat problémy s aplikacemi a prostředími.

> [!NOTE]
> Pokud nemůžete spustit prostředí pro zachytávání hybridní reality a vaše HoloLens je pracovní zařízení, ověřte si to u správce systému. Přístup k fotoaparátu je možné omezit prostřednictvím zásad společnosti.

## <a name="capture-a-mixed-reality-photo"></a>Zachycení fotky hybridní reality

Existuje několik způsobů, jak posout fotku hybridní reality na HoloLens. Můžete použít hardwarová tlačítka, hlas nebo nabídka Start.

### <a name="hardware-buttons-to-take-photos"></a>Hardwarová tlačítka pro posouní fotek

Pokud chcete pohotovou fotku aktuálního zobrazení, stiskněte současně tlačítka pro zvýšení a snížení hlasitosti.  Je to trochu jako HoloLens obrazovky snímku obrazovky nebo obrazovky tisku.

- [Umístění tlačítek na HoloLens 2](hololens2-hardware.md)
- [Umístění tlačítek v HoloLens (1. generace)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Když **podržíte** tlačítko **pro** zvýšení a snížení hlasitosti po dobu tří sekund, místo posouníte fotku, spustí se nahrávání videa. Nahrávání zastavíte tak, že  **současně klepnete** na tlačítka pro zvýšení i snížení hlasitosti.

### <a name="voice-commands-to-take-photos"></a>Hlasové příkazy pro posouní fotek

Na HoloLens 2 verze 2004 (a novější) řekněte: "Udělejte si obrázek".

V HoloLens (1. generace) nebo HoloLens 2 verze 1903 řekněme: "Na Cortana se vyfotíte."

### <a name="start-menu-to-take-photos"></a>nabídka Start posout fotografie

Pomocí gesta Start přejděte na **Start a** pak vyberte **ikonu Fotoaparát.**

Namiřte hlavičku směrem k tomu, [](hololens2-basic-usage.md#touch-holograms-near-you) co chcete zachytit, a pak klepnutím ve vzduchu pořizovat fotku. Můžete pokračovat v klepnutí ve vzduchu a pořizovat další fotky. Všechny fotografie, které pořidíte, se uloží do vašeho zařízení.

Znovu použijte gesto Start (Spustit) a zachyťte snímek fotek.  

## <a name="capture-a-mixed-reality-video"></a>Zachycení videa s hybridní realitou

Existuje několik způsobů, jak nahrát video hybridní reality na HoloLens. Můžete použít hardwarová tlačítka, hlas nebo nabídka Start.

### <a name="hardware-buttons-to-record-videos"></a>Hardwarová tlačítka pro záznam videí

Nejrychlejší způsob, jak nahrát video, je  stisknout  a podržet současně tlačítka pro zvýšení a snížení hlasitosti, dokud nezačne třísekunový odpočítávání. Pokud chcete nahrávání zastavit, klepněte současně na obě tlačítka.

> [!NOTE]
> Když současně rychle **stisknete** tlačítko pro zvýšení a snížení hlasitosti, posoute fotku, a ne nahráte video. 

### <a name="voice-to-record-videos"></a>Hlas pro záznam videí

Na HoloLens 2, verze 2004 (a novější), řekněme: "Spustit nahrávání". Pokud chcete nahrávání zastavit, řekněte "Stop recording" (Zastavit nahrávání).

V HoloLens (1. generace) nebo HoloLens 2, verze 1903, řekněme: "Hey Cortana, start recording". Pokud chcete nahrávání zastavit, řekněte "Say Cortana, stop recording".

### <a name="start-menu-to-record-videos"></a>nabídka Start k nahrávání videí

Pomocí gesta Start přejděte na **Start (Spustit)** a pak vyberte **ikonu Video.** Namiřte hlavičku směrem k tomu, [](hololens2-basic-usage.md#touch-holograms-near-you) co chcete zachytit, a pak klepnutím ve vzduchu začáte nahrávat. Bude k dispozici třísekunové odpočítávání a zahájí se nahrávání.

Pokud chcete nahrávání zastavit, použijte gesto Spustit a vyberte zvýrazněnou **ikonu Video.** Video se uloží do vašeho zařízení.

> [!NOTE]
> **Platí pouze HoloLens (1. generace)**  
> Nastavení [Aktualizace Windows 10 z října 2018](/windows/mixed-reality/release-notes-october-2018) chování gesta Start a Windows při spuštění HoloLens (1. generace). Před aktualizací zastaví tlačítko Windows nebo Spustit záznam videa. Po aktualizaci ale tlačítko Spustit gesto nebo Windows otevře nabídku **Start** (nebo nabídku rychlých akcí, pokud jste v imerzivní aplikaci), ze které můžete vybrat zvýrazněnou ikonu videa a ukončit tak nahrávání.  

## <a name="share-what-you-see-in-real-time"></a>Sdílení toho, co vidíte v reálném čase

To, co vidíte ve službě HoloLens, můžete sdílet s přáteli a kolegy v reálném čase. K dispozici je několik metod:

1. Připojení k Miracast s podporou připojení zařízení nebo adaptéru ke sledování na tv.
1. Použití [Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal) ke sledování na počítači
1. Ke sledování [Microsoft HoloLens počítači můžete použít](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) doprovodnou aplikaci.
1. Nasazení aplikace [Microsoft Dynamics 365 Remote Assist,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) která umožňuje pracovníkům front-line streamovat to, co vidí, vzdálenému odborníkovi. Vzdálený odborník pak může pracovníka front-line vést verbálně nebo anotací ve svém světě.

> [!NOTE]
> Sdílení toho, co vidíte prostřednictvím Windows Portál zařízení nebo Microsoft HoloLens aplikace, vyžaduje, aby HoloLens byla v režimu [pro vývojáře.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Streamování videa s Miracast

Pomocí gesta Start přejděte na **Start a** pak vyberte **ikonu Připojení** startu. V seznamu, který se zobrazí, vyberte zařízení nebo Miracast s podporou připojení, ke kterému se chcete připojit.

Sdílení zastavíte tak, že použijete gesto Spustit a vyberete zvýrazněnou **Připojení** ikonu. Protože jste streamování měli, nic se do vašeho zařízení nebude ukládat.

> [!NOTE]
> Miracast (1. generace) byla na HoloLens (1. generace) povolená podpora od [Aktualizace Windows 10 z října 2018](/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Video v reálném čase s Windows Portál zařízení

Protože sdílení přes Windows Portál zařízení vyžaduje, aby byl na webu HoloLens povolený vývojářský režim, nastavte vývojářský režim podle pokynů v naší dokumentaci pro vývojáře a přejděte [Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens doprovodné aplikace

Protože sdílení prostřednictvím doprovodné Microsoft HoloLens aplikace vyžaduje, aby byl ve službě HoloLens povolený vývojářský režim, nastavte režim pro vývojáře podle pokynů v naší dokumentaci [pro vývojáře.](/windows/mixed-reality/using-the-windows-device-portal) Pak si stáhněte [Microsoft HoloLens aplikaci a](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) podle pokynů v aplikaci se připojte ke svému HoloLens.

Jakmile je aplikace nastavená s vaší HoloLens, vyberte možnost **Živý stream** z hlavní nabídky aplikace.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Zobrazení fotek a videí hybridní reality

Fotky a videa hybridní reality se ukládají do fotoaparátu v zařízení. Obsah této složky ve vašem počítači můžete procházet HoloLens aplikací Průzkumník souborů (přejděte na Obrázky > **fotoaparátu).**

Fotky a videa hybridní reality si také můžete prohlédnout v aplikaci Photos, která je předem nainstalovaná na HoloLens. Pokud chcete připnout fotku ve svém světě, vyberte ji v aplikaci Fotky a zvolte **Umístit ve smíšeném světě.** Po umístění fotky po celém světě ji můžete přesunout.

Pokud chcete zobrazit a/nebo uložit fotky a videa hybridní reality na počítači připojeném k HoloLens, můžete použít [Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) nebo virtuální počítač Průzkumník souborů [prostřednictvím MTP.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Použití Průzkumník souborů k získání obrázků, videí a souborů

Podobně jako u jiných mobilních zařízení připojte HoloLens k počítači, aby se Průzkumník souborů pro přístup k knihovnám HoloLens (fotky, videa, dokumenty) pro snadný přenos. Tato metoda se snadno používá a nevyžaduje použití portálu zařízení ani Wi-Fi.

1. Odemkněte zařízení.
1. Připojení zařízení k počítači přes USB.
1. Průzkumník souborů by se na počítači mělo otevřít.
1. Přejděte na: \\ *Yourhololensname* počítače \Internal Storage\Pictures\Camera Roll
1. Do počítače zkopírujte všechny soubory, které potřebujete.

Tipy:
- Pokud žádné soubory nevidíte, ujistěte se, že se přihlásíte ke svému HoloLens přístup k vašim datům.
- Další soubory v jiných složkách, například diagnostické soubory, můžete získat [ze](hololens-diagnostic-logs.md#offline-diagnostics) složky Dokumenty.
- V Průzkumník souborů počítači můžete vybrat Vlastnosti zařízení a zobrazit číslo verze operačního systému Windows Holographic (verze firmwaru), sériové číslo zařízení Windows procento baterie.
- Pokud vaše organizace k zakázání připojení [nebo připojení AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) použila MDM, pak se k vašemu zařízení nebude možné připojit.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Sdílení fotek a videí hybridní reality

Před Windows [Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)se po zachycení fotky nebo videa hybridní reality zobrazí náhled. Výběrem **ikony** Sdílet nad náhledem zobrazte asistenta sdílení. Odtud můžete vybrat koncový bod, ke kterému chcete tuto fotku nebo video sdílet.

V Windows Holographic verze 21H1 se po pořízení fotky nebo videa hybridní reality zobrazí náhled. Výběrem **ikony** Sdílet nad náhledem zobrazte asistenta sdílení. Odtud můžete vybrat koncový bod (Mail, OneDrive atd.), se kterým chcete tuto fotku nebo video sdílet. Můžete také povolit sdílení HoloLens zařízeními v okolí tak, že Nastavení **-> Systém -> Sdílená prostředí.** Další podrobnosti najdete v tématu [Sdílení věcí s blízkými zařízeními v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> Můžete také sdílet fotky a videa hybridní reality z OneDrive tím, že automaticky nahrajete fotky a videa hybridní reality. Otevřete aplikaci OneDrive na HoloLens a přihlaste se pomocí **[osobního účet Microsoft](https://account.microsoft.com)**, pokud jste to ještě neudělali. Vyberte **ikonu Nastavení** a zvolte **Nahrání fotoaparátu.** Zapněte nahrávání z fotoaparátu. Fotky a videa hybridní reality se teď budou nahrávat do OneDrive při každém spuštění aplikace na HoloLens.

> [!NOTE]
> Nahrávání fotoaparátu v aplikaci OneDrive jenom v případě, že jste přihlášení OneDrive pomocí osobního účet Microsoft. Pokud nastavíte HoloLens pracovním nebo školním účtem, můžete přidat osobní účet účet Microsoft aplikaci OneDrive tuto funkci povolit.

## <a name="limitations-of-mixed-reality-capture"></a>Omezení zachycení hybridní reality

- Při použití zachytávání hybridní reality se frekvence snímků HoloLens na 30 Hz.
- Rozlišení fotek a videí se může omezit, pokud ji už používá jiná aplikace, při živém streamování nebo při nízkém množství systémových prostředků.

### <a name="maximum-recording-length"></a>Maximální délka záznamu

Na HoloLens 2 zařízeních před Windows Holographic verze 20H2 byla videa zaznamenaná v zařízení omezena na maximální délku pěti minut.

Z důvodu zpětné vazby od zákazníků jsme zvýšili délku záznamu zachytávání [hybridní reality.](holographic-photos-and-videos.md) Zachytávání hybridní reality už nebude ve výchozím nastavení omezené na 5 minut, ale místo toho vypočítá maximální délku záznamu na základě dostupného místa na disku. Zařízení odhadne maximální dobu trvání záznamu videa na základě dostupného místa na disku až do 80 % celkového místa na disku.

> [!NOTE]
> V HoloLens se použije výchozí délka záznamu videa (5 minut), pokud dojde k jedné z následujících akcí:
> - Odhadovaná maximální doba trvání záznamu je menší než výchozích 5 minut.
> - Dostupné místo na disku je méně než 20 % celkového místa na disku.

## <a name="default-file-format-and-resolution"></a>Výchozí formát a rozlišení souboru

### <a name="default-photo-format-and-resolution"></a>Výchozí formát a rozlišení fotografie

|  Zařízení  |  Formát  |  Linka  |  Řešení  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. generace) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408 × 792 px |

### <a name="recorded-video-format-and-resolution"></a>Formát a rozlišení zaznamenaného videa

| Zařízení | Formát | Linka | Řešení | Rychlost | Zvuk |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz Stereo |
| HoloLens (1. generace) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216 × 684 px | 24fps | 48kHz Stereo |
