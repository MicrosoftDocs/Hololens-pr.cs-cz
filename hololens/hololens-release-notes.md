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
ms.date: 9/8/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f27a469e76df1ccf29a2823b48f3640bdf414050
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427310"
---
# <a name="hololens-2-release-notes"></a>poznámky k verzi HoloLens 2

abychom se ujistili, že máte k dispozici produktivní prostředí s HoloLensmi zařízeními, budeme pořád vydávat aktualizace zabezpečení a funkce, chyby a zabezpečení. na této stránce uvidíte, co je nového pro HoloLens každý měsíc. pokud chcete získat nejnovější aktualizaci HoloLens 2, můžete buď [vyhledat aktualizace, a ručně aktualizovat](hololens-update-hololens.md#check-for-updates-and-manually-update) nebo získat úplnou aktualizaci flash (FFU), která [vám umožní flash zařízení pomocí pokročilého průvodce obnovením](hololens-recovery.md#clean-reflash-the-device). [Stažení](https://aka.ms/hololens2download) je udržováno v aktuálním stavu a poskytuje nejnovější všeobecně dostupné sestavení.

> [!NOTE]
> nedávné oznámení Windows 11 se zaměřuje na verzi Windows počítače. nedávno jsme spustili [hlavní aktualizaci operačního systému](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) HoloLens 2 v květnu 2021 a pracujeme na nadcházející verzi na základě zpětné vazby od zákazníků.

> [!IMPORTANT]
> v důsledku nově vyřešeného [známého problému v našem buildu 21H1, který má vliv na uživatele vzdálené pomoci](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes), jsme dočasně pozastavili nabídku Windowsch holografických aktualizací verze 21H1. také jsme změnili výchozí sestavení průvodce rozšířeným obnovením (ARC) na [Windows holografické verze 20H2 – červen 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Sestavení ARC teď obnoví cílení na sestavení 21H1.

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
- opraven problém, kdy Wi-Fi proxy server nelze uložit při spuštění Wi-Fi vlastností uživatelského rozhraní z **Nastavení-> síťové & > stav-> vlastnosti**.
- Vyřešili jsme problém s odebráním certifikátů eSIM napříč aktualizacemi operačního systému. Tato oprava zajistí, že se při aktualizaci verze 21H1 odebraly certifikáty eSIM a související součásti.
- Opravili jsme problém ovlivněný předinstalovanými aplikacemi v rámci resetování operačního systému.
- Zvýšení výkonu při nabíjení baterie za účelem zvýšení modulu runtime při zpoplatnění zvýšeného zatížení procesoru. při nastavování zařízení HoloLens 2, pokud se zjistilo, že se zařízení bude používat horká, bude interní baterie pomaleji, aby se snížila energie. Kladné kompromisy jsou v tom, že zařízení je méně pravděpodobně vypíná kvůli tepelným problémům, což má vliv na to, že zařízení běží delší dobu. Pokud je zařízení spuštěné, neovlivní se vám poplatky za přenos.

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
- [Příručky k Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

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
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit, že ostatní okna 2D aplikací neočekávaně prochádí. Tato okna můžete znovu aktivovat opětovnou interakcí.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

Tým Microsoft Edge má komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat víc verzí najednou. 

Další informace [o komunitě Edge Insider najdete](https://www.microsoftedgeinsider.com) na domovské stránce Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce pro [stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider Microsoft Edge několik metod, které HoloLens 2:

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

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blokování nových účtů pomocí nástroje WDAC Microsoft Edge

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

Součástí nového Microsoft Edge je podpora WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Mnoho imerzivních webových prostředí bylo navrženo s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale tato prostředí podporuje také HoloLens 2. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že nová imerzivní prostředí rozšířené reality a hybridní reality budou k dispozici HoloLens 2 zákazníci to budou zkoušet!

Rozšíření 360 Viewer je postaveno na aplikaci WebXR a automaticky se nainstaluje společně s novým Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

#### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu **vyberte tlačítko Enter VR** (Zadat virtuální realitu). Umístění a vizuální znázornění tohoto tlačítka se může u jednotlivých webových stránek lišit, ale může vypadat podobně jako:

    ![Zadejte příklad tlačítka VR.](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění prostředí WebXR v konkrétní doméně prohlížeč požádá o souhlas se zadáním imerzivního zobrazení a vybere **Povolit.**
1. K [HoloLens prostředí použijte 2 gesta.](hololens2-basic-usage.md#the-hand-tracking-frame)
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
1. [Klepnutím ve vzduchu](hololens2-basic-usage.md#select-using-air-tap) vysunutím ovládacích prvků přehrávání Pomocí [ručních paprsků](hololens2-basic-usage.md#select-using-air-tap) a klepnutí ve vzduchu můžete přehrát/pozastavit, přeskočit vpřed/zpět, zapnout nebo vypnout titulky nebo ukončit prostředí (tím se ukončí imerzivní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Hlavní známé problémy s WebXR a 360 Viewerem
- V závislosti na složitosti prostředí WebXR může snímková frekvence poklesat nebo se zhoršit.
- Podpora pro articulated handu v WebXR není ve výchozím nastavení povolená. Vývojáři mohou podporu povolit `edge://flags` zapnutím funkce "Ruční vstup WebXR".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby k WebXR a prohlížeči 360

Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce **Poslat** zpětnou vazbu v novém Microsoft Edge.

### <a name="new-settings-app"></a>Nová Nastavení aplikace

V této verzi představujeme novou verzi aplikace Nastavení. Nová aplikace Nastavení obsahuje nové funkce a rozšířená nastavení pro HoloLens 2 v následujících oblastech: Zvuk, Power & režim spánku, Síť & Internet, Aplikace, Účty, Usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, Nastavení se nová aplikace Nastavení liší od starší verze aplikace Nastavení, budou při aktualizaci odebrána jakákoli okna Nastavení, která jste předtím umístili kolem svého prostředí.

![Domovská Nastavení nové aplikace](images/new-settings-app.png)

**Nové funkce a nastavení**
- Nastavení: Na domovské stránce Nastavení pomocí klíčových slov nebo názvu nastavení vyhledejte nastavení.
- System > Sound:
  - Vstupní a výstupní zvuková zařízení: Nezávisle zvolte vstupní a výstupní zvuková zařízení (například naslouchejte zvuku prostřednictvím Bluetooth nebo použijte mikrofon USB-C pro zvukový vstup).
    > [!NOTE]
    > Bluetooth 2 nepodporuje HoloLens mikrofony.
  - Objem aplikace: Nezávisle upravte objem každé aplikace. Viz [řízení objemu na aplikaci.](#per-app-volume-control)
- System > Power & režim spánku: Zvolte, kdy má zařízení po určité době nečinnosti přejít do režimu spánku.
- Baterie >: Ručně povolte spořič baterie režimu nebo nastavte prahovou hodnotu baterie, po spořič baterie režim automaticky zapne.
- Zařízení > USB: Ve výchozím nastavení můžete zakázat připojení USB.
- Network & Internet:
  - Ethernetové adaptéry USB-C se teď zobrazí v části Síťová & internetu.
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



Pomocí tohoto nového nastavení můžete vybrat alternativní profil barev pro váš HoloLens 2. Barvy se tak můžou zdát přesnější, zejména při nižších úrovních jasu zobrazení. Barevné závislosti můžete zobrazit v aplikaci Nastavení, a to na stránce System > Aplikace.

> [!NOTE]
> Vzhledem k tomu, že toto nastavení ukládá nový profil barev do firmwaru zobrazení, jedná se o nastavení pro jednotlivá zařízení (a není jedinečné pro každý uživatelský účet).

##### <a name="how-to-use-display-color-calibration"></a>Jak používat barvu zobrazení

1. Spusťte aplikaci **Nastavení** a přejděte na **System > ádou.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Run display color **uchovat.**
1. Spustí se prostředí zobrazení barev a budete se muset ujistit, že je zorník ve správné pozici.
1. Po pokračování v dialogových oknech s pokyny se vaše zobrazení automaticky ztmaní na 30% jas.
    > [!TIP]
    > Pokud máte potíže se zobrazením tlumené scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek brightness na levé straně zařízení.
1. Výběrem tlačítek 1–6 můžete okamžitě vyzkoušet každý profil barev a najít ten, který vám vypadá nejlépe do očí (obvykle to znamená profil, který pomáhá scéně zdát se nejneužívnější, se vzorem stupňů šedé a barevnými odstíny, které vypadají podle očekávání).)

    ![Zobrazení scény barevného pozadí](images/color-cal-ui.png)
    
1. Až budete s vybraným profilem spokojeni, vyberte tlačítko **Save & Exit (Uložit** a ukončit).
1. Pokud nechcete provádět změny, vyberte tlačítko **Zrušit & Ukončit** a změny se vrátí zpět.

> [!TIP]
> Tady je několik užitečných tipů, které je dobré mít na paměti při používání nastavení barev zobrazení:
> - Kdykoli budete chtít, můžete znovu spustit barevné Nastavení zobrazení.
> - Pokud někdo v zařízení dříve použil nastavení ke změně profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte barevné zvýraznění zobrazení, profil barev, který byl dříve uložen, se zvýrazní a profil 0 se nezobrazí (protože Profil 0 představuje původní profil barvy zobrazení).
> - Pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to udělat na stránce Nastavení (viz resetování profilu [barev).](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Resetování profilu barev 

Pokud s vlastním profilem barev uloženým v počítači HoloLens 2 nejste spokojeni, můžete původní profil barev zařízení obnovit:
1. Spusťte aplikaci **Nastavení** a přejděte na **System > ádou.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Obnovit výchozí **profil** barev.
1. Po otevření dialogového okna vyberte **Restartovat,** pokud jste připraveni restartovat počítač HoloLens 2 a použít změny.

#### <a name="top-display-color-calibration-known-issues"></a>Známé problémy s nejvyšším zobrazováním barev

- Na stránce Nastavení bude stavový řetězec, který vás informuje o tom, kdy byl profil barev naposledy změněn, neaktuální, dokud znovu nenačtete tuto stránku Nastavení.
    - Alternativní řešení: Vyberte Nastavení stránku a pak znovu vyberte stránku Uchovat.

#### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když aktivujete hypertextový odkaz nebo otevřete typ souboru s více nainstalovanými aplikacemi, která ho podporuje, zobrazí se nové okno s výzvou k výběru nainstalované aplikace, která by měla typ souboru nebo odkazu zpracovat. V tomto okně se také můžete rozhodnout, že vybraná aplikace zřídí soubor nebo typ odkazu "Jednou" nebo "Vždy".

Pokud zvolíte Možnost Vždy, ale později chcete změnit, která aplikace zpracovává konkrétní soubor nebo typ odkazu, můžete uložené výchozí hodnoty resetovat v Nastavení > **Apps**. Posuňte se do dolní části stránky a vyberte tlačítko **Vymazat** v části Výchozí aplikace pro typy souborů a/nebo Výchozí aplikace pro typy odkazů. Na rozdíl od podobného nastavení na stolních počítačích nemůžete resetovat výchozí nastavení jednotlivých typů souborů.

#### <a name="per-app-volume-control"></a>Řízení objemu na aplikaci

V této Windows sestavě mohou uživatelé ručně upravit úroveň svazku každé aplikace. Díky tomu se uživatelé mohou lépe soustředit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například když potřebujete vypnout objem jedné aplikace a volat jinou osobu kvůli vzdálené pomoci v jiné.

Pokud chcete nastavit svazek jednotlivé aplikace, přejděte **na Nastavení** Zvuk systému a v části Pokročilé možnosti zvuku vyberte Svazek aplikace a  ->    ->   **předvolby zařízení.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potažením prstem zadejte

Někteří zákazníci zjistí, že psaní na virtuálních klávesnicích je rychlejší. Posouváním tvaru slova, které mají v úmyslu zadat, a my tuto funkci zobrazíme ve verzi Preview pro holografičovou klávesnici. Potažením prstem po jednom slově můžete procházet špičku prstu rovinou holografické klávesnice, potáhnutím tvaru slova a stažením špičky prstu z roviny klávesnice. Potažením prstem po sledu slov nepotřebujete stisknout mezerník odebráním prstu z klávesnice mezi slovy. Funkce funguje, když potažením prstem na klávesnici vidíte potažení prstem.

Upozorňujeme, že použití a ovládání této funkce může být obtížné, protože se jedná o holografický klávesnici, u které nemáte pocit odolnosti proti prstu (na rozdíl od displeje mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka Napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní obrazovce HoloLens, který ukazuje, kdy je dostupná aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní HoloLens obrazovky pomocí gesta [Start nebo](hololens2-basic-usage.md#start-gesture) rčení "Přejít na začátek".

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

V tomto Windows buildu se  při výběru možnosti Jiný uživatel, který se nachází napravo od pole pro zadání KÓDU PIN, na přihlašovací obrazovce zobrazí několik uživatelů, kteří se k zařízení už přihlásili. To uživatelům umožňuje vybrat svůj profil uživatele a pak se přihlásit pomocí svých přihlašovacích Windows Hello uživatele. Nového uživatele můžete do zařízení přidat také z této stránky Ostatní uživatelé pomocí **tlačítka Přidat** účet.

V nabídce Ostatní uživatelé se na tlačítku Ostatní uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka.](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiných uživatelů.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externího mikrofonu USB-C

> [!IMPORTANT]
> Když zapojíte mikrofon USB, nenastaví **se automaticky jako vstupní zařízení.** Při připojování k sadě konektorů USB-C uživatelé sledují, že zvuk zařízení se automaticky přesměruje na konektory, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad libovolným jiným vstupním zařízením. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí panelu **nastavení** Zvuk. Mikrofony USB-C je možné použít k volání, nahrávání atd.

Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**

![Zvuk Nastavení.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace** znamená, že se externí mikrofon použije ve vzdáleném asistenci a v jiných komunikačních aplikacích, ale pole HoloLens mikrofonu se může používat i pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavte výchozí mikrofon.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co podpora Bluetooth mikrofonu?

V Bluetooth 2 se bohužel stále nepodporují HoloLens mikrofony.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound explicitně nastavte vestavěné mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.** HoloLens si toto nastavení zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatické přihlášení návštěvníka pro bezobrazovkové režimy

Tato nová funkce umožňuje použití automatického přihlašování k účtům Návštěvník v bezobrazovkovém režimu.

Konfigurace bez AAD pro konfiguraci zařízení pro automatické přihlášení návštěvníka:

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje **nastavení modulu runtime /AssignedAccess tak,** aby povolují účty návštěvníka.
    1. Volitelně zaregistruje zařízení v MDM (nastavení modulu **runtime, pracoviště/ registrace),** aby ho bylo možné později spravovat.
    1. Nevytvářejte místní účet.
1. [Použijte zřizovací balíček](hololens-provisioning.md).

V případě konfigurace AAD mohou uživatelé bez této změny dosáhnout něčeho podobného. Zařízení připojená k AAD nakonfigurovaná pro beznarový režim mohou přihlásit účet Návštěvník jediným klepnutím na přihlašovací obrazovku. Jakmile se zařízení přihlásí k účtu návštěvníka, nebude znova vyzváno k přihlášení, dokud se návštěvník z nabídky Start explicitně odhlásit nebo dokud se zařízení nerestartuje.

Automatické přihlášení návštěvníka je možné spravovat [pomocí vlastních zásad OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Hodnota URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automaticky se přihlásit k bezobrazovkovému režimu.   | 1 (Ano), 0 (Ne, výchozí.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových aplikací Nastavení a Edge v režimech veřejného terminálů

Při zahrnutí aplikací do [veřejného terminálu](hololens-kiosk.md)správce IT často přidá aplikaci do veřejného terminálu, ale použije JI AUMID (App User Model ID). Vzhledem k tomu, že se aplikace Nastavení i aplikace Microsoft Edge považují za nové aplikace a liší se od starších aplikací, které pro tyto aplikace používají identifikátory AUMID, bude potřeba aktualizovat, aby bylo možné používat nové AUMID.

Při úpravách veřejného terminálů tak, aby zahrnoval nové aplikace, doporučujeme přidat nový AUMID a nechat starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou muset přijímat nové zásady, aby mohli dál používat beziosk, jak má.

| Aplikace                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stará Nastavení aplikace       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nová Nastavení aplikace       | BAEAEF15-9BE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Stará Microsoft Edge aplikace | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nová Microsoft Edge aplikace | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování v bezobrazovkovém režimu pro zpracování selhání

Pokud má zařízení ve starších buildech konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálním i přiřazeným členem skupiny AAD, pokud by se nepodařilo určit členství ve skupině AAD, uživateli se v nabídce[Start](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)nezobrazí nic.

Od této Windows se prostředí veřejného terminálu v případě selhání v beznaiosku skupiny AAD propadne ke globální konfiguraci veřejného terminálu (pokud je k dispozici).

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nové Nastavení URI pro viditelnost Nastavení stránky

V Windows Holographic verze [20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali zásadu [Nastavení/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) která omezuje stránky, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci System Nastavení, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

Pokud navštívíte [stránku s Nastavení viditelnosti,](settings-uri-list.md)najdete pokyny k použití tohoto poskytovatele CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšiřujeme seznam dostupných identifikátorů URI, Nastavení mohou spravovat správci IT. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové Nastavení aplikace. Pokud používáte zásady Nastavení/PageVisibilityList, zkontrolujte následující seznam a podle potřeby upravte povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: ms-settings:network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Stará stránka **&**  >  **internetového proxy** serveru už není dostupná jako globální nastavení. Nové nastavení proxy serveru pro připojení najdete v části **Vlastnosti internetového &** sítě  >  **Wi-Fi** nebo Vlastnosti  >   **internetového**&  >  **sítě Ethernet.**  >  

<br>

| Stránka Nastavení                                        | Identifikátor URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplikace > Apps & funkce                               | `ms-settings:appsfeatures`                         |
| Funkce > Apps & > Upřesnit možnosti          | `ms-settings:appsfeatures-app`                     |
| Aplikace > offline mapy                                  | `ms-settings:maps`                                 |
| Aplikace > offline mapy > stažení map                  | `ms-settings:maps-downloadmaps`                    |
| Zařízení > myši                                      | `ms-settings:mouse`                                |
| Zařízení > USB                                        | `ms-settings:usb`                                  |
| Režim & v > v internetovém režimu                   | `ms-settings:network-airplanemode`                 |
| Zásady > ochrany osobních údajů                                    | `ms-settings:privacy-general`                      |
| Ochrana > osobních & při psaní přizpůsobení             | `ms-settings:privacy-speechtyping`                 |
| Ochrana osobních > pohybu                                     | `ms-settings:privacy-motion`                       |
| Ochrana osobních > Snímek obrazovky s ohraničením                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Ochrana osobních > Snímky obrazovky a aplikace                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Systémová > baterie                                     | `ms-settings:batterysaver`                         |
| Systémová > baterie                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| Nastavení > pro > a předvolby zařízení v aplikaci System > | `ms-settings:apps-volume`                          |
| System > Sound > Správa zvukových zařízení              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Datum & čas > časového &                        | `ms-settings:dateandtime`                          |
| Klávesnice & jazyka Time >                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizace & obnovení > obnovení & zabezpečení               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualizované identifikátory URI

Dříve by následující dvě identifikátory URI nesly uživatele přímo na uvedené stránky, ale zablokovaly jenom hlavní stránku aktualizací. Následující položky byly aktualizovány tak, aby směrovat na jejich stránky:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurace záložní diagnostiky prostřednictvím Nastavení aplikace

Teď, Nastavení aplikaci, může uživatel nakonfigurovat chování diagnostiky [pro fallback.](hololens-diagnostic-logs.md) Na stránce Nastavení přejděte na stránku Řešení **potíží** s ochranou  ->  **osobních** údajů a nakonfigurujte toto nastavení.

> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí s blízkými zařízeními

Sdílejte věci s ostatními Windows 10 zařízeními, včetně počítačů a dalších zařízení HoloLens 2. Můžete si to vyzkoušet v **prostředích Nastavení** systému a sdílet soubory nebo adresy URL z  ->    ->   HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s blízkými zařízeními [v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tuto funkci je možné spravovat prostřednictvím [možnosti Připojení/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová diagnostická trasování operačního systému

Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte na **Nastavení**  ->  **Update Security &amp; Windows**  >    >  **Update a** vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.

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
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování v HoloLens v HoloLens prostřednictvím Nastavení  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – kontrolní seznam aktualizací

Tento kontrolní seznam vám pomůže se seznamem nových položek přidaných v této aktualizaci funkcí, které můžou mít vliv na aktuální konfiguraci správy zařízení nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace do bezobrazovkovém režimu

✔️ [**nové AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste dříve v beznaiosku Nastavení aplikaci Microsoft Edge, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové aplikace v [beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení v bezobrazovkovém okně, nebo zahrnout novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ [**automatického přihlášení návštěvníka pro bezobrazovkové režimy:**](#visitor-auto-logon-for-kiosks) 

Návštěvníci teď mohou být automaticky přihlášení do veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ [**vylepšené selhání bezobrazovkového režimu:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Pokud není členství přihlášených uživatelů AAD ve skupině AAD úspěšné, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o vašem oddělení podpory, pokud používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti Nastavení stránky

✔️ nové [**identifikátory URI Nastavení pro viditelnost Nastavení stránky**](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte viditelnost [Nastavení,](settings-uri-list.md) možná budete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC
✔️ Pokud jste dříve blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující informace a použijte poskytnutý vzorový kód.
#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge
✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ konfigurace [diagnostiky pro záložní](#configuring-fallback-diagnostics-via-settings-app)prostředky: Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

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

- Zákazníci, kteří k pořizování fotek pomocí HoloLens 2 používají AdvancedPhotoCapture nebo LowLagPhotoCapture, teď 3 sekundy po zachycení fotky mohou načíst pozici fotoaparátu.
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

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo ze strany pomocí funkce nasazení obchodní aplikace [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) MDM, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens před nasazením aplikace důvěryhodný.

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

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování rukou teď udržuje sledování v mnoha nových případech, kdy by se dříve ztratila rukou.  V některých z těchto nových případů se bude aktualizovat pouze pozice uživatele na základě jeho skutečné ruky, zatímco druhá pozice je odvozena na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako je plevání, házení, odhazování a tlesání.  Pomáhá také v případech, kdy je ruce blízko povrchu nebo drží objekt.  Při odvozování ručního odhadu se hodnota společné přesnosti nastaví na "Approximate" (Přibližný) místo na High (Vysoká). [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)
- Opravili jsme problém, kdy se při resetování kódu PIN pro účty Azure AD zobrazí chyba Něco se pokazilo.
- Při spouštění ET, Iris z aplikace nastavení, nového uživatele nebo informační zprávy by uživatelé měli vidět mnohem méně selhání při spuštění.
- Uživatelé by měli mít správné časové pásmo přicházející z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z prosince 2020
- Build 18362.1088

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet nejnovější verzi Windows Holographic, verze 20H2–prosinec 2020 Update a novou funkci Instalační program aplikací přidanou v sestavení.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic verze 20H2
- Build 19041.1128

Windows Holographic verze 20H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a IT specialisty. Od Funkce automatického umisování do Správce certifikátů v Nastavení, vylepšené funkce bezobrazovkového režimu a nové možnosti nastavení Autopilotu. Tato nová aktualizace umožňuje IT týmům převzít podrobnější kontrolu nad konfigurací a správou HoloLens zařízení a nabízí uživatelům ještě hladká holografická prostředí. 

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční vydání verze 2004 (build 19041). Na své číslo sestavení se můžete podívat na obrazovce Nastavení > o aplikaci a ověřit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete aktualizovat na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

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

Ve HoloLens 2 umožňují pozice očí přesné umístění hologramu, pohodlné sledování a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel přešel přes kalibraci sledování očí, a to i v případě, že prostředí nemusí vyžadovat pohledu.

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

![prohlížeč certifikátů v aplikaci Nastavení.](images/certificate-viewer-device.jpg)

![Obrázek ukazující, jak použít uživatelské rozhraní certifikátu k instalaci certifikátu.](images/certificate-device-install.jpg)

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
   > ![Nastavení uzamčení klienta pomocí OMA-URI.](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>jak zrušit nastavení RequireNetworkInOOBE TenantLockdown na HoloLens 2 pomocí intune? 
1. odeberte HoloLens 2 ze skupiny zařízení, ve které byla výše vytvořená konfigurace zařízení dříve přiřazena. 

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru URI OMA a zadejte hodnotu false pro RequireNetworkInOOBE, jak je znázorněno níže. Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

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

pro Windows holografické verze 20H2 se vytvořily nové zásady hybridních realit pro zařízení HoloLens 2. Mezi nová poříditelné nastavení patří: nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v hybridních zachyceních realit, nastavení, kdy se dá shromáždit Diagnostika a mezipaměť členství skupiny AAD.  

| nové zásady HoloLens                                | Description                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Povolí vypnutí tlačítek jasu, takže se nemění jas.       | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Povolí vypnutí tlačítek hlasitosti, aby se při stisknutí této klávesy nezměnila hlasitost.               | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | zakáže mikrofon, takže není možné nahrávat zvuk na HoloLens 2.                      | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\FallbackDiagnostics                   | Řídí chování, kdy se můžou shromažďovat diagnostické protokoly.                               | 0 zakázané, 1 povoleno pro vlastníky zařízení, 2 povoleno pro všechny (výchozí) |
| MixedReality\HeadTrackingMode                      | Vyhrazeno pro budoucí použití.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Určuje, kolik dní se mezipaměť členství ve skupině Azure AD používá pro veřejné terminály, které cílí na skupiny Azure AD. | Viz níže.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro celoobrazovkový terminál
- Povolené offline veřejné terminály, které se mají používat se skupinami AAD po dobu až 60 dnů.

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
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Příklad hodnoty, která se má Windows Návrháři konfigurace, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové služby pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Kvůli konzistentnímu prostředí HoloLens 2 se ujistěte, že hodnoty pro DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery jsou nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti [o moderním pohotovostním režimu](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) najdete v článku o časovačích nečinnosti pro zobrazení, režim spánku a hibernaci.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nově povolené zásady aktualizace pro HoloLens
- Další možnosti pro instalaci aktualizací nebo zakázání tlačítka Pozastavit aktualizace pro zajištění aktualizací.

Tyto zásady aktualizací jsou teď povolené na HoloLens 2:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Aktualizace/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Úplné podrobnosti o těchto zásadách aktualizací a jejich použití pro HoloLens si můžete přečíst tady v tématu Správa [HoloLens aktualizací.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Povolení Nastavení viditelnosti stránky pro HoloLens 2
- Větší ovládací prvek uživatelského rozhraní v Nastavení App, který může být zaměnit za zobrazení omezeného výběru stránek.

Teď jsme povolili zásadu, která správcům IT umožňuje zabránit tomu, aby byly konkrétní stránky v aplikaci System Nastavení viditelné nebo přístupné, nebo to dělat pro všechny stránky kromě těch, které jsou zadané. Pokud chcete zjistit, jak tuto funkci plně přizpůsobit, klikněte na následující odkaz.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informace o tom, která nastavení stránky můžete přizpůsobit na HoloLens 2, najdete na [naší Nastavení identifikátory URI.](settings-uri-list.md) 
 
![Snímek obrazovky s úpravami aktivních hodin v Nastavení aplikaci](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu
V režimu Research Mode se HoloLens 2 stává nástroj pro výzkum počítačového zpracování obrazu. V porovnání s předchozími edicemi má režim Research mode for HoloLens 2 následující výhody:
-   Kromě senzorů vystavených v režimu výzkumu HoloLens (1. generace) teď poskytujeme přístup senzorů IMU, včetně akcelerometru, krátoboru a krátometru.
-   HoloLens 2 poskytuje nové možnosti, které je možné používat společně s režimem výzkumu. Konkrétně přístup k rozhraním API pro ruční sledování a sledování očí, která doručují bohatší sadu experimentů.

Výzkumníci teď mají na svých vlastních zařízeních možnost povolit režim výzkumu HoloLens přístup ke všem těmto externím nezpracovaných datovým proudům obrázků. Režim výzkumu pro HoloLens 2 také poskytuje přístup k odečtům akcelerometru, krátoboru a ujeté vzdálenosti. V rámci ochrany osobních údajů uživatelů nejsou nezpracované obrázky z fotoaparátů pro sledování očí dostupné prostřednictvím režimu výzkumu, ale směr pohledu je k dispozici prostřednictvím stávajících rozhraní API.

Další technické podrobnosti [najdete v dokumentaci](/windows/mixed-reality/research-mode) k režimu výzkumu.

### <a name="recording-length-increased"></a>Zvýšení délky záznamu
Z důvodu zpětné vazby od zákazníků jsme zvýšili délku záznamu zachytávání [hybridní reality.](holographic-photos-and-videos.md) Zachytávání hybridní reality už nebude ve výchozím nastavení omezené na 5 minut, ale místo toho vypočítá maximální délku záznamu na základě dostupného místa na disku. Zařízení odhadne maximální dobu trvání záznamu videa na základě dostupného místa na disku až do 80 % celkového místa na disku.

> [!NOTE]
> Pokud HoloLens jedna z následujících možností, bude aplikace používat výchozí délku záznamu videa (5 minut):
> - Odhadovaná maximální doba trvání záznamu je menší než výchozích 5 minut.
> - Dostupné místo na disku je méně než 20 % celkového místa na disku.

Všechny požadavky najdete v dokumentaci k [holografickým fotografiím a videím.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:
- Další obrazovky v OOBE jsou teď v tmavém režimu.
- Další informace by měly odkazovat na nejnovější prohlášení o zásadách ochrany osobních údajů online.
- Byl vyřešen problém, kdy uživatelé nemohli zřídit profily VPN prostřednictvím zřizovacích balíčků.
- Opravili jsme problém s konfigurací proxy serveru pro připojení VPN.
- Aktualizace zásad pro zákaz výčtu funkcí USB prostřednictvím MDM pro NCM pro AllowUsbConnection
- Byl vyřešen problém, který znemožňoval zobrazení zařízení HoloLens v Průzkumník souborů přes protokol MTP (Media Transfer Protocol), když je zařízení nastavené jako beznastavový terminál s jednou [aplikací.](hololens-kiosk.md) Mějte na paměti, že MTP (a připojení USB obecně) je stále možné zakázat pomocí zásad [AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
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

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější sestavení pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze září 2020
- Build 19041.1117

Vylepšení a opravy v aktualizaci:

- Řeší problém, který Visual Studio ladění aplikace, když se v souboru appxmanifest nachází SupportsMultipleInstances="true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která řeší selhání detekce internetu přes síťový proxy server. NCSI může k detekci připojení k internetu použít proxy server počítače a proxy server pro každý profil. NcSI bude v budoucí verzi podporovat proxy pro uživatele.
- Ve většině Windows Mixed Reality zařízení je směrový vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze sady HoloLens 2 ale zarovnaly vektor tak, aby byl kolísán k zobrazovacím panelům, což je vzhledem k ideální orientaci o několik stupňů dolů. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.
- Tato verze obsahuje opravu pro zlepšení kvality časového razítka zvuku, která může přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, verze 1903 – aktualizace ze září 2020
- Build 18362.1079

Vylepšení a opravy v aktualizaci:

- Ve většině Windows Mixed Reality zařízení je směrový vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze sady HoloLens 2 ale zarovnaly vektor tak, aby byl kolísán k zobrazovacím panelům, což je vzhledem k ideální orientaci o několik stupňů dolů. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze srpna 2020
- Build 19041.1113

Vylepšení a opravy v aktualizaci:

- Nastavení aplikace už uživatele nesleduje do prostředí pro registraci Iris nebo sledování očí.
- Opravili jsme chybu, kdy se při použití zřizovacího balíčku během spuštění počítače, který přejmenovává zařízení a provádí další akce (například připojování k síti), nepodařilo provést další akce po restartování zařízení kvůli přejmenování.
- Úprava barevného schématu toků počátečního nastavení zařízení za účelem zlepšení vizuální kvality

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, verze 1903 – aktualizace ze srpna 2020
- Build 18362.1074

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější sestavení pro Windows Holographic verze 2004.

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
- Opravili jsme problém, který způsoboval HoloLens aplikace se při použití HoloLens Emulator s hardwarovou akcelerací na určitých zařízeních vrací do prostředí.
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
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení visoru, a to i v případě, že bylo povolené nastavení Spustit na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Při přístupu k Portál zařízení přes Wi-Fi připojení může webový prohlížeč bránit přístupu z důvodu neplatného certifikátu. Prohlížeč může nahlásit chybu typu "ERR_SSL_PROTOCOL_ERROR", i když byl certifikát zařízení dříve důvěryhodný. V takovém případě nemůžete postupovat k Portál zařízení, protože neexistuje možnost ignorovat upozornění zabezpečení. Tato aktualizace tento problém vyřešila. Pokud byl certifikát zařízení dříve stažen a na počítači důvěryhodný pro odebrání upozornění zabezpečení prohlížeče a dojde k chybě SSL, je třeba nový certifikát stáhnout a důvěřovat, aby se odstranila upozornění zabezpečení prohlížeče.
- Povolili jste možnost vytvořit zřizovací balíček modulu runtime, který může instalovat aplikaci pomocí balíčků MSIX.
- Přidali jsme nastavení v **Nastavení**  >  **System** Hologramy, které uživatelům umožňuje automaticky odebrat všechny hologramy z Mixed Reality domů, když  >   se zařízení vypne.
- Opravili jsme problém, který způsob HoloLens, které změnily formát pixelů tak, aby se v emulátoru HoloLens pixelů.
- Opravili jsme chybu, která způsoboval chybu při přihlášení Iris.
- Opravili jsme problém s opakovaným stahováním z obchodu pro již aktuální aplikace.
- Opravili jsme chybu, která znemožňoval opakovaným otevírání Microsoft Edge aplikací.
- Opravili jsme problém se spuštěním aplikace Photos při počátečním spuštění po aktualizaci z verze 1903.
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

Hlavní aktualizace softwaru z května 2020 pro HoloLens 2, *Windows Holographic, verze 2004* zahrnuje řadu zajímavých nových funkcí, jako je podpora Windows Autopilotu, tmavý režim aplikací, podpora ethernetového připojení USB pro hotspoty 5G/LTE a mnoho dalšího. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete **aplikaci Nastavení,** přejděte na Update & Security a vyberte tlačítko    **Zkontrolovat** ****   aktualizace. 

|             Funkce                              |          Popis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Předem nakonfigurujte a bezproblémově nastavte nová zařízení pro produkční prostředí pomocí Windows AutoPilot.                 |
|       Podpora FIDO 2                             |          Podpora klíčů zabezpečení FIDO2 pro povolení rychlého a zabezpečeného ověřování pro sdílená zařízení            |
|       Vylepšené zřizování                      |          Bezproblémové použití zřizovacího balíčku z USB flash disku do HoloLens                              |
|       Stav instalace aplikace                 |          Zkontrolujte stav instalace v Nastavení aplikace pro aplikace se přes MDM nas nabízené HoloLens 2.               |
|       Poskytovatelé konfiguračních služeb (CSP)   |          Přidání nových poskytovatelů konfiguračních služeb pro vylepšení možností správy                 |
|       Podpora USB 5G/LTE                       |          Rozšířená ethernetová funkce USB umožňuje podporu pro 5G/LTE.                                    |
|       Tmavý režim aplikace                              |          Tmavý režim aplikace dostupný pro aplikace, které podporují tmavý i světlý režim, vylepšuje prostředí pro prohlížení.        |
|       Hlasové příkazy                             |          Podpora dalších systémových hlasových příkazů pro HoloLens bez rukou                           |
|       Vylepšení sledování rukou                 |          Vylepšení sledování rukou zpřesní tlačítka a interakce s 2D slatem.                        |
|       Vylepšení a opravy kvality                 |          Různá vylepšení výkonu a spolehlivosti systému napříč platformou                            |

### <a name="support-for-windows-autopilot"></a>Podpora pro Windows Autopilot

Windows Autopilot pro HoloLens 2 umožňuje kanálu prodeje zařízení předem zaregistrovat HoloLens do vašeho tenanta Intune. Jakmile zařízení dorazí, jsou připravená k vlastnímu nasazení jako sdílená zařízení ve vašem tenantovi. Pokud chcete využít výhod vlastního nasazení, musí se zařízení připojit k síti během první obrazovky v nastavení pomocí USB-C-to-Ethernet.

Jakmile uživatel spustí proces samosazování Autopilotu, proces dokončí následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD).
1. Pomocí Azure AD zaregistrujte zařízení ve službě Microsoft Intune (nebo jiné službě MDM).
1. Stáhněte si zásady, certifikáty a síťové profily cílené na zařízení.
1. Zřídit zařízení.
1. Zobrazí přihlašovací obrazovku uživateli.

Další informace najdete v [Windows Autopilot for HoloLens 2 .](hololens2-autopilot.md)

*Požádejte svého account manažera, aby se teď připojil k AutoPilotu Preview. Zařízení připravená pro Autopilot začnou brzy doručovat.*

### <a name="fido2-security-key-support"></a>Podpora klíčů zabezpečení FIDO2

Někteří uživatelé sdílejí HoloLens zařízení s ostatními uživateli v pracovním nebo školním prostředí. Je proto důležité, aby uživatelé mohli snadno zadávat dlouhá uživatelská jména a hesla. Fast Identity Online (FIDO) umožňuje komukoli ve vaší organizaci (tenant Azure AD) bezproblémově se přihlásit k HoloLens bez zadávání uživatelského jména nebo hesla.

Klíče zabezpečení FIDO2 jsou "nepřehledná" metoda ověřování bez hesla založená na standardech, která může být v jakémkoli provedení. FIDO je otevřený standard pro ověřování bez hesla. Umožňuje uživatelům a organizacím přihlásit se ke svým prostředkům bez uživatelského jména nebo hesla. Místo toho používají externí klíč zabezpečení nebo klíč platformy integrovaný do zařízení.

Pokud chcete začít, podívejte se [na stránku Povolení přihlašování pomocí bezpečnostního klíče bez hesla.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Vylepšená registrace MDM prostřednictvím zřizovacího balíčku

Zřizovací balíčky umožňují HoloLens konfiguraci prostřednictvím konfiguračního souboru, a HoloLens prostředí. Dříve bylo třeba zřizovací balíčky zkopírovat do HoloLens paměti. Teď mohou být na USB flash disku, aby se snadněji opakovaně opakovaně HoloLens zařízeních a vy můžete zařízení zřídit paralelně. Zřizovací balíčky teď také podporují pole pro registraci do správy zařízení, takže po zřízení už neexistuje žádné ruční nastavení.

Vyzkoušejte si to:

1. Stáhněte si nejnovější verzi nástroje Windows Configuration Designer z úložiště Windows do počítače.
1. Vyberte **Provision HoloLens Devices** Provision HoloLens 2 Devices (Zřídit HoloLens zařízení  >  **2).**
2. Sestavte konfigurační profil. Potom zkopírujte všechny vytvořené soubory do úložného zařízení USB-C.
3. Připojte zařízení USB-C do všech zařízení s čerstvým HoloLens. Potom stiskněte **tlačítka napájení pro** snížení hlasitosti a použijte  +   zřizovací balíček.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodních aplikací

Nasazení a správa aplikací MDM pro obchodní aplikace je pro HoloLens. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. V této verzi jsme přidali další podrobnosti v části **Nastavení**  >  **Accounts Access** work or school (Přístup k účtům do práce nebo do školy) Klikněte na informace o  >    >  **vašem**  >  **účtu.**

### <a name="additional-csps-and-policies"></a>Další csp a zásady

Poskytovatel [konfiguračních služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. V této verzi přidáme podporu pro další zásady, které správcům řízení zvýší počet nasazených HoloLens zařízení. Seznam csP podporovaných poskytovatelem csP najdete HoloLens [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

Novinka v této verzi:

**CsP pro zásady** 

Poskytovatel konfigurační služby Policy umožňuje podniku konfigurovat zásady na Windows zařízeních. V této verzi jsme přidali nové zásady pro HoloLens, které jsou zde uvedené. Další informace najdete v tématu o [zprostředkovateli csp zásad podporovaných HoloLens 2.](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Poskytovatel konfigurační služby NetworkQoSPolicy vytváří zásady QoS (Quality of Service) sítě. Zásady QoS provádějí sadu akcí u síťového provozu na základě sady odpovídajících podmínek. Další informace najdete v tématu [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Rozšířená podpora ethernetového připojení USB pro zařízení připojená přes 5G/LTE

Byla přidána podpora pro povolení určitých mobilních širokopásmového zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když nejsou připojená k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě jako** další ethernetové připojení. (Mobilní širokopásmová zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s velkou šířkou pásmaWi-Fi není dostupná a Wi-Fi není dostatečně výkonný. Další informace o podporovaných zařízeních USB najdete v Připojení Bluetooth a [ZAŘÍZENÍ USB-C.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Vylepšení sledování rukou

Tato verze obsahuje několik vylepšení ručního sledování:

- **Bodování představuje stabilitu:** Systém teď odolá ukazováčku, když ho uchytává šedě. Tato změna zvyšuje přesnost při nabízení tlačítek, psaní, posouvání obsahu a dalších. 
- **Menší nechtěné klepnutí ve vzduchu:** Vylepšili jsme detekci gesta klepnutí ve vzduchu. V několika běžných scénářích je teď méně náhodných aktivací, například když pustíte ruce na stranu.
- **Spolehlivost uživatelského přepínače:** Systém je teď rychlejší a spolehlivější při aktualizaci velikosti ruky při sdílení zařízení.
- **Menší krádež rukou:** Vylepšili jsme zpracování případů, kdy senzory mají více než dvě ruce. Pokud spolu úzce pracuje více lidí, je teď mnohem menší pravděpodobnost, že sledovaná ruky "přeskočí" z uživatele do ruky někoho jiného ve scéně.
- **Spolehlivost systému:** Opravili jsme problém, který způsobl, že při vysokém zatížení zařízení přestalo fungovat sledování rukou.

### <a name="dark-mode"></a>Tmavý režim

Mnoho Windows aplikací teď podporuje tmavý i světlý režim. HoloLens 2 uživatelé mohou zvolit výchozí režim pro aplikace, které podporují oba režimy. Po aktualizaci je výchozí režim aplikace "tmavý", ale toto nastavení můžete snadno změnit: Přejděte na **Nastavení**  >  **Systémových** barev Zvolte výchozí  >    >  **režim aplikace.** 

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

![V tmavých oknech s dlaždicí](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systémové hlasové příkazy

Hlasové příkazy teď můžete používat s libovolnou aplikací na zařízení. Další informace najdete v tématu [Použití hlasu k ovládání HoloLens](hololens-cortana.md). Viz také [Podporované jazyky pro HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana aktualizace

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
