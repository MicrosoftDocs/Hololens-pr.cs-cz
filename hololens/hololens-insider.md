---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít s buildy Insider, a poskytněte vám užitečnou zpětnou vazbu k naší další aktualizaci operačního systému HoloLens.
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
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 19035c53fec64ec19243ab5edc79bf77acbf400a
ms.sourcegitcommit: d99de8d5afbe2585fdb5396bd0165ac74734b281
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/17/2021
ms.locfileid: "122277150"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi programu Insider

s radostí zahájíme nové funkce, které Windows insidery. Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze. tato stránka bude i nadále aktualizována, protože přidáváme další funkce a aktualizace našich Windows buildů Insider. Využijte rádi a připravte se na tyto aktualizace ke své realitě.

Tato verze se týká vylepšených sestav řešení potíží a zařízení, některých opravených chyb v celoobrazovkovém režimu a v prohlížeči certifikátů, rozšiřitelné plochy spravovatelnosti a zvýšené spolehlivosti aktualizací. nová funkce nejdůležitější této aktualizace funkcí připravujeme HoloLens je náš režim pro přesun platforem. podívejte se na všechny nové skvělé funkce HoloLens 2!

| Funkce                 | Popis                | Uživatel nebo scénář | Sestavení představeno |
|-------------------------|----------------------------|--------------|------------------|
| [Přesun režimu platformy](#moving-platform-mode) | zavádí režim přesunutí verze beta, který je v případě, že je nakonfigurován, umožňuje použití HoloLens 2 na velkých mořských plavidlech s nízkým dynamickým pohybem. | Vše | 20348,1411 |
| [Podpora souborů PFX pro správce certifikátů](#pfx-file-support-for-certificate-manager) | přidání certifikátů PFX prostřednictvím Nastavení uživatelského rozhraní | Koncový uživatel | 20348,1405 |
| [zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazit diagnostické protokoly MDM na zařízení | Řešení potíží | 20348,1405 |
| [Upozornění offline diagnostiky](#offline-diagnostics-notifications) | Audiovizuální zpětná vazba pro shromažďování protokolů | Řešení potíží | 20348,1405 |
| [Vylepšení shromažďování protokolů s nízkým úložištěm](#low-storage-log-collection-improvements) | Vylepšení scénářů shromažďování protokolů během nedostatku případů úložiště. | Řešení potíží | 20348,1412 |
| [CSP se mění pro vytváření sestav HoloLens podrobnosti](#csp-changes-for-reporting-hololens-details) | Noví poskytovatelé CSP pro k dotazování na data | Správci IT    | 20348,1403                 |
| [Zásady automatického přihlašování řízené zprostředkovatelem CSP](#auto-login-policy-controlled-by-csp) | Používá se k automatickému přihlášení k účtu. | Správci IT | 20348,1405 |
| [Vylepšené zjišťování a oznámení o aktualizacích](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské prostředí pro aktualizace. | Správci IT | 20348,1405 |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánované opakované pokusy o aktualizaci aplikací. | Správci IT | 20348,1405 |
| [Používejte pouze aplikace privátního úložiště pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby zobrazovala pouze aplikace z organizace | Správce IT | 20348,1408 |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení HoloLens. | Vše | 20348,1411 |

### <a name="it-admin-insider-feature-checklist"></a>Kontrolní seznam funkcí Insider správce IT

✔️ Pokud chcete nastavit jeden účet Azure AD tak, aby se automaticky přihlásil, [nakonfigurujte tohoto nového CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Pokud chcete, aby se vaše aplikace po selhání aktualizace automaticky pokoušely aktualizovat, [nastavte tohoto nového CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ Pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto [nově povolené zásady aktualizace.](#improved-update-restart-detection-and-notifications) <br>
pokud potřebujete, aby byly aplikace vaší organizace dostupné v obchodě společnosti prostřednictvím Microsoft Store, ale chcete přístup jenom k aplikacím vaší organizace a nikoli k úplnému úložišti, [nastavte tuto zásadu.](#use-only-private-store-apps-for-microsoft-store) ✔️ <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLensch zařízení se podívejte na tyto [zprostředkovatele csp pro vytváření sestav.](#csp-changes-for-reporting-hololens-details)

### <a name="moving-platform-mode"></a>Přesun režimu platformy

od buildu **Insider 20348,1411** jsme přidali podporu beta pro sledování na vysoce dynamických pohybových platformách na HoloLens 2. po instalaci sestavení a povolení režimu přesunu platforem budete moci použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské lodi. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

Další informace o tom, co je podporováno a jak povolit tuto novou funkci, [najdete na stránce přesun platformy.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro správce certifikátů

představeno v Windows build Insider build 20348,1405. Přidali jsme podporu [Správce certifikátů](certificate-manager.md) pro teď použití certifikátů. pfx. když uživatel přejde na **Nastavení**  >  **Update &**  >  **certifikáty** zabezpečení a vybere možnost **nainstalovat certifikát** , uživatelské rozhraní teď podporuje soubor certifikátu. pfx.
Uživatelé mohou importovat certifikát. pfx s privátním klíčem do úložiště uživatele nebo do úložiště počítače.

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

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se u zařízení při shromažďování diagnostických protokolů jeví nedostatek místa na disku, vytvoří se další zpráva s názvem **StorageDiagnostics.zip** . prahová hodnota nízkého úložiště je určena automaticky Windows [smyslem úložiště](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48).

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP se mění pro vytváření sestav HoloLens podrobnosti

- představeno v Windows build Insider, 20348,1403

následující poskytovatelé csp byli aktualizováni novými způsoby, jak ohlásit informace ze zařízení HoloLens.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – bezplatná Storage

DevDetail CSP nyní také oznamuje volné místo v úložišti HoloLens zařízení. hodnota by měla odpovídat hodnotě zobrazené na stránce Storage aplikace Nastavení. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP nyní také hlásí identifikátory SSID a BSSID Wi-Fi sítě, se kterou HoloLens aktivně připojená. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

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

Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlašuje. Někteří zákazníci chtějí nastavit zařízení, která jsou vázaná na identitu, ale nechtějí žádné přihlašovací prostředí. Imagine vyzvednutí zařízení a okamžitě pomocí programu vzdálená pomoc. nebo využijte výhod, které vám umožní rychle distribuovat HoloLens zařízení a umožnit koncovým uživatelům urychlení přihlašovacích údajů.

Když je zásada nastavená na neprázdnou hodnotu, určí se e-mailová adresa uživatele automatického přihlašování. Zadaný uživatel se musí k zařízení přihlašovat aspoň jednou, aby se povolilo automatické přihlašování.

OMA-URI nové `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` hodnoty řetězce zásad

- Uživatel se stejnou e-mailovou adresou bude mít povoleno automatické přihlašování.

V zařízení, na kterém je tato zásada nakonfigurovaná, se uživatel zadaný v zásadě musí přihlašovat aspoň jednou. Následná restartování zařízení po prvním přihlášení budou mít zadaného uživatele automaticky přihlášeni. Podporuje se jenom jeden uživatel s automatickým přihlašováním. Po povolení se automaticky přihlášený uživatel nebude moci odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být tato zásada nejdřív zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, můžou vyžadovat, aby zadaný uživatel znovu přihlásí k zařízení a obnovil chování automatického přihlašování.
> - Automatické přihlašování se podporuje jenom pro uživatele MSA a AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Vylepšené zjišťování a oznámení o aktualizacích

mezi aktivními hodinami a zásadami času instalace je možné zabránit restartování HoloLens zařízení, když se používají. Nicméně by také zpozdil přijetí aktualizací, pokud k restartování nedojde k dokončení instalace požadované aktualizace. Nyní jsme přidali zásady, které jim umožní vymáhat termíny a požadovaná restartování a zajistit, aby byla instalace aktualizace dokončena včas. Uživatelé můžou být upozorňováni před zahájením restartování a můžou zpozdit restart v souladu se zásadami IT.

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

### <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

nyní je povolena pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jednorázové datum k restartování aplikací, jejichž aktualizace se nezdařila, protože se aplikace používá, což umožňuje použití aktualizace. Je možné je nastavit na základě několika různých triggerů, jako je například naplánovaný čas nebo přihlášení. Další informace o tom, jak používat tuto zásadu, najdete v článku [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používat jenom soukromé aplikace ze Storu

Zásada RequirePrivateStoreOnly je povolená pro HoloLens. tato zásada umožňuje, aby byla aplikace Microsoft Store nakonfigurovaná tak, aby zobrazovala jenom privátní úložiště nakonfigurované pro vaši organizaci. Omezení přístupu pouze k aplikacím, které byly k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

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

Jste připraveni a doporučujeme vyzkoušet vývoj aplikací pomocí buildů Insider HoloLens.  Pokud chcete [začít, HoloLens si prohlédněte dokumentaci pro](https://developer.microsoft.com/windows/mixed-reality/development) vývojáře aplikací. Stejné pokyny fungují i s buildy insider HoloLens.  Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavení přijímání sestavení Insider

Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není z programu Insider.

> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:

1. Přejděte na **Nastavení > System > About** a vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro produkční čísla sestavení](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním sestavení přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
