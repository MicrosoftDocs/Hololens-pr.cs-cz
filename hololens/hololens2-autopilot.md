---
title: Windows Autopilot pro HoloLens 2
description: Zjistěte, jak nastavit, nakonfigurovat a řešit potíže s Autopilotem na HoloLens 2.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilota
manager: sekerawa
ms.openlocfilehash: 46b57e44186b8944e58e68da66306bbe445b704a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924442"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

## <a name="overview"></a>Přehled

Pokud chcete nasazení provést ve velkém měřítku, doporučujeme začít s Windows Autopilotem. Považuje se za "malý dotek" v tom, že výrazně zjednodušuje HoloLens pro IT i koncové uživatele. 

Na nejvyšší úrovni správce IT obvykle vytvoří konfigurace připravené pro firmy a zaregistruje zařízení HoloLens 2 na portálech MDM. Když se HoloLens 2 zařízení spustí s prostředím při spuštění a připojí se k internetu, konfigurace připravené pro firmy pro zaregistrované zařízení HoloLens 2 se automaticky stáhnou a použijí, aby byla zařízení připravená pro firmy bez zásahu uživatele.

Další informace najdete v tématu [Přehled Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot) článku.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Podporovaný scénář Autopilotu na HoloLens 2

> [!NOTE]
> Konfigurace Autopilotu pro HoloLens v Microsoft Endpoint Manager přechází z **Public Preview** **na všeobecnou dostupnost.** Autopilot budou moct nastavit všichni tenanti v Centru pro správu MEM.

Počínaje Windows Holographic verze 2004 podporuje HoloLens 2 režim automatického nasazení Windows [Autopilot](/mem/autopilot/self-deploying) s Microsoft Intune (mdm třetích stran se nepodporuje). Tato konfigurace snižuje režijní náklady na správu inventáře, náklady na přípravu zařízení a volání na podporu od zaměstnanců během nastavování. Další informace najdete v [Windows Autopilot.](/mem/autopilot/windows-autopilot)

Stejně jako u zařízení Surface se doporučuje, aby zákazníci ve společnosti Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejce nebo distributor) zaregistrovali zařízení zaregistrovaná ve službě Autopilot prostřednictvím Partnerské centrum.

Když uživatel spustí proces samosazování Autopilotu, Autopilot dokončí následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD). Autopilot pro HoloLens nepodporuje připojení ke službě Active Directory ani hybridní připojení k Azure AD.

1. Pomocí Azure AD zaregistrujte zařízení ve službě Microsoft Endpoint Manager (nebo jiné službě MDM).

1. Stáhněte a použijte zásady, certifikáty, síťové profily a aplikace cílené na zařízení.

1. Zobrazí přihlašovací obrazovku uživateli.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurace Autopilotu pro HoloLens 2

Při nastavení prostředí postupujte následovně:

1. [Zkontrolujte požadavky na Windows Autopilot pro HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Povolení automatické registrace MDM](#2-enable-automatic-mdm-enrollment)

1. (jenom pro Intune) [Ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Zaregistrujte zařízení v Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Vytvořte skupinu zařízení.](#5-create-a-device-group)

1. [Vytvořte profil Autopilot a přiřaďte ho ke skupině zařízení.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Vytvořte konfiguraci esp (Enrollment Status Page) a přiřaďte ji ke skupině zařízení.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Ověřte stav profilu zařízení HoloLens zařízení.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Kontrola požadavků na Windows Autopilot pro HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Projděte si následující části článku Windows požadavky Autopilotu:

- [Požadavky sítě](/mem/autopilot/networking-requirements)  
- [Licenční požadavky](/mem/autopilot/licensing-requirements)  
- [Požadavky na konfiguraci](/mem/autopilot/configuration-requirements)

**V článku [o Windows](/windows/deployment/windows-autopilot/self-deploying#requirements)režimu Self-Deploying Autopilot si prohlédněte požadavky.** Vaše prostředí musí splňovat tyto požadavky a standardní požadavky Windows Autopilot. V tomto článku si není muset prohlédněte oddíly "Krok za krokem" a "Ověření". Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Ujistěte se, že zařízení ještě nejsou členy Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení Autopilotu dokončí tyto kroky. Pokud se chcete ujistit, že jsou vyčištěné všechny informace týkající se zařízení, podívejte se na stránky Zařízení na portálech Azure AD i Intune.  Funkce Převést všechna cílová zařízení na Autopilot se v HoloLens nepodporuje.

#### <a name="review-hololens-os-requirements"></a>Projděte HoloLens na operační systém:

Pokud chcete ověřit verzi sestavení na vašem zařízení nebo odkazovat na nejnovější verzi operačního systému, použijte [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) a naše pokyny [k odkazování na zařízení.](hololens-recovery.md) Na zařízeních dodaných do konce září 2020 Windows předinstalovanou verzi Holographic 1903. Obraťte se na prodejce a ujistěte se, že vám budou dodána zařízení připravená pro Autopilot.

 Minimální verzi operačního systému | Podporovaná funkce | Poznámky
 ------ | ------ | ------  
 [Windows Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) nebo novější | 1. Scénář automatického nasazení Autopilotu na HoloLens 2. | Stahování profilu Autopilot se podporuje pouze přes Ethernet. Než ho HoloLens, ujistěte se, že je připojený k síti ethernet pomocí adaptéru USB-C na **Ethernet.**  Pokud plánujete, že se Autopilot zahodí do mnoha HoloLens zařízení, doporučujeme naplánovat infrastrukturu adaptéru. Rozbočovače USB nedoporučujeme, protože často vyžadují instalaci ovladačů třetích stran, které nejsou podporované v HoloLens.
 [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) nebo novější | 1. Stahování profilu Autopilot přes Wi-Fi <br> 2. [Uzamknutí tenanta CSP](#tenant-lockdown-csp-and-autopilot) a Autopilot k uzamčení zařízení pomocí tenanta určeného autopilotem. | V případě potřeby můžete i nadále používat ethernetové adaptéry. U zařízení připojených přes Wi-Fi musí uživatel jenom: <ul> <li> Projdete scénu s vousy. </li> <li> Zvolte jazyk a národní prostředí. </li> <li> Spustit z pohledu zraku. </li> <li> Úspěšně se připojte k požadované síti Wi-Fi. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Povolení automatické registrace MDM:

Aby byl Autopilot úspěšný, musíte ve svém virtuálním počítači povolit automatickou registraci MDM Azure Portal. Tím umožníte registraci zařízení bez uživatele.

Další informace o nastavení najdete v následujícím [](/mem/intune/enrollment/quickstart-setup-auto-enrollment) krátkém průvodci povolením automatické registrace [MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) nebo v průvodci rychlým zahájením automatické registrace.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.

Aby byl Autopilot úspěšný, musíte zajistit, aby se vaše HoloLens mohli zaregistrovat. Vzhledem HoloLens, že se Windows zařízení, nebude nutné mít žádná omezení registrace, která by mohla vaše nasazení blokovat. [Zkontrolujte tento seznam omezení a](/mem/intune/enrollment/enrollment-restrictions-set) ujistěte se, že budete moct zaregistrovat zařízení.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registrace zařízení v Windows Autopilotu

Vaše zařízení musí být před prvním nastavením zaregistrovaná Windows Autopilotu.

Existují tři hlavní způsoby registrace HoloLens zařízení:

 - **Prodejce může registrovat zařízení v Partnerské centrum při objednávce.**

   > [!NOTE]  
   > Toto je doporučená cesta pro přidání zařízení do služby Autopilot. [Přečtěte si další informace](/mem/autopilot/partner-registration).  

 - **Žádost o [podporu můžete odeslat přímo](hololens2-autopilot-registration-support.md) microsoftu.**
 - **Načtěte hodnotu hash hardwaru (označované** také jako ID hardwaru) a zaregistrujte zařízení ručně v Centru pro správu MEM.

#### <a name="obtain-hardware-hash"></a>Získání hodnoty hash hardwaru

Hodnotu hash hardwaru můžete načíst ze zařízení. Zařízení zaznamená hodnotu hash hardwaru do souboru CSV během procesu OOBE nebo později, když vlastník zařízení spustí proces shromažďování diagnostických protokolů (popsaný v následujícím postupu). Vlastníkem zařízení je obvykle první uživatel, který se k zařízení přihlásí.

> [!WARNING]
> Pokud jste v buildech před 20H2 prošli OOBE a telemetrie byla nastavená na Požadováno, nemůžete touto metodou shromáždit hodnotu hash hardwaru pro Autopilot. Pokud chcete shromažďovat hodnoty hash hardwaru touto metodou, nastavte možnost telemetrie prostřednictvím aplikace Nastavení App a vyberte  >  **Diagnostika ochrany osobních údajů.**

1. Spusťte zařízení HoloLens 2.

1. Na zařízení současně stiskněte  **tlačítka Napájení** a Snížení hlasitosti a pak je uvolněte. Zařízení shromažďuje diagnostické protokoly a hodnoty hash hardwaru a ukládá je do sady souborů .zip hardwaru.

1. Úplné podrobnosti a instrukční video o tom, jak to provést, najdete v tématu [Offline diagnostika.](hololens-diagnostic-logs.md#offline-diagnostics)

1. Pomocí kabelu USB-C připojte zařízení k počítači.

1. Na počítači otevřete Průzkumník souborů. Otevřete <b>Tento \\ počítač HoloLens</b>název zařízení Interní Storage <  > <b> \\ \\ Dokumenty</b>a vyhledejte AutopilotDiagnostics.zip počítače.  

   > [!NOTE]  
   > Soubor .zip nemusí být okamžitě dostupný. Pokud soubor ještě není připravený, může se ve složce Documents zobrazit soubor HoloLensDiagnostics.temp. Pokud chcete aktualizovat seznam souborů, aktualizujte okno.

1. Extrahujte obsah souboru AutopilotDiagnostics.zip.

1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru "DeviceHash". Zkopírujte tento soubor na jednotku v počítači, kde k němu máte přístup později.  

   > [!IMPORTANT]  
   > Data v souboru CSV by měla používat následující formát záhlaví a čáry:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrovat zařízení přes MEM

1. v [centru pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com)vyberte **zařízení**  >  **Windows**  >  **Windows registrace** a pak vyberte **zařízení**  >  **importovaná** v části **Windows Autopilot Deployment Program**.

1. v části **přidat Windows zařízení autopilotu** vyberte soubor CSV DeviceHash, vyberte **otevřít** a pak vyberte **importovat**.  

   > [!div class="mx-imgBorder"]
   > ![Pomocí příkazu Import importujte hodnotu hash hardwaru.](./images/hololens-ap-hash-import.png)

1. po dokončení importu vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **zařízení**  >  . Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zobrazit registrované zařízení, vyberte **aktualizovat**.  

   > [!div class="mx-imgBorder"]
   > ![K zobrazení seznamu zařízení použijte příkazy synchronizovat a aktualizovat.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Vytvoření skupiny zařízení

1. v [centru pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com)vyberte **skupiny**  >  **nová skupina**.

1. Jako **typ skupiny** vyberte **zabezpečení** a pak zadejte název a popis skupiny.

1. V případě **typu členství** vyberte buď **přiřazené** , nebo **dynamické zařízení**.

1. Proveďte některou z následujících akcí:  

   - Pokud jste v předchozím kroku vybrali **přiřazeno** k **typu členství** , vyberte **členy** a potom do skupiny přidejte zařízení autopilotu. Zařízení autopilot, která ještě nejsou zaregistrovaná, se zobrazí jako název zařízení pomocí sériového čísla zařízení.
   - Pokud jste v předchozím kroku vybrali možnost **Dynamická zařízení** pro **typ členství** , vyberte **dynamické členy zařízení** a pak zadejte kód v **rozšířeném pravidle** , které se podobá následujícímu:
     - Pokud chcete vytvořit skupinu, která bude obsahovat všechna vaše zařízení s vaším autopilotem, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Pole značky skupiny v Intune se mapuje na atribut **ČísloObjednávky** na zařízeních Azure AD. Pokud chcete vytvořit skupinu, která bude obsahovat všechna vaše zařízení autopilot, která mají specifickou značku skupiny (ČísloObjednávky pro zařízení Azure AD), musíte zadat: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Pokud chcete vytvořit skupinu, která zahrnuje všechna vaše zařízení autopilot, která mají konkrétní ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Tato pravidla cílí na atributy, které jsou jedinečné pro zařízení autopilot.
1. Vyberte **Uložit** a pak vyberte **vytvořit**.

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Vytvořte profil pro autopilot a přiřaďte ho ke skupině zařízení.

1. v [centru pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com)vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **Windows profily nasazení autopilotu**  >  **vytvořit profil**  >  **HoloLens**.
   ![rozevírací seznam vytvořit profil obsahuje položku HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Zadejte název a popis profilu a pak vyberte **Další**.  
   Měl by se zobrazit seznam, který obsahuje **HoloLens**. Pokud tato možnost není k dispozici, kontaktujte nás pomocí jedné z možností [zpětné vazby](hololens2-autopilot.md#feedback-and-support-for-autopilot) .

   > [!div class="mx-imgBorder"]
   > ![Přidejte název a popis profilu.](./images/hololens-ap-profile-name.png)

1. Na stránce spouštěné při **prvním spuštění počítače (OOBE)** je většina nastavení předem nakonfigurovaná, aby se pro toto vyhodnocení zjednodušilo počáteční nastavení. Volitelně můžete nakonfigurovat následující nastavení:  

   - **Jazyk (oblast)**: Vyberte jazyk pro OOBE. doporučujeme vybrat jazyk ze seznamu [podporovaných jazyků pro HoloLens 2](hololens2-language-support.md).
   - **Automaticky konfigurovat klávesnici**: aby se zajistilo, že klávesnice odpovídá vybranému jazyku, vyberte **Ano**.
   - **Použít šablonu názvu zařízení**: Pokud chcete automaticky nastavit název zařízení během spuštění OOBE, vyberte **Ano** a pak zadejte frázi šablony a zástupné symboly do pole **Zadejte název** , například zadejte předponu a `%RAND:4%` &mdash; zástupný text pro číslo se čtyřmi číslicemi.
     > [!NOTE]  
     > Pokud použijete šablonu názvu zařízení, proces OOBE znovu spustí zařízení jednou po použití názvu zařízení a před tím, než se připojí k zařízení do služby Azure AD. Tento restart umožní uplatnění nového názvu.  

   > [!div class="mx-imgBorder"]
   > ![Nakonfigurujte nastavení OOBE.](./images/hololens-ap-profile-oobe.png)

1. Po nakonfigurování nastavení vyberte **Další**.
1. Na stránce **značky oboru** můžete volitelně přidat značky oboru, které chcete použít pro tento profil. Další informace o značkách oboru najdete v tématu [použití značek řízení přístupu na základě role a rozsahu pro distribuci IT](/mem/intune/fundamentals/scope-tags.md). Po dokončení vyberte **Další**.
1. Na stránce **přiřazení** vyberte **vybrané skupiny** pro **přiřazení**.
1. V části **vybrané skupiny** vyberte **+ Vybrat skupiny, které chcete zahrnout**.
1. v seznamu **vybrat skupiny, které se mají zahrnout** vyberte skupinu zařízení, kterou jste vytvořili pro HoloLens zařízení autopilotu, a pak vyberte **další**.  
  
   Pokud chcete vyloučit jakékoli skupiny, vyberte **Vybrat skupiny, které se mají vyloučit**, a vyberte skupiny, které chcete vyloučit.

   > [!div class="mx-imgBorder"]
   > ![Přiřazení skupiny zařízení k profilu.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stránce **Revize + vytvořit** zkontrolujte nastavení a pak vyberte **vytvořit** a vytvořte profil.  

   > [!div class="mx-imgBorder"]
   > ![Zkontrolovat + vytvořit.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Vytvořte konfiguraci pro stav zápisu (ESP) a přiřaďte ji ke skupině zařízení.

Stránka stavu registrace (ESP) zobrazuje stav kompletního procesu konfigurace zařízení, který se spustí, když se uživatel spravovaný MDM do zařízení poprvé přihlásí. Ujistěte se, že se konfigurace protokolu ESP podobá následujícímu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP.](./images/hololens-ap-profile-settings.png)

Další informace o protokolu ESP najdete v tématu [nastavení stránky stavu registrace – Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. ověřte stav profilu HoloLens zařízení

1. v centru pro správu Microsoft Endpoint Manager vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **zařízení**.

1. ověřte, že jsou v seznamu uvedená zařízení HoloLens a že jsou jejich stav profilu **přiřazený**.  

   > [!NOTE]  
   > Přiřazení profilu k zařízení může trvat několik minut.  

   > [!div class="mx-imgBorder"]
   > ![Přiřazení zařízení a profilu.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows autopilot pro HoloLens 2 – uživatelské prostředí

po dokončení výše uvedených pokynů se uživatelům HoloLens 2 při zřizování svých HoloLensch zařízení projdou tyto možnosti:  

1. Prostředí autopilotu vyžaduje přístup k Internetu. K poskytnutí přístupu k Internetu použijte jednu z následujících možností:

    - Připojení zařízení do Wi-Fi sítě v OOBE a pak mu umožnit automatické rozpoznávání možností automatického pilotního nasazení. Toto je jediná doba, kterou budete potřebovat k interakci s OOBE, dokud se prostředí autopilotního projektu nedokončuje sami.

    - Připojení zařízení pomocí sítě ethernet s použitím adaptérů USB-C do sítě ethernet pro drátové připojení k internetu a nechte HoloLens 2 dokončit automatické pilotní prostředí.

    - Připojení zařízení pomocí adaptérů USB-C do Wi-Fi pro bezdrátové připojení k internetu a nechte HoloLens 2 dokončit automatické pilotní prostředí.

        > [!IMPORTANT]  
       > zařízení, která se pokoušejí použít Wi-Fi sítě v OOBE pro autopiloter, musí být v [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Pro zařízení, která používají adaptéry Ethernet, je nutné zařízení připojit k síti před spuštěním nástroje pro počáteční prostředí (OOBE). Zařízení určí, jestli se na první obrazovce OOBE zřídí jako zařízení s autopilotem. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete nezřídit zařízení jako zařízení autopilotu, nemůžete ho později změnit na autopilot. Místo toho byste museli spustit tento postup za účelem zřízení zařízení jako zařízení s autopilotem.

1. Zařízení by mělo automaticky spustit počáteční soubor. Nepoužívejte interakci s OOBE.

    > [!IMPORTANT]
    > Nepoužívejte prosím příkaz OOBE nebo stiskněte tlačítko napájení a převeďte systém do úsporného režimu nebo vypnutí, zatímco probíhá proces autopilotu. To může způsobit, že se tok autopilotního projektu nedokončil.

   umožněte HoloLens 2 detekci připojení k síti a umožněte automatickému dokončení souboru OOBE. Zařízení se může během POČÁTEČNÍho nastartu restartovat. Obrazovky OOBE by měly vypadat podobně jako následující.

   ![POČÁTEČNÍ krok 1. ](./images/autopilot-welcome.jpg)
    ![ POČÁTEČNÍ krok 2. ](./images/autopilot-step-complete.jpg)
    ![ POČÁTEČNÍ krok 3.](./images/autopilot-device-setup.jpg)

1. Na konci počátečního nastavení se můžete k zařízení přihlásit pomocí uživatelského jména a hesla.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Zprostředkovatel CSP pro tenanta a autopilot

HoloLens 2 zařízení podporují zprostředkovatele CSP pro Windows holografickou verzi 20H2. Tento zprostředkovatel CSP udržuje zařízení v tenantovi organizace tím, že je zamkne do tohoto tenanta i přes resetování nebo reflash zařízení.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby HoloLens 2 byly vázané jenom na registraci MDM jenom pomocí autopilotu. jakmile se uzel RequireNetworkInOOBE poskytovatele TenantLockdown CSP nastaví na hodnotu true nebo false (zpočátku nastavená) na HoloLens 2, tato hodnota zůstane na zařízení bez ohledu na to, jak se provádí bliknutí, aktualizace operačního systému atd.

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

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení nastavení TenantLockdown RequireNetworkInOOBE HoloLens 2?

1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše.

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení.

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený v HoloLens po nastavení tenantaLockdown na hodnotu true?

OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown.

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Proč se mi prostředí Autopilotu nez zobrazení, přestože je profil Autopilotu přiřazený v Intune?

Ve výchozím nastavení HoloLens 2 po zjištění internetu počká 15 sekund na rozpoznání Autopilotu. Pokud se během 15 sekund nezjme žádný profil Autopilotu, znamená to, že autopilot se nezjme správně a zobrazí se stránka s eula.

Restartujte zařízení a zkuste to znovu. Další informace najdete v tématu [Známé problémy a omezení nebo](hololens2-autopilot.md#known-issues-and-limitations) Řešení [potíží.](hololens2-autopilot.md#troubleshooting)

## <a name="known-issues-and-limitations"></a>Známé problémy a omezení

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Proč se během 0x80180014 zobrazí?

Jedná se o chybu zobrazenou během procesu Autopilot na zařízení. Tento problém se zobrazí pouze v případě HoloLens zařízení provedlo následující:

1. Už jsme aspoň jednou prošli Autopilotem.
1. Právě se resetuje a znovu používá pro Autopilot.

Prostředí Autopilotu selže s konkrétní chybou.

![HoloLens Kód chyby selhání Autopilotu](images/autopilot-0x80180014-failure.jpg)

Jaké kroky je potřeba provést k vyřešení této chyby?

1. Při odebírání zařízení z Intune postupujte podle kroků v tématu Řešení potíží s importem a registrací zařízení [Autopilot.](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode)
1. [Resetovat nebo odkazovat HoloLens](hololens-recovery.md) zařízení a pak se pokuste o Autopilot.

### <a name="troubleshooting"></a>Řešení potíží

Následující články mohou být užitečným zdrojem dalších informací a řešení potíží s Autopilotem, ale tyto články jsou založené na Windows 10 Desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [Řešení Windows registrace zařízení v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Konflikty zásad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro Autopilot

Pokud chcete poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pokud chcete podporu k registraci zařízení, obraťte se na prodejce nebo distributora.
- Pokud chcete obecné dotazy ohledně podpory Windows Autopilot nebo problémy, jako jsou přiřazení profilů, vytvoření skupin nebo ovládací prvky portálu MEM, obraťte se [Microsoft Endpoint Manager podpory.](/mem/get-support)  
- Pokud je vaše zařízení zaregistrované ve službě Autopilot a profil je přiřazený na portálu MEM, kontaktujte HoloLens [podpory](/hololens/) (viz karta Podpora). Otevřete lístek podpory, a pokud je to k dispozici, zahrřte snímky obrazovky a protokoly tím, že zachytáte [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnostické protokoly během spuštění zařízení.
- Pokud chcete nahlásit problém ze zařízení, použijte aplikaci Centrum Feedback ve vaší HoloLens. V Centrum Feedback vyberte **kategorii Enterprise Zařízení**  >  **pro správu.**
- Pokud chcete poskytnout obecnou zpětnou vazbu k Autopilotu pro HoloLens, můžete odeslat tento [průzkum.](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Možná už nebudete chtít používat zařízení pro Autopilot nebo registrovat zařízení do jiného tenanta. Pokud to chcete udělat, přečtěte si, [jak odstranit zařízení Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)
