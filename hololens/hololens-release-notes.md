---
title: poznámky k verzi HoloLens 2
description: všechny aktualizace v každé nové verzi HoloLens 2 se budou udržovat v aktuálním stavu.
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
ms.openlocfilehash: 3f5e5f3e38c24805935fc69dfacd5eac93ddd017
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034276"
---
# <a name="hololens-2-release-notes"></a>poznámky k verzi HoloLens 2

abychom se ujistili, že máte k dispozici produktivní prostředí s HoloLensmi zařízeními, budeme pořád vydávat aktualizace zabezpečení a funkce, chyby a zabezpečení. na této stránce uvidíte, co je nového pro HoloLens každý měsíc. pokud chcete získat nejnovější aktualizaci HoloLens 2, můžete buď [vyhledat aktualizace, a ručně aktualizovat](hololens-update-hololens.md#check-for-updates-and-manually-update) nebo získat úplnou aktualizaci flash (FFU), která [vám umožní flash zařízení pomocí pokročilého průvodce obnovením](hololens-recovery.md#clean-reflash-the-device). [Stažení](https://aka.ms/hololens2download) je udržováno v aktuálním stavu a poskytuje nejnovější všeobecně dostupné sestavení.

> [!NOTE]
> nedávné oznámení Windows 11 bylo zaměřené na verzi Windows počítače. nedávno jsme spustili [hlavní aktualizaci operačního systému HoloLens 2 v říjnu 2021](#windows-holographic-version-21h2)a pracujeme na dalších nadcházejících verzích na základě zpětné vazby od zákazníků.

## <a name="windows-holographic-version-21h2"></a>Windows Holografická verze 21H2

- Sestavení 20348,1432

Windows holografická verze 21H2 je teď dostupná a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a odborníky na IT. Tato verze se týká vylepšených sestav řešení potíží a zařízení, některých opravených chyb v celoobrazovkovém režimu a v prohlížeči certifikátů, rozšiřitelné plochy spravovatelnosti a zvýšené spolehlivosti aktualizací. nová funkce nejdůležitější této aktualizace funkcí připravujeme HoloLens je náš režim pro přesun platforem. podívejte se na všechny nové skvělé funkce HoloLens 2!

tato nejnovější verze je měsíční aktualizace verze 21H1, ale v tuto chvíli zahrnujeme nové funkce, protože toto hlavní číslo buildu zůstane stejné a web Windows Update bude označovat měsícovou verzi 21H1 (build 20348). HoloLens 2 nastavení budou pořád zobrazovat 21H1, i když odkazujeme na tuto verzi jako na 21H2. Abyste měli jistotu, že jste obdrželi 21H2, ověřte prosím, že je číslo verze 20348,1432 nebo vyšší. můžete se podívat na číslo svého buildu v Nastavení > o obrazovce, abyste se ujistili, že jste na nejnovějším dostupném buildu 20348.1432 +.

pokud chcete aktualizovat na nejnovější verzi, otevřete aplikaci Nastavení, pokračujte na aktualizace & zabezpečení a klepněte na vyhledat aktualizace. další informace o tom, jak spravovat HoloLens aktualizace, najdete v tématu [správa aktualizací HoloLens.](hololens-updates.md)

| Funkce                 | Popis                | Uživatel nebo scénář |
|-------------------------|----------------------------|--------------|
| [Přesun režimu platformy](#moving-platform-mode) | zavádí režim přesunutí verze beta, který je v případě, že je nakonfigurován, umožňuje použití HoloLens 2 na velkých mořských plavidlech s nízkým dynamickým pohybem. | Vše |
| [Podpora souborů PFX pro správce certifikátů](#pfx-file-support-for-certificate-manager) | přidání certifikátů PFX prostřednictvím Nastavení uživatelského rozhraní | Koncový uživatel |
| [zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazit diagnostické protokoly MDM na zařízení | Řešení potíží |
| [Upozornění offline diagnostiky](#offline-diagnostics-notifications) | Audiovizuální zpětná vazba pro shromažďování protokolů | Řešení potíží |
| [Vylepšení shromažďování protokolů s nízkým úložištěm](#low-storage-log-collection-improvements) | Vylepšení scénářů shromažďování protokolů během nedostatku případů úložiště. | Řešení potíží |
| [CSP se mění pro vytváření sestav HoloLens podrobnosti](#csp-changes-for-reporting-hololens-details) | Noví poskytovatelé CSP k dotazování na data | Správci IT    |
| [Zásady automatického přihlašování řízené zprostředkovatelem CSP](#auto-login-policy-controlled-by-csp) | Používá se k automatickému přihlášení k účtu. | Správci IT |
| [Vylepšené zjišťování a oznámení o aktualizacích](#improved-update-restart-detection-and-notifications) | Nové povolené zásady a uživatelské rozhraní pro aktualizace. | Správci IT |
| [Inteligentní opakování pro aktualizace aplikací](#smart-retry-for-app-updates) | Umožňuje správcům IT naplánované opakované pokusy o aktualizaci aplikací. | Správci IT |
| [Používejte pouze aplikace privátního úložiště pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby zobrazovala pouze aplikace z organizace | Správce IT |
| [Použití aplikací WDAC a LOB](#use-wdac-and-lob-apps) | Umožňuje správcům IT používat vlastní aplikace a nadále používat WDAC k blokování dalších aplikací. | Správci IT |
| [Opravy a vylepšení](#fixes-and-improvements) | Opravy a vylepšení HoloLens. | Vše |

### <a name="it-admin-feature-checklist"></a>Kontrolní seznam funkcí správce IT

✔️ Pokud chcete nastavit jeden účet Azure AD tak, aby se automaticky přihlásil, [nakonfigurujte tohoto nového CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Pokud chcete, aby se vaše aplikace po selhání aktualizace automaticky pokoušely aktualizovat, [nastavte tohoto nového CSP pro inteligentní opakování.](#smart-retry-for-app-updates) <br>
✔️ Pokud chcete mít větší kontrolu nad aktualizacemi operačního systému, podívejte se na tyto [nově povolené zásady aktualizace.](#improved-update-restart-detection-and-notifications) <br>
✔️, pokud potřebujete zpřístupnit aplikace vaší organizace na firemním obchodě prostřednictvím Microsoft Store, ale chcete přístup jenom k aplikacím vaší organizace, ne k úplnému úložišti, [nastavte tuto zásadu.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ pokud chcete znát volný prostor úložiště, SSID nebo BSSID vašich HoloLensch zařízení se podívejte na tyto [zprostředkovatele csp pro vytváření sestav.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Pokud chcete používat WDAC k blokování spouštění aplikací nebo procesů, ale také potřebujete použít vlastní řádek aplikací bushiness, můžete teď [ve svých zásadách pro WDAC dovolit LOB](#use-wdac-and-lob-apps).

### <a name="moving-platform-mode"></a>Přesun režimu platformy

od [Windows holografické verze 21H2](hololens-release-notes.md#windows-holographic-version-21h2) přidali jsme podporu beta pro sledování na vysoce dynamických pohybových platformách v HoloLens 2. po instalaci sestavení a povolení režimu přesunu platforem budete moci použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské lodi. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

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

Pro spravovaná zařízení při řešení potíží ověřte, že se používá očekávaná konfigurace zásad, což je důležitý krok. dříve se tato nová funkce musela po exportu protokolů pro diagnostiku mdm shromážděných prostřednictvím **Nastavení**  ->  **účtů**  >  **přistupovat do práce nebo do školy** a vybrat možnost **exportovat protokoly správy** a zobrazit je na nejbližším počítači v blízkosti zařízení.

Diagnostiku MDM je teď možné zobrazit na zařízení pomocí prohlížeče Edge. Chcete-li snadněji zobrazit diagnostickou zprávu MDM, přejděte na stránku přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu**. Tato akce vygeneruje a otevře sestavu v novém okně Edge.

![zobrazit pokročilou diagnostickou sestavu v aplikaci Nastavení.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Přehled a vyzkoušejte si pokročilou diagnostickou sestavu

1. Otevřete aplikaci Nastavení.
1. Přejděte na stránku účty a kliknutím na nový odkaz **exportujte protokoly správy**.
1. Zobrazit rozšířené informace o konfiguracích zařízení.

### <a name="offline-diagnostics-notifications"></a>Upozornění offline diagnostiky

Tato aktualizace pro existující funkci se nazývá [offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve neexistoval žádný jasný indikátor pro uživatele, kteří aktivovali diagnostické shromažďování nebo dokončili.
Nyní jsme do [Windows Holographic verze 21H2](hololens-release-notes.md#windows-holographic-version-21h2)přidali dvě formy zpětné vazby k offline diagnostice. Prvními jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a má vizuály.

![Informační zprávy pro shromažďování protokolů](./images/logcollection1.jpg)

![Informační zpráva po dokončení shromažďování protokolů](./images/logcollection2.jpg)

Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus shromažďování protokolů, když nemají přístup k zobrazení, nemůže se přihlásit nebo jsou stále v OOBE, bude se při shromažďování protokolů přehrávat také zvukové signály. Tento zvuk se přehraje spolu s informační zprávou.

Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná. Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.

Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.

Tyto informace si můžete prohlédnout později na stránce [s diagnostickými protokoly.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Přehled pro vyzkoušejte si diagnostická oznámení

1. Odemkněte zařízení a ošetřte ho.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Prohlédněte si informační zprávy a poslechu zvukových upozornění, kdy se zařízení spustí a dokončí shromažďování protokolů.

### <a name="low-storage-log-collection-improvements"></a>Vylepšení shromažďování protokolů s nízkým úložištěm

Ve scénářích, kdy se zdá, že zařízení má při shromážděných diagnostických protokolech nedostatek místa na disku, vytvoří se **StorageDiagnostics.zip** sestava s názvem . Prahovou hodnotu nízkého úložiště určuje automaticky Windows [úložiště.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

Tyto informace si můžete prohlédnout později na stránce [s diagnostickými protokoly.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Přehled pro vyzkoušejte vylepšení nízkého úložiště

1. Vyplňte prostor úložiště zařízení.
1. Stisknutím kombinace **tlačítka Napájení** **a snížení** objemu shromážděte [diagnostiku offline.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Všimněte si, že v kolekci protokolů je nový soubor uložený ve složce Documents (Dokumenty) HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Změny CSP pro podrobnosti HoloLens sestav

Následující csp se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.

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

Na zařízení, kde je tato zásada nakonfigurovaná, se uživatel zadaný v zásadách musí alespoň jednou přihlásit. Po dalším restartování zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí. Podporuje se jenom jeden uživatel s automatickým přihlášením. Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.

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

Nově povolená pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jedno časové datum restartování aplikací, jejichž aktualizace selhala kvůli tomu, že se aplikace používá a umožňuje instalaci aktualizace. Můžete je nastavit na základě několika různých triggerů, jako je naplánovaný čas nebo přihlášení. Další informace o použití této zásady najdete v tématu [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

Tyto informace najdete později v obchodě [s aplikacemi pro firmy](app-deploy-store-business.md)na stránce .

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Přehled pro pokus o inteligentní opakování aktualizací aplikací

1. Nakonfigurujte novou funkci inteligentního opakování.
1. Na zařízení, které ještě vaši aplikaci nepřijímá a je správně nakonfigurované, se přihlaste do online prostředí.
1. Zajistěte, aby zařízení nemohlo stáhnout aplikaci vypnutím nebo odpojením.
1. Během aktivované doby musí být zařízení zapnuté a připojené k internetu, aby se pokus o stažení zopakovat.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používejte jenom aplikace pro privátní Microsoft Store

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store, aby se privátní úložiště nakonfigurované pro vaši organizaci nakonfiguroval jenom [přes Microsoft Store pro firmy](/microsoft-store/microsoft-store-for-business-overview). Omezení přístupu pouze na aplikace, které jste k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Tyto informace najdete později v obchodě [s aplikacemi pro firmy](app-deploy-store-business.md)na stránce .

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

#### <a name="for-developers"></a>Pro vývojáře

- Byl opraven známý problém pro Portál zařízení, kdy se při stahování uzamčených souborů [nic nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Byl opraven [známý problém s Portál zařízení s časovými limity nahrávání](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)a stahování souborů.
- Zpracování Gamepadu pro 2D aplikace bylo ve buildech Insider zakázané. Když je odeberete, aplikace teď mohou rozhraní GAMEPAD API používat přímo a mají přístup k celé sadě ovládacích prvků a je možné je vyvíjet s vědomím, že toho budou dělat víc. Vývojáři by měli ke vstupu Gamepadu používat rozhraní API Gamepadu. Tady je ukázka třídy [Gamepad (Windows. Gaming.Input) – Windows aplikace pro UPW.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Povolili [jste rozhraní API pro](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) přiřazený přístup, aby aplikace teď mohli určit, jestli je HoloLens spuštěný v bezna meziobrazovkovém režimu pro uživatele přihlášeného k HoloLens.

#### <a name="for-enterprise"></a>Pro Enterprise

- Řeší problémy související s hlášením vlastností dodržování předpisů HoloLens zařízeními. K aktivaci správných sestav v sestaveních Insider může být nutné restartovat počítač.  
- Aktualizace dodácí verze Remote Assistu, která je nainstalovaná na aktuálních flash serverech.
- Opravili jsme problém, kdy se po prvním přihlášení uživatele ooBE ukončuje ve scénářích, AAD se používaly konfigurace veřejného terminálů založené na skupině.
- Opravil se problém se zobrazováním oznámení o aktualizacích a dialogových vý okno s výzvou k restartování zařízení.
- Opravili jsme problém, kdy po restartování zařízení byly znovu spárovány řadiče pro Xbox a Bluetooth periferní zařízení LE.
- Opravili jsme problém s kodérem videa, který mohl způsobit krátké zablokování odchozího videa během volání vzdálené pomoci. Wi-Fi ovladače a firmwaru tak, aby řešte chyby zabezpečení fragmentu Wi-Fi forge.
- Wi-Fi ovladače a firmwaru tak, aby řešte chyby zabezpečení fragmentu Wi-Fi forge.
- Při použití režimu přesunu platformy (MPM) se hodnota "down" odhadne průměrnou závažností po krátkou dobu. Tato hodnota nahrazuje skutečnou závažnost v režimu moving platformy.
- Opravili jsme pravidelné vměšování v hologramech v režimu 3DoF nebo při ztrátě sledování.
- Řeší problém, který ovlivnil aktualizace verze 21H1/21H2 ze starších verzí.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z října 2021

- Build 19041.1168

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si náš nejnovější build Windows Holographic verze 21H2.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace ze září 2021

- Build 20348.1018

Vylepšení a opravy v aktualizaci:

- Opravuje problém, kdy může neočekávaně přeskakovat systémový čas.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace ze září 2021

- Build 19041.1165

Vylepšení a opravy v aktualizaci:

- Opravuje problém, kdy může neočekávaně přeskakovat systémový čas.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace ze srpna 2021

- Build 20348.1014

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který zabraňoval tomu, aby kontrolery Xboxu pracovaly v imerzivních aplikacích s podporou kontrolerů.
- Vylepšená diagnostika pro selhání aktualizací zařízení

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace ze srpna 2021

- Build 19041.1161

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace z července 2021

- Build 20348.1010

Vylepšení a opravy v aktualizaci:

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům při otevírání uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.
- Opravili jsme problémWi-Fi kdy se při spuštění uživatelského rozhraní vlastností Wi-Fi ze služby **Nastavení > Network & Internet >** stav > Vlastnosti .
- Byl vyřešen problém s odebráním certifikátů eSIM mezi aktualizacemi operačního systému. Tato oprava zajišťuje odebrání certifikátů eSIM a souvisejících komponent při aktualizaci na verzi 21H1.
- Byl opraven problém, který ovlivnil předinstalované aplikace napříč resetováním operačního systému.
- Vyladěný výkon při dobíjení baterie za běhu při vyšším zatížení procesoru. Při HoloLens 2 zařízení, pokud se detekuje, že zařízení běží horké, bude se interní baterie nabítat pomaleji, aby se snížilo teplo. Kladným kompromisem je, že zařízení je méně pravděpodobné, že se vypne kvůli teplotním problémům, s dopadem na to, že zařízení běží déle. Pokud je zařízení studené, sazba za poplatek není ovlivněná.

> [!IMPORTANT]
> Vzhledem k vyřešení známého problému v našem buildu [21H1,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)který ovlivnil uživatele vzdálené pomoci, jsme dočasně pozastavil nabídku aktualizací Windows Holographic verze 21H1. Také jsme změnili výchozí build Advanced Recovery Companion (ARC) na [verzi Windows Holographic verze 20H2–červen 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Sestavení ARC teď bude pokračovat v cílení na sestavení 21H1.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z července 2021

- Build 19041.1157

Vylepšení a opravy v aktualizaci:

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům při otevírání uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace z června 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive nahrání fotoaparátu do práce nebo do školy

Do aplikace HoloLens 2 Nastavení jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa hybridní reality ze složky Obrázky > Fotoaparát do odpovídající složky OneDrive for work nebo school. Tato funkce řeší nedostatky funkcí v aplikaci [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) ve HoloLens 2, která podporuje jenom automatické nahrávání fotoaparátů do osobního účet Microsoft zákazníka (a ne do jeho pracovního nebo školního účtu).

**Jak to funguje**

- Pokud **Nastavení > nahrání fotoaparátu > Mixed Reality system > Mixed Reality,** přejděte na .
- Když tuto funkci  nastavíte na Na pozici, všechny fotky nebo videa hybridní reality zachycené do vašeho zařízení se automaticky zařadit do fronty pro nahrání do složky Pictures > Camera Roll vašeho účtu OneDrive for work nebo school.
    >[!NOTE]
    >Fotky a videa zachycené před  povolením této funkce nebudou zařazené do fronty pro nahrání a budou se muset nahrát ručně.
- Stavová zpráva na Nastavení zobrazí počet souborů čekajících na nahrání (nebo si přečtěte "OneDrive je aktuální", když se nahrají všechny nevyřízené soubory).
- Pokud máte obavy o šířku pásma nebo chcete nahrávání pozastavit z nějakého důvodu, můžete tuto funkci přepnout do **pozice Vypnuto.** Dočasné zakázání této funkce zajistí, že se fronta pro nahrávání bude dál zvyšovat při přidávání nových souborů do složky Fotoaparát, ale soubory se nenahrají, dokud tuto funkci znovu nepo povolením nenahrajete.
- Nejnovější soubory se nahrají jako první (poslední, první ven).
- Pokud u OneDrive účtu dochází k problémům (například po  změně hesla), zobrazí se na stránce Nastavení tlačítko Opravit.
- Neexistuje žádná maximální velikost souboru, ale upozorňujeme, že nahrávání velkých souborů bude trvat déle (zejména v případě, že je omezena šířka pásma pro nahrávání). Pokud během nahrávání velkého souboru pozastavíte nebo vypnete nahrávání, částečné nahrání se zachová. Pokud se nahrávání znovu povolí během několika hodin od "pozastavení" nebo vypnutí, nahrávání bude pokračovat tam, kde se vypnulo. Pokud se ale nahrávání po několika hodinách znovu povolí, nahrávání velkého souboru se od začátku restartuje.

**Známé problémy a upozornění**

- Toto nastavení nemá žádné integrované omezování na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Upload se pozastaví, ale funkce bude dál monitorovat nově přidané soubory do fotoaparátu. Jakmile budete připraveni pokračovat, nahrávání znovu povolte.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat jenom soubory pro uživatele, který je momentálně přihlášený k zařízení.
- Pokud během sledování počtu nahrávání na stránce Nastavení v reálném čase posouváte fotky nebo videa, nezapomeňte, že počet čekajících souborů se může změnit, dokud se nahrávání aktuálního souboru nedokončí.
- Upload se pozastaví, když zařízení usne v režimu spánku nebo je vypnuté. Pokud chcete zajistit dokončení probíhajícího nahrávání, aktivně zařízení používejte, dokud stránka Nastavení nečte "OneDrive je aktuální" nebo dokud neupravíte nastavení režimu spánku & Power **&** režimu spánku.

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

Následující zásady telemetrie se teď podporují na HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně k úplnému řízení telemetrie a chování v aplikaci Nastavení.

Vylepšení a opravy v aktualizaci:

- Opravuje hlavní poškození videa s kalibrací barev.
- Řeší problém, ve kterém může být text v nabídce napájení zkrácen.
- Povolí podporu pro zásady RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holografická verze 20H2 – června 2021 Update

- Sestavení 19041,1154

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

v HoloLens 2 se teď podporují tyto zásady telemetrie:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně k úplnému řízení telemetrie a chování v aplikaci Nastavení.

doporučujeme, abyste si vyzkoušeli naše nejnovější sestavení Windows holografické 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holografická verze 1903 – aktualizace od června 2021

- Sestavení 18362,1116

Vylepšení a opravy v aktualizaci:

- tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet naše nejnovější buildy Windows holografické 21H1 verze.

>[!IMPORTANT]
> Toto sestavení již nebude obsluhovat.

## <a name="windows-holographic-version-21h1"></a>Windows Holografická verze 21H1

- Sestavení 20346,1002

Tato aktualizace obsahuje funkce pro dva cílové skupiny. funkce, které může použít kdokoli na zařízení koncovým uživatelem, a nové možnosti správy zařízení, které můžou nakonfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro jednotlivé cílové skupiny. Pokud jste správce IT, podívejte se prosím na našeho [správce IT – aktualizace kontrolního seznamu](#it-admin---update-checklist).
>[!IMPORTANT]
>aby bylo možné aktualizovat tento build, HoloLens 2 zařízení musí v současnosti běžet aktualizace z února 2021 (build 19041,1136) nebo novější. Pokud se vám tato aktualizace funkce nezobrazuje, nejdřív prosím aktualizujte svoje zařízení a zkuste to znovu.

>[!NOTE]
>v současné době Microsoft HoloLens 2 podporuje měsíční aktualizace pro obsluhu (chyby a opravy zabezpečení) pro následující verze:
>
>- Windows Holografická verze 20H2 (Build 19041.1128 +)
>- Windows Holografická verze 2004 (Build 19041.1103 +)
>- Windows Holografická verze 1903 (Build 18362 +)
>
> díky zavedení Windows holografické verze 21H1 **netrváme měsíční aktualizace pro Windows holografické verze 1903**. Díky tomu se můžeme soustředit na další nejnovější verze a dál dodávat cenná vylepšení.

| Název funkce                                              | Krátký popis                                                                      | Cílová skupina |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nový Microsoft Edge](#introducing-the-new-microsoft-edge)  | pro HoloLens 2 je teď k dispozici nový Microsoft Edge založený na Chromium. | Koncový uživatel |
[WebXR a 360 Viewer](#webxr-and-360-viewer) | Vyzkoušejte moderní webové prostředí a 360 přehrávání videa. | Koncový uživatel |
[nová aplikace Nastavení](#new-settings-app) | starší verze aplikace Nastavení se nahrazuje aktualizovanou verzí s novými funkcemi a nastaveními. | Koncový uživatel |
[Zobrazit kalibraci barev](#display-color-calibration) | vyberte alternativní barevný profil pro zobrazení HoloLens 2. | Koncový uživatel |
[Výchozí výběr aplikace](#default-app-picker) | Vyberte aplikaci, která se má spustit pro každý soubor nebo typ odkazu. | Koncový uživatel |
[Řízení hlasitosti na aplikaci](#per-app-volume-control) | Ovládat svazek na úrovni aplikace nezávisle na systémovém svazku. | Koncový uživatel |
[Instalace webových aplikací](#install-web-apps) | pomocí nového prohlížeče Microsoft Edge nainstalujte webové aplikace v HoloLens 2, jako je Microsoft Office. | Koncový uživatel |
[Potáhnutím na typ](#swipe-to-type) | Použijte hrot prstu na potáhnutí slova na holografické klávesnici. | Koncový uživatel |
[Nabídka napájení z nabídky Start](#power-menu-from-start) | v nabídce Start restartujte a vypněte zařízení HoloLens. | Koncový uživatel |
[Více uživatelů uvedených na přihlašovací obrazovce](#multiple-users-listed-on-sign-in-screen) | Zobrazit více uživatelských účtů na přihlašovací obrazovce | Koncový uživatel |
[Podpora externích mikrofonů USB-C](#usb-c-external-microphone-support) | Použijte mikrofony USB-C pro aplikace a/nebo vzdálenou pomoc. | Koncový uživatel |
[Automatické přihlášení návštěvníka pro veřejné terminály](#visitor-auto-logon-for-kiosks) | Umožňuje, aby se automatické přihlašování na účtech návštěvníka používalo pro beznabídkový režim. | Správce IT |
[Nový AUMIDs pro nové aplikace v celoobrazovkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs se na nové aplikace Nastavení a Edge. | Správce IT |
[Vylepšené zpracování chyb v celoobrazovkovém režimu](#kiosk-mode-behavior-changes-for-handling-of-failures) | Celoobrazovkový režim vyhledá globální přiřazený přístup před prázdnou nabídkou Start. | Správce IT |
[nový SettingsURIs pro viditelnost stránky Nastavení](#new-settings-uris-for-page-settings-visibility) | 20 + nové SettingsURIs pro zásady Nastavení/PageVisibilityList. | Správce IT |
[Konfigurace záložní diagnostiky](#configuring-fallback-diagnostics-via-settings-app) | nastavení nouzového diagnostického chování v aplikaci Nastavení App | Správce IT |
[Sdílení věcí pomocí okolních zařízení](#share-things-with-nearby-devices) | sdílejte soubory nebo adresy url z HoloLens k počítači. | Vše |
[Nová trasování diagnostiky operačního systému](#new-os-diagnostic-traces) | nový poradce při potížích v Nastavení pro aktualizace operačního systému. | Správce IT |
[Optimalizace doručování – náhled](#delivery-optimization-preview) | snižte spotřebu šířky pásma pro stahování z více HoloLensch zařízení. | Správce IT |

Podívejte se na související poznámky k verzi:

- [navštívit HoloLens Emulator archivu](/windows/mixed-reality/hololens-emulator-archive)
- [Vzdálená pomoc pro Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Průvodci Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Představení nového Microsoft Edge

![Animace staršího Microsoft Edge loga na nové Microsoft Edge loga](images/new-edge.gif)

Nový Microsoft Edge využívá [projekt Chromium open source,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) aby pro zákazníky vytvořil lepší kompatibilitu a méně fragmentaci webu pro webové vývojáře.

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která [se](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) už v nových verzích nepodporuje.

![Nový Microsoft Edge obrazovky](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Spuštění nové Microsoft Edge

Nový Microsoft Edge ![Nová Microsoft Edge ikony](images/new_edge_logo.png) (znázorněná modrou a zelenou ikonou swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Při prvním spuštění nového Microsoft Edge na HoloLens 2 se vaše nastavení a data naimportuje ze starší verze Microsoft Edge. Pokud po spuštění nového Microsoft Edge nadále používáte starší verzi Microsoft Edge, nebudou se tato nová data synchronizovat ze starší verze Microsoft Edge do nového Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

Nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče pro HoloLens 2, než byly dříve dostupné ve starších verzích Microsoft Edge.

Tady je několik užitečných zdrojů informací o správě nastavení zásad pro nové Microsoft Edge:

- [Konfigurace Microsoft Edge zásad pomocí Microsoft Intune](/deployedge/configure-edge-with-intune)
- [starší verze Microsoft Edge mapování Microsoft Edge zásad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapování zásad Microsoft Edge Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Úplná [Microsoft Edge Enterprise dokumentace](/deployedge/)

> [!IMPORTANT]
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada bude fungovat HoloLens 2. Otestovali a potvrdili jsme ale, že nové zásady Microsoft Edge ekvivalentem každé starší verze zásad Microsoft Edge dříve podporované u HoloLens 2 fungují podle očekávání. V [starší verze Microsoft Edge se Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) mapování zásad a vyhledejte nový ekvivalent Microsoft Edge všech starších zásad Microsoft Edge prohlížeče, které jste s HoloLens 2 HoloLens.
>
> Minimálně dvě nové zásady Microsoft Edge, o které víme, *že nebudou* fungovat s HoloLens 2:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nového Microsoft Edge dne HoloLens 2

Vzhledem k tomu, že nová Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UPW, která umožňuje spuštění na zařízeních jenom pro UPW, jako je HoloLens 2, nemusí být některé funkce okamžitě dostupné. V nadcházejících měsících budeme podporovat nové scénáře a funkce, proto v tomto prostoru najdete aktuální informace.

**Očekávané scénáře a funkce:**

- Prostředí při prvním spuštění, přihlášení k profilu a synchronizace
- Weby by se měly vykreslit a chovat podle očekávání
- Většina funkcí prohlížeče (oblíbené položky, historie atd.) by měla fungovat podle očekávání
- Tmavý režim
- Instalace webových aplikací do zařízení
- Instalace rozšíření (dejte nám vědět, pokud používáte rozšíření, která nefungují správně v HoloLens 2)
- Zobrazení a označení souboru PDF
- Prostorový zvuk z jednoho okna prohlížeče
- Automatická a ruční aktualizace prohlížeče
- Uložení souboru PDF z nabídky Tisk (pomocí možnosti Uložit do souboru PDF)
- WebXR a rozšíření 360 Viewer
- Obnovení obsahu do správného okna při procházení několika oken umístěných ve vašem prostředí

**Scénáře a funkce, u které se neočekává, že budou fungovat:**

- Prostorový zvuk z několika oken se souběžně streamy zvuku
- "See it, say it"
- Tisk

**Hlavní známé problémy prohlížeče:**

- Náhled lupy na holografické klávesnici byl pro novou obrazovku Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu Sledovat](hololens2-basic-usage.md#follow-me-stop-following)mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna **tlačítkem X.**
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit neočekávané neaktivování ostatních 2D oken aplikací. Tato okna můžete znovu aktivovat opětovnou interakcí.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu Preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat víc verzí najednou.

Další informace [o komunitě Edge Insider najdete na domovské](https://www.microsoftedgeinsider.com) stránce Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce pro [stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider do Microsoft Edge 2 je k dispozici několik HoloLens:

**Přímá instalace na zařízení (aktuálně dostupná pouze pro nespravovaná zařízení)**

  1. Na stránce HoloLens 2 přejděte na stránku [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **Stáhnout pro HoloLens 2** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor .msix z fronty pro stahování Edge nebo ze složky Stažené soubory ze zařízení (pomocí Průzkumník souborů).
  1. [Spustí se instalační](app-deploy-app-installer.md) program aplikace.
  1. Vyberte **tlačítko** Nainstalovat.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

**Instalace přes počítač s Windows Portál zařízení [(vyžaduje](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) povolení vývojářského režimu na počítači HoloLens 2)**

  1. Na počítači přejděte na stránku pro stažení [Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte **tlačítko se šipkou rozevíracího** seznamu vedle tlačítka Stáhnout pro Windows 10 pro kanál Edge Insider, který chcete nainstalovat.
  1. V **HoloLens vyberte 2.**
  1. Uložte soubor .msix do složky Stažené soubory na počítači (nebo do jiné složky, kterou snadno najdete).
  1. Pomocí [Windows Portál zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na počítači nainstalujte stažený soubor .msix na HoloLens 2.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Použití nástroje WDAC k blokování nových Microsoft Edge

Aby správci IT mohli aktualizovat zásady [WDAC](windows-defender-application-control-wdac.md) tak, aby blokují novou aplikaci Microsoft Edge, musíte do zásad přidat následující položky.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí mohou mít omezení sítě, která je třeba vzít v úvahu. Pokud chcete zajistit bezproblémové prostředí s novým Edgem, [povolte tyto koncové body Microsoftu.](/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalace webových aplikací

 > [!Note]
>Od [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)už nebude Office webová aplikace předem nainstalovaná.

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci Microsoft Office zobrazit a upravit soubory hostované na SharePoint nebo OneDrive. Pokud chcete nainstalovat Office aplikaci, navštivte a vyberte tlačítko App Available (Aplikace k dispozici) https://www.office.com nebo Install Office **(Nainstalovat** aplikaci) na panelu Adresa.  Potvrďte **výběrem** možnosti Nainstalovat.

> [!IMPORTANT]
> Office webové aplikace je dostupná jenom v případě, že HoloLens 2 má aktivní připojení k internetu.

### <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer

Nový Microsoft Edge zahrnuje podporu WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Mnoho imerzivních webových prostředí bylo navrženo s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale tato prostředí jsou podporována také HoloLens 2. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že nová imerzivní prostředí rozšířené reality a hybridní reality HoloLens 2 zákazníci to budou zkoušet!

Rozšíření 360 Viewer je postaveno na WebXR a automaticky se nainstaluje společně s novým Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

#### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu **vyberte tlačítko Enter VR** (Zadat virtuální realitu). Umístění a vizuální znázornění tohoto tlačítka se může u jednotlivých webových stránek lišit, ale může vypadat podobně jako:

    ![Zadejte příklad tlačítka VR.](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění WebXR prostředí v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení, vyberte možnost **Povolení**.
1. pro práci s prostředím používejte [gesta HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) .
1. Pokud prostředí nemá tlačítko **ukončit** , vraťte se domů pomocí [gesta Start](hololens2-basic-usage.md#start-gesture) .

**Doporučené ukázky WebXR**

- 360 Viewer (viz další oddíl)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Malování](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na YouTube na video o 360.
1. V snímku videa vyberte tlačítko náhlavní soupravu Mixed reality:

    ![Tlačítko pro aktivaci nástroje 360 Viewer.](images/enter-360-viewer.jpg)

1. Při prvním pokusu o spuštění nástroje 360 Viewer v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení. Vyberte možnost **udělit**.
1. [Klepnutím na Air](hololens2-basic-usage.md#select-using-air-tap) otevřete ovládací prvky přehrávání. K přehrání a pozastavení použijte [ruky a klepněte na tlačítko Air](hololens2-basic-usage.md#select-using-air-tap) , přeskočte zpátky na pozadí, zapnout nebo vypnout titulky nebo zastavte prostředí (které ukončí moderní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Známé problémy pro WebXR a 360 Viewer

- V závislosti na složitosti WebXR prostředí může snímkový kmitočet vyřadit nebo Stutter.
- Podpora kloubových spojek v WebXR není ve výchozím nastavení povolená. Vývojáři můžou povolit podporu prostřednictvím `edge://flags` zapínání "WebXR ruky".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby v WebXR a v prohlížeči 360

Sdílejte prosím svůj názor a chyby pomocí našeho týmu prostřednictvím funkce pro **odeslání zpětné vazby** v novém Microsoft Edge.

### <a name="new-settings-app"></a>nová aplikace Nastavení

v této verzi zavádíme novou verzi aplikace Nastavení. nová aplikace Nastavení zahrnuje nové funkce a rozšířené nastavení pro HoloLens 2 v následujících oblastech: zvuk, Power & spánek, síť & Internet, aplikace, účty, usnadnění přístupu a další.

> [!NOTE]
> vzhledem k tomu, že je nová aplikace Nastavení odlišná od starší Nastavení aplikace, všechna Nastaveníná okna, která jste předtím umístili do svého prostředí, budou po aktualizaci odebrána.

![nová domovská stránka aplikace Nastavení.](images/new-settings-app.png)

**Nové funkce a nastavení**

- Nastavení search: vyhledejte nastavení z domovské stránky Nastavení pomocí klíčových slov nebo názvu nastavení.
- Zvuk > systému:
  - vstupní a výstupní zvuková zařízení: nezávisle vyberte vstupní a výstupní zvuková zařízení (například poslech zvuku prostřednictvím Bluetooth sluchátek nebo použití mikrofonu USB-C pro zvukový vstup).
    > [!NOTE]
    > HoloLens 2 nepodporuje Bluetooth mikrotelefonů.
  - Svazek aplikace: nezávisle upravte hlasitost každé aplikace. Zobrazit [Řízení hlasitosti jednotlivých aplikací](#per-app-volume-control).
- Systém > napájení & režimu spánku: vyberte, kdy se má zařízení po určité době nečinnosti přejít do režimu spánku.
- Systémová > baterie: ručně povolit režim spořiče baterie nebo nastavit prahovou hodnotu baterie, při které se režim spořiče baterie automaticky zapne.
- Zařízení > USB: ve výchozím nastavení můžete připojení USB zakázat.
- & sítě Internet:
  - Adaptéry USB-C Ethernet se nyní zobrazí v síti & Internetu.
  - K dispozici jsou nyní nastavení adaptéru USB-C Ethernet, včetně jeho IP adresy.
  - nyní můžete zapnout režim v letadle HoloLens 2.
- Aplikace: můžete obnovit výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu věnovaném [výchozím ovládacím prvkům aplikace](#default-app-picker).
- Účty > jiných uživatelích: vlastníci zařízení můžou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, předowngradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.

**Známé problémy**

- předchozí umístění, Nastavení windows, bude odebráno (viz poznámku výše).
- v aplikaci Nastavení už nemůžete přejmenovat zařízení. správci IT můžou zařízení přejmenovat pomocí [Windowsho autopilotu pro HoloLens 2 2](hololens2-autopilot.md) nebo v uzlu cloud MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se vždy zobrazuje virtuální síť Ethernet (UsbNcm).
- využití baterie pro nový Microsoft Edge nemusí být přesné, vzhledem k jeho povaze jako desktopová aplikace Win32 podporovaná vrstvou adaptéru UWP (zatím se nepředpokládá žádná oprava).

#### <a name="display-color-calibration"></a>Zobrazit kalibraci barev

pomocí tohoto nového nastavení můžete vybrat alternativní barevný profil pro zobrazení HoloLens 2. To může mít za přesnější vzhled barev, zejména při nižších úrovních jasu displeje. kalibraci barev displeje lze nalézt v aplikaci Nastavení na stránce pro kalibraci systému >.

> [!NOTE]
> Vzhledem k tomu, že toto nastavení uloží nový profil barev do firmwaru zobrazení, jedná se o nastavení podle zařízení (a není jedinečné pro každý uživatelský účet).

##### <a name="how-to-use-display-color-calibration"></a>Jak používat kalibraci barev displeje

1. spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **kalibrace barev displeje spustit** .
1. Spustí se prostředí kalibrace barev displeje a doporuče vám, abyste se ujistili, že je váš hypervisor ve správné pozici.
1. Až budete pokračovat v dialogových oknech instrukce, zobrazí se automaticky ztlumení jasu na 30%.
    > [!TIP]
    > pokud máte potíže se zobrazením neaktivní scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek jasu na levé straně zařízení.
1. Vyberte tlačítka 1-6, abyste si mohli okamžitě vyzkoušet jednotlivé profily barev, a najít jeden, který vypadá nejlépe pro vaši oči. (to obvykle znamená, že profil, který pomáhá scénu, se jeví jako neneutrální, se vzorkem stupňů šedi a tónům skinu, které vypadají podle očekávání.)

    ![Zobrazit scénu kalibrace barev](images/color-cal-ui.png)

1. Až budete s vybraným profilem spokojeni, vyberte tlačítko **uložit & tlačítko Storno** .
1. Pokud nechcete provádět změny, vyberte tlačítko **zrušit & ukončení** a změny se vrátí.

> [!TIP]
> Tady jsou některé užitečné tipy, které vám pomůžou při používání nastavení kalibrace barev displeje:
>
> - můžete znovu spustit kalibraci barev displeje z Nastavení vždy, když chcete
> - pokud někdo na zařízení dřív používal nastavení pro změnu profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte kalibraci barev displeje, bude zvýrazněný profil barev zvýrazněný a profil 0 se nezobrazí (jako profil 0 představuje původní barevný profil displeje).
> - pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to provést na stránce Nastavení (viz [postup resetování barevného profilu](#how-to-reset-color-profile)).

##### <a name="how-to-reset-color-profile"></a>Jak obnovit barevný profil

pokud si nejste spokojeni s vlastním profilem barev uloženým ve vašem HoloLens 2, můžete obnovit původní barevný profil zařízení:

1. spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **Obnovit výchozí barevný profil** .
1. po otevření dialogového okna vyberte **restartovat** , pokud jste připraveni restartovat HoloLens 2 a použít změny.

#### <a name="top-display-color-calibration-known-issues"></a>Známé problémy při kalibraci horních displejů

- na stránce Nastavení stavový řetězec, který oznamuje, že se naposledy změnil barevný profil, bude zastaralá, dokud tuto stránku Nastavení znovu nenačtete.
    - alternativní řešení: vyberte jinou Nastavení stránku a pak znovu vyberte stránku kalibrace.

#### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když aktivujete hypertextový odkaz nebo otevřete typ souboru s více než jednou nainstalovanou aplikací, který ho podporuje, zobrazí se nové okno s výzvou, abyste vybrali, která aplikace by měla zpracovat soubor nebo typ odkazu. V tomto okně můžete také zvolit, aby vybraná aplikace zpracovala soubor nebo typ odkazu "jednou" nebo "Always".

pokud zvolíte "vždycky", ale později chcete změnit, která aplikace zpracovává určitý typ souboru nebo propojení, můžete obnovit uložené výchozí hodnoty v **Nastavení > aplikacích**. Posuňte se do dolní části stránky a v části výchozí aplikace pro typy souborů nebo výchozí aplikace pro typy odkazů vyberte tlačítko **Vymazat** . Na rozdíl od podobných nastavení na stolních počítačích nemůžete resetovat jednotlivé výchozí hodnoty typu souboru.

#### <a name="per-app-volume-control"></a>Řízení hlasitosti na aplikaci

nyní mohou uživatelé v tomto Windows sestavení ručně upravovat úroveň hlasitosti každé aplikace. To uživatelům umožňuje lépe se zaměřit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například nutnost vypnout objem jedné aplikace a zavolat jiné osobě na vzdálenou pomoc v jiném.

pokud chcete nastavit hlasitost jednotlivé aplikace, přejděte na **Nastavení**  >  **systémový**  >  **zvuk** a v části pokročilé možnosti zvuku vyberte **předvolby aplikace a hlasitost zařízení**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potáhnutím na typ

Někteří zákazníci na virtuálních klávesnicích rychleji najdou na "typ", a to potáhnutím tvaru slova, které mají v úmyslu zadat, a my si tuto funkci zobrazíme pro holografickou klávesnici. Jedno slovo můžete potáhnutím prstem procházet rovinou holografické klávesnice, potažením tvaru slova a následným odvoláním hrotu prstu z roviny klávesnice. Potáhnutím prstů můžete přetáhnout text, aniž byste museli stisknout MEZERNÍK, a to tak, že z klávesnice odeberete prst mezi slovy. Víte, že funkce funguje v případě, že se pod pohybem prstu na klávesnici zobrazuje potáhnutí.

Upozorňujeme, že tato funkce může být obtížné použít a hlavní, a to z důvodu povahy holografické klávesnice, kde nepůsobíte proti prstům odolnost (na rozdíl od zobrazení mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní obrazovce HoloLens, který ukazuje, kdy je dostupná aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní HoloLens pomocí gesta [Start](hololens2-basic-usage.md#start-gesture) nebo rčení "Přejít na začátek".

2. Všimněte si ikony se třemi tečkami (...) vedle profilu uživatele:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Vyberte profilový obrázek uživatele pomocí rukou nebo hlasovým příkazem Power.

4. Zobrazí se nabídka s možnostmi Odhlásit se, Restartovat nebo Vypnout zařízení:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Vyberte možnosti nabídky pro odhlášení, restartování nebo vypnutí HoloLens. Možnost Odhlásit se nemusí být dostupná, pokud je zařízení nastavené pro jeden účet [Microsoft (MSA) nebo místní účet](hololens-identity.md).

6. Zavřete nabídku stisknutím libovolného jiného místa nebo zavřením nabídka Start pomocí gesta Start.

#### <a name="update-indicator"></a>Indikátor aktualizace

Když je k dispozici aktualizace, ikona se třemi tečkami se zobrazí, což značí, že restartováním se nainstaluje aktualizace. Možnosti nabídky se také změní tak, aby odrážely přítomnost aktualizace.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Dříve se na obrazovce Přihlásit zobrazí jenom naposledy přihlášený uživatel a také vstupní bod Jiný uživatel. Dostali jsme zpětnou vazbu od zákazníků, že to nestačí, pokud se k zařízení přihlásilo více uživatelů. Stále se vyžadovalo, aby znovu zadat své uživatelské jméno atd.

V tomto Windows buildu se  při výběru možnosti Jiný uživatel, který se nachází napravo od pole pro zadání kódu PIN, zobrazí přihlašovací obrazovka více uživatelů s přihlášením k zařízení. To uživatelům umožňuje vybrat svůj profil uživatele a pak se přihlásit pomocí svých přihlašovacích Windows Hello uživatele. Nového uživatele můžete do zařízení přidat také z této stránky Ostatní uživatelé pomocí **tlačítka Přidat** účet.

V nabídce Ostatní uživatelé se na tlačítku Ostatní uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka.](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiných uživatelů.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externího mikrofonu USB-C

> [!IMPORTANT]
> Když zapojíte mikrofon USB, nenastaví **se automaticky jako vstupní zařízení.** Při připojování k sadě konektorů USB-C uživatelé sledují, že zvuk zařízení se automaticky přesměruje na konektory, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad libovolným jiným vstupním zařízením. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí panelu **nastavení** Zvuk. Mikrofony USB-C je možné použít k volání, nahrávání atd.

Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**

![Sound Nastavení.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace znamená,** že externí mikrofon se použije ve vzdáleném asistenci a dalších komunikačních aplikacích, ale pole HoloLens Mic se může používat i pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavte výchozí mikrofon.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co Bluetooth mikrofonu?

V Bluetooth 2 se bohužel stále nepodporují HoloLens mikrofony.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound explicitně nastavte vestavěné mluvčí (zvukový ovladač  >    >   **analogové funkce)** jako **výchozí zařízení.** HoloLens byste si toto nastavení měli zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatické přihlášení návštěvníka pro bezobrazovkové režimy

Tato nová funkce umožňuje použití automatického přihlašování k účtům Návštěvník v bezobrazovkovém režimu.

Konfigurace zařízení bez AAD pro automatické přihlášení návštěvníka:

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje **nastavení modulu runtime /AssignedAccess tak,** aby povolují účty návštěvníka.
    1. Volitelně zaregistruje zařízení v MDM (nastavení modulu **runtime, pracoviště/ registrace),** aby ho bylo možné později spravovat.
    1. Nevytvářejte místní účet.
1. [Použijte zřizovací balíček](hololens-provisioning.md).

V případě AAD konfigurace mohou uživatelé bez této změny dosáhnout něčeho podobného. AAD zařízení připojená k bezobrazovkovému režimu mohou přihlásit účet návštěvníka jediným klepnutím na přihlašovací obrazovku. Jakmile se zařízení přihlásí k účtu návštěvníka, nebude znova vyzváno k přihlášení, dokud se návštěvník z nabídky Start explicitně odhlásit nebo dokud se zařízení nerestartuje.

Automatické přihlášení návštěvníka je možné spravovat [pomocí vlastních zásad OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Hodnota URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automaticky se přihlásit k bezobrazovkovému režimu.   | 1 (Ano), 0 (Ne, výchozí.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových aplikací Nastavení Edge v režimech veřejného terminále

Při zahrnutí aplikací do [veřejného terminálu](hololens-kiosk.md)správce IT často přidá aplikaci do veřejného terminálu, ale použije JI AUMID (App User Model ID). Vzhledem k tomu, že aplikace Nastavení i aplikace Microsoft Edge se považují za nové aplikace a liší se od starších aplikací, které pro tyto aplikace používají identifikátory AUMID, bude potřeba aktualizovat, aby bylo možné používat nové AUMID.

Při úpravách veřejného terminálů tak, aby zahrnoval nové aplikace, doporučujeme přidat nový AUMID a nechat starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou muset přijímat nové zásady, aby mohli dál používat beziosk, jak má.

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

Do Windows Holographic verze [20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali zásadu [Nastavení/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) která omezuje stránky, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit tomu, aby byly konkrétní stránky v aplikaci System Nastavení viditelné nebo přístupné, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

Pokud navštívíte [stránku s Nastavení viditelnosti,](settings-uri-list.md)najdete pokyny k použití tohoto poskytovatele CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšiřujeme seznam dostupných identifikátorů URI, Nastavení mohou spravovat správci IT. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové Nastavení aplikace. Pokud používáte zásady Nastavení/PageVisibilityList, zkontrolujte následující seznam a podle potřeby upravte povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: ms-settings:network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Stará stránka **& internetového** proxy serveru už není dostupná  >   jako globální nastavení. Nová nastavení proxy serveru pro připojení najdete v části **Network & Internet** Wi-Fi Properties (Vlastnosti internetové sítě  >  **Wi-Fi)** nebo Network & Internet Ethernet Properties (Vlastnosti  >     >  **internetového**  >  **ethernetu).**

<br>

| Stránka Nastavení                                        | Identifikátor URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplikace > Apps & funkce                               | `ms-settings:appsfeatures`                         |
| Funkce > Apps & v > Upřesnit možnosti          | `ms-settings:appsfeatures-app`                     |
| Aplikace > offline mapy                                  | `ms-settings:maps`                                 |
| Aplikace > offline mapy > stažení map                  | `ms-settings:maps-downloadmaps`                    |
| Zařízení > myši                                      | `ms-settings:mouse`                                |
| Zařízení > USB                                        | `ms-settings:usb`                                  |
| Připojení & internetové > v režimu v letadle                   | `ms-settings:network-airplanemode`                 |
| Zásady ochrany > osobních údajů                                    | `ms-settings:privacy-general`                      |
| Ochrana > osobních & při psaní přizpůsobení             | `ms-settings:privacy-speechtyping`                 |
| Ochrana osobních > pohybu                                     | `ms-settings:privacy-motion`                       |
| Ochrana osobních > Snímek obrazovky s ohraničením                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Ochrana osobních > Snímky obrazovky a aplikace                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Systémová > baterie                                     | `ms-settings:batterysaver`                         |
| Systémová > baterie                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| Předvolby > a > aplikací v nástroji System > Sound | `ms-settings:apps-volume`                          |
| System > Sound > Správa zvukových zařízení              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Datum & čas > časového &                        | `ms-settings:dateandtime`                          |
| Time & Language > klávesnice                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizace & obnovení > obnovení & zabezpečení               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualizované identifikátory URI

Dříve by následující dvě identifikátory URI nesly uživatele přímo na uvedené stránky, ale zablokovaly jenom hlavní stránku aktualizací. Následující položky byly aktualizovány tak, aby směrovat na jejich stránky:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurace diagnostiky pro záložní Nastavení aplikací

Teď, Nastavení aplikaci, může uživatel nakonfigurovat chování diagnostiky [pro fallback.](hololens-diagnostic-logs.md) Na stránce Nastavení přejděte na stránku Řešení **potíží** s  >  **ochranou osobních** údajů a nakonfigurujte toto nastavení.

> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí s blízkými zařízeními

Sdílejte věci s ostatními zařízeními Windows 10, včetně počítačů a dalších zařízení HoloLens 2. Můžete si ho vyzkoušet v **Nastavení** prostředí pro sdílení souborů nebo adres URL z  >    >   HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s [blízkými](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)zařízeními v Windows 10 .

Tuto funkci je možné spravovat prostřednictvím [možnosti Připojení/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová diagnostická trasování operačního systému

Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte na **Nastavení**  >  **Update Security &amp; Windows**  >    >  **Update a** vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručení Preview

Díky této HoloLens aktualizace Windows Holographic for Business nastavení optimalizace doručení, aby se snížila spotřeba šířky pásma pro stahování z několika HoloLens zařízení. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: Optimalizace doručení [pro Windows 10 aktualizace.](/windows/deployment/update/waas-delivery-optimization)

V rámci možností správy jsou povolená následující nastavení, [která je možné nakonfigurovat z Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DoCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DoCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DoDownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DoPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik upozornění na tuto nabídku verze Preview:

- HoloLens verze Preview je omezená pouze na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v HoloLens zařízení nepodporují.
- HoloLens nepodporuje optimalizaci nasazení nebo doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování na HoloLens v HoloLens prostřednictvím služby **Nastavení**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – kontrolní seznam aktualizací

Tento kontrolní seznam vám pomůže se seznamem nových položek přidaných v této aktualizaci funkcí, které můžou mít vliv na aktuální konfiguraci správy zařízení nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace do bezobrazovkovém režimu

✔️ Nové [**identifikátory AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste dříve v beznaiosku Nastavení aplikaci Microsoft Edge, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové aplikace v [beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení v bezobrazovkovém okně, nebo zahrnout novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ [**automatického přihlášení návštěvníka pro bezobrazovkové režimy:**](#visitor-auto-logon-for-kiosks)

Návštěvníci teď mohou být automaticky přihlášení do veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ [**vylepšené selhání bezobrazovkového režimu:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Pokud AAD AAD přihlášený uživatel ve skupině není úspěšně určen, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o vašem oddělení podpory, pokud používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti Nastavení stránky

✔️ nové [**identifikátory URI** Nastavení pro viditelnost Nastavení stránky](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte viditelnost [Nastavení,](settings-uri-list.md) možná budete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC

✔️ Pokud jste dříve blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující informace a použijte poskytnutý vzorový kód.

#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge

✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ [Konfigurace diagnostiky pro záložní](#configuring-fallback-diagnostics-via-settings-app)prostředky: Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

✔️ Sdílení[věcí s blízkými zařízeními:](#share-things-with-nearby-devices)Novou funkci sdílení v okolí můžete zakázat.

✔️ Konfigurace [nastavení zásad pro](#configuring-policy-settings-for-the-new-microsoft-edge)novou Microsoft Edge: Zkontrolujte nově dostupné konfigurace pro Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nový diagnostický nástroj

✔️[nová diagnostická trasování operačního systému:](#new-os-diagnostic-traces)Shromáždí protokoly související s aktualizacemi operačního systému.

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- [Offline diagnostika bude](hololens-diagnostic-logs.md#offline-diagnostics) obsahovat také další informace o zařízení pro sériové číslo a verzi operačního systému.
- Opravuje problém s nasazování obchodních aplikací prostřednictvím zřizovacích balíčků modulu runtime.
- Opravuje problém s hlášením stavu instalace obchodních aplikací.
- Opravuje problém s trvalostmi nových balíčků aplikací napříč resetováním zařízení.
- Opravuje problém, který mohl vést k zadání nesprávných symbolů v edgi pro japonské zákazníky.
- Vylepšuje odolnost aktualizací operačního systému u předinstalovaných aplikací, jako je Edge.
- Řeší spolehlivost aktualizací, která má vliv na instalaci Microsoft Edge.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z května 2021

- Build 19041.1146

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z května 2021

- Build 18362.1110

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné záhodné změny. **Toto sestavení už nebude dostávat měsíční aktualizace služby**. Doporučujeme vám vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

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
- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba zvýšila využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.
- Opravili jsme problém, kdy se uživatelé zaregistrovaní ve fázi rolloutu k zařízení nepokusili přihlásit.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z března 2021

- Build 18362.1102

Vylepšení a opravy v aktualizaci:

- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba zvýšila využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z února 2021

- Build 19041.1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém s počátečním nastavením zařízení a aktualizacemi aplikací pro Store.
- Řeší problém s upgrady a lety pro pozdější HoloLens verze.
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM HoloLens zařízení.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z února 2021

- Build 18362.1098

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z ledna 2021

- Build 19041.1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spouštění, obnovování a přepínání uživatelů, pokud je na zařízení mnoho uživatelů.
- Přidání podpory arm32 pro [Research Mode](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z ledna 2021

- Build 18362.1091

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, verze 20H2 – aktualizace z prosince 2020

- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací

Přidáváme **novou funkci (Instalační program aplikací),** která vám umožní hladceji instalovat aplikace na zařízení s HoloLens 2. Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.** Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli pro **spravovaná zařízení** dostupný.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:

- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, která se zobrazí s výzvou k instalaci.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní aplikace [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) MDM, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens důvěryhodný, aby bylo možné aplikaci nasadit.

**Pokyny k instalaci aplikace.**

1. Ujistěte se, že se vaše zařízení nepovažuje za spravované.
1. Ujistěte se, že HoloLens 2 je zapnuté a připojené k počítači.
1. Ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1. Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní Storage\Soubory ke stažení.   Po dokončení kopírování souboru můžete zařízení odpojit.
1. Na svém HoloLens 2 Otevřete nabídku Start, vyberte Všechny aplikace a spusťte Průzkumník souborů aplikaci.
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat Toto zařízení a pak přejít na Položky ke stažení.
1. Vyberte soubor yourapp.appxbundle.
1. Spustí Instalační program aplikací aplikace . Vyberte tlačítko Install (Nainstalovat) a nainstalujte aplikaci.
Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

Ukázkové aplikace najdete na Windows [univerzálních GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) a tento tok otestujte.

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí Instalační program aplikací](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování rukou teď udržuje sledování v mnoha nových případech, kdy by se dříve ztratila rukou.  V některých z těchto nových případů se bude aktualizovat pouze pozice uživatele na základě jeho skutečné ruky, zatímco druhá pozice je odvozena na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako je plevání, házení, odhazování a tlesání.  Pomáhá také v případech, kdy je ruce blízko povrchu nebo drží objekt.  Při odvozování ručního odhadu se hodnota společné přesnosti nastaví na "Approximate" (Přibližný) místo na High (Vysoká). [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)
- Opravili jsme problém, kdy se při resetování kódu PIN pro účty Azure AD zobrazí chyba Něco se pokazilo.
- Při spouštění ET, Iris z aplikace nastavení, nového uživatele nebo informační zprávy by uživatelé měli vidět mnohem méně selhání při spuštění.
- Uživatelé by měli mít správné časové pásmo přicházející z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z prosince 2020

- Build 18362.1088

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naši nejnovější verzi Windows Holographic verze 20H2–prosinec 2020 Update a novou funkci Instalační program aplikací přidanou v sestavení.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic verze 20H2

- Build 19041.1128

Windows Holographic verze 20H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a IT specialisty. Od funkce automatického umisování do Správce certifikátů v Nastavení, vylepšené funkce bezobrazovkového režimu a nové možnosti nastavení Autopilotu. Tato nová aktualizace umožňuje IT týmům převzít podrobnější kontrolu nad konfigurací a správou HoloLens zařízení a nabízí uživatelům ještě hladká holografická prostředí.

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční verzi verze 2004 (build 19041). Na své číslo sestavení se můžete podívat na obrazovce Nastavení > o aplikaci a ověřit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co je nového v Windows Holographic verze 20H2  

| Funkce                                              | Popis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Podpora funkce Auto Eye Position](hololens-release-notes.md#auto-eye-position-support) | Aktivně počítá pozice očí, aniž by uživatelé prošli sledováním očí.   |
| [Správce certifikátů](hololens-release-notes.md#certificate-manager)   | Umožňuje nové jednodušší metody instalace a odebrání certifikátů z Nastavení aplikace.     |
| [Automatické spuštění zřizování z USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Zřizovací balíčky na USB jednotkách automaticky zobrazí výzvu ke zřízení stránky pro spuštění počítače.                                                         |
| [Automatické potvrzení zřizovacího balíčku v OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Zřizovací balíčky se na stránce zřizování automaticky použijí během spuštění při spuštění zařízení.                                                         |
| [Automatické zřizování bez použití uživatelského rozhraní](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak kombinovat automatické spouštění zřizování a automatické potvrzení. |
| [Použití Autopilotu s Wi-Fi připojením](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Použijte Autopilot ze zařízení Wi-Fi bez potřeby ethernetového adaptéru. |
| [Tenantlockdown CSP a Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po registraci tenanta a použití zásad se zařízení může v tomto tenantovi zaregistrovat jenom pokaždé, když se zařízení resetuje nebo znovu zabliká. |
| [Globální přiřazený přístup](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nová metoda konfigurace pro režim veřejného terminálů s více aplikacemi, která používá beziosk na úrovni systému, takže je použitelný pro všechny.                  |
| [Automatické spuštění aplikace v bezobrazovkovém režimu s více aplikacemi](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Nastaví automatické spuštění aplikace při přihlášení do bezobrazovkovém režimu s více aplikacemi.                                                        |
| [Změny chování v bezobrazovkovém režimu pro zpracování selhání](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Selhání bezobrazovkového režimu teď má omezující záložní režim.                                                                                                |
| [HoloLens Politiky](hololens-release-notes.md#hololens-policies)                                    | Nové zásady pro HoloLens.     |
| [Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nové zásady umožňují uživatelům používat mezipaměť členství ve skupinách k použití bezobrazovkového režimu offline po nastavený počet dnů.                                        |
| [Nové zásady omezení zařízení pro HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Zásady správy zařízení jsou nově povolené pro HoloLens 2.                                                                                |
| [Nové zásady napájení pro HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nově podporované zásady pro nastavení časového limitu napájení  |
| [Aktualizace zásad](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nově povolené zásady umožňující kontrolu nad aktualizacemi           |
| [Povolení Nastavení viditelnosti stránky pro HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Zásady pro výběr stránek, které se v Nastavení aplikaci             |
| [Režim výzkumu](hololens-release-notes.md#research-mode) | Použití režimu Research na HoloLens 2. |
| [Zvýšení délky záznamu](hololens-release-notes.md#recording-length-increased) | Záznamy MRC se už neřízly na 5 minut. |
| [Vylepšení a opravy v aktualizaci](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Další opravy v aktualizaci   |

### <a name="auto-eye-position-support"></a>Podpora funkce Auto Eye Position

V HoloLens 2 umožňují pozice očí přesné umístění hologramu, pohodlné sledování a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**Funkce Auto Eye Position (AEP)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel zařízení spustí. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová, a proto se tento proces opakuje, když uživatel odstartuje a zařízení znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasadí neomezaný uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu neomešlený uživatel odkazuje na někoho, kdo předtím neprošel procesem sledování zraku na zařízení.

| Aktivní aplikace | Předchozí chování | Chování z Windows Holographic, aktualizace verze 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace bez pohledu nebo Holographic Shell |Zobrazí se dialogové okno příkazového řádku sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno příkazového řádku sledování očí. | Výzva ke sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke streamu pohledu do oka. |

Pokud uživatel přechází z aplikace, která není pohledem povolená, na aplikaci, která přistupuje k pohledným datům, zobrazí se výzva k přihlášení.

Veškeré ostatní chování systému bude podobné, jako když aktuální uživatel nemá aktivní sledování očí. Například gesto Jednoručné spuštění nebude povoleno. Při počátečním nastavení se prostředí prvního spuštění nezmění.

Pro prostředí, která vyžadují pohled na data nebo velmi přesné umístění hologramu, doporučujeme necibrovaným uživatelům spustit sledování očí. Je přístupný z příkazového řádku pro sledování očí nebo spuštěním aplikace Nastavení z nabídky Start a výběrem možnosti System > Vychytáující > Eye **kaša >** Spuštění oka.

Tyto informace najdete později spolu s dalšími [informacemi o produktu](hololens-calibration.md#auto-eye-position-support).

### <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené nástroje pro auditování, diagnostiku a ověřování pro zabezpečení a dodržování předpisů zařízení prostřednictvím nového Správce certifikátů Tato funkce vám umožní nasadit, řešit potíže a ověřit certifikáty ve velkém měřítku v komerčních prostředích.

V Windows Holographic verze 20H2 přidáváme Správce certifikátů do HoloLens 2 Nastavení aplikace. Přejděte na **Nastavení > Update & Security > Certificates**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů v zařízení. S novým Správcem certifikátů teď správci a uživatelé vylepšili auditování, diagnostiku a ověřování, aby zajistili, že zařízení zůstanou zabezpečená a vyhovující.

- **Auditování:** Možnost ověřit, že je certifikát správně nasazený, nebo ověřit, že byl správně odebrán.
- **Diagnostika:** Když nastanou problémy, ověření, že v zařízení existují příslušné certifikáty, šetří čas a pomáhá s řešením potíží.
- **Ověření:** Ověření, že certifikát slouží zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Pokud chcete rychle najít konkrétní certifikát v seznamu, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé mohou také přímo vyhledat certifikát. Pokud chcete zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na **Informace.**

Instalace certifikátu aktuálně podporuje soubory .cer a .crt. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  Všichni ostatní uživatelé se instaluje jenom do aktuálního uživatele. Uživatelé instalují certifikáty jenom přímo z uživatelského rozhraní Nastavení počítače. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.

#### <a name="steps-to-install-a-certificate"></a>Postup instalace certifikátu

1. Připojení počítač HoloLens 2.
1. Soubor certifikátu, který chcete nainstalovat, umístěte do umístění na HoloLens 2.
1. Přejděte na **Nastavení App > Update & Security > Certificates** a vyberte Nainstalovat certifikát.
1. Klikněte **na Importovat** soubor a přejděte do umístění, do něj které jste certifikát uložili.
1. Vyberte **Store Location (Umístění obchodu).**
1. Vyberte **Úložiště certifikátů.**
1. Klikněte na **Install** (Nainstalovat).

Certifikát by teď měl být nainstalovaný na zařízení.

#### <a name="steps-to-remove-a-certificate"></a>Postup odebrání certifikátu

1. Přejděte na **Nastavení App > Update and Security > Certificates**.
1. Ve vyhledávacím poli vyhledejte certifikát podle názvu.
1. Vyberte certifikát.
1. Klikněte na **Odebrat.**
1. Po **zobrazení** výzvy k potvrzení vyberte Ano.

![Prohlížeč certifikátů v aplikaci Nastavení.](images/certificate-viewer-device.jpg)

![Obrázek znázorňující, jak pomocí uživatelského rozhraní certifikátu nainstalovat certifikát](images/certificate-device-install.jpg)

Tyto informace najdete později [na nové stránce Správce certifikátů](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňující menší interakci uživatelů, když se během spuštění počítače používají jednotky USB se zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek ručně spustit obrazovku zřizování během spuštění počítače. Uživatelé teď mohou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na úložné jednotce USB.

1. Připojte jednotku USB se zřizovacím balíčkem během prvního interagovatelného okamžiku prvního ZOBE.
1. Až bude zařízení připravené ke zřízení, automaticky se otevře výzva se stránkou zřizování.

Poznámka: Pokud je usb flash disk při spouštění zařízení připojený k napájení, OOBE provede výčet stávajícího paměťového zařízení USB a bude sledovat připojení dalších zařízení.

Další informace o použití zřizovacích balíčků během OOBE najdete v [HoloLens zřizování.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Další informace o [automatickém spouštění zřizování](hololens-provisioning.md#auto-launch-provisioning-from-usb) z USB najdete v dokumentaci HoloLens zřizování.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacího balíčku v OOBE

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

1. Vytvořte profil konfigurace zařízení pro beznaiosk cílení na skupiny Azure AD a přiřaďte ho HoloLens zařízením.
1. Vytvořte vlastní konfiguraci zařízení založenou na identifikátoru OMA URI, která nastaví tuto hodnotu zásady na požadovaný počet dní (> 0) a přiřadí ji HoloLens zařízením.
    1. Do textového pole OMA-URI by se měla zadat hodnota URI ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays.
    1. Hodnota může být v rozmezí od minimálního do maximálního povoleného.
1. Zaregistrujte HoloLens zařízení a ověřte, že se na zařízení použijí obě konfigurace.
1. Nechte uživatele Azure AD 1 přihlásit se, když je k dispozici internet, po úspěšném potvrzení přihlášení uživatele a úspěšného členství ve skupině Azure AD se vytvoří mezipaměť.
1. Uživatel Azure AD 1 teď může HoloLens režim offline a použít ho pro bezioskový režim, pokud hodnota zásady umožňuje počet dní X.
1. Kroky 4 a 5 je možné opakovat pro libovolného jiného uživatele Azure AD N. Klíčovým bodem je, že se každý uživatel Azure AD musí přihlásit k zařízení pomocí internetu, abychom mohli aspoň jednou určit, že jsou členem skupiny Azure AD, na kterou je cílem konfigurace veřejného terminálu.

> [!NOTE]
> Dokud se pro uživatele Azure AD neprovádí krok 4, bude docházet k chování při selhání uvedeném v odpojených prostředích.

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nové zásady omezení zařízení pro HoloLens 2

- Umožňuje uživatelům spravovat konkrétní zásady správy zařízení, jako je blokování přidávání nebo odebírání zřizových balíčků.

Nově povolené zásady, které umožňují více možností správy HoloLens 2 zařízení.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [Vzdálené zamykací zařízení](/windows/client-management/mdm/remotelock-csp)

Tyto dvě nové zásady pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení.](hololens-common-device-restrictions.md)

> [!NOTE]
> Pokud jde o [RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens podporuje jenom konfiguraci ./Vendor/MSFT/RemoteLock/Lock. Konfigurace týkající se kódu PIN, jako je resetování a obnovení, se nepodporují.

### <a name="new-power-policies-for-hololens-2"></a>Nové zásady napájení pro HoloLens 2

- Další možnosti pro HoloLens nebo zámky prostřednictvím zásad napájení.

Tyto nově přidané zásady umožňují správcům řídit stavy napájení, jako je časový limit nečinnosti. Další informace o jednotlivých zásadách si můžete přečíst kliknutím na odkaz pro jednotlivé zásady.

|     Odkaz na dokumentaci k zásadám                |     Poznámky                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Příklad hodnoty, která se má Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Příklad hodnoty, která se má Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Příklad hodnoty, která se má Windows Návrháři konfigurace, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Příklad hodnoty, která se má Windows Návrháři konfigurace, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se má Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se má Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové zásady pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení.](hololens-common-device-restrictions.md)

> [!NOTE]
> Kvůli konzistentnímu prostředí HoloLens 2 se ujistěte, že hodnoty pro DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery jsou nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti [o moderním pohotovostním režimu](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) najdete v článku o časovačích nečinnosti pro zobrazení, režim spánku a hibernaci.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nově povolené zásady aktualizace pro HoloLens

- Další možnosti pro instalaci aktualizací nebo zakázání tlačítka Pozastavit aktualizace pro zajištění aktualizací.

Tyto zásady aktualizací jsou teď povolené na HoloLens 2:

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Aktualizace/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Úplné podrobnosti o těchto zásadách aktualizací a jejich použití pro HoloLens si můžete přečíst tady v tématu Správa [HoloLens aktualizací.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Povolení Nastavení viditelnosti stránky pro HoloLens 2

- Větší ovládací prvek uživatelského rozhraní v Nastavení App, který může být zaměněn za zobrazení omezeného výběru stránek.

Teď jsme povolili zásadu, která správcům IT umožňuje zabránit tomu, aby byly konkrétní stránky v aplikaci System Nastavení viditelné nebo přístupné, nebo to dělat pro všechny stránky kromě těch, které jsou zadané. Pokud chcete zjistit, jak tuto funkci plně přizpůsobit, klikněte na následující odkaz.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informace o tom, která nastavení stránky můžete přizpůsobit na HoloLens 2, najdete na [naší Nastavení identifikátorů URI.](settings-uri-list.md)

![Snímek obrazovky s úpravami aktivních hodin v Nastavení aplikaci](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu

V režimu Research Mode se HoloLens 2 stává nástroj pro výzkum počítačového zpracování obrazu. Ve srovnání s předchozími edicemi má režim Research Mode pro HoloLens 2 následující výhody:

- Kromě senzorů vystavených v režimu výzkumu HoloLens (1. generace) teď poskytujeme přístup senzorů IMU, včetně akcelerometru, krátoboru a krátometru.
- HoloLens 2 poskytuje nové možnosti, které je možné používat společně s režimem výzkumu. Konkrétně přístup k rozhraním API pro ruční sledování a sledování očí, která doručují bohatší sadu experimentů.

Výzkumníci teď mají na svých vlastních zařízeních možnost povolit režim výzkumu HoloLens přístup ke všem těmto externím datovým proudům nezpracovaných obrazových senzorů. Režim výzkumu pro HoloLens 2 také poskytuje přístup k odečtům akcelerometru, krátoboru a krátometru. V rámci ochrany osobních údajů uživatelů nejsou nezpracované obrázky z fotoaparátů pro sledování očí dostupné prostřednictvím režimu výzkumu, ale směr pohledu je k dispozici prostřednictvím stávajících rozhraní API.

Další technické podrobnosti [najdete v dokumentaci](/windows/mixed-reality/research-mode) k režimu výzkumu.

### <a name="recording-length-increased"></a>Zvýšení délky záznamu

Z důvodu zpětné vazby od zákazníků jsme zvýšili délku záznamu zachytávání [hybridní reality.](holographic-photos-and-videos.md) Zachytávání hybridní reality už nebude ve výchozím nastavení omezené na 5 minut, ale místo toho vypočítá maximální délku záznamu na základě dostupného místa na disku. Zařízení odhadne maximální dobu trvání záznamu videa na základě dostupného místa na disku až do 80 % celkového místa na disku.

> [!NOTE]
> Pokud HoloLens jedna z následujících možností, bude aplikace používat výchozí délku záznamu videa (5 minut):
>
> - Odhadovaná maximální doba trvání záznamu je menší než výchozích 5 minut.
> - Dostupné místo na disku je méně než 20 % celkového místa na disku.

Všechny požadavky najdete v dokumentaci k [holografickým fotografiím a videím.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Vylepšení a opravy v Windows Holographic verze 20H2:

- Další obrazovky v OOBE jsou teď v tmavém režimu.
- Další informace by měly odkazovat na nejnovější prohlášení o zásadách ochrany osobních údajů online.
- Byl vyřešen problém, kdy uživatelé nemohli zřídit profily VPN prostřednictvím zřizovacích balíčků.
- Opravili jsme problém s konfigurací proxy serveru pro připojení VPN.
- Aktualizace zásad pro zákaz výčtu funkcí USB prostřednictvím MDM pro NCM pro AllowUsbConnection
- Byl vyřešen problém, který zabraňoval tomu, aby se zařízení HoloLens v Průzkumník souborů přes protokol MTP (Media Transfer Protocol), když je zařízení nastavené jako beznastavovaný terminál s jednou [aplikací.](hololens-kiosk.md) Mějte na paměti, že MTP (a připojení USB obecně) je stále možné zakázat pomocí zásad [AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Opravili jsme problém, kdy se ikony v nabídka Start správně škálují v beznaiosku.
- Opravili jsme problém kvůli tomu, že ukládání do mezipaměti HTTP zasahoval do bezobrazovkového režimu cíleného na skupiny Azure AD.
- Opravili jsme problém, kdy uživatelé nemohli po povolení vývojářského režimu se zřizovacími balíčky použít tlačítko Párovat, pokud nepovolili a nepovolili vývojářský režim.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z listopadu 2020

- Build 18362.1085

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější verzi buildu pro Windows Holographic verze 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, verze 2004 – aktualizace z října 2020

- Build 19041.1124

Vylepšení a opravy v aktualizaci:

- Odebrali jsme nepotřebnou kontrolu, která způsobila chybu systému modulu runtime.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z října 2020

- Build 18362.1081

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze září 2020

- Build 19041.1117

Vylepšení a opravy v aktualizaci:

- Řeší problém, který Visual Studio ladění aplikace, když se v souboru appxmanifest nachází SupportsMultipleInstances="true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která řeší selhání detekce internetu přes síťový proxy server. NCSI může k detekci připojení k Internetu použít proxy server a proxy server pro jednotlivé profily. Proxy server bude v budoucích verzích NCSI podporován pro každého uživatele.
- u většiny zařízení Windows Mixed Reality je vektor směrového směru rovnoběžný s vozovkou, když je hlavní pozice uživatele v neutrální pozici, kde se nachází. nicméně starší verze HoloLens 2 zarovnaly vektoru, aby byl kolmý na panely zobrazení, což je nakloněné dolů o několik stupňů vzhledem k ideální orientaci. novější verze HoloLens 2 tuto opravu opravily, aby se zajistila sémantická konzistence napříč faktory formuláře.
- Vylepšená odolnost sledování a výsledkem bude méně sledování ztrát v konkrétních scénářích.
- Tato verze obsahuje opravu pro zlepšení kvality zvukového časového razítka, která mohla přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holografická verze 1903 – září 2020 aktualizace

- Sestavení 18362,1079

Vylepšení a opravy v aktualizaci:

- u většiny zařízení Windows Mixed Reality je vektor směrového směru rovnoběžný s vozovkou, když je hlavní pozice uživatele v neutrální pozici, kde se nachází. nicméně starší verze HoloLens 2 zarovnaly vektoru, aby byl kolmý na panely zobrazení, což je nakloněné dolů o několik stupňů vzhledem k ideální orientaci. novější verze HoloLens 2 tuto opravu opravily, aby se zajistila sémantická konzistence napříč faktory formuláře.
- Vylepšená odolnost sledování a výsledkem bude méně sledování ztrát v konkrétních scénářích.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holografická verze 2004 – aktualizace ze srpna 2020

- Sestavení 19041,1113

Vylepšení a opravy v aktualizaci:

- Nastavení aplikace už nedodržuje možnosti registrace v aplikaci Iris nebo kalibrace sledování očí.
- Opravili jsme chybu při použití zřizovacího balíčku při spuštění OOBE, který přejmenuje zařízení a provede jiné akce (například připojení k síti), aby se po restartu zařízení v důsledku přejmenování nepodařilo provést další akce.
- Změněné barevné schéma počátečních toků nastavení zařízení, aby se zlepšila kvalita vizuálů

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holografická verze 1903 – aktualizace ze srpna 2020

- Sestavení 18362,1074

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows holografické verze 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holografická verze 2004 – červenec 2020 aktualizace

- Sestavení 19041,1109

Vylepšení a opravy v aktualizaci:

- Vývojáři si teď můžou vybrat mezi povolením nebo zakázáním portálu pro zařízení vyžadovat zabezpečené připojení.
- Vylepšení spolehlivosti pro aplikace se spouští po aktualizacích operačního systému.
- Výchozí jas složky Doručená pošta se změnil na 100 procent.
- vyřešili jsme problém týkající se předávání HTTPS pro Windows portál zařízení v HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holografická verze 1903 – červenec 2020 aktualizace

- Sestavení 18362,1071

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který by mohl způsobit, že se v aplikacích Unity při ztrátě nebo opětovném sledování ztratí hologramy.
- opravili jsme problém, který způsobil, že exkluzivní aplikace HoloLens při použití Emulator HoloLens s hardwarovou akcelerací na některých zařízeních vrátila do prostředí chybu.
- vyřešili jsme problém týkající se předávání HTTPS pro Windows portál zařízení v HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holografická verze 2004 – aktualizace od června 2020

- Sestavení 19041,1106

Vylepšení a opravy v aktualizaci:

- Vlastní zapisovače MRC teď mají nové výchozí hodnoty pro určité vlastnosti, pokud nejsou zadané.
  - Na *efekt videa MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (moderní sluchátka)
  - U *zvukového efektu MRC*:
    - LoopbackGain (aktuální hodnota "nárůst zvuku aplikace" na stránce zachycení hybridních realit na portálu zařízení Windows)
    - MicrophoneGain (aktuální hodnota "mikrofon zvukové úrovně" na stránce zachycení hybridních realit na portálu zařízení Windows)
- Opravili jsme chybu pro zlepšení kvality zvuku ve scénářích zachycení smíšené reality. Konkrétně by tato oprava měla při zobrazení nabídky **Start** eliminovat zvukové glitching v záznamu.
- Vylepšená stabilita hologramů v zaznamenaných videích.
- Vyřešili jsme problém, kdy zachycení hybridní reality nedokázalo nahrávat video, když bylo zařízení ponecháno v pohotovostním stavu po dobu více dní.
- Rozhraní API HolographicSpace. UserPresence je obecně pro aplikace Unity zakázané. Toto chování zabrání problému, který způsobil, že některé aplikace se při převrácení hypervisoru nemusely pozastavit, i když je povolené nastavení spustit v pozadí. Rozhraní API je teď povolené pro 2018.4.18 verze Unity a novější a 2019.3.4 a novější.
- Při přístupu k portálu zařízení přes Wi-Fi připojení může webový prohlížeč zabránit přístupu k z důvodu neplatného certifikátu. Prohlížeč může hlásit chybu, jako je například "ERR_SSL_PROTOCOL_ERROR", i když byl certifikát zařízení dříve důvěryhodný. V takovém případě nemůžete postupovat na portálu zařízení, protože nejsou k dispozici žádné možnosti ignorovat upozornění zabezpečení. Tato aktualizace vyřešila problém. Pokud byl certifikát zařízení dřív stažený a důvěryhodný na počítači kvůli odebrání upozornění zabezpečení prohlížeče a dojde k chybě SSL, musí se nový certifikát stáhnout a důvěřovat, aby se využívaly výstrahy zabezpečení prohlížeče.
- Umožnění vytvoření balíčku pro zřizování za běhu, který může nainstalovat aplikaci pomocí balíčků MSIX.
- do **Nastavení**  >  **systémových**  >  **Hologramy** bylo přidáno nastavení, které umožňuje uživatelům automaticky odebrat všechny hologramy ze smíšené reality, když se zařízení vypíná.
- opravili jsme problém, který způsobil, že HoloLens aplikace, které mění formát pixelu, aby se vykreslily černě v emulátoru HoloLens.
- Opravili jsme chybu, která způsobila selhání během přihlašování Iris.
- Opravili jsme problém se stahováním opakovaného úložiště pro už aktuální aplikace.
- opravili jsme chybu, aby se zabránilo otevírání aplikací pro moderní aplikace Microsoft Edge opakovaně.
- Opravili jsme problém se spuštěním aplikace fotky v počátečním spuštění po aktualizaci verze 1903.
- Vylepšený výkon a spolehlivost.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holografická verze 1903 – aktualizace od června 2020

- Sestavení 18362,1064

Vylepšení a opravy v aktualizaci:

- Vlastní záznamy MRC mají nové výchozí hodnoty pro určité vlastnosti, pokud nejsou zadané.
  - Na *efekt videa MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (moderní sluchátka)
  - U *zvukového efektu MRC*:
    - LoopbackGain (aktuální hodnota "nárůst zvuku aplikace" na stránce zachycení hybridních realit na portálu zařízení Windows)
    - MicrophoneGain (aktuální hodnota "mikrofon zvukové úrovně" na stránce zachycení hybridních realit na portálu zařízení Windows)
- Rozhraní API HolographicSpace. UserPresence je obecně pro aplikace Unity zakázané. Toto chování zabrání problému, který způsobí, že se některé aplikace při převrácení hypervisoru nespustí, a to i v případě, že je povolené nastavení na pozadí. Rozhraní API je teď povolené pro verze Unity 2018.4.18 a novější a 2019.3.4 a novější.
- opravili jsme problém, který způsobil, že HoloLens aplikace, které mění formát pixelu, vykreslí černou v HoloLens Emulator.
- Opravili jsme problém týkající se spuštění aplikace Fotky při počátečním spuštění po aktualizaci verze 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holografická verze 2004

- Build-19041,1103

hlavní aktualizace softwaru HoloLens 2 *Windows holografická verze 2004* obsahuje hostitele zajímavých nových funkcí, jako je například podpora Windowsho autopilotního, tmavého režimu aplikace, podpora sběrnice USB Ethernet pro 5G/LTE a mnoho dalšího. 2020 pokud chcete aktualizovat na nejnovější verzi, otevřete aplikaci **Nastavení**   , pokračujte na  **aktualizace & zabezpečení** a vyberte tlačítko  **vyhledat aktualizace**   . 

|             Funkce                              |          Popis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          předběžná konfigurace a bezproblémové nastavení nových zařízení pro produkční prostředí pomocí Windowsho automatického pilotního nasazení                 |
|       Podpora FIDO 2                             |          Podpora klíčů zabezpečení FIDO2 pro zajištění rychlého a zabezpečeného ověřování pro sdílená zařízení            |
|       Vylepšené zřizování                      |          Bezproblémové použití zřizovacího balíčku z jednotky USB na HoloLens                              |
|       Stav instalace aplikace                 |          podívejte se na stav instalace v aplikaci Nastavení pro aplikace, které se odeslaly do HoloLens 2 přes MDM.               |
|       Poskytovatelé konfiguračních služeb (CSP)   |          Přidání nových poskytovatelů konfigurační služby za účelem vylepšení možností řízení správy                 |
|       Podpora sběrnice USB 5G/LTE                       |          Rozšířená funkce USB Ethernet umožňuje podporu pro 5G/LTE.                                    |
|       Tmavý režim aplikace                              |          Tmavý režim aplikace dostupný pro aplikace, které podporují tmavé i lehké režimy, což zlepšuje možnosti zobrazení        |
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

Hlasové příkazy teď můžete používat s libovolnou aplikací na zařízení. Další informace najdete v tématu [Použití hlasu k ovládání HoloLens](hololens-cortana.md). Další informace najdete [v tématu Podporované jazyky pro HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana aktualizací

Aktualizovaná aplikace se integruje s Microsoft 365, která vám pomůže udělat více napříč zařízeními (aktuálně pouze US-English aplikacích). Na HoloLens 2 už Cortana určité příkazy specifické pro zařízení, jako je úprava svazku nebo restartování. Tyto možnosti teď podporují nové hlasové příkazy systému. Další informace o nové aplikaci Cortana najdete na našem [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  

- Zavedli jsme systém aktivního zobrazení s tekutou displeji. Tato funkce zlepšuje stabilitu a zarovnání hologramů. Když přesunete hlavičku ze strany na stranu, zůstanou na místě.
- Opravili jsme chybu, kdy Wi-Fi streamování do HoloLens se pravidelně přerušilo. Pokud aplikace indikuje, že potřebuje streamování s nízkou latencí, implementujte opravu voláním funkce [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Opravili jsme zablokované zařízení, ke kterým došlo při streamování v režimu výzkumu.
- Opravili jsme chybu, kdy se v některých případech při obnovení relace na přihlašovací obrazovce nezobrazl správný uživatel.
- Opravili jsme problém, kdy uživatelé nemohli exportovat protokoly MDM **prostřednictvím Nastavení**.
- Opravili jsme problém, kdy přesnost sledování očí hned po nastavení by mohla být nižší, než se čekalo.
- Opravili jsme problém, kdy subsystém pro sledování očí za určitých podmínek neinicializoval nebo neprováděl operaci.
- Opravili jsme problém, kdy se při pohledu na uživatele vyžádá už zkalibrovaný uživatel.
- Opravili jsme problém, kdy se ovladač během měření zraku havaroval.
- Opravili jsme problém, kdy opakované stisknutí tlačítka napájení mohlo způsobit 60sekudový časový limit systému a selhání prostředí.
- Vylepšená stabilita vyrovnávacích pamětí hloubky
- Přidali **jsme tlačítko Sdílet** do Centrum Feedback aby uživatelé mohli snadněji sdílet zpětnou vazbu.
- Opravili jsme chybu, kdy se roboRaid wan neinstaluje správně.

### <a name="known-issues"></a>Známé problémy

- Problém se systémovým jazykem zh-CN brání hlasovým příkazům v zachycení nebo zobrazení IP adresy zařízení ve smíšené realitě.
- Problém vyžaduje, abyste po spuštění Cortana zařízení spouštěl aplikaci s hlasovou aktivací "Cortana". Pokud jste aktualizovali ze sestavení 18362, může se zobrazit také druhá dlaždice aplikace pro předchozí verzi aplikace Cortana, která už v nabídce **Start** nefunguje.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z května 2020

- Build 18362.1061

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny, protože tým pracoval na aktualizaci Windows Holographic z května 2004, jak je popsáno výše.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z dubna 2020

- Build 18362.1059

**Tmavý režim pro podporované aplikace**

Mnoho Windows aplikací podporuje tmavý i světlý režim. HoloLens 2 zákazníci teď mohou zvolit výchozí režim pro aplikace, které podporují obě barevná schémata. Na základě zpětné vazby od zákazníků jsme nastavili výchozí režim aplikace na "tmavý", ale toto nastavení můžete kdykoli snadno změnit: Přejděte na Nastavení > System > Colors a vyhledejte **"Choose your default app mode"** **(Zvolit** výchozí režim aplikace).

Tyto "in-box" aplikace podporují tmavý režim:

- Nastavení
- Microsoft Store
- Poštovní
- Kalendář
- Průzkumník souborů
- Centrum Feedback
- OneDrive
- Fotky
- 3D prohlížeč
- Movies & TV

**Vylepšení a opravy také v aktualizaci:**

- Zajistili jsme, že se do zachytávání hybridní reality zahrnou překryvné vrstvy prostředí.
- Unreal developers can now use the 3D View page in Portál zařízení to test and debug their applications.
- Vylepšená stabilita hologramu ve smíšené realitě při použití *algoritmu HolographicDepthReprojectionMethod DepthReprojection*
- Opravili jsme chybu "Třída rozhraní API WinRT IStreamSocketListener není zaregistrovaná" v 32bitových aplikacích ARM.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z března 2020

- Build 18362.1056

Vylepšení a opravy v aktualizaci:

- Vylepšená stabilita hologramu ve smíšené realitě při použití *algoritmu HolographicDepthReprojectionMethod AutoPlanar*
- Zajistili jsme, aby souřadnicový systém připojený k vzorku HLOUBKY byl konzistentní s veřejnou dokumentací.
- Vyšší produktivita vývojářů tím, že zákazníkům umožňuje vkládat velké objemy textu prostřednictvím portálu zařízení.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z února 2020

- Build 18362.1053

Vylepšení a opravy v aktualizaci:

- Dočasně zakázali rozhraní API HolographicSpace.UserPresence pro aplikace Unity. Tato změna zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení zorovače, a to i v případě, že bylo povolené nastavení Spustit na pozadí.
- Opravili jsme náhodné selhání HUP způsobené ručním sledováním, při kterém si uživatel po několika sekundách všiml zablokování uživatelského rozhraní a pak zpět do prostředí.
- Vylepšené sledování rukou, takže když házíte ukazováčkem, je menší pravděpodobnost, že se horní část prstu neočekávaně cvrdí.
- Vylepšili jsme spolehlivost sledování hlavy, prostorového mapování a dalších běhových prostředí.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z ledna 2020

- Build 18362.1043

Vylepšení a opravy v aktualizaci:

- Vylepšená stabilita pro exkluzivní aplikace při práci s emulátorem HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, verze 1903 – aktualizace z prosince 2019

- Build 18362.1042

Vylepšení a opravy v aktualizaci:

- Zavedli jsme opravy poslední fáze reprodukování (LSR). Vylepšené vizuální vykreslování hologramů tak, aby se zdály stabilnější a ošemetnější díky přesnějšímu účtování jejich hloubky. Tento příznak bude po této aktualizaci patrnější, pokud aplikace nebudou správně nastavovat hloubku hologramů.
- Byla opravena stabilita výhradních aplikací a navigace mezi exkluzivními aplikacemi.
- Vyřešili jsme problém, kdy zachytávání hybridní reality nemohlo po několika dnech v pohotovostním stavu nahrát video.
- Vylepšená stabilita hologramu

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, verze 1903 – aktualizace z listopadu 2019

- Build 18362.1039

Vylepšení a opravy v aktualizaci:

- Opravili jsme **funkčnost příkazu Select** voice commands during initial setup for en-CA and en-AU (Výběr hlasových příkazů během počátečního nastavení pro en-CA a en-AU).
- Vylepšená vizuální kvalita objektů umístěných daleko v nejnovějších verzích Unity a Mixed Reality Toolkit (MRTK).
- Opravili jsme problémy s holografickými aplikacemi, které se při spuštění zasekly v pozastaveném stavu, dokud se nabídka Start neotevřel a pak nezavřel.
- Opravy shody modulu runtime OpenXR a vylepšení pro HoloLens 2 a emulátor.
