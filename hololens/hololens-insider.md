---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít s buildy Insider, a poskytněte vám užitečnou zpětnou vazbu k naší další aktualizaci operačního systému HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: bdfdcda8cc890691f6112e7798d402ca9e7f4c6d
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904306"
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
✔️ Pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto [nově povolené zásady aktualizace](#improved-update-restart-detection-and-notifications). <br>
pokud potřebujete, aby byly aplikace vaší organizace dostupné v obchodě společnosti prostřednictvím Microsoft Store, ale chcete přístup jenom k aplikacím vaší organizace a nikoli k úplnému úložišti, [nastavte tuto zásadu](#use-only-private-store-apps-for-microsoft-store). ✔️ <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLensch zařízení se podívejte na tyto [zprostředkovatele csp pro vytváření sestav](#csp-changes-for-reporting-hololens-details). <br>
✔️ Pokud chcete používat WDAC k blokování spouštění aplikací nebo procesů, ale také potřebujete použít vlastní řádek aplikací bushiness, můžete teď [ve svých zásadách pro WDAC dovolit LOB](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Přesun režimu platformy

od buildu **Insider 20348,1411** jsme přidali podporu beta pro sledování na vysoce dynamických pohybových platformách na HoloLens 2. po instalaci sestavení a povolení režimu přesunu platforem budete moci použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské lodi. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

Další informace o tom, co je podporováno a jak povolit tuto novou funkci, [najdete na stránce přesun platformy](hololens2-moving-platform.md).

#### <a name="overview-to-try-out-moving-platform-mode"></a>Přehled pro vyzkoušení režimu přesunu platforem

1. [Povolí vývojářský režim a portál zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. [Povolte přesunutí režimu platforem prostřednictvím portálu zařízení](hololens2-moving-platform.md#enabling-moving-platform-mode).
1. Využijte své zařízení na velkou přesunovou platformu a sledujte, jak jsou to stabilní hologramy.

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro správce certifikátů

představeno v Windows build Insider build 20348,1405. Přidali jsme podporu [Správce certifikátů](certificate-manager.md) pro teď použití certifikátů. pfx. když uživatel přejde na **Nastavení**  >  **Update &**  >  **certifikáty** zabezpečení a vybere možnost **nainstalovat certifikát** , uživatelské rozhraní teď podporuje soubor certifikátu. pfx.
Uživatelé mohou importovat certifikát. pfx s privátním klíčem do úložiště uživatele nebo do úložiště počítače.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Přehled vyzkoušení souborů PFX ve Správci certifikátů

1. Připravte soubor PFX.
1. Zkopírujte soubor do zařízení pomocí kabelu USB-C.
1. otevřete aplikaci Nastavení a přejděte do [správce certifikátů](certificate-manager.md) a použijte certifikát.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens

Pro spravovaná zařízení při řešení potíží ověřte, že se používá očekávaná konfigurace zásad, což je důležitý krok. před touto novou funkcí se tyto informace musely po exportu protokolů pro diagnostiku mdm shromážděných prostřednictvím **Nastavení**  ->  **účtů**  >  **přistupovat do práce nebo do školy** a vybrat možnost **exportovat protokoly pro správu** a zobrazit je v blízkosti počítače.

Diagnostiku MDM je teď možné zobrazit na zařízení pomocí prohlížeče Edge. Chcete-li snadněji zobrazit diagnostickou zprávu MDM, přejděte na stránku přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu**. Tato akce vygeneruje a otevře sestavu v novém okně Edge.

![zobrazit pokročilou diagnostickou sestavu v aplikaci Nastavení.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Přehled a vyzkoušejte si pokročilou diagnostickou sestavu

1. Otevřete aplikaci Nastavení.
1. Přejděte na stránku Účty a klikněte na nový odkaz **Export protokolů správy.**
1. Zobrazení rozšířených informací o konfiguracích zařízení

### <a name="offline-diagnostics-notifications"></a>Offline diagnostická oznámení

Tato aktualizace pro existující funkci s názvem [Offline diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve se uživatelům nespouštěl jasný indikátor, že aktivoval shromažďování diagnostických dat nebo že se dokončilo.
Nyní přidaná Windows sestavení Insider existují dvě formy zpětné vazby k offline diagnostice. Prvními jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a má vizuály.

![Informační zprávy pro shromažďování protokolů](./images/logcollection1.jpg)

![Informační zpráva po dokončení shromažďování protokolů](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus shromažďování protokolů, když nemají přístup k zobrazení, nemůže se přihlásit nebo jsou stále v OOBE, bude se při shromažďování protokolů přehrávat také zvukové signály. Tento zvuk se přehraje spolu s informační zprávou.

Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná. Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.

Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Přehled pro vyzkoušejte si diagnostická oznámení

1. Odemkněte zařízení a ošetřte ho.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Prohlédněte si informační zprávy a poslechu zvukových upozornění, kdy se zařízení spustí a dokončí shromažďování protokolů.

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se zdá, že zařízení má při shromážděných diagnostických protokolech nedostatek místa na disku, vytvoří se **StorageDiagnostics.zip** sestava s názvem . Prahovou hodnotu nízkého úložiště určuje automaticky Windows [úložiště.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Přehled pro vyzkoušejte vylepšení nízkého úložiště

1. Vyplňte prostor úložiště zařízení.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Všimněte si, že v kolekci protokolů je nový soubor uložený ve složce Dokumenty ve vaší HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny CSP pro podrobnosti HoloLens sestav

- Zavedeno v Windows Insider, 20348.1403

Následující csP se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Bezplatná Storage

DevDetail CSP teď také hlásí volné místo úložiště na HoloLens zařízení. Tato hodnota by se měla přibližně shodovat s hodnotou Nastavení na stránce Storage aplikace. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP teď také hlásí SSID a BSSID Wi-Fi sítě, HoloLens je aktivně připojená. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

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

Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlásí. Někteří zákazníci chtějí nastavit zařízení, která jsou svázaná s identitou, ale nechcete žádné přihlašovací prostředí. Imagine zařízení a okamžité použití vzdálené pomoci. Nebo můžete mít výhodu, že dokážete rychle distribuovat HoloLens zařízení a umožnit koncovým uživatelům urychlit přihlášení.

Pokud je zásada nastavená na neprázdnou hodnotu, určuje e-mailovou adresu uživatele s automatickým přihlášením. Zadaný uživatel se musí alespoň jednou přihlásit k zařízení, aby se umožnilo automatické přihlášení.

OMA-URI nové hodnoty řetězce `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` zásad

- Uživatel se stejnou e-mailovou adresou bude mít povolené automatické přihlášení.

Na zařízení, kde je tato zásada nakonfigurovaná, se musí uživatel zadaný v zásadách alespoň jednou přihlásit. Po dalším restartování zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí. Podporuje se jenom jeden uživatel s automatickým přihlášením. Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, mohou vyžadovat, aby se zadaný uživatel k zařízení znovu přihlásit, aby obnovoval chování automatického přihlášení.
> - Automatické přihlášení se podporuje jenom pro uživatele MSA a AAD.

#### <a name="overview-to-try-auto-logon-csp"></a>Přehled pokusu o automatické přihlášení poskytovatele CSP

1. Nakonfigurujte nového poskytovatele CSP pro požadovaného uživatele [pomocí vlastních zásad:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Použijte poskytovatele CSP na zařízení prostřednictvím [zřizovacího balíčku](hololens-provisioning.md) nebo [MDM.](hololens-mdm-configure.md)
1. Přihlaste se k zadanému účtu.
1. Restartujte zařízení a sledujte, jak se uživatel automaticky přihlásí.

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

#### <a name="overview-to-try-new-update-notifications"></a>Přehled pro pokusy o oznámení o nových aktualizacích

1. Nakonfigurujte jednoho z nových aktualizačních csP prostřednictvím [zřizovacího balíčku](hololens-provisioning.md) nebo [MDM](hololens-mdm-configure.md) (viz výše uvedený seznam odkazů a vyberte jednoho).
1. Během naplánovaného času zařízení používejte.
1. Všimněte si, že uživatel je na aktualizaci upozorněn a že je potřeba zařízení \* restartovat.

\* Vaše výsledky se můžou lišit v závislosti na použitých zásadách aktualizace.

### <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

Nově povolená pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jedno časové datum pro restartování aplikací, jejichž aktualizace selhala kvůli tomu, že se aplikace používá a umožňuje instalaci aktualizace. Můžete je nastavit na základě několika různých triggerů, jako je naplánovaný čas nebo přihlášení. Další informace o použití této zásady najdete v tématu [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Přehled pro pokus o inteligentní opakování aktualizací aplikací

1. Nakonfigurujte novou funkci inteligentního opakování.
1. Na zařízení, které ještě vaši aplikaci nepřijímá a je správně nakonfigurované, se přihlaste do online prostředí.
1. Zajistěte, aby zařízení nemohlo stáhnout aplikaci vypnutím nebo odpojením.
1. Během aktivované doby musí být zařízení zapnuté a připojené k internetu, aby se pokus o stažení zopakovat.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používejte jenom aplikace pro privátní Microsoft Store

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se pro vaši organizaci nakonfiguroval jenom privátní obchod. Omezení přístupu pouze na aplikace, které jste k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>Přehled pokusů o použití jenom aplikací privátního Storu

1. Nakonfigurujte nové zásady pro vaše zařízení přes [MDM.](hololens-mdm-configure.md)
1. Přihlaste se k zařízení, které má zásady.
1. Otevřete aplikaci Microsoft Store a sledujte, jak vidíte jenom aplikace vaší organizace.

### <a name="use-wdac-and-lob-apps"></a>Použití aplikací WDAC a LOB

Pomocí nástroje WDAC teď můžete aplikacím nebo procesům zablokovat spouštění a dál používat vlastní řadu aplikací pro pohotové prostředí. Teď je můžete povolit v zásadách WDAC. Použití této zásady zahrnuje spuštění dodatečného řádku kódu v PowerShellu při vytváření zásad WDAC. [Postup najdete tady.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Přehled pro pokusy o vlastní aplikace při použití nástroje WDAC k blokování ostatních

1. Shromážděte identifikátory AUMID vaší obchodní aplikace a aplikace, které chcete blokovat.
1. Podle nových kroků vytvořte novou zásadu [WDAC.](/mem/intune/configuration/custom-profile-hololens)
1. [Nasaďte zásadu pomocí MDM](hololens-mdm-configure.md) do zařízení.
1. Přihlaste se k zařízení a sledujte, jak můžete aplikaci spustit a blokovat ostatní.

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

- Byl opraven známý problém s Portál zařízení, kdy se při stahování uzamčených souborů [nic nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Řeší problémy související s hlášením vlastností dodržování předpisů HoloLens zařízeními. K aktivaci správných sestav v sestaveních Insider může být nutné restartovat počítač.  
- Povolili [jste rozhraní API pro](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) přiřazený přístup, aby aplikace teď mohli určit, jestli je HoloLens spuštěný v bezna meziobrazovkovém režimu pro uživatele přihlášeného k HoloLens.
- Aktualizace dodácí verze Remote Assistu, která je nainstalovaná na aktuálních flash serverech.
- Zpracování Gamepadu pro 2D aplikace bylo ve buildech Insider zakázané. Když je odeberete, aplikace teď mohou rozhraní GAMEPAD API používat přímo a mají přístup k celé sadě ovládacích prvků a mohou dělat, co chtějí. Vývojáři by měli ke vstupu Gamepadu používat rozhraní API Gamepadu. Tady je ukázka třídy [Gamepad (Windows. Gaming.Input) – Windows aplikace pro UPW.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Opravili jsme problém, kdy se po prvním přihlášení uživatele oOBE ukončuje ve scénářích, kdy se používaly konfigurace veřejného terminálů založené na skupině AAD.
- Opravil se problém se zobrazováním oznámení o aktualizacích a dialogových vý okno s výzvou k restartování zařízení.

## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider

> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.
>
> - Hlasový příkaz Restartovat zařízení funguje dobře.
> - Můžete také zvolit tlačítko pro restartování v Nastavení/Windows Insider Program.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení** Update & Security Windows Insider Program a  >    >   vyberte **Začínáme.** Propojte účet, který jste použili k registraci, Windows Insider.

> [!NOTE]
> Pokud chcete své zařízení zaregistrovat v buildech Insider, budete muset povolit volitelnou telemetrii. Pokud jste to ještě neudělali, otevřete aplikaci **Nastavení,** vyberte Diagnostika ochrany osobních údajů a & a pak  ->   vyberte **Volitelná diagnostická data**.

Windows insider se teď přesouvá na Kanály. Kanál **Fast** se stane vývojový **kanál,** kanál **Slow** se stane **kanálem Beta kanál** a kanál verze **Preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle:

![Windows Vysvětlení kanálů insider.](images/WindowsInsiderChannels.png)

Další informace najdete v tématu [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blozích.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **sestavení,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte do Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.

### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky

Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.

#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview

1. Nastavení, & Security a Windows Insider Program vyberte Kanál Release **Preview.**

2. Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**. Po aktualizaci pokračujte k fázi 2.

#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál

1. Nastavení, & Security a Windows Insider Program vyberte **Dev Channel**.

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

Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic bez programu Insider.

> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:

1. Přejděte na Nastavení > System > About (O **produktu)** a vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním buildu přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte **Zastavit sestavení Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
