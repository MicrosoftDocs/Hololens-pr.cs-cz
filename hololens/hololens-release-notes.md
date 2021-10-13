---
title: HoloLens 2 k vydání verze
description: Aktuální informace o všech aktualizacích v každé nové verzi HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: c45a9a05cc7911bc9866df5e4313bc27a205d333
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924473"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 k vydání verze

Pro zajištění produktivního prostředí s vašimi HoloLens zařízeními pokračujeme ve vydání funkcí, chyb a aktualizací zabezpečení. Na této stránce se můžete podívat, co je nového HoloLens každý měsíc. Pokud chcete získat nejnovější aktualizaci HoloLens 2, [](hololens-update-hololens.md#check-for-updates-and-manually-update) můžete aktualizace vyhledat a ručně aktualizovat, nebo získat úplnou aktualizaci Flash Update (FFU) k flashování zařízení prostřednictvím [doprovodné funkce Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) Stahování [je](https://aka.ms/hololens2download) stále aktuální a poskytuje nejnovější obecně dostupné sestavení.

> [!NOTE]
> Nedávné oznámení Windows 11 se zaměřilo na verzi počítače Windows. Nedávno jsme spustili hlavní aktualizaci operačního systému na HoloLens 2. října [2021](#windows-holographic-version-21h2)a na základě zpětné vazby od zákazníků pracujeme na dalších nadcházejících verzích.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, verze 21H2

- Build 20348.1432

Windows Holographic verze 21H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a IT specialisty. Toto je o vylepšených řešeních potíží a sestavách zařízení, některých opravených chybách v beznaiosku a prohlížeči certifikátů, rozšířené možnosti správy a zvýšené spolehlivosti aktualizací. Novou hlavní funkcí této aktualizace funkcí, která se HoloLens, je náš režim moving platformy. Podívejte se na všechny nové skvělé funkce pro HoloLens 2!

Tato nejnovější verze je měsíční aktualizací verze 21H1, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční verzi na verzi 21H1 (build 20348). Na číslo sestavení se můžete podívat na obrazovce Nastavení > Informace a ověřit, že jste na nejnovějším dostupném buildu 20348.1432+. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

| Funkce                 | Popis                | Uživatel nebo scénář |
|-------------------------|----------------------------|--------------|
| [Přesun režimu platformy](#moving-platform-mode) | Představuje režim moving platformy beta, který po nakonfigurování umožňuje použití funkce HoloLens 2 u velkých velkého chůdy, u kterého dochází k nízkému dynamickému pohybu. | Vše |
| [Podpora souboru PFX pro Správce certifikátů](#pfx-file-support-for-certificate-manager) | Přidání certifikátu PFX prostřednictvím Nastavení uživatelského rozhraní | Koncový uživatel |
| [Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazení diagnostických protokolů MDM na zařízení | Řešení potíží |
| [Offline diagnostická oznámení](#offline-diagnostics-notifications) | Zpětná vazba k shromažďování protokolů | Řešení potíží |
| [Vylepšení shromažďování protokolů s nízkým úložištěm](#low-storage-log-collection-improvements) | Vylepšení scénářů shromažďování protokolů v situacích s nízkým úložištěm | Řešení potíží |
| [Změny CSP pro generování HoloLens sestav](#csp-changes-for-reporting-hololens-details) | Noví csp pro dotazování dat | Správci IT    |
| [Zásady automatického přihlášení řízené poskytovatelem CSP](#auto-login-policy-controlled-by-csp) | Slouží k automatickému přihlášení účtu. | Správci IT |
| [Vylepšená detekce restartování aktualizací a oznámení](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské prostředí pro aktualizace | Správci IT |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánovat opakování aktualizací aplikací. | Správci IT |
| [Používejte jenom aplikace privátního Storu jenom pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby se v aplikaci zobrazují jenom aplikace z organizace | Správce IT |
| [Použití aplikací WDAC a LOB](#use-wdac-and-lob-apps) | Umožňuje správcům IT používat vlastní aplikace a pořád používat WDAC k blokování jiných aplikací. | Správci IT |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení HoloLens. | Vše |

### <a name="it-admin-feature-checklist"></a>Kontrolní seznam funkcí správce IT

✔️ Pokud chcete nastavit jeden účet Azure AD pro automatické přihlášení, [nakonfigurujte tohoto nového poskytovatele CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Chcete-li nakonfigurovat aplikace tak, aby se po neúspěchu aktualizace automaticky pokusily o aktualizaci, nastavte tohoto nového poskytovatele [CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto nově [povolené zásady aktualizací.](#improved-update-restart-detection-and-notifications) <br>
✔️ Pokud potřebujete, aby aplikace vaší organizace dostupné v obchodě společnosti přes Microsoft Store, ale chcete povolit přístup jenom k aplikacím vaší organizace, a ne k úplnému obchodu, [nastavte tuto zásadu.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLens csP pro [generování sestav.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Chcete-li pomocí nástroje WDAC blokovat spouštění aplikací nebo procesů, ale potřebujete také použít vlastní řadu aplikací, můžete teď v zásadách [WDAC](#use-wdac-and-lob-apps)povolit obchodní aplikaci .

### <a name="moving-platform-mode"></a>Přesun režimu platformy

Od verze Windows Holographic jsme ve verzi [21H2](hololens-release-notes.md#windows-holographic-version-21h2) přidali beta verzi pro sledování na platformách s nízkým dynamickým pohybem na HoloLens 2. Po instalaci sestavení a povolení moving platformového režimu budete moci používat HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodi a velké lodi. V současné době je tato funkce zaměřená pouze na povolení těchto konkrétních pohyblivých platforem. I když vám nic nebrání ve pokusu o použití této funkce v jiných prostředích, tato funkce se zaměřuje nejprve na přidání podpory těchto prostředí.

Další informace o tom, co je podporováno a jak tuto novou funkci povolit, najdete [na stránce s pohyblivou platformou.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Přehled pro try out Moving Platform Mode (Přesun režimu platformy)

1. [Povolte vývojářský režim a portál zařízení.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Povolte přesouvání režimu platformy prostřednictvím portálu zařízení.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Převezměte své zařízení na velkou pohyblivý platformu a podívejte se, jak jsou stabilní hologramy.

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souboru PFX pro Správce certifikátů

Zavedeno v Windows Insider buildu 20348.1405. Do Správce certifikátů jsme přidali podporu pro [použití](certificate-manager.md) certifikátů .pfx. Když uživatelé **přecházou Nastavení** Update & Security Certificates a vyberou Install a certificate (Nainstalovat certifikát), uživatelské rozhraní teď podporuje soubor certifikátu  >    >    .pfx.
Uživatelé mohou importovat certifikát .pfx s privátním klíčem do uživatelského úložiště nebo do úložiště počítače.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Přehled pro vyzkoušejte soubory PFX ve Správci certifikátů

1. Připravte soubor PFX.
1. Zkopírujte soubor do zařízení pomocí kabelu USB-C.
1. Otevřete aplikaci Nastavení, přejděte do [Správce certifikátů](certificate-manager.md) a použijte certifikát.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens

Pro spravovaná zařízení při řešení potíží je důležitým krokem potvrzení, že se používá očekávaná konfigurace zásad. Dříve se tato nová funkce musela po exportu diagnostických protokolů MDM shromážděných přes přístup k účtům Nastavení do práce nebo do školy provést mimo zařízení přes MDM nebo blízko zařízení a vybrat Export protokolů správy a zobrazit se na okolním  ->    >  počítači. 

Teď můžete diagnostiku MDM zobrazit na zařízení pomocí prohlížeče Edge. Pokud chcete sestavu diagnostiky MDM snadněji zobrazit, přejděte na stránku Přístup do práce nebo do školy a vyberte **Zobrazit rozšířenou diagnostickou sestavu.** Tím se sestava vygeneruje a otevře v novém okně Edge.

![Zobrazení rozšířené diagnostické sestavy v Nastavení aplikaci](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Přehled pro vyzkoušejte pokročilou diagnostickou sestavu

1. Otevřete aplikaci Nastavení.
1. Přejděte na stránku Účty a klikněte na nový odkaz **Export protokolů správy.**
1. Zobrazení rozšířených informací o konfiguracích zařízení

### <a name="offline-diagnostics-notifications"></a>Offline diagnostická oznámení

Tato aktualizace pro existující funkci s názvem [Offline diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve se uživatelům nespouštěl jasný indikátor, že aktivoval shromažďování diagnostických dat nebo že se dokončilo.
Nyní jsme do [Windows Holographic verze 21H2](hololens-release-notes.md#windows-holographic-version-21h2)přidali dvě formy zpětné vazby k offline diagnostice. První jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a má vizuály.

![Informační zprávy pro shromažďování protokolů](./images/logcollection1.jpg)

![Informační zpráva po dokončení shromažďování protokolů](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus shromažďování protokolů, když nemají přístup k zobrazení, nelze se přihlásit nebo jsou stále v OOBE, bude se při shromažďování protokolů přehrávat také zvukové signály. Tento zvuk se přehraje spolu s informační zprávou.

Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná. Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.

Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.

Tyto informace si můžete prohlédnout později na stránce [s diagnostickými protokoly.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Přehled pro vyzkoušejte si diagnostická oznámení

1. Odemkněte zařízení a ošetřte ho.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Prohlédněte si informační zprávy a poslechu zvukových upozornění, kdy se zařízení spustí a dokončí shromažďování protokolů.

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se zdá, že zařízení má při shromážděných diagnostických protokolech nedostatek místa na disku, vytvoří se **StorageDiagnostics.zip** sestava s názvem . Prahová hodnota nízkého úložiště se určuje automaticky Windows [úložiště.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

Tyto informace si můžete prohlédnout později na stránce [s diagnostickými protokoly.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Přehled pro vyzkoušejte vylepšení nízkého úložiště

1. Vyplňte prostor úložiště zařízení.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Všimněte si, že v kolekci protokolů je nový soubor uložený ve složce Dokumenty ve vaší HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny CSP pro generování HoloLens sestav

Následující csP se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – Bezplatná Storage

DevDetail CSP teď také hlásí volné místo úložiště na HoloLens zařízení. Tato hodnota by se měla přibližně shodovat s hodnotou Nastavení na stránce Storage aplikace. Následuje konkrétní uzel, který tyto informace obsahuje.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP nyní také hlásí SSID a BSSID Wi-Fi sítě, se HoloLens je aktivně připojen. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

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

Na zařízení, kde je tato zásada nakonfigurovaná, se uživatel zadaný v zásadách musí alespoň jednou přihlásit. Při dalších restartováních zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí. Podporuje se jenom jeden uživatel s automatickým přihlášením. Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.

> [!NOTE]
>
> - Některé události, jako jsou hlavní aktualizace operačního systému, mohou vyžadovat, aby se zadaný uživatel k zařízení znovu přihlásit, aby obnovoval chování automatického přihlášení.
> - Automatické přihlášení se podporuje jenom pro MSA a AAD uživatele.

#### <a name="overview-to-try-auto-logon-csp"></a>Přehled pokusu o automatické přihlášení poskytovatele CSP

1. Nakonfigurujte nového poskytovatele CSP pro požadovaného uživatele [pomocí vlastních zásad:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Použijte poskytovatele CSP na zařízení prostřednictvím [zřizovacího balíčku](hololens-provisioning.md) nebo [MDM.](hololens-mdm-configure.md)
1. Přihlaste se k zadanému účtu.
1. Restartujte zařízení a sledujte, jak se uživatel automaticky přihlásí.

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

#### <a name="overview-to-try-new-update-notifications"></a>Přehled pro pokusy o oznámení o nových aktualizacích

1. Nakonfigurujte jednoho z nových aktualizačních csP prostřednictvím [zřizovacího balíčku](hololens-provisioning.md) nebo [MDM](hololens-mdm-configure.md) (viz výše uvedený seznam odkazů a vyberte jednoho).
1. Během naplánovaného času zařízení používejte.
1. Všimněte si, že uživatel je na aktualizaci upozorněn a že je potřeba zařízení \* restartovat.

\* Vaše výsledky se můžou lišit v závislosti na použitých zásadách aktualizace.

### <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

Nově povolená pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jedno časové datum pro restartování aplikací, jejichž aktualizace selhala kvůli tomu, že se aplikace používá a umožňuje instalaci aktualizace. Můžete je nastavit na základě několika různých triggerů, jako je naplánovaný čas nebo přihlášení. Další informace o použití této zásady najdete v tématu [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

Tyto informace najdete později v obchodě [s aplikacemi pro firmy](app-deploy-store-business.md)na stránce .

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Přehled pro pokus o inteligentní opakování aktualizací aplikací

1. Nakonfigurujte novou funkci inteligentního opakování.
1. Na zařízení, které ještě vaši aplikaci nepřijímá a je správně nakonfigurované, se přihlaste do online prostředí.
1. Zajistěte, aby zařízení nemohlo stáhnout aplikaci vypnutím nebo odpojením.
1. Během aktivované doby musí být zařízení zapnuté a připojené k internetu, aby se pokus o stažení zopakovat.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používejte jenom aplikace z privátního Microsoft Store

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se v aplikaci nakonfiguroval jenom privátní obchod nakonfigurovaný pro vaši organizaci [prostřednictvím Microsoft Store pro firmy](/microsoft-store/microsoft-store-for-business-overview). Omezení přístupu pouze na aplikace, které jste si z dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Tyto informace najdete později v obchodě [s aplikacemi pro firmy](app-deploy-store-business.md)na stránce .

#### <a name="overview-to-try-only-private-store-apps"></a>Přehled k pokusu o použití jenom aplikací privátního Storu

1. Nakonfigurujte nové zásady pro vaše zařízení přes [MDM.](hololens-mdm-configure.md)
1. Přihlaste se k zařízení, které má zásady.
1. Otevřete aplikaci Microsoft Store a sledujte, jak vidíte jenom aplikace vaší organizace.

### <a name="use-wdac-and-lob-apps"></a>Použití aplikací WDAC a LOB

Pomocí nástroje WDAC teď můžete aplikacím nebo procesům zablokovat spouštění a dál používat vlastní řadu aplikací pro pohotové prostředí. Teď je můžete povolit v zásadách WDAC. Použití této zásady zahrnuje spuštění dodatečného řádku kódu v PowerShellu při vytváření zásad WDAC. [Projděte si tento postup.](/mem/intune/configuration/custom-profile-hololens)

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
- opravili jsme problém, kdy se po prvním přihlášení uživatele ve scénářích, kdy se používaly AADé konfigurace na základě skupin, bylo ukončeno počáteční nastavení.
- Byl opraven problém s zobrazením oznámení o aktualizacích a výzev k restartování zařízení.
- opravili jsme problém, kdy po restartování zařízení je potřeba znovu párovat řadiče Xbox a další periferní zařízení Bluetooth LE, aby se mohla připojit.
- Pevný problém kodéru videa, který by při volání funkce Remote Assist mohl způsobit krátké zablokování odchozího videa. Wi-Fi ovladače a firmwaru se změní na "fragment a zfalšovat" Wi-Fi ohrožení zabezpečení.
- Wi-Fi ovladače a firmwaru se změní na "fragment a zfalšovat" Wi-Fi ohrožení zabezpečení.
- Při použití režimu přesunu platforem (MPM) bude odhad "vyhodnocený" průměrnou hustotou v krátké době. Tato hodnota při přesunu režimu platformy nahrazuje skutečnou závažnost.
- Pevná pravidelná Wobble v hologramech v režimu 3DoF nebo během ztráty sledování.
- Řeší problém, který má dopad na aktualizace verze 21H1/21H2 ze starších verzí.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holografická verze 20H2 – říjen 2021 Update

- Sestavení 19041,1168

Vylepšení a opravy v aktualizaci:

- tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet naše nejnovější buildy Windows holografické 21H2 verze.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holografická verze 21H1 – září 2021 – aktualizace

- Sestavení 20348,1018

Vylepšení a opravy v aktualizaci:

- Opravuje řešení problému, kdy může dojít k neočekávanému přechodu systémového času.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holografická verze 20H2 – září 2021 – aktualizace

- Sestavení 19041,1165

Vylepšení a opravy v aktualizaci:

- Opravuje řešení problému, kdy může dojít k neočekávanému přechodu systémového času.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holografická verze 21H1-srpen 2021 Update

- Sestavení 20348,1014

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který brání řadičům Xbox v práci s moderními aplikacemi s podporou řadičů.
- Vylepšená Diagnostika pro chyby aktualizace zařízení.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holografická verze 20H2-srpen 2021 Update

- Sestavení 19041,1161

Vylepšení a opravy v aktualizaci:

- tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet naše nejnovější buildy Windows holografické 21H1 verze.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holografická verze 21H1 – červenec 2021 Update

- Sestavení 20348,1010

Vylepšení a opravy v aktualizaci:

- Portál zařízení má rozšířené metody upozorňování zákazníka, když se v Průzkumníkovi souborů vyskytnou problémy s otevíráním uzamčených souborů.
- Nahrání souboru, stažení, přejmenování a odstranění je teď opravené při použití protokolu HTTPS ve všech podporovaných prohlížečích.
- opravili jsme problém, kdy Wi-Fi proxy server nejde uložit, když se Wi-Fi vlastnosti uživatelského rozhraní spustí ze služby **Nastavení > síťové & stav > > vlastnosti**.
- Vyřešili jsme problém s odebráním certifikátů eSIM napříč aktualizacemi operačního systému. Tato oprava zajistí, že se při aktualizaci verze 21H1 odebraly certifikáty eSIM a související součásti.
- Opravili jsme problém ovlivněný předinstalovanými aplikacemi v rámci resetování operačního systému.
- Zvýšení výkonu při nabíjení baterie za účelem zvýšení modulu runtime při zpoplatnění zvýšeného zatížení procesoru. při nastavování zařízení HoloLens 2, pokud se zjistilo, že se zařízení bude používat horká, bude interní baterie pomaleji, aby se snížila energie. Kladné kompromisy jsou v tom, že zařízení je méně pravděpodobně vypíná kvůli tepelným problémům, což má vliv na to, že zařízení běží delší dobu. Pokud je zařízení spuštěné, neovlivní se vám poplatky za přenos.

> [!IMPORTANT]
> v důsledku nově vyřešeného [známého problému v našem buildu 21H1, který má vliv na uživatele vzdálené pomoci](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), jsme dočasně pozastavili nabídku Windowsch holografických aktualizací verze 21H1. také jsme změnili výchozí sestavení průvodce rozšířeným obnovením (ARC) na [Windows holografické verze 20H2 – červen 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Sestavení ARC teď obnoví cílení na sestavení 21H1.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holografická verze 20H2 – červenec 2021 Update

- Sestavení 19041,1157

Vylepšení a opravy v aktualizaci:

- Portál zařízení má rozšířené metody upozorňování zákazníka, když se v Průzkumníkovi souborů vyskytnou problémy s otevíráním uzamčených souborů.
- Nahrání souboru, stažení, přejmenování a odstranění je teď opravené při použití protokolu HTTPS ve všech podporovaných prohlížečích.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holografická verze 21H1, aktualizace od června 2021

- Sestavení 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>nahrávání OneDrive pro pracovní nebo školní kameru

do Nastavení aplikace HoloLens 2 jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa > ze hybridní reality do odpovídajících OneDrive pro pracovní nebo školní složku. tato funkce řeší [mezeru funkcí v rámci aplikace OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) v HoloLens 2, která podporuje automatické odesílání snímků na osobní účet Microsoft zákazníka (a ne na svůj pracovní nebo školní účet).

**Jak to funguje**

- pokud chcete povolit "nahrávání kamery", navštivte web **Nastavení > System > Mixed Reality** .
- když nastavíte tuto funkci na **pozici,** všechny fotky nebo videa ve smíšené realitě zaznamenané do vašeho zařízení se automaticky zařadí do fronty pro nahrání do složky obrázky > kamery OneDrive pro pracovní nebo školní účet.
    >[!NOTE]
    >Fotografie a videa zachycené před povolením této funkce *se* nebudou zařadit do fronty pro nahrání a pořád je budete muset nahrát ručně.
- stavová zpráva na stránce Nastavení zobrazí počet souborů, které čekají na nahrání (nebo čtení "OneDrive je aktuální" při odeslání všech nevyřízených souborů).
- Pokud máte obavy o šířku pásma nebo chcete "pozastavit" nahrávání z jakéhokoli důvodu, můžete funkci přepnout na **volnou** pozici. Když funkci dočasně zakážete, zajistíte tak, že se fronta nahrávání během přidávání nových souborů do složky fotoaparátu bude dál zvyšovat, ale soubory se nebudou nahrávat, dokud tuto funkci znovu nepovolíte.
- Nejnovější soubory se nahraje jako první (poslední v, první ven).
- pokud má váš OneDrive účet problémy (například po změně hesla), zobrazí se na stránce Nastavení tlačítko **opravit** .
- Není k dispozici žádná maximální velikost souboru, ale mějte na paměti, že se nahrávání velkých souborů bude trvat déle (zejména pokud je vaše šířka pásma nahrávání omezená). Pokud zadáte "pozastavit" nebo vypnete nahrávání při nahrávání velkého souboru, částečná nahrávání se zachová. Pokud je nahrání znovu povoleno do několika hodin pozastaveno nebo vypnuto, bude nahrávání pokračovat od místa, kde bylo přerušeno. Pokud je ale nahrávání po několika hodinách znovu povolené, nahrávání ve velkém souboru se restartuje od začátku.

**Známé problémy a upozornění**

- Toto nastavení nemá integrované omezení na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Upload se pozastaví, ale funkce bude nadále monitorovat nově přidané soubory do sady fotoaparátů. Až budete připraveni, můžete nahrávání znovu povolit.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat soubory pro uživatele, který je aktuálně přihlášený k zařízení.
- pokud přenášíte fotky nebo videa při sledování počtu nahrávání na Nastavení stránce v reálném čase, poznamenejte si, že počet nezpracovaných souborů se nemusí změnit, dokud se nedokončí nahrávání aktuálního souboru.
- Upload se pozastaví, pokud zařízení přejde do režimu spánku nebo je vypnuté. chcete-li zajistit, aby vaše nevyřízená nahrávání byla dokončena, aktivně zařízení používat, dokud Nastavení page nepřečte "OneDrive je aktuální" nebo upravte nastavení **napájení & režimu spánku** .

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

v HoloLens 2 se teď podporují tyto zásady telemetrie:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Systém\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně, aby měly úplnou kontrolu nad telemetrií a chováním v Nastavení aplikaci.

Vylepšení a opravy v aktualizaci:

- Opravuje hlavní poškození videa pomocí barevného poškození.
- Řeší problém, kdy se v nabídce Power může oříznou text.
- Povolí podporu pro zásadu RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z června 2021

- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

Následující zásady telemetrie se teď podporují na HoloLens 2:

- KonfiguraceTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Systém\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně, aby měly úplnou kontrolu nad telemetrií a chováním v Nastavení aplikaci.

Doporučujeme, abyste si mohli vyzkoušet náš nejnovější build Windows Holographic verze 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z června 2021

- Build 18362.1116

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

>[!IMPORTANT]
> Toto sestavení už nebude v provozu.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, verze 21H1

- Build 20346.1002

Tato aktualizace obsahuje funkce pro dvě cílové skupiny. Funkce, které může koncový uživatel na zařízení používat kdokoli na zařízení, a nové možnosti správy zařízení, které mohou konfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro každou cílovou skupinu. Pokud jste správcem IT, podívejte se na náš kontrolní seznam pro správce [IT – aktualizace.](#it-admin---update-checklist)
>[!IMPORTANT]
>Aby bylo možné aktualizovat toto sestavení, musí na zařízeních HoloLens 2 aktuálně běžet aktualizace z února 2021 (build 19041.1136) nebo novější. Pokud se vám tato aktualizace funkcí neschová k dispozici, nejprve aktualizujte své zařízení a zkuste to znovu.

>[!NOTE]
>V současné Microsoft HoloLens verze 2 podporuje měsíční servisní aktualizace (opravy chyb a zabezpečení) pro následující verze:
>
>- Windows Holographic, verze 20H2 (build 19041.1128+)
>- Windows Holographic, verze 2004 (build 19041.1103+)
>- Windows Holographic, verze 1903 (build 18362+)
>
> Se zavedením Windows Holographic verze 21H1 přerušujeme měsíční servisní aktualizace pro **Windows Holographic verze 1903.** Díky tomu se můžete zaměřit na novější verze a pokračovat v poskytování cenných vylepšení.

| Název funkce                                              | Krátký popis                                                                      | Cílovou skupinu |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nové Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nová verze Chromium založená na Microsoft Edge je teď k dispozici pro HoloLens 2. | Koncový uživatel |
[WebXR a 360 Viewer](#webxr-and-360-viewer) | Vyzkoušejte imerzivní webová prostředí a přehrávání videa 360. | Koncový uživatel |
[Nová Nastavení aplikace](#new-settings-app) | Starší Nastavení nahrazuje aktualizovaná verze novými funkcemi a nastaveními. | Koncový uživatel |
[Zobrazení barevného pozadí](#display-color-calibration) | Vyberte alternativní profil barev pro váš HoloLens 2. | Koncový uživatel |
[Výchozí výběr aplikace](#default-app-picker) | Vyberte, která aplikace se má spustit pro každý typ souboru nebo odkazu. | Koncový uživatel |
[Řízení objemu na aplikaci](#per-app-volume-control) | Objem na úrovni aplikace můžete řídit nezávisle na systémovém svazku. | Koncový uživatel |
[Instalace webových aplikací](#install-web-apps) | Nainstalujte webové aplikace na HoloLens 2, například Microsoft Office, pomocí nového Microsoft Edge prohlížeče. | Koncový uživatel |
[Potažením prstem zadejte](#swipe-to-type) | Pomocí špičky prstu potáhněte slova na holografické klávesnici. | Koncový uživatel |
[Nabídka Napájení z nabídky Start](#power-menu-from-start) | V nabídce Start restartujte a vypněte HoloLens zařízení. | Koncový uživatel |
[Více uživatelů uvedených na přihlašovací obrazovce](#multiple-users-listed-on-sign-in-screen) | Zobrazení několika uživatelských účtů na přihlašovací obrazovce | Koncový uživatel |
[Podpora externího mikrofonu USB-C](#usb-c-external-microphone-support) | Použijte mikrofony USB-C pro aplikace a /nebo Remote Assist. | Koncový uživatel |
[Automatické přihlášení návštěvníka pro bezobrazovkové režimy](#visitor-auto-logon-for-kiosks) | Povolí použití automatického přihlášení k účtům Návštěvník v bezobrazovkovém režimu. | Správce IT |
[Nové identifikátory AUMID pro nové aplikace v beznavídkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Identifikátory AUMID pro nové Nastavení a aplikace Edge. | Správce IT |
[Vylepšené předání chyb v bezobrazovkovém režimu](#kiosk-mode-behavior-changes-for-handling-of-failures) | V bezobrazovkovém režimu se před prázdnou nabídkou Start vyhledá globální přiřazený přístup. | Správce IT |
[Nová nastaveníURIs pro viditelnost Nastavení zobrazení stránky](#new-settings-uris-for-page-settings-visibility) | Více než 20 nových nastaveníUI pro Nastavení/PageVisibilityList. | Správce IT |
[Konfigurace diagnostiky pro záložní prostředky](#configuring-fallback-diagnostics-via-settings-app) | Nastavení chování diagnostiky pro záložní Nastavení aplikaci | Správce IT |
[Sdílení věcí s blízkými zařízeními](#share-things-with-nearby-devices) | Sdílet soubory nebo adresy URL z HoloLens do počítače. | Vše |
[Nová diagnostická trasování operačního systému](#new-os-diagnostic-traces) | Nový poradce při potížích Nastavení pro aktualizace operačního systému. | Správce IT |
[Optimalizace doručení Preview](#delivery-optimization-preview) | Snižte využití šířky pásma pro stahování z více HoloLens zařízení. | Správce IT |

Projděte si související poznámky k verzi:

- [Navštivte archiv HoloLens Emulator.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Průvodci Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Představujeme nový Microsoft Edge

![animace starší verze Microsoft Edge loga na nové Microsoft Edge logo.](images/new-edge.gif)

nový Microsoft Edge [přijme projekt Chromium open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) , aby vytvořil lepší kompatibilitu pro zákazníky a méně fragmentaci webu pro webové vývojáře.

> [!IMPORTANT]
> tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která již není v nových verzích [podporována](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) .

![nový snímek obrazovky Microsoft Edge.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Spouští se nový Microsoft Edge.

Nový Microsoft Edge ![ikona nové Microsoft Edge](images/new_edge_logo.png) (reprezentované modrou a zelenou ikonou) jsou připnuté na nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> když poprvé spustíte nový Microsoft Edge v HoloLens 2, vaše nastavení a data se naimportují ze starší verze Microsoft Edge. pokud po spuštění nového Microsoft Edge budete nadále používat starší verze Microsoft Edge, nebudou se nová data synchronizovat ze starší verze Microsoft Edge do nového Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče pro HoloLens 2, než bylo dříve k dispozici ve starších verzích Microsoft Edge.

Tady je několik užitečných prostředků, které vám pomůžou se správou nastavení zásad pro nové Microsoft Edge:

- [konfigurace nastavení zásad Microsoft Edge pomocí Microsoft Intune](/deployedge/configure-edge-with-intune)
- [mapování zásad starší verze Microsoft Edge Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [mapování zásad Google Chrome na Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- úplná [dokumentace k Microsoft Edge Enterprise](/deployedge/)

> [!IMPORTANT]
> vzhledem k tomu, že se jedná o řadu zásad prohlížeče podporovaných novým Microsoft Edge, náš tým nemůže zaručit, že každá nová zásada funguje na HoloLens 2. ale otestovali a potvrdili jsme to, než je nový Microsoft Edge ekvivalent každé starší verze Microsoft Edge zásady, která byla dřív podporovaná na HoloLens 2 fungovala podle očekávání. v tématu [starší verze Microsoft Edge Microsoft Edge mapování zásad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) najdete nové Microsoft Edge ekvivalent každé starší zásady Microsoft Edge prohlížeče, kterou jste používali s HoloLens 2.
>
> existují alespoň dvě nové zásady Microsoft Edge, které *nebudeme* spolupracovat s HoloLens 2:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>co očekávat od nového Microsoft Edge v HoloLens 2

vzhledem k tomu, že nový Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru uwp, která umožňuje běžet na zařízeních jenom s uwp, jako je HoloLens 2, některé funkce nemusí být k dispozici okamžitě. V nadcházejících měsících budeme podporovat nové scénáře a funkce, takže na tomto místě najdete aktuální informace.

**Očekává se, že scénáře a funkce budou fungovat:**

- První spuštění, přihlášení k profilování a synchronizace
- Weby by se měly vykreslovat a chovat podle očekávání
- Většina funkcí prohlížeče (oblíbená, historie atd.) by měla fungovat podle očekávání.
- Tmavý režim
- Instalace webových aplikací do zařízení
- instalování rozšíření (pokud používáte jakákoli rozšíření, která nefungují správně na HoloLens 2), dejte nám prosím nějaké informace.
- Zobrazení a označení PDF
- Prostorové zvuky z jednoho okna prohlížeče
- Automatická a ruční aktualizace prohlížeče
- Uložení PDF z nabídky tisk (pomocí možnosti Uložit do PDF)
- Rozšíření prohlížeče WebXR a 360
- Obnovení obsahu do správného okna při prohlížení mezi několika okny umístěnými ve vašem prostředí

**Neočekávané scénáře a funkce pro práci:**

- Prostorový zvuk z více oken se současnými datovými proudy
- "Podívejte se, jak to znamená"
- Tisk

**Hlavní známé problémy v prohlížeči:**

- Pro nové Microsoft Edge je verze Preview pro lupu vypnutá. Doufáme, že tuto funkci znovu povolíme v budoucí aktualizaci, jakmile bude zvětšení fungovat správně.
- Zvuk může být přehráván z nesprávného okna prohlížeče, pokud máte otevřeno a aktivní jiné okno prohlížeče. Tento problém můžete obejít tak, že zavřete jiné aktivní okno, které nemá přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu "pořídit"](hololens2-basic-usage.md#follow-me-stop-following)bude pokračovat přehrávání zvuku, pokud zakážete režim "pořídit". Tento problém můžete obejít tak, že přehrávání zvuku zastavíte ještě před tím, než zakážete režim "pořídit" nebo zavřením okna tlačítkem **X** .
- interakce s aktivními Microsoft Edge windows může způsobit neočekávané neočekávané neočekávané ukončení jiných oken aplikace 2d. Tato okna můžete znovu aktivovat pomocí interakce s nimi.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

tým Microsoft Edge zpřístupňuje komunitě programu Edge Insider tři kanály verze preview: Beta, vývojová a kanárské. při instalaci kanálu verze preview nedojde k odinstalaci vydané verze Microsoft Edge v HoloLens 2 a můžete nainstalovat více než jednu současně.

další informace o komunitě Edge Insider najdete na [domovské stránce Microsoft Edge Insider](https://www.microsoftedgeinsider.com) . Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na [stránce pro stažení produktu Edge Insider](https://www.microsoftedgeinsider.com/download).

pro instalaci kanálů Microsoft Edge Insider do HoloLens 2 je k dispozici několik metod:

**Přímá instalace na zařízení (aktuálně dostupná jenom pro nespravovaná zařízení)**

  1. na HoloLens 2 navštivte [stránku pro stažení aplikace Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. vyberte tlačítko **stáhnout pro HoloLens 2** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor. msix z fronty pro stahování z Edge nebo ze složky Ke_stažení vašeho zařízení (pomocí Průzkumníka souborů).
  1. Spustí se [instalační program aplikace](app-deploy-app-installer.md) .
  1. Vyberte tlačítko **instalovat** .
  1. po úspěšné instalaci najdete Microsoft Edge Beta, vývoj nebo kanárské jako samostatnou položku v seznamu **všechny aplikace** nabídka Start.

**instalace prostřednictvím počítače s Windows portálem zařízení (vyžaduje, aby byl v HoloLens 2 povolen [režim pro vývojáře](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) )**

  1. Na svém počítači navštivte stránku pro [stažení Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. vyberte **tlačítko se šipkou rozevíracího** seznamu vedle tlačítka stáhnout pro Windows 10 pro kanál Edge Insider, který chcete nainstalovat.
  1. v rozevírací nabídce vyberte **HoloLens 2** .
  1. Uložte soubor. msix do složky Ke_stažení vašeho počítače (nebo do jiné složky, kterou můžete snadno najít).
  1. pomocí [Windows portálu zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na počítači nainstalujte stažený soubor. msix na HoloLens 2.
  1. po úspěšné instalaci najdete Microsoft Edge Beta, vývoj nebo kanárské jako samostatnou položku v seznamu **všechny aplikace** nabídka Start.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blokování nových Microsoft Edge pomocí WDAC

pro správce IT, kteří chtějí aktualizovat [zásady WDAC](windows-defender-application-control-wdac.md) k blokování nové aplikace Microsoft Edge, budete muset do své zásady přidat následující.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí můžou mít k dispozici omezení sítě, aby se mohla brát v úvahu. Chcete-li zajistit hladké prostředí s novým okrajem, [povolte tyto koncové body společnosti Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalace webových aplikací

 > [!Note]
>od [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1), Office webová aplikace už nebude předem nainstalovaná.

novou hranici můžete použít k instalaci webových aplikací společně s aplikacemi Microsoft Store. můžete například nainstalovat Microsoft Office webové aplikace pro zobrazení a úpravy souborů hostovaných v SharePoint nebo OneDrive. pokud chcete nainstalovat Office webovou aplikaci, přejděte na https://www.office.com adresu a vyberte aplikaci, kterou **máte k dispozici** , nebo si na adresní řádek **nainstalujte Office** tlačítko. Kliknutím na **instalovat** potvrďte.

> [!IMPORTANT]
> funkce Office webové aplikace je dostupná jenom v případě, že má HoloLens 2 aktivní připojení k internetu.

### <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer

nový Microsoft Edge zahrnuje podporu pro WebXR, což je nový standard pro vytváření moderního webového prostředí (nahrazuje WebVR). mnoho poutavých webových prostředí bylo navrženo s ohledem na VR (nahrazuje vaše pole zobrazení virtuálním prostředím), ale tato prostředí jsou také podporována HoloLens 2. Standard WebXR také umožňuje rozšířit a míchat působivá webová prostředí, která využívají vaše fyzické prostředí. protože vývojáři stráví více času s WebXR, předpokládáme, že pro zákazníky HoloLens 2 se dokončí nová rozšířená a smíšená prostředí realit, která vám pomůžou vyzkoušet!

rozšíření pro program 360 Viewer je postavené na WebXR a automaticky se instaluje společně s novým Microsoft Edge v HoloLens 2. Toto webové rozšíření vám dává možnost ponořit si vaše videa 360 ve stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

#### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu vyberte tlačítko pro **zadání VR** . Umístění a vizuální znázornění tohoto tlačítka se může na webu lišit, ale může vypadat podobně jako:

    ![Zadejte příklad tlačítka VR.](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění WebXR prostředí v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení, vyberte možnost **Povolení**.
1. K [HoloLens s prostředím používejte 2](hololens2-basic-usage.md#the-hand-tracking-frame) gesta.
1. Pokud prostředí nemá tlačítko Ukončit, **pomocí** gesta [Start](hololens2-basic-usage.md#start-gesture) se vraťte domů.

**Doporučené ukázky WebXR**

- 360 Viewer (viz další část)
- [XR Užis](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR – Malování](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na video o 360 stupních na YouTube.
1. V rámečku videa vyberte tlačítko náhlavní soupravy hybridní reality:

    ![Tlačítko pro aktivaci prohlížeče 360.](images/enter-360-viewer.jpg)

1. Když se poprvé pokusíte spustit prohlížeč 360 v konkrétní doméně, prohlížeč požádá o souhlas se zadáním imerzivního zobrazení. Vyberte **Povolit.**
1. [Klepnutím ve vzduchu](hololens2-basic-usage.md#select-using-air-tap) vysunutím ovládacích prvků přehrávání Pomocí [ručních paprsků](hololens2-basic-usage.md#select-using-air-tap) a klepnutí ve vzduchu můžete přehrát/pozastavit, přeskočit vpřed/zpět, zapnout nebo vypnout titulky nebo ukončit prostředí (které ukončí imerzivní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Hlavní známé problémy s WebXR a 360 Viewerem

- V závislosti na složitosti prostředí WebXR může snímková frekvence poklesat nebo se zhoršit.
- Podpora pro articulated handu v WebXR není ve výchozím nastavení povolená. Vývojáři mohou podporu povolit `edge://flags` zapnutím funkce "Ruční vstup WebXR".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby k WebXR a 360 Vieweru

Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce **Poslat** zpětnou vazbu v novém Microsoft Edge.

### <a name="new-settings-app"></a>Nová Nastavení aplikace

V této verzi představujeme novou verzi této Nastavení aplikace. Nová aplikace Nastavení obsahuje nové funkce a rozšířená nastavení pro HoloLens 2 v následujících oblastech: Zvuk, Režim spánku Power &, Síť & Internet, Aplikace, Účty, Usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, Nastavení se nová aplikace Nastavení liší od starší verze aplikace Nastavení, budou při aktualizaci odebrána jakákoli okna Nastavení, která jste předtím umístili kolem svého prostředí.

![Domovská Nastavení nové aplikace](images/new-settings-app.png)

**Nové funkce a nastavení**

- Nastavení vyhledávání: Vyhledá nastavení z domovské Nastavení pomocí klíčových slov nebo názvu nastavení.
- System > Sound( Zvuk systémového >):
  - Vstupní a výstupní zvuková zařízení: Nezávisle zvolte vstupní a výstupní zvuková zařízení (například naslouchejte zvuku prostřednictvím Bluetooth nebo použijte mikrofon USB-C pro zvukový vstup).
    > [!NOTE]
    > Bluetooth 2 nepodporuje HoloLens mikrofony.
  - Objem aplikace: Nezávisle upravte objem každé aplikace. Viz [řízení objemu na aplikaci.](#per-app-volume-control)
- System > Power & režim spánku: Zvolte, kdy má zařízení po určité době nečinnosti přejít do režimu spánku.
- Baterie >: Ručně povolte spořič baterie režimu nebo nastavte prahovou hodnotu baterie, po spořič baterie režim automaticky zapne.
- Zařízení > USB: Ve výchozím nastavení můžete zakázat připojení USB.
- Network & Internet:
  - Ethernetové adaptéry USB-C se teď zobrazí v části & internetu.
  - K dispozici jsou teď nastavení ethernetového adaptéru USB-C, včetně jeho IP adresy.
  - Režim v letadle teď můžete povolit na HoloLens 2.
- Aplikace: Můžete resetovat výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu [Výběr výchozí aplikace.](#default-app-picker)
- Účty > Ostatní uživatelé: Vlastníci zařízení mohou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, downgradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.

**Známé problémy**

- Dříve umístěná Nastavení okna budou odebrána (viz poznámka výše).
- Zařízení už nemůžete přejmenovat pomocí Nastavení aplikace. Správci IT mohou zařízení přejmenovat pomocí šablony [Windows Autopilot pro název](hololens2-autopilot.md) zařízení HoloLens 2 nebo uzlu MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se za všech okolností zobrazuje virtuální ethernetové zařízení (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, protože je povaha desktopové aplikace Win32 podporované vrstvou adaptéru UPW (brzy se neočekává žádná oprava).

#### <a name="display-color-calibration"></a>Zobrazení barevného pozadí

Pomocí tohoto nového nastavení můžete vybrat alternativní profil barev pro váš HoloLens 2. Barvy se tak můžou zdát přesnější, zejména při nižších úrovních jasu zobrazení. Informace o zobrazení barevného pozadí najdete v Nastavení na stránce System > Aplikace.

> [!NOTE]
> Vzhledem k tomu, že toto nastavení ukládá nový profil barev do firmwaru zobrazení, jedná se o nastavení pro jednotlivá zařízení (a není jedinečné pro každý uživatelský účet).

##### <a name="how-to-use-display-color-calibration"></a>Použití barevného zobrazování

1. Spusťte aplikaci **Nastavení** a přejděte na **System > átem.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Spustit zobrazit **barvu.**
1. Spustí se prostředí zobrazení barev a budete se muset ujistit, že je zorník ve správné pozici.
1. Po pokračování v dialogových oknech s pokyny se vaše zobrazení automaticky ztmaní na 30% jas.
    > [!TIP]
    > Pokud máte potíže se zobrazením tlumené scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek brightness na levé straně zařízení.
1. Výběrem tlačítek 1 až 6 můžete okamžitě vyzkoušet každý profil barev a najít ten, který vám vypadá nejlépe do očí (obvykle to znamená, že profil, který pomáhá scéně vypadat nejneužívěnější, se vzorem stupňů šedé a barevnými odstíny, které vypadají podle očekávání).)

    ![Zobrazení scény barevného pozadí](images/color-cal-ui.png)

1. Až budete s vybraným profilem spokojeni, vyberte tlačítko **Save & Exit** (Uložit a ukončit).
1. Pokud nechcete provádět změny, vyberte **tlačítko Zrušit & Ukončit** a změny se vrátí zpět.

> [!TIP]
> Tady je několik užitečných tipů, které je dobré mít na paměti při používání nastavení barev zobrazení:
>
> - Kdykoli chcete, můžete znovu spustit barevné Nastavení zobrazení.
> - Pokud někdo v zařízení dříve použil nastavení ke změně profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte barevné zvýraznění zobrazení, profil barev, který byl dříve uložen, se zvýrazní a profil 0 se nezobrazí (protože Profil 0 představuje původní profil barvy zobrazení).
> - Pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to udělat na stránce Nastavení (viz resetování profilu [barev).](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Resetování profilu barev

Pokud s vlastním profilem barev uloženým v počítači HoloLens 2 nejste spokojeni, můžete původní profil barev zařízení obnovit:

1. Spusťte aplikaci **Nastavení** a přejděte na **System > átem.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Obnovit výchozí **profil** barev.
1. Po otevření dialogového okna vyberte **Restartovat,** pokud jste připraveni restartovat počítač HoloLens 2 a použít změny.

#### <a name="top-display-color-calibration-known-issues"></a>Známé problémy s nejvyšším zobrazováním barev

- Na stránce Nastavení bude stavový řetězec, který vás informuje o tom, kdy byl profil barev naposledy změněn, neaktuální, dokud znovu nenačtete tuto stránku Nastavení.
    - Alternativní řešení: Vyberte Nastavení obrazovky a pak znovu vyberte stránku Uchovat.

#### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když aktivujete hypertextový odkaz nebo otevřete typ souboru s více nainstalovanými aplikacemi, která ho podporuje, zobrazí se nové okno s výzvou k výběru nainstalované aplikace, která by měla typ souboru nebo odkazu zpracovat. V tomto okně se také můžete rozhodnout, že vybraná aplikace zřídí soubor nebo typ odkazu "Jednou" nebo "Vždy".

Pokud zvolíte Možnost Vždy, ale později chcete změnit, která aplikace zpracovává konkrétní soubor nebo typ odkazu, můžete uložené výchozí hodnoty resetovat v Nastavení > **Apps**. Posuňte se do dolní části stránky a vyberte tlačítko **Vymazat** v části Výchozí aplikace pro typy souborů a/nebo Výchozí aplikace pro typy odkazů. Na rozdíl od podobného nastavení na stolních počítačích nemůžete resetovat výchozí nastavení jednotlivých typů souborů.

#### <a name="per-app-volume-control"></a>Řízení objemu na aplikaci

V této Windows sestavě mohou uživatelé ručně upravit úroveň svazku každé aplikace. Díky tomu se uživatelé mohou lépe soustředit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například když potřebujete vypnout objem jedné aplikace a volat jinou osobu kvůli vzdálené pomoci v jiné.

Pokud chcete nastavit svazek jednotlivé aplikace, přejděte **na Nastavení** Zvuk systému a v části Pokročilé možnosti zvuku vyberte Svazek aplikace a  >    >   **předvolby zařízení.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potažením prstem zadejte

Někteří zákazníci zjistí, že psaní na virtuálních klávesnicích je rychlejší. Posouváním tvaru slova, které zamýšlejí, zobrazíme náhled této funkce pro holografičovou klávesnici. Potažením prstem po jednom slově můžete procházet špičku prstu rovinou holografické klávesnice, potáhnutím tvaru slova a stažením špičky prstu z roviny klávesnice. Potažením prstem po sledu slov nepotřebujete stisknout mezerník odebráním prstu z klávesnice mezi slovy. Pokud vidíte potažení prstem za pohybem prstu na klávesnici, budete vědět, že tato funkce funguje.

Upozorňujeme, že použití a ovládání této funkce může být obtížné, protože se jedná o holografický klávesnici, u které nemáte pocit odolnosti proti prstu (na rozdíl od displeje mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka Napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní HoloLens, který ukazuje, kdy je dostupná aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní HoloLens obrazovky pomocí [gesta Start](hololens2-basic-usage.md#start-gesture) nebo rčení "Přejít na start".

2. Všimněte si ikony se třemi tečkami (...) vedle profilu uživatele:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Vyberte profilový obrázek uživatele pomocí rukou nebo hlasovým příkazem Power.

4. Zobrazí se nabídka s možnostmi Odhlásit se, Restartovat nebo Vypnout zařízení:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Výběrem možností nabídky se odhlásit, restartovat nebo vypnout HoloLens. Možnost Odhlásit se nemusí být dostupná, pokud je zařízení nastavené pro jeden účet [Microsoft (MSA) nebo místní účet](hololens-identity.md).

6. Zavřete nabídku stisknutím libovolného jiného místa nebo zavřením nabídka Start pomocí gesta Spustit.

#### <a name="update-indicator"></a>Indikátor aktualizace

Když je k dispozici aktualizace, ikona se třemi tečkami se zobrazí, což značí, že restartováním se nainstaluje aktualizace. Možnosti nabídky se také změní tak, aby odrážely přítomnost aktualizace.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Dříve se na obrazovce Přihlásit zobrazí jenom naposledy přihlášený uživatel a také vstupní bod Jiný uživatel. Dostali jsme zpětnou vazbu od zákazníků, že to nestačí, pokud se k zařízení přihlásilo více uživatelů. Stále se vyžadovalo, aby znovu zadat své uživatelské jméno atd.

V tomto Windows buildu se při  výběru možnosti Jiný uživatel, který se nachází napravo od pole pro zadání kódu PIN, zobrazí přihlašovací obrazovka více uživatelů, kteří se k zařízení už přihlásili. To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlásit pomocí svých přihlašovacích Windows Hello uživatele. Nového uživatele můžete do zařízení přidat také z této stránky Ostatní uživatelé pomocí **tlačítka Přidat** účet.

V nabídce Ostatní uživatelé se na tlačítku Ostatní uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka.](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiných uživatelů.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externího mikrofonu USB-C

> [!IMPORTANT]
> Když **zapojíte mikrofon USB, nenastaví se automaticky jako vstupní zařízení.** Při připojování k sadě konektorů USB-C uživatelé sledují, že zvuk zařízení se automaticky přesměruje na konektory, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad libovolným jiným vstupním zařízením. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí **panelu Nastavení** zvuku. Mikrofony USB-C je možné použít k volání, nahrávání atd.

Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**

![Sound Nastavení.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace** znamená, že externí mikrofon se použije ve vzdáleném asistenci a dalších komunikačních aplikacích, ale pole HoloLens mikrofonu se může používat i pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavte výchozí mikrofon.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co Bluetooth mikrofonu?

V Bluetooth 2 se bohužel stále nepodporují HoloLens mikrofony.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound explicitně nastavte vestavěné mluvčí (zvukový ovladač  >    >   **analogové funkce)** jako **výchozí zařízení.** HoloLens byste si toto nastavení měli zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatické přihlášení návštěvníka pro terminály

Tato nová funkce umožňuje použití automatického přihlašování k účtům Návštěvník v bezobrazovkovém režimu.

Konfigurace zařízení bez AAD pro automatické přihlášení návštěvníka:

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje **nastavení modulu runtime /AssignedAccess tak,** aby povolují účty návštěvníka.
    1. Volitelně zaregistruje zařízení v MDM (nastavení modulu runtime, pracoviště **nebo registrace),** aby ho bylo možné později spravovat.
    1. Nevytvářejte místní účet.
1. [Použijte zřizovací balíček](hololens-provisioning.md).

V případě AAD konfigurace mohou uživatelé bez této změny dosáhnout něčeho podobného. AAD zařízení připojená k bezobrazovkovému režimu mohou přihlásit účet Návštěvník jediným klepnutím na přihlašovací obrazovku. Jakmile se zařízení přihlásí k účtu návštěvníka, nebude znova vyzváno k přihlášení, dokud se návštěvník z nabídky Start explicitně odhlásit nebo dokud se zařízení nerestartuje.

Automatické přihlášení návštěvníka je možné spravovat [pomocí vlastních zásad OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Hodnota URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automaticky se přihlásit k bezobrazovkovému režimu.   | 1 (Ano), 0 (Ne, výchozí.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových aplikací Nastavení Edge v režimech veřejného terminálů

Při zahrnutí aplikací do [veřejného terminálu](hololens-kiosk.md)správce IT často přidá aplikaci do veřejného terminálu, ale použije JI AUMID (App User Model ID). Vzhledem k tomu, že se aplikace Nastavení i aplikace Microsoft Edge považují za nové aplikace a liší se od starších aplikací, které pro tyto aplikace používají identifikátory AUMID, bude potřeba aktualizovat, aby bylo možné používat nové AUMID.

Při úpravách veřejného terminálů tak, aby zahrnoval nové aplikace, doporučujeme přidat nové AUMID a nechat starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou muset dostávat nové zásady, aby mohli dál používat beziosk, jak má.

| Aplikace                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stará Nastavení aplikace       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nová Nastavení aplikace       | BAEAEF15-9BE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Stará Microsoft Edge aplikace | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nová Microsoft Edge aplikace | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování v bezobrazovkovém režimu pro zpracování selhání

Pokud má zařízení ve starších buildech konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálním i přiřazeným členem skupiny AAD AAD,[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)pokud by se nepodařilo určit členství ve skupině, uživateli se v nabídce Start nezobrazí nic.

Od této Windows verze se prostředí veřejného terminálu v případě selhání v bezobrazovkovém režimu skupiny veřejného AAD pro použití v globální konfiguraci veřejného terminálu (pokud je k dispozici).

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nové Nastavení URI pro viditelnost Nastavení stránky

Do Windows Holographic verze [20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali zásadu [Nastavení/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) která omezí stránky, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci System Nastavení, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

Pokud navštívíte [stránku s Nastavení viditelnosti,](settings-uri-list.md)najdete pokyny k použití tohoto poskytovatele CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšiřujeme seznam dostupných identifikátorů URI, Nastavení mohou spravovat správci IT. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové Nastavení aplikace. Pokud používáte zásady Nastavení/PageVisibilityList, zkontrolujte následující seznam a podle potřeby upravte povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: ms-settings:network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Stará stránka **&**  >  **internetového proxy** serveru už není dostupná jako globální nastavení. Nové nastavení proxy serveru pro připojení najdete v části **Vlastnosti internetové** sítě &  >  **Wi-Fi** nebo Vlastnosti  >   **internetového**&  >  **sítě Ethernet.**  >  

<br>

| Stránka Nastavení                                        | Identifikátor URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplikace > Apps & funkce                               | `ms-settings:appsfeatures`                         |
| Funkce > Apps & v > Upřesnit možnosti          | `ms-settings:appsfeatures-app`                     |
| Aplikace > Offline mapy                                  | `ms-settings:maps`                                 |
| Aplikace > offline mapy > stažení map                  | `ms-settings:maps-downloadmaps`                    |
| Zařízení > myši                                      | `ms-settings:mouse`                                |
| Zařízení > USB                                        | `ms-settings:usb`                                  |
| Režim sítě & Internet > v letadle                   | `ms-settings:network-airplanemode`                 |
| Ochrana osobních údajů > obecné                                    | `ms-settings:privacy-general`                      |
| Ochrana osobních údajů > rukopisu & psaní             | `ms-settings:privacy-speechtyping`                 |
| Ochrana osobních údajů > pohyb                                     | `ms-settings:privacy-motion`                       |
| Ochrana osobních údajů > ohraničení obrazovky                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Ochrana osobních údajů > snímky obrazovky a aplikace                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Baterie > systému                                     | `ms-settings:batterysaver`                         |
| Baterie > systému                                     | `ms-settings:batterysaver-settings`                |
| Zvuk > systému                                       | `ms-settings:sound`                                |
| Zvuk > zvuku > aplikace a předvolby zařízení | `ms-settings:apps-volume`                          |
| Systémový > Sound > Správa zvukových zařízení              | `ms-settings:sound-devices`                        |
| systémová > Storage > konfigurace Storageho rozpoznávání         | `ms-settings:storagepolicies`                      |
| Čas & jazyka > datum & data                        | `ms-settings:dateandtime`                          |
| Čas & jazyka > klávesnice                           | `ms-settings:keyboard`                             |
| Jazyk > jazyka času &                           | `ms-settings:language`                             |
| Jazyk > jazyka času &                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizace zabezpečení & > resetování & obnovení               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualizované identifikátory URI

Předchozí dva identifikátory URI by nemusely uživatele přímo na označené stránky zablokovat, ale jenom zablokovali stránku hlavní aktualizace. Následující položky byly aktualizovány, aby byly na své stránky přesměrovány:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>konfigurace záložní diagnostiky prostřednictvím aplikace Nastavení

nyní může uživatel v aplikaci Nastavení nakonfigurovat chování [záložní diagnostiky](hololens-diagnostic-logs.md). v aplikaci Nastavení přejděte na   >  stránku **poradce při potížích** s nastavením ochrany osobních údajů, abyste mohli nakonfigurovat toto nastavení.

> [!NOTE]
> Pokud je pro zařízení nakonfigurovaná zásada MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí pomocí okolních zařízení

sdílejte věci s Windows 10 zařízení, včetně počítačů i dalších zařízení HoloLens 2. můžete si to vyzkoušet v **Nastavení**  >    >  **sdílených prostředích** , abyste mohli sdílet soubory nebo adresy url od HoloLens k počítači. Další podrobnosti najdete v tématu o tom, jak [sdílet věci s blízkými zařízeními v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tuto funkci je možné spravovat prostřednictvím [Možnosti připojení/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová trasování diagnostiky operačního systému

kromě předchozích poradců při potížích v aplikaci Nastavení byla přidána nová poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. přejděte na **Nastavení**  >  **aktualizace &amp; zabezpečení**  >  **řešit**  >  **web Windows Update** a vyberte **spustit**. Díky tomu můžete shromažďovat trasování a při reprodukci problému s aktualizacemi operačního systému pomoct lépe při řešení problémů s vaším IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručování – náhled

pomocí této HoloLens aktualizace Windows Holographic for Business umožňuje nastavení optimalizace doručení snížit spotřebu šířky pásma pro stahování z více zařízení HoloLens. úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: [optimalizace doručení pro Windows 10 aktualizace](/windows/deployment/update/waas-delivery-optimization).

Následující nastavení jsou povolená jako součást plochy pro správu a [dají se nakonfigurovat z Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik aspektů informací o této nabídce Preview:

- podpora HoloLens je v této verzi preview omezená jenom na aktualizace operačního systému.
- Windows Holographic for Business podporuje jenom režimy stahování HTTP a stažené soubory z [koncového bodu připojené mezipaměti microsoftu](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). režimy stahování peer-to-peer a přiřazení skupin se v tuto chvíli nepodporují pro HoloLens zařízení.
- HoloLens nepodporuje optimalizaci nasazení nebo doručování pro koncové body Windows Server Update Services.
- poradce při potížích bude vyžadovat buď diagnostiku serveru připojené mezipaměti, nebo shromažďovat trasování na HoloLens HoloLens prostřednictvím **Nastavení**  >  **aktualizace zabezpečení &**  >     >   **web Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – aktualizovat kontrolní seznam

Tento kontrolní seznam vám pomůže zjistit nové položky, které funkce přidávají v této aktualizaci funkcí, které můžou ovlivnit vaše aktuální konfigurace správy zařízení, nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace pro celoobrazovkový režim

✔️ [**Nový AUMIDs pro nové aplikace v celoobrazovkovém režimu**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

pokud jste dřív používali aplikaci Nastavení nebo aplikaci Microsoft Edge na veřejném terminálu, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si přečetli [nové AUMIDs pro nové aplikace v celoobrazovkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes) níže. tím zajistíte, že budete mít v terminálu i nadále aplikaci Nastavení, nebo zadáte novou aplikaci Microsoft Edge. Tyto změny se dají udělat hned a nasazovat na všechna zařízení a v případě aktualizace umožňují hladký přechod.

✔️ [**Automatické přihlášení návštěvníka pro veřejné terminály**](#visitor-auto-logon-for-kiosks):

Návštěvníci se teď můžou automaticky přihlásit do veřejného terminálu. Toto chování je ve výchozím nastavení zapnuté, ale může být spravované a zakázané.

✔️ [**vylepšené zpracování chyb v celoobrazovkovém režimu**](#kiosk-mode-behavior-changes-for-handling-of-failures):

pokud není úspěšně zjištěno členství v AAD skupině přihlášeného AAD uživatele, pak se globální konfigurace veřejného terminálu používá v nabídce start (pokud je k dispozici). v opačném případě se uživateli zobrazí prázdná nabídka start. I když prázdná nabídka Start není konfigurací, kterou můžete nastavit přímo, může to být tím, že toto nové zpracování bude informovat vaše oddělení podpory, pokud používáte veřejné terminály, protože to může platit pro vaše konfigurace nebo můžete chtít udělat nové úpravy pro vaše přiřazené konfigurace přístupu.

#### <a name="updates-to-page-settings-visibility"></a>aktualizace stránky Nastavení viditelnost

✔️ [**nové identifikátory uri Nastavení pro stránku Nastavení viditelnost**](#new-settings-uris-for-page-settings-visibility)

pokud aktuálně používáte [stránku Nastavení viditelnost](settings-uri-list.md) , možná budete chtít upravit existující identifikátory uri, které jste buď povolili, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC

✔️ pokud jste předtím Microsoft Edge přes WDAC, budete chtít zásady WDAC aktualizovat. Zkontrolujte prosím následující a použijte poskytnutý vzorový kód.

#### <a name="enable-new-endpoints-for-edge"></a>Povolit nové koncové body pro Edge

✔️ pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je například proxy server nebo brána firewall, povolte tyto nové koncové body pro novou aplikaci Microsoft Edge.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ [nakonfigurovat nouzovou diagnostiku](#configuring-fallback-diagnostics-via-settings-app): můžete nakonfigurovat, jestli a kdo může shromažďovat nouzovou diagnostiku.

✔️[sdílet s okolními zařízeními](#share-things-with-nearby-devices): můžete zakázat novou funkci okolního sdílení.

✔️ [konfigurace nastavení zásad pro nové Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): projděte si nově dostupné konfigurace pro Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nový diagnostický nástroj

✔️[nové trasování diagnostiky operačního systému](#new-os-diagnostic-traces): Shromážděte protokoly související s AKTUALIZACEMI operačního systému.

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- [Offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics) bude obsahovat také další informace o zařízení pro sériové číslo a verzi operačního systému.
- Opravuje problém týkající se nasazení obchodních aplikací prostřednictvím balíčků zřizování za běhu.
- Opravuje problém týkající se zasílání zpráv o stavu instalace obchodní aplikace.
- Opravuje problém týkající se trvalosti nových balíčků aplikací napříč obnovením zařízení.
- Opravuje problém, který by mohl vést k nesprávným zadávaným symbolům pro japonské zákazníky.
- Vylepšuje odolnost aktualizací operačního systému u předinstalovaných aplikací, jako je třeba Edge.
- Řeší spolehlivost aktualizace, která má vliv na instalaci Microsoft Edge.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holografická verze 20H2 – květen 2021 Update

- Sestavení 19041,1146

Vylepšení a opravy v aktualizaci:

- tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet naše nejnovější buildy Windows holografické 21H1 verze.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holografická verze 1903 – květen 2021 Update

- Sestavení 18362,1110

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné významné změny. V **tomto sestavení už nebudete dostávat měsíční aktualizace služeb**. doporučujeme, abyste si vyzkoušeli naše nejnovější sestavení Windows holografické 21H1.

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z dubna 2021

- Build 19041.1144

Vylepšení a opravy v aktualizaci:

- Opravuje problém s hlášením stavu instalace obchodních aplikací.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z dubna 2021

- Build 18362.1108

Vylepšení a opravy v aktualizaci:

- Řeší problém, kdy Nastavení aplikace při pokusu o změnu hesla místního účtu dojde k chybě aplikace.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z března 2021

- Build 19041.1140

Vylepšení a opravy v aktualizaci:

- Zákazníci, kteří k pořizování fotek pomocí HoloLens 2 používají AdvancedPhotoCapture nebo LowLagPhotoCapture, teď 3 sekundy po zachycení fotky načítá pozici fotoaparátu.
- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba vyvolala zvýšené využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.
- Opravili jsme problém, kdy se uživatelé zaregistrovaní ve fázi rolloutu k zařízení nepokusili přihlásit.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z března 2021

- Build 18362.1102

Vylepšení a opravy v aktualizaci:

- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba vyvolala zvýšené využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z února 2021

- Build 19041.1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém s počátečním nastavením zařízení a aktualizacemi aplikací pro Store.
- Řeší problém s upgrady a lety pro pozdější HoloLens verze.
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM HoloLens zařízení.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z února 2021

- Build 18362.1098

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z ledna 2021

- Build 19041.1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spouštění, obnovování a přepínání uživatelů, pokud je na zařízení mnoho uživatelů.
- Přidání podpory arm32 pro [Research Mode](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z ledna 2021

- Build 18362.1091

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, verze 20H2 – aktualizace z prosince 2020

- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací

Přidáváme **novou funkci (Instalační program aplikací),** která vám umožní bezproblémověji instalovat aplikace na zařízení s HoloLens 2. Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.** Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:

- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní aplikace MDM, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) musí být aplikace digitálně podepsané nástrojem Sign [Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a certifikát použitý k podepsání musí být pro zařízení HoloLens důvěryhodný, aby bylo možné aplikaci nasadit.

**Pokyny k instalaci aplikace.**

1. Ujistěte se, že se vaše zařízení nepovažuje za spravované.
1. Ujistěte se, že HoloLens 2 je zapnuté a připojené k počítači.
1. Ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1. Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní Storage\Soubory ke stažení.   Po zkopírování souboru můžete zařízení odpojit.
1. Na svém HoloLens 2 Otevřete nabídku Start, vyberte Všechny aplikace a spusťte Průzkumník souborů aplikaci.
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat Toto zařízení a pak přejít na Položky ke stažení.
1. Vyberte soubor yourapp.appxbundle.
1. Spustí Instalační program aplikací. Výběrem tlačítka Install (Nainstalovat) nainstalujte aplikaci.
Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

Ukázkové aplikace najdete na Windows [univerzálních GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) testování tohoto toku.

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí Instalační program aplikací](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování rukou teď udržuje sledování v mnoha nových případech, kdy by se dříve ztratila rukou.  V některých z těchto nových případů se bude aktualizovat pouze pozice uživatele na základě jeho skutečné ruky, zatímco druhá pozice je odvozena na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako je plevání, odhazování, tlesání a tlesění.  Pomáhá také v případech, kdy se ruce nachází blízko povrchu nebo drží objekt.  Při odvozování ručního odhadu se hodnota společné přesnosti nastaví na "Approximate" (Přibližný) místo na High (Vysoká). [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)
- Opravili jsme problém, kdy se při resetování kódu PIN pro účty Azure AD zobrazí chyba Něco se pokazilo.
- Při spouštění ET, Iris z aplikace nastavení, nového uživatele nebo informační zprávy by uživatelé měli vidět mnohem méně selhání při spuštění.
- Uživatelé by měli mít správné časové pásmo přicházející z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z prosince 2020

- Build 18362.1088

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější verzi Windows Holographic verze 20H2–prosinec 2020 Update a novou funkci Instalační program aplikací přidanou v sestavení.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, verze 20H2

- Build 19041.1128

Windows Holographic verze 20H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a IT specialisty. Od funkce automatického umístění oka až po Správce certifikátů v Nastavení, vylepšené funkce bezobrazovkovém režimu a nové možnosti nastavení Autopilotu. Tato nová aktualizace umožňuje IT týmům převzít podrobnější kontrolu nad konfigurací a správou HoloLens zařízení a nabízí uživatelům ještě hladká holografická prostředí.

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční vydání verze 2004 (build 19041). Na číslo sestavení se můžete podívat na obrazovce Nastavení > o aplikaci a ověřit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co je nového v Windows Holographic verze 20H2  

| Funkce                                              | Popis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Podpora funkce Auto Eye Position](hololens-release-notes.md#auto-eye-position-support) | Aktivně počítá pozice očí, aniž by uživatelé prošli sledováním očí.   |
| [Správce certifikátů](hololens-release-notes.md#certificate-manager)   | Umožňuje nové jednodušší metody instalace a odebrání certifikátů z Nastavení aplikace.     |
| [Automatické spuštění zřizování z USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Zřizovací balíčky na USB jednotkách automaticky zobrazí výzvu ke zřízení stránky pro spuštění počítače.                                                         |
| [Automatické potvrzení zřizovacího balíčku v OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Zřizovací balíčky se na stránce zřizování automaticky použijí během spuštění při spuštění zařízení.                                                         |
| [Automatické zřizování bez použití uživatelského rozhraní](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak kombinovat automatické spouštění zřizování a automatické potvrzení. |
| [Použití autopilotu pomocí Wi-Fiho připojení](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Použijte autopilot ze zařízení Wi-Fi bez potřeby adaptéru sítě Ethernet. |
| [Tenantlockdown CSP a autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po registraci tenanta a použití zásady je možné zařízení zaregistrovat jenom v tomto tenantovi, kdykoli se zařízení resetuje nebo znovu zabliká. |
| [Globální přiřazený přístup](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nová metoda konfigurace pro celoobrazovkový režim s více aplikacemi, který využívá veřejný terminál na úrovni systému a který se vztahuje na všechny.                  |
| [Automatické spuštění aplikace v celoobrazovkovém terminálu s více aplikacemi](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Nastaví aplikaci tak, aby se spouštěla automaticky při přihlášení do celoobrazovkového režimu s více aplikacemi.                                                        |
| [Změny chování celoobrazovkového režimu pro zpracování selhání](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Chyba celoobrazovkového režimu teď má omezující zálohu.                                                                                                |
| [HoloLens Konfigurovaný](hololens-release-notes.md#hololens-policies)                                    | Nové zásady pro HoloLens.     |
| [Ukládání členství ve skupině Azure AD do mezipaměti pro celoobrazovkový terminál](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nové zásady umožňují uživatelům používat mezipaměť členství ve skupině pro použití celoobrazovkového režimu offline pro nastavený počet dnů.                                        |
| [nové zásady omezení pro zařízení HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | zásady správy zařízení povolené nově povoleným HoloLens 2.                                                                                |
| [nové zásady napájení pro HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nově podporované zásady pro nastavení časového limitu napájení.  |
| [Aktualizovat zásady](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nově povolené zásady umožňují kontrolu aktualizací.           |
| [povolená Nastavení viditelnost stránky pro HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | zásady, které vám umožní vybrat, které stránky se zobrazí v aplikaci Nastavení.             |
| [Režim výzkumu](hololens-release-notes.md#research-mode) | použití výzkumného režimu na HoloLens 2. |
| [Zvýšení délky záznamu](hololens-release-notes.md#recording-length-increased) | Nahrávky MRC už nejsou omezené na 5 minut. |
| [Vylepšení a opravy v aktualizaci](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Další opravy v aktualizaci.   |

### <a name="auto-eye-position-support"></a>Podpora pozice automatického oka

ve HoloLens 2 se poloha oka povoluje přesnou polohu hologramu, pohodlné zobrazení a vylepšená kvalita zobrazení. Pozice oka se vypočítávají interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel přešel přes kalibraci sledování očí, a to i v případě, že prostředí nemusí vyžadovat pohledu.

**Pozice pro automatické oči (AEP)** umožňuje těmto scénářům, které jsou v rámci interakce k dispozici, způsob výpočtu očí pro uživatele. Pozice automatického oka začne pracovat na pozadí automaticky od okamžiku, kdy uživatel zařízení umístí. Pokud uživatel nemá k dispozici kalibraci pro sledování očí, začne poloha automatického oka začínat umístěním očí uživatele do zobrazovacího systému po dobu zpracování 20-30 sekund. Uživatelská data se v zařízení neukládají, takže se tento proces opakuje, pokud uživatel odchází a znovu ho zaznamená nebo pokud se zařízení restartuje nebo se probudí z režimu spánku.

K dispozici je několik změn chování systému s funkcí pozice automatického oka, když uživatel do zařízení vloží nekalibrovaného uživatele. V tomto kontextu se nekalibrovaný uživatel odkazuje na někoho, kdo předtím neprošlý procesem kalibrace sledování očí na zařízení.

| Aktivní aplikace | Předchozí chování | chování z Windows holografické verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace, která není povolená pohledu, nebo holografické prostředí |Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Výzva k kalibraci sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke pohledumu streamu očí. |

Pokud uživatel přejde z aplikace s povoleným pohledu na jednu, která přistupuje k datům pohledu, zobrazí se výzva k kalibraci.

Všechny ostatní chování systému budou podobné jako v případě, kdy aktuální uživatel nemá aktivní sledování očí. Například ruční gesto spuštění nebude povoleno. Při počátečním nastavení se neprojeví žádné změny v prostředí před prvním nastavením.

Pro prostředí, která vyžadují pohledu data nebo velmi přesné umístění na hologram, doporučujeme nekalibrovaným uživatelům spustit kalibraci sledování očí. je přístupná z výzvy k kalibraci sledování očí nebo spuštěním aplikace Nastavení z nabídky start a následným výběrem kalibrace **> systému > kalibraci očí > kalibraci běhu**.

Tyto informace se dají najít později s [dalšími informacemi o kalibraci](hololens-calibration.md#auto-eye-position-support).

### <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené auditování, diagnostika a nástroje ověřování pro zabezpečení zařízení a dodržování předpisů prostřednictvím nového správce certifikátů. Tato funkce vám umožní nasadit, řešit potíže a ověřit škálování vašich certifikátů v komerčních prostředích.

v Windows holografické verze 20H2 přidáváme do aplikace HoloLens 2 Nastavení správce certifikátů. přejít na **Nastavení > aktualizace & certifikátů zabezpečení >**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů na vašem zařízení. Díky novému Správci certifikátů a správcům a uživatelům teď vylepšili Nástroj pro auditování, diagnostiku a ověřování, aby zařízení zůstala zabezpečená a kompatibilní.

- **Auditování:** Možnost ověřit, jestli je certifikát správně nasazený, nebo ověřit, že se certifikát odebral správně.
- **Diagnostika:** V případě problémů se ověří, že na zařízení existují vhodné certifikáty, které šetří čas a pomáhají při řešení problémů.
- **Ověření:** Ověření, že certifikát slouží k zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Chcete-li v seznamu rychle najít konkrétní certifikát, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé můžou taky certifikát vyhledat přímo. Chcete-li zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na tlačítko **informace**.

Instalace certifikátu v současné době podporuje soubory. cer a. CRT. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  všechny ostatní uživatele lze instalovat pouze do aktuálního uživatele. uživatelé můžou odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.

#### <a name="steps-to-install-a-certificate"></a>Postup instalace certifikátu

1. Připojení HoloLens 2 k počítači.
1. soubor certifikátu, který chcete nainstalovat, umístěte do umístění na vašem HoloLens 2.
1. přejděte na **Nastavení > aktualizace & > certifikátů zabezpečení** a vyberte nainstalovat certifikát.
1. Klikněte na **importovat soubor** a přejděte do umístění, kam jste certifikát uložili.
1. Vyberte **umístění úložiště**.
1. Vyberte **úložiště certifikátů**.
1. Klikněte na **Install** (Nainstalovat).

Certifikát by se teď měl nainstalovat na zařízení.

#### <a name="steps-to-remove-a-certificate"></a>Postup odebrání certifikátu

1. přejděte na **Nastavení App > aktualizace a > certifikáty zabezpečení**.
1. Ve vyhledávacím poli vyhledejte certifikát podle názvu.
1. Vyberte certifikát.
1. Klikněte na **Odebrat** .
1. Po zobrazení výzvy k potvrzení vyberte **Ano** .

![prohlížeč certifikátů v aplikaci Nastavení.](images/certificate-viewer-device.jpg)

![Obrázek ukazující, jak použít uživatelské rozhraní certifikátu k instalaci certifikátu.](images/certificate-device-install.jpg)

Tyto informace se dají najít později [na nové stránce Správce certifikátů](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňují menší interakci s uživatelem, když se při počátečním spuštění počítače použijí jednotky USB s Zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek spustit zřizování obrazovky ručně. Uživatelé teď můžou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na USB paměťové jednotce.

1. Připojte se k jednotce USB pomocí zřizovacího balíčku během prvního prozatím Provisioning OOBE
1. Když je zařízení připravené k zřízení, automaticky se otevře výzva se stránkou zřizování.

Poznámka: Pokud se jednotka USB v době, kdy se zařízení spouští, dokončí, vytvoří OOBE výčet existujícího úložného zařízení USB a sledujte další zařízení, která jsou zapojená do sítě.

další informace o použití zřizovacích balíčků při spuštění OOBE najdete v dokumentaci pro [zřizování HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) .

další informace o [automatickém spuštění zřizování z USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) najdete v dokumentaci pro zřizování HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacích balíčků v OOBE

- Automatizovaný proces – při zobrazení stránky zřizovacího balíčku se automaticky použije všechny uvedené balíčky.

Když se objeví hlavní obrazovka zřizování, počáteční čas se bude počítat 10 sekund, než se automaticky začnou používat všechny zřizovací balíčky. Po ověření balíčků, které se očekávají, můžou uživatelé tuto dobu 10 sekund [potvrdit i zrušit](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) .

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní

- Kombinované automatické procesy pro zajištění omezeného počtu interakcí zařízení pro zřizování.

díky kombinaci automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovacích balíčků může uživatel zřídit zařízení HoloLens 2 automaticky bez použití uživatelského rozhraní zařízení nebo dokonce zařízení. Můžete nadále používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení několika zařízení najednou ve stejné oblasti.

1. [vytvořte zřizovací balíček](hololens-provisioning.md) pomocí [návrháře konfigurace Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22).
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Flash HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) až [19041,1361 nebo novější sestavení](https://aka.ms/hololens2previewdownload).
1. Až [Průvodce pokročilým obnovením](https://www.microsoft.com/store/productId/9P74Z35SFRS8) dokončí blikání vašeho zařízení, odpojte kabel USB-C.
1. Připojte jednotku USB k zařízení.
1. když se zařízení HoloLens 2 spustí do režimu OOBE, automaticky rozpozná zřizovací balíček na jednotce USB a spustí stránku zřizování.
1. Po 10 sekundách bude zařízení automaticky používat zřizovací balíček.

Vaše zařízení je teď nakonfigurované a [zobrazí se úspěšná obrazovka zřizování](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Použití autopilotu pomocí Wi-Fiho připojení

- Odebráním potřebných adaptérů USB-C pro ethernetové snížení potřeb hardwaru umožníte funkci autopilotu fungovat na Wi-Fi připojených zařízeních.

po připojení HoloLens 2 k síti Wi-Fi teď při spuštění nástroje oobe zkontroluje profil automatického pilotního nasazení pro zařízení. pokud se najde, bude se používat k dokončení AAD připojení a toku registrace. Jinými slovy, použití sítě Ethernet pro USB-C nebo Wi-Fi do adaptéru USB-C ještě není požadavkem, ale budou fungovat i v případě, že jsou k dispozici na začátku počátečního nastavení. přečtěte si další informace o [autopilotu pro zařízení HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a autopilot

- Zachovává zařízení v tenantovi organizace tím, že je zamkne na tenanta i přes resetování nebo reflash zařízení. Díky dalšímu zabezpečení zakážete vytváření účtů prostřednictvím zřizování.

HoloLens 2 zařízení nyní podporují zprostředkovatele CSP pro [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2).

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby HoloLens 2 byly vázané jenom na registraci MDM jenom pomocí autopilotu. jakmile se uzel RequireNetworkInOOBE poskytovatele TenantLockdown CSP nastaví na hodnotu true nebo false (zpočátku nastavená) na HoloLens 2, tato hodnota zůstane na zařízení i bez ohledu na to, jestli se jedná o opětovné spuštění, aktualizace operačního systému atd.

jakmile je uzel TenantLockdown csp ' RequireNetworkInOOBE ' nastaven na hodnotu true v HoloLens 2, bude po připojení k síti znovu čekat na neomezenou dobu pro stažení a použití profilu autopilotu.

jakmile je uzel TenantLockdown csp ' RequireNetworkInOOBE ' nastaven na hodnotu true u HoloLens 2, v počátečním souboru OOBE nejsou povoleny následující operace:

- Vytváření místního uživatele pomocí zřizování za běhu
- Provádění operace připojení ke službě Azure AD prostřednictvím zřizování za běhu
- Výběr toho, kdo zařízení vlastní v prostředí OOBE

#### <a name="how-to-set-this-using-intune"></a>Jak ho nastavit pomocí Intune?

1. Vytvořte vlastní konfigurační profil zařízení OMA URI a zadejte hodnotu true pro uzel RequireNetworkInOOBE, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamčení klienta pomocí OMA-URI.](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení.

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>jak zrušit nastavení RequireNetworkInOOBE TenantLockdown na HoloLens 2 pomocí intune?

1. odeberte HoloLens 2 ze skupiny zařízení, ve které byla výše vytvořená konfigurace zařízení dříve přiřazena.

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru OMA URI a zadejte hodnotu false pro RequireNetworkInOOBE, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím identifikátoru URI OMA v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení.

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky TenantLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>co se stane při počátečním spuštění, pokud je profil autopilotu nepřiřazený u HoloLens po nastavení TenantLockdown na hodnotu true?

Při POČÁTEČNÍm navýšení bude profil pro autopilot čekat na neomezenou dobu stahování a zobrazí se dialogové okno. Aby se odstranily účinky TenantLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí jenom autopilotu a RequireNetworkInOOBE musí být nastavené tak, jak je popsané v předchozím kroku, než se odeberou omezení zavedená poskytovatelem CSP pro TenantLockdown.

![Zobrazení v zařízení pro dobu, kdy se na zařízení vynutila zásada.](images/hololens-autopilot-lockdown.png)

Tyto informace se teď dají najít spolu se zbytkem autopilotu v rámci [TENANTLOCKDOWN CSP a autopilotu](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – celoobrazovkový režim

- Omezená Správa identit pro veřejný terminál tím, že povolíte novou metodu veřejného terminálu, která na úrovni systému aplikuje celoobrazovkový režim.

tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro celoobrazovkový celoobrazovkový režim, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. další informace o této nové funkci najdete podrobněji v [HoloLens celoobrazovkovém režimu](hololens-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatické spuštění aplikace v celoobrazovkovém režimu s více aplikacemi

- Cílené prostředí s automatickým spouštěním aplikací, další zvyšování uživatelského rozhraní a výběrů aplikací vybraných pro prostředí v celoobrazovkovém režimu.

Platí jenom pro celoobrazovkový režim s více aplikacemi a jenom jedna aplikace může být určená k automatickému spuštění pomocí zvýrazněného atributu v konfiguraci přiřazeného přístupu.

Aplikace se automaticky spustí, když se uživatel přihlásí.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování celoobrazovkového režimu pro zpracování selhání

- Bezpečnější celoobrazovkový režim tím, že eliminuje dostupné aplikace v případě výpadků celoobrazovkového režimu.

dříve při selhání při použití celoobrazovkového režimu HoloLens použít k zobrazení všech aplikací v nabídce start. nyní v Windows holografické verze 20H2 v případě selhání nebudou v nabídce start zobrazeny žádné aplikace, jak je uvedeno níže:

![Obrázek, který celoobrazovkový režim teď vypadá, když se nezdařil.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Konfigurovaný

- možnosti správy zařízení specificky pro HoloLens vytvořené pro správu zařízení.

pro Windows holografické verze 20H2 se vytvořily nové zásady hybridních realit pro zařízení HoloLens 2. mezi nová poříditelné nastavení patří: nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v hybridních zachyceních realit, nastavení, kdy se může diagnostika shromáždit, a AAD mezipaměť členství ve skupině.  

| nové zásady HoloLens                                | Description                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Povolí vypnutí tlačítek jasu, takže se nemění jas.       | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Povolí vypnutí tlačítek hlasitosti, aby se při stisknutí této klávesy nezměnila hlasitost.               | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | zakáže mikrofon, takže není možné nahrávat zvuk na HoloLens 2.                      | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\FallbackDiagnostics                   | Řídí chování, kdy se můžou shromažďovat diagnostické protokoly.                               | 0 zakázané, 1 povoleno pro vlastníky zařízení, 2 povoleno pro všechny (výchozí) |
| MixedReality\HeadTrackingMode                      | Vyhrazeno pro budoucí použití.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Určuje, kolik dní se mezipaměť členství ve skupině Azure AD používá pro veřejné terminály, které cílí na skupiny Azure AD. | Viz níže.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro celoobrazovkový terminál

- povolené Offline veřejné terminály, které se mají používat s AADmi skupinami po dobu až 60 dnů.

Tato zásada určuje, kolik dní se má pro přihlášeného uživatele použít mezipaměť členství ve skupině Azure AD pro přiřazené konfigurace přístupu, které cílí na skupiny Azure AD. Jakmile je tato hodnota zásad nastavená na hodnotu větší než 0, použije se mezipaměť v opačném případě.  

Název: hodnota identifikátoru URI AADGroupMembershipCacheValidityInDays:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 dnů  
Max. 60 dní

Postup pro správné použití této zásady:

1. vytvořte profil konfigurace zařízení pro webdirectory cílící na skupiny Azure AD a přiřaďte ho k HoloLens zařízením.
1. vytvořte vlastní konfiguraci zařízení založenou na identifikátoru OMA URI, která nastaví hodnotu této zásady na požadovaný počet dní (> 0) a přiřaďte ji do HoloLens zařízení.
    1. Do textového pole OMA-URI by se měla zadat hodnota identifikátoru URI jako./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Hodnota může být mezi minimální a maximální povolenou hodnotou.
1. zaregistrujte zařízení HoloLens a ověřte, že se obě konfigurace na zařízení nastavily.
1. Umožněte uživateli Azure AD 1 přihlášení, když je dostupný internet, po přihlášení uživatele a členství ve skupině Azure AD se vytvoří mezipaměť.
1. uživatel Azure AD 1 teď může HoloLens offline a používat ho pro celoobrazovkový režim, pokud hodnota zásady umožňuje X počet dnů.
1. Kroky 4 a 5 se můžou opakovat pro všechny ostatní uživatele Azure AD N. klíčovým bodem, který tady znamená, že se musí přihlásit k zařízení přes Internet, aby aspoň jednou bylo možné určit, že jsou členy skupiny Azure AD, na kterou cílí konfigurace veřejného terminálu.

> [!NOTE]
> Dokud se krok 4 neprovede pro uživatele Azure AD, dojde k chování při selhání zmíněném v "odpojeném" prostředí.

### <a name="new-device-restriction-policies-for-hololens-2"></a>nové zásady omezení pro zařízení HoloLens 2

- Umožňuje uživatelům spravovat konkrétní zásady správy zařízení, jako je například blokování přidávání nebo odebírání zřizovacích balíčků.

nově povolené zásady, které umožňují více možností správy zařízení HoloLens 2.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Tyto dvě nové zásady pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> v souvislosti s [RemoteLock](/windows/client-management/mdm/remotelock-csp)bude HoloLens podporovat jenom konfiguraci./Vendor/MSFT/RemoteLock/Lock. Konfigurace, které se týkají kódu PIN, jako je resetování a obnovení, se nepodporují.

### <a name="new-power-policies-for-hololens-2"></a>nové zásady napájení pro HoloLens 2

- další možnosti při HoloLens režimu spánku nebo zámků prostřednictvím zásad napájení.

Tyto nově přidané zásady umožňují správcům řídit stavy napájení, jako je například časový limit nečinnosti. Pokud si chcete přečíst více o jednotlivých zásadách, klikněte prosím na odkaz pro tuto zásadu.

|     Odkaz na dokumentaci k zásadám                |     Poznámky                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     ukázková hodnota, která se má použít v návrháři konfigurace Windows, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové zásady pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> pro konzistentní prostředí HoloLens 2 prosím zajistěte, aby byly hodnoty pro obě DisplayOffTimeoutOnBattery a StandbyTimeoutOnBattery nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti o moderním pohotovostním režimu najdete v tématu o [časovačích nečinných pro zobrazení, přechod do režimu spánku a hibernace](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### <a name="newly-enabled-update-policies-for-hololens"></a>Nově povolené zásady aktualizace pro HoloLens

- Další možnosti pro instalaci aktualizací nebo zakázání tlačítka pozastavit aktualizace, aby se zajistila aktualizace.

v zařízeních HoloLens 2 jsou teď povolené tyto zásady aktualizace:

- [Aktualizovat/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Aktualizovat/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Aktualizovat/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Aktualizovat/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

úplné podrobnosti o těchto zásadách aktualizace a jejich použití pro HoloLens zařízení je možné číst v tématu [správa aktualizací HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>povolená Nastavení viditelnost stránky pro HoloLens 2

- vylepšené řízení uživatelského rozhraní v aplikaci Nastavení, které může být zaměňováno k zobrazení omezeného výběru stránek.

nyní jsme povolili zásadu, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené. Informace o tom, jak tuto funkci plně přizpůsobit, získáte kliknutím na odkaz níže.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

pokud chcete zjistit, která nastavení stránky můžete přizpůsobit HoloLens 2, navštivte prosím naši [Nastavení na stránce identifikátory uri](settings-uri-list.md).

![snímek obrazovky s aktivními hodinami upravovanými v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu

v rámci výzkumného režimu se HoloLens 2 stal nástrojem potent pro výzkum počítačových visionů. v porovnání s předchozími edicemi má výzkumný režim pro HoloLens 2 následující výhody:

- kromě senzorů vystavených v HoloLens (1.1. generace) průzkumu teď poskytujeme přístup ke senzorům IMU, včetně měřičů akcelerometr, vybavený gyroskopem a magnetometer.
- HoloLens 2 poskytuje nové funkce, které se dají použít společně s výzkumným režimem. Konkrétně přístup k rozhraním API pro sledování kloubů a sledování očí, který může poskytovat bohatší sadu experimentů.

výzkumníki teď mají možnost povolit výzkumný režim na svých zařízeních HoloLens pro přístup ke všem těmto externím proudům s nezpracovanými obrazci. výzkumný režim pro HoloLens 2 také poskytuje přístup ke čtení akcelerometr, vybavený gyroskopem a magnetometer. V zájmu ochrany osobních údajů uživatelů nejsou k dispozici obrázky z nezpracovaného oka pro sledování očí prostřednictvím výzkumného režimu, ale směr pohledu je k dispozici prostřednictvím existujících rozhraní API.

Další technické podrobnosti najdete v [dokumentaci ke výzkumnému režimu](/windows/mixed-reality/research-mode) .

### <a name="recording-length-increased"></a>Zvýšení délky záznamu

Z důvodu zpětné vazby od zákazníků jsme zvýšili délku nahrávání u [hybridních zachycení realit](holographic-photos-and-videos.md). Ve výchozím nastavení se hybridní zachycení realit nebudou standardně omezovat na 5 minut, ale místo toho se vypočítá maximální délka nahrávání na základě dostupného místa na disku. Zařízení bude odhadnout maximální dobu trvání nahrávání videa na základě dostupného místa na disku až do 80% celkového místa na disku.

> [!NOTE]
> HoloLens použije výchozí délku nahrávání videa (5 minut), pokud dojde k jedné z následujících akcí:
>
> - Odhadovaná maximální doba trvání záznamu je menší než výchozí hodnota 5 minut.
> - Dostupné místo na disku je méně než 20% celkového místa na disku.

Plné požadavky najdete v dokumentaci k [holografickým fotografiím a videím](holographic-photos-and-videos.md#maximum-recording-length) .

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>vylepšení a opravy ve Windows holografické verzi 20H2 update:

- Další obrazovky v OOBE jsou nyní v tmavém režimu.
- Další obsah by měl odkazovat na nejnovější prohlášení o zásadách ochrany osobních údajů online.
- Vyřešili jsme problém, kdy uživatelé nemohli zřizovat profily sítě VPN prostřednictvím zřizovacích balíčků.
- Problémy s konfigurací pevného proxy serveru pro připojení VPN
- Aktualizované zásady pro zakázání výčtu funkcí USB prostřednictvím MDM pro NCM pro AllowUsbConnection.
- vyřešili jsme problém, který brání zobrazení zařízení HoloLens v průzkumníkovi souborů přes protokol MTP (Media Transfer Protocol), když se zařízení nastaví jako veřejný [terminál s jednou aplikací](hololens-kiosk.md). Upozorňujeme, že MTP (a připojení USB obecně) je možné dál zakázat pomocí zásad [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- opravili jsme problém, kdy se v celoobrazovkovém režimu správně škálují ikony v nabídka Start.
- Opravili jsme problém, protože mezipaměť HTTP koliduje s režimem celoobrazovkového režimu, který je zaměřený na skupiny Azure AD.
- Opravili jsme problém, kdy uživatelé nedokázali použít tlačítko dvojice po povolení vývojářského režimu s zřizovacími balíčky, pokud je nezakáže a znovu nepovolí vývojářský režim.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holografická verze 1903 – aktualizace z listopadu 2020

- Sestavení 18362,1085

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet naše nejnovější buildy pro vydání funkcí Windows holografické 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holografická verze 2004 – říjen 2020 – aktualizace

- Sestavení 19041,1124

Vylepšení a opravy v aktualizaci:

- Odstranila se nepotřebná kontrolu, která způsobila chybu běhového systému.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holografická verze 1903 – říjen 2020 – aktualizace

- Sestavení 18362,1081

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows holografické verze 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holografická verze 2004 – září 2020 aktualizace

- Sestavení 19041,1117

Vylepšení a opravy v aktualizaci:

- řeší problém, který zabránil Visual Studio ladění aplikace v případě, že v appxmanifest existuje SupportsMultipleInstances = "true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která se nezdařila kvůli selhání detekce Internetu prostřednictvím síťového proxy serveru. NCSI může k detekci připojení k Internetu použít proxy server a proxy server pro jednotlivé profily. NcSI bude v budoucí verzi podporovat proxy pro uživatele.
- Ve většině Windows Mixed Reality zařízení je směrový vektor vpřed paralelně se zemí, když je hlavička uživatele v neutrální pozici a hledí dopředu. Starší verze sady HoloLens 2 však zarovnaly vektor tak, aby byl perpenduován k panelům zobrazení, což je o několik stupňů dolů vzhledem k ideální orientaci. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.
- Tato verze obsahuje opravu pro zlepšení kvality časového razítka zvuku, která může přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, verze 1903 – aktualizace ze září 2020

- Build 18362.1079

Vylepšení a opravy v aktualizaci:

- Ve většině Windows Mixed Reality zařízení je směrový vektor vpřed paralelně se zemí, když je hlavička uživatele v neutrální pozici a hledí dopředu. Starší verze sady HoloLens 2 však zarovnaly vektor tak, aby byl perpenduován k panelům zobrazení, což je o několik stupňů dolů vzhledem k ideální orientaci. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze srpna 2020

- Build 19041.1113

Vylepšení a opravy v aktualizaci:

- Nastavení už uživatele nebude sledovat v prostředích pro registraci Iris nebo sledování očí.
- Opravili jsme chybu, kdy se při použití zřizovacího balíčku během spuštění počítače, který přejmenovává zařízení a provádí další akce (například připojování k síti), nepodařilo kvůli přejmenování provést další akce po restartování zařízení.
- Úprava barevného schématu toků počátečního nastavení zařízení za účelem zlepšení vizuální kvality

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, verze 1903 – aktualizace ze srpna 2020

- Build 18362.1074

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, verze 2004 – aktualizace z července 2020

- Build 19041.1109

Vylepšení a opravy v aktualizaci:

- Vývojáři si teď mohou vybrat mezi povolením nebo zakázáním Portál zařízení vyžadovat zabezpečené připojení.
- Vylepšili jsme spolehlivost spouštění aplikací po aktualizacích operačního systému.
- Změna výchozího jasu doručené pošty na 100 %.
- Byl vyřešen problém s předáváním HTTPS pro Windows Portál zařízení na HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z července 2020

- Build 18362.1071

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který mohl způsobovat, že hologramy při ztrátě nebo obnovení sledování zmizely v aplikacích Unity.
- Opravili jsme problém, který způsoboval HoloLens aplikace se při použití rozhraní HoloLens Emulator hardwarovou akcelerací na určitých zařízeních vrací zpět do prostředí.
- Byl vyřešen problém týkající se předávání HTTPS pro Windows Portál zařízení na HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, verze 2004 – aktualizace z června 2020

- Build 19041.1106

Vylepšení a opravy v aktualizaci:

- Vlastní záznamníky MRC teď mají nové výchozí hodnoty pro určité vlastnosti, pokud nejsou zadané.
  - On the *MRC Video Effect*:.
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Imerzivní náhlavní souprava))
  - Zvukový *efekt MRC:*
    - LoopbackGain (aktuální hodnota "App Audio Gain" na Záznam hybridní reality stránce v Windows Portál zařízení)
    - MicrophoneGain (aktuální hodnota Mic Audio Gain na Záznam hybridní reality stránce v Windows Portál zařízení)
- Opravili jsme chybu, která vylepšuje kvalitu zvuku ve scénářích zachycení hybridní reality. Konkrétně by tato oprava měla eliminovat potíže se zvukem v nahrávce, když se **zobrazí** nabídka Start.
- Vylepšená stabilita hologramů v zaznamenaných videích
- Vyřešili jsme problém, kdy zachytávání hybridní reality nemohlo po několika dnech v pohotovostním stavu nahrát video.
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení zorovače, i když bylo povolené nastavení Spustit na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Když k Portál zařízení přes Wi-Fi připojení, webový prohlížeč může přístup z důvodu neplatného certifikátu zabránit. Prohlížeč může nahlásit chybu typu "ERR_SSL_PROTOCOL_ERROR", i když byl certifikát zařízení dříve důvěryhodný. V takovém případě nemůžete postupovat k Portál zařízení, protože neexistuje možnost ignorovat upozornění zabezpečení. Tato aktualizace tento problém vyřešila. Pokud byl certifikát zařízení dříve stažen a na počítači důvěryhodný pro odebrání upozornění zabezpečení prohlížeče a dojde k chybě SSL, je třeba nový certifikát stáhnout a důvěřovat, aby se odstranila upozornění zabezpečení prohlížeče.
- Povolili jste možnost vytvořit zřizovací balíček modulu runtime, který může instalovat aplikaci pomocí balíčků MSIX.
- Přidali jsme nastavení **v Nastavení** System Hologramy, které uživatelům umožňuje automaticky odebrat všechny  >    >   hologramy z Mixed Reality domů, když se zařízení vypne.
- Opravili jsme problém, který způsob HoloLens, které změnily formát pixelů tak, aby se v emulátoru HoloLens pixelů vykreslují černě.
- Opravili jsme chybu, která způsoboval chybu při přihlášení Iris.
- Opravili jsme problém s opakovaným stahováním ze Storu pro již aktuální aplikace.
- Opravili jsme chybu, která znemožňoval opakovaným Microsoft Edge aplikacím.
- Opravili jsme problém se spuštěním aplikace Photos při počátečních spuštěních po aktualizaci z verze 1903.
- Vyšší výkon a spolehlivost.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z června 2020

- Build 18362.1064

Vylepšení a opravy v aktualizaci:

- Vlastní záznamníky MRC mají nové výchozí hodnoty určitých vlastností, pokud nejsou zadané.
  - On the *MRC Video Effect*:.
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Imerzivní náhlavní souprava))
  - Zvukový *efekt MRC:*
    - LoopbackGain (aktuální hodnota "App Audio Gain" na Záznam hybridní reality stránce v Windows Portál zařízení)
    - MicrophoneGain (aktuální hodnota Mic Audio Gain na Záznam hybridní reality stránce v Windows Portál zařízení)
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsobuje, že se některé aplikace po překlopení visoru pozastaví, a to i v případě, že je povolené nastavení pro spuštění na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Opravili jsme problém, který způsob HoloLens, které změnily formát pixelů tak, aby se v HoloLens Emulator.
- Opravili jsme problém se spuštěním aplikace Photos při počátečním spuštění po aktualizaci z verze 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, verze 2004

- Sestavení – 19041.1103

Hlavní aktualizace softwaru z května 2020 pro HoloLens 2, *Windows Holographic, verze 2004* obsahuje řadu zajímavých nových funkcí, jako je podpora Windows Autopilotu, tmavého režimu aplikací, podpora ethernetového připojení USB pro hotspoty 5G/LTE a mnoho dalšího. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete **aplikaci Nastavení,** přejděte na Update & Security a vyberte tlačítko    **Zkontrolovat** ****   aktualizace. 

|             Funkce                              |          Popis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Předběžná konfigurace a bezproblémové nastavení nových zařízení pro produkci pomocí Windows AutoPilotu                 |
|       Podpora FIDO 2                             |          Podpora klíčů zabezpečení FIDO2 pro povolení rychlého a zabezpečeného ověřování pro sdílená zařízení            |
|       Vylepšené zřizování                      |          Bezproblémové použití zřizovacího balíčku z USB flash disku do HoloLens                              |
|       Stav instalace aplikace                 |          Zkontrolujte stav instalace v Nastavení aplikace pro aplikace se přes MDM nas nabízené HoloLens 2.               |
|       Poskytovatelé konfiguračních služeb (CSP)   |          Přidání nových poskytovatelů konfiguračních služeb pro vylepšení možností řízení správy                 |
|       Podpora USB 5G/LTE                       |          Rozšířená ethernetová funkce USB umožňuje podporu pro 5G/LTE.                                    |
|       Tmavý režim aplikace                              |          Tmavý režim aplikace dostupný pro aplikace, které podporují tmavý i světlý režim, vylepšuje prostředí pro prohlížení.        |
|       Hlasové příkazy                             |          podpora dalších systémových hlasových příkazů pro řízení HoloLens bez jakýchkoli rukou                           |
|       Vylepšení sledování ruky                 |          Vylepšení ručního sledování usnadňuje tlačítka a 2D SLAT interakce                        |
|       Vylepšení a opravy kvality                 |          Různá vylepšení výkonu a spolehlivosti systému napříč platformou                            |

### <a name="support-for-windows-autopilot"></a>podpora Windowsho autopilotního nasazení

Windows automatický pilot pro HoloLens 2 umožňuje, aby byl prodejní kanál zařízení předem zaregistrován HoloLens do vašeho tenanta intune. Jakmile zařízení dorazí, budou připravená na samoobslužné nasazení jako sdílená zařízení v rámci vašeho tenanta. Aby bylo možné využít výhody samoobslužného nasazení, musí se zařízení připojit k síti během první obrazovky v instalačním programu pomocí technologie USB-C-to-Ethernet.

Poté, co uživatel spustí proces automatického nasazení autopilotu, proces provede následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD).
1. pomocí služby Azure AD zaregistrujete zařízení v Microsoft Intune (nebo jiné službě MDM).
1. Stáhněte si zásady, certifikáty a síťové profily zaměřené na zařízení.
1. Zřídí zařízení.
1. Prezentovat přihlašovací obrazovku uživateli

další informace najdete v [průvodci hodnocením Windows autopilot pro HoloLens 2](hololens2-autopilot.md).

*Obraťte se na svého správce účtu, abyste se připojili k programu autopilot Preview nyní. Zařízení, která jsou připravena k autopilotu, začnou brzy dodávat.*

### <a name="fido2-security-key-support"></a>Podpora klíče zabezpečení FIDO2

někteří uživatelé sdílejí zařízení HoloLens s ostatními v pracovním nebo školním prostředí. Proto je důležité, aby uživatelé mohli snadno bez psaní dlouhých uživatelských jmen a hesel. rychlá identita Online (FIDO) umožňuje všem uživatelům ve vaší organizaci (Azure AD tenant) bezproblémově se přihlašovat k HoloLens bez zadání uživatelského jména nebo hesla.

Klíče zabezpečení FIDO2 jsou "nepřesné" metody ověřování bez hesla založené na standardech, které mohou být v libovolném tvaru. FIDO je otevřený standard pro ověřování neheslem. Umožňuje uživatelům a organizacím přihlašovat se ke svým prostředkům bez uživatelského jména nebo hesla. Místo toho používají externí klíč zabezpečení nebo klíč platformy integrovaný do zařízení.

Informace o tom, jak začít, najdete v tématu [Povolení přihlášení k bezpečnostnímu klíči bez hesla](/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Vylepšená registrace MDM prostřednictvím zřizovacího balíčku

zřizovací balíčky umožňují nastavit HoloLens konfiguraci prostřednictvím konfiguračního souboru, a ne prostřednictvím HoloLens připraveného prostředí. dříve musely být zřizovací balíčky zkopírovány do HoloLens interní paměti. teď můžou být na jednotce USB, aby je bylo snazší znovu použít na více HoloLens zařízeních a můžete zařízení zřizovat paralelně. Zřizovací balíčky teď také podporují pole pro registraci ve správě zařízení, takže se po zřízení neprovádí ruční instalace.

Vyzkoušejte:

1. stáhněte si nejnovější verzi návrháře konfigurace Windows z Windows storu na váš počítač.
1. vyberte **zřídit HoloLens zařízení**  >  **zřídí HoloLens 2 zařízení**.
1. Sestavte konfigurační profil. Pak zkopírujte všechny soubory, které byly vytvořeny na paměťové zařízení USB-C.
1. Připojte zařízení USB-C k jakémukoli čerstvě blikajícímu HoloLens. Potom stisknutím tlačítka **hlasitosti dolů**  +   použijte balíček zřizování.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodní aplikace

Nasazení a Správa aplikací MDM pro obchodní aplikace je pro HoloLens zásadní. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. v této verzi jsme přidali další podrobnosti v **Nastavení**  >  **účty**  >  **přístup do práce nebo do školy**  >  klikněte na informace **o účtu**  >  .

### <a name="additional-csps-and-policies"></a>Další zprostředkovatelé CSP a zásady

[Zprostředkovatel kryptografických služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravy nebo odstranění nastavení konfigurace na zařízení. v této verzi přidáváme podporu pro další zásady, aby zvýšili správce řízení nad nasazením zařízení HoloLens. seznam csp, který podporuje HoloLens, najdete v tématu [NetworkQoSPolicy csp](/windows/client-management/mdm/networkqospolicy-csp).

Novinka v této verzi:

**Zprostředkovatel CSP pro zásady** 

poskytovatel služeb konfigurace zásad umožňuje podniku nakonfigurovat zásady na zařízeních Windows. v této verzi jsme přidali nové zásady pro HoloLens, které jsou tady uvedené. další informace najdete v tématu [zprostředkovatelé csp, které podporuje HoloLens 2](/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

Poskytovatel služby NetworkQoSPolicy Configuration Service vytvoří zásady technologie QoS (Quality of Service) sítě. Zásada QoS provede sadu akcí pro síťový provoz na základě sady podmínek, které splňují podmínky. Další informace najdete v tématu [NETWORKQOSPOLICY CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Rozšířená podpora USB Ethernet pro 5G/LTE připojená zařízení

přidala se podpora pro určitá mobilní širokopásmová zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když jsou připojené k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě** jako jiné připojení k síti Ethernet. (Mobilní širokopásmová zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s vysokou šířkou pásma, když Wi-Fi není k dispozici a Wi-Fi sdílení do cloudu není dostatečně výkonné. další informace o podporovaných zařízeních usb najdete v tématu [Připojení Bluetooth a USB-C zařízení](hololens-connect-devices.md).  

### <a name="hand-tracking-improvements"></a>Vylepšení sledování ruky

Tato verze zahrnuje několik vylepšení sledování ruky:

- **Pozice ukazující na stabilitu:** Systém teď zajímá ohyb prstu indexu, když ho dostanou zastíněna od ruky. Tato změna zlepšuje přesnost při vkládání tlačítek, psaní, posouvání obsahu a dalších. 
- **Zkrácení náhodných leteckých kohoutů:** Zlepšili jsme detekci gesta klepnutí vzduchu. V několika běžných scénářích je teď k dispozici méně náhodných aktivací, jako třeba při vyřazení vašich rukou na své strany.
- **Spolehlivost přepínání uživatelů:** Při aktualizaci velikosti ručně při sdílení zařízení je systém teď rychlejší a spolehlivější.
- **Omezené krádeže:** Vylepšili jsme manipulaci s případy, kdy je v zobrazení senzorů k dispozici více než dvě věci. Pokud více lidí pracuje blízko sebe, je teď mnohem nižší pravděpodobnost, že sledovaná ruka "bude" hrát od uživatele až po někoho jiného ve scéně.
- **Spolehlivost systému:** Opravili jsme problém, který způsobil, že při vysokém zatížení zařízení přestane fungovat.

### <a name="dark-mode"></a>Tmavý režim

mnoho aplikací Windows nyní podporuje tmavé i lehké režimy. HoloLens 2 uživatelé můžou zvolit výchozí režim pro aplikace, které podporují obojí. po aktualizaci je výchozím režimem aplikace "tmavý", ale toto nastavení můžete snadno změnit: přejít na **Nastavení**  >  **systémové**  >  **barvy**  >  **vyberte výchozí režim aplikace**.

Tyto "integrované" aplikace podporují tmavý režim:

- Nastavení
- Microsoft Store
- Poštovní
- Kalendář
- Průzkumník souborů
- Centrum Feedback
- OneDrive
- Fotky
- Prohlížeč 3D
- Filmy & televizor

![Okna s tmavým režimem vedle sebe](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systémové hlasové příkazy

Nyní můžete hlasové příkazy použít u libovolné aplikace v zařízení. Další informace najdete v tématu [použití hlasu k provozu HoloLens](hololens-cortana.md). viz také [podporované jazyky pro HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>aktualizace Cortana

aktualizovaná aplikace se integruje s Microsoft 365, která vám umožní více práce v rámci svých zařízení (v současnosti jenom v US-English). v HoloLens 2 Cortana nadále nepodporuje určité příkazy specifické pro zařízení, jako je třeba úprava svazku nebo restartování. Tyto možnosti teď podporují nové systémové hlasové příkazy. další informace o nové aplikaci Cortana najdete na našem [blogu](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  

- Byl představen systém kalibrace aktivního zobrazení. Tato funkce zlepšuje stabilitu a sbližování hologramů. Když přesunete hlavu ze strany na stranu, zůstane na místě.
- opravili jsme chybu, kdy Wi-Fi streamování HoloLens přerušilo pravidelné přerušení. Pokud aplikace indikuje, že potřebuje pro streamování s nízkou latencí, implementujte opravu voláním [funkce SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Opravili jsme zablokování zařízení, ke kterému došlo během streamování v režimu výzkumu.
- Opravili jsme chybu, kdy v některých případech se na přihlašovací obrazovce při obnovení relace nezobrazil správný uživatel.
- opravili jsme problém, kdy uživatelé nemohli exportovat protokoly MDM prostřednictvím **Nastavení**.
- Opravili jsme problém, kdy se přesnost sledování očí hned po dopředné instalaci může snížit, než se očekávalo.
- Opravili jsme problém, kdy se nepovedlo inicializovat podsystém sledování očí nebo za určitých podmínek provést kalibraci.
- Opravili jsme problém, kdy by se zobrazila výzva k kalibraci očí pro již kalibrovaného uživatele.
- Opravili jsme problém, kdy by během kalibrace očí došlo k chybě ovladače.
- Opravili jsme problém, kdy by opakované stisknutí tlačítka napájení mohlo způsobit 60 sekundový časový limit systému a zhroucení prostředí.
- Vylepšená stabilita pro vyrovnávací paměti hloubky.
- Do centra pro názory se přidalo tlačítko **sdílet** , aby uživatelé mohli snadněji sdílet zpětnou vazbu.
- Opravili jsme chybu, kde se správně nainstalovala aplikace RoboRaid wan't.

### <a name="known-issues"></a>Známé problémy

- Problém se systémovým jazykem zh-CN brání hlasovým příkazům v přebírání směsného zachycení realit nebo zobrazení IP adresy zařízení.
- problém vyžaduje spuštění aplikace Cortana po spuštění zařízení, aby se použila hlasová aktivace "Hey Cortana". pokud jste aktualizovali z buildu 18362, může se také zobrazit druhá dlaždice aplikace pro předchozí verzi aplikace Cortana, která už nefunguje v **nabídce Start**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holografická verze 1903 – květen 2020 Update

- Sestavení 18362,1061

tato měsíční aktualizace kvality neobsahuje žádné významné změny, protože tým pracoval na Windows holografické verzi 2004, jak je popsáno výše.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holografická verze 1903 – duben 2020 Update

- Sestavení 18362,1059

**Tmavý režim pro podporované aplikace**

mnoho aplikací Windows podporuje tmavé i světlé režimy. HoloLens 2 zákazníci teď můžou zvolit výchozí režim pro aplikace, které podporují jak barevná schémata. na základě zpětné vazby od zákazníků nastavíme výchozí režim aplikace na "tmavé", ale toto nastavení můžete kdykoli změnit. pokud chcete najít možnost **zvolit si výchozí režim aplikace,** přejděte na **Nastavení > systémových > barvy** .

Tyto "integrované" aplikace podporují tmavý režim:

- Nastavení
- Microsoft Store
- Poštovní
- Kalendář
- Průzkumník souborů
- Centrum Feedback
- OneDrive
- Fotky
- Prohlížeč 3D
- Filmy & televizor

**Vylepšení a opravy také v aktualizaci:**

- Je zajištěno, aby překryvy prostředí byly zahrnuty do hybridních zachycení realit.
- Unreal vývojáři teď můžou pomocí stránky 3D zobrazení na portálu zařízení testovat a ladit své aplikace.
- Zlepšená stabilita při hybridní realitě při použití algoritmu *DepthReprojection HolographicDepthReprojectionMethod* .
- V 32ch aplikacích ARM se opravila chyba Třída rozhraní API WinRT IStreamSocketListener není zaregistrovaná.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holografická verze 1903 – březen 2020 – aktualizace

- Sestavení 18362,1056

Vylepšení a opravy v aktualizaci:

- Zlepšená stabilita při hybridní realitě při použití algoritmu *AutoPlanar HolographicDepthReprojectionMethod* .
- Zajistěte, aby byl souřadnicový systém připojený k hloubkové ukázce MF konzistentní s veřejnou dokumentací.
- Zlepšení produktivity vývojářů tím, že zákazníkům umožníte vkládat velké objemy textu prostřednictvím portálu zařízení.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holografická verze 1903 – únor 2020 aktualizace

- Sestavení 18362,1053

Vylepšení a opravy v aktualizaci:

- Dočasně zakázalo rozhraní API HolographicSpace. UserPresence pro aplikace Unity. Tato změna zabrání problému, který způsobil, že některé aplikace se při převrácení hypervisoru nemusely pozastavit, a to i v případě, že je povolené nastavení spustit v pozadí.
- Opravili náhodnou HUP havárií způsobenou ručním sledováním, ve kterém uživatel všiml, že se zablokuje uživatelské rozhraní a pak se po několika sekundách zpátky do prostředí shell.
- Vylepšené sledování, takže když se poke s prstem na index, je horní část tohoto prstu méně pravděpodobná na neočekávaném otáčení.
- Zlepšená spolehlivost sledování hlav, prostorového mapování a dalších modulů runtime.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holografická verze 1903 – leden 2020 – aktualizace

- Sestavení 18362,1043

Vylepšení a opravy v aktualizaci:

- lepší stabilita pro exkluzivní aplikace při práci s emulátorem HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holografická verze 1903 – prosinec 2019 Update

- Sestavení 18362,1042

Vylepšení a opravy v aktualizaci:

- Představily se opravy LSR (poslední fáze kopírování). Vylepšené vizuální vykreslování hologramů, aby se zobrazovalo více stabilních a bylo zaostřené o přesnější zúčtování jejich hloubky. Pokud aplikace nenastaví hloubku poznatku na hologramech, bude tento příznaku po této aktualizaci více patrné.
- Pevná stabilita exkluzivních aplikací a navigace mezi exkluzivními aplikacemi
- Vyřešili jsme problém, kdy zachycení hybridní reality nedokázalo nahrávat video po několika dnech v pohotovostním stavu zařízení.
- Zlepšená stabilita hologramů.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holografická verze 1903 – aktualizace z listopadu 2019

- Sestavení 18362,1039

Vylepšení a opravy v aktualizaci:

- Při počátečním nastavení pro en-CA a EN-AU se opravily funkce **vybraných** hlasových příkazů.
- vylepšená vizuální kvalita objektů umístěných v nejnovější Unity a verzích MRTK (Mixed Reality Toolkit).
- opravili jsme problémy se zablokovanými holografickými aplikacemi při spuštění v pozastaveném stavu, dokud se nabídka Start neotevřeli a pak zavřeli.
- opravy a vylepšení dodržování OpenXR za běhu pro HoloLens 2 a emulátor.
