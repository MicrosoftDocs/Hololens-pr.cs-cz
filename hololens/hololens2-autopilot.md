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
ms.openlocfilehash: 05eb629e05395f04ddb8723d58d41db4161896fa
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964577"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

## <a name="overview"></a>Přehled

Pokud chcete nasazení provést ve velkém měřítku, doporučujeme začít s Windows Autopilotem. Považuje se za "malý dotek" v tom, že výrazně zjednodušuje nastavení HoloLens pro IT i koncové uživatele. 

Na nejvyšší úrovni správce IT obvykle vytvoří konfigurace připravené pro firmy a zaregistruje zařízení HoloLens 2 na portálech MDM. Když se HoloLens 2 zařízení spustí s prostředím při spuštění a připojí se k internetu, konfigurace připravené pro firmy pro registrované zařízení HoloLens 2 se automaticky stáhnou a použijí, aby byla zařízení připravená pro firmy bez zásahu uživatele.

Další informace najdete v tématu [Přehled Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot) článku.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Podporovaný scénář Autopilotu na HoloLens 2

> [!NOTE]
> Konfigurace Autopilotu pro HoloLens v Microsoft Endpoint Manager přechází z **Public Preview** **na všeobecnou dostupnost.** Autopilot budou moct nastavit všichni tenanti v Centru pro správu MEM.

Počínaje Windows Holographic verze 2004 podporuje HoloLens 2 režim automatického nasazení Windows [Autopilotu](/mem/autopilot/self-deploying) s Microsoft Intune (mdm třetích stran se nepodporují). Tato konfigurace snižuje režijní náklady na správu inventáře, náklady na přípravu zařízení a volání na podporu od zaměstnanců během nastavování. Další informace najdete v [Windows Autopilot.](/mem/autopilot/windows-autopilot)

Stejně jako u zařízení Surface se doporučuje, aby zákazníci pracovali se svým partnerem Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejcem nebo distributorem), aby prostřednictvím služby Autopilot zaregistrovali Partnerské centrum.

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

**V článku [o režimu](/windows/deployment/windows-autopilot/self-deploying#requirements)Windows Autopilot si Self-Deploying požadavky.** Vaše prostředí musí splňovat tyto požadavky a standardní požadavky Windows Autopilot. V tomto článku si není muset prohlédněte oddíly Krok za krokem a Ověření. Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Ujistěte se, že zařízení ještě nejsou členy Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení Autopilotu dokončí tyto kroky. Pokud se chcete ujistit, že jsou všechny  informace související se zařízením vyčištěné, podívejte se na stránky Zařízení na portálech Azure AD i Intune. Funkce Převést všechna cílová zařízení na Autopilot se v HoloLens nepodporuje.

#### <a name="review-hololens-os-requirements"></a>Projděte HoloLens na operační systém:

Pokud chcete ověřit verzi buildu na vašem zařízení nebo odkazovat na nejnovější verzi operačního systému, použijte [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) a naše pokyny k [odkazování na zařízení.](hololens-recovery.md) Na zařízeních doručovaných do konce září 2020 Windows předem nainstalovaná verze Holographic 1903. Obraťte se na prodejce a ujistěte se, že vám budou dodána zařízení připravená pro Autopilot.

 Minimální verzi operačního systému | Podporovaná funkce | Poznámky
 ------ | ------ | ------  
 [Windows Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) nebo novější | 1. Scénář automatického nasazení Autopilotu na HoloLens 2. | Stahování profilu Autopilot se podporuje pouze přes Ethernet. Než ho HoloLens, ujistěte se, že je připojený k síti ethernet pomocí adaptéru USB-C na **Ethernet.**  Pokud plánujete nasavit Autopilot do mnoha HoloLens zařízení, doporučujeme naplánovat infrastrukturu adaptéru. Rozbočovače USB nedoporučujeme, protože často vyžadují instalaci ovladačů třetích stran, které nejsou podporované v HoloLens.
 [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) nebo novější | 1. Stahování profilu Autopilot přes Wi-Fi <br> 2. [Uzamčení tenanta CSP](#tenant-lockdown-csp-and-autopilot) a Autopilot k uzamčení zařízení pomocí tenanta určeného autopilotem. | V případě potřeby můžete stále používat ethernetové adaptéry. U zařízení připojených přes Wi-Fi musí uživatel jenom: <ul> <li> Projdete scénu s vousy. </li> <li> Zvolte jazyk a národní prostředí. </li> <li> Spustit z pohledu zraku. </li> <li> Úspěšně se připojte k požadované síti Wi-Fi. </li> </ul>

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

1. Extrahujte obsah AutopilotDiagnostics.zip souboru.

1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru DeviceHash. Zkopírujte tento soubor na jednotku v počítači, kde k ní budete později mít přístup.  

   > [!IMPORTANT]  
   > Data v souboru CSV by měla používat následující hlavičku a formát řádku:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrace zařízení prostřednictvím MEM

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení Windows Windows registrace a pak v části Windows Autopilot Deployment Program vyberte  >    >     >   **Import zařízení.**

1. V **části Windows zařízení Autopilot** vyberte soubor CSV DeviceHash, vyberte **Otevřít** a pak vyberte **Importovat.**  

   > [!div class="mx-imgBorder"]
   > ![K importu hodnoty hash hardwaru použijte příkaz Import.](./images/hololens-ap-hash-import.png)

1. Po dokončení importu vyberte Zařízení **Windows**  >    >  **Windows**  >  **zařízení**  >  **Synchronizovat.** Dokončení tohoto procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zaregistrované zařízení zobrazit, vyberte **Aktualizovat.**  

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

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení **Windows** Windows registraci  >    >  **Windows** nasazení  >  **Autopilotu** Vytvořit  >  **profil**  >  **HoloLens**.
   ![Rozevírací seznam Vytvořit profil obsahuje HoloLens položky.](./images/hololens-ap-enrollment-profiles.png)

1. Zadejte název a popis profilu a pak vyberte **Další.**  
   Měl by se zobrazit seznam, který **obsahuje HoloLens**. Pokud tato možnost není k dispozici, kontaktujte nás pomocí jedné z možností [zpětné](hololens2-autopilot.md#feedback-and-support-for-autopilot) vazby.

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
1. Na **stránce Přiřazení v** části Přiřadit **k vyberte** **Vybrané skupiny.**
1. V **části VYBRANÉ SKUPINY** vyberte + Vybrat **skupiny, které se zahrnou.**
1. V seznamu **Vybrat skupiny** k zahrnutí vyberte skupinu zařízení, kterou jste vytvořili pro zařízení Autopilot HoloLens a pak vyberte **Další.**  
  
   Pokud chcete některé skupiny vyloučit, vyberte **Vybrat skupiny, které** chcete vyloučit, a vyberte skupiny, které chcete vyloučit.

   > [!div class="mx-imgBorder"]
   > ![Přiřazení skupiny zařízení k profilu](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stránce **Zkontrolovat a vytvořit** zkontrolujte nastavení a pak výběrem možnosti **Vytvořit** vytvořte profil.  

   > [!div class="mx-imgBorder"]
   > ![Zkontrolujte a vytvořte.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Vytvoření konfigurace stránky stavu registrace (ESP) a jeho přiřazení ke skupině zařízení

Stránka stavu registrace (ESP) zobrazuje stav úplného procesu konfigurace zařízení, který se spustí, když se uživatel spravovaný pomocí MDM poprvé přihlásí k zařízení. Ujistěte se, že vaše konfigurace ESP vypadá podobně jako v následujícím příkladu, a ověřte správnost přiřazení.  

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

Po dokončení výše uvedených pokynů si vaši uživatelé HoloLens 2 projde následující prostředí a zřžou svá HoloLens zařízení:  

1. Prostředí Autopilotu vyžaduje přístup k internetu. K zajištění přístupu k internetu použijte jednu z následujících možností:

    - Připojení zařízení do Wi-Fi v prostředí OOBE a nechat ho automaticky detekovat prostředí Autopilotu. Je to jediný čas, kdy budete muset pracovat s OOBE, dokud se prostředí Autopilotu nedokoní samo.

    - Připojení připojit zařízení k síti Ethernet pomocí adaptérů USB-C na Ethernet pro připojení k drátovému internetu a nechat HoloLens 2 dokončit prostředí Autopilotu.

    - Připojení bezdrátového připojení k internetu připojte zařízení pomocí adaptérů USB-C na Wi-Fi a nechte HoloLens 2 dokončit prostředí Autopilotu.

        > [!IMPORTANT]  
       > Zařízení, která se pokoušejí Wi-Fi v OOBE pro Autopilot, musí být na [Windows Holographic verze 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > U zařízení, která používají ethernetové adaptéry, musíte zařízení připojit k síti před tím, než se spustí prostředí při spuštění počítače. Zařízení určuje, jestli se na první obrazovce OOBE zřizuje jako zařízení Autopilot. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete zařízení zřídit jako zařízení Autopilot, nemůžete ho později změnit na Autopilot Provisioning. Místo toho byste muset tento postup spustit znovu, abyste mohli zařízení zřídit jako zařízení Autopilot.

1. Zařízení by mělo automaticky spustit OOBE. Nereagovat na OOBE.

    > [!IMPORTANT]
    > Pokud chcete systém přenést do pohotovostního režimu nebo vypnutí, v průběhu režimu Autopilotu nereagovat na OOBE nebo stisknout tlačítko napájení. To může způsobit, že se tok Autopilotu dokončí.

   Nechte HoloLens 2 zjistit připojení k síti a povolit automatické dokončení spuštění počítače. Zařízení se může restartovat během spuštění počítače. Obrazovky OOBE by měly vypadat podobně jako na následujícím příkladu.

   ![OOBE krok 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE krok 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE krok 3.](./images/autopilot-device-setup.jpg)

1. Na konci OOBE se k zařízení můžete přihlásit pomocí svého uživatelského jména a hesla.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Uzamčení tenanta CSP a Autopilot

HoloLens 2 podporují TenantLockdown CSP od verze Windows Holographic verze 20H2. Tento CSP udržuje zařízení v tenantovi organizace tím, že je uzamyká pro tohoto tenanta, a to i přes resetování zařízení nebo koliázku.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, HoloLens 2 k registraci MDM pouze pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (na začátku nastavená) na HoloLens 2, zůstane tato hodnota v zařízení bez ohledu na kolísání, aktualizace operačního systému atd.

Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true na HoloLens 2, po připojení k síti počká OOBE po neomezenou dobu na úspěšné stažení a použití profilu Autopilot.

Po nastavení uzlu RequireNetworkInOOBE u tenantaLockdown CSP na úrovni HoloLens 2 jsou v OOBE zakázané následující operace:

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

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Proč se při autopilotu zobrazuje 0x80180014?

Toto je chyba zobrazená během procesu autopilotu na zařízení. tento problém se zobrazí jenom v případě, že zařízení HoloLens provedlo následující:

1. Už jste prošli prostřednictvím autopilotu aspoň jednou.
1. Nyní se resetuje a znovu použije pro autopilot.

Prostředí funguje v případě, že se s určitou chybou spustí i funkce autopilot.

![HoloLens Kód chyby selhání autopilotu](images/autopilot-0x80180014-failure.jpg)

Jaké kroky je potřeba provést k vyřešení této chyby?

1. Postupujte podle kroků v tématu [řešení potíží s automatickým pilotním importem a](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) registrací pro odebrání zařízení z Intune. (Správce Intune bude muset tuto úlohu provést.)
1. Po dokončení kroku 1 restartujte zařízení a přihlaste se.
1. přejděte na **Nastavení**  ->  **Update & Security**  ->  **Reset & recovery** a vyberte začínáme.
    1. Pokud se vyskytnou problémy s kroky 2 & 3, přečtěte si téma alternativy k [resetování zařízení v HoloLens Reset/reflash](hololens-recovery.md).

Autopilot by se pak měl úspěšně zaregistrovat.

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
