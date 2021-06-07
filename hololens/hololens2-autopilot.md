---
title: Windows Autopilot pro HoloLens 2
description: Naučte se, jak nastavit, nakonfigurovat a řešit potíže s autopilotem na zařízeních HoloLens 2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 9625f3fd1cd6a928f6bd20ba809c750c625143cf
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379307"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

Od Windows holografické verze 2004, HoloLens 2 podporuje [režim automatického nasazení](https://docs.microsoft.com/mem/autopilot/self-deploying) Windows autopilotu s Microsoft Intuneem (podpora třetích stran MDMs se nepodporuje). Správci můžou nakonfigurovat integrované prostředí (OOBE) ve službě Microsoft Endpoint Manager a povolit koncovým uživatelům připravovat zařízení pro obchodní použití bez jakýchkoli interakcí. Tím se sníží nároky na správu inventáře, náklady na praktickou přípravu zařízení a podpora volání od zaměstnanců během prostředí pro nastavení. Další informace najdete v dokumentaci k [Windows autopilotu](https://docs.microsoft.com/mem/autopilot/windows-autopilot) .

Podobně jako u zařízení Surface doporučujeme, aby zákazníci spolupracovali s [poskytovatelem Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejce nebo distributor) a získali zařízení zaregistrovaná ve službě autopilotu prostřednictvím partnerského centra. Další metody registrace zařízení jsou popsány v dokumentaci k [Přidání zařízení](https://docs.microsoft.com/mem/autopilot/add-devices) , i když využívají partneři Microsoftu pro kanály k zajištění nejefektivnějších kompletních cest.

> [!NOTE]
> Od 11/20/2020 konfigurace autopilotu pro HoloLens v Microsoft Endpoint Manageru se převádí na **Public Preview**. Zákazníci už nebudou muset registrovat v privátní verzi Preview a všichni klienti budou moct nastavit automatický pilotní nasazení v centru pro správu nástroje MEM.

Když uživatel spustí proces automatického nasazení autopilotu, provede autopilotní následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD). Všimněte si, že autopilot pro HoloLens nepodporuje připojení ke službě Active Directory ani hybridní připojení ke službě Azure AD.

1. K registraci zařízení ve službě Microsoft Endpoint Manager (nebo jiné službě MDM) použijte službu Azure AD.

1. Stáhněte a použijte zásady zaměřené na zařízení, certifikáty, síťové profily a aplikace.

1. Zřídí zařízení.

1. Prezentovat přihlašovací obrazovku uživateli

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurace autopilotu pro HoloLens 2

Použijte prosím následující postup a nastavte prostředí:

1. [Přečtěte si požadavky pro Windows autopilot pro HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Povolit automatickou registraci MDM](#2-enable-automatic-mdm-enrollment)

1. [Registrovat zařízení ve Windows autopilotu.](#3-register-devices-in-windows-autopilot)

1. [Vytvořte skupinu zařízení.](#4-create-a-device-group)

1. [Vytvořte profil nasazení.](#5-create-a-deployment-profile)

1. [Ověřte konfiguraci stránky stavu registrace (ESP).](#6-verify-the-esp-configuration)

1. [Ověřte stav profilu zařízení HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Projděte si požadavky na Windows autopilot pro HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Přečtěte si následující části článku věnovaném požadavkům na Windows autopilot:

- [Požadavky sítě](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Licenční požadavky](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Požadavky na konfiguraci](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Přečtěte si část [požadavky](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)v článku Self-Deploying režimu Windows autopilot.** Vaše prostředí musí splňovat tyto požadavky a také standardní požadavky Windows autopilotování. Nemusíte si projít části "krok za krokem" a "ověření" v článku. Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Informace o tom, jak zaregistrovat zařízení a nakonfigurovat profily, najdete v části [2. Registrovat zařízení ve Windows autopilotu](#3-register-devices-in-windows-autopilot) a [4. Vytvořit profil nasazení](#5-create-a-deployment-profile) v tomto článku. Pokud chcete nakonfigurovat a spravovat profily režimu automatického nasazení autopilotu, ujistěte se, že máte přístup k [centru pro správu služby Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### <a name="review-hololens-os-requirements"></a>Kontrola požadavků na operační systém HoloLens:

- Zařízení musí být ve [Windows holografické verzi 2004](hololens-release-notes.md#windows-holographic-version-2004) (Build 19041,1103) nebo novější. K potvrzení verze buildu na vašem zařízení nebo opětovném bliknutí do nejnovějšího operačního systému použijte [Průvodce rozšířeným obnovením (oblouk)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) a [pokyny pro opětovné použití zařízení v přehrávači](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). Všimněte si, že zařízení dodaná až do 12. září 2020 mají předinstalované Windows holografické verze 1903. Obraťte se na svého prodejce, abyste měli jistotu, že se vám budou dodávat zařízení připravená k autopilotu.

- Windows holografický verze 2004 podporuje jenom připojení typu autopilot přes Ethernet. **Před zapnutím** adaptéru zajistěte, aby byl adaptér HoloLens připojen k síti Ethernet pomocí adaptéru USB-C do sítě Ethernet. Při spuštění zařízení není nutná žádná interakce s uživatelem. Pokud plánujete zavedení autopilotního nasazení na mnoho zařízení HoloLens, doporučujeme, abyste si vyplánovali infrastrukturu adaptéru. Nedoporučujeme používat rozbočovače USB, protože často vyžadují instalaci dalších ovladačů třetích stran, což u HoloLens nepodporuje.

- [Windows holografický, verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (Build 19041,1128) nebo novější podporuje autopilotování prostřednictvím Wi-Fi, i když stále můžete používat adaptéry Ethernet. Pro zařízení připojená přes Wi-Fi musí uživatel:

     - Projděte si scénu Hummingbird
     - Zvolit jazyk a národní prostředí
     - Spustit oči – kalibrace
     - Navázat připojení k síti

- Windows Holografick, verze 20H2 podporuje [TENANTLOCKDOWN CSP a autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), který zamkne zařízení pro tenanta, a zajišťuje, aby zařízení zůstalo vázané na tohoto tenanta v případě náhodného nebo úmyslného resetování nebo vymazání.  

- Ujistěte se, že zařízení ještě nejsou členem služby Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení autopilotu dokončí tyto kroky. Pokud chcete zajistit, aby se všechny informace týkající se zařízení vyčistily, zkontrolujte stránky **zařízení** v portálech Azure AD a Intune. Všimněte si, že funkce "převést všechna cílová zařízení na autopilot" není v tomto okamžiku podporována na HoloLens.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. povolení automatického zápisu MDM:

Aby mohl Automatický pilot úspěšně probíhat, budete muset v Azure Portal povolit automatickou registraci MDM. Tím umožníte, aby se zařízení zaregistrovalo bez uživatele.

V [Azure Portal](https://portal.azure.com/#home) vyberte Microsoft Intune **Azure Active Directory**  ->  **mobility (MDM a mam)**  ->  . Pak nakonfigurujte **obor uživatele MDM**, budete muset vybrat **vše**.

Přečtěte si následující stručné pokyny, jak [Povolit automatickou registraci MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) , nebo [Úvodní příručku pro automatické registrace](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) , kde najdete ještě další informace o nastavení.

### <a name="3-register-devices-in-windows-autopilot"></a>3. registrace zařízení ve Windows autopilotu

Vaše zařízení musí být zaregistrovaná ve Windows autopilotu před prvním nastavením. Dokumentaci k paměti pro MEM o registraci zařízení najdete v tématu [Přidání zařízení do autopilotního nasazení](https://docs.microsoft.com/mem/autopilot/add-devices).  

Existují tři hlavní způsoby registrace zařízení HoloLens:

 - **Prodejce může zaregistrovat zařízení v partnerském centru, když umístíte objednávku.**

   > [!NOTE]  
   > Toto je doporučená cesta pro přidávání zařízení do služby autopilotu. [Přečtěte si další informace](https://docs.microsoft.com/mem/autopilot/partner-registration).  

 - **Žádost o [podporu můžete odeslat](hololens2-autopilot-registration-support.md) přímo společnosti Microsoft.**
 - **Načtěte hodnotu hash hardwaru (označuje se také jako ID hardwaru) a zaregistrujte zařízení ručně v centru pro správu nástroje mem**.

#### <a name="obtain-hardware-hash"></a>Získat hodnotu hash hardwaru
Existují dva způsoby, jak načíst hodnotu hash hardwaru.
1. Žádost o [podporu můžete odeslat](hololens2-autopilot-registration-support.md) přímo společnosti Microsoft.
2. Můžete ho načíst ze zařízení. Zařízení zaznamenává jeho hodnotu hash hardwaru do souboru CSV během procesu OOBE nebo později, pokud vlastník zařízení spustí proces shromažďování protokolů diagnostiky (popsaný v následujícím postupu). Většinou je vlastníkem zařízení první uživatel, který se k zařízení přihlašuje.
     > [!WARNING]
     > Pokud jste v sestaveních před 20H2 prošli pomocí OOBE a telemetrie byla nastavena na hodnotu požadováno, nemůžete pomocí této metody shromáždit hodnotu hash hardwaru pro autopilot. Aby se hodnota hash hardwaru mohla shromažďovat přes tuto metodu, nastavte možnost telemetrie na úplnou prostřednictvím aplikace nastavení a vyberte > Diagnostika osobních údajů.

    1. Spusťte zařízení HoloLens 2.

    1. Na zařízení stiskněte tlačítko **napájení** a **rozhlasitost dolů** a pak je uvolněte. Zařízení shromažďuje diagnostické protokoly a hodnotu hash hardwaru a ukládá je do sady .zip souborů.

   1. Úplné podrobnosti a výukové video, jak si to předtvořit, najdete v článku o [diagnostice offline](hololens-diagnostic-logs.md#offline-diagnostics).

    1. Připojte zařízení k počítači pomocí kabelu USB-C.

    1. V počítači otevřete Průzkumníka souborů. Otevřete **Tento počítač \\ \<*HoloLens device name*> \\ interní \\ dokumenty úložiště** a vyhledejte soubor AutopilotDiagnostics.zip.  

       > [!NOTE]  
       > Soubor .zip možná není hned dostupný. Pokud soubor ještě není připravený, může se ve složce dokumenty zobrazit soubor HoloLensDiagnostics. Temp. Chcete-li aktualizovat seznam souborů, aktualizujte okno.
    
    1. Extrahujte obsah souboru AutopilotDiagnostics.zip.

    1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru "DeviceHash". Zkopírujte tento soubor na jednotku v počítači, kde k němu máte přístup později.  

       > [!IMPORTANT]  
       > Data v souboru CSV by měla používat následující formát záhlaví a čáry:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrovat zařízení přes MEM

1. V [centru pro správu Microsoft Endpoint Manageru](https://endpoint.microsoft.com)vyberte **zařízení**  >    >  **registrace Windows Windows** a pak vyberte **zařízení**  >  **importovat** v rámci **programu Windows autopilot Deployment**.

1. V části **Přidat zařízení Windows autopilot** vyberte soubor CSV DeviceHash, vyberte **otevřít** a pak vyberte **importovat**.  

   > [!div class="mx-imgBorder"]
   > ![K importu hodnoty hash hardwaru použijte příkaz Import.](./images/hololens-ap-hash-import.png)

1. Po dokončení importu vyberte Zařízení **s**  >  **Windows Registrace zařízení**  >  **s Windows**  >    >  **Synchronizovat**. Dokončení tohoto procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zaregistrované zařízení zobrazit, vyberte **Aktualizovat.**  

   > [!div class="mx-imgBorder"]
   > ![Seznam zařízení zobrazíte pomocí příkazů Synchronizovat a Aktualizovat.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Vytvoření skupiny zařízení

1. V [Centru Endpoint Manager Microsoftu](https://endpoint.microsoft.com)vyberte **Skupiny Nová**  >  **skupina.**

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

### <a name="5-create-a-deployment-profile"></a>5. Vytvoření profilu nasazení

1. V [Centru Endpoint Manager](https://endpoint.microsoft.com)microsoftu vyberte Zařízení s Windows registrace zařízení s  >    >  **Windows** Windows Autopilot  >  **profilů nasazení** Vytvořit  >  **profil**  >  **HoloLens.**
   ![Rozevírací seznam Vytvořit profil obsahuje položku HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Zadejte název a popis profilu a pak vyberte **Další.**  
   Měl by se zobrazit seznam, který obsahuje **HoloLens**. Pokud tato možnost není k dispozici, kontaktujte nás pomocí jedné z možností [zpětné](hololens2-autopilot.md#feedback-and-support-for-autopilot) vazby.

   > [!div class="mx-imgBorder"]
   > ![Přidání názvu a popisu profilu](./images/hololens-ap-profile-name.png)

1. Většina **nastavení je** předem nakonfigurovaná tak, aby se pro toto vyhodnocení zjednodušil přístupový proces. Volitelně můžete nakonfigurovat následující nastavení:  

   - **Jazyk (oblast):** Vyberte jazyk pro OOBE. Doporučujeme vybrat jazyk ze seznamu podporovaných jazyků [pro HoloLens 2.](hololens2-language-support.md)
   - **Automaticky nakonfigurovat klávesnici:** Pokud chcete zajistit, aby klávesnice odpovídala vybranému jazyku, vyberte **Ano.**
   - Použít **šablonu** názvu zařízení: Pokud chcete automaticky nastavit  název zařízení při spuštění počítače, vyberte Ano a potom zadejte frázi šablony **a** zástupné symboly do pole Zadejte název. Zadejte například předponu a zástupný symbol pro čtyřciferné `%RAND:4%` &mdash; náhodné číslo.
     > [!NOTE]  
     > Pokud použijete šablonu názvu zařízení, proces OOBE restartuje zařízení ještě jednou po použití názvu zařízení a před jeho připojením ke službě Azure AD. Toto restartování umožňuje, aby se nový název projeví.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurace nastavení OOBE](./images/hololens-ap-profile-oobe.png)

1. Po konfiguraci nastavení vyberte **Další.**
1. Na stránce **Značky** oboru můžete volitelně přidat značky oboru, které chcete pro tento profil použít. Další informace o značkách oboru najdete v tématu Použití řízení přístupu na základě role a značek [oboru pro distribuované IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Po dokončení vyberte **Další.**
1. Na stránce **Přiřazení v** části Přiřadit **k** vyberte **Vybrané skupiny.**
1. V **části VYBRANÉ SKUPINY** vyberte + Vybrat **skupiny, které se zahrnou.**
1. V seznamu **Vybrat skupiny** k zahrnutí vyberte skupinu zařízení, kterou jste vytvořili pro zařízení Autopilot HoloLens, a pak vyberte **Další.**  
  
   Pokud chcete některé skupiny vyloučit, vyberte **Vybrat skupiny, které** chcete vyloučit, a vyberte skupiny, které chcete vyloučit.

   > [!div class="mx-imgBorder"]
   > ![Přiřazení skupiny zařízení k profilu](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stránce **Zkontrolovat a vytvořit** zkontrolujte nastavení a pak výběrem možnosti **Vytvořit** vytvořte profil.  

   > [!div class="mx-imgBorder"]
   > ![Kontrola a vytvoření](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Ověření konfigurace ESP

Stránka stavu registrace (ESP) zobrazuje stav úplného procesu konfigurace zařízení, který se spustí při prvním přihlášení spravovaného uživatele MDM k zařízení. Ujistěte se, že vaše konfigurace ESP vypadá podobně jako v následujícím příkladu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Ověření stavu profilu zařízení HoloLens

1. V Centru pro Endpoint Manager Microsoftu **vyberte** Zařízení s Windows zařízení s  >    >  **Windows pro**  >  **registraci.**

1. Ověřte, že jsou uvedená zařízení HoloLens a že jejich stav profilu je **Přiřazeno.**  

   > [!NOTE]  
   > Přiřazení profilu k zařízení může několik minut trvat.  

   > [!div class="mx-imgBorder"]
   > ![Přiřazení zařízení a profilu.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot pro uživatelské prostředí HoloLens 2

Po dokončení výše uvedených pokynů si uživatelé HoloLens 2 projde následující prostředí ke zřízení svých zařízení HoloLens:  

1. Prostředí Autopilotu vyžaduje přístup k internetu. Pokud chcete zajistit přístup k internetu, použijte jednu z následujících možností:

    - Připojte zařízení k síti Wi-Fi oOBE a nechte ho automaticky detekovat prostředí Autopilotu. Je to jediný čas, kdy budete potřebovat pracovat s OOBE, dokud se prostředí Autopilot samo nedokoní. Upozorňujeme, že Ve výchozím nastavení HoloLens 2 po zjištění internetu počká 10 sekund na rozpoznání Autopilotu. Pokud během 10 sekund není detekován žádný profil Autopilot, zobrazí se při jeho aktivaci eula. Pokud narazíte na tento scénář, restartujte zařízení, aby bylo možné udělat další pokus o rozpoznání Autopilotu. Upozorňujeme také, že OOBE může čekat po neomezenou dobu na Autopilot pouze v případě, že je na zařízení nastavená zásada TenantLockdown.

    - Připojte zařízení k Ethernetu pomocí adaptérů USB-C na Ethernet pro připojení k drátovému internetu a nechte HoloLens 2 automaticky dokončit prostředí Autopilot.

    - Připojte zařízení pomocí adaptérů USB-C na Wi-Fi pro bezdrátové připojení k internetu a nechte HoloLens 2 automaticky dokončit prostředí Autopilot.

        > [!IMPORTANT]  
       > Zařízení, která se pokoušejí Wi-Fi v prostředí OOBE pro Autopilot, musí být na [Windows Holographic verze 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > U zařízení, která používají ethernetové adaptéry, musíte zařízení připojit k síti před tím, než se spustí prostředí při spuštění počítače. Zařízení určuje, jestli se na první obrazovce OOBE zřizuje jako zařízení Autopilot. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete zařízení zřídit jako zařízení Autopilot, nemůžete ho později změnit na Autopilot Provisioning. Místo toho byste muset tento postup spustit znovu, abyste zařízení z mohli zřídit jako zařízení Autopilot.

1. Zařízení by mělo automaticky spustit OOBE. Nereagovat na OOBE. Místo toho si sedněte, vraťte se a uvolněte se! Nechte HoloLens 2 detekovat připojení k síti a umožnovat automatické dokončení OOBE. Zařízení se může restartovat během spuštění počítače. Obrazovky OOBE by měly vypadat podobně jako na následujícím příkladu.

   ![OOBE krok 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE krok 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE krok 3](./images/autopilot-device-setup.jpg)

1. Na konci OOBE se k zařízení můžete přihlásit pomocí svého uživatelského jména a hesla.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a Autopilot

Zařízení HoloLens 2 podporují tenantaLockdown CSP ve Windows Holographic verze 20H2. Tento zprostředkovatel CSP uchovává zařízení v tenantovi organizace tím, že je uzamyká pro tohoto tenanta, a to i přes resetování zařízení nebo koliázku.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby se HoloLens 2 váže na registraci MDM jenom pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (původně nastavená) na HoloLens 2, zůstane tato hodnota na zařízení i přes znovu blikající, aktualizace operačního systému atd.

Jakmile je u HoloLens 2 uzel RequireNetworkInOOBE tenantaLockdown nastaven na true, po připojení k síti počká OOBE po neomezenou dobu na úspěšné stažení a použití profilu Autopilot.

Jakmile je u HoloLens 2 uzel RequireNetworkInOOBE tenantaLockdownu nastavený na true, jsou v OOBE zakázané následující operace:

- Vytvoření místního uživatele pomocí zřizování modulu runtime 
- Provádění operace připojení k Azure AD prostřednictvím zřizování modulu runtime 
- Výběr vlastníka zařízení v prostředí pro OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak to nastavit pomocí Intune? 
1. Vytvořte vlastní konfigurační profil zařízení OMA URI a jako uzel RequireNetworkInOOBE zadejte true, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Nastavení uzamykání tennantu přes OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení.

1. Vytvořte člena zařízení HoloLens 2 skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení TenantLockdown RequireNetworkInOOBE na HoloLens 2?

1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše.

1. Vytvořte vlastní konfigurační profil zařízení založený na OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže.
Hodnota OMA-URI by měla být./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím identifikátoru URI OMA v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení. 

1. Nastavte člena zařízení HoloLens 2 pro skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. Po úspěšném nastavení této konfigurace zařízení na zařízení HoloLens 2 budou účinky TenantLockdown neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co se stane při POČÁTEČNÍm spuštění, pokud je profil autopilotu nepřiřazený k HoloLens po nastavení TenantLockdown na hodnotu true? 
Při POČÁTEČNÍm navýšení bude profil pro autopilot čekat na neomezenou dobu stahování a zobrazí se dialogové okno. Aby se odstranily účinky TenantLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí jenom autopilotu a RequireNetworkInOOBE musí být nastavené tak, jak je popsané v předchozím kroku, než se odeberou omezení zavedená poskytovatelem CSP pro TenantLockdown.

![Zobrazení v zařízení pro dobu, kdy se na zařízení vynutila zásada.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Známé problémy & omezení

- Zkoumáme problém, kdy se instalace aplikace na základě kontextu zařízení nakonfigurovaná v programu MEM nevztahuje na HoloLens. [Přečtěte si další informace o kontextu zařízení a o instalaci kontextu uživatele.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Při nastavování autopilotu přes Wi-Fi může nastat instance, ve které se profil autopilotu nestáhne při prvním navázání připojení k Internetu. V tomto případě se zobrazí licenční smlouva s koncovým uživatelem (EULA) a uživatel má možnost pokračovat v instalaci bez automatického pilotního nasazení. Pokud se chcete znovu pokusit o nastavení pomocí modulu autopilot, vložte zařízení do režimu spánku a pak ho restartujte, nebo zařízení restartujte a nechte to znovu.
- Funkce převést všechna cílová zařízení na autopilots není v tomto okamžiku podporována na HoloLens.  

### <a name="troubleshooting"></a>Řešení potíží

Následující články můžou být užitečným prostředkem, abyste si mohli přečíst další informace a řešit problémy s výkonem pro autopilot, ale pamatujte na to, že tyto články jsou založené na Windows 10 desktopu a ne všechny informace se můžou vztahovat na HoloLens:

- [Windows autopilot – známé problémy](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Řešení potíží s registrací zařízení s Windows v Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows autopilot – konflikty zásad](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro autopilot

Chcete-li poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pro podporu registrace zařízení se obraťte na svého prodejce nebo distributora.
- U obecných dotazů na podporu týkající se služby Windows autopilot nebo pro problémy, jako jsou přiřazení profilů, vytváření skupin nebo ovládací prvky pro pracovní portál, [kontaktujte podporu služby Microsoft Endpoint Manager](https://docs.microsoft.com/mem/get-support) .  
- Pokud je zařízení zaregistrované do služby autopilot a profil se přiřadí na portále MEM, obraťte se na [podporu](https://docs.microsoft.com/hololens/) HoloLens (viz karta podpora). Otevřete prosím lístek podpory a pokud je to možné, zahrňte snímky obrazovky a protokoly zachytáváním [offline diagnostických protokolů](hololens-diagnostic-logs.md#offline-diagnostics) během nastavování mimo prostředí (OOBE).
- K nahlášení problému ze zařízení použijte aplikaci centra Feedback na svém HoloLens. V centru pro zpětnou vazbu vyberte kategorii zařízení **podnikového řízení**  >   .
- Pokud chcete poskytnout obecnou zpětnou vazbu k autopilotu pro HoloLens, můžete odeslat tento [průzkum](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) .
