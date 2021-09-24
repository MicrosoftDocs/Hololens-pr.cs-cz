---
title: Insider preview pro Microsoft HoloLens
description: Zjistěte, jak začít se sestaveními Insider a poskytnout cennou zpětnou vazbu pro naši další velkou aktualizaci operačního systému pro HoloLens.
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
ms.openlocfilehash: 68485fd0ad7f050748a412da3d57eb8f59e9a685
ms.sourcegitcommit: d09556a101663ef5dfff865d4753e64a41032b78
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/23/2021
ms.locfileid: "128346740"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview pro Microsoft HoloLens

Vítá vás nejnovější sestavení Insider Preview pro HoloLens! Začít a poskytnout cennou [zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi Insider

S radostí můžeme začít s novými funkcemi, které Windows Insiderům. Nové buildy budou přichytá k nejnovějším aktualizacím do kanálů pro vývoj a beta verze. Tuto stránku budeme dál aktualizovat, protože do našich buildů pro Windows Insider přidáme další funkce a aktualizace. Připravte se na kombinaci těchto aktualizací do vaší reality.

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
✔️ chcete nakonfigurovat, aby se vaše aplikace po neúspěchu aktualizace automaticky pokusily o aktualizaci, nastavte tohoto nového poskytovatele [CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto nově [povolené zásady aktualizací.](#improved-update-restart-detection-and-notifications) <br>
✔️ Pokud potřebujete, aby aplikace vaší organizace mohly být dostupné v obchodě společnosti přes Microsoft Store, ale chcete povolit přístup jenom k aplikacím vaší organizace, a ne k úplnému obchodu, [nastavte](#use-only-private-store-apps-for-microsoft-store)tuto zásadu. <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLens si tyto csP pro [generování sestav.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Pokud chcete pomocí nástroje WDAC blokovat spouštění aplikací nebo procesů, ale potřebujete také použít vlastní řadu aplikací pro obchodní aplikace, můžete teď v zásadách [WDAC](#use-wdac-and-lob-apps)povolit lob.

### <a name="moving-platform-mode"></a>Přesun režimu platformy

Od **buildu Insider 20348.1411** jsme přidali podporu beta verze pro sledování na platformách s pohyblivou nízkou dynamickou dynamikou na HoloLens 2. Po instalaci sestavení a povolení moving platformového režimu budete moct používat HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodi a velké lodi. V současné době je tato funkce zaměřená pouze na povolení těchto konkrétních pohyblivých platforem. I když vám nic nebrání ve pokusu o použití této funkce v jiných prostředích, tato funkce se zaměřuje nejprve na přidání podpory těchto prostředí.

Další informace o tom, co je podporováno a jak tuto novou funkci povolit, najdete [na stránce s pohyblivou platformou.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Přehled pro vyzkoušejte přesun režimu platformy

1. [Povolte vývojářský režim a portál zařízení.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Povolte přesouvání režimu platformy prostřednictvím portálu zařízení.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Převezměte své zařízení na velkou pohyblivý platformu a podívejte se, jak jsou stabilní hologramy.

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro Správce certifikátů

Zavedeno v Windows Insider buildu 20348.1405. Do Správce certifikátů jsme přidali [podporu](certificate-manager.md) pro použití certifikátů .pfx. Když uživatelé **přecházou Nastavení** Update & Security Certificates a vyberou Install a certificate (Nainstalovat certifikát), uživatelské rozhraní teď podporuje soubor certifikátu  >    >    .pfx.
Uživatelé mohou importovat certifikát .pfx s privátním klíčem do uživatelského úložiště nebo do úložiště počítače.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Přehled pro vyzkoušejte soubory PFX ve Správci certifikátů

1. Připravte soubor PFX.
1. Zkopírujte soubor do zařízení pomocí kabelu USB-C.
1. Otevřete aplikaci Nastavení, přejděte do [Správce certifikátů](certificate-manager.md) a použijte certifikát.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens

Pro spravovaná zařízení při řešení potíží je důležitým krokem potvrzení, že se používá očekávaná konfigurace zásad. V předchozích verzích této nové funkce bylo po exportu diagnostických protokolů MDM shromážděných prostřednictvím přístupu k účtům Nastavení Do práce nebo do školy provedeno zobrazení těchto informací ze zařízení přes MDM nebo blízko zařízení a vybrat Export protokolů správy a zobrazit ho na  ->    >  okolním počítači. 

Teď můžete diagnostiku MDM zobrazit na zařízení pomocí prohlížeče Edge. Pokud chcete sestavu diagnostiky MDM snadněji zobrazit, přejděte na stránku Přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu.** Tím se sestava vygeneruje a otevře v novém okně Edge.

![Zobrazení rozšířené diagnostické sestavy v Nastavení aplikaci](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Přehled pro vyzkoušejte pokročilou diagnostickou sestavu

1. Otevřete aplikaci Nastavení.
1. Přejděte na stránku Účty a klikněte na nový odkaz **Export protokolů správy.**
1. Zobrazení rozšířených informací o konfiguracích zařízení

### <a name="offline-diagnostics-notifications"></a>Offline diagnostická oznámení

Tato aktualizace pro existující funkci s názvem [Offline diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve se uživatelům nespouštěl jasný indikátor, že aktivoval shromažďování diagnostických dat nebo že se dokončilo.
V buildech Windows Insider jsou teď k dispozici dvě formy zpětné vazby k offline diagnostice. Prvními jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a má vizuály.

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
1. Všimněte si, že v kolekci protokolů je nový soubor uložený ve složce Documents (Dokumenty) HoloLens.

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

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se v aplikaci nakonfiguroval jenom privátní obchod nakonfigurovaný pro vaši [organizaci prostřednictvím Microsoft Store pro firmy](/microsoft-store/microsoft-store-for-business-overview). Omezení přístupu pouze na aplikace, které jste k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>Přehled pokusů o použití jenom aplikací privátního Storu

1. Nakonfigurujte nové zásady pro vaše zařízení přes [MDM.](hololens-mdm-configure.md)
1. Přihlaste se k zařízení, které má zásady.
1. Otevřete aplikaci Microsoft Store a sledujte, jak vidíte jenom aplikace vaší organizace.

### <a name="use-wdac-and-lob-apps"></a>Použití aplikací WDAC a LOB

Teď můžete pomocí WDAC blokovat spouštění aplikací nebo procesů a dál používat vlastní řádek aplikací bushiness. Teď je můžete v zásadách WDAC zapnout. Použití těchto zásad zahrnuje při vytváření zásad WDAC spuštění dalšího řádku kódu v PowerShellu. [Projděte si tento postup](/mem/intune/configuration/custom-profile-hololens).

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Přehled, jak vyzkoušet vlastní aplikace při použití WDAC k blokování dalších uživatelů

1. Shromážděte AUMIDs aplikace LOB a aplikace, které chcete blokovat.
1. [Vytvořte novou zásadu WDAC](/mem/intune/configuration/custom-profile-hololens) podle nového postupu.
1. [Nasaďte zásady pomocí MDM](hololens-mdm-configure.md) do svého zařízení.
1. Přihlaste se k zařízení a sledujte, jak můžete spustit aplikaci a zablokovat ostatním.

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

#### <a name="for-developers"></a>Pro vývojáře

- Opravili [jsme známý problém s portálem zařízení, kde se nestáhly uzamčené soubory](hololens-troubleshooting.md#downloading-locked-files-doesnt-error).
- Opravili jsme [známý problém s portálem zařízení s časovým limitem nahrávání a stahování souborů](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out).
- Zpracování přes Gamepad pro 2D aplikace bylo v buildech Insider zakázáno. Když je odeberete, aplikace teď zdarma používají rozhraní API pro Gamepad a mají přístup k celé sadě ovládacích prvků a je možné je vyvíjet na více případech. Vývojáři by měli používat rozhraní API Gamepad pro využívání vstupu přes Gamepad. Tady je ukázka pro [třídu Gamepad (Windows. hraní her. Input) – Windows aplikací UWP](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- povolili jste [přiřazené přístupové rozhraní API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) , takže aplikace teď můžou určit, jestli HoloLens běží v celoobrazovkovém režimu pro uživatele přihlášeného k HoloLens.

#### <a name="for-enterprise"></a>Pro Enterprise

- řeší problémy při vytváření sestav vlastností dodržování předpisů z HoloLens zařízení; pro spuštění správných sestav na buildech Insider může být nutné restartovat počítač.  
- Aktualizace integrované verze vzdálené pomoci, která je nainstalovaná na nových bliknutích
- Opravili jsme problém, když se po prvním přihlášení uživatele ve scénářích, kde se používají konfigurace veřejného terminálu na základě skupin AAD, ukončilo počáteční nastavení.
- Byl opraven problém s zobrazením oznámení o aktualizacích a výzev k restartování zařízení.
- opravili jsme problém, kdy po restartování zařízení je potřeba znovu párovat řadiče Xbox a další periferní zařízení Bluetooth LE, aby se mohla připojit.

## <a name="start-receiving-insider-builds"></a>Zahájit přijímání buildů Insider

> [!NOTE]
> Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.
>
> - Hlasový příkaz "restartovat zařízení" dobře funguje.
> - můžete také zvolit tlačítko restartovat v programu Nastavení/Windows Insider.
>
> Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.

na zařízení HoloLens 2 přejít do **Nastavení**  >  **Update & Security**  >  **Windows Program Insider** a vyberte začínáme . propojte účet, který jste použili k registraci jako Windows Insider.

> [!NOTE]
> Aby bylo možné zaregistrovat zařízení v buildech Insider, budete muset povolit volitelnou telemetrii. pokud jste to ještě neudělali, otevřete aplikaci Nastavení a vyberte možnost diagnostika **osobních údajů**  ->  **& zpětná vazba** a pak vyberte **volitelná diagnostická data**.

Windows insider se teď přesouvá na kanály. **Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**. Toto mapování vypadá takto:

![Windows Vysvětlení kanálů Insider.](images/WindowsInsiderChannels.png)

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

1. přejít na **Nastavení > systému > o** a najít číslo sestavení.

1. [Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).

Odhlášení od buildů Insider:

1. na HoloLens, na kterém běží výrobní sestavení, navštivte **Nastavení > Update & Security > Windows Insider** a vyberte zastavit buildy **Insider**.

1. Pokud chcete zařízení odhlásit, postupujte podle pokynů.
