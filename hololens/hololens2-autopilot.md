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
ms.openlocfilehash: 28793b385bad58d44c6592a800c4f56b18d152ce
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833569"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

## <a name="overview"></a>Přehled

pro nasazení ve velkém měřítku doporučujeme začít s Windowsm autopilotem. považuje se za "malé dotykové ovládání" v tom, že výrazně zjednodušuje nastavení HoloLens pro koncové uživatele. 

na vysoké úrovni správce IT obvykle vytvoří konfigurace připravené pro firmy a registruje HoloLens 2 zařízení na portálech MDM. když se HoloLens 2 zařízení spouští s předčasným prostředím (OOBE) a připojí se k internetu, budou se automaticky stahovat a používat konfigurace pro registrované HoloLens 2 zařízení, aby se zajistila příprava zařízení bez zásahu uživatele.

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
   > Toto je doporučená cesta pro přidávání zařízení do služby autopilotu. [Přečtěte si další informace](/mem/autopilot/partner-registration).  

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
    
1. Extrahujte obsah AutopilotDiagnostics.zip souboru.

1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru DeviceHash. Zkopírujte tento soubor na jednotku v počítači, kde k ní budete později mít přístup.  

   > [!IMPORTANT]  
   > Data v souboru CSV by měla používat následující hlavičku a formát řádku:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrace zařízení prostřednictvím MEM

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení Windows Windows registrace a pak v části  >    >  Windows Autopilot Deployment   >   Program vyberte **Import zařízení.**

1. V **části Windows zařízení Autopilot** vyberte soubor CSV DeviceHash, vyberte **Otevřít** a pak vyberte **Importovat.**  

   > [!div class="mx-imgBorder"]
   > ![K importu hodnoty hash hardwaru použijte příkaz Import.](./images/hololens-ap-hash-import.png)

1. Po dokončení importu vyberte Zařízení **Windows**  >    >  **Windows zařízení**  >    >  **Synchronizovat.** Dokončení tohoto procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zaregistrované zařízení zobrazit, vyberte **Aktualizovat.**  

   > [!div class="mx-imgBorder"]
   > ![Seznam zařízení zobrazíte pomocí příkazů Synchronizovat a Aktualizovat.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Vytvoření skupiny zařízení

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Skupiny **Nová**  >  **skupina.**

1. Jako **Typ skupiny** vyberte **Zabezpečení** a pak zadejte název a popis skupiny.

1. Jako **Typ členství** vyberte Přiřazené **nebo** **Dynamické zařízení.**

1. Proveďte některou z následujících akcí:  

   - Pokud jste v **předchozím kroku** jako Typ **členství** vybrali Přiřazeno, vyberte **Členové** a pak do skupiny přidejte zařízení Autopilot. Zařízení Autopilot, která ještě nejsou zaregistrovaná, jsou uvedena pomocí sériového čísla zařízení jako názvu zařízení.
   - Pokud jste **v**  předchozím kroku jako Typ členství vybrali Dynamická zařízení, vyberte Dynamické členy zařízení a pak do pole **Pokročilé** pravidlo zadejte kód, který bude vypadat podobně jako v následujícím příkladu:
     - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Pole značky skupiny Intune se mapuje na **atribut OrderID** na zařízeních Azure AD. Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot, která mají konkrétní značku skupiny (OrderID zařízení Azure AD), musíte zadat: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot, která mají konkrétní ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Tato pravidla cílí na atributy, které jsou jedinečné pro zařízení Autopilot.
1. Vyberte **Uložit** a pak vyberte **Vytvořit.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Vytvoření profilu Autopilot a jeho přiřazení ke skupině zařízení

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení   >  **Windows** Windows  >  **a** Windows nasazení  >  **Autopilotu** Vytvořte  >  **profil**  >  **HoloLens**.
   ![Rozevírací seznam Vytvořit profil obsahuje HoloLens položky.](./images/hololens-ap-enrollment-profiles.png)

1. Zadejte název a popis profilu a pak vyberte **Další.**  
   Měl by se zobrazit seznam, který obsahuje **HoloLens**. Pokud tato možnost není k dispozici, kontaktujte nás pomocí jedné z možností [zpětné](hololens2-autopilot.md#feedback-and-support-for-autopilot) vazby.

   > [!div class="mx-imgBorder"]
   > ![Přidejte název a popis profilu.](./images/hololens-ap-profile-name.png)

1. Většina **nastavení je předem** nakonfigurovaná tak, aby se pro toto vyhodnocení zjednodušil přístupový proces. Volitelně můžete nakonfigurovat následující nastavení:  

   - **Jazyk (oblast):** Vyberte jazyk pro OOBE. Doporučujeme vybrat jazyk ze seznamu podporovaných jazyků pro HoloLens [2.](hololens2-language-support.md)
   - **Automaticky nakonfigurovat klávesnici:** Pokud chcete zajistit, aby klávesnice odpovídala vybranému jazyku, vyberte **Ano.**
   - Použít **šablonu** názvu zařízení: Pokud chcete automaticky nastavit  název zařízení při spuštění počítače, vyberte Ano a potom zadejte frázi šablony **a** zástupné symboly do pole Zadejte název. Zadejte například předponu a zástupný symbol pro čtyřciferné `%RAND:4%` &mdash; náhodné číslo.
     > [!NOTE]  
     > Pokud použijete šablonu názvu zařízení, proces OOBE restartuje zařízení jednou po použití názvu zařízení a před jeho připojením ke službě Azure AD. Toto restartování umožňuje, aby se nový název projeví.  

   > [!div class="mx-imgBorder"]
   > ![Nakonfigurujte nastavení OOBE.](./images/hololens-ap-profile-oobe.png)

1. Po konfiguraci nastavení vyberte **Další.**
1. Na stránce **Značky** oboru můžete volitelně přidat značky oboru, které chcete pro tento profil použít. Další informace o značkách oboru najdete v tématu Použití řízení přístupu na základě role a značek [oboru pro distribuované IT](/mem/intune/fundamentals/scope-tags.md). Po dokončení vyberte **Další.**
1. Na stránce **Přiřazení v** části Přiřadit **k** vyberte **Vybrané skupiny.**
1. V **části VYBRANÉ SKUPINY** vyberte + Vybrat **skupiny, které se zahrnou.**
1. V seznamu **Vybrat skupiny** k zahrnutí vyberte skupinu zařízení, kterou jste vytvořili pro zařízení Autopilot HoloLens, a pak vyberte **Další.**  
  
   Pokud chcete některé skupiny vyloučit, vyberte **Vybrat skupiny, které** chcete vyloučit, a vyberte skupiny, které chcete vyloučit.

   > [!div class="mx-imgBorder"]
   > ![Přiřazení skupiny zařízení k profilu](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stránce **Zkontrolovat a vytvořit** zkontrolujte nastavení a pak výběrem možnosti **Vytvořit** vytvořte profil.  

   > [!div class="mx-imgBorder"]
   > ![Zkontrolujte a vytvořte.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Vytvoření konfigurace stránky stavu registrace (ESP) a jeho přiřazení ke skupině zařízení

Stránka stavu registrace (ESP) zobrazuje stav úplného procesu konfigurace zařízení, který se spustí, když se uživatel spravovaný pomocí MDM poprvé přihlásí k zařízení. Ujistěte se, že vaše konfigurace ESP vypadá podobně jako v následujícím příkladu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP.](./images/hololens-ap-profile-settings.png)

Další informace o ESP najdete v tématu [Nastavení stránky stavu registrace – Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Ověření stavu profilu zařízení HoloLens zařízení

1. V Microsoft Endpoint Manager Admin Center vyberte Zařízení **Windows**  >    >  **Windows registraci**  >  **zařízení.**

1. Ověřte, že HoloLens uvedená zařízení a že jejich profil je ve stavu **Přiřazeno.**  

   > [!NOTE]  
   > Přiřazení profilu k zařízení může několik minut trvat.  

   > [!div class="mx-imgBorder"]
   > ![Přiřazení zařízení a profilu.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot pro HoloLens 2 uživatelské prostředí

Po dokončení výše uvedených pokynů vaši HoloLens 2 uživatelé zřžou svá zařízení HoloLens prostředí:  

1. Prostředí Autopilotu vyžaduje přístup k internetu. K zajištění přístupu k internetu použijte jednu z následujících možností:

    - Připojení zařízení do Wi-Fi v prostředí OOBE a nechat ho automaticky detekovat prostředí Autopilotu. Je to jediný čas, kdy budete potřebovat pracovat s OOBE, dokud se prostředí Autopilot samo nedokoní. Ve výchozím HoloLens 2 po zjištění internetu počká 10 sekund na rozpoznání Autopilotu. Pokud během 10 sekund není detekován žádný profil Autopilot, zobrazí se při jeho aktivaci eula. Pokud narazíte na tento scénář, restartujte zařízení, aby bylo možné udělat další pokus o rozpoznání Autopilotu. Upozorňujeme také, že funkce při neověřené aktivaci může čekat na Autopilot po neomezenou dobu pouze v případě, že je na zařízení nastavená zásada TenantLockdown.

    - Připojení připojit zařízení k síti Ethernet pomocí adaptérů USB-C na Ethernet pro připojení k drátovému internetu a nechat HoloLens 2 dokončit prostředí Autopilotu automaticky.

    - Připojení bezdrátového připojení k internetu připojte k zařízení adaptéry USB-C na Wi-Fi a nechte HoloLens 2 dokončit prostředí Autopilotu.

        > [!IMPORTANT]  
       > Zařízení, která se Wi-Fi síti v OOBE pro Autopilot, musí být na [Windows Holographic verze 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > U zařízení, která používají ethernetové adaptéry, musíte zařízení připojit k síti před tím, než se spustí prostředí při spuštění počítače. Zařízení určuje, jestli se na první obrazovce OOBE zřizuje jako zařízení Autopilot. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete zařízení zřídit jako zařízení Autopilot, nemůžete ho později změnit na Zřizování Autopilotu. Místo toho byste muset tento postup spustit znovu, abyste mohli zařízení zřídit jako zařízení Autopilot.

1. Zařízení by mělo automaticky spustit OOBE. Nereagovat na OOBE.

    > [!IMPORTANT]
    > Pokud chcete systém přenést do pohotovostního režimu nebo vypnutí, neaktivuje se prosím software při provozu ani nestiskne tlačítko napájení, zatímco probíhá Režim autopilotu. To může způsobit, že se tok Autopilotu dokončí.

   Nechte HoloLens 2, aby detekovat síťové připojení a umožnilo automatické dokončení prostředí OOBE. Zařízení se může restartovat během spuštění počítače. Obrazovky OOBE by měly vypadat podobně jako na následujícím příkladu.

   ![OOBE krok 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE krok 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE krok 3.](./images/autopilot-device-setup.jpg)

1. Na konci OOBE se k zařízení můžete přihlásit pomocí svého uživatelského jména a hesla.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Uzamčení tenanta CSP a Autopilot

HoloLens 2 podporují TenantLockdown CSP od verze Windows Holographic verze 20H2. Tento CSP udržuje zařízení v tenantovi organizace tím, že je uzamyká pro tohoto tenanta, a to i přes resetování zařízení nebo koliázku.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, HoloLens 2 k registraci MDM pouze pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (počáteční nastavení) na HoloLens 2, zůstane tato hodnota na zařízení bez ohledu na kolísání, aktualizace operačního systému atd.

Po nastavení uzlu RequireNetworkInOOBE na tenantoviLockdown CSP na HoloLens 2 počká OOBE po připojení k síti po neomezenou dobu na úspěšné stažení a použití profilu Autopilot.

Po nastavení uzlu RequireNetworkInOOBE u tenantaLockdown CSP na úrovni HoloLens 2 jsou v OOBE zakázané následující operace:

- Vytvoření místního uživatele pomocí zřizování modulu runtime 
- Provádění operace připojení k Azure AD prostřednictvím zřizování modulu runtime 
- Výběr vlastníka zařízení v prostředí pro OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak to nastavit pomocí Intune? 
1. Vytvořte vlastní konfigurační profil zařízení OMA URI a jako uzel RequireNetworkInOOBE zadejte true, jak je znázorněno níže.
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

## <a name="known-issues--limitations"></a>Známé problémy & omezení

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