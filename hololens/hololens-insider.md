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
ms.openlocfilehash: b865f9f9a9a734ef6a6c6419fc523049e925d5f8
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189473"
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
| [Vylepšené zjišťování a oznámení o aktualizacích](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské rozhraní pro aktualizace. | Správci IT | 20348,1405 |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánované opakované pokusy o aktualizaci aplikací. | Správci IT | 20348,1405 |
| [Používejte pouze aplikace privátního úložiště pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby zobrazovala pouze aplikace z organizace | Správce IT | 20348,1408 |
| [Použití aplikací WDAC a LOB](#use-wdac-and-lob-apps) | Umožňuje správcům IT používat vlastní aplikace a nadále používat WDAC k blokování dalších aplikací. | Správci IT | 20348,1405 |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení HoloLens. | Vše | 20348,1411 |

### <a name="it-admin-insider-feature-checklist"></a>Kontrolní seznam funkcí Insider správce IT

✔️ Pokud chcete nastavit jeden účet Azure AD pro automatické přihlášení, [nakonfigurujte tohoto nového CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Pokud chcete, aby se vaše aplikace po selhání aktualizace automaticky pokoušely aktualizovat, [nastavte tohoto nového CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ Pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto [nově povolené zásady aktualizace.](#improved-update-restart-detection-and-notifications) <br>
pokud potřebujete, aby byly aplikace vaší organizace dostupné v obchodě společnosti prostřednictvím Microsoft Store, ale chcete přístup jenom k aplikacím vaší organizace a nikoli k úplnému úložišti, [nastavte tuto zásadu.](#use-only-private-store-apps-for-microsoft-store) ✔️ <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLensch zařízení se podívejte na tyto [zprostředkovatele csp pro vytváření sestav.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Pokud chcete používat WDAC k blokování spouštění aplikací nebo procesů, ale také potřebujete použít vlastní řádek aplikací bushiness, můžete teď [ve svých zásadách pro WDAC dovolit LOB](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Přesun režimu platformy

od buildu **Insider 20348,1411** jsme přidali podporu beta pro sledování na vysoce dynamických pohybových platformách na HoloLens 2. po instalaci sestavení a povolení režimu přesunu platforem budete moci použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské lodi. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

Další informace o tom, co je podporováno a jak povolit tuto novou funkci, [najdete na stránce přesun platformy.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro správce certifikátů

představeno v Windows build Insider build 20348,1405. Přidali jsme podporu [Správce certifikátů](certificate-manager.md) pro teď použití certifikátů. pfx. když uživatel přejde na **Nastavení**  >  **Update &**  >  **certifikáty** zabezpečení a vybere možnost **nainstalovat certifikát** , uživatelské rozhraní teď podporuje soubor certifikátu. pfx.
Uživatelé mohou importovat certifikát. pfx s privátním klíčem do úložiště uživatele nebo do úložiště počítače.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens

Pro spravovaná zařízení při řešení potíží ověřte, že se používá očekávaná konfigurace zásad, což je důležitý krok. před touto novou funkcí se tyto informace musely po exportu protokolů pro diagnostiku mdm shromážděných prostřednictvím **Nastavení**  ->  **účtů**  >  **přistupovat do práce nebo do školy** a vybrat možnost **exportovat protokoly pro správu** a zobrazit je v blízkosti počítače.

Diagnostiku MDM je teď možné zobrazit na zařízení pomocí prohlížeče Edge. Chcete-li snadněji zobrazit diagnostickou zprávu MDM, přejděte na stránku přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu**. Tato akce vygeneruje a otevře sestavu v novém okně Edge.

![zobrazit pokročilou diagnostickou sestavu v aplikaci Nastavení.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Upozornění offline diagnostiky

Tato aktualizace pro existující funkci se nazývá [offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve neexistoval žádný jasný indikátor pro uživatele, kteří aktivovali diagnostické shromažďování nebo dokončili.
nově přidaná v Windows buildů Insider existují dvě formy audiovizuální zpětné vazby pro Offline diagnostiku. První je oznámení, která se zobrazují pro obě při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a obsahuje vizuály.

![Informační zprávy pro shromažďování protokolů.](./images/logcollection1.jpg)

![Informační zprávy, když je shromažďování protokolů dokončeno.](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus pro shromažďování protokolů, kdy nemají přístup k zobrazení, nemůžete se přihlásit nebo jsou pořád v počátečním souboru OOBE, při shromažďování protokolů se taky dohraje zvukový signál. Tento zvuk se přehraje kromě informačního oznámení.

Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná. Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.

Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se zdá, že zařízení má při shromážděných diagnostických protokolech nedostatek místa na disku, vytvoří seStorageDiagnostics.zipsestava s názvem .  Prahová hodnota nízkého úložiště se určuje automaticky Windows [úložiště.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny CSP pro podrobnosti HoloLens sestav

- Zavedeno v Windows Insider, 20348.1403

Následující csP se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Bezplatná Storage

DevDetail CSP teď také hlásí volné místo v HoloLens zařízení. Tato hodnota by se měla přibližně shodovat s hodnotou Nastavení na stránce Storage aplikace. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP teď také hlásí SSID a BSSID Wi-Fi sítě, se HoloLens je aktivně připojená. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa mac Wi-Fi adaptéru*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa mac Wi-Fi adaptéru*/BSSID

Příklad objektu blob syncml (pro dodavatele MDM) pro dotaz na NetworkIdentifiers

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

### <a name="auto-login-policy-controlled-by-csp"></a>Zásady automatického přihlášení řízené poskytovatelem CSP

Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlásí. Někteří zákazníci chtějí nastavit zařízení, která jsou svázaná s identitou, ale nechcete žádné přihlašovací prostředí. Imagine vyzvednutí zařízení a okamžité použití vzdálené pomoci. Nebo můžete mít výhodu, že dokážete rychle distribuovat HoloLens zařízení a umožnit koncovým uživatelům urychlit přihlášení.

Pokud je zásada nastavená na neprázdnou hodnotu, určuje e-mailovou adresu uživatele s automatickým přihlášením. Zadaný uživatel se musí alespoň jednou přihlásit k zařízení, aby se umožnilo automatické přihlášení.

OMA-URI nové hodnoty řetězce `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` zásad

- Uživatel se stejnou e-mailovou adresou bude mít povolené automatické přihlášení.

Na zařízení, kde je tato zásada nakonfigurovaná, se musí uživatel zadaný v zásadách alespoň jednou přihlásit. Po dalším restartování zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí. Podporuje se jenom jeden uživatel s automatickým přihlášením. Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, mohou vyžadovat, aby se zadaný uživatel k zařízení znovu přihlásit, aby obnovoval chování automatického přihlášení.
> - Automatické přihlášení se podporuje jenom pro uživatele MSA a AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Vylepšená detekce restartování aktualizací a oznámení

Mezi aktivními hodinami a zásadami doby instalace je možné se vyhnout restartování HoloLens zařízení, když se používají. Pokud ale nedojde k restartování, instalace požadované aktualizace by také pozdrží přijetí aktualizací. Přidali jsme zásady, které IT umožňují vynucovat konečné termíny a požadovaná restartování a zajistit, aby se instalace aktualizace dokončila včas. Uživatelé mohou být upozorněni před zahájením restartování a mohou restartování zpozdit v souladu se zásadami IT.

Byly přidány následující zásady aktualizace:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Aktualizace/konfiguraceDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Aktualizace/konfiguraceDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Aktualizace/konfiguraceDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Aktualizace/konfiguraceDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

Nově povolená pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jedno časové datum pro restartování aplikací, jejichž aktualizace selhala kvůli tomu, že se aplikace používá a umožňuje instalaci aktualizace. Můžete je nastavit na základě několika různých triggerů, jako je naplánovaný čas nebo přihlášení. Další informace o použití této zásady najdete v tématu [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používejte jenom aplikace pro privátní Microsoft Store

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se v aplikaci nakonfiguroval jenom privátní obchod nakonfigurovaný pro vaši organizaci. Omezení přístupu pouze na aplikace, které jste k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>Použití aplikací WDAC a LOB

Pomocí nástroje WDAC teď můžete aplikacím nebo procesům zablokovat spouštění a dál používat vlastní řadu aplikací pro pohotové prostředí. Teď je můžete povolit v zásadách WDAC. Použití této zásady zahrnuje spuštění dodatečného řádku kódu v PowerShellu při vytváření zásad WDAC. [Postup najdete tady.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

- Byl opraven známý problém s Portál zařízení, kdy se při stahování uzamčených souborů nic [nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Řeší problémy související s hlášením vlastností dodržování předpisů HoloLens zařízeními. K aktivaci správných sestav v sestaveních Insider může být nutné restartovat počítač.  
- Povolili [jste rozhraní API pro](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) přiřazený přístup, aby aplikace teď pro uživatele přihlášeného k HoloLens mohli určit, jestli je spuštěná HoloLens.
- Aktualizace dodácí verze Remote Assistu, která je nainstalovaná na aktuálních flash serverech.

## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider

> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.
>
> - Hlasový příkaz Restartovat zařízení funguje dobře.
> - Můžete také zvolit tlačítko restartování v Nastavení/Windows Insider Program.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení**  >  **Update & Security**  >  **Windows Insider Program** a vyberte **Začínáme.** Propojte účet, který jste použili k registraci, Windows Insider.

Windows insider se teď přesouvá na Kanály. Kanál **Fast** se stane vývojový **kanál,** kanál **Slow** se stane **kanálem Beta kanál** a kanál release **preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle:

![Windows Vysvětlení kanálů insider.](images/WindowsInsiderChannels.png)

Další informace najdete v článku [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blogech.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **buildy,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte do Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.

### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky

Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.

#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview

1. Nastavení, & Security a Windows Insider Program vyberte **Kanál Release Preview.**

2. Nastavení, Aktualizace & Security, Windows Update, Kontrola **aktualizací**. Po aktualizaci pokračujte k fázi 2.

#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál

1. Nastavení, Aktualizovat & Security, Windows Insider Program vyberte **Dev Channel**.

2. Nastavení, Aktualizace & Security, Windows Update, Kontrola **aktualizací**.

## <a name="ffu-download-and-flash-directions"></a>Pokyny ke stažení ffu a flash

Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.

1. Na počítači:
    1. Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

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

1. přejít na **Nastavení > systému > o** a najít číslo sestavení.

1. [Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).

Odhlášení od buildů Insider:

1. na HoloLens, na kterém běží výrobní sestavení, navštivte **Nastavení > Update & Security > Windows Insider** a vyberte zastavit buildy **Insider**.

1. Pokud chcete zařízení odhlásit, postupujte podle pokynů.
