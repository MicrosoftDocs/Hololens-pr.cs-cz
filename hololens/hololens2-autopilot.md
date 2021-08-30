---
title: Windows Autopilot pro HoloLens 2
description: naučte se, jak nastavit, nakonfigurovat a řešit potíže s autopilotem na zařízeních HoloLens 2.
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
ms.openlocfilehash: 4782b5d4d3c51038f7810c57d2144758ce0dc1ac
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190187"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

> [!NOTE]
> konfigurace autopilotu pro HoloLens v Microsoft Endpoint Manager provádí přechod z **Public Preview** na **obecnou dostupnost**. Všichni klienti budou moci nastavit program Autopilot v centru pro správu nástroje MEM.

počínaje Windows holografickou verzí 2004 HoloLens 2 podporuje Windows [režim automatického nasazení](/mem/autopilot/self-deploying) autopilotu s Microsoft Intune (MDMs třetí strany se nepodporuje). správci můžou nakonfigurovat integrované prostředí (OOBE) v Microsoft Endpoint Manager a umožnit koncovým uživatelům připravovat zařízení pro podnikové použití bez jakýchkoli interakcí. Tím se sníží nároky na správu inventáře, náklady na praktickou přípravu zařízení a podpora volání od zaměstnanců během prostředí nastavení. další informace najdete v dokumentaci k [Windows autopilotu](/mem/autopilot/windows-autopilot) .

podobně jako u zařízení surface je vhodné, aby zákazníci spolupracovali se společností Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejci nebo distributor) a mohli zařízení zaregistrovaná ve službě autopilotu prostřednictvím partnerského centra. Další metody registrace zařízení jsou popsány v dokumentaci k [Přidání zařízení](/mem/autopilot/add-devices) , i když používají partneři Microsoftu pro kanály k zajištění nejefektivnějších kompletních cest.



Když uživatel spustí proces automatického nasazení autopilotu, provede autopilotní následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD). všimněte si, že autopilot for HoloLens nepodporuje připojení ke službě Active Directory ani k hybridní službě Azure AD join.

1. pomocí služby Azure AD zaregistrujete zařízení v Microsoft Endpoint Manager (nebo jiné službě MDM).

1. Stáhněte a použijte zásady zaměřené na zařízení, certifikáty, síťové profily a aplikace.

1. Zřídí zařízení.

1. Prezentovat přihlašovací obrazovku uživateli

## <a name="configuring-autopilot-for-hololens-2"></a>konfigurace autopilotu pro HoloLens 2

Pro nastavení prostředí postupujte podle následujících kroků:

1. [přečtěte si požadavky na Windows autopilot pro HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Povolit automatickou registraci MDM](#2-enable-automatic-mdm-enrollment)

1. (Jenom pro Intune) [ujistěte se prosím, že registrace MDM není pro zařízení Windows blokovaná.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [registrujte zařízení v Windows autopilotu.](#4-register-devices-in-windows-autopilot)

1. [Vytvořte skupinu zařízení.](#5-create-a-device-group)

1. [Vytvořte profil nasazení.](#6-create-a-deployment-profile)

1. [Ověřte konfiguraci stránky stavu registrace (ESP).](#7-verify-the-esp-configuration)

1. [ověřte stav profilu zařízení HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. projděte si požadavky na Windows autopilot pro HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>přečtěte si následující oddíly článku Windows požadavky na autopilot:

- [Požadavky sítě](/mem/autopilot/networking-requirements)  
- [Licenční požadavky](/mem/autopilot/licensing-requirements)  
- [Požadavky na konfiguraci](/mem/autopilot/configuration-requirements)

**přečtěte si část [požadavky](/windows/deployment/windows-autopilot/self-deploying#requirements)v článku Windows Self-Deploying režimu autopilotu.** vaše prostředí musí splňovat tyto požadavky a také standardní Windows požadavky na autopilot. Nemusíte si projít části "krok za krokem" a "ověření" v článku. Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Informace o tom, jak zaregistrovat zařízení a nakonfigurovat profily, najdete v části [4. registrace zařízení v Windows autopilot](#4-register-devices-in-windows-autopilot) a [6. Vytvořit profil nasazení](#6-create-a-deployment-profile) v tomto článku. pokud chcete nakonfigurovat a spravovat profily režimu automatického nasazení autopilotu, ujistěte se, že máte přístup k [centru pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### <a name="review-hololens-os-requirements"></a>kontrola HoloLens požadavků na operační systém:

- zařízení musí být na [Windows holografické verze 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041,1103) nebo novější. Pokud chcete ověřit verzi buildu na vašem zařízení nebo se znovu dosvítit k nejnovějšímu operačnímu systému, použijte [Průvodce rozšířeným obnovením (oblouk)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) a pokyny pro opětovné použití [zařízení](/hololens/hololens-recovery#clean-reflash-the-device). všimněte si, že zařízení dodaná až do 12. září 2020 mají předem nainstalovanou Windows holografickou verzi 1903. Obraťte se na svého prodejce a ujistěte se, že vám budou zasílána zařízení pro autopiloting, která jsou připravena k vám.

- Windows Holografická verze 2004 podporuje jenom připojení typu autopilot přes Ethernet. **před zapnutím** adaptéru zajistěte, aby byla HoloLens připojená k síti ethernet pomocí adaptéru USB-C do sítě ethernet. Při spuštění zařízení není nutná žádná interakce s uživatelem. pokud plánujete zavedení autopilotního nasazení na mnoho HoloLensch zařízení, doporučujeme, abyste si vyplánovali infrastrukturu adaptéru. Nedoporučujeme používat rozbočovače USB, protože často vyžadují instalaci dalších ovladačů třetích stran, což se v HoloLens nepodporuje.

- [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041,1128) nebo novější podporuje autopilotování prostřednictvím Wi-Fi, i když stále můžete používat adaptéry ethernet. Pro zařízení připojená přes Wi-Fi musí uživatel:

     - Projděte si scénu Hummingbird
     - Zvolit jazyk a národní prostředí
     - Spustit oči – kalibrace
     - Navázat připojení k síti

- Windows Holografická verze 20H2 podporuje [TENANTLOCKDOWN CSP a autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), který zamkne zařízení pro tenanta a zajišťuje, aby zařízení zůstalo vázané na tohoto tenanta v případě náhodného nebo úmyslného resetování nebo vymazání.  

- Ujistěte se, že zařízení ještě nejsou členem služby Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení autopilotu dokončí tyto kroky. Pokud chcete zajistit, aby se všechny informace týkající se zařízení vyčistily, zkontrolujte stránky **zařízení** v portálech Azure AD a Intune. všimněte si, že funkce převést veškerou cílovou zařízení na autopilot není v současnosti podporovaná HoloLens.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. povolení automatického zápisu MDM:

Aby mohl Automatický pilot úspěšně probíhat, budete muset v Azure Portal povolit automatickou registraci MDM. Tím umožníte, aby se zařízení zaregistrovalo bez uživatele.

v [Azure Portal](https://portal.azure.com/#home) vyberte Microsoft Intune **Azure Active Directory**  ->  **mobility (MDM a MAM)**  ->  . Pak nakonfigurujte **obor uživatele MDM**, budete muset vybrat **vše**.

Přečtěte si následující stručné pokyny [k povolení automatické registrace MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) nebo [Úvodní příručky k automatickému](/mem/intune/enrollment/quickstart-setup-auto-enrollment) zprovoznění, kde najdete ještě další informace o nastavení.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.

aby mohl automatický pilotní postup úspěšně proběhnout, musíte zajistit, aby se zařízení HoloLens mohla zaregistrovat. vzhledem k tomu, že se HoloLens považuje za Windows zařízení, bude nutné, aby nedocházelo k omezením registrace, která by mohla blokovat nasazení. [Projděte si tento seznam omezení](/mem/intune/enrollment/enrollment-restrictions-set) a ujistěte se, že budete moci zaregistrovat svá zařízení.

### <a name="4-register-devices-in-windows-autopilot"></a>4. registrace zařízení v Windows autopilotování

vaše zařízení musí být zaregistrovaná v Windows autopilotu před prvním nastavením. Dokumentaci k paměti pro MEM o registraci zařízení najdete v tématu [Přidání zařízení do autopilotního nasazení](/mem/autopilot/add-devices).  

existují tři základní způsoby, jak zaregistrovat HoloLens zařízení:

 - **Prodejce může zaregistrovat zařízení v partnerském centru, když umístíte objednávku.**

   > [!NOTE]  
   > Toto je doporučená cesta pro přidávání zařízení do služby autopilotu. [Přečtěte si další informace](/mem/autopilot/partner-registration).  

 - **Žádost o [podporu můžete odeslat](hololens2-autopilot-registration-support.md) přímo společnosti Microsoft.**
 - **Načtěte hodnotu hash hardwaru (označuje se také jako ID hardwaru) a zaregistrujte zařízení ručně v centru pro správu nástroje mem**.

#### <a name="obtain-hardware-hash"></a>Získat hodnotu hash hardwaru
Existují dva způsoby, jak načíst hodnotu hash hardwaru.
1. Žádost o [podporu můžete odeslat](hololens2-autopilot-registration-support.md) přímo společnosti Microsoft.
2. Můžete ho načíst ze zařízení. Zařízení zaznamenává jeho hodnotu hash hardwaru do souboru CSV během procesu OOBE nebo později, pokud vlastník zařízení spustí proces shromažďování protokolů diagnostiky (popsaný v následujícím postupu). Většinou je vlastníkem zařízení první uživatel, který se k zařízení přihlašuje.
     > [!WARNING]
     > Pokud jste v sestaveních před 20H2 prošli pomocí OOBE a telemetrie byla nastavena na hodnotu požadováno, nemůžete pomocí této metody shromáždit hodnotu hash hardwaru pro autopilot. aby bylo možné shromáždit hodnotu hash hardwaru prostřednictvím této metody, nastavte možnost telemetrie na úplnou prostřednictvím aplikace Nastavení a vyberte možnost diagnostika osobních údajů >.

    1. spusťte zařízení HoloLens 2.

    1. Na zařízení stiskněte tlačítko **napájení** a **rozhlasitost dolů** a pak je uvolněte. Zařízení shromažďuje diagnostické protokoly a hodnotu hash hardwaru a ukládá je do sady .zip souborů.

   1. Úplné podrobnosti a výukové video, které vám poformují o tom, jak se seznámit s [diagnostikou offline](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Připojte zařízení k počítači pomocí kabelu USB-C.

    1. V počítači otevřete Průzkumníka souborů. otevřete **tento počítač \\ \<*HoloLens device name*> \\ interní Storage \\ dokumenty** a vyhledejte AutopilotDiagnostics.zip soubor.  

       > [!NOTE]  
       > Soubor .zip možná není hned dostupný. Pokud soubor ještě není připravený, může se ve složce dokumenty zobrazit soubor HoloLensDiagnostics. Temp. Chcete-li aktualizovat seznam souborů, aktualizujte okno.
    
    1. Extrahujte obsah souboru AutopilotDiagnostics.zip.

    1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru "DeviceHash". Zkopírujte tento soubor na jednotku v počítači, kde k ní budete později mít přístup.  

       > [!IMPORTANT]  
       > Data v souboru CSV by měla používat následující hlavičku a formát řádku:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrace zařízení prostřednictvím MEM

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com) **vyberte** Zařízení Windows Windows registraci a potom v části Windows Autopilot Deployment Program vyberte Import  >    >     >   **zařízení.**

1. V **části Windows zařízení Autopilot** vyberte soubor CSV DeviceHash, vyberte **Otevřít** a pak vyberte **Importovat.**  

   > [!div class="mx-imgBorder"]
   > ![K importu hodnoty hash hardwaru použijte příkaz Import.](./images/hololens-ap-hash-import.png)

1. Po dokončení importu vyberte Zařízení **Windows**  >    >  **Windows registrace**  >  **Zařízení**  >  **Synchronizovat.** Dokončení tohoto procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zaregistrované zařízení zobrazit, vyberte **Aktualizovat.**  

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

### <a name="6-create-a-deployment-profile"></a>6. Vytvoření profilu nasazení

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení   >  **Windows** Windows  >  **a** Windows nasazení  >  **Autopilotu** Vytvořte  >  **profil**  >  **HoloLens**.
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
     > Pokud použijete šablonu názvu zařízení, proces OOBE restartuje zařízení ještě jednou po použití názvu zařízení a před jeho připojením ke službě Azure AD. Toto restartování umožňuje, aby se nový název projeví.  

   > [!div class="mx-imgBorder"]
   > ![Nakonfigurujte nastavení OOBE.](./images/hololens-ap-profile-oobe.png)

1. Po konfiguraci nastavení vyberte **Další.**
1. Na stránce **Značky** oboru můžete volitelně přidat značky oboru, které chcete pro tento profil použít. Další informace o značkách oboru najdete v tématu Použití řízení přístupu na základě role a značek [oboru pro distribuované IT](/mem/intune/fundamentals/scope-tags.md). Po dokončení vyberte **Další.**
1. Na stránce **Přiřazení v** části Přiřadit **k** vyberte **Vybrané skupiny.**
1. V **části VYBRANÉ SKUPINY** vyberte + Vybrat **skupiny, které se zahrnou.**
1. V seznamu **Vybrat skupiny** k zahrnutí vyberte skupinu zařízení, kterou jste vytvořili pro zařízení Autopilot HoloLens a pak vyberte **Další.**  
  
   Pokud chcete některé skupiny vyloučit, vyberte **Vybrat skupiny, které** chcete vyloučit, a vyberte skupiny, které chcete vyloučit.

   > [!div class="mx-imgBorder"]
   > ![Přiřazení skupiny zařízení k profilu](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stránce **Zkontrolovat a vytvořit** zkontrolujte nastavení a pak výběrem možnosti **Vytvořit** vytvořte profil.  

   > [!div class="mx-imgBorder"]
   > ![Zkontrolujte a vytvořte.](./images/hololens-ap-profile-summ.png)

### <a name="7-verify-the-esp-configuration"></a>7. Ověření konfigurace ESP

Stránka stavu registrace (ESP) zobrazuje stav úplného procesu konfigurace zařízení, který se spustí při prvním přihlášení spravovaného uživatele MDM k zařízení. Ujistěte se, že vaše konfigurace ESP vypadá podobně jako v následujícím příkladu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP.](./images/hololens-ap-profile-settings.png)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Ověření stavu profilu zařízení HoloLens zařízení

1. V Microsoft Endpoint Manager Admin Center vyberte Zařízení **Windows**  >    >  **Windows registraci**  >  **zařízení.**

1. Ověřte, že HoloLens uvedená zařízení a že jejich stav profilu je **Přiřazeno.**  

   > [!NOTE]  
   > Přiřazení profilu k zařízení může několik minut trvat.  

   > [!div class="mx-imgBorder"]
   > ![Přiřazení zařízení a profilu.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot pro HoloLens 2 uživatelské prostředí

Po dokončení výše uvedených pokynů vaši uživatelé HoloLens 2 projde následujícím prostředím a zřžou svá zařízení HoloLens zařízení:  

1. Prostředí Autopilotu vyžaduje přístup k internetu. K zajištění přístupu k internetu použijte jednu z následujících možností:

    - Připojení zařízení do Wi-Fi v prostředí OOBE a nechat ho automaticky detekovat prostředí Autopilotu. Je to jediný čas, kdy budete potřebovat pracovat s OOBE, dokud se prostředí Autopilot samo nedokoní. Upozorňujeme, že ve výchozím HoloLens 2 po zjištění internetu počká 10 sekund na rozpoznání Autopilotu. Pokud během 10 sekund není detekován žádný profil Autopilot, zobrazí se při jeho aktivaci eula. Pokud narazíte na tento scénář, restartujte zařízení, aby bylo možné udělat další pokus o rozpoznání Autopilotu. Upozorňujeme také, že funkce při neověřené aktivaci může čekat na Autopilot po neomezenou dobu pouze v případě, že je na zařízení nastavená zásada TenantLockdown.

    - Připojení připojit zařízení k síti Ethernet pomocí adaptérů USB-C na Ethernet pro připojení k drátovému internetu a nechat HoloLens 2 dokončit prostředí Autopilotu.

    - Připojení připojit zařízení pomocí adaptérů USB-C na Wi-Fi pro bezdrátové připojení k internetu a nechat HoloLens 2 dokončit prostředí Autopilotu automaticky.

        > [!IMPORTANT]  
       > Zařízení, která se pokoušejí Wi-Fi v OOBE pro Autopilot, musí být na [Windows Holographic verze 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > U zařízení, která používají ethernetové adaptéry, musíte zařízení připojit k síti před tím, než se spustí prostředí při spuštění počítače. Zařízení určuje, jestli se na první obrazovce OOBE zřizuje jako zařízení Autopilot. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete zařízení zřídit jako zařízení Autopilot, nemůžete ho později změnit na Zřizování Autopilotu. Místo toho byste muset tento postup spustit znovu, abyste mohli zařízení zřídit jako zařízení Autopilot.

1. Zařízení by mělo automaticky spustit OOBE. Nereagovat na OOBE.

    > [!IMPORTANT]
    > Pokud chcete systém přenést do pohotovostního režimu nebo vypnutí, neaktivuje se prosím software při provozu ani nestiskne tlačítko napájení, zatímco probíhá Režim autopilotu. To může způsobit, že se tok Autopilotu dokončí.

   Nechte HoloLens 2 zjistit připojení k síti a povolit automatické dokončení spuštění počítače. Zařízení se může restartovat během spuštění počítače. Obrazovky OOBE by měly vypadat podobně jako na následujícím příkladu.

   ![OOBE krok 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE krok 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE krok 3.](./images/autopilot-device-setup.jpg)

1. Na konci OOBE se k zařízení můžete přihlásit pomocí svého uživatelského jména a hesla.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a Autopilot

HoloLens 2 podporují TenantLockdown CSP od verze Windows Holographic verze 20H2. Tento CSP udržuje zařízení v tenantovi organizace tím, že je uzamyká pro tohoto tenanta, a to i přes resetování zařízení nebo koliázku.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, HoloLens 2 k registraci MDM pouze pomocí Autopilotu. Jakmile je u uzlu RequireNetworkInOOBE tenantaLockdown CSP nastavená hodnota true nebo false (původně nastavená) na HoloLens 2, zůstane tato hodnota v zařízení bez ohledu na kolísání, aktualizace operačního systému atd.

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

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou aktivní.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak pomocí Intune zrušit nastavení nastavení TenantLockdown RequireNetworkInOOBE HoloLens 2?

1. Odeberte HoloLens 2 ze skupiny zařízení, ke které byla dříve přiřazena konfigurace zařízení vytvořená výše.

1. Vytvořte vlastní konfigurační profil zařízení založený na OMA URI a jako RequireNetworkInOOBE zadejte false, jak je znázorněno níže.
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false prostřednictvím OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený v HoloLens po nastavení TenantLockdown na hodnotu true? 
OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown.

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Známé problémy a & omezení

- Zkoumáme problém, kdy instalace aplikace na základě kontextu zařízení nakonfigurovaná v MEM neplatí pro HoloLens. [Přečtěte si další informace o instalaci kontextu zařízení a kontextu uživatele.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Při nastavování Autopilotu přes Wi-Fi může dojít k instanci, kdy se profil Autopilotu při prvním vytvoření připojení k internetu nestáhne. V takovém případě se zobrazí licenční smlouva s koncovým uživatelem (EULA) a uživatel má možnost pokračovat v instalaci mimo Autopilot. Pokud chcete nastavení zopakovat pomocí Autopilotu, přestavte zařízení do režimu spánku, pak ho restartujte nebo restartujte a zkuste to znovu.
- Funkce "Převést všechna cílová zařízení na Autopilot" se v HoloLens nepodporuje.  

### <a name="troubleshooting"></a>Řešení potíží

Následující články mohou být užitečným zdrojem dalších informací a řešení potíží s Autopilotem. Mějte ale na paměti, že tyto články jsou založené na Windows 10 Desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [Řešení Windows problémů s registrací zařízení v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Konflikty zásad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro Autopilot

Pokud chcete poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pokud chcete podporu k registraci zařízení, obraťte se na prodejce nebo distributora.
- Pokud chcete obecné dotazy ohledně podpory Windows Autopilot nebo problémy, jako jsou přiřazení profilů, vytvoření skupin nebo ovládací prvky portálu MEM, obraťte se Microsoft Endpoint Manager [podporu.](/mem/get-support)  
- Pokud je vaše zařízení zaregistrované ve službě Autopilot a profil je přiřazený na portálu MEM, kontaktujte HoloLens [podporu](/hololens/) (viz karta Podpora). Otevřete lístek podpory, a pokud je to k dispozici, zahrřte snímky obrazovky a protokoly tím, že zachytáte [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnostické protokoly během spuštění zařízení.
- Pokud chcete nahlásit problém ze zařízení, použijte aplikaci Centrum Feedback ve vaší HoloLens. V Centrum Feedback vyberte **kategorii Enterprise Zařízení**  >  **pro správu.**
- Pokud chcete poskytnout obecnou zpětnou vazbu k Autopilotu pro HoloLens, můžete odeslat tento [průzkum.](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Možná už nebudete chtít používat zařízení pro Autopilot nebo registrovat zařízení do jiného tenanta. Pokud to chcete udělat, přečtěte si o odstranění zařízení[Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)