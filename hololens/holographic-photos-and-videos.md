---
title: Zachycení, záznam a sdílení fotek a videí hybridní reality
description: Naučte se zaznamenávat, zaznamenávat a prohlížet fotky a videa hybridní reality pomocí zařízení hybridní reality HoloLens. Zjistěte, jak sdílet přes Miracast nebo shromážděné soubory.
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
ms.openlocfilehash: 178dff5d8a30fdd9c5012e2d14f5d4683d6cc23e
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377551"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Vytváření fotek a videí hybridní reality

HoloLens poskytuje uživatelům prostředí pro kombinaci skutečného světa s digitálním světem.  Zachycení hybridní reality (MRC) umožňuje zachytit toto prostředí jako fotku nebo video nebo sdílet to, co vidíte s ostatními, v reálném čase.

Zachycení hybridní reality používá z pohledu první osoby, aby ostatní viděli hologramy podle toho, jak je vidíte. Z pohledu třetí osoby použijte [zobrazení spectator .](https://docs.microsoft.com/windows/mixed-reality/spectator-view) Zobrazení Spectator je užitečné zejména pro ukázky.

Je sice zábavné sdílet videa mezi přáteli a kolegy, ale videa také můžou pomoct naučit ostatní uživatele používat aplikaci nebo komunikovat problémy s aplikacemi a prostředími.

> [!NOTE]
> Pokud nemůžete spustit prostředí pro zachytávání hybridní reality a HoloLens je pracovní zařízení, ověřte si to u správce systému. Přístup k fotoaparátu je možné omezit prostřednictvím zásad společnosti.

## <a name="capture-a-mixed-reality-photo"></a>Zachycení fotky hybridní reality

Existuje několik způsobů, jak posout fotku hybridní reality na HoloLens. Můžete použít hardwarová tlačítka, hlas nebo nabídka Start.

### <a name="hardware-buttons-to-take-photos"></a>Hardwarová tlačítka pro posouní fotek

Pokud chcete pohotovou fotku aktuálního zobrazení, stiskněte současně tlačítka pro zvýšení a snížení hlasitosti.  Je to něco jako verze holoLens snímku obrazovky nebo obrazovky tisku.

- [Umístění tlačítek na HoloLens 2](hololens2-hardware.md)
- [Umístění tlačítek v HoloLens (1. generace)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Když **podržíte** tlačítko **pro** zvýšení a snížení hlasitosti po dobu tří sekund, místo posouníte fotku, začne se nahrávat video. Pokud chcete nahrávání zastavit,  **klepněte současně na** tlačítka zvýšení a snížení hlasitosti.

### <a name="voice-commands-to-take-photos"></a>Hlasové příkazy pro posouní fotek

Na HoloLens 2 verze 2004 (a novější) řekněte: "Vyfoťte obrázek".

V HoloLens (1. generace) nebo HoloLens 2 verze 1903 řekněme: "Ahoj Cortano, vyfoťte obrázek".

### <a name="start-menu-to-take-photos"></a>nabídka Start k posouní fotek

Pomocí gesta Start přejděte na **Start a** pak vyberte **ikonu Fotoaparát.**

Namiřte hlavičku směrem k tomu, [](hololens2-basic-usage.md#touch-holograms-near-you) co chcete zachytit, a pak klepnutím ve vzduchu pořizovat fotku. Můžete pokračovat v klepnutí ve vzduchu a pořizovat další fotky. Všechny fotografie, které pořidíte, se uloží do vašeho zařízení.

Znovu použijte gesto Start (Spustit) a zachyťte snímek fotek.  

## <a name="capture-a-mixed-reality-video"></a>Zachycení videa s hybridní realitou

Existuje několik způsobů, jak nahrát video hybridní reality na HoloLens. Můžete použít hardwarová tlačítka, hlas nebo nabídka Start.

### <a name="hardware-buttons-to-record-videos"></a>Hardwarová tlačítka pro záznam videí

Nejrychlejší způsob, jak nahrát video, je  stisknout  a podržet současně tlačítka pro zvýšení a snížení hlasitosti, dokud nezačne třísekunové odpočítávání. Pokud chcete záznam zastavit, klepněte současně na obě tlačítka.

> [!NOTE]
> Když současně rychle **stisknete** tlačítka pro zvýšení a snížení hlasitosti, posoute fotku, a ne nahráte video. 

### <a name="voice-to-record-videos"></a>Hlas pro záznam videí

Na HoloLens 2, verze 2004 (a novější), řekněme: "Spustit nahrávání". Pokud chcete nahrávání zastavit, řekněte "Stop recording" (Zastavit nahrávání).

V HoloLens (1. generace) nebo HoloLens 2 verze 1903 řekněme: "Cortana, začněte nahrávat". Pokud chcete nahrávání zastavit, řekněte "Ahoj Cortano, zastavte nahrávání".

### <a name="start-menu-to-record-videos"></a>nabídka Start k nahrávání videí

Pomocí gesta Start přejděte na **Start (Spustit)** a pak vyberte **ikonu Video.** Namiřte hlavičku směrem k tomu, [](hololens2-basic-usage.md#touch-holograms-near-you) co chcete zachytit, a pak klepnutím ve vzduchu začáte nahrávat. Odpočítávání bude tři sekundy a vaše nahrávka začne.

Pokud chcete nahrávání zastavit, použijte gesto Spustit a vyberte zvýrazněnou **ikonu Video.** Video se uloží do vašeho zařízení.

> [!NOTE]
> **Platí jenom pro HoloLens (1. generace)**  
> Nastavení [Aktualizace Windows 10 z října 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) chování gesta Start a tlačítka Windows na HoloLens (1. generace). Před aktualizací zastaví gesto spuštění nebo tlačítko Windows záznam videa. Po aktualizaci ale tlačítko Spustit gesto nebo tlačítko Windows otevře  nabídku **Start** (nebo nabídku rychlých akcí, pokud  jste v imerzivní aplikaci), ze které můžete výběrem zvýrazněné ikony videa zastavit nahrávání.

## <a name="share-what-you-see-in-real-time"></a>Sdílení toho, co vidíte v reálném čase

To, co vidíte v HoloLens, můžete sdílet s přáteli a kolegy v reálném čase. K dispozici je několik metod:

1. Připojení k zařízení nebo adaptéru s podporou Miracast pro sledování na TV
1. Použití [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) ke sledování na počítači
1. Ke sledování [Microsoft HoloLens počítači můžete použít doprovodnou](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) aplikaci.
1. Nasazení aplikace [Microsoft Dynamics 365 Remote Assist,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) která umožňuje pracovníkům front-line streamovat to, co vidí, do vzdáleného odborníka. Vzdálený odborník pak může pracovníka front-line vést verbálně nebo anotací ve svém světě.

> [!NOTE]
> Sdílení toho, co vidíte prostřednictvím Portál zařízení s Windows nebo Microsoft HoloLens aplikace vyžaduje, aby holoLens byl v [režimu pro vývojáře.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Streamování videa pomocí Miracastu

Pomocí gesta Start přejděte na **Start (Spustit)** a pak vyberte **ikonu Connect (Připojit).** V seznamu, který se zobrazí, vyberte zařízení nebo adaptér s podporou Miracast, ke kterému se chcete připojit.

Sdílení zastavíte tak, že použijete gesto Spustit a vyberete zvýrazněnou **ikonu** Připojit. Protože jste streamování měli, nic se do vašeho zařízení nebude ukládat.

> [!NOTE]
> Podpora Miracastu byla povolena na HoloLens (1. generace) počínaje [Aktualizace Windows 10 z října 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).

### <a name="real-time-video-with-windows-device-portal"></a>Video v reálném čase s Portál zařízení s Windows

Protože sdílení přes Portál zařízení s Windows vyžaduje, aby byl na HoloLens povolený vývojářský režim, nastavte režim pro vývojáře podle pokynů v naší dokumentaci pro vývojáře a přejděte [na Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens doprovodné aplikace

Protože sdílení prostřednictvím doprovodné Microsoft HoloLens aplikace vyžaduje, aby byl na HoloLens povolený vývojářský režim, nastavte režim pro vývojáře podle pokynů v naší dokumentaci [pro vývojáře.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Pak si stáhněte [Microsoft HoloLens aplikaci](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) a podle pokynů v aplikaci se připojte k HoloLens.

Po nastavení aplikace pomocí HoloLens vyberte  v hlavní nabídce aplikace možnost Živý stream.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Zobrazení fotek a videí hybridní reality

Fotky a videa hybridní reality se ukládají do fotoaparátu v zařízení. Obsah této složky v HoloLens můžete procházet pomocí aplikace Průzkumník souborů (přejděte na Obrázky a **> fotoaparátu).**

Fotky a videa hybridní reality můžete také zobrazit v aplikaci Photos, která je předem nainstalovaná na HoloLens. Pokud chcete připnout fotku ve svém světě, vyberte ji v aplikaci Fotky a zvolte **Umístit ve smíšeném světě.** Po umístění fotky po celém světě ji můžete přesunout.

Pokud chcete zobrazit nebo uložit fotky a videa hybridní reality na počítači připojeném k HoloLens, můžete použít [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) nebo virtuální počítače [Průzkumník souborů prostřednictvím MTP.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Použití Průzkumník souborů k získání obrázků, videí a souborů

Podobně jako u jiných mobilních zařízení připojte HoloLens k počítači, aby se Průzkumník souborů pro přístup k knihovnám HoloLens (fotky, videa, dokumenty) pro snadný přenos. Tato metoda se snadno používá a nevyžaduje použití portálu zařízení ani Wi-Fi.

1. Odemkněte zařízení.
1. Připojte zařízení k počítači přes USB.
1. Průzkumník souborů by se na počítači mělo otevřít.
1. Přejděte na: \\ *Yourhololensname* tohoto počítače \Internal Storage\Pictures\Camera Roll
1. Do počítače zkopírujte všechny soubory, které potřebujete.

Tipy:
- Pokud žádné soubory nevidíte, přihlaste se ke svému HoloLens a povolte přístup k vašim datům.
- Další soubory v jiných složkách, například diagnostické soubory, můžete [získat](hololens-diagnostic-logs.md#offline-diagnostics) ze složky Dokumenty.
- V Průzkumník souborů počítači můžete vybrat Vlastnosti zařízení a zobrazit číslo verze (verze firmwaru), sériové číslo zařízení a procento baterie.
- Pokud vaše organizace k zakázání připojení [nebo připojení AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) použila MDM, pak se k vašemu zařízení nebude možné připojit.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Sdílení fotek a videí hybridní reality

Před Windows [Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)se po zachycení fotky nebo videa hybridní reality zobrazí náhled. Výběrem **ikony** Sdílet nad náhledem zobrazte asistenta sdílení. Odtud můžete vybrat koncový bod, ke kterému chcete tuto fotku nebo video sdílet.

Ve Windows Holographic verze 21H1 se po zachycení fotky nebo videa hybridní reality zobrazí náhled. Výběrem **ikony** Sdílet nad náhledem zobrazte asistenta sdílení. Odtud můžete vybrat koncový bod (Mail, OneDrive atd.), se kterým chcete tuto fotku nebo video sdílet. Můžete také povolit, aby váš HoloLens sdílel zařízení s okolními zařízeními, a to tak, že na **nastavení > >m prostředí** pro sdílení systému. Pokud chcete získat další informace, přečtěte si téma [sdílení informací v blízkosti zařízení ve Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> Můžete také sdílet fotky a videa ve smíšeném realitě z OneDrivu tím, že automaticky nahrajete fotky a videa ve smíšené realitě. Otevřete aplikaci OneDrive na HoloLens a přihlaste se pomocí **osobního [účet Microsoft](https://account.microsoft.com)**, pokud jste to ještě neudělali. Vyberte ikonu **Nastavení** a zvolte **nahrávání pomocí fotoaparátu**. Zapněte nahrávání kamery. Vaše fotky a videa ve smíšené realitě se teď nahrají na OneDrive pokaždé, když aplikaci spustíte na HoloLens.

> [!NOTE]
> Nahrávání kamery můžete povolit jenom na OneDrivu, pokud jste se k OneDrivu přihlásili pomocí osobního účet Microsoft. Pokud nastavíte HoloLens pomocí pracovního nebo školního účtu, můžete k povolení této funkce Přidat osobní účet Microsoft v aplikaci OneDrive.

## <a name="limitations-of-mixed-reality-capture"></a>Omezení pro zachycení směsné reality

- Při použití hybridního zachycení realit se kmitočet snímků HoloLens sníží na 30 Hz.
- Rozlišení fotek a videí se může snížit, pokud už se fotka nebo Videokamera používá v jiné aplikaci, při živém streamování nebo v případě nízkého množství systémových prostředků.

### <a name="maximum-recording-length"></a>Maximální délka záznamu

Na zařízeních s HoloLens 2 před 20H2em ve Windows holografické verzi se videa zaznamenaná na zařízení omezila na maximální dobu pěti minut.

Z důvodu zpětné vazby od zákazníků jsme zvýšili délku nahrávání [hybridních zachycení realit](holographic-photos-and-videos.md). Ve výchozím nastavení se u hybridních zachycení realit neomezí na 5 minut, ale místo toho se vypočítá maximální délka nahrávání na základě dostupného místa na disku. Zařízení bude odhadnout maximální dobu trvání nahrávání videa na základě dostupného místa na disku až do 80% celkového místa na disku.

> [!NOTE]
> HoloLens použije výchozí délku nahrávání videa (5 minut), pokud dojde k jedné z následujících akcí:
> - Odhadovaná maximální doba trvání záznamu je menší než výchozí hodnota 5 minut.
> - Dostupné místo na disku je méně než 20% celkového místa na disku.

## <a name="default-file-format-and-resolution"></a>Výchozí formát souboru a rozlišení

### <a name="default-photo-format-and-resolution"></a>Výchozí formát a rozlišení fotek

|  Zařízení  |  Formát  |  Linka  |  Řešení  |
|----------|----------|----------|----------|
| HoloLens 2 | [VE](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. generace) | [VE](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Formát a rozlišení zaznamenaného videa

| Zařízení | Formát | Linka | Řešení | Rychlost | Zvuk |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz stereo |
| HoloLens (1. generace) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz stereo |
