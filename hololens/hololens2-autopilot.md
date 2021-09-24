---
title: Windows Autopilot pro HoloLens 2
description: naučte se, jak nastavit, nakonfigurovat a řešit potíže s autopilotem na zařízeních HoloLens 2.
author: qianw211
ms.author: v-qianwen
ms.date: 9/8/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: sekerawa
ms.openlocfilehash: 10dc251bbeb204a6621ca0891029858c00c467bc
ms.sourcegitcommit: d09556a101663ef5dfff865d4753e64a41032b78
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/23/2021
ms.locfileid: "128346770"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

## <a name="overview"></a>Přehled

pro nasazení ve velkém měřítku doporučujeme začít s Windowsm autopilotem. považuje se za "malé dotykové ovládání" v tom, že výrazně zjednodušuje nastavení HoloLens pro koncové uživatele. 

na vysoké úrovni správce IT obvykle vytvoří konfigurace připravené pro firmy a registruje HoloLens 2 zařízení na portálech MDM. když se HoloLens 2 zařízení spouští s předčasným prostředím (OOBE) a připojí se k internetu, budou se automaticky stahovat a používat konfigurace pro zaregistrované HoloLens 2 zařízení, aby se zajistila příprava zařízení bez zásahu uživatele.

další informace najdete v tématu [přehled Windowsho autopilotu | Microsoft Docs](/mem/autopilot/windows-autopilot) článek.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>podporovaný scénář autopilotu na HoloLens 2

> [!NOTE]
> konfigurace autopilotu pro HoloLens v Microsoft Endpoint Manager provádí přechod z **Public Preview** na **obecnou dostupnost**. Všichni klienti budou moci nastavit program Autopilot v centru pro správu nástroje MEM.

počínaje Windows holografickou verzí 2004 HoloLens 2 podporuje Windows [režimu automatického nasazení](/mem/autopilot/self-deploying) autopilotu s Microsoft Intune (MDMs třetích stran se nepodporuje). Tato konfigurace snižuje režijní náklady na správu inventáře, náklady na praktická zařízení pro přípravu a podporu hovorů od zaměstnanců během prostředí nastavení. další informace najdete v dokumentaci k [Windows autopilotu](/mem/autopilot/windows-autopilot) .

podobně jako u zařízení surface je vhodné, aby zákazníci spolupracovali se společností Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejci nebo distributor) a mohli zařízení zaregistrovaná ve službě autopilotu prostřednictvím partnerského centra.

Když uživatel spustí proces automatického nasazení autopilotu, provede autopilotní následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD). autopilot pro HoloLens nepodporuje připojení ke službě Active Directory ani hybridní službu Azure AD join.

1. pomocí služby Azure AD zaregistrujete zařízení v Microsoft Endpoint Manager (nebo jiné službě MDM).

1. Stáhněte a použijte zásady zaměřené na zařízení, certifikáty, síťové profily a aplikace.

1. Prezentovat přihlašovací obrazovku uživateli

## <a name="configuring-autopilot-for-hololens-2"></a>konfigurace autopilotu pro HoloLens 2

Pro nastavení prostředí postupujte podle následujících kroků:

1. [přečtěte si požadavky na Windows autopilot pro HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Povolit automatickou registraci MDM](#2-enable-automatic-mdm-enrollment)

1. (Jenom pro Intune) [ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [registrujte zařízení v Windows autopilotu.](#4-register-devices-in-windows-autopilot)

1. [Vytvořte skupinu zařízení.](#5-create-a-device-group)

1. [Vytvořte profil autopilotu a přiřaďte ho ke skupině zařízení.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Vytvořte konfiguraci na stavové stránce zápisu (ESP) a přiřaďte ji ke skupině zařízení.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [ověřte stav profilu zařízení HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. projděte si požadavky na Windows autopilot pro HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>přečtěte si následující oddíly článku Windows požadavky na autopilot:

- [Požadavky sítě](/mem/autopilot/networking-requirements)  
- [Licenční požadavky](/mem/autopilot/licensing-requirements)  
- [Požadavky na konfiguraci](/mem/autopilot/configuration-requirements)

**přečtěte si část [požadavky](/windows/deployment/windows-autopilot/self-deploying#requirements)v článku Windows Self-Deploying režimu autopilotu.** vaše prostředí musí splňovat tyto požadavky a standardní Windows požadavky na autopilot. Nemusíte si projít části "krok za krokem" a "ověření" v článku. Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Ujistěte se, že zařízení ještě nejsou členem služby Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení autopilotu dokončí tyto kroky. Pokud chcete zajistit, aby se všechny informace týkající se zařízení vyčistily, zkontrolujte stránky **zařízení** v portálech Azure AD a Intune. funkce převedení všech cílových zařízení na autopilots se v HoloLens v tuto chvíli nepodporuje. 

#### <a name="review-hololens-os-requirements"></a>kontrola HoloLens požadavků na operační systém:

Pokud chcete ověřit verzi buildu na vašem zařízení nebo se znovu dosvítit k nejnovějšímu operačnímu systému, použijte [Průvodce rozšířeným obnovením (oblouk)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) a pokyny pro opětovné použití [zařízení](hololens-recovery.md). zařízení dodávaná do zpožděného dne 2020 mají předinstalované Windows holografické verze 1903. Obraťte se na svého prodejce a ujistěte se, že vám budou zasílána zařízení pro autopiloting, která jsou připravena k vám.

 Minimální verzi operačního systému | Podporovaná funkce | Poznámky 
 ------ | ------ | ------  
 [Windows holografická verze 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041,1103) nebo novější | 1. scénář automatického nasazení autopilotu na HoloLens 2. | Stažení profilu autopilotu se podporuje jenom přes síť Ethernet. **před zapnutím** adaptéru zajistěte, aby byla HoloLens připojená k síti ethernet pomocí adaptéru USB-C do sítě ethernet.  pokud plánujete zavedení autopilotního nasazení na mnoho HoloLensch zařízení, doporučujeme, abyste si vyplánovali infrastrukturu adaptéru. Nedoporučujeme používat rozbočovače USB, protože často vyžadují instalaci ovladačů třetích stran, což není v HoloLens podporováno.
 [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041,1128) nebo novější | 1. stahuje se profil pro autopiloting přes Wi-Fi. <br> 2. [zprostředkovatel CSP pro klienty a autopilot](#tenant-lockdown-csp-and-autopilot) pro zamčení zařízení se zadaným klientem autopilotu. | V případě potřeby můžete i nadále používat adaptéry sítě Ethernet. Pro zařízení připojená přes Wi-Fi musí uživatel: <ul> <li> Projděte si scénu Hummingbird. </li> <li> Vyberte jazyk a národní prostředí. </li> <li> Spusťte kalibraci očí. </li> <li> Připojení k požadované síti Wi-Fi se úspěšně provedlo. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. povolení automatického zápisu MDM:

Aby mohl Automatický pilot úspěšně probíhat, budete muset v Azure Portal povolit automatickou registraci MDM. Tím umožníte, aby se zařízení zaregistrovalo bez uživatele.

Přečtěte si následující krátký návod, jak [Povolit automatickou registraci MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) , nebo [Úvodní příručku pro automatické registrace](/mem/intune/enrollment/quickstart-setup-auto-enrollment) , kde najdete ještě další informace o nastavení.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.

aby mohl automatický pilotní postup úspěšně proběhnout, musíte zajistit, aby se zařízení HoloLens mohla zaregistrovat. vzhledem k tomu, že se HoloLens považuje za Windows zařízení, bude nutné provést žádná omezení registrace, která by mohla blokovat vaše nasazení. [Projděte si tento seznam omezení](/mem/intune/enrollment/enrollment-restrictions-set) a ujistěte se, že budete moci zaregistrovat svá zařízení.

### <a name="4-register-devices-in-windows-autopilot"></a>4. registrace zařízení v Windows autopilotování

vaše zařízení musí být zaregistrovaná v Windows autopilotu před prvním nastavením. 

existují tři základní způsoby, jak zaregistrovat HoloLens zařízení:

 - **Prodejce může zaregistrovat zařízení v partnerském centru, když umístíte objednávku.**

   > [!NOTE]  
   > Toto je doporučená cesta pro přidávání zařízení do služby autopilotu. [Další informace](/mem/autopilot/partner-registration).  

 - **Žádost o [podporu můžete odeslat](hololens2-autopilot-registration-support.md) přímo společnosti Microsoft.**
 - **Načtěte hodnotu hash hardwaru (označuje se také jako ID hardwaru) a zaregistrujte zařízení ručně v centru pro správu nástroje mem**.

#### <a name="obtain-hardware-hash"></a>Získat hodnotu hash hardwaru

Hodnotu hash hardwaru můžete ze zařízení načíst. Zařízení zaznamenává jeho hodnotu hash hardwaru do souboru CSV během procesu OOBE nebo později, pokud vlastník zařízení spustí proces shromažďování protokolů diagnostiky (popsaný v následujícím postupu). Většinou je vlastníkem zařízení první uživatel, který se k zařízení přihlašuje.

> [!WARNING]
> Pokud jste v sestaveních před 20H2 prošli pomocí OOBE a telemetrie byla nastavena na hodnotu požadováno, nemůžete pomocí této metody shromáždit hodnotu hash hardwaru pro autopilot. aby bylo možné shromáždit hodnotu hash hardwaru přes tuto metodu, nastavte možnost telemetrie na úplnou prostřednictvím aplikace Nastavení a vyberte možnost **diagnostika osobních údajů**  >  .

1. spusťte zařízení HoloLens 2.

1. Na zařízení stiskněte tlačítko **napájení** a **rozhlasitost dolů** a pak je uvolněte. Zařízení shromažďuje diagnostické protokoly a hodnotu hash hardwaru a ukládá je do sady .zip souborů.

1. Úplné podrobnosti a pokyny, jak tento postup provést, najdete v tématu věnovaném [offline diagnostice](hololens-diagnostic-logs.md#offline-diagnostics).

1. Připojte zařízení k počítači pomocí kabelu USB-C.

1. V počítači otevřete Průzkumníka souborů. otevřete <b>tento počítač \\</b> < *HoloLens* > <b> \\ interních \\ dokumentů Storage</b>jména zařízení a vyhledejte soubor AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Soubor .zip možná není hned dostupný. Pokud soubor ještě není připravený, může se ve složce dokumenty zobrazit soubor HoloLensDiagnostics. Temp. Chcete-li aktualizovat seznam souborů, aktualizujte okno.
    
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

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>jak zrušit nastavení RequireNetworkInOOBE TenantLockdown na HoloLens 2 pomocí intune?

1. odeberte HoloLens 2 ze skupiny zařízení, ve které byla výše vytvořená konfigurace zařízení dříve přiřazena.

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru OMA URI a zadejte hodnotu false pro RequireNetworkInOOBE, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím identifikátoru URI OMA v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky TenantLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>co se stane při počátečním spuštění, pokud je profil autopilotu nepřiřazený u HoloLens po nastavení TenantLockdown na hodnotu true? 
Při POČÁTEČNÍm navýšení bude profil pro autopilot čekat na neomezenou dobu stahování a zobrazí se dialogové okno. Aby se odstranily účinky TenantLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí jenom autopilotu a RequireNetworkInOOBE musí být nastavené tak, jak je popsané v předchozím kroku, než se odeberou omezení zavedená poskytovatelem CSP pro TenantLockdown.

![Zobrazení v zařízení pro dobu, kdy se na zařízení vynutila zásada.](images/hololens-autopilot-lockdown.png)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Proč se mi nezobrazilo prostředí pro autopilotování, i když se profil autopilotu přiřadí v Intune?

ve výchozím nastavení HoloLens 2 čeká 15 sekund na detekci automatického pilotního projektu po zjištění internetu. Pokud se během 15 sekund nezjistí žádný profil autopilotu, znamená to, že nebyl správně zjištěn autopilot a zobrazí se stránka EULA.

Restartujte zařízení a zkuste to znovu. Další informace najdete v tématu [známé problémy a omezení](hololens2-autopilot.md#known-issues-and-limitations) nebo [řešení potíží](hololens2-autopilot.md#troubleshooting).

## <a name="known-issues-and-limitations"></a>Známé problémy a omezení

- Zkoumáme problém, kdy se instalace aplikace na základě kontextu zařízení nakonfigurovaná v programu MEM nevztahuje na HoloLens. [Přečtěte si další informace o kontextu zařízení a o instalaci kontextu uživatele.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Při nastavování autopilotu přes Wi-Fi může nastat instance, ve které se profil autopilotu nestáhne při prvním navázání připojení k Internetu. V tomto případě se zobrazí licenční smlouva s koncovým uživatelem (EULA) a uživatel má možnost pokračovat v instalaci bez automatického pilotního nasazení. Pokud se chcete znovu pokusit o nastavení pomocí modulu autopilot, vložte zařízení do režimu spánku a pak ho restartujte, nebo zařízení restartujte a nechte to znovu.

### <a name="troubleshooting"></a>Řešení potíží

následující články můžou být užitečným prostředkem, který vám umožní zjistit další informace a řešit problémy s autopilotem, ale tyto články jsou založené na Windows 10 desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [řešení potíží s registrací zařízení Windows v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – konflikty zásad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro autopilot

Chcete-li poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pro podporu registrace zařízení se obraťte na prodejce nebo distributora.
- u obecných dotazů na podporu týkající se Windows autopilotu nebo pro problémy, jako jsou přiřazení profilů, vytváření skupin nebo ovládací prvky pro pracovní portál, [kontaktujte Microsoft Endpoint Manager podporu](/mem/get-support) .  
- pokud je zařízení zaregistrované do služby autopilot a profil se přiřadí na portále MEM, kontaktujte [podporu](/hololens/) HoloLens (viz karta podpora). Otevřete lístek podpory a pokud je to možné, zahrňte snímky obrazovky a protokoly zachytáváním [offline diagnostických protokolů](hololens-diagnostic-logs.md#offline-diagnostics) během nastavování mimo prostředí (OOBE).
- Pokud chcete ohlásit problém ze zařízení, použijte aplikaci centra Feedback na vašem HoloLens. v centru pro zpětnou vazbu vyberte kategorii zařízení **pro správu Enterprise**  >   .
- pokud chcete získat obecnou zpětnou vazbu k autopilotu pro HoloLens, můžete odeslat tento [průzkum](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) .

## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Možná budete chtít, aby zařízení už nepoužívalo k autopilotu, nebo aby se vaše zařízení zaregistrovala v jiném tenantovi. Pokud to chcete provést, přečtěte si, [Jak odstranit zařízení autopilotu.](/mem/autopilot/add-devices#delete-autopilot-devices)
