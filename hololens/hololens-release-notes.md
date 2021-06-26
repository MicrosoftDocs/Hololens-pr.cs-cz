---
title: Poznámky k verzi HoloLens 2
description: Udržte si aktuální informace o všech aktualizacích v každé nové verzi HoloLens 2.
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
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924532"
---
# <a name="hololens-2-release-notes"></a>Poznámky k verzi HoloLens 2

Aby bylo zajištěno, že zařízení HoloLens budou produktivně pracovat, budeme dál vysílovat aktualizace funkcí, chyb a zabezpečení. Na této stránce uvidíte, co je nového pro HoloLens každý měsíc. Pokud chcete získat nejnovější aktualizaci HoloLens [](hololens-update-hololens.md#check-for-updates-and-manually-update) 2, můžete aktualizace zkontrolovat a ručně aktualizovat, nebo získat úplnou aktualizaci Flash Update (FFU) k flash disku vašeho zařízení prostřednictvím [doprovodné funkce Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) Stahování [je](https://aka.ms/hololens2download) stále aktuální a poskytuje nejnovější obecně dostupné sestavení.

> [!NOTE]
> Nedávné oznámení o Windows 11 se zaměřovala na verzi Windows na počítači. Nedávno jsme v květnu 2021 spustili hlavní aktualizaci operačního systému pro HoloLens 2 [a](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) na základě zpětné vazby zákazníků na tento pokles pracujeme na nadcházející verzi.

> [!IMPORTANT]
> Vzhledem k známému problému v našem buildu [21H1,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)který ovlivňuje uživatele vzdálené pomoci, v současné době postavíme nabídku aktualizací Windows Holographic verze 21H1. Výchozí sestavení Advanced Recovery Companion jsme také změnili na [Windows Holographic verze 20H2–June 2021 Update,](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)která je nejnovější verzí 20H2.
>
> I když zmírníme dopad tohoto problému omezením dostupnosti 21H1, chápeme, že někteří zákazníci stále chtějí provést aktualizaci na 21H1. Pro zákazníky, kteří chtějí aktualizovat na 21H1, jsou k dispozici dvě různé cesty:
>
> - [Zaregistrujte zařízení](hololens-insider.md#start-receiving-insider-builds) jako Windows Insiders a vyberte **Beta kanál**. Tím umožníte, aby se tato zařízení mohla aktualizovat na 21H1 a mít spolehlivá sestavení.
> - [Stáhněte si na počítač nejnovější ffu a](https://aka.ms/hololens2download) pak zařízení flash přes [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic verze 21H1 – aktualizace z června 2021
- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive pro nahrávání fotoaparátů do práce nebo do školy

Do aplikace Nastavení HoloLens 2 jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa hybridní reality ze složky Obrázky > Fotoaparát do odpovídající složky OneDrive pro pracovní nebo školní použití. Tato funkce řeší mezeru ve funkcích v aplikaci [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) na HoloLens 2, která podporuje jenom automatické nahrávání fotoaparátů do osobního účet Microsoft zákazníka (a ne jeho pracovního nebo školního účtu).

**Jak to funguje**

- Pokud **chcete povolit > fotoaparátu, > Mixed Reality** přejděte na Nastavení > Mixed Reality System > Mixed Reality Camera.
- Když tuto funkci  nastavíte na Na pozici, všechny fotky nebo videa hybridní reality zachycené do vašeho zařízení se automaticky zařadit do fronty pro nahrání do složky Obrázky > Fotoaparát na vašem pracovním nebo školním účtu OneDrivu.
    >[!NOTE]
    >Fotky a videa zachycené před  povolením této funkce nebudou zařazené do fronty pro nahrání a budou se muset nahrát ručně.
- Stavová zpráva na stránce Nastavení zobrazí počet souborů čekajících na nahrání (nebo si přečtěte "OneDrive je aktuální" po nahrání všech čekajících souborů).
- Pokud máte obavy o šířku pásma nebo chcete nahrávání pozastavit z nějakého důvodu, můžete tuto funkci přepnout do **pozice Vypnuto.** Dočasné zakázání této funkce zajistí, že se fronta pro nahrávání bude dál zvyšovat při přidávání nových souborů do složky Fotoaparát, ale soubory se nenahrají, dokud tuto funkci znovu nepo povolením nenahrajete.
- Nejnovější soubory se nahrají jako první (poslední za, první ven).
- Pokud má váš účet OneDrive problémy (například po  změně hesla), na stránce Nastavení se zobrazí tlačítko Opravit.
- Neexistuje žádná maximální velikost souboru, ale mějte na paměti, že nahrávání velkých souborů bude trvat déle (zejména pokud je vaše šířka pásma pro nahrávání omezena). Pokud během nahrávání velkého souboru pozastavíte nebo vypnete nahrávání, částečné nahrání se zachová. Pokud se nahrávání znovu povolí během několika hodin od "pozastavení" nebo vypnutí, nahrávání bude pokračovat tam, kde se vypnulo. Pokud se ale nahrávání po několika hodinách znovu povolí, nahrávání velkého souboru se od začátku restartuje.

**Známé problémy a upozornění**

- Toto nastavení nemá žádné integrované omezování na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Nahrávání se pozastaví, ale funkce bude dál monitorovat nově přidané soubory do fotoaparátu. Jakmile budete připraveni pokračovat, nahrávání znovu povolte.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat jenom soubory pro uživatele, který je momentálně přihlášený k zařízení.
- Pokud během sledování počtu nahrávání v reálném čase posouváte fotky nebo videa na stránce Nastavení, nezapomeňte, že počet čekajících souborů se může změnit, dokud se nahrávání aktuálního souboru nedokončí.
- Nahrávání se pozastaví, když zařízení usne v režimu spánku nebo je vypnuté. Pokud chcete zajistit dokončení probíhajícího nahrávání, aktivně zařízení používejte, dokud stránka Nastavení nečte "OneDrive je aktuální" nebo neupravte nastavení Režimu spánku **& Power** & režimu spánku.
### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

HoloLens 2 teď podporuje následující zásady telemetrie:
- KonfiguraceTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Systém\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně, aby měly úplnou kontrolu nad telemetrií a chováním v aplikaci Nastavení.

Vylepšení a opravy v aktualizaci:
- Opravuje hlavní poškození videa pomocí barevného poškození.
- Řeší problém, kdy se v nabídce Power může oříznou text.
- Povolí podporu pro zásadu RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z června 2021
- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

HoloLens 2 teď podporuje následující zásady telemetrie:
- KonfiguraceTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Systém\AllowTelemetry i System\ConfigureTelemetryOptInSettingsUx by se měly používat společně, aby měly úplnou kontrolu nad telemetrií a chováním v aplikaci Nastavení.

Doporučujeme vám vyzkoušet si nejnovější build s Windows Holographic verze 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic verze 1903 – aktualizace z června 2021
- Build 18362.1116

Vylepšení a opravy v aktualizaci:
- Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si nejnovější build Windows Holographic verze 21H1.

>[!IMPORTANT]
> Toto sestavení už nebude v provozu.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic verze 21H1
- Build 20346.1002

Tato aktualizace obsahuje funkce pro dvě cílové skupiny. Funkce, které může koncový uživatel na zařízení používat kdokoli na zařízení, a nové možnosti správy zařízení, které mohou konfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro každou cílovou skupinu. Pokud jste správcem IT, podívejte se na náš kontrolní seznam pro správce [IT – aktualizace.](#it-admin---update-checklist)
>[!IMPORTANT]
>Aby bylo možné aktualizovat toto sestavení, musí zařízení HoloLens 2 aktuálně běžet na aktualizaci z února 2021 (build 19041.1136) nebo novější. Pokud se vám tato aktualizace funkcí neschová k dispozici, nejprve aktualizujte své zařízení a zkuste to znovu.

>[!NOTE]
>V současné Microsoft HoloLens verze 2 podporuje měsíční servisní aktualizace (opravy chyb a zabezpečení) pro následující verze:
>- Windows Holographic verze 20H2 (build 19041.1128+)
>- Windows Holographic verze 2004 (build 19041.1103+)
>- Windows Holographic verze 1903 (build 18362+) 
>
> Se zavedením Windows Holographic verze 21H1 přerušujeme měsíční servisní aktualizace **pro Windows Holographic verze 1903.** Díky tomu se můžete zaměřit na novější verze a pokračovat v poskytování cenných vylepšení. 


| Název funkce                                              | Krátký popis                                                                      | Cílovou skupinu | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nový Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nová funkce založená na Chromium Microsoft Edge k dispozici pro HoloLens 2. | Koncový uživatel | 
[WebXR a 360 Viewer](#webxr-and-360-viewer) | Vyzkoušejte imerzivní webová prostředí a přehrávání videa 360. | Koncový uživatel | 
[Nová aplikace Nastavení](#new-settings-app) | Starší verze aplikace Nastavení je nahrazena aktualizovanou verzí novými funkcemi a nastaveními. | Koncový uživatel |
[Zobrazení barevného pozadí](#display-color-calibration) | Vyberte alternativní profil barev pro zobrazení HoloLens 2. | Koncový uživatel |
[Výchozí výběr aplikace](#default-app-picker) | Vyberte, která aplikace se má spustit pro každý typ souboru nebo odkazu. | Koncový uživatel |
[Řízení objemu na aplikaci](#per-app-volume-control) | Ovládat svazek na úrovni aplikace nezávisle na systémovém svazku. | Koncový uživatel |
[Instalace webových aplikací](#install-web-apps) | Pomocí nového prohlížeče Microsoft Edge nainstalujte webové aplikace na HoloLens 2, například systém Microsoft Office. | Koncový uživatel |
[Potáhnutím na typ](#swipe-to-type) | Použijte hrot prstu na potáhnutí slova na holografické klávesnici. | Koncový uživatel |
[Nabídka napájení z nabídky Start](#power-menu-from-start) | V nabídce Start restartujte a vypněte zařízení HoloLens. | Koncový uživatel |
[Více uživatelů uvedených na přihlašovací obrazovce](#multiple-users-listed-on-sign-in-screen) | Zobrazit více uživatelských účtů na přihlašovací obrazovce | Koncový uživatel |
[Podpora externích mikrofonů USB-C](#usb-c-external-microphone-support) | Použijte mikrofony USB-C pro aplikace a/nebo vzdálenou pomoc. | Koncový uživatel |
[Automatické přihlášení návštěvníka pro veřejné terminály](#visitor-auto-logon-for-kiosks) | Umožňuje, aby se automatické přihlašování na účtech návštěvníka používalo pro beznabídkový režim. | Správce IT |
[Nový AUMIDs pro nové aplikace v celoobrazovkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs pro nová nastavení a aplikace Edge. | Správce IT |
[Vylepšené zpracování chyb v celoobrazovkovém režimu](#kiosk-mode-behavior-changes-for-handling-of-failures) | Celoobrazovkový režim vyhledá globální přiřazený přístup před prázdnou nabídkou Start. | Správce IT |
[Nový SettingsURIs pro viditelnost nastavení stránky](#new-settings-uris-for-page-settings-visibility) | 20 + nové SettingsURIs pro zásady nastavení/PageVisibilityList. | Správce IT |
[Konfigurace záložní diagnostiky](#configuring-fallback-diagnostics-via-settings-app) | Nastavení nouzového diagnostického chování v aplikaci nastavení. | Správce IT |
[Sdílení věcí pomocí okolních zařízení](#share-things-with-nearby-devices) | Sdílejte soubory nebo adresy URL z HoloLens do počítače. | Vše |
[Nová trasování diagnostiky operačního systému](#new-os-diagnostic-traces) | Nový Poradce při potížích s nastavením pro aktualizace operačního systému. | Správce IT |
[Optimalizace doručování – náhled](#delivery-optimization-preview) | Snižte spotřebu šířky pásma pro soubory ke stažení z více zařízení HoloLens. | Správce IT |

Podívejte se na související poznámky k verzi:

- [Navštívit archiv emulátoru HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Vzdálená pomoc pro Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Příručky k Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Představení nového Microsoft Edge

![Animace staršího loga Microsoft Edge na nové logo Microsoft Edge](images/new-edge.gif)

Nový Microsoft Edge [přijme projekt chrom Open Source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) , aby vytvořil lepší kompatibilitu pro zákazníky a méně fragmentaci webu pro webové vývojáře.

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší verzi Microsoft Edge, která se už v nových verzích [nepodporuje](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) .

![Nový snímek obrazovky Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Spouští se nový Microsoft Edge.

Nové Microsoft Edge ![Nová ikona Microsoft Edge](images/new_edge_logo.png) (reprezentované modrou a zelenou ikonou) je připnuté do nabídky Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Když poprvé spustíte nový Microsoft Edge na HoloLens 2, vaše nastavení a data se naimportují ze starší verze Microsoft Edge. Pokud po spuštění nového Microsoft Edge budete nadále používat starší verzi Microsoft Edge, nebudou se nová data synchronizovat ze starší verze Microsoft Edge na nové Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

Nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče na HoloLens 2, než bylo dříve k dispozici ve starší verzi Microsoft Edge.

Tady je několik užitečných prostředků, které vám pomůžou se správou nastavení zásad pro nové Microsoft Edge:

- [Konfigurace nastavení zásad Microsoft Edge pomocí Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge starší než mapování zásad Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapování zásad pro Google Chrome na Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Kompletní [dokumentace k Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Vzhledem k tomu, že se jedná o řadu zásad prohlížeče, které podporuje nové Microsoft Edge, náš tým nemůže zaručit, že každá nová zásada funguje na HoloLens 2. Ale otestovali a potvrdili jsme se, než je nový Microsoft Edge ekvivalent každé starší verze zásad Microsoft Edge, která byla dřív podporovaná na práci HoloLens 2, podle očekávání. Pokud chcete najít nový ekvivalent Microsoft Edge pro každou starší zásadu prohlížeče Microsoft Edge, kterou jste používali s HoloLens 2, přečtěte si téma [mapování Microsoft Edge na](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edge.
>
> Existují alespoň dvě nové zásady Microsoft Edge, které *nebudeme* spolupracovat s HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nového Microsoft Edge na HoloLens 2

Vzhledem k tomu, že nový Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UWP, která umožňuje spouštění na zařízeních jenom s UWP, jako je HoloLens 2, některé funkce nemusí být k dispozici okamžitě. V nadcházejících měsících budeme podporovat nové scénáře a funkce, takže na tomto místě najdete aktuální informace.

**Očekává se, že scénáře a funkce budou fungovat:**
- První spuštění, přihlášení k profilování a synchronizace
- Weby by se měly vykreslovat a chovat podle očekávání
- Většina funkcí prohlížeče (oblíbená, historie atd.) by měla fungovat podle očekávání.
- Tmavý režim
- Instalace webových aplikací do zařízení
- Instalování rozšíření (Pokud používáte jakákoli rozšíření, která na HoloLens 2 nefungují správně), dejte nám prosím nějaké informace.
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

- Verze Preview lupy v holografické klávesnici je pro nový Microsoft Edge zakázaná. Doufáme, že tuto funkci znovu povolíme v budoucí aktualizaci, jakmile bude zvětšení fungovat správně.
- Zvuk může být přehráván z nesprávného okna prohlížeče, pokud máte otevřeno a aktivní jiné okno prohlížeče. Tento problém můžete obejít tak, že zavřete jiné aktivní okno, které nemá přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu "pořídit"](hololens2-basic-usage.md#follow-me-stop-following)bude pokračovat přehrávání zvuku, pokud zakážete režim "pořídit". Tento problém můžete obejít tak, že přehrávání zvuku zastavíte ještě před tím, než zakážete režim "pořídit" nebo zavřením okna tlačítkem **X** .
- Interakce s aktivními okny Microsoft Edge může způsobit neočekávaně neočekávaně jiné okna aplikace 2D. Tato okna můžete znovu aktivovat pomocí interakce s nimi.

#### <a name="microsoft-edge-insider-channels"></a>Kanály Microsoft Edge Insider

Microsoft Edge tým má k dispozici tři kanály verze Preview pro komunitu programu Edge Insider: beta, vývoj a Kanárské. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat více verzí najednou. 

Další informace [o komunitě Edge Insider najdete na domovské stránce](https://www.microsoftedgeinsider.com) Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider do HoloLens 2 Microsoft Edge několik metod:

**Přímá instalace na zařízení (aktuálně dostupná pouze pro nespravovaná zařízení)**
  1. Na holoLens 2 přejděte na stránku pro stažení [Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko Download for HoloLens 2 (Stáhnout pro **HoloLens 2)** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor .msix z fronty pro stahování Edge nebo ze složky Stažené soubory (pomocí příkazu Průzkumník souborů).
  1. [Spustí se instalační](app-deploy-app-installer.md) program aplikace.
  1. Vyberte **tlačítko** Nainstalovat.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

**Instalace prostřednictvím počítače s Portál zařízení s Windows [(vyžaduje](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) povolení vývojářského režimu na HoloLens 2)**
  1. Na počítači přejděte na stránku pro stažení [Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte **tlačítko se šipkou rozevíracího** seznamu vedle tlačítka Stáhnout pro Windows 10 pro kanál Edge Insider, který chcete nainstalovat.
  1. V **rozevírací nabídce vyberte HoloLens 2.**
  1. Uložte soubor .msix do složky Stažené soubory na počítači (nebo do jiné složky, kterou snadno najdete).
  1. Pomocí [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na počítači nainstalujte stažený soubor .msix na HoloLens 2.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Použití nástroje WDAC k blokování nových Microsoft Edge

Aby správci IT mohli aktualizovat zásady [WDAC](windows-defender-application-control-wdac.md) tak, aby blokují novou aplikaci Microsoft Edge, musíte do zásad přidat následující položky.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí mohou mít omezení sítě, která je třeba vzít v úvahu. Pokud chcete zajistit bezproblémové prostředí s novým Edgem, [povolte tyto koncové body Microsoftu.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Instalace webových aplikací
 > [!Note]
>Od [verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ve Windows Holographic se už webová aplikace Office nebude předinstalovat.

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci systém Microsoft Office zobrazit a upravit soubory hostované na SharePointu nebo OneDrivu. Webovou aplikaci Office nainstalujete tak, že na panelu Adresa navštívíte a vyberete tlačítko App Available (Aplikace k dispozici) nebo Install Office (Nainstalovat https://www.office.com Office).   Potvrďte **výběrem** možnosti Nainstalovat.

> [!IMPORTANT]
> Funkce webové aplikace Office je dostupná jenom v případě, že holoLens 2 má aktivní připojení k internetu.

### <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer

Nový Microsoft Edge zahrnuje podporu WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Mnoho imerzivních webových prostředí bylo navrženo s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale holoLens 2 tato prostředí podporuje. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že pro zákazníky HoloLens 2, kteří si to budou zkoušet, přijde nové imerzivní prostředí rozšířené hybridní reality.

Rozšíření 360 Viewer je postaveno na WebXR a automaticky se nainstaluje společně s novou Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

#### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu **vyberte tlačítko Enter VR** (Zadat virtuální realitu). Umístění a vizuální znázornění tohoto tlačítka se může u jednotlivých webových stránek lišit, ale může vypadat podobně jako:

    ![Příklad zadání tlačítka VR](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění prostředí WebXR v konkrétní doméně prohlížeč požádá o souhlas se zadáním imerzivního zobrazení a vybere **Povolit.**
1. K [manipulaci s prostředím používejte gesta HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)
1. Pokud prostředí nemá tlačítko Ukončit, **pomocí** gesta [Start](hololens2-basic-usage.md#start-gesture) se vraťte domů.

**Doporučené ukázky WebXR**
- 360 Viewer (viz další část)
- [XR Užis](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

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

### <a name="new-settings-app"></a>Nová aplikace Nastavení

V této verzi představujeme novou verzi aplikace Nastavení. Nová aplikace Nastavení obsahuje nové funkce a rozšířená nastavení pro HoloLens 2 v následujících oblastech: Zvuk, Power & režim spánku, Síť & Internet, Aplikace, Účty, Usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, že se nová aplikace Nastavení liší od starší verze aplikace Nastavení, budou při aktualizaci odebrána okna Nastavení, která jste předtím umístili kolem svého prostředí.

![Domovská stránka nové aplikace Nastavení](images/new-settings-app.png)

**Nové funkce a nastavení**
- Vyhledávání nastavení: Vyhledá nastavení z domovské stránky Nastavení pomocí klíčových slov nebo názvu nastavení.
- System > Sound:
  - Vstupní a výstupní zvuková zařízení: Nezávisle zvolte vstupní a výstupní zvuková zařízení (například naslouchejte zvukovému signálu bluetooth nebo pro zvukový vstup použijte mikrofon USB-C).
    > [!NOTE]
    > HoloLens 2 nepodporuje mikrofony Bluetooth.
  - Objem aplikace: Nezávisle upravte objem každé aplikace. Viz [řízení objemu na aplikaci.](#per-app-volume-control)
- System > Power & režim spánku: Zvolte, kdy má zařízení po určité době nečinnosti přejít do režimu spánku.
- Baterie >: Ručně povolte režim spořič baterie nebo nastavte prahovou hodnotu baterie, po spořič baterie režim zapne automaticky.
- Zařízení > USB: Ve výchozím nastavení můžete zakázat připojení USB.
- Network & Internet:
  - Ethernetové adaptéry USB-C se teď zobrazí v části Síťová & internetu.
  - K dispozici jsou teď nastavení ethernetového adaptéru USB-C, včetně jeho IP adresy.
  - Na HoloLens 2 teď můžete povolit režim v letadle.
- Aplikace: Můžete resetovat výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu [Výběr výchozí aplikace.](#default-app-picker)
- Účty > Ostatní uživatelé: Vlastníci zařízení mohou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, downgradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů

**Známé problémy**
- Dříve umístěná okna Nastavení se odstraní (viz poznámka výše).
- Zařízení už nemůžete přejmenovat pomocí aplikace Nastavení. Správci IT mohou zařízení přejmenovat pomocí šablony Windows Autopilot pro název zařízení [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) nebo uzlu MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se za všech okolností zobrazuje virtuální ethernetové zařízení (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, protože je povaha desktopové aplikace Win32 podporované vrstvou adaptéru UPW (brzy se neočekává žádná oprava).

#### <a name="display-color-calibration"></a>Zobrazení barevného pozadí



Pomocí tohoto nového nastavení můžete vybrat alternativní profil barev pro zobrazení HoloLens 2. Barvy se tak můžou zdát přesnější, zejména při nižších úrovních jasu zobrazení. Kalibraci barev displeje můžete najít v aplikaci nastavení na stránce kalibrace systému >.

> [!NOTE]
> Vzhledem k tomu, že toto nastavení uloží nový profil barev do firmwaru zobrazení, jedná se o nastavení podle zařízení (a není jedinečné pro každý uživatelský účet).

##### <a name="how-to-use-display-color-calibration"></a>Jak používat kalibraci barev displeje

1. Spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **kalibrace barev displeje spustit** .
1. Spustí se prostředí kalibrace barev displeje a doporuče vám, abyste se ujistili, že je váš hypervisor ve správné pozici.
1. Až budete pokračovat v dialogových oknech instrukce, zobrazí se automaticky ztlumení jasu na 30%.
    > [!TIP]
    > Pokud máte potíže se zobrazením ztlumené scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek jas na levé straně zařízení.
1. Vyberte tlačítka 1-6, abyste si mohli okamžitě vyzkoušet jednotlivé profily barev, a najít jeden, který vypadá nejlépe pro vaši oči. (to obvykle znamená, že profil, který pomáhá scénu, se jeví jako neneutrální, se vzorkem stupňů šedi a tónům skinu, které vypadají podle očekávání.)

    ![Zobrazit scénu kalibrace barev](images/color-cal-ui.png)
    
1. Až budete s vybraným profilem spokojeni, vyberte tlačítko **uložit & tlačítko Storno** .
1. Pokud nechcete provádět změny, vyberte tlačítko **zrušit & ukončení** a změny se vrátí.

> [!TIP]
> Tady jsou některé užitečné tipy, které vám pomůžou při používání nastavení kalibrace barev displeje:
> - Můžete znovu spustit kalibraci barev displeje z nastavení, kdykoli budete chtít.
> - Pokud někdo na zařízení dřív používal nastavení pro změnu profilů barev, datum a čas poslední změny se projeví na stránce nastavení.
> - Když znovu spustíte kalibraci barev displeje, bude zvýrazněný profil barev zvýrazněný a profil 0 se nezobrazí (jako profil 0 představuje původní barevný profil displeje).
> - Pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete tak učinit na stránce nastavení (viz [Postup resetování barevného profilu](#how-to-reset-color-profile)).

##### <a name="how-to-reset-color-profile"></a>Jak obnovit barevný profil 

Pokud si nejste spokojeni s vlastním profilem barev uloženým do HoloLens 2, můžete obnovit původní barevný profil zařízení:
1. Spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **Obnovit výchozí barevný profil** .
1. Po otevření dialogového okna vyberte **restartovat** , pokud jste připraveni restartovat HoloLens 2 a použít změny.

#### <a name="top-display-color-calibration-known-issues"></a>Známé problémy při kalibraci horních displejů

- Na stránce nastavení se stavový řetězec, který oznamuje, že se naposledy změnil barevný profil, bude zastaralá, dokud tuto stránku nastavení znovu nenačtete.
    - Alternativní řešení: Vyberte jinou stránku nastavení a pak znovu vyberte stránku kalibrace.

#### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když aktivujete hypertextový odkaz nebo otevřete typ souboru s více než jednou nainstalovanou aplikací, který ho podporuje, zobrazí se nové okno s výzvou, abyste vybrali, která aplikace by měla zpracovat soubor nebo typ odkazu. V tomto okně můžete také zvolit, aby vybraná aplikace zpracovala soubor nebo typ odkazu "jednou" nebo "Always".

Pokud zvolíte "vždycky", ale později chcete změnit, která aplikace zpracovává určitý typ souboru nebo propojení, můžete obnovit uložené výchozí hodnoty v **nastavení > aplikace**. Posuňte se do dolní části stránky a v části výchozí aplikace pro typy souborů nebo výchozí aplikace pro typy odkazů vyberte tlačítko **Vymazat** . Na rozdíl od podobných nastavení na stolních počítačích nemůžete resetovat jednotlivé výchozí hodnoty typu souboru.

#### <a name="per-app-volume-control"></a>Řízení hlasitosti na aplikaci

Teď v tomto buildu Windows můžou uživatelé ručně upravovat úroveň hlasitosti každé aplikace. To uživatelům umožňuje lépe se zaměřit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například nutnost vypnout objem jedné aplikace a zavolat jiné osobě na vzdálenou pomoc v jiném.

Pokud chcete nastavit hlasitost jednotlivé aplikace, přejděte na **Nastavení**  ->  **systémový**  ->  **zvuk** a v části Pokročilé možnosti zvuku vyberte **Předvolby aplikace a hlasitost zařízení**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potáhnutím na typ

Někteří zákazníci na virtuálních klávesnicích rychleji najdou na "typ", a to potáhnutím tvaru slova, které mají v úmyslu zadat, a my si tuto funkci zobrazíme pro holografickou klávesnici. Jedno slovo můžete potáhnutím prstem procházet rovinou holografické klávesnice, potažením tvaru slova a následným odvoláním hrotu prstu z roviny klávesnice. Potáhnutím prstů můžete přetáhnout text, aniž byste museli stisknout MEZERNÍK, a to tak, že z klávesnice odeberete prst mezi slovy. Víte, že funkce funguje v případě, že se pod pohybem prstu na klávesnici zobrazuje potáhnutí.

Upozorňujeme, že tato funkce může být obtížné použít a hlavní, a to z důvodu povahy holografické klávesnice, kde nepůsobíte proti prstům odolnost (na rozdíl od zobrazení mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní obrazovce HoloLens, který ukazuje, kdy je k dispozici aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní obrazovku HoloLens pomocí [gesta Start](hololens2-basic-usage.md#start-gesture) nebo vyslovení příkazu "Přejít na začátek".

2. Všimněte si ikony tří teček (...) vedle obrázku profilu uživatele:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Vyberte si obrázek profilu uživatele pomocí vašich rukou nebo hlasového příkazu "Power".

4. Zobrazí se nabídka s možnostmi pro odhlášení, restartování nebo vypnutí zařízení:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Vyberte možnosti nabídky pro odhlášení, restartování nebo vypnutí HoloLens. Možnost odhlášení možná není dostupná, pokud je zařízení nastavené na [jeden účet Microsoft (MSA) nebo místní účet](hololens-identity.md).

6. Zavřete nabídku tak, že se dotknete kamkoli jinde nebo zavřete nabídku Start pomocí gesta Start.

#### <a name="update-indicator"></a>Aktualizovat indikátor

Pokud je k dispozici aktualizace, ikona se třemi tečkami až do indikace, že restartování nainstaluje aktualizace možností nabídky, se také změní tak, aby odrážely přítomnost aktualizace.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Předchozí přihlašovací obrazovka zobrazila pouze posledního přihlášeného uživatele a vstupní bod jiného uživatele. Dostali jsme zpětnou vazbu od zákazníků, pokud se k zařízení přihlásilo více uživatelů. Pořád se vyžadovalo, aby znovu zapisovali své uživatelské jméno atd.

Když se v tomto buildu Windows zavedlo výběr **jiného uživatele** , který se nachází napravo od pole pro zadání kódu PIN, zobrazí se na přihlašovací obrazovce několik uživatelů, kteří se k zařízení dříve přihlásili. To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlašovat pomocí svých přihlašovacích údajů Windows Hello. Do zařízení můžete přidat nového uživatele pomocí tlačítka **Přidat účet** na stránce ostatní uživatelé.

Když v nabídce ostatní uživatelé přejdete na tlačítko ostatní uživatelé, zobrazí se poslední uživatel přihlášený k zařízení. Kliknutím na toto tlačítko se vrátíte na přihlašovací obrazovku pro tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiní uživatelé](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externích mikrofonů USB-C

> [!IMPORTANT]
> Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**. Při zapojení do sady uživatelů sluchátek se systémem USB-C bude považovat zvuk do sluchátka automaticky přesměrován na sluchátka, ale operační systém HoloLens nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C. Mikrofony USB-C lze použít pro volání, záznam atd.

Otevřete aplikaci **Nastavení** a vyberte **systémové**  >  **zvuky**.

![Nastavení zvuku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba **výchozí** znamená, že se externí mikrofon bude používat všude.
>
> Zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a v dalších komunikačních aplikacích, ale pro jiné úkoly se může používat i pole mikrofonu HoloLens.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavit výchozí mikrofon](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Co je podpora mikrofonu Bluetooth?

Technologie HoloLens 2 bohužel v současné době nepodporuje mikrofony Bluetooth.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a ne s HoloLens. Při zapojení jednoho z těchto mikrofonů do HoloLens může dojít ke ztrátě zvuku. Naštěstí je jednoduchá oprava.  

V **Nastavení**  ->    ->  **zvuk** systému explicitně nastavte Vestavěné reproduktory **(zvukový ovladač analogové funkce)** jako **výchozí zařízení**. HoloLens by si mělo pamatovat toto nastavení i v případě, že mikrofon odeberete a znovu připojíte později.

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

Automatické přihlašování návštěvníka se dá spravovat pomocí [vlastních zásad OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) :

- Hodnota identifikátoru URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automatické přihlašování k veřejnému terminálu.   | 1 (Ano), 0 (ne, výchozí)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových nastavení a aplikací Edge v celoobrazovkovém režimu

Když do veřejného terminálu zahrnete i [aplikace, správce](hololens-kiosk.md)IT tuto aplikaci často přidá do veřejného terminálu, ale pomocí ID uživatelského modelu aplikace (AUMID). Vzhledem k tomu, že se aplikace nastavení i aplikace Microsoft Edge považují za nové aplikace a jiné než veřejné terminály aplikací, které používají AUMIDs pro tyto aplikace, bude nutné aktualizovat, aby používaly nové AUMID.

Při úpravách veřejného terminálu, který bude obsahovat nové aplikace, doporučujeme přidat do nového AUMID a ponechat si ho starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou potřebovat dostávat nové zásady, aby mohli používat veřejný terminál jako zamýšlený.

| Aplikace                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stará aplikace nastavení       | HolographicSystemSettings_cw5n1h2txyewy! Aplikace            |
| Nová aplikace nastavení       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplikace |
| Stará aplikace Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nová aplikace Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování celoobrazovkového režimu pro zpracování selhání

Pokud se ve starších buildech zařízení nacházela konfigurace veřejného terminálu, což je kombinace obou uživatelů s přiřazeným přístupem a přiřazeným členem skupiny AAD, v případě neúspěšného určení členství ve skupině AAD by se uživateli zobrazila zpráva "[nic nezobrazuje" v nabídce Start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures).

Od této verze systému Windows se bude beznabídkový režim v případě selhání v celoobrazovkovém režimu skupiny AAD zacházet na globální konfiguraci veřejného terminálu (Pokud je k dispozici).

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nová nastavení identifikátorů URI pro viditelnost nastavení stránky

Ve [Windows holografické verzi 20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali [zásadu Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) , která omezí stránky zobrazené v aplikaci nastavení. PageVisibilityList je zásada, která správcům IT umožňuje buď zabránit zobrazení určitých stránek v aplikaci nastavení systému, aby byla viditelná nebo přístupná, nebo aby to bylo možné udělat pro všechny stránky kromě těch, které jsou uvedené.

Pokud navštívíte [nastavení stránky viditelnost](settings-uri-list.md), můžete najít pokyny k použití tohoto CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšíříme seznam dostupných identifikátorů URI nastavení, které můžou správci IT spravovat. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové aplikace nastavení. Pokud používáte zásady nastavení/PageVisibilityList, přečtěte si následující seznam a podle potřeby upravte své povolené nebo blokované stránky.

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
| Úložiště systémových > > konfigurace rozpoznávání úložiště         | `ms-settings:storagepolicies`                      |
| Čas & jazyka > datum & data                        | `ms-settings:dateandtime`                          |
| Čas & jazyka > klávesnice                           | `ms-settings:keyboard`                             |
| Jazyk > jazyka času &                           | `ms-settings:language`                             |
| Jazyk > jazyka času &                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizace zabezpečení & > resetování & obnovení               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualizované identifikátory URI

Předchozí dva identifikátory URI by nemusely uživatele přímo na označené stránky zablokovat, ale jenom zablokovali stránku hlavní aktualizace. Následující položky byly aktualizovány, aby byly na své stránky přesměrovány:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurace záložní diagnostiky prostřednictvím nastavení aplikace

Uživatel teď v aplikaci nastavení může nakonfigurovat chování [záložní diagnostiky](hololens-diagnostic-logs.md). V aplikaci nastavení přejděte na stránku   ->  **Poradce při potížích** s nastavením ochrany osobních údajů, abyste mohli nakonfigurovat toto nastavení.

> [!NOTE]
> Pokud je pro zařízení nakonfigurovaná zásada MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí pomocí okolních zařízení

Sdílejte věci s okolím zařízení s Windows 10, včetně počítačů i dalších zařízení s HoloLens 2. Můžete si to vyzkoušet v **Nastavení**  ->  **Systémová**  ->  **sdílená prostředí** pro sdílení souborů nebo adres URL z HoloLens do počítače. Další podrobnosti najdete v článku o tom, jak [sdílet věci s blízkými zařízeními ve Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tuto funkci je možné spravovat prostřednictvím [Možnosti připojení/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová trasování diagnostiky operačního systému

Kromě předchozích poradců při potížích v aplikaci nastavení se přidal nový Poradce při potížích s přidáním nové aplikace nastavení pro aktualizace operačního systému. Přejděte na **Nastavení**  ->  **aktualizace &amp; zabezpečení**  >  **vyřešit**  >  **web Windows Update** a vyberte **Spustit**. Díky tomu můžete shromažďovat trasování a při reprodukci problému s aktualizacemi operačního systému pomoct lépe při řešení problémů s vaším IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručování – náhled

V rámci této aktualizace HoloLens nabízí Windows Holografick pro firmy nastavení optimalizace doručování, které snižuje spotřebu šířky pásma pro stahování z více zařízení HoloLens. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: [Optimalizace doručení pro aktualizace Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Následující nastavení jsou povolená jako součást plochy pro správu a [dají se nakonfigurovat z Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik aspektů informací o této nabídce Preview:

- Podpora HoloLens je v této verzi Preview omezená jenom na aktualizace operačního systému.
- Windows Holografick pro firmy podporuje jenom režimy stahování HTTP a stažené soubory z [koncového bodu připojené mezipaměti Microsoftu](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). režimy stahování peer-to-peer a přiřazení skupin se v tuto chvíli nepodporují pro zařízení HoloLens.
- HoloLens nepodporuje optimalizaci nasazení ani doručování pro koncové body Windows Server Update Services.
- Řešení potíží bude vyžadovat buď diagnostiku serveru připojené mezipaměti, nebo shromažďování trasování na HoloLens na HoloLens prostřednictvím   >  **aktualizace nastavení &**  >   **řešení potíží** se zabezpečením  >   **web Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – aktualizovat kontrolní seznam

Tento kontrolní seznam vám pomůže zjistit nové položky, které funkce přidávají v této aktualizaci funkcí, které můžou ovlivnit vaše aktuální konfigurace správy zařízení, nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace pro celoobrazovkový režim

✔️ [**Nový AUMIDs pro nové aplikace v celoobrazovkovém režimu**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

Pokud jste dřív používali aplikaci nastavení nebo aplikaci Microsoft Edge na veřejném terminálu, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si přečetli [nové AUMIDs pro nové aplikace v celoobrazovkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes) níže. Tím se zajistí, že budete mít ve svém terminálu i nadále aplikaci nastavení nebo zadáte novou aplikaci Microsoft Edge. Tyto změny se dají udělat hned a nasazovat na všechna zařízení a v případě aktualizace umožňují hladký přechod.

✔️ [**Automatické přihlášení návštěvníka pro veřejné terminály**](#visitor-auto-logon-for-kiosks): 

Návštěvníci se teď můžou automaticky přihlásit do veřejného terminálu. Toto chování je ve výchozím nastavení zapnuté, ale může být spravované a zakázané.

✔️ [**vylepšené zpracování chyb v celoobrazovkovém režimu**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Pokud není úspěšně zjištěno členství v rámci skupiny AAD přihlášeného uživatele AAD, pak se globální konfigurace veřejného terminálu používá v nabídce Start (Pokud je k dispozici). v opačném případě se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurací, kterou můžete nastavit přímo, může to být tím, že toto nové zpracování bude informovat vaše oddělení podpory, pokud používáte veřejné terminály, protože to může platit pro vaše konfigurace nebo můžete chtít udělat nové úpravy pro vaše přiřazené konfigurace přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti nastavení stránky

✔️ [**nové identifikátory URI nastavení pro viditelnost nastavení stránky**](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte [viditelnost nastavení stránky](settings-uri-list.md) , možná budete chtít upravit existující identifikátory URI, které jste buď povolili, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC
✔️ Pokud jste dříve blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Zkontrolujte prosím následující a použijte poskytnutý vzorový kód.
#### <a name="enable-new-endpoints-for-edge"></a>Povolit nové koncové body pro Edge
✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je například proxy server nebo brána firewall, povolte prosím tyto nové koncové body pro novou aplikaci Microsoft Edge.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ [nakonfigurovat nouzovou diagnostiku](#configuring-fallback-diagnostics-via-settings-app): můžete nakonfigurovat, jestli a kdo může shromažďovat nouzovou diagnostiku.

✔️[sdílet s okolními zařízeními](#share-things-with-nearby-devices): můžete zakázat novou funkci okolního sdílení.

✔️ [Konfigurace nastavení zásad pro nové Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge): Projděte si nově dostupné konfigurace pro Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nový diagnostický nástroj

✔️[nové trasování diagnostiky operačního systému](#new-os-diagnostic-traces): Shromážděte protokoly související s AKTUALIZACEMI operačního systému.

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- [Offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics) bude obsahovat také další informace o zařízení pro sériové číslo a verzi operačního systému.
- Opravuje problém týkající se nasazení obchodních aplikací prostřednictvím zřizovacích balíčků za běhu.
- Opravuje problém týkající se zasílání zpráv o stavu instalace obchodní aplikace.
- Opravuje problém týkající se trvalosti nových balíčků aplikací napříč obnovením zařízení.
- Opravuje problém, který by mohl vést k nesprávným zadávaným symbolům pro japonské zákazníky.
- Vylepšuje odolnost aktualizací operačního systému u předinstalovaných aplikací, jako je třeba Edge. 
- Řeší spolehlivost aktualizace, která má vliv na instalaci Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows holografická verze 20H2 – květen 2021 Update
- Sestavení 19041,1146

Vylepšení a opravy v aktualizaci:
- Tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy, Windows holografickou verzi 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows holografická verze 1903-květen 2021 Update
- Sestavení 18362,1110

Vylepšení a opravy v aktualizaci:
- Tato měsíční aktualizace kvality neobsahuje žádné významné změny. V **tomto sestavení už nebudete dostávat měsíční aktualizace služeb**. Doporučujeme, abyste si vyzkoušeli naše nejnovější buildy, Windows holografické a 21H1 verze.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows holografické verze 20H2 – duben 2021 – aktualizace
- Sestavení 19041,1144

Vylepšení a opravy v aktualizaci:

- Opravuje problém týkající se zasílání zpráv o stavu instalace obchodní aplikace.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows holografická verze 1903 – duben 2021 Update
- Sestavení 18362,1108

Vylepšení a opravy v aktualizaci:

- Řeší problém, při kterém dojde k chybě aplikace nastavení při pokusu o změnu hesla pro místní účet.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows holografická verze 20H2 – březen 2021 – aktualizace
- Sestavení 19041,1140

Vylepšení a opravy v aktualizaci:

- Zákazníci, kteří používají AdvancedPhotoCapture nebo LowLagPhotoCapture k zachycení fotek pomocí HoloLens 2, teď můžou načítat fotoaparát až 3 sekundy od zachycení fotografie.
- Oprava pro nevracení paměti ve službě Device Portal: problém způsobil zvýšené využití paměti službou, která způsobila selhání přidělování paměti jiným aplikacím.
- Opravili jsme problém, kdy se uživatelé zaregistrují do připraveného zavedení, se nemůžou přihlásit k zařízení.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows holografická verze 1903 – březen 2021 – aktualizace
- Sestavení 18362,1102

Vylepšení a opravy v aktualizaci:

- Oprava pro nevracení paměti ve službě Device Portal: problém způsobil zvýšené využití paměti službou, která způsobila selhání přidělování paměti jiným aplikacím.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows holografické verze 20H2 – únor 2021 – aktualizace
- Sestavení 19041,1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém týkající se počátečního nastavení zařízení a aktualizací pro aplikace ze Storu.
- Řeší potíže s upgrady a lety pro pozdější verze HoloLens.
- Z kořenového úložiště eSIM se odebraly nepoužívané předinstalované certifikáty ze zařízení HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows holografická verze 1903 – únor 2021 aktualizace
- Sestavení 18362,1098

Tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows Holografick, verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows holografické verze 20H2 – leden 2021 – aktualizace
- Sestavení 19041,1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spuštění, obnovení a přepínání uživatelů v případě, že zařízení obsahuje mnoho uživatelů.
- Přidání podpory arm32 pro [výzkumný režim](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows holografická verze 1903 – leden 2021 – aktualizace
- Sestavení 18362,1091

Tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows Holografick, verze 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows holografická verze 20H2 – prosince 2020 Update
- Sestavení 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace

**Přidáváme novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** . Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**. Aby nedošlo k narušení podniků, instalační program aplikace nebude v tuto chvíli **k dispozici pro spravovaná zařízení** .  

Zařízení se považuje za spravované, pokud platí **některá** z následujících podmínek:
- [Zaregistrované](hololens-enroll-mdm.md) MDM
- Nakonfigurováno pomocí [zřizovacího balíčku](hololens-provisioning.md)
- [Identita](hololens-identity.md) uživatele je Azure AD

Nyní je možné instalovat aplikace bez nutnosti povolit vývojářský režim ani používat portál zařízení.  Stačí stáhnout (přes USB nebo přes Edge) sadu appx do zařízení a přejít do sady appx v Průzkumníkovi souborů, aby se zobrazila výzva k ukončení instalace.  Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem pomocí možnosti nasazení aplikace LOB pro správu mobilních aplikací, musí být aplikace digitálně podepsané pomocí [nástroje Signer](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a [certifikát použitý k podepsání musí být](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) před nasazením aplikace důvěryhodný pro zařízení HoloLens.

**Pokyny k instalaci aplikace**

1.  Ujistěte se, že se zařízení nepovažuje za spravované.
1.  Ujistěte se, že je zařízení HoloLens 2 zapnuté a připojené k počítači.
1.  Ujistěte se, že jste se přihlásili k zařízení HoloLens 2.
1.  Na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage\Downloads..   Po dokončení kopírování souboru můžete odpojit své zařízení.
1.  V zařízení HoloLens 2 otevřete nabídku Start, vyberte všechny aplikace a spusťte aplikaci Průzkumník souborů.
1.  Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace vybrat toto zařízení jako první a pak přejít na soubory ke stažení.
1.  Vyberte soubor yourapp. appxbundle.
1.  Spustí se instalační program aplikace. Vyberte tlačítko nainstalovat a nainstalujte svou aplikaci.
Nainstalovaná aplikace se po dokončení instalace automaticky spustí.

K otestování tohoto toku najdete ukázkové aplikace na [GitHubu Windows Universal Samples](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) .

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí instalačního programu aplikace](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování teď uchovává sledování v mnoha nových případech, kdy by došlo ke ztrátě výše.  V některých z těchto nových případů se aktualizuje jenom pozice Palm na základě reálné ruky uživatele, zatímco ostatní klouby se odkládají na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako jsou Slapping, throw, scooping a clapping.  Pomáhá taky v případech, kdy se ruka blíží povrchu nebo drží objekt.  Pokud jsou spojky odvoditelné, nastaví se hodnota pro stejnou [přesnost](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) na "Přibližná" místo "vysoká".
- Opravili jsme problém, kdy se pro účty Azure AD Resetování PIN kódu zobrazí chyba něco se nepovedlo.
- Uživatelé by měli při spuštění ET, Iris z nastavení aplikace, nového uživatele nebo informační zprávy o oznámení zobrazovat mnohem méně havárií po spuštění OOBE.
- Uživatelé by měli mít správné časové pásmo vycházející z počátečního nastavení.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows holografická verze 1903 – prosinec 2020 Update
- Sestavení 18362,1088

Tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vyzkoušet si nejnovější verzi Windows holografickou, verze 20H2 – prosinec 2020 a novou funkci instalačního programu aplikace přidanou v buildu.


## <a name="windows-holographic-version-20h2"></a>Windows holografické, verze 20H2
- Sestavení 19041,1128

Systém Windows Holografick, verze 20H2 je teď dostupný a přináší skvělou sadu nových funkcí pro uživatele HoloLens 2 a odborníky na IT. Z automatického oka do Správce certifikátů v nastavení, pro lepší funkčnost celoobrazovkového režimu a nové možnosti nastavení autopilotu. Tato nová aktualizace umožňuje týmům IT podrobnější kontrolu nad konfigurací a správou zařízení HoloLens a nabízí uživatelům ještě více bezproblémového holografického prostředí. 

Tato nejnovější verze je měsíční aktualizace verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo buildu zůstane stejné a web Windows Update bude uvádět měsíční vydání verze 2004 (Build 19041). Můžete se podívat na číslo sestavení v nastavení > o obrazovce, abyste se ujistili, že jste na nejnovějším dostupném buildu 19041.1128 +. Chcete-li provést aktualizaci na nejnovější verzi, otevřete aplikaci nastavení, pokračujte na aktualizace & zabezpečení a klepněte na vyhledat aktualizace. Další informace o tom, jak spravovat aktualizace HoloLens, najdete na [této stránce](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co je nového ve Windows holografickém systému, verze 20H2  

| Funkce                                              | Popis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Podpora pozice automatického oka](hololens-release-notes.md#auto-eye-position-support) | Aktivně vypočítává pozice očí bez uživatelů přes kalibraci sledování očí.   |
| [Správce certifikátů](hololens-release-notes.md#certificate-manager)   | Umožňuje nově jednodušší metody instalovat a odebírat certifikáty z aplikace nastavení.     |
| [Automatické spuštění zřizování z USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Zřizovací balíčky na jednotkách USB se automaticky zobrazí na stránce pro zřizování v OOBE.                                                         |
| [Automatické potvrzení zřizovacích balíčků v OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Zřizovací balíčky se automaticky aplikují během OOBE ze stránky zřizování.                                                         |
| [Automatické zřizování bez použití uživatelského rozhraní](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak kombinovat automatické spouštění zřizování a automaticky potvrzovat dohromady. |
| [Použití autopilotu pomocí Wi-Fiho připojení](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Použijte autopilot ze zařízení Wi-Fi bez potřeby adaptéru sítě Ethernet. |
| [Tenantlockdown CSP a autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po registraci tenanta a použití zásady je možné zařízení zaregistrovat jenom v tomto tenantovi, kdykoli se zařízení resetuje nebo znovu zabliká. |
| [Globální přiřazený přístup](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nová metoda konfigurace pro celoobrazovkový režim s více aplikacemi, který využívá veřejný terminál na úrovni systému a který se vztahuje na všechny.                  |
| [Automatické spuštění aplikace v celoobrazovkovém terminálu s více aplikacemi](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Nastaví aplikaci tak, aby se spouštěla automaticky při přihlášení do celoobrazovkového režimu s více aplikacemi.                                                        |
| [Změny chování celoobrazovkového režimu pro zpracování selhání](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Chyba celoobrazovkového režimu teď má omezující zálohu.                                                                                                |
| [Zásady HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nové zásady pro HoloLens     |
| [Ukládání členství ve skupině Azure AD do mezipaměti pro celoobrazovkový terminál](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nové zásady umožňují uživatelům používat mezipaměť členství ve skupině pro použití celoobrazovkového režimu offline pro nastavený počet dnů.                                        |
| [Nové zásady omezení pro zařízení pro HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Zásady správy zařízení s povoleným nově povoleným pro HoloLens 2                                                                                |
| [Nové zásady napájení pro HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nově podporované zásady pro nastavení časového limitu napájení.  |
| [Aktualizovat zásady](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nově povolené zásady umožňují kontrolu aktualizací.           |
| [Viditelnost stránky s povoleným nastavením pro HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Zásady, které vám umožní vybrat, které stránky se zobrazují v aplikaci nastavení.             |
| [Režim výzkumu](hololens-release-notes.md#research-mode) | Použití výzkumného režimu na HoloLens 2. |
| [Zvýšení délky záznamu](hololens-release-notes.md#recording-length-increased) | Nahrávky MRC už nejsou omezené na 5 minut. |
| [Vylepšení a opravy v aktualizaci](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Další opravy v aktualizaci.   |

### <a name="auto-eye-position-support"></a>Podpora pozice automatického oka

V HoloLens 2 se poloha oka povoluje přesnou polohu hologramu, pohodlné zobrazení a vylepšená kvalita zobrazení. Pozice oka se vypočítávají interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel přešel přes kalibraci sledování očí, a to i v případě, že prostředí nemusí vyžadovat pohledu.

**Pozice pro automatické oči (AEP)** umožňuje těmto scénářům, které jsou v rámci interakce k dispozici, způsob výpočtu očí pro uživatele. Pozice automatického oka začne pracovat na pozadí automaticky od okamžiku, kdy uživatel zařízení umístí. Pokud uživatel nemá k dispozici kalibraci pro sledování očí, začne poloha automatického oka začínat umístěním očí uživatele do zobrazovacího systému po dobu zpracování 20-30 sekund. Uživatelská data se v zařízení neukládají, takže se tento proces opakuje, pokud uživatel odchází a znovu ho zaznamená nebo pokud se zařízení restartuje nebo se probudí z režimu spánku.

K dispozici je několik změn chování systému s funkcí pozice automatického oka, když uživatel do zařízení vloží nekalibrovaného uživatele. V tomto kontextu se nekalibrovaný uživatel odkazuje na někoho, kdo předtím neprošlý procesem kalibrace sledování očí na zařízení.

| Aktivní aplikace | Předchozí chování | Chování z Windows holografické verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace, která není povolená pohledu, nebo holografické prostředí |Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Výzva k kalibraci sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke pohledumu streamu očí. |

Pokud uživatel přejde z aplikace s povoleným pohledu na jednu, která přistupuje k datům pohledu, zobrazí se výzva k kalibraci. 

Všechny ostatní chování systému budou podobné jako v případě, kdy aktuální uživatel nemá aktivní sledování očí. Například ruční gesto spuštění nebude povoleno. Při počátečním nastavení se neprojeví žádné změny v prostředí před prvním nastavením.

Pro prostředí, která vyžadují pohledu data nebo velmi přesné umístění na hologram, doporučujeme nekalibrovaným uživatelům spustit kalibraci sledování očí. Je přístupná z výzvy k kalibraci sledování očí nebo spuštěním aplikace nastavení z nabídky Start a následným výběrem možnosti **kalibrace systémových > > kalibraci očí > spuštění kalibrace očí**.

Tyto informace se dají najít později s [dalšími informacemi o kalibraci](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené nástroje pro auditování, diagnostiku a ověřování pro zabezpečení a dodržování předpisů zařízení prostřednictvím nového Správce certifikátů Tato funkce vám umožní nasazovat, řešit potíže a ověřovat certifikáty ve velkém měřítku v komerčních prostředích.

Ve Windows Holographic verze 20H2 přidáváme Správce certifikátů v aplikaci Nastavení HoloLens 2. Přejděte na **Nastavení > Update & Security > Certificates**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů v zařízení. S novým Správcem certifikátů teď správci a uživatelé vylepšili auditování, diagnostiku a ověřování, aby zajistili, že zařízení zůstanou zabezpečená a vyhovující. 

-   **Auditování:** Možnost ověřit, že je certifikát správně nasazený, nebo ověřit, že byl správně odebrán. 
-   **Diagnostika:** Když nastanou problémy, ověření, že v zařízení existují příslušné certifikáty, šetří čas a pomáhá s řešením potíží. 
-   **Ověření:** Ověření, že certifikát slouží zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Pokud chcete rychle najít konkrétní certifikát v seznamu, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé mohou také přímo vyhledat certifikát. Pokud chcete zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na **Informace.** 

Instalace certifikátu aktuálně podporuje soubory .cer a .crt. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  Všichni ostatní uživatelé se instaluje jenom do aktuálního uživatele. Uživatelé mohou odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.

#### <a name="to-install-a-certificate"></a>Instalace certifikátu: 

1.  Připojte HoloLens 2 k počítači.
1.  Umístěte soubor certifikátu, který chcete nainstalovat, do umístění na holoLens 2.
1.  Přejděte na **Nastavení App > Update & Security > Certificates** a vyberte Nainstalovat certifikát.
1.  Klikněte **na Importovat** soubor a přejděte do umístění, do něj které jste certifikát uložili.
1.  Vyberte **Store Location (Umístění obchodu).**
1.  Vyberte **Úložiště certifikátů.**
1.  Klikněte na **Install** (Nainstalovat).

Certifikát by teď měl být nainstalovaný na zařízení.

#### <a name="to-remove-a-certificate"></a>Odebrání certifikátu: 
1. Přejděte na **Nastavení App > Update and Security > Certificates**.
1. Ve vyhledávacím poli vyhledejte certifikát podle názvu.
1. Vyberte certifikát.
1. Klikněte na **Odebrat.**
1. Po **zobrazení** výzvy k potvrzení vyberte Ano.

![Prohlížeč certifikátů v aplikaci Nastavení](images/certificate-viewer-device.jpg)

![Obrázek znázorňující, jak pomocí uživatelského rozhraní certifikátu nainstalovat certifikát](images/certificate-device-install.jpg)

Tyto informace najdete později [na nové stránce Správce certifikátů](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňující menší interakci uživatelů, když se během spuštění počítače používají jednotky USB se zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek ručně spustit obrazovku zřizování během spuštění při spuštění počítače. Uživatelé teď mohou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na jednotce úložiště USB. 

1. Připojte jednotku USB se zřizovacím balíčkem během prvního interagovatelného okamžiku prvního ZOBE.
1. Až bude zařízení připravené ke zřízení, automaticky se otevře výzva se stránkou zřizování. 

Poznámka: Pokud je usb flash disk při spouštění zařízení připojený k napájení, OOBE provede výčet stávajícího paměťového zařízení USB a bude sledovat, jestli se neschytí další zařízení.

Další informace o použití zřizovacích balíčků během OOBE najdete v dokumentaci ke [zřizování HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Další informace o [automatickém spouštění zřizování](hololens-provisioning.md#auto-launch-provisioning-from-usb) z USB najdete v dokumentaci ke zřizování HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacího balíčku v OOBE
- Automatizovaný proces, který umožňuje menší interakci uživatelů, a když se zobrazí stránka zřizovací balíček, automaticky použije všechny uvedené balíčky.

Když se zobrazí hlavní obrazovka zřizování, OOBE odpočítá 10 sekund, než automaticky začne používat všechny zřizovací balíčky. Do 10 sekund od ověření [balíčků,](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) které očekávali, je uživatelé stále mohou potvrdit nebo zrušit.

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní
- Kombinované automatické procesy pro menší interakce zařízení pro zřizování 

Zkombinováním automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovacího balíčku může uživatel zřídit zařízení HoloLens 2 automaticky bez použití uživatelského rozhraní zařízení nebo dokonce s jeho používáním. Můžete dál používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení více zařízení najednou ve stejné oblasti. 

1. [Pomocí nástroje](hololens-provisioning.md) Windows Configuration Designer vytvořte [zřizovací balíček.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Vytvořte flash disk HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) na [build 19041.1361 nebo novější.](https://aka.ms/hololens2previewdownload) 
1. Po [dokončení rozšířeného](https://www.microsoft.com/store/productId/9P74Z35SFRS8) průvodce obnovením zařízení odpojte kabel USB-C. 
1. Připojte jednotku USB k zařízení.
1. Když se zařízení HoloLens 2 spustí do OOBE, automaticky zjistí zřizovací balíček na USB disku a spustí stránku zřizování.
1. Po 10 sekundách zařízení automaticky použije zřizovací balíček. 

Vaše zařízení je teď nakonfigurované a [zobrazí obrazovku Provisioning Successful (Úspěšné zřizování).](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Použití Autopilotu s Wi-Fi připojením
- Odebrání potřeby adaptérů USB-C k ethernetovému omezení hardwarových potřeb tím, že umožňuje, aby Autopilot fungoval Wi-Fi připojených zařízeních.

Když teď během OOBE připojíte HoloLens 2 k Wi-Fi, OOBE zkontroluje profil Autopilotu pro zařízení. Pokud ho najdete, použije se k dokončení zbývající části toku připojení a registrace AAD. Jinými slovy, použití ethernetu na USB-C nebo Wi-Fi na adaptér USB-C už není povinné, ale i nadále fungují, pokud jsou k dispozici na začátku OOBE. Přečtěte si další [informace o Autopilotu pro zařízení HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a Autopilot
- Udržuje zařízení v tenantovi organizace tím, že je uzamyká pro tenanta i přes resetování zařízení nebo koliázi. S dalším zabezpečením tím, že prostřednictvím zřizování neumožníte vytvoření účtu v . 

Zařízení HoloLens 2 teď podporují TenantLockdown CSP od [verze Windows Holographic 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby se HoloLens 2 váže na registraci MDM jenom pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (původně nastavená) na HoloLens 2, zůstane tato hodnota na zařízení i přes znovu blikající, aktualizace operačního systému atd. 

Jakmile je u HoloLens 2 uzel RequireNetworkInOOBE tenantaLockdown nastaven na true, po připojení k síti počká OOBE po neomezenou dobu na úspěšné stažení a použití profilu Autopilot. 

Jakmile je u HoloLens 2 uzel RequireNetworkInOOBE tenantaLockdownu nastavený na true, jsou v OOBE zakázané následující operace: 
- Vytvoření místního uživatele pomocí zřizování modulu runtime 
- Provádění operace připojení k Azure AD prostřednictvím zřizování modulu runtime 
- Výběr vlastníka zařízení v prostředí pro OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak to nastavit pomocí Intune? 
1. Vytvořte vlastní konfigurační profil zařízení OMA URI a jako uzel RequireNetworkInOOBE zadejte true, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamykací funkce tennant přes OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Vytvořte člena zařízení HoloLens 2 skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení TenantLockdown RequireNetworkInOOBE na HoloLens 2? 
1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše. 

1. Vytvořte vlastní konfigurační profil zařízení založený na OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže. Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Vytvořte člena zařízení HoloLens 2 skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud se profil Autopilotu nepřiřazený v HoloLens po nastavení TenantLockdownu na hodnotu true? 
OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown. 

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

Tyto informace teď najdete společně se zbytkem Autopilotu v části [Tenantlockdown CSP a Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim
- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije režim veřejného terminálu.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálu s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Přečtěte si o této nové funkci podrobně v globálním veřejného terminále [holoLens s globálním přiřazeným přístupem.](hololens-global-assigned-access-kiosk.md)

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

V předchozích verzích, kdy došlo k selháním při použití beznaiosku, se holoLens používal k zobrazení všech aplikací v nabídce Start. Teď ve Windows Holographic verze 20H2 v případě selhání se v nabídce Start nezobrazí žádné aplikace, jak je znázorněno níže: 

![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Zásady HoloLens
- Možnosti správy zařízení speciálně pro HoloLens vytvořené pro správu zařízení. 

Pro zařízení HoloLens 2 ve Windows Holographic verze 20H2 byly vytvořeny nové zásady hybridní reality. Mezi nová říditelná nastavení patří nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v záznamech hybridní reality, nastavení, kdy je možné shromažďovat diagnostiku, a mezipaměť členství ve skupinách AAD.  

| Nová zásada HoloLens                                | Description                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Umožňuje zakázat tlačítka jasu, takže se jeho stisknutí nezmění na brightness.       | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Umožňuje zakázat tlačítka hlasitosti, aby se po stisknutí tlačítka neměňte svazek.               | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | Zakáže mikrofon, takže na HoloLens 2 není možný žádný zvukový záznam.                      | 1 Ano, 0 Ne (výchozí)                                                |
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
1. Vytvořte profil konfigurace zařízení pro beznaiosk cílení na skupiny Azure AD a přiřaďte ho k zařízením HoloLens. 
1. Vytvořte vlastní konfiguraci zařízení založenou na OMA URI, která nastaví tuto hodnotu zásady na požadovaný počet dní (> 0) a přiřadí ji k zařízením HoloLens. 
    1. Do textového pole OMA-URI by se měla zadat hodnota URI ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays.
    1. Hodnota může být v rozmezí od minimálního do maximálního povoleného.
1. Zaregistrujte zařízení HoloLens a ověřte, že se na zařízení použijí obě konfigurace. 
1. Nechte uživatele Azure AD 1 přihlásit se, když je k dispozici internet, po úspěšném potvrzení přihlášení uživatele a úspěšného členství ve skupině Azure AD se vytvoří mezipaměť. 
1. Uživatel Azure AD 1 teď může HoloLens pře offline a používat ho pro beznaioskový režim, pokud hodnota zásad umožňuje počet dní X. 
1. Kroky 4 a 5 je možné opakovat pro libovolného jiného uživatele Azure AD N. Klíčovým bodem je, že každý uživatel Azure AD se musí přihlásit k zařízení pomocí internetu, takže aspoň jednou můžeme určit, že jsou členem skupiny Azure AD, na kterou je cílem konfigurace veřejného terminálu. 
 
> [!NOTE]
> Dokud se pro uživatele Azure AD neprovádí krok 4, bude docházet k chování při selhání uvedeném v odpojených prostředích. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nové zásady omezení zařízení pro HoloLens 2
- Umožňuje uživatelům spravovat konkrétní zásady správy zařízení, jako je blokování přidávání nebo odebírání zřizových balíčků.

Nově povolené zásady, které umožňují více možností správy zařízení HoloLens 2 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [Vzdálené zamykací zařízení](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Tyto dvě nové zásad pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> S ohledem [na RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)bude HoloLens podporovat jenom konfiguraci ./Vendor/MSFT/RemoteLock/Lock. Konfigurace týkající se kódu PIN, jako je resetování a obnovení, se nepodporují.

### <a name="new-power-policies-for-hololens-2"></a>Nové zásady napájení pro HoloLens 2
- Další možnosti pro, kdy HoloLens uspí nebo zamkne prostřednictvím zásad napájení. 

Tyto nově přidané zásady umožňují správcům řídit stavy napájení, jako je časový limit nečinnosti. Další informace o jednotlivých zásadách si můžete přečíst kliknutím na odkaz pro jednotlivé zásady.

|     Odkaz na dokumentaci k zásadám                |     Poznámky                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se má použít v nástroji Windows Configuration Designer, tj.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové služby pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Pro zajištění konzistentního prostředí v HoloLens 2 se ujistěte, že hodnoty pro DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery jsou nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti [o moderním pohotovostním režimu](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) najdete v článku o časovačích nečinnosti pro zobrazení, režim spánku a hibernaci.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nově povolené zásady aktualizace pro HoloLens
- Další možnosti pro instalaci aktualizací nebo zakázání tlačítka Pozastavit aktualizace pro zajištění aktualizací.

Na zařízeních HoloLens 2 jsou teď povolené tyto zásady aktualizace:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Aktualizace/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Úplné podrobnosti o těchto zásadách aktualizací a jejich použití pro zařízení HoloLens najdete tady v tématu [Správa aktualizací HoloLens.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Povolená viditelnost stránky Nastavení pro HoloLens 2
- Větší ovládací prvek uživatelského rozhraní v aplikaci Nastavení, který může být zaměnit za zobrazení omezeného výběru stránek.

Teď jsme povolili zásadu, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci Nastavení systému, nebo to udělat pro všechny stránky kromě těch, které jsou zadané. Pokud chcete zjistit, jak tuto funkci plně přizpůsobit, klikněte na následující odkaz.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Informace o tom, která nastavení stránky můžete přizpůsobit na HoloLens 2, najdete na naší stránce [Identifikátory URI nastavení.](settings-uri-list.md) 
 
![Snímek obrazovky s úpravami aktivních hodin v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu
V režimu Research Mode se HoloLens 2 stává nástroj pro výzkum počítačového zpracování obrazu. V porovnání s předchozími edicemi má Režim výzkumu pro HoloLens 2 následující výhody:
-   Kromě senzorů vystavených v režimu výzkumu HoloLens (1. generace) teď poskytujeme přístup senzorů IMU, včetně akcelerometru, krátoboru a krátometru.
-   HoloLens 2 poskytuje nové možnosti, které je možné používat společně s režimem Research Mode. Konkrétně přístup k rozhraním API pro ruční sledování a sledování očí, která doručují bohatší sadu experimentů.

Výzkumníci teď mají na svých zařízeních HoloLens možnost povolit výzkumný režim pro přístup ke všem těmto externím datovým proudům nezpracovaných obrazových senzorů. Režim research pro HoloLens 2 také poskytuje přístup k odečtům akcelerometru, krátoboru a krátometru. V rámci ochrany osobních údajů uživatelů nejsou nezpracované obrázky z fotoaparátů pro sledování očí dostupné prostřednictvím režimu výzkumu, ale směr pohledu je k dispozici prostřednictvím stávajících rozhraní API.

Další technické podrobnosti [najdete v dokumentaci k](https://docs.microsoft.com/windows/mixed-reality/research-mode) režimu výzkumu.

### <a name="recording-length-increased"></a>Zvýšení délky záznamu
Z důvodu zpětné vazby od zákazníků jsme zvýšili délku záznamu zachytávání [hybridní reality.](holographic-photos-and-videos.md) Zachytávání hybridní reality už nebude ve výchozím nastavení omezené na 5 minut, ale místo toho vypočítá maximální délku záznamu na základě dostupného místa na disku. Zařízení odhadne maximální dobu trvání záznamu videa na základě dostupného místa na disku až do 80 % celkového místa na disku.

> [!NOTE]
> HoloLens použije výchozí délku záznamu videa (5 minut), pokud dojde k jedné z následujících akcí:
> - Odhadovaná maximální doba trvání záznamu je menší než výchozích 5 minut.
> - Dostupné místo na disku je méně než 20 % celkového místa na disku.

Všechny požadavky najdete v dokumentaci k [holografickým fotografiím a videím.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:
- Další obrazovky v OOBE jsou teď v tmavém režimu.
- Další informace by měly odkazovat na nejnovější prohlášení o zásadách ochrany osobních údajů online.
- Byl vyřešen problém, kdy uživatelé nemohli zřídit profily VPN prostřednictvím zřizovacích balíčků.
- Opravili jsme problém s konfigurací proxy serveru pro připojení VPN.
- Aktualizace zásad pro zákaz výčtu funkcí USB prostřednictvím MDM pro NCM pro AllowUsbConnection
- Byl vyřešen problém, který znemožňoval, aby se zařízení HoloLens v Průzkumník souborů přes protokol MTP (Media Transfer Protocol) při nastavení zařízení jako veřejného terminál s jednou [aplikací.](hololens-kiosk.md) Mějte na paměti, že MTP (a připojení USB obecně) je stále možné zakázat pomocí zásad [AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Opravili jsme problém, kdy se ikony v nabídka Start správně škálují v beznaiosku.
- Opravili jsme problém kvůli tomu, že ukládání do mezipaměti HTTP narušuje režim veřejného terminálů cílený na skupiny Azure AD.
- Opravili jsme problém, kdy uživatelé nemohli po povolení vývojářského režimu se zřizovacími balíčky použít tlačítko Párovat, pokud nepovolili a nepovolili vývojářský režim.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic verze 1903 – aktualizace z listopadu 2020
- Build 18362.1085

Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si nejnovější verzi buildu Windows Holographic verze 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic verze 2004 – aktualizace z října 2020
- Build 19041.1124
 
Vylepšení a opravy v aktualizaci:

- Odebrali jsme nepotřebnou kontrolu, která způsobila chybu systému modulu runtime.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic verze 1903 – aktualizace z října 2020
- Build 18362.1081

Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze září 2020
- Build 19041.1117

Vylepšení a opravy v aktualizaci:

- Řeší problém, který Visual Studio ladění aplikace, když se v souboru appxmanifest nachází SupportsMultipleInstances="true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která řeší selhání detekce internetu přes síťový proxy server. NCSI může k detekci připojení k internetu použít proxy server počítače a proxy server pro každý profil. NcSI bude v budoucí verzi podporovat proxy pro uživatele.
- Ve většině Windows Mixed Reality zařízení je vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze HoloLens 2 však zarovnaly vektor tak, aby byl perpend se zobrazením panelů, což je posunutý o několik stupňů dolů vzhledem k ideální orientaci. Novější verze HoloLens 2 to opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.
- Tato verze obsahuje opravu pro zlepšení kvality časového razítka zvuku, která může přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic verze 1903 – aktualizace ze září 2020
- Build 18362.1079

Vylepšení a opravy v aktualizaci:

- Ve většině Windows Mixed Reality zařízení je vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze HoloLens 2 však zarovnaly vektor tak, aby byl perpend se zobrazením panelů, což je posunutý o několik stupňů dolů vzhledem k ideální orientaci. Novější verze HoloLens 2 to opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze srpna 2020
- Build 19041.1113

Vylepšení a opravy v aktualizaci:

- Aplikace Nastavení už uživatele nebude sledovat v prostředí zápisu Iris nebo sledování očí.
- Opravili jsme chybu, kdy se při použití zřizovacího balíčku během spuštění počítače, který přejmenovává zařízení a provádí další akce (například připojování k síti), nepodařilo provést další akce po restartování zařízení kvůli přejmenování.
- Úprava barevného schématu toků počátečního nastavení zařízení za účelem zlepšení vizuální kvality

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic verze 1903 – aktualizace ze srpna 2020
- Build 18362.1074

Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic verze 2004 – aktualizace z července 2020
- Build 19041.1109

Vylepšení a opravy v aktualizaci:

- Vývojáři si teď mohou vybrat mezi povolením nebo zakázáním Portál zařízení vyžadovat zabezpečené připojení.
- Vylepšili jsme spolehlivost spouštění aplikací po aktualizacích operačního systému.
- Změna výchozího jasu doručené pošty na 100 %.
- Byl vyřešen problém s předáváním HTTPS pro Portál zařízení s Windows na HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic verze 1903 – aktualizace z července 2020
- Build 18362.1071

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který mohl způsobovat, že hologramy při ztrátě nebo obnovení sledování zmizely v aplikacích Unity.
- Opravili jsme problém, který způsoboval, že se výhradní aplikace HoloLens při použití emulátoru HoloLens s hardwarovou akcelerací na určitých zařízeních vrací zpět do prostředí.
- Byl vyřešen problém týkající se předávání HTTPS pro Portál zařízení s Windows na HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic verze 2004 – aktualizace z června 2020
- Build 19041.1106

Vylepšení a opravy v aktualizaci:

- Vlastní záznamníky MRC teď mají nové výchozí hodnoty pro určité vlastnosti, pokud nejsou zadané.
  - On the *MRC Video Effect*:.
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Imerzivní náhlavní souprava))
  - Zvukový *efekt MRC:*
    - LoopbackGain (aktuální hodnota "App Audio Gain" na Záznam hybridní reality stránce Portál zařízení s Windows)
    - MicrophoneGain (aktuální hodnota Mic Audio Gain na Záznam hybridní reality stránce Portál zařízení s Windows)
- Opravili jsme chybu, která vylepšuje kvalitu zvuku ve scénářích zachycení hybridní reality. Konkrétně by tato oprava měla eliminovat potíže se zvukem v nahrávce, když se **zobrazí** nabídka Start.
- Vylepšená stabilita hologramů v zaznamenaných videích
- Vyřešili jsme problém, kdy zachytávání hybridní reality nemohlo po několika dnech v pohotovostním stavu nahrát video.
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení visoru, a to i v případě, že bylo povolené nastavení Spustit na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Když k Portál zařízení přes Wi-Fi připojení, webový prohlížeč může přístup k bránit z důvodu neplatného certifikátu. Prohlížeč může nahlásit chybu typu "ERR_SSL_PROTOCOL_ERROR", i když byl certifikát zařízení dříve důvěryhodný. V takovém případě nemůžete postupovat k Portál zařízení, protože neexistuje možnost ignorovat upozornění zabezpečení. Tato aktualizace vyřešila problém. Pokud byl certifikát zařízení dřív stažený a důvěryhodný na počítači kvůli odebrání upozornění zabezpečení prohlížeče a dojde k chybě SSL, musí se nový certifikát stáhnout a důvěřovat, aby se využívaly výstrahy zabezpečení prohlížeče.
- Umožnění vytvoření balíčku pro zřizování za běhu, který může nainstalovat aplikaci pomocí balíčků MSIX.
- Do **Nastavení**  >  **systémových**  >  **hologramů** se přidalo nastavení, které umožňuje uživatelům automaticky odebrat všechny hologramy ze smíšené reality, když se zařízení vypíná.
- Opravili jsme problém, který způsobil, že aplikace HoloLens se změnou jejich formátu v pixelech vykreslí černou v emulátoru HoloLens.
- Opravili jsme chybu, která způsobila selhání během přihlašování Iris.
- Opravili jsme problém se stahováním opakovaného úložiště pro už aktuální aplikace.
- Opravili jsme chybu, která zabraňuje moderním aplikacím v otevírání Microsoft Edge opakovaně.
- Opravili jsme problém se spuštěním aplikace fotky v počátečním spuštění po aktualizaci verze 1903.
- Vylepšený výkon a spolehlivost.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows holografická verze 1903 – června 2020 – aktualizace
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
- Opravili jsme problém, který způsobil, že aplikace HoloLens se změnou jejich formátu v pixelech vykreslí černou v emulátoru HoloLens.
- Opravili jsme problém týkající se spuštění aplikace Fotky při počátečním spuštění po aktualizaci verze 1903.

## <a name="windows-holographic-version-2004"></a>Systém Windows Holografick, verze 2004  
- Build-19041,1103

2020 hlavní aktualizace softwaru pro HoloLens 2, *Windows holografická verze 2004* obsahuje hostitele zajímavých nových funkcí, jako je například podpora pro Windows autopilot, tmavý režim aplikace, podpora sběrnice USB Ethernet pro 5g/LTE hotspotů a mnoho dalšího. Chcete-li provést aktualizaci na nejnovější verzi, otevřete aplikaci **Nastavení**   , pokračujte na  **aktualizace & zabezpečení** a vyberte tlačítko  **Vyhledat aktualizace**   . 

|             Funkce                              |          Popis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Předběžná konfigurace a bezproblémové nastavení nových zařízení pro produkční prostředí pomocí automatického pilotního projektu Windows                 |
|       Podpora FIDO 2                             |          Podpora klíčů zabezpečení FIDO2 pro zajištění rychlého a zabezpečeného ověřování pro sdílená zařízení            |
|       Vylepšené zřizování                      |          Bezproblémové použití zřizovacího balíčku z jednotky USB na HoloLens                              |
|       Stav instalace aplikace                 |          Podívejte se na stav instalace v aplikaci nastavení pro aplikace, které byly vloženy do HoloLens 2 přes MDM.               |
|       Poskytovatelé konfiguračních služeb (CSP)   |          Přidání nových poskytovatelů konfigurační služby za účelem vylepšení možností řízení správy                 |
|       Podpora sběrnice USB 5G/LTE                       |          Rozšířená funkce USB Ethernet umožňuje podporu pro 5G/LTE.                                    |
|       Tmavý režim aplikace                              |          Tmavý režim aplikace dostupný pro aplikace, které podporují tmavé i lehké režimy, což zlepšuje možnosti zobrazení        |
|       Hlasové příkazy                             |          Podpora dalších systémových hlasových příkazů pro řízení ruky s HoloLens                           |
|       Vylepšení sledování ruky                 |          Vylepšení ručního sledování usnadňuje tlačítka a 2D SLAT interakce                        |
|       Vylepšení a opravy kvality                 |          Různá vylepšení výkonu a spolehlivosti systému napříč platformou                            |

### <a name="support-for-windows-autopilot"></a>Podpora pro Windows autopilot

Windows autopilot pro HoloLens 2 umožňuje, aby prodejní kanál zařízení předem zaregistroval HoloLens do svého tenanta Intune. Jakmile zařízení dorazí, budou připravená na samoobslužné nasazení jako sdílená zařízení v rámci vašeho tenanta. Aby bylo možné využít výhody samoobslužného nasazení, musí se zařízení připojit k síti během první obrazovky v instalačním programu pomocí technologie USB-C-to-Ethernet.

Poté, co uživatel spustí proces automatického nasazení autopilotu, proces provede následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD).
1. Pomocí služby Azure AD zaregistrujete zařízení v Microsoft Intune (nebo jiné službě MDM).
1. Stáhněte si zásady, certifikáty a síťové profily zaměřené na zařízení.
1. Zřídí zařízení.
1. Prezentovat přihlašovací obrazovku uživateli

Další informace najdete v [Průvodci hodnocením Windows autopilot pro HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Obraťte se na svého správce účtu, abyste se připojili k programu autopilot Preview nyní. Zařízení, která jsou připravena k autopilotu, začnou brzy dodávat.*

### <a name="fido2-security-key-support"></a>Podpora klíče zabezpečení FIDO2

Někteří uživatelé sdílejí zařízení HoloLens s ostatními v pracovním nebo školním prostředí. Proto je důležité, aby uživatelé mohli snadno bez psaní dlouhých uživatelských jmen a hesel. Rychlá identita online (FIDO) umožňuje všem uživatelům ve vaší organizaci (Azure AD tenant) bezproblémové přihlašovat se k HoloLens bez zadání uživatelského jména nebo hesla.

Klíče zabezpečení FIDO2 jsou "nepřesné" metody ověřování bez hesla založené na standardech, které mohou být v libovolném tvaru. FIDO je otevřený standard pro ověřování neheslem. Umožňuje uživatelům a organizacím přihlašovat se ke svým prostředkům bez uživatelského jména nebo hesla. Místo toho používají externí klíč zabezpečení nebo klíč platformy integrovaný do zařízení.

Informace o tom, jak začít, najdete v tématu [Povolení přihlášení k bezpečnostnímu klíči bez hesla](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Vylepšená registrace MDM prostřednictvím zřizovacího balíčku

Zřizovací balíčky umožňují nastavovat konfiguraci HoloLens prostřednictvím konfiguračního souboru, a ne prostřednictvím připraveného prostředí HoloLens. Dříve musely být zřizovací balíčky zkopírovány do interní paměti HoloLens. Teď můžou být na jednotce USB, aby je bylo snazší znovu použít na více zařízeních HoloLens a můžete zařízení zřizovat paralelně. Zřizovací balíčky teď také podporují pole pro registraci ve správě zařízení, takže se po zřízení neprovádí ruční instalace.

Vyzkoušejte:

1. Stáhněte si nejnovější verzi Windows Configuration designeru z Windows Storu do svého počítače.
1. Vyberte **zřídit zařízení HoloLens**  >  **zřídit zařízení HoloLens 2**.
2. Sestavte konfigurační profil. Pak zkopírujte všechny soubory, které byly vytvořeny na paměťové zařízení USB-C.
3. Připojte zařízení USB-C k jakémukoli čerstvě blikajícímu HoloLens. Potom stisknutím tlačítka **hlasitosti dolů**  +   použijte balíček zřizování.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodní aplikace

Nasazení a Správa aplikací MDM pro obchodní aplikace jsou klíčové pro HoloLens. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. V této verzi jsme přidali další podrobnosti v **Nastavení**  >  **účty**  >  **přístup do práce nebo do školy**  >  klikněte na informace **o účtu**  >  .

### <a name="additional-csps-and-policies"></a>Další zprostředkovatelé CSP a zásady

[Zprostředkovatel kryptografických služeb (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravy nebo odstranění nastavení konfigurace na zařízení. V této verzi přidáváme podporu pro další zásady, aby bylo zvýšení správců ovládacích prvků nad nasazenými zařízeními HoloLens. Seznam CSP, který podporuje HoloLens, najdete v tématu [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novinka v této verzi:

**Zprostředkovatel CSP pro zásady** 

Poskytovatel služeb konfigurace zásad umožňuje podniku nakonfigurovat zásady na zařízeních s Windows. V této verzi jsme přidali nové zásady pro HoloLens, které jsou tady uvedené. Další informace najdete v tématu [Zprostředkovatelé CSP, které podporuje HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

Poskytovatel konfigurační služby NetworkQoSPolicy vytváří zásady QoS (Quality of Service) sítě. Zásady QoS provádějí sadu akcí u síťového provozu na základě sady odpovídajících podmínek. Další informace najdete v tématu [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Rozšířená podpora ethernetového připojení USB pro zařízení připojená přes 5G/LTE

Byla přidána podpora pro povolení určitých mobilních širokopásmového zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když nejsou připojená k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě jako** další ethernetové připojení. (Mobilní širokopásmová zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s velkou šířkou pásmaWi-Fi není dostupná a Wi-Fi není dostatečně výkonný. Další informace o podporovaných zařízeních USB najdete v tématu Připojení k zařízením Bluetooth a [USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Vylepšení sledování rukou

Tato verze obsahuje několik vylepšení ručního sledování:

- **Bodování představuje stabilitu:** Systém teď odolá odsouvání indexování, když ho uchytává šedě. Tato změna zvyšuje přesnost při nabízení tlačítek, psaní, posouvání obsahu a dalších. 
- **Menší nechtěné klepnutí ve vzduchu:** Vylepšili jsme detekci gesta klepnutí ve vzduchu. V několika běžných scénářích, například když pustíte ruce na stranu, je teď méně náhodných aktivací.
- **Spolehlivost uživatelského přepínače:** Systém je teď při aktualizaci velikosti ruky při sdílení zařízení rychlejší a spolehlivější.
- **Menší krádež rukou:** Vylepšili jsme zpracování případů, kdy senzory mají více než dvě ruce. Pokud spolu úzce pracuje více lidí, je teď mnohem menší pravděpodobnost, že sledovaná ruky "přeskočí" z uživatele do ruky někoho jiného ve scéně.
- **Spolehlivost systému:** Opravili jsme problém, který způsobl, že při vysokém zatížení zařízení přestalo fungovat sledování rukou.

### <a name="dark-mode"></a>Tmavý režim

Mnoho aplikací pro Windows teď podporuje tmavý i světlý režim. Uživatelé HoloLens 2 mohou zvolit výchozí režim pro aplikace, které podporují obojí. Po aktualizaci je výchozí režim aplikace "tmavý", ale toto nastavení můžete snadno změnit: Přejděte na **Nastavení** Barvy systému Zvolte  >    >    >  **výchozí režim aplikace.** 

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

![Dlaždicová okna v tmavém režimu](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systémové hlasové příkazy

Hlasové příkazy teď můžete používat s libovolnou aplikací na zařízení. Další informace najdete v tématu [Použití hlasu k ovládání HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Další informace najdete [v tématu Podporované jazyky pro HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### <a name="cortana-updates"></a>Aktualizace Cortany

Aktualizovaná aplikace se integruje s Microsoft 365, která vám pomůže udělat více napříč zařízeními (v současné době US-English nástroji). Na HoloLens 2 už Cortana nepodporuje určité příkazy specifické pro zařízení, jako je úprava svazku nebo restartování. Tyto možnosti teď podporují nové systémové hlasové příkazy. Další informace o nové aplikaci Cortany najdete na našem [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  
- Zavedli jsme systém aktivního zobrazení s tekutou displeji. Tato funkce zlepšuje stabilitu a zarovnání hologramů. Nyní zůstanou na místě, když přesunete hlavičku ze strany na stranu.
- Opravili jsme chybu, Wi-Fi se pravidelně přerušilo streamování do HoloLens. Pokud aplikace indikuje, že potřebuje streamování s nízkou latencí, implementujte opravu voláním funkce [SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Opravili jsme zablokované zařízení, ke kterým došlo při streamování v režimu výzkumu.
- Opravili jsme chybu, kdy se v některých případech při obnovení relace na přihlašovací obrazovce nezobrazl správný uživatel.
- Opravili jsme problém, kdy uživatelé nemohli exportovat protokoly MDM prostřednictvím **nastavení**.
- Opravili jsme problém, kdy přesnost sledování očí hned po nastavení by mohla být nižší, než se čekalo.
- Opravili jsme problém, kdy subsystém pro sledování očí za určitých podmínek neinicializoval nebo neprováděl operaci.
- Opravili jsme problém, kdy se při pohledu na uživatele zobrazí výzva k zadání již zkalibrovaných uživatelů.
- Opravili jsme problém, kdy se ovladač během měření zraku havaroval.
- Opravili jsme problém, kdy opakované stisknutí tlačítka napájení mohlo způsobit 60sekudový časový limit systému a selhání prostředí.
- Vylepšená stabilita vyrovnávacích pamětí hloubky
- Přidali **jsme tlačítko Sdílet** do Centrum Feedback aby uživatelé mohli snadněji sdílet zpětnou vazbu.
- Opravili jsme chybu, kdy se roboRaid wan neinstaluje správně.

### <a name="known-issues"></a>Známé problémy

- Problém se systémovým jazykem zh-CN brání hlasovým příkazům v zachycení nebo zobrazení IP adresy zařízení ve smíšené realitě.
- Problém vyžaduje, abyste po spuštění zařízení spouštěnou hlasovou aktivací spouštěnou Cortanou spouštěla aplikaci Cortana. Pokud jste aktualizovali ze sestavení 18362, může se zobrazit také druhá dlaždice aplikace pro předchozí verzi aplikace Cortana, která už v nabídce **Start nefunguje.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic verze 1903 – aktualizace z května 2020 
- Build 18362.1061

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny, protože tým pracoval na windows holografické verzi 2004 May Update, jak je popsáno výše.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic verze 1903 – aktualizace z dubna 2020
- Build 18362.1059

**Tmavý režim pro podporované aplikace** 

Řada aplikací pro Windows podporuje tmavý i světlý režim. Zákazníci HoloLens 2 teď mohou zvolit výchozí režim pro aplikace, které podporují obě barevná schémata. Na základě zpětné vazby od zákazníků jsme nastavili výchozí režim aplikace na "tmavý", ale toto nastavení můžete kdykoli snadno změnit: Přejděte na Nastavení > Systém **> Barvy** a vyhledejte "Zvolit výchozí režim **aplikace".**

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
- Zajistili jsme, že se do zachytávání hybridní reality zahrnou překryvy prostředí.
- Unreal developers can now use the 3D View page in Portál zařízení to test and debug their applications.
- Vylepšená stabilita hologramu ve smíšené realitě při použití *algoritmu HolographicDepthReprojectionMethod DepthReprojection*
- Opravili jsme chybu "Třída rozhraní API WinRT IStreamSocketListener není zaregistrovaná" v 32bitových aplikacích ARM.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic verze 1903 – aktualizace z března 2020 
- Sestavení 18362,1056

Vylepšení a opravy v aktualizaci:

- Zlepšená stabilita při hybridní realitě při použití algoritmu *AutoPlanar HolographicDepthReprojectionMethod* .
- Zajistěte, aby byl souřadnicový systém připojený k hloubkové ukázce MF konzistentní s veřejnou dokumentací.
- Zlepšení produktivity vývojářů tím, že zákazníkům umožníte vkládat velké objemy textu prostřednictvím portálu zařízení.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows holografická verze 1903 – únor 2020 aktualizace 
- Sestavení 18362,1053

Vylepšení a opravy v aktualizaci:

- Dočasně zakázalo rozhraní API HolographicSpace. UserPresence pro aplikace Unity. Tato změna zabrání problému, který způsobil, že některé aplikace se při převrácení hypervisoru nemusely pozastavit, a to i v případě, že je povolené nastavení spustit v pozadí.
- Opravili náhodnou HUP havárií způsobenou ručním sledováním, ve kterém uživatel všiml, že se zablokuje uživatelské rozhraní a pak se po několika sekundách zpátky do prostředí shell.
- Vylepšené sledování, takže když se poke s prstem na index, je horní část tohoto prstu méně pravděpodobná na neočekávaném otáčení.
- Zlepšená spolehlivost sledování hlav, prostorového mapování a dalších modulů runtime.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows holografická verze 1903 – leden 2020 – aktualizace 
- Sestavení 18362,1043
 
Vylepšení a opravy v aktualizaci:

- Lepší stabilita pro exkluzivní aplikace při práci s emulátorem HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows holografická verze 1903 – prosinec 2019 Update 
- Sestavení 18362,1042

Vylepšení a opravy v aktualizaci:

- Představily se opravy LSR (poslední fáze kopírování). Vylepšené vizuální vykreslování hologramů, aby se zobrazovalo více stabilních a bylo zaostřené o přesnější zúčtování jejich hloubky. Pokud aplikace nenastaví hloubku poznatku na hologramech, bude tento příznaku po této aktualizaci více patrné.
- Pevná stabilita exkluzivních aplikací a navigace mezi exkluzivními aplikacemi
- Vyřešili jsme problém, kdy zachycení hybridní reality nedokázalo nahrávat video po několika dnech v pohotovostním stavu zařízení.
- Zlepšená stabilita hologramů.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows holografická verze 1903 – listopad 2019 – aktualizace 
- Sestavení 18362,1039

Vylepšení a opravy v aktualizaci:

- Při počátečním nastavení pro en-CA a EN-AU se opravily funkce **vybraných** hlasových příkazů.
- Vylepšená vizuální kvalita objektů, které jsou umístěné daleko v nejnovějších verzích Unity a Mixed reality Toolkit (MRTK).
- Vyřešené problémy s adresováním u holografických aplikací, které při spuštění přestávají stav pozastaveno, dokud se nabídka Start neotevřela a pak zavřela.
- Opravy a vylepšení dodržování shody za běhu OpenXR pro HoloLens 2 a emulátor.
