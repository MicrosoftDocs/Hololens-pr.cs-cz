---
title: Poznámky k verzi HoloLens 2
description: Všechny aktualizace v každé nové verzi HoloLens 2 se udržují v aktuálním stavu.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377698"
---
# <a name="hololens-2-release-notes"></a>Poznámky k verzi HoloLens 2

Abychom se ujistili, že budete mít k dispozici produktivní prostředí s vašimi zařízeními HoloLens, budeme pořád vydávat aktualizace zabezpečení a funkce, chyby a zabezpečení. Na této stránce se můžete podívat, co je nového pro HoloLens každý měsíc. Chcete-li získat nejnovější aktualizaci HoloLens 2, můžete buď [Vyhledat aktualizace, a ručně aktualizovat](hololens-update-hololens.md#check-for-updates-and-manually-update) nebo získat úplnou aktualizaci Flash (FFU), která [vám umožní flash zařízení prostřednictvím pokročilého Průvodce obnovením](hololens-recovery.md#clean-reflash-the-device). [Stažení](https://aka.ms/hololens2download) je udržováno v aktuálním stavu a poskytuje nejnovější všeobecně dostupné sestavení.

## <a name="windows-holographic-version-21h1"></a>Windows holografické, verze 21H1
- Sestavení 20346,1002

Tato aktualizace obsahuje funkce pro dva cílové skupiny. funkce, které může použít kdokoli na zařízení koncovým uživatelem, a nové možnosti správy zařízení, které můžou nakonfigurovat správci IT. Následující tabulka uvádí funkce, které jsou relevantní pro jednotlivé cílové skupiny. Pokud jste správce IT, podívejte se prosím na našeho [správce IT – aktualizace kontrolního seznamu](#it-admin---update-checklist).
>[!IMPORTANT]
>Aby bylo možné aktualizovat na toto sestavení, musí být zařízení s HoloLens 2 v současnosti spuštěna aktualizací únor 2021 (Build 19041,1136) nebo novější. Pokud se vám tato aktualizace funkce nezobrazuje, nejdřív prosím aktualizujte svoje zařízení a zkuste to znovu.

>[!NOTE]
>V dnešní době Microsoft HoloLens 2 podporuje měsíční aktualizace pro údržbu (chyby a opravy zabezpečení) pro následující verze:
>- Windows holografické, verze 20H2 (Build 19041.1128 +)
>- Windows holografická verze 2004 (Build 19041.1103 +)
>- Windows holografická verze 1903 (Build 18362 +) 
>
> Díky zavedení Windows holografické verze 21H1 **nepokračuje měsíční aktualizace pro Windows holografick verze 1903**. Díky tomu se můžeme soustředit na další nejnovější verze a dál dodávat cenná vylepšení. 


| Název funkce                                              | Krátký popis                                                                      | Cílová skupina | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nové Microsoft Edge](#introducing-the-new-microsoft-edge)  | Pro HoloLens 2 je teď k dispozici nový Microsoft Edge založený na Chromu. | Koncový uživatel | 
[WebXR a 360 Viewer](#webxr-and-360-viewer) | Vyzkoušejte moderní webové prostředí a 360 přehrávání videa. | Koncový uživatel | 
[Nová aplikace nastavení](#new-settings-app) | Aplikace se starším nastavením se nahrazuje aktualizovanou verzí s novými funkcemi a nastaveními. | Koncový uživatel |
[Zobrazit kalibraci barev](#display-color-calibration) | Vyberte alternativní barevný profil pro displej HoloLens 2. | Koncový uživatel |
[Výchozí výběr aplikace](#default-app-picker) | Vyberte aplikaci, která se má spustit pro každý soubor nebo typ odkazu. | Koncový uživatel |
[Řízení hlasitosti na aplikaci](#per-app-volume-control) | Ovládat svazek na úrovni aplikace nezávisle na systémovém svazku. | Koncový uživatel |
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
- [Mapování zásad Microsoft Edge Google Chrome](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Úplná [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada funguje na HoloLens 2. Otestovali jsme a potvrdili jsme, že nová zásada Microsoft Edge všech starších verzí zásad Microsoft Edge dříve podporovaných na HoloLens 2 fungovala podle očekávání. V [starší verze Microsoft Edge Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zásad najdete nový ekvivalent Microsoft Edge zásad prohlížeče Microsoft Edge, které jste s HoloLens 2 měli.
>
> Existují alespoň dvě nové zásady Microsoft Edge, o které víme, že *nebudou* s HoloLens 2 fungovat:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nové verze Microsoft Edge HoloLens 2

Vzhledem k tomu, že Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UPW, která umožňuje spuštění na zařízeních jenom pro UPW, jako je HoloLens 2, nemusí být některé funkce okamžitě dostupné. V nadcházejících měsících budeme podporovat nové scénáře a funkce, proto v tomto prostoru najdete aktuální informace.

**Očekávané scénáře a funkce:**
- Prostředí při prvním spuštění, přihlášení k profilu a synchronizace
- Weby by se měly vykreslit a chovat podle očekávání
- Většina funkcí prohlížeče (oblíbené položky, historie atd.) by měla fungovat podle očekávání
- Tmavý režim
- Instalace webových aplikací do zařízení
- Instalace rozšíření (pokud používáte rozšíření, která na HoloLens 2 nefungují správně, dejte nám vědět)
- Zobrazení a označení souboru PDF
- Prostorový zvuk z jednoho okna prohlížeče
- Automatická a ruční aktualizace prohlížeče
- Uložení souboru PDF z nabídky Tisk (pomocí možnosti Uložit do souboru PDF)
- Rozšíření WebXR a 360 Viewer
- Obnovení obsahu do správného okna při procházení několika oken umístěných ve vašem prostředí

**Scénáře a funkce, u které se neočekává, že budou fungovat:**
- Prostorový zvuk z několika oken se souběžně zvukovými streamy
- "See it, say it"
- Tisk

**Hlavní známé problémy prohlížeče:**

- Náhled lupy na holografické klávesnici byl pro novou obrazovku Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v [režimu Sledovat](hololens2-basic-usage.md#follow-me-stop-following)mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna **tlačítkem X.**
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit neočekávané neaktivování ostatních 2D oken aplikací. Tato okna můžete znovu aktivovat opětovnou interakcí.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge kanálů Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat více verzí najednou. 

Další informace [o komunitě Edge Insider najdete na domovské stránce](https://www.microsoftedgeinsider.com) Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce pro [stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

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
  1. Uložte soubor .msix do složky Stažené soubory (nebo do jiné složky, kterou snadno najdete).
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
>Ve [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)už webová aplikace Office nebude předem nainstalovaná.

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
1. [Klepnutím ve vzduchu](hololens2-basic-usage.md#select-using-air-tap) vylepšete ovládací prvky přehrávání. Pomocí [ručních paprsků](hololens2-basic-usage.md#select-using-air-tap) a klepnutí ve vzduchu můžete přehrát/pozastavit, přeskočit vpřed/zpět, zapnout nebo vypnout titulky nebo ukončit prostředí (které ukončí imerzivní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Známé problémy pro WebXR a 360 Viewer
- V závislosti na složitosti WebXR prostředí může snímkový kmitočet vyřadit nebo Stutter.
- Podpora kloubových spojek v WebXR není ve výchozím nastavení povolená. Vývojáři můžou povolit podporu prostřednictvím `edge://flags` zapínání "WebXR ruky".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby v WebXR a v prohlížeči 360

Sdílejte prosím svůj názor a chyby pomocí našeho týmu prostřednictvím funkce pro **odeslání zpětné vazby** v novém Microsoft Edge.

### <a name="new-settings-app"></a>Nová aplikace nastavení

V této verzi zavádíme novou verzi aplikace nastavení. Nová aplikace nastavení zahrnuje nové funkce a rozšířené nastavení pro HoloLens 2 v následujících oblastech: zvuk, Power & režim spánku, síť & Internetu, aplikace, účty, usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, že je nová aplikace nastavení odlišná od aplikace se staršími nastaveními, všechna nastavení, která jste předtím umístili do prostředí, se po aktualizaci odeberou.

![Domovská stránka nové aplikace nastavení](images/new-settings-app.png)

**Nové funkce a nastavení**
- Hledání nastavení: Vyhledejte nastavení z domovské stránky nastavení pomocí klíčových slov nebo názvu nastavení.
- Zvuk > systému:
  - Vstupní a výstupní zvuková zařízení: nezávisle vyberte vstupní a výstupní zvuková zařízení (například poslech zvuku přes sluchátka Bluetooth nebo použití mikrofonu USB-C pro zvukový vstup).
    > [!NOTE]
    > Technologie HoloLens 2 nepodporuje mikrofony Bluetooth.
  - Svazek aplikace: nezávisle upravte hlasitost každé aplikace. Zobrazit [Řízení hlasitosti jednotlivých aplikací](#per-app-volume-control).
- Systém > napájení & režimu spánku: vyberte, kdy se má zařízení po určité době nečinnosti přejít do režimu spánku.
- Systémová > baterie: ručně povolit režim spořiče baterie nebo nastavit prahovou hodnotu baterie, při které se režim spořiče baterie automaticky zapne.
- Zařízení > USB: ve výchozím nastavení můžete připojení USB zakázat.
- & sítě Internet:
  - Adaptéry USB-C Ethernet se nyní zobrazí v síti & Internetu.
  - K dispozici jsou nyní nastavení adaptéru USB-C Ethernet, včetně jeho IP adresy.
  - Nyní můžete zapnout režim v letadle na HoloLens 2.
- Aplikace: můžete obnovit výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu věnovaném [výchozím ovládacím prvkům aplikace](#default-app-picker).
- Účty > jiných uživatelích: vlastníci zařízení můžou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, předowngradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.

**Známé problémy**
- Okna dříve umístěná nastavení se odeberou (viz poznámku výše).
- Zařízení už nemůžete přejmenovat pomocí aplikace nastavení. Správci IT můžou zařízení přejmenovat pomocí šablony [Windows autopilot pro název zařízení HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) nebo uzlu MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) EXT/Microsoft/DNSComputerName.
- Na stránce Ethernet se vždy zobrazuje virtuální síť Ethernet (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, vzhledem k jeho povaze jako desktopová aplikace Win32 podporovaná vrstvou adaptéru UWP (zatím se nepředpokládá žádná oprava).

#### <a name="display-color-calibration"></a>Zobrazit kalibraci barev



Pomocí tohoto nového nastavení můžete vybrat alternativní barevný profil pro displej HoloLens 2. To může mít za přesnější vzhled barev, zejména při nižších úrovních jasu displeje. Kalibraci barev displeje můžete najít v aplikaci nastavení na stránce kalibrace systému >.

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

Pokud chcete nastavit hlasitost jednotlivé aplikace, přejděte na **Nastavení**  ->  **systémový**  ->  **zvuk** a v části Pokročilé možnosti zvuku vyberte **Předvolby aplikace a hlasitost zařízení**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Potáhnutím na typ

Někteří zákazníci na virtuálních klávesnicích rychleji najdou na "typ", a to potáhnutím tvaru slova, které mají v úmyslu zadat, a my si tuto funkci zobrazíme pro holografickou klávesnici. Jedno slovo můžete potáhnutím prstem procházet rovinou holografické klávesnice, potažením tvaru slova a následným odvoláním hrotu prstu z roviny klávesnice. Potáhnutím prstů můžete přetáhnout text, aniž byste museli stisknout MEZERNÍK, a to tak, že z klávesnice odeberete prst mezi slovy. Víte, že funkce funguje v případě, že se pod pohybem prstu na klávesnici zobrazuje potáhnutí.

Upozorňujeme, že tato funkce může být obtížné použít a hlavní, a to z důvodu povahy holografické klávesnice, kde nepůsobíte proti prstům odolnost (na rozdíl od zobrazení mobilního telefonu). 

### <a name="power-menu-from-start"></a>Nabídka napájení z nabídky Start

Nová nabídka, která uživateli umožňuje odhlásit se, vypnout a restartovat zařízení. Indikátor na úvodní obrazovce HoloLens, který ukazuje, kdy je k dispozici aktualizace systému.

#### <a name="how-to-use"></a>Způsob použití

1. Otevřete úvodní obrazovku HoloLens pomocí [gesta Start](hololens2-basic-usage.md#start-gesture) nebo vyslovení příkazu "Přejít na začátek".

2. Všimněte si ikony tří teček (...) vedle obrázku profilu uživatele:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Vyberte si obrázek profilu uživatele pomocí vašich rukou nebo hlasového příkazu "Power".

4. Zobrazí se nabídka s možnostmi pro odhlášení, restartování nebo vypnutí zařízení:

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
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizace & obnovení > obnovení & zabezpečení               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Aktualizované identifikátory URI

Dříve by následující dvě identifikátory URI nesly uživatele přímo na uvedené stránky, ale zablokovaly jenom hlavní stránku aktualizací. Aktualizovali jsme následující položky tak, aby se směrují na jejich stránky:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurace záložní diagnostiky prostřednictvím aplikace Nastavení

Teď v aplikaci Nastavení může uživatel nakonfigurovat chování [fallback diagnostics](hololens-diagnostic-logs.md). V aplikaci Nastavení přejděte na stránku Řešení **potíží s ochranou** osobních údajů a  ->   nakonfigurujte toto nastavení.

> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.  

### <a name="share-things-with-nearby-devices"></a>Sdílení věcí s blízkými zařízeními

Sdílejte věci s dalšími Windows 10 zařízeními, včetně počítačů a dalších zařízení HoloLens 2. Můžete si to vyzkoušet v **nastavení** sdílená prostředí systému a sdílet soubory nebo adresy  ->    ->   URL z HoloLens do počítače. Další podrobnosti najdete v tématu Sdílení věcí s blízkými zařízeními [v Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tuto funkci je možné spravovat prostřednictvím [možnosti Připojení/AllowConnectedZařízení.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nová diagnostická trasování operačního systému

Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte na **Nastavení Řešení** potíží  ->  **se &amp;**  >    >  **zabezpečením služba Windows Update** a vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.

### <a name="delivery-optimization-preview"></a>Optimalizace doručení Preview

Díky této aktualizaci HoloLens Windows Holographic for Business nastavení optimalizace doručení, aby se snížila spotřeba šířky pásma pro stahování z několika zařízení HoloLens. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: Optimalizace doručení [pro Windows 10 aktualizace.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

V rámci možností správy jsou povolená následující nastavení, [která je možné nakonfigurovat z Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DoCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DoCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DoDownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DoPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik upozornění na tuto nabídku verze Preview:

- Podpora HoloLens je v této verzi Preview omezená jenom na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v tuto chvíli nepodporují pro zařízení HoloLens.
- HoloLens nepodporuje nasazení ani optimalizaci doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování na HoloLensu na HoloLens prostřednictvím možnosti Aktualizace nastavení & Řešení potíží se  >    >     >   **zabezpečením služba Windows Update**.

### <a name="it-admin---update-checklist"></a>Správce IT – kontrolní seznam aktualizací

Tento kontrolní seznam vám pomůže se seznamem nových položek přidaných v této aktualizaci funkcí, které můžou mít vliv na vaši aktuální konfiguraci správy zařízení nebo nové funkce, které můžete chtít začít používat.

#### <a name="updates-to-kiosk-mode"></a>Aktualizace bezobrazovkového režimu

✔️ Nové [**identifikátory AUMID pro nové aplikace v beznaiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Pokud jste dříve v beznaiosku Microsoft Edge aplikaci Nastavení, nahradili jsme tyto aplikace novými aplikacemi, které používají jiné ID aplikace. Důrazně doporučujeme, abyste si níže přečetli článek Nové identifikátory AUMID pro nové aplikace v [beznabídkovém](#use-the-new-settings-and-edge-apps-in-kiosk-modes) režimu. Tím zajistíte, že buď budete mít aplikaci Nastavení ve svém bezobrazovkovém prostředí, nebo zahrníte novou Microsoft Edge aplikace. Tyto změny je možné provést teď a nasadit na všechna zařízení a umožnit plynulejší přechod při aktualizaci.

✔️ [**automatického přihlášení návštěvníka pro bezobrazovkové režimy:**](#visitor-auto-logon-for-kiosks) 

Návštěvníci teď mohou být automaticky přihlášení do veřejného terminálu. Toto chování je ve výchozím nastavení aktivní, ale je možné ho spravovat a zakázat.

✔️ [**vylepšené selhání bezobrazovkového režimu:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Pokud není členství přihlášených uživatelů AAD ve skupině AAD úspěšné, pak se pro nabídku Start (pokud existuje) použije globální konfigurace veřejného terminálu, jinak se uživateli zobrazí prázdná nabídka Start. I když prázdná nabídka Start není konfigurace, kterou můžete nastavit přímo, toto nové zpracování může být něco, co by vás mělo informovat o tom, jestli používáte terminály, protože to může platit pro vaše konfigurace nebo můžete chtít provést nové úpravy konfigurací přiřazeného přístupu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizace viditelnosti nastavení stránky

✔️ nové [**identifikátory URI nastavení pro viditelnost nastavení stránky**](#new-settings-uris-for-page-settings-visibility)

Pokud aktuálně používáte Viditelnost [nastavení](settings-uri-list.md) stránky, možná budete chtít upravit stávající identifikátory URI, které jste buď povoleni, nebo blokovali.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizace zásad WDAC
✔️ Pokud jste dřív blokovali Microsoft Edge přes WDAC, budete chtít aktualizovat zásady WDAC. Projděte si následující a použijte poskytnutý vzorový kód.
#### <a name="enable-new-endpoints-for-edge"></a>Povolení nových koncových bodů pro Edge
✔️ Pokud máte infrastrukturu, která zahrnuje konfiguraci koncových bodů sítě, jako je proxy server nebo brána firewall, povolte tyto nové koncové body pro novou Microsoft Edge aplikace.

#### <a name="newly-configurable-items"></a>Nově konfigurovatelné položky

✔️ konfigurace [diagnostiky pro záložní prostředky:](#configuring-fallback-diagnostics-via-settings-app)Můžete nakonfigurovat, jestli a kdo může shromažďovat fallback diagnostics.

✔️ Sdílení[věcí s blízkými zařízeními:](#share-things-with-nearby-devices)Novou funkci sdílení v okolí můžete zakázat.

✔️ konfigurace [nastavení zásad pro](#configuring-policy-settings-for-the-new-microsoft-edge)novou Microsoft Edge: Zkontrolujte nově dostupné konfigurace pro Microsoft Edge.

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


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z května 2021
- Build 19041.1146

Vylepšení a opravy v aktualizaci:
- Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si nejnovější build Windows Holographic verze 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic verze 1903 – aktualizace z května 2021
- Build 18362.1110

Vylepšení a opravy v aktualizaci:
- Tato měsíční aktualizace kvality neobsahuje žádné záhodné změny. **Toto sestavení už nebude dostávat měsíční aktualizace služby**. Doporučujeme vám vyzkoušet si nejnovější build s Windows Holographic verze 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z dubna 2021
- Build 19041.1144

Vylepšení a opravy v aktualizaci:

- Opravuje problém s hlášením stavu instalace obchodních aplikací.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic verze 1903 – aktualizace z dubna 2021
- Build 18362.1108

Vylepšení a opravy v aktualizaci:

- Řeší problém, kdy při pokusu o změnu hesla místního účtu dojde k chybě aplikace Nastavení.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z března 2021
- Build 19041.1140

Vylepšení a opravy v aktualizaci:

- Zákazníci, kteří k pořizování fotek pomocí HoloLens 2 používají AdvancedPhotoCapture nebo LowLagPhotoCapture, teď mohou načíst pozici fotoaparátu až 3 sekundy po zachycení fotky.
- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba vyvolala zvýšené využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.
- Opravili jsme problém, kdy se uživatelé zaregistrovaní ve fázi rolloutu mohli k zařízení přihlásit.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic verze 1903 – aktualizace z března 2021
- Build 18362.1102

Vylepšení a opravy v aktualizaci:

- Byl opraven problém s nevrácenou pamětí ve službě Portál zařízení Service, kdy služba vyvolala zvýšené využití paměti, které způsobilo selhání přidělení paměti jinými aplikacemi.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z února 2021
- Build 19041.1136

Vylepšení a opravy v aktualizaci:

- Opravuje problém s počátečním nastavením zařízení a aktualizacemi aplikací pro Store.
- Řeší problém s upgrady a lety pro pozdější verze HoloLens.
- Odebrání nepoužívaných předinstalovaných certifikátů z kořenového úložiště eSIM ze zařízení HoloLens

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic verze 1903 – aktualizace z února 2021
- Build 18362.1098

Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic verze 20H2 – aktualizace z ledna 2021
- Build 19041.1134

Vylepšení a opravy v aktualizaci:

- Vylepšený výkon při spouštění, obnovování a přepínání uživatelů, pokud je na zařízení mnoho uživatelů.
- Přidání podpory arm32 pro [Research Mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic verze 1903 – aktualizace z ledna 2021
- Build 18362.1091

Tato měsíční aktualizace kvality neobsahuje žádné změny, doporučujeme vyzkoušet si naše nejnovější buildy pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic verze 20H2 – aktualizace z prosince 2020
- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací

Přidáváme **novou funkci (Instalační program aplikací),** která vám umožní bezproblémověji instalovat aplikace na zařízení HoloLens 2. Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.** Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:
- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Jednoduše si do svého zařízení stáhněte (přes USB nebo přes Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) aplikace MDM, musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens důvěryhodný, aby bylo možné aplikaci nasadit. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)

**Pokyny k instalaci aplikace.**

1.  Ujistěte se, že se vaše zařízení nepovažuje za spravované.
1.  Ujistěte se, že je zařízení HoloLens 2 zapnuté a připojené k počítači.
1.  Ujistěte se, že jste přihlášeni k zařízení HoloLens 2.
1.  Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní úložiště\Soubory ke stažení.   Po zkopírování souboru můžete zařízení odpojit.
1.  Na zařízení HoloLens 2 Otevřete nabídku Start, vyberte Všechny aplikace a spusťte Průzkumník souborů aplikaci.
1.  Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat Toto zařízení a pak přejít na Položky ke stažení.
1.  Vyberte soubor yourapp.appxbundle.
1.  Spustí Instalační program aplikací. Vyberte tlačítko Install (Nainstalovat) a nainstalujte aplikaci.
Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

Ukázkové aplikace najdete na [GitHubu univerzálních ukázek Pro Windows,](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) kde tento tok otestujte.

Přečtěte si o úplném procesu [instalace aplikací na HoloLens 2 pomocí Instalační program aplikací](app-deploy-app-installer.md).  

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Vylepšení a opravy v aktualizaci:

- Sledování rukou teď udržuje sledování v mnoha nových případech, kdy by se dříve ztratila rukou.  V některých z těchto nových případů se bude aktualizovat pouze pozice uživatele na základě jeho skutečné ruky, zatímco druhá pozice je odvozena na základě předchozí pozice.  Tato změna pomáhá zlepšit konzistenci sledování v pohybech, jako je plevání, odhazování, tlesání a tlesění.  Pomáhá také v případech, kdy se ruce nachází blízko povrchu nebo drží objekt.  Při odvozování ručního odhadu se hodnota společné přesnosti nastaví na "Approximate" (Přibližný) místo na High (Vysoká). [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)
- Opravili jsme problém, kdy se při resetování kódu PIN pro účty Azure AD zobrazí chyba Něco se pokazilo.
- Při spouštění ET, Iris z aplikace nastavení, nového uživatele nebo informační zprávy by uživatelé měli vidět mnohem méně selhání při spuštění.
- Uživatelé by měli mít správné časové pásmo, které přichází z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic verze 1903 – aktualizace z prosince 2020
- Build 18362.1088

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naši nejnovější verzi Windows Holographic verze 20H2–prosinec 2020 Update a novou funkci Instalační program aplikací přidanou v sestavení.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic verze 20H2
- Build 19041.1128

Windows Holographic verze 20H2 je teď k dispozici a přináší skvělou sadu nových funkcí pro uživatele HoloLens 2 a it profesionály. Od automatického umístění oka po Správce certifikátů v Nastavení až po vylepšené funkce bezobrazovkového režimu a nové možnosti nastavení Autopilotu. Tato nová aktualizace umožňuje IT týmům převzít podrobnější kontrolu nad konfigurací a správou zařízení HoloLens a nabízí uživatelům ještě hladká holografická prostředí. 

Tato nejnovější verze je měsíční aktualizací verze 2004, ale tentokrát zahrnujeme nové funkce. Hlavní číslo sestavení zůstane stejné a služba Windows Update bude označovat měsíční verzi verze 2004 (build 19041). Na číslo sestavení se můžete podívat na obrazovce Nastavení > Informace a potvrdit, že jste na nejnovějším dostupném buildu 19041.1128+. Pokud chcete provést aktualizaci na nejnovější verzi, otevřete aplikaci Nastavení, přejděte na Update & Security a klepněte na Zkontrolovat aktualizace. Další informace o správě aktualizací HoloLens najdete na [této stránce.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co je nového ve Windows Holographic verze 20H2  

| Funkce                                              | Popis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Podpora funkce Auto Eye Position](hololens-release-notes.md#auto-eye-position-support) | Aktivně počítá pozice očí, aniž by uživatelé prošli sledováním očí.   |
| [Správce certifikátů](hololens-release-notes.md#certificate-manager)   | Umožňuje nové jednodušší metody instalace a odebrání certifikátů z aplikace Nastavení.     |
| [Automatické spuštění zřizování z USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Zřizovací balíčky na USB jednotkách automaticky zobrazí výzvu ke zřízení stránky pro spuštění počítače.                                                         |
| [Automatické potvrzení zřizovacího balíčku v OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Zřizovací balíčky se na stránce zřizování automaticky použijí během spuštění při spuštění zařízení.                                                         |
| [Automatické zřizování bez použití uživatelského rozhraní](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak kombinovat automatické spouštění zřizování a automatické potvrzení. |
| [Použití Autopilotu s Wi-Fi připojením](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Použijte Autopilot ze zařízení Wi-Fi bez potřeby ethernetového adaptéru. |
| [Tenantlockdown CSP a Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po registraci tenanta a použití zásad se zařízení může v tomto tenantovi zaregistrovat jenom pokaždé, když se zařízení resetuje nebo znovu zabliká. |
| [Globální přiřazený přístup](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nová metoda konfigurace pro režim veřejného terminálů s více aplikacemi, která používá beziosk na úrovni systému, takže je použitelný pro všechny.                  |
| [Automatické spuštění aplikace v bezobrazovkovém režimu s více aplikacemi](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Nastaví automatické spuštění aplikace při přihlášení do bezobrazovkovém režimu s více aplikacemi.                                                        |
| [Změny chování v bezobrazovkovém režimu pro zpracování selhání](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Selhání bezobrazovkového režimu teď má omezující záložní režim.                                                                                                |
| [Zásady HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nové zásady pro HoloLens     |
| [Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nové zásady umožňují uživatelům používat mezipaměť členství ve skupinách k použití bezobrazovkového režimu offline po nastavený počet dnů.                                        |
| [Nové zásady omezení zařízení pro HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Nově povolené zásady správy zařízení pro HoloLens 2                                                                                |
| [Nové zásady napájení pro HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nově podporované zásady pro nastavení časového limitu napájení  |
| [Aktualizace zásad](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nově povolené zásady umožňující kontrolu nad aktualizacemi           |
| [Povolená viditelnost stránky Nastavení pro HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Zásada pro výběr stránek, které se mají zobrazit v aplikaci Nastavení             |
| [Režim výzkumu](hololens-release-notes.md#research-mode) | Použití režimu Research na HoloLens 2 |
| [Zvýšení délky záznamu](hololens-release-notes.md#recording-length-increased) | Záznamy MRC se už neřízly na 5 minut. |
| [Vylepšení a opravy v aktualizaci](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Další opravy v aktualizaci   |

### <a name="auto-eye-position-support"></a>Podpora funkce Auto Eye Position

Pozice očí v HoloLens 2 umožňují přesné umístění hologramu, pohodlné zobrazení a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**AEP (Auto Eye Position)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel zařízení spustí. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová, a proto se tento proces opakuje, pokud uživatel zařízení odstartuje a znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasádá nezabý uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu neomešlený uživatel odkazuje na někoho, kdo předtím neprošel procesem sledování zraku na zařízení.

| Aktivní aplikace | Předchozí chování | Chování z Windows Holographic, verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace bez pohledu nebo Holographic Shell |Zobrazí se dialogové okno příkazového řádku sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno příkazového řádku sledování očí. | Výzva ke sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke streamu pohledu do oka. |

Pokud uživatel přechází z aplikace, která není pohledem povolená, na aplikaci, která přistupuje k pohledným datům, zobrazí se výzva k zadání hledaní. 

Veškeré ostatní chování systému bude podobné, jako když aktuální uživatel nemá aktivní sledování očí. Například gesto Jednoručné spuštění nebude povoleno. Při počátečním nastavení se prostředí prvního spuštění nezmění.

Pro prostředí, která vyžadují pohled na data nebo velmi přesné umístění hologramu, doporučujeme necibrovaným uživatelům spustit sledování očí. Je přístupný z příkazového řádku pro sledování očí nebo tak, že v nabídce Start spustíte aplikaci Nastavení a pak vyberete System > Nespouštět > Eye **>** Spuštění oka.

Tyto informace najdete později spolu s dalšími [informacemi o produktu](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené nástroje pro auditování, diagnostiku a ověřování pro zabezpečení a dodržování předpisů zařízení prostřednictvím nového Správce certifikátů Tato funkce vám umožní nasadit, řešit potíže a ověřit certifikáty ve velkém měřítku v komerčních prostředích.

Ve Windows Holographic verze 20H2 přidáváme Správce certifikátů v aplikaci Nastavení HoloLens 2. Přejděte na **Nastavení > Update & Security > Certificates**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů v zařízení. S novým Správcem certifikátů teď správci a uživatelé vylepšili auditování, diagnostiku a ověřování, aby zajistili, že zařízení zůstanou zabezpečená a vyhovující. 

-   **Auditování:** Možnost ověřit, že je certifikát správně nasazený, nebo ověřit, že byl správně odebrán. 
-   **Diagnostika:** Když dojde k problémům, ověření, že v zařízení existují příslušné certifikáty, šetří čas a pomáhá s řešením potíží. 
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

- Automatizované procesy, které umožňují menší interakci uživatelů, když se během spuštění počítače používají jednotky USB se zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek ručně spustit obrazovku zřizování během spuštění při spuštění počítače. Uživatelé teď mohou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na jednotce úložiště USB. 

1. Připojte jednotku USB se zřizovacím balíčkem během prvního interagovatelného okamžiku prvního zařízení.
1. Až bude zařízení připravené ke zřízení, automaticky se otevře výzva se stránkou zřizování. 

Poznámka: Pokud je usb flash disk při spouštění zařízení připojený k napájení, OOBE provede výčet stávajícího paměťového zařízení USB a bude sledovat, jestli se neschytí další zařízení.

Další informace o použití zřizovacích balíčků během OOBE najdete v dokumentaci ke [zřizování HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Další informace o [automatickém spouštění zřizování](hololens-provisioning.md#auto-launch-provisioning-from-usb) z USB najdete v dokumentaci ke zřizování HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacího balíčku v OOBE
- Automatizovaný proces, který umožňuje menší interakci uživatelů, a když se zobrazí stránka zřizovací balíček, automaticky použije všechny uvedené balíčky.

Když se zobrazí hlavní obrazovka zřizování, OOBE odpočítá 10 sekund, než automaticky začne používat všechny zřizovací balíčky. Do 10 sekund od ověření [balíčků,](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) které očekávali, je uživatelé stále mohou potvrdit nebo zrušit.

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní
- Kombinované automatické procesy pro menší interakce zařízení pro zřizování. 

Zkombinováním automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovacího balíčku může uživatel zřídit zařízení HoloLens 2 automaticky bez použití uživatelského rozhraní zařízení nebo dokonce s jeho používáním. Můžete dál používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení více zařízení najednou ve stejné oblasti. 

1. [Pomocí nástroje](hololens-provisioning.md) Windows Configuration Designer vytvořte [zřizovací balíček.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Vytvořte flash disk HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) na [build 19041.1361 nebo novější.](https://aka.ms/hololens2previewdownload) 
1. Jakmile [advanced recovery companion dokončí](https://www.microsoft.com/store/productId/9P74Z35SFRS8) blikající flash disk zařízení, odpojte kabel USB-C. 
1. Připojte jednotku USB k zařízení.
1. Když se zařízení HoloLens 2 spustí do OOBE, automaticky zjistí zřizovací balíček na USB disku a spustí stránku zřizování.
1. Po 10 sekundách zařízení automaticky použije zřizovací balíček. 

Vaše zařízení je teď nakonfigurované a [zobrazí obrazovku Provisioning Successful (Úspěšné zřizování).](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Použití Autopilotu s Wi-Fi připojením
- Odebráním potřebných adaptérů USB-C pro ethernetové snížení potřeb hardwaru umožníte funkci autopilotu fungovat na Wi-Fi připojených zařízeních.

Po připojení HoloLens 2 k síti Wi-Fi teď při spuštění OOBE zkontroluje počáteční projekt profil pro zařízení. Pokud se najde, použije se k dokončení připojení AAD a toku registrace. Jinými slovy, použití sítě Ethernet pro USB-C nebo Wi-Fi do adaptéru USB-C ještě není požadavkem, ale budou fungovat i v případě, že jsou k dispozici na začátku počátečního nastavení. Přečtěte si další informace o [autopilotu pro zařízení HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a autopilot
- Zachovává zařízení v tenantovi organizace tím, že je zamkne na tenanta i přes resetování nebo reflash zařízení. Díky dalšímu zabezpečení zakážete vytváření účtů prostřednictvím zřizování. 

Zařízení HoloLens 2 teď podporují TenantLockdown CSP jako [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Zprostředkovatel kryptografických služeb umožňuje, aby HoloLens 2 bylo vázané na registraci MDM jenom pomocí autopilotu. Jakmile se uzel RequireNetworkInOOBE poskytovatele TenantLockdown CSP nastaví na hodnotu true nebo false (zpočátku nastavená) na HoloLens 2, tato hodnota zůstane na zařízení i bez ohledu na to, jestli se jedná o opětovné spuštění, aktualizace operačního systému atd. 

Jakmile je uzel TenantLockdown CSP ' RequireNetworkInOOBE ' nastaven na hodnotu true na HoloLens 2, bude po připojení k síti po připojení k síti znovu čekat na neomezenou dobu pro stažení a použití profilu autopilotu. 

Jakmile je uzel TenantLockdown CSP ' RequireNetworkInOOBE ' nastaven na hodnotu true na HoloLens 2, v počátečním souboru OOBE nejsou povoleny tyto operace: 
- Vytváření místního uživatele pomocí zřizování za běhu 
- Provádění operace připojení ke službě Azure AD prostřednictvím zřizování za běhu 
- Výběr toho, kdo zařízení vlastní v prostředí OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak ho nastavit pomocí Intune? 
1. Vytvořte vlastní konfigurační profil zařízení OMA URI a zadejte hodnotu true pro uzel RequireNetworkInOOBE, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamčení klienta pomocí OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. Nastavte člena zařízení HoloLens 2 pro skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak zrušit nastavení RequireNetworkInOOBE TenantLockdown na HoloLens 2 pomocí Intune? 
1. Odeberte HoloLens 2 ze skupiny zařízení, ve které byla výše vytvořená konfigurace zařízení dříve přiřazena. 

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru URI OMA a zadejte hodnotu false pro RequireNetworkInOOBE, jak je znázorněno níže. Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím identifikátoru URI OMA v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. Nastavte člena zařízení HoloLens 2 pro skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. Po úspěšném nastavení této konfigurace zařízení na zařízení HoloLens 2 budou účinky TenantLockdown neaktivní. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co se stane při POČÁTEČNÍm spuštění, pokud je profil autopilotu nepřiřazený k HoloLens po nastavení TenantLockdown na hodnotu true? 
Při POČÁTEČNÍm navýšení bude profil pro autopilot čekat na neomezenou dobu stahování a zobrazí se dialogové okno. Aby se odstranily účinky TenantLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí jenom autopilotu a RequireNetworkInOOBE musí být nastavené tak, jak je popsané v předchozím kroku, než se odeberou omezení zavedená poskytovatelem CSP pro TenantLockdown. 

![Zobrazení v zařízení pro dobu, kdy se na zařízení vynutila zásada.](images/hololens-autopilot-lockdown.png)

Tyto informace se teď dají najít spolu se zbytkem autopilotu v rámci [TENANTLOCKDOWN CSP a autopilotu](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – celoobrazovkový režim
- Omezená Správa identit pro veřejný terminál tím, že povolíte novou metodu veřejného terminálu, která na úrovni systému aplikuje celoobrazovkový režim.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro celoobrazovkový celoobrazovkový režim, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Další informace o této nové funkci najdete podrobněji v veřejného [terminálu s přístupem k HoloLens](hololens-global-assigned-access-kiosk.md).

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

Dříve v případě, že došlo k selhání při použití celoobrazovkového režimu, můžete použít HoloLens pro zobrazení všech aplikací v nabídce Start. Nyní ve Windows holografické verzi 20H2 v případě selhání nebudou v nabídce Start zobrazeny žádné aplikace, jak je uvedeno níže: 

![Obrázek, který celoobrazovkový režim teď vypadá, když se nezdařil.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Zásady HoloLens
- Možnosti správy zařízení specificky pro HoloLens vytvořené pro správu zařízení. 

Pro zařízení HoloLens 2 ve Windows holografické verzi 20H2 se vytvořily nové zásady hybridní reality. Mezi nová poříditelné nastavení patří: nastavení jasu, nastavení hlasitosti, zakázání záznamu zvuku v hybridních zachyceních realit, nastavení, kdy se dá shromáždit Diagnostika a mezipaměť členství skupiny AAD.  

| Nové zásady HoloLens                                | Description                                                                               | Poznámky                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Povolí vypnutí tlačítek jasu, takže se nemění jas.       | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\VolumeButtonDisabled                  | Povolí vypnutí tlačítek hlasitosti, aby se při stisknutí této klávesy nezměnila hlasitost.               | 1 Ano, 0 No (výchozí)                                                |
| MixedReality\MicrophoneDisabled                    | Zakáže mikrofon, takže v HoloLens 2 není možné nahrávat zvuk.                      | 1 Ano, 0 No (výchozí)                                                |
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
1. Vytvořte profil konfigurace zařízení pro WebDirectory cílící na skupiny Azure AD a přiřaďte ho k zařízením s HoloLens. 
1. Vytvořte vlastní konfiguraci zařízení založenou na identifikátoru OMA URI, která nastaví tuto hodnotu této zásady na požadovaný počet dní (> 0) a přiřadí ji k zařízením s HoloLens. 
    1. Do textového pole OMA-URI by se měla zadat hodnota identifikátoru URI jako./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Hodnota může být mezi minimální a maximální povolenou hodnotou.
1. Zaregistrujte zařízení HoloLens a ověřte, že se na zařízení aplikují obě konfigurace. 
1. Umožněte uživateli Azure AD 1 přihlášení, když je dostupný internet, po přihlášení uživatele a členství ve skupině Azure AD se vytvoří mezipaměť. 
1. Uživatel Azure AD 1 teď může pracovat s HoloLens offline a používat ho pro celoobrazovkový režim, pokud hodnota zásady umožňuje X počet dnů. 
1. Kroky 4 a 5 se můžou opakovat pro všechny ostatní uživatele Azure AD N. klíčovým bodem, který tady znamená, že se musí přihlásit k zařízení přes Internet, aby aspoň jednou bylo možné určit, že jsou členy skupiny Azure AD, na kterou cílí konfigurace veřejného terminálu. 
 
> [!NOTE]
> Dokud se krok 4 neprovede pro uživatele Azure AD, dojde k chování při selhání zmíněném v "odpojeném" prostředí. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nové zásady omezení pro zařízení pro HoloLens 2
- Umožňuje uživatelům spravovat konkrétní zásady správy zařízení, jako je například blokování přidávání nebo odebírání zřizovacích balíčků.

Nově povolené zásady, které umožňují více možností správy zařízení HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Tyto dvě nové zásady pro AllowAddProvisioningPackage a AllowRemoveProvisioningPackage se přidávají do našich [běžných omezení zařízení](hololens-common-device-restrictions.md).

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
-   HoloLens 2 poskytuje nové funkce, které je možné používat společně s režimem výzkumu. Konkrétně přístup k rozhraním API pro ruční sledování a sledování očí, která doručují bohatší sadu experimentů.

Výzkumníci teď mají na svých zařízeních HoloLens možnost povolit výzkumný režim pro přístup ke všem těmto externím datovým proudům nezpracovaných obrazových senzorů. Režim výzkumu pro HoloLens 2 také poskytuje přístup k odečtům akcelerometru, krátoboru a krátometru. V rámci ochrany osobních údajů uživatelů nejsou nezpracované obrázky z fotoaparátů pro sledování očí dostupné prostřednictvím režimu výzkumu, ale směr pohledu je k dispozici prostřednictvím stávajících rozhraní API.

Další technické podrobnosti [najdete v dokumentaci](https://docs.microsoft.com/windows/mixed-reality/research-mode) k režimu výzkumu.

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
- Byl vyřešen problém, kdy uživatelé nemohli zřídit profily SÍTĚ VPN prostřednictvím zřizovacích balíčků.
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

Tato měsíční aktualizace kvality neobsahuje žádné citelné změny. Doporučujeme vyzkoušet si naše nejnovější sestavení pro Windows Holographic verze 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze září 2020
- Build 19041.1117

Vylepšení a opravy v aktualizaci:

- Řeší problém, který Visual Studio ladění aplikace, když se v souboru appxmanifest nachází SupportsMultipleInstances="true".
- Tato verze zahrnuje opravu detekce proxy serveru NCSI, která řeší selhání detekce internetu přes síťový proxy server. NCSI může k detekci připojení k internetu použít proxy server počítače a proxy server pro každý profil. NcSI bude v budoucí verzi podporovat proxy pro uživatele.
- Ve většině Windows Mixed Reality zařízení je směrový vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze HoloLens 2 však zarovnaly vektor tak, aby byl perpend se zobrazením panelů, což je posunutý o několik stupňů dolů vzhledem k ideální orientaci. Novější verze HoloLens 2 to opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.
- Tato verze obsahuje opravu pro zlepšení kvality časového razítka zvuku, která může přispět k problémům se zachytáváním videa.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic verze 1903 – aktualizace ze září 2020
- Build 18362.1079

Vylepšení a opravy v aktualizaci:

- Ve většině Windows Mixed Reality zařízení je směrový vektor dopředu paralelní k zemi, když je hlavička uživatele v neutrální pozici a hledí dopředu. Dřívější verze HoloLens 2 však zarovnaly vektor tak, aby byl perpend se zobrazením panelů, což je posunutý o několik stupňů dolů vzhledem k ideální orientaci. Novější verze HoloLens 2 to opraví, aby se zajistila sémantická konzistence napříč provedeními.
- Vylepšená odolnost při ručním sledování, která v konkrétních scénářích bude mít za následek menší ztráty sledování.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, verze 2004 – aktualizace ze srpna 2020
- Build 19041.1113

Vylepšení a opravy v aktualizaci:

- Aplikace nastavení už nebude odpovídat na možnosti registrace v aplikaci Iris nebo kalibraci sledování očí.
- Opravili jsme chybu při použití zřizovacího balíčku při spuštění OOBE, který přejmenuje zařízení a provede jiné akce (například připojení k síti), aby se po restartu zařízení v důsledku přejmenování nepodařilo provést další akce.
- Změněné barevné schéma počátečních toků nastavení zařízení, aby se zlepšila kvalita vizuálů

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows holografická verze 1903 – aktualizace ze srpna 2020
- Sestavení 18362,1074

Tato měsíční aktualizace kvality neobsahuje žádné významné změny, doporučujeme, abyste si vyzkoušeli naše nejnovější buildy pro Windows Holografick, verze 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows holografická verze 2004 – červenec 2020 – aktualizace
- Sestavení 19041,1109

Vylepšení a opravy v aktualizaci:

- Vývojáři si teď můžou vybrat mezi povolením nebo zakázáním portálu pro zařízení vyžadovat zabezpečené připojení.
- Vylepšení spolehlivosti pro aplikace se spouští po aktualizacích operačního systému.
- Výchozí jas složky Doručená pošta se změnil na 100 procent.
- Vyřešili jsme problém týkající se předávání HTTPS pro portál zařízení Windows na HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows holografická verze 1903 – červenec 2020 – aktualizace
- Sestavení 18362,1071

Vylepšení a opravy v aktualizaci:

- Opravili jsme problém, který by mohl způsobit, že se v aplikacích Unity při ztrátě nebo opětovném sledování ztratí hologramy.
- Opravili jsme problém, který způsobil exkluzivní aplikacím HoloLens návrat do prostředí při použití emulátoru HoloLens s hardwarovou akcelerací na určitých zařízeních.
- Vyřešili jsme problém týkající se předávání HTTPS pro portál zařízení Windows na HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows holografická verze 2004 – června 2020 – aktualizace
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

Další informace najdete v [Windows Autopilot pro zkušební verzi HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Požádejte správce účtu, aby se připojil k verzi AutoPilot Preview. Zařízení připravená pro Autopilot začnou brzy doručovat.*

### <a name="fido2-security-key-support"></a>Podpora klíčů zabezpečení FIDO2

Někteří uživatelé sdílejí zařízení HoloLens s ostatními uživateli v pracovním nebo školním prostředí. Je proto důležité, aby uživatelé mohli snadno zadávat dlouhá uživatelská jména a hesla. Fast Identity Online (FIDO) umožňuje komukoli ve vaší organizaci (tenant Azure AD) bezproblémově se přihlásit k HoloLens bez zadávání uživatelského jména nebo hesla.

Klíče zabezpečení FIDO2 jsou "nepřehledná" metoda ověřování bez hesla založená na standardech, která může být v jakémkoli provedení. FIDO je otevřený standard pro ověřování bez hesla. Umožňuje uživatelům a organizacím přihlásit se ke svým prostředkům bez uživatelského jména nebo hesla. Místo toho používají externí klíč zabezpečení nebo klíč platformy integrovaný do zařízení.

Pokud chcete začít, podívejte se [na stránku Povolení přihlašování pomocí bezpečnostního klíče bez hesla.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Vylepšená registrace MDM prostřednictvím zřizovacího balíčku

Zřizovací balíčky umožňují nastavit konfiguraci HoloLens prostřednictvím konfiguračního souboru, a ne pomocí prostředí HoloLens. Dříve bylo třeba zřizovací balíčky zkopírovat do interní paměti HoloLens. Teď mohou být na USB flash disku, aby se snadněji opakovaně šly opakovaně používat na několika zařízeních HoloLens a vy můžete zařízení zřovat paralelně. Zřizovací balíčky teď také podporují pole pro registraci ve správě zařízení, takže po zřízení už neexistuje žádné ruční nastavení.

Vyzkoušejte si to:

1. Stáhněte si nejnovější verzi Windows Configuration Designeru z Windows Storu do svého počítače.
1. Vyberte Provision HoloLens Devices Provision HoloLens 2 devices **(Zřídit zařízení HoloLens**  >  **2).**
2. Sestavte konfigurační profil. Potom zkopírujte všechny vytvořené soubory do úložného zařízení USB-C.
3. Připojte zařízení USB-C k libovolnému zařízení HoloLens s čerstvým bleskem. Potom stiskněte **tlačítka napájení pro** snížení hlasitosti a použijte  +   zřizovací balíček.

### <a name="line-of-business-application-install-status"></a>Stav instalace obchodních aplikací

Nasazení a správa aplikací MDM pro obchodní aplikace je pro HoloLens zásadní. Správci a uživatelé musí zobrazit stav instalace aplikace pro auditování a diagnostiku. V této verzi jsme přidali další podrobnosti do **části** Nastavení Účty Přístup do práce nebo do školy  >    >    >  **Klikněte na informace o vašem**  >  **účtu.**

### <a name="additional-csps-and-policies"></a>Další csp a zásady

Poskytovatel [konfiguračních služeb (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) je rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. V této verzi přidáme podporu pro další zásady, které správcům řízení zvýší počet nasazených zařízení HoloLens. Seznam csP podporovaných společností HoloLens najdete v tématu [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novinka v této verzi:

**CsP pro zásady** 

Poskytovatel konfigurační služby Policy umožňuje podniku konfigurovat zásady na zařízeních s Windows. V této verzi jsme přidali nové zásady pro HoloLens, které jsou zde uvedené. Další informace najdete v tématu Zásady [CSP podporované HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Byla přidána podpora pro povolení určitých mobilních širokopásmového zařízení, jako jsou telefony 5G/LTE a Wi-Fi hotspoty, když nejsou připojená k HoloLens 2 přes USB. Tato zařízení se teď zobrazují v **nastavení sítě jako** další ethernetové připojení. (Mobilní širokopásmové zařízení, která vyžadují externí ovladač, se nepodporují.) Tato funkce umožňuje připojení s velkou šířkou pásmaWi-Fi není dostupná a Wi-Fi není dostatečně výkonný. Další informace o podporovaných zařízeních USB najdete v tématu Připojení k zařízením Bluetooth a [USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Vylepšení sledování rukou

Tato verze obsahuje několik vylepšení ručního sledování:

- **Bodování představuje stabilitu:** Systém teď odolá odsouvání indexování, když ho uchytává šedě. Tato změna zvyšuje přesnost při nabízení tlačítek, psaní, posouvání obsahu a dalších. 
- **Menší nechtěné klepnutí ve vzduchu:** Vylepšili jsme detekci gesta klepnutí ve vzduchu. V několika běžných scénářích je teď méně náhodných aktivací, například když pustíte ruce na stranu.
- **Spolehlivost uživatelského přepínače:** Při aktualizaci velikosti ruky při sdílení zařízení je teď systém rychlejší a spolehlivější.
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

Aktualizovaná aplikace se integruje s Microsoft 365, která vám pomůže udělat více napříč zařízeními (aktuálně pouze US-English počítače). Na HoloLens 2 už Cortana nepodporuje určité příkazy specifické pro zařízení, jako je úprava svazku nebo restartování. Tyto možnosti teď podporují nové hlasové příkazy systému. Další informace o nové aplikaci Cortany najdete na našem [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Vylepšení a opravy kvality

Vylepšení a opravy také v aktualizaci:  
- Zavedli jsme systém aktivního zobrazení s tekutou displeji. Tato funkce zlepšuje stabilitu a zarovnání hologramů. Nyní zůstanou na místě, když přesunete svou hlavičku ze strany na stranu.
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
- Opravili jsme chybu "Třída rozhraní API WinRT IStreamSocketListener není zaregistrovaná" u 32bitových aplikací ARM.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic verze 1903 – aktualizace z března 2020 
- Build 18362.1056

Vylepšení a opravy v aktualizaci:

- Vylepšená stabilita hologramu ve smíšené realitě při použití *algoritmu HolographicDepthReprojectionMethod AutoPlanar*
- Zajistili jsme, aby souřadnicový systém připojený k vzorku s hloubkou BYL konzistentní s veřejnou dokumentací.
- Vylepšili produktivitu vývojářů tím, že zákazníkům umožnili vkládat velké objemy textu prostřednictvím portálu zařízení.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic verze 1903 – aktualizace z února 2020 
- Build 18362.1053

Vylepšení a opravy v aktualizaci:

- Dočasně zakázali rozhraní API HolographicSpace.UserPresence pro aplikace Unity. Tato změna zabraňuje problému, který způsoboval pozastavení některých aplikací při překlopení zorovače, a to i v případě, že bylo povolené nastavení Spustit na pozadí.
- Opravili jsme náhodné selhání HUP způsobené ručním sledováním, při kterém si uživatel po několika sekundách všiml zablokování uživatelského rozhraní a pak zpátky do prostředí.
- Vylepšené sledování rukou, takže když házíte ukazováčkem, je menší pravděpodobnost, že se horní část prstu neočekávaně cvrdí.
- Vylepšili jsme spolehlivost sledování hlavy, prostorového mapování a dalších runtime.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic verze 1903 – aktualizace z ledna 2020 
- Build 18362.1043
 
Vylepšení a opravy v aktualizaci:

- Vylepšená stabilita pro exkluzivní aplikace při práci s emulátorem HoloLens 2

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic verze 1903 – aktualizace z prosince 2019 
- Build 18362.1042

Vylepšení a opravy v aktualizaci:

- Zavedli jsme opravy poslední fáze reprodukování (LSR). Vylepšené vizuální vykreslování hologramů tak, aby se zdály stabilnější a ošemetnější díky přesnějšímu účtování jejich hloubky. Tento příznak bude po této aktualizaci patrnější, pokud aplikace nebudou správně nastavovat hloubku hologramů.
- Byla opravena stabilita výhradních aplikací a navigace mezi exkluzivními aplikacemi.
- Vyřešili jsme problém, kdy zachytávání hybridní reality nemohlo po několika dnech v pohotovostním stavu nahrát video.
- Vylepšená stabilita hologramu

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic verze 1903 – aktualizace z listopadu 2019 
- Build 18362.1039

Vylepšení a opravy v aktualizaci:

- Opravili jsme **funkčnost příkazu Select** voice commands during initial setup for en-CA and en-AU (Výběr hlasových příkazů během počátečního nastavení pro en-CA a en-AU).
- Vylepšená vizuální kvalita objektů umístěných daleko v nejnovějších verzích Unity a Mixed Reality Toolkit (MRTK).
- Opravili jsme problémy s holografickými aplikacemi, které se při spuštění zablokují v pozastaveném stavu, dokud se nabídka Start neotevřela a pak nezavřela.
- Opravy a vylepšení shody modulu runtime OpenXR pro HoloLens 2 a emulátor
