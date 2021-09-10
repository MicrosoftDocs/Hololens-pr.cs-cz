---
title: Představujeme nový Microsoft Edge
description: Další informace o nové aplikaci Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, prohlížeč
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427919"
---
# <a name="introducing-the-new-microsoft-edge"></a>Představujeme nový Microsoft Edge

![animace starší verze Microsoft Edge loga na nové Microsoft Edge logo.](images/new-edge.gif)

nový Microsoft Edge [přijme projekt Chromium open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) , aby vytvořil lepší kompatibilitu pro zákazníky a méně fragmentaci webu pro webové vývojáře.

[Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)je nový Microsoft Edge k dispozici pro HoloLens 2 zákazníky poprvé! pošlete nám svůj názor a chyby pomocí našeho týmu prostřednictvím funkce pro **odeslání zpětné vazby** v novém Microsoft Edge nebo prostřednictvím [centra pro zpětnou vazbu](hololens-feedback.md).

> [!IMPORTANT]
> tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která již není v nových verzích [podporována](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) .

![nový snímek obrazovky Microsoft Edge.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Spouští se nový Microsoft Edge.

Nový Microsoft Edge ![ikona nové Microsoft Edge](images/new_edge_logo.png) (reprezentované modrou a zelenou ikonou) jsou připnuté na nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> když poprvé spustíte nový Microsoft Edge v HoloLens 2, vaše nastavení a data se naimportují ze starší verze Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

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

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>co očekávat od nového Microsoft Edge v HoloLens 2

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

**Nejčastější známé problémy prohlížeče:**
- Pro nové Microsoft Edge je verze Preview pro lupu vypnutá. Doufáme, že tuto funkci znovu povolíme v budoucí aktualizaci, jakmile bude zvětšení fungovat správně.
- Zvuk může být přehráván z nesprávného okna prohlížeče, pokud máte otevřeno a aktivní jiné okno prohlížeče. Tento problém můžete obejít tak, že zavřete jiné aktivní okno, které nemá přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v režimu "pořídit" bude pokračovat přehrávání zvuku, pokud zakážete režim "pořídit". Tento problém můžete obejít tak, že přehrávání zvuku zastavíte ještě před tím, než zakážete režim "pořídit" nebo zavřením okna tlačítkem X.
- interakce s aktivními Microsoft Edge windows může způsobit neočekávané neočekávané neočekávané ukončení jiných oken aplikace 2d. Tato okna můžete znovu aktivovat pomocí interakce s nimi.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

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

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Blokování nových Microsoft Edge pomocí WDAC

pro správce IT, kteří chtějí aktualizovat [zásady WDAC](windows-defender-application-control-wdac.md) k blokování nové aplikace Microsoft Edge, budete muset do své zásady přidat následující.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí můžou mít k dispozici omezení sítě, aby se mohla brát v úvahu. Chcete-li zajistit hladké prostředí s novým okrajem, [povolte tyto koncové body společnosti Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Instalace webových aplikací
 > [!Note]
> od [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1), Office webová aplikace už nebude předem nainstalovaná. 

novou hranici můžete použít k instalaci webových aplikací společně s aplikacemi Microsoft Store. můžete například nainstalovat Microsoft Office webové aplikace pro zobrazení a úpravy souborů hostovaných v SharePoint nebo OneDrive. pokud chcete nainstalovat Office webovou aplikaci, přejděte na https://www.office.com adresu a vyberte aplikaci, kterou **máte k dispozici** , nebo si na adresní řádek **nainstalujte Office** tlačítko. Kliknutím na **instalovat** potvrďte.
> [!IMPORTANT]
> funkce Office webové aplikace je dostupná jenom v případě, že má HoloLens 2 aktivní připojení k internetu.

## <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer


nový Microsoft Edge zahrnuje podporu pro WebXR, což je nový standard pro vytváření moderního webového prostředí (nahrazuje WebVR). mnoho poutavých webových prostředí bylo navrženo s ohledem na VR (nahrazuje vaše pole zobrazení virtuálním prostředím), ale tato prostředí jsou také podporována HoloLens 2. Standard WebXR také umožňuje rozšířit a míchat působivá webová prostředí, která využívají vaše fyzické prostředí. protože vývojáři stráví více času s WebXR, předpokládáme, že pro zákazníky HoloLens 2 se dokončí nová rozšířená a smíšená prostředí realit, která vám pomůžou vyzkoušet!

rozšíření pro program 360 Viewer je postavené na WebXR a automaticky se instaluje společně s novým Microsoft Edge v HoloLens 2. Toto webové rozšíření vám dává možnost ponořit si vaše videa 360 ve stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

### <a name="how-to-use-webxr"></a>Jak používat WebXR

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

### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na video o 360 stupních na YouTube.
1. V rámečku videa vyberte tlačítko náhlavní soupravy hybridní reality:

    ![Tlačítko pro aktivaci prohlížeče 360.](images/enter-360-viewer.jpg)

1. Když se poprvé pokusíte spustit prohlížeč 360 v konkrétní doméně, prohlížeč požádá o souhlas se zadáním imerzivního zobrazení. Vyberte **Povolit.**
1. [Klepnutím ve vzduchu](hololens2-basic-usage.md#select-using-air-tap) vysunutím ovládacích prvků přehrávání Pomocí [ručních paprsků](hololens2-basic-usage.md#select-using-air-tap) a klepnutí ve vzduchu můžete přehrát/pozastavit, přeskočit vpřed/zpět, zapnout nebo vypnout titulky nebo ukončit prostředí (tím se ukončí imerzivní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Hlavní známé problémy s WebXR a 360 Viewerem
- V závislosti na složitosti prostředí WebXR může snímková frekvence poklesat nebo se zhoršit.
- Podpora pro articulated handu v WebXR není ve výchozím nastavení povolená. Vývojáři mohou podporu povolit prostřednictvím edge://flags zapnutím nastavení "Ruční vstup WebXR".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby k WebXR a prohlížeči 360

Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce **Poslat** zpětnou vazbu v novém Microsoft Edge.
