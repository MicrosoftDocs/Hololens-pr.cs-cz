---
title: Představujeme nové Microsoft Edge
description: Další informace o nové aplikaci Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, Edge, internet, prohlížeč
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035991"
---
# <a name="introducing-the-new-microsoft-edge"></a>Představujeme nové Microsoft Edge

![Animace staršího Microsoft Edge loga k novému Microsoft Edge logu](images/new-edge.gif)

Nový Microsoft Edge [přijme projekt Chromium open source,](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) aby pro zákazníky vytvořil lepší kompatibilitu a pro webové vývojáře méně fragmentace webu.

S [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)je nový Microsoft Edge poprvé k dispozici HoloLens 2 zákazníkům. Podělte se s naším týmem o zpětnou vazbu a chyby prostřednictvím funkce Poslat zpětnou vazbu v novém Microsoft Edge nebo [přes Centrum Feedback](hololens-feedback.md). 

> [!IMPORTANT]
> Tato nová Microsoft Edge automaticky nahrazuje starší Microsoft Edge, která [se](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) už v nových verzích nepodporuje.

![Nový Microsoft Edge obrazovky](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Spuštění nové Microsoft Edge

Nový Microsoft Edge ![Nová Microsoft Edge ikony](images/new_edge_logo.png) (znázorněná ikonou modré a zelené swirl) je připnutá k nabídka Start a automaticky se spustí při aktivaci webového odkazu.

> [!NOTE]
> Při prvním spuštění nového Microsoft Edge na HoloLens 2 se vaše nastavení a data naimportuje ze starší verze Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurace nastavení zásad pro nové Microsoft Edge

Nový Microsoft Edge nabízí správcům IT mnohem širší sadu zásad prohlížeče pro HoloLens 2, než byly dříve dostupné ve starších verzích Microsoft Edge.

Tady je několik užitečných zdrojů informací o správě nastavení zásad pro nové Microsoft Edge:

- [Konfigurace Microsoft Edge zásad pomocí Microsoft Intune](/deployedge/configure-edge-with-intune)
- [starší verze Microsoft Edge mapování Microsoft Edge zásad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapování zásad na Microsoft Edge Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Úplná [Microsoft Edge Enterprise dokumentace](/deployedge/)

> [!IMPORTANT]
> Vzhledem k objemu zásad prohlížeče podporovaných novou Microsoft Edge nemůže náš tým zaručit, že každá nová zásada bude fungovat HoloLens 2. Otestovali a potvrdili jsme ale, že nové zásady Microsoft Edge všechny starší verze zásad Microsoft Edge dříve podporované u HoloLens 2 fungují podle očekávání. V [starší verze Microsoft Edge se Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) mapování zásad a vyhledejte nový ekvivalent Microsoft Edge všech starších zásad prohlížeče Microsoft Edge, které jste s HoloLens 2 HoloLens.
>
> Minimálně dvě nové zásady Microsoft Edge, o které víme, *že nebudou* fungovat s HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Co očekávat od nového Microsoft Edge na HoloLens 2

Vzhledem k tomu, že Microsoft Edge je nativní aplikace Win32 s novou vrstvou adaptéru UPW, která umožňuje spuštění na zařízeních jen pro UPW, jako je HoloLens 2, nemusí být některé funkce okamžitě dostupné. V nadcházejících měsících budeme podporovat nové scénáře a funkce, proto v tomto prostoru najdete aktuální informace.

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
- Rozšíření WebXR a 360 Viewer
- Obnovení obsahu do správného okna při procházení několika oken umístěných ve vašem prostředí

**Scénáře a funkce, u které se neočekává, že budou fungovat:**
- Prostorový zvuk z několika oken se souběžně streamy zvuku
- "See it, say it"
- Tisk

**Hlavní známé problémy s prohlížečem:**
- Náhled lupy na holografické klávesnici byl pro novou obrazovku Microsoft Edge. Doufáme, že tuto funkci znovu umožníme v budoucí aktualizaci, jakmile zvětšení bude fungovat správně.
- Zvuk se může přehrát z nesprávného okna prohlížeče, pokud máte otevřené a aktivní jiné okno prohlížeče. Tento problém můžete vyřešit zavřením druhého aktivního okna, které by nemělo přehrávat zvuk.
- Při přehrávání zvuku z okna prohlížeče v režimu Sledovat mě se zvuk bude přehrávat i v případě, že zakážete režim Sledovat mě. Tento problém můžete vyřešit zastavením přehrávání zvuku před zakázáním režimu Sledovat mě nebo zavřením okna tlačítkem X.
- Interakce s aktivními aplikacemi Microsoft Edge windows může způsobit, že ostatní okna 2D aplikací neočekávaně prochádí. Tato okna můžete znovu aktivovat opětovnou interakcí.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanály Insider

Tým Microsoft Edge komunitě Edge Insider k dispozici tři kanály Preview: Beta, Dev a Canary. Instalace kanálu preview neinstaluje vydanou verzi Microsoft Edge na HoloLens 2 a můžete nainstalovat víc verzí najednou. 

Další informace [o komunitě Edge Insider najdete na domovské stránce](https://www.microsoftedgeinsider.com) Microsoft Edge Insider. Další informace o různých kanálech Edge Insider a o tom, jak začít, najdete na stránce pro [stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)

Pro instalaci kanálů Insider Microsoft Edge několik metod, které HoloLens 2:

**Přímá instalace na zařízení (aktuálně dostupná pouze pro nespravovaná zařízení)**
  1. Na stránce HoloLens 2 přejděte na stránku [pro stažení Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **Stáhnout pro HoloLens 2** pro kanál Edge Insider, který chcete nainstalovat.
  1. Spusťte stažený soubor .msix z fronty pro stahování Edge nebo ze složky Stažené soubory (pomocí příkazu Průzkumník souborů).
  1. [Spustí se instalační](app-deploy-app-installer.md) program aplikace.
  1. Vyberte **tlačítko** Nainstalovat.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

**Instalace prostřednictvím počítače s Windows Portál zařízení [(vyžaduje](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) povolení vývojářského režimu na počítači HoloLens 2)**
  1. Na počítači přejděte na stránku pro stažení [Aplikace Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Vyberte tlačítko **se šipkou rozevíracího** seznamu vedle tlačítka Stáhnout pro Windows 10 pro kanál Edge Insider, který chcete nainstalovat.
  1. V **HoloLens vyberte 2.**
  1. Uložte soubor .msix do složky Stažené soubory na počítači (nebo do jiné složky, kterou snadno najdete).
  1. Pomocí [Windows Portál zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na počítači nainstalujte stažený soubor .msix na HoloLens 2.
  1. Po úspěšné instalaci najdete Microsoft Edge Beta, Dev nebo Canary jako samostatnou položku v **Všechny aplikace** seznamu nabídka Start.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Použití nástroje WDAC k blokování nových Microsoft Edge

Aby správci IT mohli aktualizovat zásady [WDAC](windows-defender-application-control-wdac.md) tak, aby blokují novou aplikaci Microsoft Edge, musíte do zásad přidat následující položky.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Správa koncových bodů pro nové Microsoft Edge

Některá prostředí mohou mít omezení sítě, která je třeba vzít v úvahu. Pokud chcete zajistit bezproblémové prostředí s novým Edgem, [povolte tyto koncové body Microsoftu.](/deployedge/microsoft-edge-security-endpoints)

Přečtěte si další informace o aktuálně dostupných [koncových bodech pro HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Instalace webových aplikací
 > [!Note]
> Od [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)už nebude Office webová aplikace předem nainstalovaná. 

Nový Edge můžete použít k instalaci webových aplikací společně s Microsoft Store aplikacemi. Můžete například nainstalovat webovou aplikaci Microsoft Office zobrazit a upravit soubory hostované na SharePoint nebo OneDrive. Pokud chcete nainstalovat Office aplikaci, navštivte a vyberte tlačítko App Available (Aplikace k dispozici) https://www.office.com nebo Install Office **(Nainstalovat** aplikaci) na panelu Adresa.  Potvrďte **výběrem** možnosti Nainstalovat.
> [!IMPORTANT]
> Office webové aplikace je dostupná jenom v případě, že HoloLens 2 má aktivní připojení k internetu.

## <a name="webxr-and-360-viewer"></a>WebXR a 360 Viewer


Součástí nového Microsoft Edge je podpora WebXR, což je nový standard pro vytváření imerzivních webových prostředí (nahrazení WebVR). Řada imerzivních webových prostředí byla navržena s ohledem na virtuální prostředí (nahradí vaše zorné pole virtuálním prostředím), ale tato prostředí podporuje také HoloLens 2. Standard WebXR také umožňuje rozšířit imerzivní webová prostředí hybridní reality, která používají vaše fyzické prostředí. S tím, jak vývojáři tráví více času s WebXR, očekáváme, že nová imerzivní prostředí rozšířené reality a hybridní reality HoloLens 2 zákazníci to budou zkoušet!

Rozšíření 360 Viewer je postaveno na WebXR a automaticky se nainstaluje společně s novým Microsoft Edge na HoloLens 2. Toto webové rozšíření vám umožňuje ponořit se do videí o 360 stupních. YouTube nabízí největší výběr 360 videí, takže doporučujeme začít tam.

### <a name="how-to-use-webxr"></a>Jak používat WebXR

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

### <a name="how-to-use-360-viewer"></a>Jak používat prohlížeč 360

1. Přejděte na YouTube na video o 360.
1. V snímku videa vyberte tlačítko náhlavní soupravu Mixed reality:

    ![Tlačítko pro aktivaci nástroje 360 Viewer.](images/enter-360-viewer.jpg)

1. Při prvním pokusu o spuštění nástroje 360 Viewer v konkrétní doméně bude prohlížeč požádat o souhlas s přechodem do moderního zobrazení. Vyberte možnost **udělit**.
1. [Klepnutím na Air](hololens2-basic-usage.md#select-using-air-tap) otevřete ovládací prvky přehrávání. K přehrání a pozastavení použijte [ruky a klepněte na tlačítko Air](hololens2-basic-usage.md#select-using-air-tap) , přeskočte zpátky na pozadí, zapnout nebo vypnout titulky nebo zastavte prostředí (které ukončí moderní zobrazení). Ovládací prvky přehrávání zmizí po několika sekundách nečinnosti.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Známé problémy pro WebXR a 360 Viewer
- V závislosti na složitosti WebXR prostředí může snímkový kmitočet vyřadit nebo Stutter.
- Podpora kloubových spojek v WebXR není ve výchozím nastavení povolená. Vývojáři můžou povolit podporu prostřednictvím edge://flags zapnutím "WebXR rukou".
- 360 videí z jiných webů než YouTube nemusí fungovat podle očekávání.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Poskytnutí zpětné vazby v WebXR a v prohlížeči 360

Sdílejte prosím svůj názor a chyby pomocí našeho týmu prostřednictvím funkce pro **odeslání zpětné vazby** v novém Microsoft Edge.
