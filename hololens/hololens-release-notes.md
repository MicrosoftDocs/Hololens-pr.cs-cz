---
title: HoloLens verze 2
description: Aktuální informace o všech aktualizacích v každé nové verzi HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8ad76f1c0cc16101b10fb0576c1b3763caac450d
ms.sourcegitcommit: db573910a0c81fdf6edaca8cb8ef3d0be5e25603
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2021
ms.locfileid: "129432024"
---
# <a name="hololens-2-release-notes"></a>HoloLens verze 2

Pro zajištění produktivního prostředí s vašimi HoloLens zařízeními pokračujeme ve vydání funkcí, chyb a aktualizací zabezpečení. Na této stránce se můžete podívat, co je nového HoloLens každý měsíc. Pokud chcete získat nejnovější aktualizaci HoloLens 2, můžete aktualizace vyhledat a ručně aktualizovat, nebo získat úplnou aktualizaci Flash Update (FFU) pro flash disk vašeho zařízení prostřednictvím Doprovodný průvodce pokročilým [obnovením.](hololens-recovery.md#clean-reflash-the-device) [](hololens-update-hololens.md#check-for-updates-and-manually-update) Stahování [je](https://aka.ms/hololens2download) stále aktuální a poskytuje nejnovější obecně dostupné sestavení.

> [!NOTE]
> Nedávné oznámení Windows 11 se zaměřilo na verzi počítače Windows. Nedávno jsme [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) v květnu 2021 spustili hlavní aktualizaci operačního systému na HoloLens 2. Pracujeme na nadcházející verzi na základě zpětné vazby od zákazníků na tento rok.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace ze září 2021

- Build 20348.1018

Vylepšení a opravy v aktualizaci:

- Opravuje problém, kdy může neočekávaně skočí systémový čas.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace ze září 2021

- Build 19041.1165

Vylepšení a opravy v aktualizaci:

- Opravuje problém, kdy může neočekávaně skočí systémový čas.

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

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům s otevíráním uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.
- Opravili jsme problémWi-Fi kdy se při spuštění uživatelského rozhraní vlastností Wi-Fi ze služby **Nastavení > Network & Internet**> stav > Vlastnosti .
- Byl vyřešen problém s odebráním certifikátů eSIM mezi aktualizacemi operačního systému. Tato oprava zajišťuje odebrání certifikátů eSIM a souvisejících komponent při aktualizaci na verzi 21H1.
- Byl opraven problém, který ovlivnil předinstalované aplikace napříč resetováním operačního systému.
- Vyladěný výkon při dobíjení baterie za běhu při vyšším zatížení procesoru. Při HoloLens 2 zařízení, pokud se detekuje, že je zařízení spuštěné v horkém stavu, interní baterie se bude nabítat pomaleji, aby se snížilo teplo. Kladným kompromisem je, že zařízení je méně pravděpodobné, že se vypne kvůli teplotním problémům, s dopadem na to, že zařízení běží déle. Pokud je zařízení studené, sazba za poplatek není ovlivněná.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z července 2021

- Build 19041.1157

Vylepšení a opravy v aktualizaci:

- Portál zařízení nabízí vylepšené metody, jak upozornit zákazníka, když Průzkumník souborů dojde k problémům s otevíráním uzamčených souborů.
- Při použití https ve všech podporovaných prohlížečích je teď opravené nahrávání, stahování, přejmenování a odstraňování souborů.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, verze 21H1 – aktualizace z června 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive nahrání fotoaparátu do práce nebo do školy

Do aplikace HoloLens 2 Nastavení jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa hybridní reality ze složky Obrázky > Fotoaparát do odpovídající složky OneDrive for work nebo school. Tato funkce řeší nedostatky funkcí v aplikaci [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) ve HoloLens 2, která podporuje jenom automatické nahrávání fotoaparátů do osobního účtu účet Microsoft zákazníka (a ne jeho pracovního nebo školního účtu).

**Jak to funguje**

- Pokud **Nastavení > nahrání fotoaparátu> Mixed Reality** přejděte do části Systémová > Mixed Reality kamera.
- Když tuto funkci  nastavíte na Na pozici, všechny fotky nebo videa hybridní reality zachycené do vašeho zařízení se automaticky zařadit do fronty pro nahrání do složky Pictures > Camera Roll vašeho účtu OneDrive for work nebo school.
    >[!NOTE]
    >Fotky a videa zachycené před  povolením této funkce nebudou zařazené do fronty pro nahrání a budou se muset nahrát ručně.
- Stavová zpráva na Nastavení zobrazí počet souborů čekajících na nahrání (nebo si přečtěte "OneDrive je aktuální" po nahrání všech čekajících souborů).
- Pokud máte obavy o šířku pásma nebo chcete nahrávání pozastavit z nějakého důvodu, můžete tuto funkci přepnout do **pozice Vypnuto.** Dočasné zakázání této funkce zajistí, že se fronta pro nahrávání bude dál zvyšovat při přidávání nových souborů do složky Fotoaparát, ale soubory se nenahrají, dokud tuto funkci znovu nepo povolením nenahrajete.
- Nejnovější soubory se nahrají jako první (poslední, první ven).
- Pokud u OneDrive účtu dochází k problémům (například po  změně hesla), zobrazí se na stránce Nastavení opravit.
- Neexistuje žádná maximální velikost souboru, ale upozorňujeme, že nahrávání velkých souborů bude trvat déle (zejména v případě, že je omezena šířka pásma pro nahrávání). Pokud během nahrávání velkého souboru pozastavíte nebo vypnete nahrávání, částečné nahrání se zachová. Pokud se nahrávání znovu povolí během několika hodin od "pozastavení" nebo vypnutí, nahrávání bude pokračovat tam, kde se vypnulo. Pokud se ale nahrávání po několika hodinách znovu povolí, nahrávání velkého souboru se od začátku restartuje.

**Známé problémy a upozornění**

- Toto nastavení nemá žádné integrované omezování na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Upload se pozastaví, ale funkce bude dál monitorovat nově přidané soubory do fotoaparátu. Jakmile budete připraveni pokračovat, nahrávání znovu povolte.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat jenom soubory pro uživatele, který je momentálně přihlášený k zařízení.
- Pokud během sledování počtu nahrávání na stránce Nastavení v reálném čase posouváte fotky nebo videa, nezapomeňte, že počet čekajících souborů se může změnit, dokud se nahrávání aktuálního souboru nedokončí.
- Upload se pozastaví, když zařízení přepadne do režimu spánku nebo je vypnuté. Pokud chcete zajistit dokončení probíhajícího nahrávání, aktivně zařízení používejte, dokud stránka Nastavení nečte "OneDrive je aktuální" nebo neupravte nastavení režimu spánku **Power &.**

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

Tato aktualizace obsahuje funkce pro dvě cílové skupiny. Funkce, které může koncový uživatel na zařízení používat kdokoli na zařízení, a nové možnosti správy zařízení, které mohou konfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro jednotlivé cílové skupiny. Pokud jste správce IT, podívejte se prosím na našeho [správce IT – aktualizace kontrolního seznamu](#it-admin---update-checklist).
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

![Přihlašovací obrazovka je ve výchozím nastavení nastavená.](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka dalších uživatelů](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Podpora externích mikrofonů USB-C

> [!IMPORTANT]
> Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**. při zapojení do sady uživatelů sluchátek se systémem USB-C bude docházet k automatickému přesměrování zvukového přenosu do sluchátek, ale HoloLens operační systém nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C. Mikrofony USB-C lze použít pro volání, záznam atd.

otevřete aplikaci **Nastavení** a vyberte **systémový**  >  **zvuk**.

![zvukový Nastavení.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba **výchozí** znamená, že se externí mikrofon bude používat všude.
>
> zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a dalších komunikačních aplikacích, ale pole HoloLensho mikrofonu se může používat i pro jiné úkoly.

![Správa zvukových zařízení.](images/usbc-mic-2.png)

<br>

![Nastavte výchozí mikrofon.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>co Bluetooth podpora mikrofonu?

v HoloLens 2 bohužel Bluetooth mikrofony stále nejsou podporovány.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a nikoli s HoloLens. při zapojení jednoho z těchto telefonů do HoloLens může dojít ke ztrátě zvuku. Naštěstí je jednoduchá oprava.  

v **Nastavení**  >  **systémový**  >  **zvuk** explicitně nastavte integrované reproduktory **(zvukový ovladač analogických funkcí)** jako **výchozí zařízení**. HoloLens by si toto nastavení měli pamatovat i v případě, že mikrofon odeberete a znovu připojíte později.

![Řešení potíží s mikrofony USB-C.](images/usbc-mic-4.png)

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

| Zásady  | Popis   | Konfigurace  |
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

Pokud se ve starších buildech zařízení nacházela konfigurace veřejného terminálu, což je kombinace obou uživatelů s přiřazeným přístupem a přiřazeným členem skupiny AAD, v případě neúspěšného určení členství ve skupině AAD by se uživateli zobrazila zpráva "[nic nezobrazuje" v nabídce Start](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode).

od tohoto Windows vydané verze se bude beznabídkový režim zaregistrovat do globální konfigurace veřejného terminálu (pokud je k dispozici) v případě selhání během celoobrazovkového režimu skupiny AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>nové identifikátory uri Nastavení pro viditelnost stránky Nastavení

v [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali [zásady Nastavení/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) , abyste omezili stránky, které jsou v aplikaci pro Nastavení viditelné. PageVisibilityList je zásada, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené.

pokud navštívíte [stránku Nastavení viditelnost](settings-uri-list.md), najdete pokyny k použití tohoto CSP a seznam identifikátorů uri dostupných v předchozích verzích.

rozšiřujeme seznam dostupných identifikátorů uri Nastavení, které můžou správci IT spravovat. některé z těchto identifikátorů uri jsou pro nově dostupné oblasti v rámci nové aplikace Nastavení. pokud používáte zásady Nastavení/PageVisibilityList, přečtěte si následující seznam a podle potřeby upravte své povolené nebo blokované stránky.

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

nyní může uživatel v aplikaci Nastavení nakonfigurovat chování [záložní diagnostiky](hololens-diagnostic-logs.md). v aplikaci Nastavení přejděte na   >  stránku **poradce při potížích** s nastavením ochrany osobních údajů, abyste mohli nakonfigurovat toto nastavení.

> [!NOTE]
> Pokud je pro zařízení nakonfigurovaná zásada MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí pomocí okolních zařízení

Sdílejte věci s ostatními zařízeními Windows 10, včetně počítačů a dalších zařízení HoloLens 2. Můžete si ho vyzkoušet v **prostředích Nastavení** systému a sdílet soubory nebo adresy URL z  >    >   HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s blízkými zařízeními [v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

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
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování pro HoloLens v HoloLens prostřednictvím Nastavení  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – kontrolní seznam aktualizací

Tento kontrolní seznam vám pomůže se seznamem nových položek přidaných v této aktualizaci funkcí, které můžou mít vliv na aktuální konfiguraci správy zařízení nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace do bezobrazovkovém režimu

✔️ [**nové AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste už dříve v bezna Nastavení aplikace nebo Microsoft Edge, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové aplikace v [beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení v bezobrazovkovém okně, nebo zahrnout novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ k [**bezobrazovkovému režimu automatické přihlášení návštěvníka:**](#visitor-auto-logon-for-kiosks)

Návštěvníci teď mohou být automaticky přihlášeni k veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ [**vylepšené selhání bezobrazovkového režimu:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Pokud není členství přihlášených uživatelů AAD ve skupině AAD úspěšné, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o vašem oddělení podpory, pokud používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti Nastavení stránky

✔️ nové [**identifikátory URI Nastavení pro** viditelnost Nastavení stránky](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte viditelnost [Nastavení,](settings-uri-list.md) můžete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC

✔️ Pokud jste dřív blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující informace a použijte poskytnutý vzorový kód.

#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge

✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ konfigurace [diagnostiky pro záložní prostředky:](#configuring-fallback-diagnostics-via-settings-app)Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

✔️[Sdílení věcí s blízkými zařízeními:](#share-things-with-nearby-devices)Novou funkci sdílení v okolí můžete zakázat.

✔️ Konfigurace [nastavení zásad pro](#configuring-policy-settings-for-the-new-microsoft-edge)novou Microsoft Edge: Zkontrolujte nově dostupné konfigurace pro Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nový diagnostický nástroj

✔️ nová[diagnostická trasování operačního systému:](#new-os-diagnostic-traces)Shromáždí protokoly související s aktualizacemi operačního systému.

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

- Tato měsíční aktualizace kvality neobsahuje žádné z jakýchkoliv jakýchkoliv změn. **Toto sestavení už nebude dostávat měsíční aktualizace služby**. Doporučujeme, abyste si mohli vyzkoušet náš nejnovější build Windows Holographic verze 21H1.

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
- Byl opraven problém způsobující nevrácenou paměť ve službě Portál zařízení Service, který způsobil vyšší využití paměti službou, která způsobila selhání přidělení paměti jinými aplikacemi.
- Opravili jsme problém, kdy se uživatelé zaregistrovaní ve fázi rolloutu k zařízení nepokusili přihlásit.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z března 2021

- Build 18362.1102

Vylepšení a opravy v aktualizaci:

- Byl opraven problém způsobující nevrácenou paměť ve službě Portál zařízení Service, který způsobil vyšší využití paměti službou, která způsobila selhání přidělení paměti jinými aplikacemi.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z února 2021

- Build 19041.1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém s počátečním nastavením zařízení a aktualizacemi aplikací pro Store.
- Řeší problém s upgrady a lety pro pozdější HoloLens verze.
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM z HoloLens zařízení

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z února 2021

- Build 18362.1098

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

**přidáváme novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** . Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**. Aby nedošlo k narušení podniků, instalační program aplikace nebude v tuto chvíli **k dispozici pro spravovaná zařízení** .  

Zařízení se považuje za spravované, pokud platí **některá** z následujících podmínek:

- [Zaregistrované](hololens-enroll-mdm.md) MDM
- Nakonfigurováno pomocí [zřizovacího balíčku](hololens-provisioning.md)
- [Identita](hololens-identity.md) uživatele je Azure AD

Nyní je možné instalovat aplikace bez nutnosti povolit vývojářský režim ani používat portál zařízení.  Stačí stáhnout (přes USB nebo přes Edge) sadu appx do zařízení a přejít do sady appx v Průzkumníkovi souborů, aby se zobrazila výzva k ukončení instalace.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web).  stejně jako aplikace, které instalujete z Microsoft Store nebo bokem pomocí možnosti nasazení aplikace LOB pro správu mobilních aplikací, musí být aplikace digitálně podepsané pomocí [nástroje signer](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a [certifikát použitý k podepsání musí být](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) před nasazením aplikace důvěryhodný pro HoloLens zařízení.

**Pokyny k instalaci aplikace**

1. Ujistěte se, že se zařízení nepovažuje za spravované.
1. ujistěte se, že je zařízení HoloLens 2 zapnuté a připojené k počítači.
1. ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1. na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage \Downloads.   Po dokončení kopírování souboru můžete odpojit své zařízení.
1. v zařízení HoloLens 2 otevřete nabídku Start, vyberte všechny aplikace a spusťte aplikaci průzkumník souborů.
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace vybrat toto zařízení jako první a pak přejít na soubory ke stažení.
1. Vyberte soubor yourapp. appxbundle.
1. Spustí se instalační program aplikace. Vyberte tlačítko nainstalovat a nainstalujte svou aplikaci.
Nainstalovaná aplikace se po dokončení instalace automaticky spustí.

k otestování tohoto toku můžete najít ukázkové aplikace na [Windows Universal samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) .

přečtěte si o úplném procesu [instalace aplikací v HoloLens 2 s instalačním programem aplikace](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování teď uchovává sledování v mnoha nových případech, kdy by došlo ke ztrátě výše.  V některých z těchto nových případů se aktualizuje jenom pozice Palm na základě reálné ruky uživatele, zatímco ostatní klouby se odkládají na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako jsou Slapping, throw, scooping a clapping.  Pomáhá taky v případech, kdy se ruka blíží povrchu nebo drží objekt.  Pokud jsou spojky odvoditelné, nastaví se hodnota pro stejnou [přesnost](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) na "Přibližná" místo "vysoká".
- Opravili jsme problém, kdy se pro účty Azure AD Resetování PIN kódu zobrazí chyba něco se nepovedlo.
- Uživatelé by měli při spuštění ET, Iris z nastavení aplikace, nového uživatele nebo informační zprávy o oznámení zobrazovat mnohem méně havárií po spuštění OOBE.
- Uživatelé by měli mít správné časové pásmo vycházející z počátečního nastavení.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holografická verze 1903 – prosinec 2020 Update

- Sestavení 18362,1088

tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme vám vyzkoušet nejnovější Windows holografickou verzi 20H2 – prosinec 2020 update a novou funkci instalačního programu aplikace přidanou v buildu.

## <a name="windows-holographic-version-20h2"></a>Windows Holografická verze 20H2

- Sestavení 19041,1128

Windows holografická verze 20H2 je teď dostupná a přináší skvělou sadu nových funkcí pro HoloLens 2 uživatele a odborníky na IT. z automatického oka do správce certifikátů v Nastavení, aby se zlepšila funkčnost celoobrazovkového režimu a nové možnosti nastavení autopilotu. tato nová aktualizace umožňuje týmům IT vytvářet podrobnější kontrolu nad konfigurací a správou HoloLensch zařízení a nabízí uživatelům ještě více bezproblémového holografického prostředí.

Tato nejnovější verze je měsíční aktualizace verze 2004, ale tentokrát zahrnujeme nové funkce. hlavní číslo buildu zůstane stejné a web Windows Update bude uvádět měsíční vydání verze 2004 (build 19041). můžete se podívat na číslo svého buildu v Nastavení > o obrazovce, abyste se ujistili, že jste na nejnovějším dostupném buildu 19041.1128 +. pokud chcete aktualizovat na nejnovější verzi, otevřete aplikaci Nastavení, pokračujte na aktualizace & zabezpečení a klepněte na vyhledat aktualizace. další informace o tom, jak spravovat HoloLens aktualizace, najdete v tématu [správa aktualizací HoloLens](hololens-updates.md).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>co je nového ve Windows holografickém 20H2, verze  

| Funkce                                              | Popis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Podpora pozice automatického oka](hololens-release-notes.md#auto-eye-position-support) | Aktivně vypočítává pozice očí bez uživatelů přes kalibraci sledování očí.   |
| [Správce certifikátů](hololens-release-notes.md#certificate-manager)   | umožňuje nově jednodušší metody instalovat a odebírat certifikáty z aplikace Nastavení.     |
| [Automatické spuštění zřizování z USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Zřizovací balíčky na jednotkách USB se automaticky zobrazí na stránce pro zřizování v OOBE.                                                         |
| [Automatické potvrzení zřizovacích balíčků v OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Zřizovací balíčky se automaticky aplikují během OOBE ze stránky zřizování.                                                         |
| [Automatické zřizování bez použití uživatelského rozhraní](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak kombinovat automatické spouštění zřizování a automaticky potvrzovat dohromady. |
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

po připojení HoloLens 2 k síti Wi-Fi teď při spuštění nástroje oobe zkontroluje profil automatického pilotního nasazení pro zařízení. Pokud se najde, použije se k dokončení připojení AAD a toku registrace. Jinými slovy, použití sítě Ethernet pro USB-C nebo Wi-Fi do adaptéru USB-C ještě není požadavkem, ale budou fungovat i v případě, že jsou k dispozici na začátku počátečního nastavení. přečtěte si další informace o [autopilotu pro zařízení HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a autopilot

- Zachovává zařízení v tenantovi organizace tím, že je zamkne na tenanta i přes resetování nebo reflash zařízení. Díky dalšímu zabezpečení zakážete vytváření účtů prostřednictvím zřizování.

HoloLens 2 zařízení nyní podporují zprostředkovatele CSP pro [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2).

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby HoloLens 2 byly vázané jenom na registraci MDM jenom pomocí autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (na začátku nastavená) na HoloLens 2, zůstane tato hodnota v zařízení i přes znovu blikající, aktualizace operačního systému atd.

Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true na HoloLens 2, po připojení k síti počká OOBE po neomezenou dobu na úspěšné stažení a použití profilu Autopilot.

Jakmile je u uzlu RequireNetworkInOOBE klientaLockdown CSP nastavená hodnota true na úrovni HoloLens 2, jsou v OOBE zakázané následující operace:

- Vytvoření místního uživatele pomocí zřizování modulu runtime
- Provádění operace připojení k Azure AD prostřednictvím zřizování modulu runtime
- Výběr vlastníka zařízení v prostředí pro OOBE

#### <a name="how-to-set-this-using-intune"></a>Jak to nastavit pomocí Intune?

1. Vytvořte vlastní konfigurační profil zařízení OMA URI a jako uzel RequireNetworkInOOBE zadejte true, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamykací funkce tennant přes OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení.

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení nastavení TenantLockdown RequireNetworkInOOBE HoloLens 2?

1. Odeberte předchozí HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše.

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení.

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený HoloLens po nastavení tenantaLockdown na hodnotu true?

OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown.

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

Tyto informace teď najdete společně se zbytkem Autopilotu v části [Tenantlockdown CSP a Autopilot.](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim

- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije režim veřejného terminálu.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Přečtěte si o této nové funkci podrobně v [HoloLens beznaiosku.](hololens-kiosk.md)

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

Dříve v případě selhání při použití bezobrazovkovém režimu HoloLens se všechny aplikace zobrazují v nabídce Start. Nyní v Windows Holographic verze 20H2 v případě selhání se v nabídce Start nezobrazí žádné aplikace, jak je znázorněno níže:

![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Politiky

- Možnosti správy zařízení speciálně pro HoloLens pro správu zařízení.

Nové zásady hybridní reality byly vytvořeny pro HoloLens 2 zařízení na Windows Holographic verze 20H2. Mezi nová říditelná nastavení patří nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v záznamech hybridní reality, nastavení, kdy je možné shromažďovat diagnostiku, a mezipaměť členství ve skupinách AAD.  

| Nové HoloLens zásad                                | Popis                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Umožňuje zakázat tlačítka jasu, takže se jeho stisknutí nezmění na brightness.       | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Umožňuje zakázat tlačítka hlasitosti, aby se po stisknutí tlačítka neměňte svazek.               | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | Zakáže mikrofon, takže na počítači s HoloLens 2 není možný žádný zvukový záznam.                      | 1 Ano, 0 Ne (výchozí)                                                |
| MixedReality\FallbackDiagnostics                   | Řídí chování, kdy je možné shromažďovat diagnostické protokoly.                               | 0 Zakázáno, 1 Povoleno pro vlastníky zařízení, 2 Povoleno pro všechny (výchozí) |
| MixedReality\HeadTrackingMode                      | Vyhrazeno pro budoucí použití.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Určuje, kolik dní se mezipaměť členství ve skupinách Azure AD používá pro bezobrazovkové režimy cílené na skupiny Azure AD. | Viz níže.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy

- Povolili jste použití offline terminálů se skupinami AAD po dobu až 60 dnů.

Tato zásada určuje, kolik dní může být mezipaměť členství ve skupinách Azure AD použita pro konfigurace přiřazeného přístupu, které cílí na skupiny Azure AD pro přihlášené uživatele. Jakmile je hodnota této zásady nastavená na hodnotu větší než 0, použije se mezipaměť, jinak se hodnota mezipaměti nenastaví.  

Název: AADGroupMembershipCacheValidityInDays Hodnota identifikátoru URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dní  
Max. – 60 dnů

Postup správných použití těchto zásad:

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

Tyto dvě nové zásad pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Pokud jde o [RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens bude podporovat jenom konfiguraci ./Vendor/MSFT/RemoteLock/Lock. Konfigurace týkající se kódu PIN, jako je resetování a obnovení, se nepodporují.

### <a name="new-power-policies-for-hololens-2"></a>Nové zásady napájení pro HoloLens 2

- Další možnosti pro HoloLens režimu spánku nebo uzamčení prostřednictvím zásad napájení.

Tyto nově přidané zásady umožňují správcům řídit stavy napájení, jako je časový limit nečinnosti. Další informace o jednotlivých zásadách si můžete přečíst kliknutím na odkaz pro jednotlivé zásady.

|     Odkaz na dokumentaci k zásadám                |     Poznámky                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Příklad hodnoty pro použití Windows Configuration Designeru, tj.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
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
