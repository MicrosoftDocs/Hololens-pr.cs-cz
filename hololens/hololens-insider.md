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
ms.openlocfilehash: 86a763adb233b45242182d069a56692aeddc2e59
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858568"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Poznámky k verzi Windows Insider

S radostí začneme znovu začínat nové funkce pro Windows Insider. Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze. Tuto stránku budeme dál aktualizovat, protože přidáváme další funkce a aktualizace našich buildů Windows Insider. Využijte rádi a připravte se na tyto aktualizace ke své realitě.

| Funkce                 | Popis                | Uživatel nebo scénář | Sestavení představeno |
|-------------------------|----------------------------|--------------|------------------|
| [Změny zprostředkovatele CSP pro vytváření sestav – podrobnosti o HoloLens](#csp-changes-for-reporting-hololens-details) | Noví poskytovatelé CSP pro k dotazování na data | Správci IT    | 20348,1403                 |
| [Zásady automatického přihlašování řízené zprostředkovatelem CSP](#auto-login-policy-controlled-by-csp) | Používá se k automatickému přihlášení k účtu. | Správci IT | 20348,1405 |
| [Vylepšené zjišťování a oznámení o aktualizacích](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské prostředí pro aktualizace. | Správci IT | 20348,1405 |
| [Podpora souborů PFX pro správce certifikátů](#pfx-file-support-for-certificate-manager) | Přidání certifikátů PFX prostřednictvím nastavení uživatelského rozhraní | Koncový uživatel | 20348,1405 |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánované opakované pokusy o aktualizaci aplikací. | Správci IT | 20348,1405 |
| [Zobrazit pokročilou diagnostickou sestavu v nastaveních na HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazit diagnostické protokoly MDM na zařízení | Řešení potíží | 20348,1405 |
| [Upozornění offline diagnostiky](#offline-diagnostics-notifications) | Audiovizuální zpětná vazba pro shromažďování protokolů | Řešení potíží | 20348,1405 |
| [Používejte pouze aplikace privátního úložiště pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby zobrazovala pouze aplikace z organizace | Správce IT | 20348,1408 |
| [Vylepšení shromažďování protokolů s nízkým úložištěm](#low-storage-log-collection-improvements) | Vylepšení scénářů shromažďování protokolů během nedostatku případů úložiště. | Správce IT | 20348,1412 |
| [Přesun režimu platformy](#moving-platform-mode) | Zavádí režim přesunutí verze beta, který je v případě konfigurace povolený, umožňuje použití HoloLens 2 na velkých mořských plavidlech, u kterých dochází k nízkému dynamickému pohybu. | Vše | 20348,1411 |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení pro HoloLens. | Vše | 20348,1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny zprostředkovatele CSP pro vytváření sestav – podrobnosti o HoloLens

- Představeno v buildu Windows Insider, 20348,1403

Následující poskytovatelé CSP byli aktualizováni novými způsoby, jak ohlásit informace ze zařízení HoloLens.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – volné úložiště

DevDetail CSP teď také oznamuje volné místo v úložišti na zařízení HoloLens. To by mělo odpovídat hodnotě zobrazené na stránce nastavení úložiště aplikace. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP teď také hlásí identifikátory SSID a BSSID Wi-Fi sítě, se kterou je aktivně připojená síť HoloLens. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

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

### <a name="auto-login-policy-controlled-by-csp"></a>Zásady automatického přihlašování řízené zprostředkovatelem CSP

Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlašuje. Někteří zákazníci chtějí nastavit zařízení, která jsou vázaná na identitu, ale nechtějí žádné přihlašovací prostředí. Představte si, že si vybíráte zařízení a okamžitě pomocí programu Remote Assist. Nebo máte výhodu, že je možné rychle distribuovat zařízení s HoloLens a umožnit koncovým uživatelům urychlení přihlašovacích údajů.

Když je zásada nastavená na neprázdnou hodnotu, určí se e-mailová adresa uživatele automatického přihlašování. Zadaný uživatel se musí k zařízení přihlašovat aspoň jednou, aby se povolilo automatické přihlašování.

OMA-URI nové `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` hodnoty řetězce zásad

- Uživatel se stejnou e-mailovou adresou bude mít povoleno automatické přihlašování.

V zařízení, na kterém je tato zásada nakonfigurovaná, se uživatel zadaný v zásadě musí přihlašovat aspoň jednou. Následná restartování zařízení po prvním přihlášení budou mít zadaného uživatele automaticky přihlášeni. Podporuje se jenom jeden uživatel s automatickým přihlašováním. Po povolení se automaticky přihlášený uživatel nebude moci odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být tato zásada nejdřív zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, můžou vyžadovat, aby zadaný uživatel znovu přihlásí k zařízení a obnovil chování automatického přihlašování.
> - Automatické přihlašování se podporuje jenom pro uživatele MSA a AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Vylepšené zjišťování a oznámení o aktualizacích

Mezi aktivními hodinami a zásadami času instalace je možné vyhnout se restartování zařízení HoloLens při jejich používání. Nicméně by také zpozdil přijetí aktualizací, pokud k restartování nedojde k dokončení instalace požadované aktualizace. Nyní jsme přidali zásady, které jim umožní vymáhat termíny a požadovaná restartování a zajistit, aby byla instalace aktualizace dokončena včas. Uživatelé můžou být upozorňováni před zahájením restartování a můžou zpozdit restart v souladu se zásadami IT.

Byly přidány následující zásady aktualizace:

- [Aktualizovat/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Aktualizovat/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Aktualizovat/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Aktualizovat/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Aktualizovat/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Aktualizovat/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Aktualizovat/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Aktualizovat/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Aktualizovat/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro správce certifikátů

představeno v Windows build Insider build 20348,1405. Přidali jsme podporu [Správce certifikátů](certificate-manager.md) pro teď použití certifikátů. pfx. když uživatel přejde na **Nastavení**  >  **Update &**  >  **certifikáty** zabezpečení a vybere možnost **nainstalovat certifikát** , uživatelské rozhraní teď podporuje soubor certifikátu. pfx.
Uživatelé mohou importovat certifikát. pfx s privátním klíčem do úložiště uživatele nebo do úložiště počítače.

### <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

nyní je povolena pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jednorázové datum k restartování aplikací, jejichž aktualizace se nezdařila, protože se aplikace používá, což umožňuje použití aktualizace. Je možné je nastavit na základě několika různých triggerů, jako je například naplánovaný čas nebo přihlášení. Další informace o tom, jak používat tuto zásadu, najdete v článku [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens

Pro spravovaná zařízení při řešení potíží ověřte, že se používá očekávaná konfigurace zásad, což je důležitý krok. dříve se tato nová funkce musela po exportu protokolů pro diagnostiku mdm shromážděných prostřednictvím **Nastavení**  ->  **účtů**  >  **přistupovat do práce nebo do školy** a vybrat možnost **exportovat protokoly správy** a zobrazit je na nejbližším počítači v blízkosti zařízení.

Diagnostiku MDM je teď možné zobrazit na zařízení pomocí prohlížeče Edge. Chcete-li snadněji zobrazit diagnostickou zprávu MDM, přejděte na stránku přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu**. Tato akce vygeneruje a otevře sestavu v novém okně Edge.

![zobrazit pokročilou diagnostickou sestavu v aplikaci Nastavení.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Upozornění offline diagnostiky

Tato aktualizace pro existující funkci se nazývá [offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve neexistoval žádný jasný indikátor pro uživatele, kteří aktivovali diagnostické shromažďování nebo dokončili.
nově přidaná v Windows buildů Insider existují dvě formy audiovizuální zpětné vazby pro Offline diagnostiku. První je oznámení, která se zobrazují pro obě při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a obsahuje vizuály.

![Informační zprávy pro shromažďování protokolů.](./images/logcollection1.jpg)

![Informační zprávy, když je shromažďování protokolů dokončeno.](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus pro shromažďování protokolů, kdy nemají přístup k zobrazení, nemůžete se přihlásit nebo jsou pořád v počátečním souboru OOBE, při shromažďování protokolů se taky dohraje zvukový signál. Tento zvuk se přehraje kromě informačního oznámení.

Tato nová funkce bude povolená, když se vaše zařízení aktualizuje a nebude nutné ho povolit ani spravovat. V případě, že tuto novou zpětnou vazbu nelze zobrazit nebo zobrazit, bude i nadále vygenerována offline Diagnostika.

Doufáme, že s tímto novějším přidáním audiovizuální zpětné vazby je snazší shromažďovat diagnostická data a rychleji řešit problémy.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používat jenom soukromé aplikace ze Storu

Zásada RequirePrivateStoreOnly je povolená pro HoloLens. tato zásada umožňuje, aby byla aplikace Microsoft Store nakonfigurovaná tak, aby zobrazovala jenom privátní úložiště nakonfigurované pro vaši organizaci. Omezení přístupu pouze k aplikacím, které byly k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se u zařízení při shromažďování diagnostických protokolů jeví nedostatek místa na disku, vytvoří se další zpráva s názvem **StorageDiagnostics.zip** . prahová hodnota nízkého úložiště je určena automaticky Windows [smyslem úložiště](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

### <a name="moving-platform-mode"></a>Přesun režimu platformy

od buildu **Insider 20348,1411** jsme přidali podporu beta pro sledování na vysoce dynamických pohybových platformách na HoloLens 2. po instalaci sestavení a povolení režimu přesunu platforem budete moci použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské lodi. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

Další informace o tom, co je podporováno a jak povolit tuto novou funkci, [najdete na stránce přesun platformy.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

- Opravili [jsme známý problém s portálem zařízení, kde se nestáhly uzamčené soubory.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili jsme [známý problém s portálem zařízení s časovým limitem nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- řeší problémy při vytváření sestav vlastností dodržování předpisů z HoloLens zařízení; pro spuštění správných sestav na buildech Insider může být nutné restartovat počítač.  
- povolili jste [přiřazené přístupové rozhraní API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) , takže aplikace teď můžou určit, jestli HoloLens běží v celoobrazovkovém režimu pro uživatele přihlášeného k HoloLens.
- Aktualizace integrované verze vzdálené pomoci, která je nainstalovaná na nových bliknutích

## <a name="start-receiving-insider-builds"></a>Zahájit přijímání buildů Insider

> [!NOTE]
> Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.
>
> - Hlasový příkaz "restartovat zařízení" dobře funguje.
> - můžete také zvolit tlačítko restartovat v programu Nastavení/Windows Insider.
>
> Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.

na zařízení HoloLens 2 přejít do **Nastavení**  >  **Update & Security**  >  **Windows Program Insider** a vyberte začínáme . propojte účet, který jste použili k registraci jako Windows Insider.

Windows insider se teď přesouvá na kanály. **Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**. Toto mapování vypadá takto:

![Windows Vysvětlení kanálů Insider](images/WindowsInsiderChannels.png)

další informace najdete v tématu [představení Windowsch kanálů Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na Windows blogů.
pak vyberte možnost **aktivní vývoj Windows**, zvolte, jestli chcete dostávat buildy pro **vývoj** nebo **Beta kanál** , a podívejte se na licenční program.
Kliknutím na tlačítko **potvrdit > restartovat nyní** dokončete instalaci. po restartování zařízení přejít na **Nastavení > Update & Security > vyhledat aktualizace** a získat nejnovější build.

### <a name="update-error-0x80070490-work-around"></a>Chyba aktualizace 0x80070490 práce

Pokud narazíte na chybu aktualizace 0x80070490 při aktualizaci na vývojovém nebo beta kanálu, zkuste následující krátkodobé řešení. Zahrnuje přesun kanálu služby Insider, aktualizaci a přesun kanálu Insider zpátky.

#### <a name="stage-one---release-preview"></a>Fáze verze Preview 1

1. Nastavení, Update & Security Windows programu Insider vyberte **kanál verze preview**.

2. Nastavení, aktualizujte & zabezpečení, web Windows Update vyhledejte **aktualizace**. Po aktualizaci pokračujte do fáze 2.

#### <a name="stage-two---dev-channel"></a>Fáze – dva vývojové kanály

1. Nastavení, aktualizovat & zabezpečení Windows programu Insider vyberte možnost **vývojového kanálu**.

2. Nastavení, aktualizujte & zabezpečení, web Windows Update vyhledejte **aktualizace**.

## <a name="ffu-download-and-flash-directions"></a>FFU stažení a pokyny pro Flash

Pokud chcete otestovat ffuem podepsaným letem, musíte nejdřív zařízení odemknout a před zavedením ffuého letu podepsaného.

1. V počítači:
    1. Stáhněte si FFU do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Nainstalujte oblouk (Průvodce pokročilým obnovením) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. při HoloLensovém odemknutí: otevřít **Nastavení**  >  **aktualizace & zabezpečení**  >  **Windows programu Insider** , zaregistrujte se a restartujte zařízení.

1. FFU Flash – nyní můžete FFU podepsaný pro let pomocí ARC.

### <a name="provide-feedback-and-report-issues"></a>Poskytněte zpětnou vazbu a nahlásit problémy

k poskytnutí zpětné vazby a hlášení problémů použijte prosím [aplikaci centra Feedback](hololens-feedback.md) v HoloLens. Pomocí centra Feedback zajišťujeme, aby byly k dispozici všechny potřebné diagnostické informace, které nám pomohly rychle ladit a řešit potíže.  problémy s čínskou a japonskou verzí HoloLens by měly být hlášeny stejným způsobem.

> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete, aby měl centrum zpětné vazby přístup ke složce dokumentů (po zobrazení výzvy vyberte **Ano** ).

## <a name="note-for-developers"></a>Poznámka pro vývojáře

Jste připraveni a doporučujeme vyzkoušet vývoj aplikací pomocí buildů Insider HoloLens.  pokud chcete začít, podívejte se na [dokumentaci pro vývojáře HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) . Stejné pokyny fungují s buildy Insider HoloLens.  můžete použít stejná sestavení Unity a Visual Studio, která už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavit příjem buildů Insider

pokud už nechcete dostávat buildy Insider Windows holografické, můžete se odhlásit, když HoloLens spouští výrobní sestavení, nebo můžete [zařízení obnovit](hololens-recovery.md) pomocí průvodce pokročilým obnovením a obnovit zařízení do verze programu Windows holografické v jiné verzi než Insider.

> [!CAUTION]
> Došlo k známému problému, při kterém se uživatelé, kteří zruší registraci v buildu Insider Preview po ruční instalaci nového buildu Preview, zobrazí modrá obrazovka. Potom musí zařízení ručně obnovit. Podrobné informace o tom, jestli by se to ovlivnilo, najdete v tomto [známém problému](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).

chcete-li ověřit, zda HoloLens spouští výrobní sestavení:

1. Přejděte na Nastavení > System > About (O **produktu) a** vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním buildu přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
