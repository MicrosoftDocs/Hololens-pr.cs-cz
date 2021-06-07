---
title: Představujeme nové Microsoft Edge
description: Další informace o nové aplikaci Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, prohlížeč
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: aefb414deb68376ea45e792f21a929fac7cf3969
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379332"
---
# <a name="introducing-the-new-microsoft-edge"></a>Představujeme nové Microsoft Edge

![Animace staršího Microsoft Edge loga na nové Microsoft Edge loga](images/new-edge.gif)

Nový Microsoft Edge využívá [projekt Chromium open source,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) aby pro zákazníky vytvořil lepší kompatibilitu a menší fragmentaci webu pro webové vývojáře.

S [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)je nová Microsoft Edge poprvé dostupná zákazníkům HoloLens 2. Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce Poslat zpětnou **vazbu** v novém Microsoft Edge nebo [přes Centrum Feedback](hololens-feedback.md).

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která [se](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) už v nových verzích nepodporuje.

![Snímek obrazovky Microsoft Edge nového snímku obrazovky](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Spuštění nové Microsoft Edge

Nová Microsoft Edge ![Ikona Microsoft Edge nový](images/new_edge_logo.png) (znázorněná modrou a zelenou ikonou swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Při prvním spuštění nové aplikace Microsoft Edge HoloLens 2 se vaše nastavení a data naimportuje ze starší verze Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

Nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče pro HoloLens 2, než byly dříve dostupné ve starších verzích Microsoft Edge.

Tady je několik užitečných zdrojů informací o správě nastavení zásad pro nové Microsoft Edge:

- [Konfigurace Microsoft Edge zásad pomocí Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [starší verze Microsoft Edge mapování Microsoft Edge zásad](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapování zásad Microsoft Edge Google Chrome](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Úplná [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada funguje na HoloLens 2. Otestovali jsme a potvrdili jsme, že nová zásada Microsoft Edge všech starších verzí zásad Microsoft Edge dříve podporovaných na HoloLens 2 fungovala podle očekávání. V [starší verze Microsoft Edge Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zásad najdete nový ekvivalent Microsoft Edge zásad prohlížeče Microsoft Edge, které jste s HoloLens 2 měli.
>
> Existují alespoň dvě nové zásady Microsoft Edge, o které víme, že *nebudou* s HoloLens 2 fungovat:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nové verze Microsoft Edge HoloLens 2

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
- WebXR a rozšíření 360 Viewer
- Obnovení obsahu do správného okna při procházení několika oken umístěných ve vašem prostředí

**Scénáře a funkce, u které se neočekává, že budou fungovat:**
- Prostorový zvuk z několika oken se souběžně zvukovými streamy
- "See it, say it"
- Tisk

**Hlavní známé problémy s prohlížečem:**
- Náhled lupy na holografické klávesnici byl pro novou obrazovku Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v režimu Sledovat mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna tlačítkem X.
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit neočekávané neaktivování ostatních 2D oken aplikací. Tato okna můžete znovu aktivovat opětovnou interakcí.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge kanálů Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat více verzí najednou. 

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
  1. Uložte soubor .msix do složky Stažené soubory (nebo do jiné složky, kterou snadno najdete).
  1. Pomocí [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na počítači nainstalujte stažený soubor .msix na HoloLens 2.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Použití nástroje WDAC k blokování nových Microsoft Edge

Aby správci IT mohli aktualizovat zásady [WDAC](windows-defender-application-control-wdac.md) tak, aby blokují novou aplikaci Microsoft Edge, musíte do zásad přidat následující položky.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí mohou mít omezení sítě, která je třeba vzít v úvahu. Pokud chcete zajistit bezproblémové prostředí s novým Edgem, [povolte tyto koncové body Microsoftu.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens.](hololens-offline.md)

## <a name="install-web-apps"></a>Instalace webových aplikací
 > [!Note]
> Od [verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ve Windows Holographic se už webová aplikace Office nebude předinstalovat. 

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci systém Microsoft Office zobrazit a upravit soubory hostované na SharePointu nebo OneDrivu. Webovou aplikaci Office nainstalujete tak, že na panelu Adresa navštívíte a vyberete tlačítko App Available (Aplikace k dispozici) nebo Install Office (Nainstalovat https://www.office.com Office).   Potvrďte **výběrem** možnosti Nainstalovat.
> [!IMPORTANT]
> Funkce webové aplikace Office je dostupná jenom v případě, že holoLens 2 má aktivní připojení k internetu.

## <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer


Nový Microsoft Edge zahrnuje podporu WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Mnoho imerzivních webových prostředí bylo navrženo s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale holoLens 2 tato prostředí podporuje. Standard WebXR také umožňuje rozšířenou imerzivní webovou prostředí s hybridní realitou, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že pro zákazníky HoloLens 2, kteří si to budou zkoušet, přijde nové imerzivní prostředí rozšířené hybridní reality.

Rozšíření 360 Viewer je postaveno na WebXR a automaticky se nainstaluje společně s novou Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

### <a name="how-to-use-webxr"></a>Jak používat WebXR

1. Přejděte na web s podporou WebXR.
1. Na webu vyberte tlačítko pro **zadání VR** . Umístění a vizuální znázornění tohoto tlačítka se může na webu lišit, ale může vypadat podobně jako:

    ![Zadejte příklad tlačítka VR.](images/75px-enter-vr.png)

1. Při prvním pokusu o spuštění WebXR prostředí v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení, vyberte možnost **Povolení**.
1. Použijte [gesta HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) k manipulaci s prostředím.
1. Pokud prostředí nemá tlačítko **ukončit** , vraťte se domů pomocí [gesta Start](hololens2-basic-usage.md#start-gesture) .

**Doporučené ukázky WebXR**
- 360 Viewer (viz další oddíl)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR nátěr](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na YouTube na video o 360.
1. V snímku videa vyberte tlačítko náhlavní soupravu Mixed reality:

    ![Tlačítko pro aktivaci 360 Viewer](images/enter-360-viewer.jpg)

1. Při prvním pokusu o spuštění nástroje 360 Viewer v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení. Vyberte možnost **udělit**.
1. [Klepnutím na Air](hololens2-basic-usage.md#select-using-air-tap) otevřete ovládací prvky přehrávání. K přehrání a pozastavení použijte [ruky a klepněte na tlačítko Air](hololens2-basic-usage.md#select-using-air-tap) , přeskočte zpátky na pozadí, zapnout nebo vypnout titulky nebo zastavte prostředí (které ukončí moderní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Známé problémy pro WebXR a 360 Viewer
- V závislosti na složitosti WebXR prostředí může snímkový kmitočet vyřadit nebo Stutter.
- Podpora kloubových spojek v WebXR není ve výchozím nastavení povolená. Vývojáři můžou povolit podporu prostřednictvím edge://flags zapnutím "WebXR rukou".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby v WebXR a v prohlížeči 360

Sdílejte prosím svůj názor a chyby pomocí našeho týmu prostřednictvím funkce pro **odeslání zpětné vazby** v novém Microsoft Edge.
