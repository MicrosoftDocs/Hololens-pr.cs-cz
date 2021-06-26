---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít se sestavami Insider a poskytnout cennou zpětnou vazbu k naší další hlavní aktualizaci operačního systému pro HoloLens.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977223"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Poznámky k verzi Windows Insider

S radostí začneme znovu začínat nové funkce pro Windows Insider. Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze. Tuto stránku budeme dál aktualizovat, protože přidáváme další funkce a aktualizace našich buildů Windows Insider. Využijte rádi a připravte se na tyto aktualizace ke své realitě.

| Funkce                 | Popis                | Cíloví uživatelé | Sestavení představeno |
|-------------------------|----------------------------|--------------|------------------|
| Změny CSP na HoloLens | Noví poskytovatelé CSP pro k dotazování na data | Správci IT    | 20348,1403                 |

### <a name="csp-changes-on-hololens"></a>Změny CSP na HoloLens

- Představeno v buildu Windows Insider, 20348,1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP teď také oznamuje volné místo v úložišti na zařízení HoloLens. To by mělo odpovídat hodnotě zobrazené na stránce nastavení úložiště aplikace. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP teď také hlásí identifikátory SSID a BSSID sítě Wi-Fi, se kterými je síť HoloLens aktivně připojená. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

- *Adresa MAC adaptéru Wi-Fi*/SSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/
- *Adresa MAC adaptéru Wi-Fi*/BSSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/

Příklad objektu BLOB SyncML (pro dodavatele MDM) pro dotazování na NetworkIdentifiers

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

- Opravili [jsme známý problém s portálem zařízení, kde se nestáhly uzamčené soubory.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili jsme [známý problém s portálem zařízení s časovým limitem nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Zahájit přijímání buildů Insider
> [!NOTE]
> Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.
> - Hlasový příkaz "restartovat zařízení" dobře funguje. 
> - V nastavení/programu Windows Insider můžete také zvolit tlačítko restartovat.
>
> Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.

V zařízení HoloLens 2 přejít na **Nastavení**  >  **aktualizace & zabezpečení**  >  **Windows Insider program** a vyberte Začínáme . Propojte účet, který jste použili k registraci jako Windows Insider.
Windows Insider se teď přesouvá na kanály. **Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**. Toto mapování vypadá takto: ![ vysvětlení kanálů Windows Insider ](images/WindowsInsiderChannels.png) pro další informace najdete v tématu [představení kanálů Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na blogu Windows.
Pak vyberte **aktivní vývoj oken**, zvolte, jestli chcete dostávat buildy pro **vývoj** nebo **beta kanál** , a zkontrolujte, jaké jsou tyto programy.
Kliknutím na tlačítko **potvrdit > restartovat nyní** dokončete instalaci. Po restartování zařízení přejít na **nastavení > Update & Security > vyhledat aktualizace** a získat nejnovější Build.
### <a name="update-error-0x80070490-work-around"></a>Chyba aktualizace 0x80070490 práce
Pokud narazíte na chybu aktualizace 0x80070490 při aktualizaci na vývojovém nebo beta kanálu, zkuste následující krátkodobé řešení. Zahrnuje přesun kanálu služby Insider, aktualizaci a přesun kanálu Insider zpátky.
#### <a name="stage-one---release-preview"></a>Fáze verze Preview 1
1.  Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **kanálu verze Preview**.
2.  Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**. Po aktualizaci pokračujte do fáze 2.
#### <a name="stage-two---dev-channel"></a>Fáze – dva vývojové kanály
1. Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **vývojového kanálu**.
2. Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**.
## <a name="ffu-download-and-flash-directions"></a>FFU stažení a pokyny pro Flash
Pokud chcete otestovat ffuem podepsaným letem, musíte nejdřív zařízení odemknout a před zavedením ffuého letu podepsaného.
1. V počítači:
    1. Stáhněte si FFU do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Nainstalujte oblouk (Průvodce pokročilým obnovením) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Při zablokování HoloLens: Otevřete **Nastavení**  >  **aktualizovat & zabezpečení**  >  **program Windows Insider** a potom se zaregistrujte a restartujte zařízení.
1. FFU Flash – nyní můžete FFU podepsaný pro let pomocí ARC.
### <a name="provide-feedback-and-report-issues"></a>Poskytněte zpětnou vazbu a nahlásit problémy
K poskytnutí zpětné vazby a hlášení problémů použijte prosím [aplikaci centra Feedback](hololens-feedback.md) na HoloLens. Pomocí centra Feedback zajišťujeme, aby byly k dispozici všechny potřebné diagnostické informace, které nám pomohly rychle ladit a řešit potíže.  Problémy s čínskou a japonskou verzí HoloLens by měly být hlášeny stejným způsobem.
> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete, aby měl centrum zpětné vazby přístup ke složce dokumentů (po zobrazení výzvy vyberte **Ano** ).
## <a name="note-for-developers"></a>Poznámka pro vývojáře
Jste připraveni a doporučujeme vyzkoušet vývoj vašich aplikací pomocí buildů Insider pro HoloLens.  Začněte tím, že si Projděte [dokumentaci pro vývojáře HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) . Stejné pokyny fungují s buildy pro práci s buildem HoloLens.  Můžete použít stejné sestavení Unity a Visual Studio, které už používáte pro vývoj na HoloLens.
## <a name="stop-receiving-insider-builds"></a>Zastavit příjem buildů Insider
Pokud už nechcete dostávat buildy Insider pro Windows holografické, můžete se odhlásit, když na HoloLens běží výrobní sestavení, nebo můžete [zařízení obnovit](hololens-recovery.md) pomocí Průvodce pokročilým obnovením a obnovit zařízení do verze Windows holografického v jiné verzi než Insider.
> [!CAUTION]
> Došlo k známému problému, při kterém se uživatelé, kteří zruší registraci v buildu Insider Preview po ruční instalaci nového buildu Preview, zobrazí modrá obrazovka. Potom musí zařízení ručně obnovit. Podrobné informace o tom, jestli by se to ovlivnilo, najdete v tomto [známém problému](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).
Chcete-li ověřit, zda je na HoloLens spuštěno výrobní sestavení:
1. Přejít na **nastavení > systémové > o produktu** a najít číslo buildu.
1. [Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).
Odhlášení od buildů Insider:
1. Na HoloLens, na kterém běží výrobní sestavení, klikněte na **nastavení > Update & Security > program Windows Insider** a vyberte **Zastavit buildy Insider**.
1. Pokud chcete zařízení odhlásit, postupujte podle pokynů.
