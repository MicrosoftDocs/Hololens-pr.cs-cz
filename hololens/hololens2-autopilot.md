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
ms.openlocfilehash: 7dbe77c8c5999d5be1a61ca9deaa8071d152c87a
ms.sourcegitcommit: d0c7bf5b055fa1fa8ac5562eef904583a655da99
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2021
ms.locfileid: "122782803"
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

    1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru "DeviceHash". Zkopírujte tento soubor na jednotku v počítači, kde k němu máte přístup později.  

       > [!IMPORTANT]  
       > Data v souboru CSV by měla používat následující formát záhlaví a čáry:
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

### <a name="6-create-a-deployment-profile"></a>6. vytvoření profilu nasazení

1. v [centru pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com)vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **Windows profily nasazení autopilotu**  >  **vytvořit profil**  >  **HoloLens**.
   ![rozevírací seznam vytvořit profil obsahuje položku HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Zadejte název a popis profilu a pak vyberte **Další**.  
   Měl by se zobrazit seznam, který obsahuje **HoloLens**. Pokud tato možnost není k dispozici, kontaktujte nás pomocí jedné z možností [zpětné vazby](hololens2-autopilot.md#feedback-and-support-for-autopilot) .

   > [!div class="mx-imgBorder"]
   > ![Přidat název a popis profilu](./images/hololens-ap-profile-name.png)

1. Na stránce spouštěné při **prvním spuštění počítače (OOBE)** je většina nastavení předem nakonfigurovaná, aby se pro toto vyhodnocení zjednodušilo počáteční nastavení. Volitelně můžete nakonfigurovat následující nastavení:  

   - **Jazyk (oblast)**: Vyberte jazyk pro OOBE. doporučujeme vybrat jazyk ze seznamu [podporovaných jazyků pro HoloLens 2](hololens2-language-support.md).
   - **Automaticky konfigurovat klávesnici**: aby se zajistilo, že klávesnice odpovídá vybranému jazyku, vyberte **Ano**.
   - **Použít šablonu názvu zařízení**: Pokud chcete automaticky nastavit název zařízení během spuštění OOBE, vyberte **Ano** a pak zadejte frázi šablony a zástupné symboly do pole **Zadejte název** , například zadejte předponu a `%RAND:4%` &mdash; zástupný text pro číslo se čtyřmi číslicemi.
     > [!NOTE]  
     > Pokud použijete šablonu názvu zařízení, proces OOBE znovu spustí zařízení ještě jednou, když se použije název zařízení a předtím, než se zařízení připojí k Azure AD. Tento restart umožní uplatnění nového názvu.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurace nastavení OOBE](./images/hololens-ap-profile-oobe.png)

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
   > ![Kontrola a vytvoření](./images/hololens-ap-profile-summ.png)

### <a name="7-verify-the-esp-configuration"></a>7. Ověřte konfiguraci protokolu ESP.

Stránka stavu registrace (ESP) zobrazuje stav kompletního procesu konfigurace zařízení, který se spustí, když se uživatel spravovaný MDM poprvé přihlásí do zařízení. Ujistěte se, že se konfigurace protokolu ESP podobá následujícímu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP](./images/hololens-ap-profile-settings.png)

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

    - Připojení zařízení do Wi-Fi sítě v OOBE a pak mu umožnit automatické rozpoznávání možností automatického pilotního nasazení. Toto je jediná doba, kterou budete potřebovat k interakci s OOBE, dokud se prostředí autopilotního projektu nedokončuje sami. všimněte si, že ve výchozím nastavení HoloLens 2 čeká 10 sekund na detekci automatického pilotního projektu po zjištění internetu. Pokud se během 10 sekund nezjistí žádný profil autopilotu, vytvoří se v počátečním souboru EULA. Pokud se setkáte s tímto scénářem, restartujte prosím zařízení, aby bylo možné zjistit automatický pilotní nasazení. Všimněte si také, že počáteční nastavení může na zařízení počkat na neomezenou dobu, jenom když je na zařízení nastavené zásady TenantLockdown.

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

   ![OOBE krok 1 ](./images/autopilot-welcome.jpg)
    ![ oobe krok 2 ](./images/autopilot-step-complete.jpg)
    ![ oobe krok 3](./images/autopilot-device-setup.jpg)

1. Na konci počátečního nastavení se můžete k zařízení přihlásit pomocí uživatelského jména a hesla.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a autopilot

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
   > ![Nastavení uzamčení klienta pomocí OMA-URI](images/hololens-tenant-lockdown.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení profil konfigurace zařízení.

1. nastavte jako člena zařízení HoloLens 2 skupinu vytvořenou v předchozím kroku a spusťte synchronizaci.  

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně nastavila. jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, projeví se aktivní účinky TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>jak zrušit nastavení RequireNetworkInOOBE TenantLockdown na HoloLens 2 pomocí intune?

1. odeberte HoloLens 2 ze skupiny zařízení, ve které byla výše vytvořená konfigurace zařízení dříve přiřazena.

1. Vytvořte vlastní konfigurační profil zařízení založený na identifikátoru URI OMA a zadejte hodnotu false pro RequireNetworkInOOBE, jak je znázorněno níže.
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
- funkce převést veškerou cílovou zařízení na autopilotu není v současnosti podporovaná HoloLens.  

### <a name="troubleshooting"></a>Řešení potíží

následující články můžou být užitečným prostředkem, abyste si mohli přečíst další informace a řešit problémy s výkonem pro autopilot, ale pamatujte na to, že tyto články jsou založené na Windows 10 desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [řešení potíží s registrací zařízení Windows v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – konflikty zásad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro autopilot

Chcete-li poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pro podporu registrace zařízení se obraťte na svého prodejce nebo distributora.
- u obecných dotazů na podporu týkající se Windows autopilotu nebo pro problémy, jako jsou přiřazení profilů, vytváření skupin nebo ovládací prvky pro pracovní portál, [kontaktujte podporu Microsoft Endpoint Manager](/mem/get-support)  
- pokud je zařízení zaregistrované do služby autopilot a profil se přiřadí na portále MEM, kontaktujte [podporu](/hololens/) HoloLens (viz karta podpora). Otevřete prosím lístek podpory a pokud je to možné, zahrňte snímky obrazovky a protokoly zachytáváním [offline diagnostických protokolů](hololens-diagnostic-logs.md#offline-diagnostics) během nastavování mimo prostředí (OOBE).
- Pokud chcete ohlásit problém ze zařízení, použijte aplikaci centra Feedback na vašem HoloLens. v centru pro zpětnou vazbu vyberte kategorii zařízení **pro správu Enterprise**  >   .
- pokud chcete získat obecnou zpětnou vazbu k autopilotu pro HoloLens, můžete odeslat tento [průzkum](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) .

## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Možná budete chtít, aby zařízení už nepoužívalo k autopilotu, nebo aby se vaše zařízení zaregistrovala v jiném tenantovi. Pokud to chcete provést, přečtěte si téma[Jak odstranit zařízení autopilotu.](/mem/autopilot/add-devices#delete-autopilot-devices)