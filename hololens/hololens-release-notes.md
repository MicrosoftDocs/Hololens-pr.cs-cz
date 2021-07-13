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
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 1de9687174bf9c1de2e2b15ee03aa841254b0b82
ms.sourcegitcommit: 2988afb1d7792c9e4bae15485cd52d6eff7e27c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "113685044"
---
# <a name="hololens-2-release-notes"></a>poznámky k verzi HoloLens 2

abychom se ujistili, že máte k dispozici produktivní prostředí s HoloLensmi zařízeními, budeme pořád vydávat aktualizace zabezpečení a funkce, chyby a zabezpečení. na této stránce uvidíte, co je nového pro HoloLens každý měsíc. pokud chcete získat nejnovější aktualizaci HoloLens 2, můžete buď [vyhledat aktualizace, a ručně aktualizovat](hololens-update-hololens.md#check-for-updates-and-manually-update) nebo získat úplnou aktualizaci flash (FFU), která [vám umožní flash zařízení pomocí pokročilého průvodce obnovením](hololens-recovery.md#clean-reflash-the-device). [Stažení](https://aka.ms/hololens2download) je udržováno v aktuálním stavu a poskytuje nejnovější všeobecně dostupné sestavení.

> [!NOTE]
> nedávné oznámení Windows 11 se zaměřuje na verzi Windows počítače. nedávno jsme spustili [hlavní aktualizaci operačního systému](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) HoloLens 2 v květnu 2021 a pracujeme na nadcházející verzi na základě zpětné vazby od zákazníků.

> [!IMPORTANT]
> v důsledku nově vyřešeného [známého problému v našem buildu 21H1, který má vliv na uživatele vzdálené pomoci](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), jsme dočasně pozastavili nabídku Windowsch holografických aktualizací verze 21H1. také jsme změnili výchozí sestavení průvodce rozšířeným obnovením (ARC) na [Windows holografické verze 20H2 – červen 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Sestavení ARC teď obnoví cílení na sestavení 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holografická verze 21H1 – červenec 2021 Update
- Sestavení 20348,1010

Vylepšení a opravy v aktualizaci:

- Portál zařízení má rozšířené metody upozorňování zákazníka, když se v Průzkumníkovi souborů vyskytnou problémy s otevíráním uzamčených souborů.
- při použití Emulator HoloLens 2 v počítači s integrovanými i diskrétními grafickými adaptéry bude emulátor ve většině případů moci povolit akceleraci hardwarových grafik, i když může používat méně výkonný integrovaný adaptér.  Dříve nebylo možné povolit hardwarovou akceleraci, což často oznamuje selhání grafiky s kódem 43.  V některých případech se emulátor nerestartoval úspěšně, ale teď se spustí.
- Nahrání souboru, stažení, přejmenování a odstranění je teď opravené při použití protokolu HTTPS ve všech podporovaných prohlížečích.
- opraven problém, kdy Wi-Fi proxy server nelze uložit při spuštění Wi-Fi vlastností uživatelského rozhraní z **Nastavení-> síťové & > stav-> vlastnosti**.
- Vyřešili jsme problém s odebráním certifikátů eSIM napříč aktualizacemi operačního systému. Tato oprava zajistí, že se při aktualizaci verze 21H1 odebraly certifikáty eSIM a související součásti.
- Opravili jsme problém ovlivněný předinstalovanými aplikacemi v rámci resetování operačního systému. 
- Zvýšení výkonu při nabíjení baterie za účelem zvýšení modulu runtime při zpoplatnění zvýšeného zatížení procesoru.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holografická verze 20H2 – červenec 2021 Update
- Sestavení 19041,1157

Vylepšení a opravy v aktualizaci:
- Portál zařízení má rozšířené metody upozorňování zákazníka, když se v Průzkumníkovi souborů vyskytnou problémy s otevíráním uzamčených souborů. 
- při použití Emulator HoloLens 2 v počítači s integrovanými i diskrétními grafickými adaptéry bude emulátor ve většině případů moci povolit akceleraci hardwarových grafik, i když může používat méně výkonný integrovaný adaptér.  Dříve nebylo možné povolit hardwarovou akceleraci, což často oznamuje selhání grafiky s kódem 43.  V některých případech se emulátor nespustí úspěšně, ale teď to bude.
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
>- Windows Holografická verze 20H2 (Build 19041.1128 +)
>- Windows Holografická verze 2004 (Build 19041.1103 +)
>- Windows Holografická verze 1903 (Build 18362 +) 
>
> díky zavedení Windows holografické verze 21H1 **netrváme měsíční aktualizace pro Windows holografické verze 1903**. Díky tomu se můžeme soustředit na další nejnovější verze a dál dodávat cenná vylepšení. 


| Název funkce                                              | Krátký popis                                                                      | Cílovou skupinu | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nové Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nová aplikace Chromium založená na Microsoft Edge je teď k dispozici pro HoloLens 2. | Koncový uživatel | 
[WebXR a 360 Viewer](#webxr-and-360-viewer) | Vyzkoušejte imerzivní webová prostředí a přehrávání videa 360. | Koncový uživatel | 
[Nová Nastavení aplikace](#new-settings-app) | Starší Nastavení nahrazuje aktualizovaná verze novými funkcemi a nastaveními. | Koncový uživatel |
[Zobrazení barevného pozadí](#display-color-calibration) | Vyberte alternativní profil barev pro váš HoloLens 2. | Koncový uživatel |
[Výchozí výběr aplikace](#default-app-picker) | Vyberte, která aplikace se má spustit pro každý typ souboru nebo odkazu. | Koncový uživatel |
[Řízení objemu na aplikaci](#per-app-volume-control) | Objem na úrovni aplikace můžete řídit nezávisle na systémovém svazku. | Koncový uživatel |
[Instalace webových aplikací](#install-web-apps) | Nainstalujte webové aplikace na HoloLens 2, například Microsoft Office, pomocí nového Microsoft Edge prohlížeče. | Koncový uživatel |
[Potažením prstem zadejte](#swipe-to-type) | Pomocí špičky prstu potáhněte slova na holografické klávesnici. | Koncový uživatel |
[Nabídka Napájení z nabídky Start](#power-menu-from-start) | V nabídce Start restartujte a vypněte HoloLens zařízení. | Koncový uživatel |
[Více uživatelů uvedených na přihlašovací obrazovce](#multiple-users-listed-on-sign-in-screen) | Zobrazení několika uživatelských účtů na přihlašovací obrazovce | Koncový uživatel |
[Podpora externího mikrofonu USB-C](#usb-c-external-microphone-support) | Pro aplikace a/nebo Remote Assist použijte mikrofony USB-C. | Koncový uživatel |
[Automatické přihlášení návštěvníka pro terminály](#visitor-auto-logon-for-kiosks) | Povolí použití automatického přihlášení k účtům Návštěvník v bezobrazovkovém režimu. | Správce IT |
[Nové identifikátory AUMID pro nové aplikace v beznavídkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Identifikátory AUMID pro nové Nastavení a aplikace Edge. | Správce IT |
[Vylepšené předání chyb v bezobrazovkovém režimu](#kiosk-mode-behavior-changes-for-handling-of-failures) | V bezobrazovkovém režimu se před prázdnou nabídkou Start hledá globální přiřazený přístup. | Správce IT |
[Nová nastaveníURIs pro viditelnost Nastavení zobrazení stránky](#new-settings-uris-for-page-settings-visibility) | Více než 20 nových nastaveníURIs pro Nastavení/PageVisibilityList. | Správce IT |
[Konfigurace diagnostiky pro záložní prostředky](#configuring-fallback-diagnostics-via-settings-app) | Nastavení chování diagnostiky pro záložní Nastavení aplikaci | Správce IT |
[Sdílení věcí s blízkými zařízeními](#share-things-with-nearby-devices) | Sdílet soubory nebo adresy URL z HoloLens do počítače. | Vše |
[Nová diagnostická trasování operačního systému](#new-os-diagnostic-traces) | Nový poradce při potížích Nastavení pro aktualizace operačního systému. | Správce IT |
[Optimalizace doručení Preview](#delivery-optimization-preview) | Snižte využití šířky pásma pro stahování z více HoloLens zařízení. | Správce IT |

Projděte si související poznámky k verzi:

- [Navštivte archiv HoloLens Emulator dat.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Průvodci Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Představení nového Microsoft Edge

![Animace staršího Microsoft Edge loga na nové Microsoft Edge loga](images/new-edge.gif)

Nový Microsoft Edge přijme [projekt Chromium open source,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) aby pro zákazníky vytvořil lepší kompatibilitu a méně fragmentace webu pro webové vývojáře.

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která [se](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) už v nových verzích nepodporuje.

![Snímek obrazovky Microsoft Edge nového snímku obrazovky](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Spuštění nové Microsoft Edge

Nový Microsoft Edge ![Ikona Microsoft Edge nový](images/new_edge_logo.png) (znázorněná ikonou modré a zelené swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

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
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada bude fungovat HoloLens 2. Otestovali a potvrdili jsme ale, že nové zásady Microsoft Edge ekvivalentem každé starší verze zásad Microsoft Edge dříve podporované u HoloLens 2 fungují podle očekávání. V [starší verze Microsoft Edge Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zásad najdete nový ekvivalent Microsoft Edge pro všechny starší zásady prohlížeče Microsoft Edge, které jste s verzí HoloLens 2 HoloLens.
>
> Existují alespoň dvě nové zásady Microsoft Edge, o které víme, *že nebudou* fungovat s HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nového Microsoft Edge na HoloLens 2

Vzhledem k tomu, že Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UPW, která umožňuje spuštění na zařízeních jenom pro UPW, jako je HoloLens 2, nemusí být některé funkce okamžitě dostupné. V nadcházejících měsících budeme podporovat nové scénáře a funkce, proto v tomto prostoru najdete aktuální informace.

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
- Prostorový zvuk z několika oken se souběžně zvukovými streamy
- "See it, say it"
- Tisk

**Hlavní známé problémy prohlížeče:**

- Náhled lupy na holografické klávesnici byl pro novou klávesnici Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu Sledovat](hololens2-basic-usage.md#follow-me-stop-following)mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna **tlačítkem X.**
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit neočekávané neaktivování ostatních 2D oken aplikací. Tato okna můžete znovu aktivovat opětovnou interakcí.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat víc verzí najednou. 

Další informace [o komunitě Edge Insider najdete na domovské stránce Microsoft Edge Insider.](https://www.microsoftedgeinsider.com) Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider Microsoft Edge několik metod, které HoloLens 2:

**Přímá instalace na zařízení (aktuálně dostupná pouze pro nespravovaná zařízení)**
  1. Na stránce HoloLens 2 přejděte na stránku [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **Stáhnout pro HoloLens 2** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor .msix z fronty pro stahování Edge nebo ze složky Stažené soubory (pomocí příkazu Průzkumník souborů).
  1. [Spustí se instalační](app-deploy-app-installer.md) program aplikace.
  1. Vyberte **tlačítko** Nainstalovat.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

**Instalace přes počítač s Windows Portál zařízení [(vyžaduje](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) povolení vývojářského režimu na počítači HoloLens 2)**
  1. Na počítači přejděte na stránku pro stažení [Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **se šipkou rozevíracího** seznamu vedle tlačítka Stáhnout pro Windows 10 pro kanál Edge Insider, který chcete nainstalovat.
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
>Od [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)nebude Office webová aplikace předem nainstalovaná.

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci Microsoft Office zobrazit a upravit soubory hostované na SharePoint nebo OneDrive. Pokud chcete nainstalovat Office aplikaci, navštivte a vyberte tlačítko App Available (Aplikace k dispozici) https://www.office.com nebo Install Office **(Nainstalovat** aplikaci) na panelu Adresa.  Potvrďte **výběrem** možnosti Nainstalovat.

> [!IMPORTANT]
> Office webové aplikace je dostupná jenom v případě, že HoloLens 2 má aktivní připojení k internetu.

### <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer

Součástí nového Microsoft Edge je podpora WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Řada imerzivních webových prostředí byla navržena s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale tato prostředí podporuje také virtuální HoloLens 2. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že nová imerzivní prostředí rozšířené reality a hybridní reality budou k dispozici HoloLens 2 zákazníky, kteří si to budou zkoušet!

Rozšíření 360 Viewer je postaveno na Aplikaci WebXR a automaticky se nainstaluje společně s novým Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

#### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu **vyberte tlačítko Enter VR** (Zadat virtuální realitu). Umístění a vizuální znázornění tohoto tlačítka se může u jednotlivých webových stránek lišit, ale může vypadat podobně jako:

    ![Příklad zadání tlačítka VR](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění prostředí WebXR v konkrétní doméně prohlížeč požádá o souhlas se zadáním imerzivního zobrazení a vybere **Povolit.**
1. K [HoloLens prostředí použijte 2](hololens2-basic-usage.md#the-hand-tracking-frame) gesta.
1. Pokud prostředí nemá tlačítko Ukončit, **pomocí** gesta [Start](hololens2-basic-usage.md#start-gesture) se vraťte domů.

**Doporučené ukázky WebXR**
- 360 Viewer (viz další část)
- [XR Užis](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR – Malování](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na video o 360 stupních na YouTube.
1. V rámečku videa vyberte tlačítko náhlavní soupravy hybridní reality:

    ![Tlačítko pro aktivaci prohlížeče 360](images/enter-360-viewer.jpg)

1. Když se poprvé pokusíte spustit prohlížeč 360 v konkrétní doméně, prohlížeč požádá o souhlas se zadáním imerzivního zobrazení. Vyberte **Povolit.**
1. [Klepnutím ve vzduchu](hololens2-basic-usage.md#select-using-air-tap) vylepšete ovládací prvky přehrávání. Pomocí [ručních paprsků](hololens2-basic-usage.md#select-using-air-tap) a klepnutí ve vzduchu můžete přehrát/pozastavit, přeskočit dopředu/dozadu, zapnout nebo vypnout titulky nebo ukončit prostředí (které ukončí imerzivní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Hlavní známé problémy s WebXR a 360 Viewerem
- V závislosti na složitosti prostředí WebXR může snímková frekvence poklesat nebo se zhoršit.
- Podpora pro articulated handu v WebXR není ve výchozím nastavení povolená. Vývojáři mohou podporu povolit `edge://flags` prostřednictvím zapnutím funkce "Ruční vstup WebXR".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby k WebXR a prohlížeči 360

Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce **Poslat** zpětnou vazbu v novém Microsoft Edge.

### <a name="new-settings-app"></a>Nová Nastavení aplikace

V této verzi představujeme novou verzi aplikace Nastavení. Nová aplikace Nastavení obsahuje nové funkce a rozšířená nastavení pro HoloLens 2 v následujících oblastech: Zvuk, Power & režim spánku, Síť & Internet, Aplikace, Účty, Usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, Nastavení nová aplikace se liší od starší Nastavení aplikace, při aktualizaci se Nastavení okna, která jste předtím umístili kolem svého prostředí.

![Domovská stránka Nastavení nové aplikace](images/new-settings-app.png)

**Nové funkce a nastavení**
- Nastavení: Na domovské stránce Nastavení pomocí klíčových slov nebo názvu nastavení vyhledejte nastavení.
- System > Sound:
  - Vstupní a výstupní zvuková zařízení: Nezávisle zvolte vstupní a výstupní zvuková zařízení (například naslouchejte zvuku prostřednictvím Bluetooth nebo použijte mikrofon USB-C pro zvukový vstup).
    > [!NOTE]
    > Bluetooth 2 nepodporuje HoloLens mikrofony.
  - Objem aplikace: Nezávisle upravte objem každé aplikace. Viz [řízení objemu na aplikaci.](#per-app-volume-control)
- System > Power & režim spánku: Zvolte, kdy má zařízení po určité době nečinnosti přejít do režimu spánku.
- Baterie >: Ručně povolte režim spořič baterie nebo nastavte prahovou hodnotu baterie, po spořič baterie režim zapne automaticky.
- Zařízení > USB: Ve výchozím nastavení můžete zakázat připojení USB.
- Network & Internet:
  - Ethernetové adaptéry USB-C se teď zobrazí v části Síťová & internetu.
  - K dispozici jsou teď nastavení ethernetového adaptéru USB-C, včetně jeho IP adresy.
  - Režim v letadle teď můžete povolit na HoloLens 2.
- Aplikace: Můžete resetovat výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu [Výběr výchozí aplikace.](#default-app-picker)
- Účty > Ostatní uživatelé: Vlastníci zařízení mohou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, downgradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů

**Známé problémy**
- Dříve umístěná Nastavení okna budou odebrána (viz poznámka výše).
- Zařízení už nemůžete přejmenovat pomocí Nastavení aplikace. Správci IT mohou zařízení přejmenovat pomocí šablony [Windows Autopilot pro název](hololens2-autopilot.md) zařízení HoloLens 2 nebo uzlu MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se za všech okolností zobrazuje virtuální ethernetové zařízení (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, protože je povaha desktopové aplikace Win32 podporované vrstvou adaptéru UPW (brzy se neočekává žádná oprava).

#### <a name="display-color-calibration"></a>Zobrazení barevného pozadí



Pomocí tohoto nového nastavení můžete vybrat alternativní profil barev pro váš HoloLens 2. Barvy se tak můžou zdát přesnější, zejména při nižších úrovních jasu zobrazení. Barevné závislosti můžete zobrazit v aplikaci Nastavení, a to na stránce System > Aplikace.

> [!NOTE]
> Vzhledem k tomu, že toto nastavení ukládá nový profil barev do firmwaru zobrazení, jedná se o nastavení pro jednotlivá zařízení (a není jedinečné pro každý uživatelský účet).

##### <a name="how-to-use-display-color-calibration"></a>Jak používat barvu zobrazení

1. Spusťte aplikaci **Nastavení** a přejděte na **System > Zakašlovací systém.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Spustit barvu pro **zobrazení.**
1. Spustí se prostředí zobrazení barev a budete se muset ujistit, že je zorník ve správné pozici.
1. Po pokračování v dialogových oknech s pokyny se vaše zobrazení automaticky ztmaní na 30% jas.
    > [!TIP]
    > Pokud máte potíže se zobrazením tlumené scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek brightness na levé straně zařízení.
1. Výběrem tlačítek 1–6 můžete okamžitě vyzkoušet každý profil barev a najít ten, který vám vypadá nejlépe do očí (obvykle to znamená profil, který pomáhá scéně zdát se nejneužívnější, se vzorem stupňů šedé a barevnými odstíny, které vypadají podle očekávání).)

    ![Zobrazení scény barevného pozadí](images/color-cal-ui.png)
    
1. Až budete s vybraným profilem spokojeni, vyberte tlačítko **Save & Exit (Uložit** a ukončit).
1. Pokud nechcete provádět změny, vyberte **tlačítko Zrušit & Ukončit** a změny se vrátí zpět.

> [!TIP]
> Tady je několik užitečných tipů, které je dobré mít na paměti při používání nastavení barev zobrazení:
> - Kdykoli chcete, můžete znovu spustit barevné Nastavení zobrazení.
> - Pokud někdo v zařízení dříve použil nastavení ke změně profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte barevné zvýraznění zobrazení, profil barev, který byl dříve uložen, se zvýrazní a profil 0 se nezobrazí (protože Profil 0 představuje původní profil barvy zobrazení).
> - Pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to udělat na stránce Nastavení (viz resetování profilu [barev).](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Resetování profilu barev 

Pokud s vlastním profilem barev uloženým v počítači HoloLens 2 nejste spokojeni, můžete původní profil barev zařízení obnovit:
1. Spusťte aplikaci **Nastavení** a přejděte na **System > Zakašlovací systém.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Obnovit výchozí **profil** barev.
1. Po otevření dialogového okna vyberte **Restartovat,** pokud jste připraveni restartovat počítač HoloLens 2 a použít změny.

#### <a name="top-display-color-calibration-known-issues"></a>Známé problémy s nejvyšším zobrazováním barev

- Na stránce Nastavení bude stavový řetězec, který vás informuje o tom, kdy byl profil barev naposledy změněn, neaktuální, dokud znovu nenačtete tuto stránku Nastavení.
    - Alternativní řešení: Vyberte Nastavení stránku a pak znovu vyberte stránku Uchovat.

#### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když aktivujete hypertextový odkaz nebo otevřete typ souboru s více nainstalovanými aplikacemi, která ho podporuje, zobrazí se nové okno s výzvou k výběru nainstalované aplikace, která by měla typ souboru nebo odkazu zpracovat. V tomto okně se také můžete rozhodnout, že vybraná aplikace zřídí soubor nebo typ odkazu "Jednou" nebo "Vždy".

Pokud zvolíte Možnost Vždy, ale později chcete změnit, která aplikace zpracovává konkrétní soubor nebo typ odkazu, můžete uložené výchozí hodnoty resetovat v Nastavení > **Apps**. Posuňte se do dolní části  stránky a vyberte tlačítko Vymazat v části Výchozí aplikace pro typy souborů a/nebo Výchozí aplikace pro typy odkazů. Na rozdíl od podobného nastavení na stolních počítačích nemůžete resetovat výchozí nastavení jednotlivých typů souborů.

#### <a name="per-app-volume-control"></a>Řízení objemu na aplikaci

V této Windows sestavě mohou uživatelé ručně upravit úroveň svazku každé aplikace. To umožňuje uživatelům lépe se soustředit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například když potřebujete vypnout objem jedné aplikace a volat jinou osobu kvůli vzdálené pomoci v jiné.

Pokud chcete nastavit svazek jednotlivé aplikace, přejděte **na Nastavení** Zvuk systému a v části Pokročilé možnosti zvuku vyberte Svazek aplikace a  ->    ->   **předvolby zařízení.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potažením prstem zadejte

Někteří zákazníci zjistí, že psaní na virtuálních klávesnicích je rychlejší. Posouváním tvaru slova, které zamýšlejí, zobrazíme náhled této funkce pro holografičovou klávesnici. Potažením prstem po jednom slově můžete procházet špičku prstu rovinou holografické klávesnice, potáhnutím tvaru slova a stažením špičky prstu z roviny klávesnice. Potažením prstem po sledu slov nepotřebujete stisknout mezerník odebráním prstu z klávesnice mezi slovy. Pokud vidíte potažení prstem za pohybem prstu na klávesnici, budete vědět, že tato funkce funguje.

Upozorňujeme, že použití a ovládání této funkce může být obtížné, protože se jedná o holografický klávesnici, u které nemáte pocit odolnosti proti prstu (na rozdíl od displeje mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka Napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní obrazovce HoloLens, který ukazuje, kdy je dostupná aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní HoloLens obrazovky pomocí [gesta Start nebo](hololens2-basic-usage.md#start-gesture) rčení "Přejít na start".

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

V tomto Windows buildu se  při výběru možnosti Jiný uživatel, který se nachází napravo od pole pro zadání KÓDU PIN, zobrazí obrazovka Přihlášení více uživatelů, kteří se k zařízení už přihlásili. To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlásit pomocí svých přihlašovacích Windows Hello uživatele. Nového uživatele můžete do zařízení přidat také z této stránky Ostatní uživatelé pomocí **tlačítka Přidat** účet.

V nabídce Ostatní uživatelé se na tlačítku Ostatní uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka – ostatní uživatelé](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externího mikrofonu USB-C

> [!IMPORTANT]
> Když zapojíte mikrofon USB, nenastaví **se automaticky jako vstupní zařízení.** Při zapojení sady konektorů USB-C uživatelé pozorují, že zvuk zařízení se automaticky přesměruje na konektory, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad libovolným jiným vstupním zařízením. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí panelu **nastavení** Zvuk. Mikrofony USB-C je možné použít k volání, nahrávání atd.

Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**

![Sound Nastavení](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace** znamená, že externí mikrofon se použije ve vzdáleném asistenci a dalších komunikačních aplikacích, ale pole mikrofonu HoloLens mikrofonu se stále může používat pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavení výchozího nastavení mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co Bluetooth mikrofonu?

V Bluetooth 2 se bohužel stále nepodporují HoloLens mikrofony.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a nikoli s HoloLens. při zapojení jednoho z těchto telefonů do HoloLens může dojít ke ztrátě zvuku. Naštěstí je jednoduchá oprava.  

v **Nastavení**  ->  **systémový**  ->  **zvuk** explicitně nastavte integrované reproduktory **(zvukový ovladač analogických funkcí)** jako **výchozí zařízení**. HoloLens by si toto nastavení měli pamatovat i v případě, že mikrofon odeberete a znovu připojíte později.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatické přihlašování návštěvníka pro veřejné terminály

Tato nová funkce umožňuje, aby se automatické přihlašování na účtech návštěvníka používalo pro beznabídkový režim.

V případě konfigurace bez AAD se má nakonfigurovat zařízení pro automatické přihlašování návštěvníka:

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje **nastavení modulu runtime/AssignedAccess** tak, aby umožňoval účty návštěvníků.
    1. Volitelně můžete zařízení zaregistrovat v MDM **(nastavení modulu runtime/pracoviště/registrace)** , aby se mohlo spravovat později.
    1. Nevytvářet místní účet
1. [Použijte zřizovací balíček](hololens-provisioning.md).

V případě konfigurace AAD můžou uživatelé v dnešní době dosáhnout něco podobného, aniž by tato změna měla. Zařízení připojená k AAD nakonfigurovaná pro celoobrazovkový režim se můžou přihlásit k účtu návštěvníka jediným klepnutím na tlačítko na přihlašovací obrazovce. Po přihlášení k účtu návštěvníka se zařízení nevyzve k opětovnému přihlášení, dokud se návštěvník výslovně odhlásí z nabídky Start nebo když se zařízení nerestartuje.

Automatické přihlašování návštěvníka se dá spravovat pomocí [vlastních zásad OMA-URI](/mem/intune/configuration/custom-settings-windows-10) :

- Hodnota identifikátoru URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automatické přihlašování k veřejnému terminálu.   | 1 (Ano), 0 (ne, výchozí)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>použití nových aplikací Nastavení a Edge v celoobrazovkovém režimu

Když do veřejného terminálu zahrnete i [aplikace, správce](hololens-kiosk.md)IT tuto aplikaci často přidá do veřejného terminálu, ale pomocí ID uživatelského modelu aplikace (AUMID). vzhledem k tomu, že aplikace Nastavení i aplikace Microsoft Edge jsou považovány za nové aplikace a jiné než veřejné terminály aplikací, které používají AUMIDs pro tyto aplikace, bude nutné aktualizovat, aby používaly nové AUMID.

Při úpravách veřejného terminálu, který bude obsahovat nové aplikace, doporučujeme přidat do nového AUMID a ponechat si ho starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou potřebovat dostávat nové zásady, aby mohli používat veřejný terminál jako zamýšlený.

| Aplikace                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| stará aplikace Nastavení       | HolographicSystemSettings_cw5n1h2txyewy! Aplikace            |
| nová aplikace Nastavení       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplikace |
| stará aplikace Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| nová aplikace Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování celoobrazovkového režimu pro zpracování selhání

Pokud se ve starších buildech zařízení nacházela konfigurace veřejného terminálu, což je kombinace obou uživatelů s přiřazeným přístupem a přiřazeným členem skupiny AAD, v případě neúspěšného určení členství ve skupině AAD by se uživateli zobrazila zpráva "[nic nezobrazuje" v nabídce Start](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures).

od tohoto Windows vydané verze se bude beznabídkový režim zaregistrovat do globální konfigurace veřejného terminálu (pokud je k dispozici) v případě selhání během celoobrazovkového režimu skupiny AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>nové identifikátory uri Nastavení pro viditelnost stránky Nastavení

v [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali [zásady Nastavení/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) , abyste omezili stránky, které jsou v aplikaci pro Nastavení viditelné. PageVisibilityList je zásada, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené.

pokud navštívíte [stránku Nastavení viditelnost](settings-uri-list.md), najdete pokyny k použití tohoto CSP a seznam identifikátorů uri dostupných v předchozích verzích.

rozšiřujeme seznam dostupných Nastavení identifikátorů uri, které můžou správci IT spravovat. některé z těchto identifikátorů uri jsou pro nově dostupné oblasti v rámci nové aplikace Nastavení. pokud používáte zásady Nastavení/PageVisibilityList, přečtěte si následující seznam a podle potřeby upravte své povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: MS-Settings: Network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Starší **Síťová & proxy stránka internetového**  >  **serveru** již není k dispozici jako globální nastavení. Nové nastavení proxy serveru pro připojení najdete v části **síť &**  >  vlastnosti **Wi-Fi** sítě Internet  >   nebo **síťové &** vlastnosti sítě Internet  >  **Ethernet**  >  .

<br>

| Stránka Nastavení                                        | Identifikátor URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplikace > aplikace & funkce                               | `ms-settings:appsfeatures`                         |
| Aplikace > aplikací & funkcí > pokročilé možnosti          | `ms-settings:appsfeatures-app`                     |
| Aplikace > Offlinech mapách                                  | `ms-settings:maps`                                 |
| Aplikace > offline mapování > stáhnout mapy                  | `ms-settings:maps-downloadmaps`                    |
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

nyní může uživatel v aplikaci Nastavení nakonfigurovat chování [záložní diagnostiky](hololens-diagnostic-logs.md). v aplikaci Nastavení přejděte na   ->  stránku **poradce při potížích** s nastavením ochrany osobních údajů, abyste mohli nakonfigurovat toto nastavení.

> [!NOTE]
> Pokud je pro zařízení nakonfigurovaná zásada MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí pomocí okolních zařízení

sdílejte věci s Windows 10 zařízení, včetně počítačů i dalších zařízení HoloLens 2. můžete si to vyzkoušet v **Nastavení**  ->    ->  **sdílených prostředích** , abyste mohli sdílet soubory nebo adresy url od HoloLens k počítači. Další podrobnosti najdete v tématu o tom, jak [sdílet věci s blízkými zařízeními v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tuto funkci je možné spravovat prostřednictvím [Možnosti připojení/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová trasování diagnostiky operačního systému

kromě předchozích poradců při potížích v aplikaci Nastavení byla přidána nová poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. přejděte na **Nastavení**  ->  **aktualizace &amp; zabezpečení**  >  **řešit**  >  **web Windows Update** a vyberte **spustit**. Díky tomu můžete shromažďovat trasování a při reprodukci problému s aktualizacemi operačního systému pomoct lépe při řešení problémů s vaším IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručování – náhled

pomocí této HoloLens aktualizace Windows Holographic for Business umožňuje nastavení optimalizace doručení snížit spotřebu šířky pásma pro stahování z více zařízení HoloLens. úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: [optimalizace doručení pro Windows 10 aktualizace](/windows/deployment/update/waas-delivery-optimization).

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

Několik upozornění na tuto nabídku Verze Preview:

- HoloLens verze Preview je omezená jenom na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v HoloLens zařízení nepodporují.
- HoloLens nepodporuje optimalizaci nasazení nebo doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování pro HoloLens v HoloLens prostřednictvím služby **Nastavení**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update.**

### <a name="it-admin---update-checklist"></a>Správce IT – kontrolní seznam aktualizací

Tento kontrolní seznam vám pomůže se seznamem nových položek přidaných v této aktualizaci funkcí, které můžou mít vliv na vaši aktuální konfiguraci správy zařízení nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace bezobrazovkového režimu

✔️ Nové [**identifikátory AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste dříve v beznaiosku Nastavení aplikaci Microsoft Edge, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové [aplikace v beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení v bezobrazovkovém okně, nebo zahrnout novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ [**automatického přihlášení návštěvníka pro bezobrazovkové režimy:**](#visitor-auto-logon-for-kiosks) 

Návštěvníci teď mohou být automaticky přihlášení do veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ [**vylepšené selhání bezobrazovkového režimu:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Pokud není členství přihlášených uživatelů AAD ve skupině AAD úspěšné, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o vašem oddělení podpory, pokud používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti Nastavení stránky

✔️ [**nové identifikátory URI Nastavení pro viditelnost Nastavení stránky**](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte viditelnost [Nastavení,](settings-uri-list.md) možná budete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC
✔️ Pokud jste dříve blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující a použijte poskytnutý vzorový kód.
#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge
✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ konfigurace [diagnostiky pro záložní prostředky:](#configuring-fallback-diagnostics-via-settings-app)Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

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

- Řeší problém, kdy Nastavení při pokusu o změnu hesla místního účtu dojde k chybě aplikace.


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
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM z HoloLens zařízení

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

Přidáváme **novou funkci (Instalační program aplikací),** která vám umožní hladceji instalovat aplikace na zařízení s HoloLens 2. Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.** Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:
- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní aplikace [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) MDM, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens před nasazením aplikace důvěryhodný.

**Pokyny k instalaci aplikace.**

1.  Ujistěte se, že se vaše zařízení nepovažuje za spravované.
1.  Ujistěte se, že HoloLens 2 je zapnuté a připojené k počítači.
1.  Ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1.  Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní Storage\Soubory ke stažení.   Po dokončení kopírování souboru můžete zařízení odpojit.
1.  Na svém HoloLens 2 Otevřete nabídku Start, vyberte Všechny aplikace a spusťte Průzkumník souborů aplikaci.
1.  Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat Toto zařízení a pak přejít na Položky ke stažení.
1.  Vyberte soubor yourapp.appxbundle.
1.  Spustí Instalační program aplikací. Vyberte tlačítko Install (Nainstalovat) a nainstalujte aplikaci.
Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

Ukázkové aplikace najdete na Windows [univerzálních GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) a tento tok otestujte.

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí Instalační program aplikací](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací](images/hololens-app-installer-picture.jpg)

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

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční vydání verze 2004 (build 19041). Na číslo sestavení se můžete podívat na obrazovce Nastavení > Informace a potvrdit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete aktualizovat na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

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

V HoloLens 2 umožňují pozice očí přesné umístění hologramu, pohodlné zobrazení a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**Funkce Auto Eye Position (AEP)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel zařízení spustí. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová, a proto se tento proces opakuje, když uživatel odstartuje a zařízení znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasádá nezabý uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu se nekalibrovaný uživatel odkazuje na někoho, kdo předtím neprošlý procesem kalibrace sledování očí na zařízení.

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

-   **Auditování:** Možnost ověřit, jestli je certifikát správně nasazený, nebo ověřit, že se certifikát odebral správně. 
-   **Diagnostika:** V případě problémů se ověří, že na zařízení existují vhodné certifikáty, které šetří čas a pomáhají při řešení problémů. 
-   **Ověření:** Ověření, že certifikát slouží k zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Chcete-li v seznamu rychle najít konkrétní certifikát, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé můžou taky certifikát vyhledat přímo. Chcete-li zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na tlačítko **informace**. 

Instalace certifikátu v současné době podporuje soubory. cer a. CRT. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  všechny ostatní uživatele lze instalovat pouze do aktuálního uživatele. uživatelé můžou odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.

#### <a name="to-install-a-certificate"></a>Instalace certifikátu: 

1.  Připojení HoloLens 2 k počítači.
1.  soubor certifikátu, který chcete nainstalovat, umístěte do umístění na vašem HoloLens 2.
1.  přejděte na **Nastavení > aktualizace & > certifikátů zabezpečení** a vyberte nainstalovat certifikát.
1.  Klikněte na **importovat soubor** a přejděte do umístění, kam jste certifikát uložili.
1.  Vyberte **umístění úložiště**.
1.  Vyberte **úložiště certifikátů**.
1.  Klikněte na **Install** (Nainstalovat).

Certifikát by se teď měl nainstalovat na zařízení.

#### <a name="to-remove-a-certificate"></a>Odebrání certifikátu: 
1. přejděte na **Nastavení App > aktualizace a > certifikáty zabezpečení**.
1. Ve vyhledávacím poli vyhledejte certifikát podle názvu.
1. Vyberte certifikát.
1. Klikněte na **Odebrat** .
1. Po zobrazení výzvy k potvrzení vyberte **Ano** .

![prohlížeč certifikátů v aplikaci Nastavení](images/certificate-viewer-device.jpg)

![Obrázek ukazující použití uživatelského rozhraní certifikátu k instalaci certifikátu](images/certificate-device-install.jpg)

Tyto informace se dají najít později [na nové stránce Správce certifikátů](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňují menší interakci s uživatelem, když se při počátečním spuštění počítače použijí jednotky USB s Zřizovacími balíčky.

Předtím, než uživatelé této verze museli při zřizování pomocí kombinace tlačítek znovu spustit zřizování obrazovky během vytváření POČÁTEČNÍch hodnot. Uživatelé teď můžou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na USB paměťové jednotce. 

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

po připojení HoloLens 2 k síti Wi-Fi teď při spuštění nástroje oobe zkontroluje profil automatického pilotního nasazení pro zařízení. Pokud se najde, použije se k dokončení připojení AAD a toku registrace. Jinými slovy, použití sítě Ethernet pro USB-C nebo Wi-Fi do adaptéru USB-C ještě není požadavkem, ale budou fungovat i v případě, že jsou k dispozici na začátku počátečního nastavení. přečtěte si další informace o [autopilotu pro zařízení HoloLens 2](hololens2-autopilot.md).

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
   > ![Nastavení uzamčení klienta pomocí OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení nastavení TenantLockdown RequireNetworkInOOBE HoloLens 2? 
1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše. 

1. Vytvořte vlastní konfigurační profil zařízení založený na OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže. Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený v HoloLens po nastavení tenantaLockdown na hodnotu true? 
OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown. 

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

Tyto informace teď najdete společně se zbytkem Autopilotu v části [Tenantlockdown CSP a Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim
- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije režim veřejného terminálu.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Podrobné informace o této nové funkci najdete v HoloLens veřejného terminálu s [globálním přiřazeným přístupem.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatické spuštění aplikace v bezobrazovkovém režimu s více aplikacemi 
- Cílené prostředí s automatickým spouštěním aplikací, které dále zvyšuje výběr uživatelského rozhraní a aplikací zvolených pro prostředí v bezobrazovkovém režimu.

Platí jenom pro beznarový režim s více aplikacemi a jenom 1 aplikaci je možné pomocí zvýrazněných atributů níže v konfiguraci Přiřazený přístup určená k automatickému spuštění. 

Aplikace se automaticky spustí při přihlášení uživatele. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování v bezobrazovkovém režimu pro zpracování selhání
- Bezpečnější bezobrazovkové režimy eliminují selhání dostupných aplikací v bezobrazovkovém režimu. 

Dříve v případě selhání při použití bezobrazovkovém režimu se HoloLens k zobrazení všech aplikací v nabídce Start. Nyní Windows Holographic verze 20H2 v případě selhání se v nabídce Start nezobrazí žádné aplikace, jak je znázorněno níže: 

![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politiky
- Možnosti správy zařízení speciálně pro HoloLens pro správu zařízení. 

Nové zásady hybridní reality byly vytvořeny pro HoloLens 2 zařízení na Windows Holographic verze 20H2. Mezi nová říditelná nastavení patří nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v záznamech hybridní reality, nastavení, kdy je možné shromažďovat diagnostiku, a mezipaměť členství ve skupinách AAD.  

| Nové HoloLens zásad                                | Description                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Umožňuje zakázat tlačítka jasu, takže se jeho stisknutí nezmění na brightness.       | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Umožňuje zakázat tlačítka hlasitosti, aby se po stisknutí tlačítka neměňte svazek.               | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | Zakáže mikrofon, takže na počítači s HoloLens 2 není možný žádný zvukový záznam.                      | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\FallbackDiagnostics                   | Řídí chování, kdy je možné shromažďovat diagnostické protokoly.                               | 0 Zakázáno, 1 Povoleno pro vlastníky zařízení, 2 Povoleno pro všechny (výchozí) |
| MixedReality\HeadTrackingMode                      | Vyhrazeno pro budoucí použití.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Určuje, kolik dní se mezipaměť členství ve skupinách Azure AD používá pro bezobrazovkové režimy cílené na skupiny Azure AD. | Viz níže.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy
- Povolili jste použití offline terminálů se skupinami AAD po dobu až 60 dnů.

Tato zásada určuje, kolik dní může být mezipaměť členství ve skupinách Azure AD použita pro konfigurace přiřazeného přístupu, které cílí na skupiny Azure AD pro přihlášené uživatele. Jakmile je hodnota této zásady nastavená na hodnotu větší než 0, použije se mezipaměť, jinak se tato hodnota nenastaví.  

Název: AADGroupMembershipCacheValidityInDays Hodnota identifikátoru URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dní  
Max. – 60 dnů 

Postup správných použití těchto zásad: 
1. Vytvořte profil konfigurace zařízení pro beznaiosk cílení na skupiny Azure AD a přiřaďte ho HoloLens zařízením. 
1. Vytvořte vlastní konfiguraci zařízení založenou na OMA URI, která nastaví tuto hodnotu zásady na požadovaný počet dní (> 0) a přiřadí ji HoloLens zařízením. 
    1. Do textového pole OMA-URI by se měla zadat hodnota URI ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays.
    1. Hodnota může být v rozmezí od minimálního do maximálního povoleného.
1. Zaregistrujte HoloLens zařízení a ověřte, že se na zařízení použijí obě konfigurace. 
1. Nechte uživatele Azure AD 1 přihlásit se, když je k dispozici internet, po úspěšném potvrzení přihlášení uživatele a úspěšného členství ve skupině Azure AD se vytvoří mezipaměť. 
1. Uživatel Azure AD 1 teď může HoloLens režim offline a použít ho pro bezioskový režim, pokud hodnota zásad umožňuje počet dní X. 
1. Kroky 4 a 5 je možné opakovat pro libovolného jiného uživatele Azure AD N. Klíčovým bodem je, že každý uživatel Azure AD se musí přihlásit k zařízení pomocí internetu, takže aspoň jednou můžeme určit, že jsou členem skupiny Azure AD, na kterou je cílem konfigurace veřejného terminálu. 
 
> [!NOTE]
> Dokud se pro uživatele Azure AD neprovádí krok 4, bude docházet k chování při selhání uvedeném v odpojených prostředích. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nové zásady omezení zařízení pro HoloLens 2
- Umožňuje uživatelům spravovat konkrétní zásady správy zařízení, jako je blokování přidávání nebo odebírání zřizových balíčků.

Nově povolené zásady, které umožňují více možností správy HoloLens 2 zařízení. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [Vzdálené zamykací zařízení](/windows/client-management/mdm/remotelock-csp)

Tyto dvě nové zásad pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Pokud jde o [RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens podporuje jenom konfiguraci ./Vendor/MSFT/RemoteLock/Lock. Konfigurace týkající se kódu PIN, jako je resetování a obnovení, se nepodporují.

### <a name="new-power-policies-for-hololens-2"></a>Nové zásady napájení pro HoloLens 2
- Další možnosti pro HoloLens režimu spánku nebo uzamčení prostřednictvím zásad napájení. 

Tyto nově přidané zásady umožňují správcům řídit stavy napájení, jako je časový limit nečinnosti. Další informace o jednotlivých zásadách si můžete přečíst kliknutím na odkaz pro jednotlivé zásady.

|     Odkaz na dokumentaci k zásadám                |     Poznámky                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Příklad hodnoty, která se má Windows Návrháři konfigurace, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Příklad hodnoty, která se má Windows Návrháři konfigurace, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové služby pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> pro konzistentní prostředí HoloLens 2 prosím zajistěte, aby byly hodnoty pro obě DisplayOffTimeoutOnBattery a StandbyTimeoutOnBattery nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti o moderním pohotovostním režimu najdete v tématu o [časovačích nečinných pro zobrazení, přechod do režimu spánku a hibernace](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### <a name="newly-enabled-update-policies-for-hololens"></a>Nově povolené zásady aktualizace pro HoloLens
- Další možnosti pro instalaci aktualizací nebo zakázání tlačítka pozastavit aktualizace, aby se zajistila aktualizace.

v zařízeních HoloLens 2 jsou teď povolené tyto zásady aktualizace:
-   [Aktualizovat/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Aktualizovat/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Aktualizovat/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Aktualizovat/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

úplné podrobnosti o těchto zásadách aktualizace a jejich použití pro HoloLens zařízení je možné číst v tématu [správa aktualizací HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>povolená Nastavení viditelnost stránky pro HoloLens 2
- vylepšené řízení uživatelského rozhraní v aplikaci Nastavení, které může být zaměňováno k zobrazení omezeného výběru stránek.

nyní jsme povolili zásadu, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené. Informace o tom, jak tuto funkci plně přizpůsobit, získáte kliknutím na odkaz níže.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

pokud chcete zjistit, která nastavení stránky můžete přizpůsobit HoloLens 2, navštivte prosím naši [Nastavení na stránce identifikátory uri](settings-uri-list.md). 
 
![snímek obrazovky s aktivními hodinami upravovanými v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu
v rámci výzkumného režimu se HoloLens 2 stal nástrojem potent pro výzkum počítačových visionů. v porovnání s předchozími edicemi má výzkumný režim pro HoloLens 2 následující výhody:
-   kromě senzorů vystavených v HoloLens (1.1. generace) průzkumu teď poskytujeme přístup ke senzorům IMU, včetně měřičů akcelerometr, vybavený gyroskopem a magnetometer.
-   HoloLens 2 poskytuje nové funkce, které se dají použít společně s výzkumným režimem. Konkrétně přístup k rozhraním API pro sledování kloubů a sledování očí, který může poskytovat bohatší sadu experimentů.

výzkumníki teď mají možnost povolit výzkumný režim na svých zařízeních HoloLens pro přístup ke všem těmto externím proudům s nezpracovanými obrazci. výzkumný režim pro HoloLens 2 také poskytuje přístup ke čtení akcelerometr, vybavený gyroskopem a magnetometer. V zájmu ochrany osobních údajů uživatelů nejsou k dispozici obrázky z nezpracovaného oka pro sledování očí prostřednictvím výzkumného režimu, ale směr pohledu je k dispozici prostřednictvím existujících rozhraní API.

Další technické podrobnosti najdete v [dokumentaci ke výzkumnému režimu](/windows/mixed-reality/research-mode) .

### <a name="recording-length-increased"></a>Zvýšení délky záznamu
Z důvodu zpětné vazby od zákazníků jsme zvýšili délku nahrávání u [hybridních zachycení realit](holographic-photos-and-videos.md). Ve výchozím nastavení se hybridní zachycení realit nebudou standardně omezovat na 5 minut, ale místo toho se vypočítá maximální délka nahrávání na základě dostupného místa na disku. Zařízení bude odhadnout maximální dobu trvání nahrávání videa na základě dostupného místa na disku až do 80% celkového místa na disku.

> [!NOTE]
> HoloLens použije výchozí délku nahrávání videa (5 minut), pokud dojde k jedné z následujících akcí:
> - Odhadovaná maximální doba trvání záznamu je menší než výchozí hodnota 5 minut.
> - Dostupné místo na disku je méně než 20% celkového místa na disku.

Plné požadavky najdete v dokumentaci k [holografickým fotografiím a videím](holographic-photos-and-videos.md#maximum-recording-length) . 

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:
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
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která se nezdařila kvůli selhání detekce Internetu prostřednictvím síťového proxy serveru. NCSI může k detekci připojení k Internetu použít proxy server a proxy server pro jednotlivé profily. Proxy server bude v budoucích verzích NCSI podporován pro každého uživatele.
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
2. Sestavte konfigurační profil. Pak zkopírujte všechny soubory, které byly vytvořeny na paměťové zařízení USB-C.
3. Připojte zařízení USB-C k jakémukoli čerstvě blikajícímu HoloLens. Potom stisknutím tlačítka **hlasitosti dolů**  +   použijte balíček zřizování.

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
