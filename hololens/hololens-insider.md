---
title: Insider preview pro Microsoft HoloLens
description: Zjistěte, jak začít se sestaveními Insider a poskytnout cennou zpětnou vazbu pro naši další velkou aktualizaci operačního systému pro HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924362"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview pro Microsoft HoloLens

Vítá vás nejnovější sestavení Insider Preview pro HoloLens! Začít a poskytnout [cennou zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens je jednoduché.

## <a name="windows-insider-release-notes"></a>Windows Insider k vydání verze

S radostí můžeme znovu začít přechádovat nové funkce do programu Windows Insider. Nové buildy budou uchytát se do kanálů pro vývoj a beta verze a budou dostávat nejnovější aktualizace. Tuto stránku budeme dál aktualizovat, jakmile do našich buildů přidáme další funkce a Windows Insider aktualizace. Připravte se na kombinaci těchto aktualizací do vaší reality. 

### <a name="csp-changes-on-hololens"></a>Změny CSP na HoloLens
 
- Zavedeno v Windows Insider buildu, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP teď také hlásí volné místo úložiště na zařízení HoloLens. Tato hodnota by se měla přibližně shodovat s hodnotou zobrazenou na stránce Úložiště aplikace Nastavení. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP teď také hlásí SSID a BSSID wi-fi sítě, se kterou je HoloLens aktivně připojený. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa mac Wi-Fi adaptéru*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa MAC Wi-Fi adaptéru*/BSSID

Příklad objektu blob syncml (pro dodavatele MDM) pro dotazování na NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Opravy a vylepšení:

- Byl opraven známý problém pro Portál zařízení, kdy se při stahování uzamčených souborů nic [nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider
> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.
> - Hlasový příkaz Restartovat zařízení funguje dobře. 
> - Můžete také zvolit tlačítko restartovat v Nastavení/Program Windows Insider.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení**  >  **Aktualizace & Security**  >  **Program Windows Insider** a vyberte **Začínáme.** Propojte účet, který jste použili k registraci, jako Windows Insider.
Windows Insider se teď přesouvá na Kanály. Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál release **preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle: Windows Insider vysvětlení kanálů Další informace najdete v tématu Představení kanálů Windows Insider ![ ](images/WindowsInsiderChannels.png) [na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) blozích Windows.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **buildy,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte na Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.
### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky
Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.
#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview
1.  Settings, Update & Security, Program Windows Insider vyberte **Release Preview Channel**.
2.  Settings, Update & Security, služba Windows Update, **Check for updates**. Po aktualizaci pokračujte k fázi 2.
#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál
1. Settings(Nastavení), Update & Security (Zabezpečení Program Windows Insider) a vyberte **Dev Channel (Vývojový kanál).**
2. Settings, Update & Security, služba Windows Update, **Check for updates**.
## <a name="ffu-download-and-flash-directions"></a>Pokyny ke stažení ffu a flash
Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.
1. Na počítači:
    1. Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Na HoloLens – Letové odemčení: **Otevřete** Nastavení Aktualizace &  >  **Security**  >  **Program Windows Insider** a pak se zaregistrujte a restartujte zařízení.
1. Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.
### <a name="provide-feedback-and-report-issues"></a>Poskytnutí zpětné vazby a hlášení problémů
Pokud chcete [poskytnout zpětnou vazbu Centrum Feedback nahlásit](hololens-feedback.md) problémy, použijte prosím aplikaci pro Centrum Feedback na HoloLens. Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.  Problémy s čínštinou a japonštinou holoLens by se měly hlásit stejným způsobem.
> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli Centrum Feedback přístup ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).
## <a name="note-for-developers"></a>Poznámka pro vývojáře
Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí sestavení Insider pro HoloLens.  Pokud chcete začít, podívejte se do dokumentace pro vývojáře [HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development) Stejné pokyny fungují i se sestaveními Insider pro HoloLens.  Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro vývoj pro HoloLens.
## <a name="stop-receiving-insider-builds"></a>Zastavení přijímání sestavení Insider
Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když [](hololens-recovery.md) HoloLens používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není součástí programu Insider.
> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Ověření, že HoloLens používá produkční sestavení:
1. Přejděte na **Nastavení > System > About (O aplikaci) a** vyhledejte číslo sestavení.
1. [Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).
Odhlášení sestavení Insider:
1. V HoloLens, na které běží produkční sestavení, přejděte na Nastavení **> Update & Security > Program Windows Insider** a vyberte Zastavit sestavení **Insider.**
1. Postupujte podle pokynů a odhlásit zařízení.
