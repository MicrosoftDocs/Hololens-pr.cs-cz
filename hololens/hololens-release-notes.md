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
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: bbbe01723cab70fa802b5a5db44bc812ce71cb2be2e3f283af698f161084f256
ms.sourcegitcommit: cb77de303607ef1340effeababf603d05d1a8048
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2021
ms.locfileid: "116975491"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 k vydání verze

Pro zajištění produktivního prostředí s vašimi HoloLens zařízeními pokračujeme ve vydání funkcí, chyb a aktualizací zabezpečení. Na této stránce se můžete podívat, co je nového pro HoloLens každý měsíc. Pokud chcete získat nejnovější aktualizaci HoloLens 2, [](hololens-update-hololens.md#check-for-updates-and-manually-update) můžete aktualizace vyhledat a ručně aktualizovat, nebo získat úplnou aktualizaci Flash Update (FFU) k flashování vašeho zařízení prostřednictvím [doprovodné funkce Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) Stahování [je](https://aka.ms/hololens2download) stále aktuální a poskytuje nejnovější obecně dostupné sestavení.

> [!NOTE]
> Nedávné oznámení Windows 11 se zaměřilo na verzi počítače Windows. Nedávno jsme [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) v květnu 2021 spustili hlavní aktualizaci operačního systému na HoloLens 2. Pracujeme na nadcházející verzi na základě zpětné vazby od zákazníků na tento rok.

> [!IMPORTANT]
> Vzhledem k vyřešeným známým problémům v našem buildu [21H1,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)který ovlivnil uživatele vzdálené pomoci, jsme dočasně pozastavil nabídku aktualizací Windows Holographic verze 21H1. Také jsme změnili výchozí build Advanced Recovery Companion (ARC) na [verzi Windows Holographic verze 20H2–june 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Sestavení ARC teď bude pokračovat v cílení na sestavení 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace z července 2021

- Build 20348.1010

Vylepšení a opravy v aktualizaci:

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům s otevíráním uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.
- Oprava problému, kdy Wi-Fi proxy server nelze uložit při spuštění uživatelského rozhraní vlastností Wi-Fi ze souboru **Nastavení -> Network & Internet -> Status -> Properties**.
- Byl vyřešen problém s odebráním certifikátů eSIM mezi aktualizacemi operačního systému. Tato oprava zajišťuje odebrání certifikátů eSIM a souvisejících komponent při aktualizaci na verzi 21H1.
- Byl opraven problém, který ovlivnil předinstalované aplikace napříč resetováním operačního systému.
- Vyladěný výkon při dobíjení baterie za běhu při vyšším zatížení procesoru. Při HoloLens 2 zařízení, pokud se detekuje, že je zařízení spuštěné v horkém stavu, bude se interní baterie nabítat pomaleji, aby se snížilo teplo. Kladným kompromisem je, že zařízení je méně pravděpodobné, že se vypne kvůli teplotním problémům, s dopadem na to, že zařízení běží déle. Pokud je zařízení studené, sazba za poplatek není ovlivněná.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z července 2021

- Build 19041.1157

Vylepšení a opravy v aktualizaci:

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům s otevíráním uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace z června 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive pro nahrání fotoaparátu do práce nebo do školy

Do aplikace HoloLens 2 Nastavení jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa hybridní reality ze složky Obrázky > Fotoaparát do odpovídající složky OneDrive for work nebo school. Tato funkce řeší nedostatky funkcí v aplikaci [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) ve HoloLens 2, která podporuje jenom automatické nahrávání fotoaparátů do osobních účet Microsoft zákazníka (a ne do pracovního nebo školního účtu).

**Jak to funguje**

- Pokud **Nastavení > nahrání fotoaparátu > Mixed Reality system > Mixed Reality,** navštivte webovou stránku.
- Když tuto funkci  nastavíte na Na pozici, všechny fotky nebo videa hybridní reality zachycené do vašeho zařízení se automaticky zařadit do fronty pro nahrání do složky Pictures > Camera Roll vašeho účtu OneDrive for work nebo school.
    >[!NOTE]
    >Fotky a videa zachycené před  povolením této funkce nebudou zařazené do fronty pro nahrání a budou se muset nahrát ručně.
- Stavová zpráva na Nastavení zobrazí počet souborů čekajících na nahrání (nebo si přečtěte "OneDrive je aktuální" po nahrání všech čekajících souborů).
- Pokud máte obavy o šířku pásma nebo chcete nahrávání pozastavit z nějakého důvodu, můžete tuto funkci přepnout do **pozice Vypnuto.** Dočasné zakázání této funkce zajistí, že se fronta pro nahrávání bude dál zvyšovat při přidávání nových souborů do složky Fotoaparát, ale soubory se nenahrají, dokud tuto funkci znovu nepo povolením nenahrajete.
- Nejnovější soubory se nahrají jako první (poslední, první ven).
- Pokud u OneDrive účtu dochází k problémům (například po  změně hesla), na stránce Nastavení se tlačítko Opravit.
- Neexistuje žádná maximální velikost souboru, ale mějte na paměti, že nahrávání velkých souborů bude trvat déle (zejména pokud je vaše šířka pásma pro nahrávání omezena). Pokud během nahrávání velkého souboru pozastavíte nebo vypnete nahrávání, částečné nahrání se zachová. Pokud se nahrávání znovu povolí během několika hodin od "pozastavení" nebo vypnutí, nahrávání bude pokračovat tam, kde se vypnulo. Pokud se ale nahrávání po několika hodinách znovu povolí, nahrávání velkého souboru se od začátku restartuje.

**Známé problémy a upozornění**

- Toto nastavení nemá žádné integrované omezování na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Upload se pozastaví, ale funkce bude dál monitorovat nově přidané soubory do fotoaparátu. Jakmile budete připraveni pokračovat, nahrávání znovu povolte.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat jenom soubory pro uživatele, který je momentálně přihlášený k zařízení.
- Pokud během sledování počtu nahrávání na stránce Nastavení v reálném čase posouváte fotky nebo videa, nezapomeňte, že počet čekajících souborů se může změnit, dokud se nahrávání aktuálního souboru nedokončí.
- Upload se pozastaví, když zařízení usne v režimu spánku nebo je vypnuté. Pokud chcete zajistit dokončení probíhajícího nahrávání, aktivně zařízení používejte, dokud stránka Nastavení nečte "OneDrive je aktuální" nebo neupravte nastavení režimu spánku **power &.**

### <a name="added-support-for-some-telemetry-policies"></a>Přidání podpory pro některé zásady telemetrie

Následující zásady telemetrie se teď podporují na HoloLens 2:

- KonfiguraceTelemetryOptInSettingsUx
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

Doporučujeme vám vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z června 2021

- Build 18362.1116

Vylepšení a opravy v aktualizaci:

- Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si náš nejnovější build Windows Holographic verze 21H1.

>[!IMPORTANT]
> Toto sestavení už nebude v provozu.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic verze 21H1
- Build 20346.1002

Tato aktualizace obsahuje funkce pro dvě cílové skupiny. Funkce, které může koncový uživatel na zařízení používat kdokoli na zařízení, a nové možnosti správy zařízení, které mohou konfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro každou cílovou skupinu. Pokud jste správcem IT, podívejte se na náš kontrolní seznam pro správce [IT – aktualizace.](#it-admin---update-checklist)
>[!IMPORTANT]
>Aby bylo možné aktualizovat toto sestavení, musí na zařízeních HoloLens 2 aktuálně běžet aktualizace z února 2021 (build 19041.1136) nebo novější. Pokud se vám tato aktualizace funkcí neschová k dispozici, nejprve aktualizujte své zařízení a zkuste to znovu.

>[!NOTE]
>V současné Microsoft HoloLens verze 2 podporuje měsíční servisní aktualizace (opravy chyb a zabezpečení) pro následující verze:
>- Windows Holographic, verze 20H2 (build 19041.1128+)
>- Windows Holographic, verze 2004 (build 19041.1103+)
>- Windows Holographic, verze 1903 (build 18362+)
>
> Se zavedením Windows Holographic verze 21H1 přerušujeme měsíční servisní aktualizace pro **Windows Holographic verze 1903.** Díky tomu se můžete zaměřit na novější verze a pokračovat v poskytování cenných vylepšení.


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
[Podpora externího mikrofonu USB-C](#usb-c-external-microphone-support) | Použijte mikrofony USB-C pro aplikace a /nebo Remote Assist. | Koncový uživatel |
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

Nový Microsoft Edge ![Ikona Microsoft Edge nový](images/new_edge_logo.png) (znázorněná modrou a zelenou ikonou swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Při prvním spuštění nového Microsoft Edge na HoloLens 2 se vaše nastavení a data naimportuje ze starších verzí Microsoft Edge. Pokud po spuštění nové Microsoft Edge nadále používáte starší verzi Microsoft Edge, nebudou se tato nová data synchronizovat ze starší verze Microsoft Edge do nové Microsoft Edge.

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

    ![Tlačítko pro aktivaci 360 Viewer](images/enter-360-viewer.jpg)

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

![nová domovská stránka aplikace Nastavení](images/new-settings-app.png)

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

pokud chcete nastavit hlasitost jednotlivé aplikace, přejděte na **Nastavení**  ->  **systémový**  ->  **zvuk** a v části pokročilé možnosti zvuku vyberte **předvolby aplikace a hlasitost zařízení**.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potáhnutím na typ

Někteří zákazníci na virtuálních klávesnicích rychleji najdou na "typ", a to potáhnutím tvaru slova, které mají v úmyslu zadat, a my si tuto funkci zobrazíme pro holografickou klávesnici. Jedno slovo můžete potáhnutím prstem procházet rovinou holografické klávesnice, potažením tvaru slova a následným odvoláním hrotu prstu z roviny klávesnice. Potáhnutím prstů můžete přetáhnout text, aniž byste museli stisknout MEZERNÍK, a to tak, že z klávesnice odeberete prst mezi slovy. Víte, že funkce funguje v případě, že se pod pohybem prstu na klávesnici zobrazuje potáhnutí.

Upozorňujeme, že tato funkce může být obtížné použít a hlavní, a to z důvodu povahy holografické klávesnice, kde nepůsobíte proti prstům odolnost (na rozdíl od zobrazení mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. indikátor na úvodní obrazovce HoloLens, který ukazuje, zda je k dispozici aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. otevřete HoloLens úvodní obrazovku pomocí [gesta start](hololens2-basic-usage.md#start-gesture) nebo vyslovení příkazu "přejít na začátek".

2. Všimněte si ikony tří teček (...) vedle obrázku profilu uživatele:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Vyberte si obrázek profilu uživatele pomocí vašich rukou nebo hlasového příkazu "Power".

4. Zobrazí se nabídka s možnostmi pro odhlášení, restartování nebo vypnutí zařízení:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Vyberte možnosti nabídky pro odhlášení, restartování nebo vypnutí HoloLens. Možnost odhlášení možná není dostupná, pokud je zařízení nastavené na [jeden účet Microsoft (MSA) nebo místní účet](hololens-identity.md).

6. zavřete nabídku tak, že se dotknete kamkoli jinde nebo zavřete nabídka Start pomocí gesta Start.

#### <a name="update-indicator"></a>Aktualizovat indikátor

Pokud je k dispozici aktualizace, ikona se třemi tečkami až do indikace, že restartování nainstaluje aktualizace možností nabídky, se také změní tak, aby odrážely přítomnost aktualizace.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Předchozí přihlašovací obrazovka zobrazila pouze posledního přihlášeného uživatele a vstupní bod jiného uživatele. Dostali jsme zpětnou vazbu od zákazníků, pokud se k zařízení přihlásilo více uživatelů. Pořád se vyžadovalo, aby znovu zapisovali své uživatelské jméno atd.

když se v tomto Windows buildu vybere **jiný uživatel** , který je umístěný napravo od pole pro zadání kódu PIN, zobrazí se na přihlašovací obrazovce několik uživatelů, kteří se k zařízení dříve přihlásili. to umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlašovat pomocí svých Windows Hello přihlašovacích údajů. Do zařízení můžete přidat nového uživatele pomocí tlačítka **Přidat účet** na stránce ostatní uživatelé.

Když v nabídce ostatní uživatelé přejdete na tlačítko ostatní uživatelé, zobrazí se poslední uživatel přihlášený k zařízení. Kliknutím na toto tlačítko se vrátíte na přihlašovací obrazovku pro tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiní uživatelé](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externích mikrofonů USB-C

> [!IMPORTANT]
> Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**. při zapojení do sady uživatelů sluchátek se systémem USB-C bude docházet k automatickému přesměrování zvukového přenosu do sluchátek, ale HoloLens operační systém nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C. Mikrofony USB-C lze použít pro volání, záznam atd.

otevřete aplikaci **Nastavení** a vyberte **systémový**  >  **zvuk**.

![zvukový Nastavení](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba **výchozí** znamená, že se externí mikrofon bude používat všude.
>
> zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a dalších komunikačních aplikacích, ale pole HoloLensho mikrofonu se může používat i pro jiné úkoly.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavit výchozí mikrofon](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>co Bluetooth podpora mikrofonu?

v HoloLens 2 bohužel Bluetooth mikrofony stále nejsou podporovány.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a nikoli s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound (Zvuk systému) explicitně nastavte integrované mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.** HoloLens si toto nastavení zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatické přihlášení návštěvníka pro terminály

Tato nová funkce umožňuje použití automatického přihlašování k účtům Návštěvník v bezobrazovkovém režimu.

Konfigurace bez AAD pro konfiguraci zařízení pro automatické přihlášení návštěvníka:

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje **nastavení modulu runtime /AssignedAccess tak,** aby povolují účty návštěvníka.
    1. Volitelně zaregistruje zařízení v MDM (nastavení modulu **runtime, pracoviště/ registrace),** aby ho bylo možné později spravovat.
    1. Nevytvářejte místní účet.
1. [Použijte zřizovací balíček](hololens-provisioning.md).

V případě konfigurace AAD mohou uživatelé bez této změny dosáhnout něčeho podobného. Zařízení připojená k AAD nakonfigurovaná pro režim veřejného terminála se mohou přihlásit k účtu návštěvníka jediným klepnutím na tlačítko na přihlašovací obrazovce. Jakmile se zařízení přihlásí k účtu návštěvníka, nebude znova vyzváno k přihlášení, dokud se návštěvník z nabídky Start explicitně odhlásit nebo dokud se zařízení nerestartuje.

Automatické přihlášení návštěvníka je možné spravovat [pomocí vlastních zásad OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Hodnota URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady  | Description   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automaticky se přihlásit k bezobrazovkovému režimu.   | 1 (Ano), 0 (Ne, výchozí.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových aplikací Nastavení a Edge v režimech veřejného terminálů

Při zahrnutí aplikací do [veřejného terminálu](hololens-kiosk.md)správce IT často přidává aplikaci do veřejného terminálů, ale používá ID modelu uživatele aplikace (AUMID). Vzhledem k tomu, že aplikace Nastavení i aplikace Microsoft Edge se považují za nové aplikace a liší se od starších aplikací, které pro tyto aplikace používají identifikátory AUMID, bude potřeba aktualizovat, aby bylo možné používat nové AUMID.

Při úpravách veřejného terminálů tak, aby zahrnoval nové aplikace, doporučujeme přidat nové AUMID a nechat starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou muset přijímat nové zásady, aby mohli dál používat beziosk, jak má.

| Aplikace                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stará Nastavení aplikace       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nová Nastavení aplikace       | BAEAEF15-9BE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Stará Microsoft Edge aplikace | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nová Microsoft Edge aplikace | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování v bezobrazovkovém režimu pro zpracování selhání

Pokud má zařízení ve starších buildech konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálním i přiřazeným členem skupiny AAD, pokud by se nepodařilo určit členství ve skupině AAD, uživateli se v nabídce[Start](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)nezobrazí nic.

Od této Windows se prostředí veřejného terminálu v případě selhání v beznaiosku skupiny AAD propadne ke globální konfiguraci veřejného terminálu (pokud je k dispozici).

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nové Nastavení URI pro viditelnost Nastavení stránky

Do Windows Holographic verze [20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali zásadu [Nastavení/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) která omezuje stránky, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci System Nastavení, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

Pokud navštívíte [stránku s Nastavení viditelnosti,](settings-uri-list.md)najdete pokyny k použití tohoto poskytovatele CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšiřujeme seznam dostupných identifikátorů URI, Nastavení mohou správci IT spravovat. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové Nastavení aplikace. Pokud používáte zásady Nastavení/PageVisibilityList, zkontrolujte následující seznam a podle potřeby upravte povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: ms-settings:network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Stará stránka **& proxy** serveru již není  >   dostupná jako globální nastavení. Nové nastavení proxy serveru pro připojení najdete v části **Vlastnosti sítě & internetové**  >  **wi-fi** nebo Vlastnosti  >   **internetového**&  >  **sítě Ethernet.**  >  

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
| Ochrana osobních > snímek obrazovky s ohraničením                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Ochrana osobních > Snímky obrazovky a aplikace                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Systémová > baterie                                     | `ms-settings:batterysaver`                         |
| Systémová > baterie                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| Předvolby > a > aplikace v nástroji Sound > | `ms-settings:apps-volume`                          |
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

Teď, Nastavení aplikaci, může uživatel nakonfigurovat chování diagnostiky [pro fallback.](hololens-diagnostic-logs.md) Na stránce Nastavení přejděte na stránku Řešení **potíží** s  ->  **ochranou osobních** údajů a nakonfigurujte toto nastavení.

> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí s blízkými zařízeními

Sdílejte věci v blízkosti Windows 10 zařízení, včetně počítačů a dalších zařízení HoloLens 2. Můžete si ho vyzkoušet v **prostředích Nastavení** systému a sdílet soubory nebo adresy URL z  ->    ->   HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s [blízkými](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)zařízeními v Windows 10 .

Tuto funkci je možné spravovat prostřednictvím [možnosti Připojení/AllowConnectedZařízení.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nová diagnostická trasování operačního systému

Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte na **Nastavení**  ->  **update &amp; security**  >  **Windows**  >  **Update a** vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručení Preview

Díky této HoloLens aktualizace Windows Holographic for Business nastavení optimalizace doručení, aby se snížila spotřeba šířky pásma pro stahování z několika HoloLens zařízení. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: Optimalizace doručení [pro Windows 10 aktualizace.](/windows/deployment/update/waas-delivery-optimization)

V rámci možností správy jsou povolená následující nastavení, [která je možné nakonfigurovat z Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DoCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DoCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
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

Pokud není úspěšně zjištěno členství v rámci skupiny AAD přihlášeného uživatele AAD, pak se globální konfigurace veřejného terminálu používá v nabídce Start (Pokud je k dispozici). v opačném případě se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurací, kterou můžete nastavit přímo, může to být tím, že toto nové zpracování bude informovat vaše oddělení podpory, pokud používáte veřejné terminály, protože to může platit pro vaše konfigurace nebo můžete chtít udělat nové úpravy pro vaše přiřazené konfigurace přístupu.

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
- Opravuje problém týkající se nasazení obchodních aplikací prostřednictvím zřizovacích balíčků za běhu.
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



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holografická verze 20H2 – duben 2021 Update
- Sestavení 19041,1144

Vylepšení a opravy v aktualizaci:

- Opravuje problém týkající se zasílání zpráv o stavu instalace obchodní aplikace.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holografická verze 1903 – duben 2021 Update
- Sestavení 18362,1108

Vylepšení a opravy v aktualizaci:

- řeší problém, při kterém při pokusu o změnu hesla pro místní účet dojde k chybě aplikace Nastavení.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holografická verze 20H2 – březen 2021 – aktualizace
- Sestavení 19041,1140

Vylepšení a opravy v aktualizaci:

- zákazníci, kteří používají AdvancedPhotoCapture nebo LowLagPhotoCapture k zachycení fotek pomocí HoloLens 2, teď můžou načítat fotoaparát až 3 sekundy od zachycení fotografie.
- Oprava pro nevracení paměti ve službě Device Portal: problém způsobil zvýšené využití paměti službou, která způsobila selhání přidělování paměti jiným aplikacím.
- Opravili jsme problém, kdy se uživatelé zaregistrují do připraveného zavedení, se nemůžou přihlásit k zařízení.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holografická verze 1903 – březen 2021 – aktualizace
- Sestavení 18362,1102

Vylepšení a opravy v aktualizaci:

- Oprava pro nevracení paměti ve službě Device Portal: problém způsobil zvýšené využití paměti službou, která způsobila selhání přidělování paměti jiným aplikacím.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holografická verze 20H2 – únor 2021 Update
- Sestavení 19041,1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém týkající se počátečního nastavení zařízení a aktualizací pro aplikace ze Storu.
- řeší potíže s upgrady a lety pro pozdější HoloLens verze.
- z kořenového úložiště eSIM se odebraly nepoužívané předinstalované certifikáty z HoloLens zařízení.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holografická verze 1903 – únor 2021 aktualizace
- Sestavení 18362,1098

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows holografické verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holografická verze 20H2 – leden 2021 – aktualizace
- Sestavení 19041,1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spuštění, obnovení a přepínání uživatelů v případě, že zařízení obsahuje mnoho uživatelů.
- Přidání podpory arm32 pro [výzkumný režim](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holografická verze 1903 – leden 2021 – aktualizace
- Sestavení 18362,1091

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows holografické verze 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holografická verze 20H2 – prosince 2020 Update
- Sestavení 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace

**přidáváme novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** . Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**. Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:
- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní aplikace [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) MDM, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens před nasazením aplikace důvěryhodný.

**Pokyny k instalaci aplikace.**

1.  Ujistěte se, že se vaše zařízení nepovažuje za spravované.
1.  Ujistěte se, že HoloLens 2 je zapnuté a připojené k počítači.
1.  Ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1.  Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky yourdevicename\Internal Storage\Downloads.   Po dokončení kopírování souboru můžete zařízení odpojit.
1.  Na svém HoloLens 2 Otevřete nabídku Start, vyberte Všechny aplikace a spusťte Průzkumník souborů aplikaci.
1.  Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat Toto zařízení a pak přejít na Položky ke stažení.
1.  Vyberte soubor yourapp.appxbundle.
1.  Spustí Instalační program aplikací. Vyberte tlačítko Install (Nainstalovat) a nainstalujte aplikaci.
Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

Ukázkové aplikace najdete na Windows [univerzálních GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) a tento tok otestujte.

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí Instalační program aplikací](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování rukou teď udržuje sledování v mnoha nových případech, kdy by se dříve ztratila rukou.  V některých z těchto nových případů se na základě skutečné ruky uživatele stále aktualizuje pouze pozice uživatele, zatímco druhá pozice je odvozena na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako je plevání, odhazování, tlesání a tlesění.  Pomáhá také v případech, kdy je ruce blízko povrchu nebo drží objekt.  Při odvozování ručního odhadu se hodnota společné přesnosti nastaví na "Approximate" (Přibližný) místo na High (Vysoká). [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)
- Opravili jsme problém, kdy se při resetování kódu PIN pro účty Azure AD zobrazí chyba Něco se pokazilo.
- Při spouštění ET, Iris z aplikace nastavení, nového uživatele nebo informační zprávy by uživatelé měli vidět mnohem méně selhání při spuštění.
- Uživatelé by měli mít správné časové pásmo přicházející z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z prosince 2020
- Build 18362.1088

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější verzi Windows Holographic verze 20H2–prosinec 2020 Update a novou funkci Instalační program aplikací přidanou v sestavení.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, verze 20H2
- Build 19041.1128

Windows Holographic verze 20H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a IT specialisty. Od funkce automatického umístění oka až po Správce certifikátů v Nastavení, vylepšené funkce bezobrazovkovém režimu a nové možnosti nastavení Autopilotu. Tato nová aktualizace umožňuje IT týmům převzít podrobnější kontrolu nad konfigurací a správou HoloLens zařízení a nabízí uživatelům ještě hladká holografická prostředí. 

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a Windows Update bude označovat měsíční vydání verze 2004 (build 19041). Na číslo sestavení se můžete podívat na obrazovce Nastavení > O aplikaci a ověřit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)

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

**Funkce Auto Eye Position (AEP)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel zařízení spustí. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position (Pozice automatického pohledu) začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová, a proto se tento proces opakuje, pokud uživatel zařízení odstartuje a znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasádá nezabý uživatel, dojde u funkce Automatické umístění oka k několika změnám chování systému. V tomto kontextu neomešlený uživatel odkazuje na někoho, kdo předtím neprošel procesem sledování zraku na zařízení.

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

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení nastavení TenantLockdown RequireNetworkInOOBE HoloLens 2? 
1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše. 

1. Vytvořte vlastní konfigurační profil zařízení založený na OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže. Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false přes OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený v HoloLens po nastavení tenantaLockdown na hodnotu true? 
OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown. 

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

Tyto informace teď najdete společně se zbytkem Autopilotu v části [Tenantlockdown CSP a Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim
- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije bezobrazovkové režimy.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Podrobné informace o této nové funkci najdete v HoloLens veřejného terminálu s [globálním přiřazeným přístupem.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatické spuštění aplikace v bezobrazovkovém režimu s více aplikacemi 
- Cílené prostředí s automatickým spouštěním aplikací, které dále zvyšuje možnosti uživatelského rozhraní a aplikací zvolené pro prostředí bezobrazovkovém režimu.

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
| MixedReality\MicrophoneDisabled                    | Zakáže mikrofon, takže na počítači s HoloLens 2 není možné nahrávat zvuk.                      | 1 Ano, 0 Ne (výchozí)                                                |
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
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se Windows nástroji Configuration Designer, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se Windows návrháři konfigurace, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové služby pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Pro zajištění konzistentního prostředí HoloLens 2 se ujistěte, že hodnoty pro DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery jsou nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti [o moderním pohotovostním režimu](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) najdete v článku o časovačích nečinnosti pro zobrazení, režim spánku a hibernaci.

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
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Imerzivní náhlavní souprava))
  - Zvukový *efekt MRC:*
    - LoopbackGain (aktuální hodnota "App Audio Gain" na Záznam hybridní reality stránce v Windows Portál zařízení)
    - MicrophoneGain (aktuální hodnota Mic Audio Gain na Záznam hybridní reality stránce v Windows Portál zařízení)
- Opravili jsme chybu, která vylepšuje kvalitu zvuku ve scénářích zachycení hybridní reality. Konkrétně by tato oprava měla eliminovat potíže se zvukem v nahrávce, když se **zobrazí** nabídka Start.
- Vylepšená stabilita hologramů v zaznamenaných videích
- Vyřešili jsme problém, kdy zachytávání hybridní reality nemohlo po několika dnech v pohotovostním stavu nahrát video.
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení zorovače, i když bylo povolené nastavení Spustit na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Při přístupu k Portál zařízení přes Wi-Fi připojení může webový prohlížeč bránit přístupu z důvodu neplatného certifikátu. Prohlížeč může nahlásit chybu typu "ERR_SSL_PROTOCOL_ERROR", i když byl certifikát zařízení dříve důvěryhodný. V takovém případě nemůžete postupovat k Portál zařízení, protože neexistuje možnost ignorovat upozornění zabezpečení. Tato aktualizace tento problém vyřešila. Pokud byl certifikát zařízení dříve stažen a na počítači důvěryhodný pro odebrání upozornění zabezpečení prohlížeče a dojde k chybě SSL, je třeba nový certifikát stáhnout a důvěřovat, aby se těmto upozorněním zabezpečení prohlížeče rovnal.
- Povolili jste možnost vytvořit zřizovací balíček modulu runtime, který může instalovat aplikaci pomocí balíčků MSIX.
- Přidali jsme nastavení **v Nastavení** System Hologramy, které uživatelům umožňuje automaticky odebrat všechny  >    >   hologramy z Mixed Reality domů, když se zařízení vypne.
- Opravili jsme problém, který způsob HoloLens, které změnily formát pixelů tak, aby se v emulátoru HoloLens pixelů vykreslují černě.
- Opravili jsme chybu, která způsoboval chybu při přihlášení Iris.
- Opravili jsme problém s opakovaným stahováním ze Storu pro již aktuální aplikace.
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
- Rozhraní API HolographicSpace.UserPresence je obecně zakázané pro aplikace Unity. Toto chování zabraňuje problému, který způsobuje, že se některé aplikace po překlopení visoru pozastaví, i když je povolené nastavení pro spuštění na pozadí. Rozhraní API je teď povolené pro Unity verze 2018.4.18 a novější a 2019.3.4 a novější.
- Opravili jsme problém, který způsob HoloLens, které změnily formát pixelů tak, aby se v HoloLens Emulator.
- Opravili jsme problém se spuštěním aplikace Photos při počátečním spuštění po aktualizaci z verze 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, verze 2004  
- Sestavení – 19041.1103

Hlavní aktualizace softwaru pro HoloLens 2, *Windows Holographic, verze 2004* z května 2020 obsahuje řadu zajímavých nových funkcí, jako je podpora Windows Autopilotu, tmavého režimu aplikací, podpora sítě USB Ethernet pro hotspoty 5G/LTE a mnoho dalšího. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete **aplikaci Nastavení,** přejděte na Update & Security a vyberte tlačítko    **Zkontrolovat** ****   aktualizace. 

|             Funkce                              |          Popis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Předem nakonfigurujte a bezproblémově nastavte nová zařízení pro produkční prostředí pomocí Windows AutoPilot.                 |
|       Podpora FIDO 2                             |          Podpora klíčů zabezpečení FIDO2 pro povolení rychlého a zabezpečeného ověřování pro sdílená zařízení            |
|       Vylepšené zřizování                      |          Bezproblémové použití zřizovacího balíčku z USB flash disku do HoloLens                              |
|       Stav instalace aplikace                 |          Zkontrolujte stav instalace v Nastavení aplikace pro aplikace se přes MDM nas nabízené HoloLens 2.               |
|       Poskytovatelé konfiguračních služeb (CSP)   |          Přidání nových poskytovatelů konfiguračních služeb pro vylepšení možností správy                 |
|       Podpora USB 5G/LTE                       |          Rozšířená schopnost ethernetového připojení USB umožňuje podporu pro 5G/LTE                                    |
|       Tmavý režim aplikace                              |          Tmavý režim aplikace dostupný pro aplikace, které podporují tmavý i světlý režim, vylepšuje prostředí pro prohlížení.        |
|       Hlasové příkazy                             |          Podpora dalších systémových hlasových příkazů pro ovládání HoloLens bez rukou                           |
|       Vylepšení sledování rukou                 |          Vylepšení sledování rukou zpřesní tlačítka a interakce s 2D slatem.                        |
|       Vylepšení a opravy kvality                 |          Různá vylepšení výkonu a spolehlivosti systému napříč platformou                            |

### <a name="support-for-windows-autopilot"></a>Podpora pro Windows Autopilot

Windows Autopilot pro HoloLens 2 umožňuje kanálu prodeje zařízení předem zaregistrovat HoloLens do vašeho tenanta Intune. Jakmile zařízení dorazí, jsou připravená k vlastnímu nasazení jako sdílená zařízení ve vašem tenantovi. Pokud chcete využít výhod vlastního nasazení, musí se zařízení připojit k síti během první obrazovky v nastavení pomocí USB-C-ethernet.

Jakmile uživatel spustí proces automatického nasazení Autopilotu, proces dokončí následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD).
1. Pomocí Azure AD zaregistrujte zařízení ve službě Microsoft Intune (nebo jiné službě MDM).
1. Stáhněte si zásady, certifikáty a síťové profily cílené na zařízení.
1. Zřídit zařízení.
1. Zobrazí přihlašovací obrazovku uživateli.

Další informace najdete v [Windows Autopilot for HoloLens 2](hololens2-autopilot.md).

*Požádejte správce účtu, aby se připojil k verzi AutoPilot Preview. Zařízení připravená pro Autopilot začnou brzy doručovat.*

### <a name="fido2-security-key-support"></a>Podpora klíčů zabezpečení FIDO2

Někteří uživatelé sdílejí HoloLens zařízení s ostatními uživateli v pracovním nebo školním prostředí. Je proto důležité, aby uživatelé mohli snadno zadávat dlouhá uživatelská jména a hesla. Fast Identity Online (FIDO) umožňuje komukoli ve vaší organizaci (tenant Azure AD) bezproblémově se přihlásit k HoloLens bez zadávání uživatelského jména nebo hesla.

Klíče zabezpečení FIDO2 jsou "nepřehledná" metoda ověřování bez hesla založená na standardech, která může být v jakémkoli provedení. FIDO je otevřený standard pro ověřování bez hesla. Umožňuje uživatelům a organizacím přihlásit se ke svým prostředkům bez uživatelského jména nebo hesla. Místo toho používají externí klíč zabezpečení nebo klíč platformy integrovaný do zařízení.

Pokud chcete začít, podívejte se [na stránku Povolení přihlašování pomocí bezpečnostního klíče bez hesla.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Vylepšená registrace MDM prostřednictvím zřizovacího balíčku

Zřizovací balíčky umožňují HoloLens konfiguraci prostřednictvím konfiguračního souboru, a HoloLens prostředí. Dříve bylo třeba zřizovací balíčky zkopírovat do HoloLens paměti. Teď mohou být na USB flash disku, aby se snadněji opakovaně opakovaně HoloLens zařízeních a vy můžete zařízení zřídit paralelně. Zřizovací balíčky teď také podporují pole pro registraci ve správě zařízení, takže po zřízení už neexistuje žádné ruční nastavení.

Vyzkoušejte si to:

1. Stáhněte si nejnovější verzi nástroje Windows Configuration Designer z úložiště Windows do počítače.
1. Vyberte **Provision HoloLens Devices** Provision HoloLens 2 Devices (Zřídit HoloLens zařízení  >  **2).**
2. Sestavte konfigurační profil. Potom zkopírujte všechny vytvořené soubory do úložného zařízení USB-C.
3. Připojte zařízení USB-C k novému flash HoloLens. Potom stiskněte **tlačítka napájení pro** snížení hlasitosti a použijte  +   zřizovací balíček.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodních aplikací

Nasazení a správa aplikací MDM pro obchodní aplikace je pro HoloLens. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. V této verzi jsme přidali další podrobnosti v části **Nastavení**  >  **Accounts Access** work or school (Přístup k účtům do práce nebo do školy) Klikněte na informace o  >    >  **vašem**  >  **účtu.**

### <a name="additional-csps-and-policies"></a>Další csp a zásady

Poskytovatel [konfiguračních služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. V této verzi přidáme podporu pro další zásady, které správcům zvýší kontrolu nad nasazenou HoloLens zařízení. Seznam csP podporovaných poskytovatelem csP najdete HoloLens [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

Novinka v této verzi:

**CsP pro zásady** 

Poskytovatel konfigurační služby Policy umožňuje podniku konfigurovat zásady na Windows zařízeních. V této verzi jsme přidali nové zásady pro HoloLens, které jsou zde uvedené. Další informace najdete v tématu o [csp zásadách podporovaných HoloLens 2.](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Byla přidána podpora pro povolení určitých mobilních širokopásmového zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když nejsou připojená k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě jako** další ethernetové připojení. (Mobilní širokopásmová zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s velkou šířkou pásmaWi-Fi není dostupná a Wi-Fi není dostatečně výkonný. Další informace o podporovaných zařízeních USB najdete v tématu Připojení připojení Bluetooth a [USB-C.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Vylepšení sledování rukou

Tato verze obsahuje několik vylepšení ručního sledování:

- **Bodování představuje stabilitu:** Systém teď odolá odsouvání indexového prstu, když ho uchytává šedě. Tato změna zvyšuje přesnost při nabízení tlačítek, psaní, posouvání obsahu a dalších. 
- **Menší nechtěné klepnutí ve vzduchu:** Vylepšili jsme detekci gesta klepnutí ve vzduchu. V několika běžných scénářích, například když pustíte ruce na stranu, je teď méně náhodných aktivací.
- **Spolehlivost uživatelského přepínače:** Při aktualizaci velikosti ruky při sdílení zařízení je teď systém rychlejší a spolehlivější.
- **Menší krádež rukou:** Vylepšili jsme zpracování případů, kdy senzory mají více než dvě ruce. Pokud spolu úzce pracuje více lidí, je teď mnohem menší pravděpodobnost, že sledovaná ruky "přeskočí" z uživatele do ruky někoho jiného ve scéně.
- **Spolehlivost systému:** Opravili jsme problém, který způsobl, že při vysokém zatížení zařízení přestalo fungovat sledování rukou.

### <a name="dark-mode"></a>Tmavý režim

Mnoho Windows aplikací teď podporuje tmavý i světlý režim. HoloLens 2 uživatelé mohou zvolit výchozí režim pro aplikace, které podporují oba režimy. Po aktualizaci je výchozí režim aplikace "tmavý", ale toto nastavení můžete snadno změnit: Přejděte na **Nastavení**  >  **Systémových** barev Zvolte  >    >  **výchozí režim aplikace.** 

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

Hlasové příkazy teď můžete používat s libovolnou aplikací na zařízení. Další informace najdete v tématu [Použití hlasu k ovládání HoloLens](hololens-cortana.md). Viz také [Podporované jazyky pro HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana aktualizací

Aktualizovaná aplikace se integruje s Microsoft 365, která vám pomůže udělat více napříč zařízeními (aktuálně pouze US-English aplikacích). Na HoloLens 2 už Cortana určité příkazy specifické pro zařízení, jako je úprava svazku nebo restartování. Tyto možnosti teď podporují nové systémové hlasové příkazy. Další informace o nové aplikaci Cortana najdete na našem [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  
- Zavedli jsme systém aktivního zobrazení s tekutou displeji. Tato funkce zlepšuje stabilitu a zarovnání hologramů. Nyní zůstanou na místě, když přesunete hlavičku ze strany na stranu.
- Opravili jsme chybu, kdy Wi-Fi do HoloLens se pravidelně přerušilo streamování. Pokud aplikace indikuje, že potřebuje streamování s nízkou latencí, implementujte opravu voláním funkce [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Opravili jsme zablokované zařízení, ke kterým došlo při streamování v režimu výzkumu.
- Opravili jsme chybu, kdy se v některých případech při pokračování relace na přihlašovací obrazovce nezobrazl správný uživatel.
- Opravili jsme problém, kdy uživatelé nemohli exportovat protokoly MDM **prostřednictvím Nastavení**.
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
- Problém vyžaduje, abyste po spuštění Cortana spouštěl aplikaci Cortana aktivaci. Pokud jste aktualizovali ze sestavení 18362, může se zobrazit také druhá dlaždice aplikace pro předchozí verzi aplikace Cortana, která už v nabídce **Start** nefunguje.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z května 2020 
- Build 18362.1061

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny, protože tým pracoval na aktualizaci Windows Holographic verze 2004 May Update, jak je popsáno výše.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, verze 1903 – aktualizace z dubna 2020
- Build 18362.1059

**Tmavý režim pro podporované aplikace** 

Řada Windows aplikací podporuje tmavý i světlý režim. HoloLens 2 zákazníci teď mohou zvolit výchozí režim pro aplikace, které podporují obě barevná schémata. Na základě zpětné vazby od zákazníků jsme nastavili výchozí režim aplikace na "tmavý", ale toto nastavení můžete kdykoli snadno změnit: Přejděte na **Nastavení > System > Colors** a vyhledejte **"Choose your default app mode"** (Zvolit výchozí režim aplikace).

Tyto "in-box" aplikace podporují tmavý režim:
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
