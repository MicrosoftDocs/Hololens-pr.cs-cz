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
ms.date: 08/10/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: a8d1f9b8d04324236cb610b6018880891bdabdd1
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858675"
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
>- Windows Holographic, verze 20H2 (build 19041.1128+)
>- Windows Holographic, verze 2004 (build 19041.1103+)
>- Windows Holographic, verze 1903 (build 18362+)
>
> Se zavedením Windows Holographic verze 21H1 přerušujeme měsíční servisní aktualizace pro **Windows Holographic verze 1903.** Díky tomu se můžete zaměřit na novější verze a pokračovat v poskytování cenných vylepšení.


| Název funkce                                              | Krátký popis                                                                      | Cílovou skupinu | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nové Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nový, Chromium založený na Microsoft Edge, je teď k dispozici pro HoloLens 2. | Koncový uživatel | 
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
[Automatické přihlášení návštěvníka pro bezobrazovkové režimy](#visitor-auto-logon-for-kiosks) | Povolí použití automatického přihlášení k účtům Návštěvník v bezobrazovkovém režimu. | Správce IT |
[Nové identifikátory AUMID pro nové aplikace v beznavídkovém režimu](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Identifikátory AUMID pro nové Nastavení a aplikace Edge. | Správce IT |
[Vylepšené předání chyb v bezobrazovkovém režimu](#kiosk-mode-behavior-changes-for-handling-of-failures) | V bezobrazovkovém režimu se před prázdnou nabídkou Start vyhledá globální přiřazený přístup. | Správce IT |
[Nová nastaveníURIs pro viditelnost Nastavení stránky](#new-settings-uris-for-page-settings-visibility) | Více než 20 nových nastaveníURI pro Nastavení/PageVisibilityList. | Správce IT |
[Konfigurace diagnostiky pro záložní prostředky](#configuring-fallback-diagnostics-via-settings-app) | Nastavení chování diagnostiky pro záložní Nastavení aplikaci | Správce IT |
[Sdílení věcí s blízkými zařízeními](#share-things-with-nearby-devices) | Sdílení souborů nebo adres URL z HoloLens do počítače | Vše |
[Nová diagnostická trasování operačního systému](#new-os-diagnostic-traces) | Nový poradce při potížích Nastavení pro aktualizace operačního systému. | Správce IT |
[Optimalizace doručení Preview](#delivery-optimization-preview) | Snižte využití šířky pásma pro stahování z více HoloLens zařízení. | Správce IT |

Projděte si související poznámky k verzi:

- [Navštivte archiv HoloLens Emulator.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Průvodci Dynamics 365](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Představení nového Microsoft Edge

![Animace staršího Microsoft Edge loga na nové Microsoft Edge loga](images/new-edge.gif)

Nový Microsoft Edge přijme [projekt Chromium open source,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) aby pro zákazníky vytvořil lepší kompatibilitu a méně fragmentace webu pro webové vývojáře.

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která se už [v](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nových verzích nepodporuje.

![Snímek obrazovky Microsoft Edge nového snímku obrazovky](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Spuštění nové Microsoft Edge

Nový Microsoft Edge ![Ikona Microsoft Edge nový](images/new_edge_logo.png) (znázorněná modrou a zelenou ikonou swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Při prvním spuštění nového Microsoft Edge na HoloLens 2 se vaše nastavení a data naimportuje ze starší verze Microsoft Edge. Pokud po spuštění nového Microsoft Edge nadále používáte starší verzi Microsoft Edge, nebudou se tato nová data synchronizovat ze starší verze Microsoft Edge do nového Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

Nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče pro HoloLens 2, než byly dříve dostupné ve starších verzích Microsoft Edge.

Tady je několik užitečných zdrojů informací o správě nastavení zásad pro nové Microsoft Edge:

- [Konfigurace Microsoft Edge zásad pomocí Microsoft Intune](/deployedge/configure-edge-with-intune)
- [starší verze Microsoft Edge mapování Microsoft Edge zásad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome pro Microsoft Edge zásad](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Úplná [Microsoft Edge Enterprise dokumentace](/deployedge/)

> [!IMPORTANT]
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada bude fungovat HoloLens 2. Otestovali a potvrdili jsme ale, že nové zásady Microsoft Edge ekvivalentem každé starší Microsoft Edge zásad, které se dříve podporovaly u HoloLens 2 podle očekávání. V [starší verze Microsoft Edge Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zásad najdete nový ekvivalent Microsoft Edge pro všechny starší zásady prohlížeče Microsoft Edge, které jste s verzí HoloLens 2 HoloLens.
>
> Minimálně dvě nové zásady Microsoft Edge, o které víme, *že nebudou* fungovat s HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nového Microsoft Edge na HoloLens 2

Vzhledem k tomu, že Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UPW, která umožňuje jeho spuštění na zařízeních pouze pro UPW, jako je HoloLens 2, nemusí být některé funkce okamžitě dostupné. V nadcházejících měsících budeme podporovat nové scénáře a funkce, proto v tomto prostoru najdete aktuální informace.

**Očekávané scénáře a funkce:**
- Prostředí při prvním spuštění, přihlášení k profilu a synchronizace
- Weby by se měly vykreslit a chovat podle očekávání
- Většina funkcí prohlížeče (oblíbené položky, historie atd.) by měla fungovat podle očekávání
- Tmavý režim
- Instalace webových aplikací do zařízení
- Instalace rozšíření (pokud používáte rozšíření, která nefungují správně v HoloLens 2)
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

- Náhled lupy na holografické klávesnici byl pro novou klávesnici Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu Sledovat](hololens2-basic-usage.md#follow-me-stop-following)mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna **tlačítkem X.**
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit, že ostatní okna 2D aplikací neočekávaně prochádí. Tato okna můžete znovu aktivovat opětovnou interakcí.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat víc verzí najednou. 

Další informace [o komunitě Edge Insider najdete na domovské stránce](https://www.microsoftedgeinsider.com) Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce pro [stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider do Microsoft Edge 2 je k dispozici několik HoloLens:

**Přímá instalace na zařízení (aktuálně dostupná pouze pro nespravovaná zařízení)**
  1. Na stránce HoloLens 2 přejděte na stránku [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **Stáhnout pro HoloLens 2** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor .msix z fronty pro stahování Edge nebo ze složky Stažené soubory (pomocí příkazu Průzkumník souborů).
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

Aby správci IT mohli aktualizovat zásady [WDAC](windows-defender-application-control-wdac.md) tak, aby blokují novou aplikaci Microsoft Edge, musíte do zásad přidat následující kód.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí mohou mít omezení sítě, která je třeba vzít v úvahu. Pokud chcete zajistit bezproblémové prostředí s novým Edgem, [povolte tyto koncové body Microsoftu.](/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalace webových aplikací
 > [!Note]
>Od [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)Office webová aplikace už nebude předem nainstalovaná.

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci Microsoft Office zobrazit a upravit soubory hostované na SharePoint nebo OneDrive. Pokud chcete nainstalovat Office aplikaci, navštivte a vyberte tlačítko App Available (Aplikace k dispozici) https://www.office.com nebo Install Office **(Nainstalovat** aplikaci) na panelu Adresa.  Potvrďte **výběrem** možnosti Nainstalovat.

> [!IMPORTANT]
> Office webové aplikace je dostupná jenom v případě, že HoloLens 2 má aktivní připojení k internetu.

### <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer

Součástí nového Microsoft Edge je podpora WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Řada imerzivních webových prostředí byla navržena s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale tato prostředí podporuje také HoloLens 2. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že nová imerzivní prostředí rozšířené reality a hybridní reality dorazí na HoloLens 2 zákazníky.

Rozšíření 360 Viewer je postaveno na aplikaci WebXR a automaticky se nainstaluje společně s novou Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

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
> Vzhledem k tomu, Nastavení nová aplikace se liší od starší Nastavení aplikace, při aktualizaci se Nastavení okna, která jste předtím umístili kolem svého prostředí.

![Domovská stránka Nastavení nové aplikace](images/new-settings-app.png)

**Nové funkce a nastavení**
- Nastavení vyhledávání: Na domovské stránce Nastavení pomocí klíčových slov nebo názvu nastavení vyhledejte nastavení.
- System > Sound (Zvuk systémového >):
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
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace** znamená, že se externí mikrofon použije ve vzdáleném asistenci a v jiných komunikačních aplikacích, ale pole HoloLens Mic se může používat i pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavení výchozího nastavení mikrofonu](images/usbc-mic-3.jpg)

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

| Zásady  | Popis   | Konfigurace  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umožňuje návštěvníkovi automaticky se přihlásit k bezobrazovkovému režimu.   | 1 (Ano), 0 (Ne, výchozí.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Použití nových aplikací Nastavení a Edge v režimech veřejného terminálů

Při zahrnutí aplikací do [veřejného terminálu](hololens-kiosk.md)správce IT často přidá aplikaci do veřejného terminálu, ale použije JI AUMID (App User Model ID). Vzhledem k tomu, že aplikace Nastavení i aplikace Microsoft Edge se považují za nové aplikace a liší se od starších aplikací, které pro tyto aplikace používají identifikátory AUMID, bude potřeba aktualizovat, aby bylo možné používat nové AUMID.

Při úpravách veřejného terminálů tak, aby zahrnoval nové aplikace, doporučujeme přidat nový AUMID a nechat starý. Tím se vytvoří snadný přechod, když uživatelé aktualizují operační systém a nebudou muset přijímat nové zásady, aby mohli dál používat beziosk, jak má.

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

V [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) jsme přidali zásadu [Nastavení/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) která omezuje stránky, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci System Nastavení, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

Pokud navštívíte [page Nastavení Visibility](settings-uri-list.md), najdete pokyny k použití tohoto poskytovatele CSP a seznam identifikátorů URI dostupných v předchozích verzích.

Rozšiřujeme seznam dostupných identifikátorů URI, Nastavení mohou spravovat správci IT. Některé z těchto identifikátorů URI jsou pro nově dostupné oblasti v rámci nové Nastavení aplikace. Pokud používáte zásady Nastavení/PageVisibilityList, zkontrolujte následující seznam a podle potřeby upravte povolené nebo blokované stránky.

> [!NOTE]
> **Zastaralé: ms-settings:network-proxy**
>
> Jedna stránka nastavení je v těchto novějších sestaveních zastaralá. Stará stránka **& proxy** serveru již není  >   dostupná jako globální nastavení. Nové nastavení proxy serveru pro připojení najdete v části **Network & Internet** Wi-Fi Properties (Vlastnosti internetové sítě  >  **Wi-Fi)** nebo Network & Internet Ethernet Properties (Vlastnosti  >     >  **internetového ethernetu).**  >  

<br>

| Stránka Nastavení                                        | Identifikátor URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplikace > Apps & funkce                               | `ms-settings:appsfeatures`                         |
| Funkce > Apps & > Upřesnit možnosti          | `ms-settings:appsfeatures-app`                     |
| Aplikace > offline mapy                                  | `ms-settings:maps`                                 |
| Aplikace > offline mapy > stahování map                  | `ms-settings:maps-downloadmaps`                    |
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
| Nastavení > pro > a předvolby zařízení v aplikaci System > | `ms-settings:apps-volume`                          |
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

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurace záložní diagnostiky prostřednictvím Nastavení aplikace

Teď, Nastavení aplikaci, může uživatel nakonfigurovat chování diagnostiky [pro fallback.](hololens-diagnostic-logs.md) Na stránce Nastavení přejděte na stránku **Řešení potíží** s ochranou osobních údajů a  ->   nakonfigurujte toto nastavení.

> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí s blízkými zařízeními

Sdílejte věci s ostatními zařízeními Windows 10, včetně počítačů a dalších zařízení HoloLens 2. Můžete si ho vyzkoušet v **prostředích Nastavení** systému a sdílet soubory nebo adresy URL z  ->    ->   HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s [blízkými](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)zařízeními v Windows 10 .

Tuto funkci je možné spravovat prostřednictvím [možnosti Připojení/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nová diagnostická trasování operačního systému

Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte do **Nastavení**  ->  **Update Security &amp; a**  >    >  **Windows Update a** vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.

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

✔️ Nové [**identifikátory AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste dříve v bezna Nastavení nebo v bezna Microsoft Edge aplikace, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové aplikace v [beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení v bezobrazovkovém systému, nebo zahrnout novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ [**automatického přihlášení návštěvníka pro bezobrazovkové režimy:**](#visitor-auto-logon-for-kiosks) 

Návštěvníci teď mohou být automaticky přihlášení do veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ chyba [**v bezobrazovkovém**](#kiosk-mode-behavior-changes-for-handling-of-failures)režimu:

Pokud není členství přihlášených uživatelů AAD ve skupině AAD úspěšné, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o vašem oddělení podpory, pokud používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti Nastavení stránky

✔️ nové [**identifikátory URI Nastavení pro viditelnost** Nastavení stránky](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte viditelnost [Nastavení,](settings-uri-list.md) možná budete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo zablokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC
✔️ Pokud jste dřív blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující informace a použijte poskytnutý vzorový kód.
#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge
✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ konfigurace [diagnostiky pro záložní](#configuring-fallback-diagnostics-via-settings-app)prostředky: Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

✔️[Sdílení věcí s blízkými zařízeními:](#share-things-with-nearby-devices)Novou funkci sdílení v okolí můžete zakázat.

✔️ [Konfigurace nastavení zásad pro novou Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Zkontrolujte nově dostupné konfigurace pro Microsoft Edge.

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
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM z HoloLens zařízení

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, verze 1903 – aktualizace z února 2021
- Build 18362.1098

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, verze 20H2 – aktualizace z ledna 2021
- Build 19041.1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spouštění, obnovování a přepínání uživatelů, pokud je na zařízení mnoho uživatelů.
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

1.  Ujistěte se, že se zařízení nepovažuje za spravované.
1.  ujistěte se, že je zařízení HoloLens 2 zapnuté a připojené k počítači.
1.  ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1.  na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage \Downloads.   Po dokončení kopírování souboru můžete odpojit své zařízení.
1.  v zařízení HoloLens 2 otevřete nabídku Start, vyberte všechny aplikace a spusťte aplikaci průzkumník souborů.
1.  Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace vybrat toto zařízení jako první a pak přejít na soubory ke stažení.
1.  Vyberte soubor yourapp. appxbundle.
1.  Spustí se instalační program aplikace. Vyberte tlačítko nainstalovat a nainstalujte svou aplikaci.
Nainstalovaná aplikace se po dokončení instalace automaticky spustí.

k otestování tohoto toku můžete najít ukázkové aplikace na [Windows Universal samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) .

přečtěte si o úplném procesu [instalace aplikací v HoloLens 2 s instalačním programem aplikace](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace](images/hololens-app-installer-picture.jpg)

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

ve HoloLens 2 se poloha oka povoluje přesnou polohu hologramu, pohodlné zobrazení a vylepšená kvalita zobrazení. Pozice oka se vypočítávají interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**Funkce Auto Eye Position (AEP)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel zařízení spustí. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová, a proto se tento proces opakuje, když uživatel odstartuje a zařízení znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasadí neomezaný uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu neomešlený uživatel odkazuje na někoho, kdo předtím neprošel procesem sledování zraku na zařízení.

| Aktivní aplikace | Předchozí chování | Chování z Windows Holographic, verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace bez pohledu nebo Holographic Shell |Zobrazí se dialogové okno příkazového řádku sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno příkazového řádku sledování očí. | Výzva ke sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke streamu pohledu do oka. |

Pokud uživatel přechází z aplikace, která není pohledem povolená, na aplikaci, která přistupuje k pohledným datům, zobrazí se výzva k přihlášení. 

Veškeré ostatní chování systému bude podobné, jako když aktuální uživatel nemá aktivní sledování očí. Například gesto Jednoručné spuštění nebude povoleno. Při počátečním nastavení se prostředí prvního spuštění nezmění.

Pro prostředí, která vyžadují pohled na data nebo velmi přesné umístění hologramu, doporučujeme necibrovaným uživatelům spustit sledování očí. Je přístupný z příkazového řádku pro sledování očí nebo tak, že z nabídky Start spustí aplikaci Nastavení a pak vyberete System > Ástečka > **Eye Nádroní**> Spuštění oka.

Tyto informace najdete později spolu s dalšími [informacemi o produktu](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené nástroje pro auditování, diagnostiku a ověřování pro zabezpečení a dodržování předpisů zařízení prostřednictvím nového Správce certifikátů Tato funkce vám umožní nasadit, řešit potíže a ověřit certifikáty ve velkém měřítku v komerčních prostředích.

V Windows Holographic verze 20H2 přidáváme Správce certifikátů do HoloLens 2 Nastavení aplikace. Přejděte na **Nastavení > Update & Security > Certificates**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů v zařízení. S novým Správcem certifikátů teď správci a uživatelé vylepšili auditování, diagnostiku a ověřování, aby zajistili, že zařízení zůstanou zabezpečená a vyhovující. 

-   **Auditování:** Možnost ověřit, že je certifikát správně nasazený, nebo ověřit, že byl správně odebrán. 
-   **Diagnostika:** Když nastanou problémy, ověření, že v zařízení existují příslušné certifikáty, šetří čas a pomáhá s řešením potíží. 
-   **Ověření:** Ověření, že certifikát slouží zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Pokud chcete rychle najít konkrétní certifikát v seznamu, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé mohou také přímo vyhledat certifikát. Pokud chcete zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na **Informace.** 

Instalace certifikátu aktuálně podporuje soubory .cer a .crt. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  Všichni ostatní uživatelé se instaluje jenom do aktuálního uživatele. Uživatelé mohou odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení počítače. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.

#### <a name="to-install-a-certificate"></a>Instalace certifikátu: 

1.  Připojení počítač HoloLens 2.
1.  Soubor certifikátu, který chcete nainstalovat, umístěte do umístění na HoloLens 2.
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

![Prohlížeč certifikátů v Nastavení aplikaci](images/certificate-viewer-device.jpg)

![Obrázek znázorňující, jak pomocí uživatelského rozhraní certifikátu nainstalovat certifikát](images/certificate-device-install.jpg)

Tyto informace najdete později [na nové stránce Správce certifikátů](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňující menší interakci uživatelů, když se během spuštění počítače používají jednotky USB se zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek ručně spustit obrazovku zřizování během spuštění při spuštění počítače. Uživatelé teď mohou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na úložné jednotce USB. 

1. Připojte jednotku USB se zřizovacím balíčkem během prvního interagovatelného okamžiku prvního ZOBE.
1. Až bude zařízení připravené ke zřízení, automaticky se otevře výzva se stránkou zřizování. 

Poznámka: Pokud je usb flash disk při spouštění zařízení připojený k napájení, OOBE provede výčet stávajícího paměťového zařízení USB a bude sledovat připojení dalších zařízení.

Další informace o použití zřizovacích balíčků během OOBE najdete v [dokumentaci HoloLens zřizování.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Další informace o [zřizování automatického spouštění z USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) najdete v dokumentaci HoloLens zřizování.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacího balíčku v OOBE
- Automatizovaný proces, který umožňuje menší interakci uživatelů, a když se zobrazí stránka zřizovací balíček, automaticky použije všechny uvedené balíčky.

Když se zobrazí hlavní obrazovka zřizování, OOBE odpočítá 10 sekund, než automaticky začne používat všechny zřizovací balíčky. Do 10 sekund od ověření [balíčků,](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) které očekávali, je uživatelé stále mohou potvrdit nebo zrušit.

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní
- Kombinované automatické procesy pro menší interakce zařízení pro zřizování 

Kombinací automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovací balíčky může uživatel automaticky zřídit zařízení HoloLens 2, aniž by mohl používat uživatelské rozhraní zařízení nebo dokonce mít zařízení. Můžete dál používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení více zařízení najednou ve stejné oblasti. 

1. [Pomocí nástroje Windows](hololens-provisioning.md) [Configuration Designer vytvořte zřizovací balíček.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Flash váš HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) až [19041.1361 nebo novější build](https://aka.ms/hololens2previewdownload). 
1. Po [dokončení rozšířeného](https://www.microsoft.com/store/productId/9P74Z35SFRS8) průvodce obnovením zařízení odpojte kabel USB-C. 
1. Připojte usb flash disk k zařízení.
1. Když se HoloLens 2 spustí do OOBE, automaticky zjistí zřizovací balíček na USB disku a spustí stránku zřizování.
1. Po 10 sekundách zařízení automaticky použije zřizovací balíček. 

Vaše zařízení je teď nakonfigurované a [zobrazí obrazovku Provisioning Successful (Úspěšné zřizování).](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Použití Autopilotu s Wi-Fi připojením
- Odebrání potřeby adaptérů USB-C k ethernetovému omezení hardwarových potřeb díky povolení funkce Autopilotu na Wi-Fi připojených zařízeních.

Teď, když se během OOBE připojíte k HoloLens 2 pomocí Wi-Fi, OOBE zkontroluje profil Autopilotu pro zařízení. Pokud ho najdete, použije se k dokončení zbývající části toku připojení a registrace AAD. Jinými slovy, použití ethernetu na USB-C nebo Wi-Fi na adaptér USB-C už není povinné, ale i nadále fungují, pokud jsou k dispozici na začátku OOBE. Další informace o [Autopilotu pro HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a Autopilot
- Udržuje zařízení v tenantovi organizace tím, že je uzamyká pro tenanta i přes resetování zařízení nebo koliázi. S dalším zabezpečením tím, že prostřednictvím zřizování neumožníte vytvoření účtu v . 

HoloLens 2 teď podporují TenantLockdown CSP od [Windows Holographic verze 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, HoloLens 2 k registraci MDM pouze pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (počáteční nastavení) na HoloLens 2, zůstane tato hodnota v zařízení i přes znovu blikající, aktualizace operačního systému atd. 

Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true na HoloLens 2, po připojení k síti počká OOBE po neomezenou dobu na úspěšné stažení a použití profilu Autopilot. 

Jakmile je uzel RequireNetworkInOOBE u klientaLockdown CSP nastavený na hodnotu true HoloLens 2, jsou v OOBE zakázané následující operace: 
- Vytvoření místního uživatele pomocí zřizování modulu runtime 
- Provádění operace připojení k Azure AD prostřednictvím zřizování modulu runtime 
- Výběr toho, kdo zařízení vlastní v prostředí OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak ho nastavit pomocí Intune? 
1. Vytvořte vlastní konfigurační profil zařízení OMA URI a zadejte hodnotu true pro uzel RequireNetworkInOOBE, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamčení klienta pomocí OMA-URI](images/hololens-tenant-lockdown.png)

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

Tyto informace se teď dají najít spolu se zbytkem autopilotu v rámci [TENANTLOCKDOWN CSP a autopilotu](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – celoobrazovkový režim
- Omezená Správa identit pro veřejný terminál tím, že povolíte novou metodu veřejného terminálu, která na úrovni systému aplikuje celoobrazovkový režim.

tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro celoobrazovkový celoobrazovkový režim, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. podrobněji si přečtěte informace o této nové funkci v [HoloLens globálním terminálu s přístupem k globálním přiřazeným](hololens-global-assigned-access-kiosk.md).

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

| nové zásady HoloLens                                | Popis                                                                               | Poznámky                                                                |
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
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Příklad hodnoty, která se má Windows Návrháři konfigurace, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [PohotovostníTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Příklad hodnoty, která se má Windows Návrháři konfigurace, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Tyto dvě nové služby pro DisplayOffTimeoutOnBattery a DisplayOffTimeoutPluggedIn se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

> [!NOTE]
> Pro zajištění konzistentního prostředí HoloLens 2 se ujistěte, že hodnoty pro DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery jsou nastavené na stejnou hodnotu. Totéž platí pro DisplayOffTimeoutPluggedIn a StandbyTimeoutPluggedIn. Další podrobnosti [o moderním pohotovostním režimu](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) najdete v článku o časovačích nečinnosti pro zobrazení, režim spánku a hibernaci.

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

Informace o tom, která nastavení stránky můžete přizpůsobit na HoloLens 2, najdete na [naší Nastavení identifikátorů URI.](settings-uri-list.md) 
 
![Snímek obrazovky s úpravami aktivních hodin v Nastavení aplikaci](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Režim výzkumu
V režimu Research Mode se HoloLens 2 stává nástroj pro výzkum počítačového zpracování obrazu. V porovnání s předchozími edicemi má režim Research Mode for HoloLens 2 následující výhody:
-   Kromě senzorů vystavených v režimu výzkumu HoloLens (1. generace) teď poskytujeme přístup senzorů IMU, včetně akcelerometru, krátoboru a krátometru.
-   HoloLens 2 poskytuje nové možnosti, které je možné používat společně s režimem výzkumu. Konkrétně přístup k rozhraním API pro ruční sledování a sledování očí, která doručují bohatší sadu experimentů.

Výzkumníci teď mají na svých vlastních zařízeních možnost povolit režim výzkumu HoloLens přístup ke všem těmto externím nezpracovaných datovým proudům obrázků. Režim výzkumu pro HoloLens 2 také poskytuje přístup k odečtům akcelerometru, krátoboru a krátometru. V rámci ochrany osobních údajů uživatelů nejsou nezpracované obrázky z fotoaparátů pro sledování očí dostupné prostřednictvím režimu výzkumu, ale směr pohledu je k dispozici prostřednictvím stávajících rozhraní API.

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
- Byl vyřešen problém, který znemožňoval zobrazení zařízení HoloLens v Průzkumník souborů přes protokol MTP (Media Transfer Protocol), když je zařízení nastavené jako bezna terminál s jednou [aplikací.](hololens-kiosk.md) Mějte na paměti, že MTP (a připojení USB obecně) je stále možné zakázat pomocí zásad [AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
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

- Řeší problém, který zabránil Visual Studio aplikace, když se v souboru appxmanifest nachází SupportsMultipleInstances="true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která řeší selhání detekce internetu přes síťový proxy server. NCSI může k detekci připojení k internetu použít proxy server počítače a proxy server pro každý profil. NcSI bude v budoucí verzi podporovat proxy pro uživatele.
- Ve většině Windows Mixed Reality zařízení je směrový vektor vpřed paralelně k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Starší verze sady HoloLens 2 však zarovnaly vektor tak, aby byl perpenduován k panelům zobrazení, což je oproti ideální orientaci o několik stupňů dolů. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.
- Tato verze obsahuje opravu pro zlepšení kvality časového razítka zvuku, která může přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, verze 1903 – aktualizace ze září 2020
- Build 18362.1079

Vylepšení a opravy v aktualizaci:

- Ve většině Windows Mixed Reality zařízení je směrový vektor vpřed paralelně k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Starší verze sady HoloLens 2 však zarovnaly vektor tak, aby byl perpenduován k panelům zobrazení, což je oproti ideální orientaci o několik stupňů dolů. Novější verze systému HoloLens 2 tuto chybu opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze srpna 2020
- Build 19041.1113

Vylepšení a opravy v aktualizaci:

- Nastavení už uživatele nesleduje do prostředí pro registraci Iris nebo sledování očí.
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

zřizovací balíčky umožňují nastavit HoloLens konfiguraci prostřednictvím konfiguračního souboru, a ne prostřednictvím HoloLens připraveného prostředí. dříve musely být zřizovací balíčky zkopírovány do HoloLens interní paměti. teď můžou být na jednotce USB, aby je bylo snazší znovu použít na více HoloLens zařízeních a můžete zařízení zřizovat paralelně. Zřizovací balíčky teď také podporují pole pro registraci do správy zařízení, takže po zřízení už neexistuje žádné ruční nastavení.

Vyzkoušejte si to:

1. Stáhněte si nejnovější verzi nástroje Windows Configuration Designer z úložiště Windows do počítače.
1. Vyberte **Provision HoloLens Devices** Provision HoloLens 2 devices (Zřídit HoloLens zařízení  >  **2).**
2. Sestavte konfigurační profil. Potom zkopírujte všechny vytvořené soubory do úložného zařízení USB-C.
3. Připojte zařízení USB-C do všech zařízení s čerstvým HoloLens. Potom stiskněte **tlačítka napájení pro** snížení hlasitosti a použijte  +   zřizovací balíček.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodních aplikací

Nasazení a správa aplikací MDM pro obchodní aplikace je pro HoloLens. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. V této verzi jsme přidali další podrobnosti v části **Nastavení** Accounts Access work or school (Přístup k účtům do práce nebo do školy) Klikněte  >    >    >  **na your account** Info (Informace o vašem  >  **účtu).**

### <a name="additional-csps-and-policies"></a>Další csp a zásady

Poskytovatel [konfiguračních služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. V této verzi přidáme podporu pro další zásady, které správcům zvýší kontrolu nad nasazením HoloLens zařízení. Seznam csP podporovaných poskytovatelem csP najdete HoloLens [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

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

Byla přidána podpora pro povolení určitých mobilních širokopásmového zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když nejsou připojená k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě jako** další ethernetové připojení. (Mobilní širokopásmová zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s velkou šířkou pásmaWi-Fi není dostupná a Wi-Fi není dostatečně výkonný. Další informace o podporovaných zařízeních USB najdete v tématu Připojení k Bluetooth a [USB-C.](hololens-connect-devices.md)  

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

![Dlaždicová okna v tmavém režimu](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systémové hlasové příkazy

Hlasové příkazy teď můžete používat s libovolnou aplikací na zařízení. Další informace najdete v tématu [Použití hlasu k ovládání HoloLens](hololens-cortana.md). Viz také [Podporované jazyky pro HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana aktualizací

Aktualizovaná aplikace se integruje s Microsoft 365, která vám pomůže udělat více napříč zařízeními (aktuálně pouze US-English aplikacích). Na HoloLens 2 už Cortana určité příkazy specifické pro zařízení, jako je úprava svazku nebo restartování. Tyto možnosti teď podporují nové hlasové příkazy systému. Další informace o nové aplikaci Cortana najdete na našem [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  
- Zavedli jsme systém aktivního zobrazení s tekutou displeji. Tato funkce zlepšuje stabilitu a zarovnání hologramů. Když přesunete hlavičku ze strany na stranu, zůstanou na místě.
- Opravili jsme chybu, kdy Wi-Fi do HoloLens se pravidelně přerušilo streamování. Pokud aplikace indikuje, že potřebuje streamování s nízkou latencí, implementujte opravu voláním funkce [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
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
