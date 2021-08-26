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
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859013"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview pro Microsoft HoloLens

Vítá vás nejnovější sestavení Insider Preview pro HoloLens! Začít a poskytnout cennou [zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi Insider

S radostí můžeme začít s novými funkcemi, které Windows Insiders. Nové buildy budou přichytá k nejnovějším aktualizacím do kanálů pro vývoj a beta verze. Tuto stránku budeme dál aktualizovat, protože do našich buildů pro Windows Insider přidáme další funkce a aktualizace. Připravte se na kombinaci těchto aktualizací do vaší reality.

Toto je o vylepšených řešeních potíží a sestavách zařízení, některých opravených chybách v beznaiosku a prohlížeči certifikátů, rozšířené možnosti správy a zvýšené spolehlivosti aktualizací. Novou hlavní funkcí této aktualizace funkcí, která se HoloLens, je náš režim moving platformy. Podívejte se na všechny nové skvělé funkce pro HoloLens 2!

| Funkce                 | Popis                | Uživatel nebo scénář | Zavedené sestavení |
|-------------------------|----------------------------|--------------|------------------|
| [Přesun režimu platformy](#moving-platform-mode) | Představuje režim moving platformy beta, který po nakonfigurování umožňuje použití funkce HoloLens 2 u velkých velkého sádrohováka, u kterých dochází k nízkému dynamickému pohybu. | Vše | 20348.1411 |
| [Podpora souborů PFX pro Správce certifikátů](#pfx-file-support-for-certificate-manager) | Přidání certifikátu PFX prostřednictvím Nastavení uživatelského rozhraní | Koncový uživatel | 20348.1405 |
| [Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazení diagnostických protokolů MDM na zařízení | Řešení potíží | 20348.1405 |
| [Offline diagnostická oznámení](#offline-diagnostics-notifications) | Zpětná vazba k shromažďování protokolů | Řešení potíží | 20348.1405 |
| [Vylepšení shromažďování protokolů s nízkým úložištěm](#low-storage-log-collection-improvements) | Vylepšení scénářů shromažďování protokolů v situacích s nízkým úložištěm | Řešení potíží | 20348.1412 |
| [Změny CSP pro generování HoloLens sestav](#csp-changes-for-reporting-hololens-details) | Noví csp pro dotazování dat | Správci IT    | 20348.1403                 |
| [Zásady automatického přihlášení řízené poskytovatelem CSP](#auto-login-policy-controlled-by-csp) | Slouží k automatickému přihlášení účtu. | Správci IT | 20348.1405 |
| [Vylepšená detekce restartování aktualizací a oznámení](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské prostředí pro aktualizace | Správci IT | 20348.1405 |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánovat opakování aktualizací aplikací. | Správci IT | 20348.1405 |
| [Používejte jenom aplikace privátního Storu pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby se v aplikaci zobrazují jenom aplikace z organizace | Správce IT | 20348.1408 |
| [Použití aplikací WDAC a LOB](#use-wdac-and-lob-apps) | Umožňuje správcům IT používat vlastní aplikace a pořád používat WDAC k blokování jiných aplikací. | Správci IT | 20348.1405 |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení pro HoloLens. | Vše | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Kontrolní seznam funkcí insiderského správce IT

✔️ Pokud chcete nastavit jeden účet Azure AD pro automatické přihlášení, [nakonfigurujte tohoto nového poskytovatele CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Pokud chcete nakonfigurovat, aby se vaše aplikace po neúspěchu aktualizace automaticky pokusily o aktualizaci, nastavte tohoto nového poskytovatele [CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ Pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto nově [povolené zásady aktualizací.](#improved-update-restart-detection-and-notifications) <br>
✔️ Pokud potřebujete, aby aplikace vaší organizace mohly být dostupné v obchodě společnosti přes Microsoft Store, ale chcete povolit přístup jenom k aplikacím vaší organizace, a ne k úplnému obchodu, [nastavte tuto zásadu.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLens csP pro [generování sestav.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Pokud chcete použít WDAC k blokování spouštění aplikací nebo procesů, ale potřebujete také použít vlastní aplikace pro připojení, můžete teď ve svých zásadách [WDAC](#use-wdac-and-lob-apps)povolit lob.

### <a name="moving-platform-mode"></a>Přesun režimu platformy

Od **buildu Insider 20348.1411** jsme přidali podporu beta verze pro sledování na platformách s pohyblivou nízkou dynamickou dynamikou na HoloLens 2. Po instalaci buildu a povolení moving platformového režimu budete moct používat HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodi a velké lodi. V současné době je tato funkce zaměřená pouze na povolení těchto konkrétních pohyblivých platforem. I když vám nic nebrání ve pokusu o použití této funkce v jiných prostředích, tato funkce se zaměřuje nejprve na přidání podpory těchto prostředí.

Další informace o tom, co je podporováno a jak tuto novou funkci povolit, najdete [na stránce s pohyblivou platformou.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro Správce certifikátů

Zavedeno v Windows Insider buildu 20348.1405. Do Správce certifikátů jsme přidali [podporu](certificate-manager.md) pro použití certifikátů .pfx. Když uživatelé **přecházou Nastavení** Update & Security Certificates a vyberou Install a certificate (Nainstalovat certifikát), uživatelské rozhraní teď podporuje soubor certifikátu  >    >    .pfx.
Uživatelé mohou importovat certifikát .pfx s privátním klíčem do uživatelského úložiště nebo do úložiště počítače.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens

Pro spravovaná zařízení při řešení potíží je důležitým krokem potvrzení, že se používá očekávaná konfigurace zásad. V předchozích verzích této nové funkce bylo po exportu diagnostických protokolů MDM shromážděných prostřednictvím přístupu k účtům Nastavení Do práce nebo do školy provedeno zobrazení těchto informací ze zařízení přes MDM nebo blízko zařízení a vybrat Export protokolů správy a zobrazit ho na  ->    >  okolním počítači. 

Teď můžete diagnostiku MDM zobrazit na zařízení pomocí prohlížeče Edge. Pokud chcete sestavu diagnostiky MDM snadněji zobrazit, přejděte na stránku Přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu.** Tím se sestava vygeneruje a otevře v novém okně Edge.

![Zobrazení rozšířené diagnostické sestavy v Nastavení aplikaci](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnostická oznámení

Tato aktualizace pro existující funkci s názvem [Offline diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve nebyl pro uživatele žádný jasný indikátor, že aktivoval shromažďování diagnostických dat nebo že se dokončilo.
Nyní přidaná Windows sestavení Insider existují dvě formy zpětné vazby k offline diagnostice. Prvními jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a má vizuály.

![Informační zprávy pro shromažďování protokolů](./images/logcollection1.jpg)

![Informační zpráva po dokončení shromažďování protokolů](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus shromažďování protokolů, když nemají přístup k zobrazení, nemůže se přihlásit nebo jsou stále v OOBE, bude se při shromažďování protokolů přehrávat také zvukové signály. Tento zvuk se přehraje spolu s informační zprávou.

Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná. Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.

Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se zdá, že zařízení má při shromážděných diagnostických protokolech nedostatek místa na disku, vytvoří se **StorageDiagnostics.zip** sestava s názvem . Prahová hodnota nízkého úložiště se určuje automaticky Windows [úložiště.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny CSP pro generování HoloLens sestav

- Zavedeno v Windows Insider build, 20348.1403

Následující csP se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Bezplatná Storage

DevDetail CSP teď také hlásí volné místo úložiště na HoloLens zařízení. Tato hodnota by se měla přibližně shodovat s hodnotou Nastavení na stránce Storage aplikace. Následuje konkrétní uzel, který tyto informace obsahuje.

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

Na zařízení, kde je tato zásada nakonfigurovaná, se musí uživatel zadaný v zásadách alespoň jednou přihlásit. Při dalších restartováních zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí. Podporuje se jenom jeden uživatel s automatickým přihlášením. Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, mohou vyžadovat, aby se zadaný uživatel k zařízení znovu přihlásit, aby obnovoval chování automatického přihlášení.
> - Automatické přihlášení se podporuje pouze pro uživatele MSA a AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Vylepšená detekce restartování aktualizací a oznámení

Mezi aktivními hodinami a zásadami doby instalace je možné se vyhnout restartování HoloLens zařízení, když se používají. Pokud ale nedojde k restartování, instalace požadované aktualizace by také pozdrží přijetí aktualizací. Přidali jsme zásady, které IT umožňují vynutit konečné termíny a požadovaná restartování a zajistit, aby se instalace aktualizace dokončila včas. Uživatelé mohou být upozorněni před zahájením restartování a mohou restartování zpozdit v souladu se zásadami IT.

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

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se pro vaši organizaci nakonfiguroval jenom privátní obchod. Omezení přístupu pouze na aplikace, které jste si z dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>Použití aplikací WDAC a LOB

Pomocí nástroje WDAC teď můžete aplikacím nebo procesům zablokovat spouštění a dál používat vlastní řadu aplikací pro pohotové prostředí. Teď je můžete povolit v zásadách WDAC. Použití této zásady zahrnuje spuštění dodatečného řádku kódu v PowerShellu při vytváření zásad WDAC. [Postup najdete tady.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

- Opravili jsme známý problém pro Portál zařízení, kdy se při stahování uzamčených souborů [nestahují žádné výzvy.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Řeší problémy související s hlášením vlastností dodržování předpisů HoloLens zařízeními. K aktivaci správných sestav v sestaveních Insider může být nutné restartovat počítač.  
- Povolili [jste rozhraní API pro](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) přiřazený přístup, aby aplikace teď pro uživatele přihlášeného k HoloLens mohli určit, jestli je v beznabovém režimu spuštěná HoloLens.
- Aktualizace dodácí verze Remote Assistu, která je nainstalovaná na aktuálních flash serverech.

## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider

> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.
>
> - Hlasový příkaz Restartovat zařízení funguje dobře.
> - Můžete také zvolit tlačítko restartování v Nastavení/Windows Insider Program.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení** Update & Security Windows Insider Program a  >    >   vyberte **Začínáme.** Propojte účet, který jste použili k registraci, Windows Insider.

Windows insider se teď přesouvá na Kanály. Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál verze **Preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle:

![Windows Vysvětlení kanálů insider](images/WindowsInsiderChannels.png)

Další informace najdete v tématu [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blogech.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **buildy,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte na stránku **Nastavení > Update & Security >** Vyhledejte aktualizace a získejte nejnovější sestavení.

### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky

Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.

#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview

1. Nastavení, Aktualizovat & Security, Windows Insider Program vyberte **Kanál Release Preview.**

2. Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**. Po aktualizaci pokračujte k fázi 2.

#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál

1. Nastavení, Update & Security, Windows Insider Program vyberte **Dev Channel**.

2. Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**.

## <a name="ffu-download-and-flash-directions"></a>Pokyny ke stažení ffu a flash

Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.

1. Na počítači:
    1. Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Na HoloLens – Letové odemčení: Otevřete **Nastavení** Update & Security Windows Insider Program a pak  >    >   se zaregistrujte a restartujte zařízení.

1. Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.

### <a name="provide-feedback-and-report-issues"></a>Poskytnutí zpětné vazby a hlášení problémů

Pokud chcete [poskytnout zpětnou Centrum Feedback a nahlásit problémy,](hololens-feedback.md) HoloLens aplikaci na svém počítači. Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.  Problémy s čínským a japonském HoloLens by měly být hlášeny stejným způsobem.

> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete Centrum Feedback ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).

## <a name="note-for-developers"></a>Poznámka pro vývojáře

Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí sestavení Insider HoloLens.  Pokud chcete [začít, HoloLens se podívejte do dokumentace pro](https://developer.microsoft.com/windows/mixed-reality/development) vývojáře. Stejné pokyny fungují i se sestaveními insider HoloLens.  Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavení přijímání sestavení Insider

Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není součástí programu Windows.

> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v dalších informacích o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:

1. Přejděte na Nastavení > System > About (O **produktu) a** vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro produkční čísla sestavení](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním sestavení přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
