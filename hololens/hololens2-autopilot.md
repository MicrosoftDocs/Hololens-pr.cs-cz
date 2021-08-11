---
title: Windows Autopilot pro HoloLens 2
description: Zjistěte, jak nastavit, nakonfigurovat a řešit potíže s Autopilotem na HoloLens 2.
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
keywords: Autopilota
manager: jarrettr
ms.openlocfilehash: 7438b147a31ff38233412a4213a568286fb2e3b8982bc4fd6af3f9dde842fd1a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662429"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot pro HoloLens 2

> [!NOTE]
> Konfigurace Autopilotu pro HoloLens v Microsoft Endpoint Manager přechází z **Public Preview** **na všeobecnou dostupnost.** Autopilot budou moct nastavit všichni tenanti v Centru pro správu MEM.

Počínaje Windows Holographic verze 2004 podporuje HoloLens 2 režim automatického nasazení Windows [Autopilotu](/mem/autopilot/self-deploying) s Microsoft Intune (mdm třetích stran se nepodporuje). Správci můžou v systému Microsoft Endpoint Manager nakonfigurovat prostředí pro první použití a umožnit koncovým uživatelům připravovat zařízení pro obchodní použití s malými nebo žádnými interakcemi. Tím se sníží režijní náklady na správu inventáře, náklady na přípravu zařízení a volání na podporu od zaměstnanců během nastavování. Další informace najdete v [Windows Autopilot.](/mem/autopilot/windows-autopilot)

Stejně jako u zařízení Surface se doporučuje, aby zákazníci ve společnosti Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (prodejce nebo distributor) prostřednictvím služby Autopilot zaregistrovali Partnerské centrum. Další metody registrace zařízení jsou [](/mem/autopilot/add-devices) uvedené v dokumentaci k přidání zařízení, ale využití kanálů partnerů Microsoftu zajišťuje nejúčinnější cestu od konce.



Když uživatel spustí proces samosazování Autopilotu, Autopilot dokončí následující kroky:

1. Připojte zařízení k Azure Active Directory (Azure AD). Autopilot pro HoloLens nepodporuje připojení ke službě Active Directory ani hybridní připojení k Azure AD.

1. Pomocí Azure AD zaregistrujte zařízení ve službě Microsoft Endpoint Manager (nebo jiné službě MDM).

1. Stáhněte a použijte zásady, certifikáty, síťové profily a aplikace cílené na zařízení.

1. Zřídit zařízení.

1. Zobrazí přihlašovací obrazovku uživateli.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurace Autopilotu pro HoloLens 2

Při nastavení prostředí postupujte následovně:

1. [Zkontrolujte požadavky na Windows Autopilot pro HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Povolení automatické registrace MDM](#2-enable-automatic-mdm-enrollment)

1. [Registrace zařízení v Windows Autopilotu.](#3-register-devices-in-windows-autopilot)

1. [Vytvořte skupinu zařízení.](#4-create-a-device-group)

1. [Vytvořte profil nasazení.](#5-create-a-deployment-profile)

1. [Ověřte konfiguraci stránky stavu registrace (ESP).](#6-verify-the-esp-configuration)

1. [Ověřte stav profilu zařízení HoloLens zařízení.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Kontrola požadavků na Windows Autopilot pro HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Projděte si následující části článku Windows Autopilot:

- [Požadavky sítě](/mem/autopilot/networking-requirements)  
- [Licenční požadavky](/mem/autopilot/licensing-requirements)  
- [Požadavky na konfiguraci](/mem/autopilot/configuration-requirements)

**V článku [o Windows](/windows/deployment/windows-autopilot/self-deploying#requirements)režimu Self-Deploying Autopilot si Self-Deploying požadavky.** Vaše prostředí musí splňovat tyto požadavky i standardní požadavky Windows Autopilot. V tomto článku si není muset prohlédněte oddíly "Krok za krokem" a "Ověření". Postupy dále v tomto článku poskytují odpovídající kroky, které jsou specifické pro HoloLens.

Informace o registraci zařízení a konfiguraci profilů najdete v části [2. Registrace zařízení v Windows Autopilot a](#3-register-devices-in-windows-autopilot) [4. V tomto článku vytvořte](#5-create-a-deployment-profile) profil nasazení. Pokud chcete konfigurovat a spravovat profily režimu automatického nasazení Autopilotu, ujistěte se, že máte přístup k [Microsoft Endpoint Manager pro správu.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Projděte HoloLens na operační systém:

- Zařízení musí být na [Windows Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) nebo novější. Pokud chcete ověřit verzi sestavení na vašem zařízení nebo znovu zobrazit flash disk na nejnovější verzi operačního systému, použijte [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) a naše zařízení znovu flash [pokyny.](/hololens/hololens-recovery#clean-reflash-the-device) Upozorňujeme, že zařízení dodaná do konce září 2020 Windows nainstalovaná verze Holographic 1903. Obraťte se na prodejce a ujistěte se, že vám budou dodána zařízení připravená pro Autopilot.

- Windows Holographic verze 2004 podporuje pouze připojení Autopilot přes ethernet. Než ho HoloLens, ujistěte se, že je připojený k síti ethernet pomocí adaptéru USB-C na **Ethernet.** Při spuštění zařízení není nutná žádná interakce uživatele. Pokud plánujete nasavit Autopilot do mnoha HoloLens zařízení, doporučujeme naplánovat infrastrukturu adaptéru. Rozbočovače USB nedoporučujeme, protože často vyžadují instalaci dalších ovladačů třetích stran, které nejsou podporované v HoloLens.

- [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) nebo novější podporují Autopilot přes Wi-Fi, i když můžete stále používat ethernetové adaptéry. U zařízení připojených přes Wi-Fi musí uživatel jenom:

     - Projít scénu s vlhmingbird
     - Volba jazyka a národního prostředí
     - Spuštění pohledu
     - Navázání síťového připojení

- Windows Holographic verze 20H2 podporuje [Tenantlockdown CSP a Autopilot,](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)které uzamknou zařízení k tenantovi a zajistí, aby zařízení zůstalo vázaná na tohoto tenanta v případě náhodného nebo úmyslného resetování nebo vymazání.  

- Ujistěte se, že zařízení ještě nejsou členy Azure AD a nejsou zaregistrovaná v Intune (nebo jiném systému MDM). Proces automatického nasazení Autopilotu dokončí tyto kroky. Pokud se chcete ujistit, že jsou všechny  informace související se zařízením vyčištěné, podívejte se na stránky Zařízení na portálech Azure AD i Intune. Upozorňujeme, že funkce Převést všechna cílová zařízení na Autopilot se v současné HoloLens nepodporuje.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Povolení automatické registrace MDM:

Aby byl Autopilot úspěšný, musíte ve svém virtuálním počítači povolit automatickou registraci MDM Azure Portal. Tím umožníte registraci zařízení bez uživatele.

V [Azure Portal](https://portal.azure.com/#home) vyberte **Azure Active Directory**  ->  **Mobility (MDM** a MAM)  ->  **Microsoft Intune**. Pak nakonfigurujte **obor uživatele MDM**, budete muset vybrat **Vše.**

Další informace o nastavení najdete v následujícím krátkém průvodci povolením automatické registrace [MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) nebo v průvodci rychlým zahájením automatické registrace. [](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

### <a name="3-register-devices-in-windows-autopilot"></a>3. Registrace zařízení v Windows Autopilotu

Vaše zařízení musí být před prvním nastavením zaregistrovaná Windows Autopilotu. Dokumentaci MEM k registraci zařízení najdete v tématu [Přidání zařízení do Autopilotu.](/mem/autopilot/add-devices)  

Existují tři hlavní způsoby registrace HoloLens zařízení:

 - **Prodejce může registrovat zařízení v Partnerské centrum při objednávce.**

   > [!NOTE]  
   > Toto je doporučená cesta pro přidání zařízení do služby Autopilot. [Další informace](/mem/autopilot/partner-registration).  

 - **Žádost o [podporu můžete odeslat přímo](hololens2-autopilot-registration-support.md) microsoftu.**
 - **Načtěte hodnotu hash hardwaru (označované** také jako ID hardwaru) a zaregistrujte zařízení ručně v Centru pro správu MEM.

#### <a name="obtain-hardware-hash"></a>Získání hodnoty hash hardwaru
Existují dva způsoby, jak načíst hodnotu hash hardwaru.
1. Žádost o [podporu můžete odeslat přímo](hololens2-autopilot-registration-support.md) microsoftu.
2. Můžete ho načíst ze zařízení. Zařízení zaznamená hodnotu hash hardwaru do souboru CSV během procesu OOBE nebo později, když vlastník zařízení spustí proces shromažďování diagnostických protokolů (popsaný v následujícím postupu). Vlastníkem zařízení je obvykle první uživatel, který se k zařízení přihlásí.
     > [!WARNING]
     > Pokud jste v buildech před 20H2 prošli OOBE a telemetrie byla nastavená na Požadováno, nemůžete touto metodou shromáždit hodnotu hash hardwaru pro Autopilot. Pokud chcete shromažďovat hodnoty hash hardwaru touto metodou, nastavte možnost telemetrie prostřednictvím aplikace Nastavení App na Full (Úplné) a vyberte Privacy -> Diagnostics (Ochrana osobních údajů – > Diagnostika).

    1. Spusťte HoloLens 2.

    1. Na zařízení současně stiskněte  **tlačítka Napájení** a Snížení hlasitosti a pak je uvolněte. Zařízení shromažďuje diagnostické protokoly a hodnoty hash hardwaru a ukládá je do sady .zip souborů.

   1. Úplné podrobnosti a instrukční video, jak to předem zformovat, najdete v tématu [Offline diagnostika.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Pomocí kabelu USB-C připojte zařízení k počítači.

    1. Na počítači otevřete Průzkumník souborů. Otevřete **soubor This PC Internal Storage \\ \<*HoloLens device name*> \\ \\ Documents** a vyhledejte AutopilotDiagnostics.zip počítače.  

       > [!NOTE]  
       > Soubor .zip nemusí být okamžitě dostupný. Pokud soubor ještě není připravený, může se ve složce Documents zobrazit soubor HoloLensDiagnostics.temp. Pokud chcete aktualizovat seznam souborů, aktualizujte okno.
    
    1. Extrahujte obsah AutopilotDiagnostics.zip souboru.

    1. V extrahovaných souborech vyhledejte soubor CSV s předponou názvu souboru DeviceHash. Zkopírujte tento soubor na jednotku v počítači, kde k ní budete později mít přístup.  

       > [!IMPORTANT]  
       > Data v souboru CSV by měla používat následující hlavičku a formát řádku:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Registrace zařízení prostřednictvím MEM

1. V [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com)vyberte Zařízení Windows Windows registrace a pak v části Windows Autopilot Deployment Program vyberte  >    >     >   **Import zařízení.**

1. V **části Windows zařízení Autopilot** vyberte soubor CSV DeviceHash, vyberte **Otevřít** a pak vyberte **Importovat.**  

   > [!div class="mx-imgBorder"]
   > ![Pomocí příkazu Import importujte hodnotu hash hardwaru.](./images/hololens-ap-hash-import.png)

1. po dokončení importu vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **zařízení**  >  . Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje. Pokud chcete zobrazit registrované zařízení, vyberte **aktualizovat**.  

   > [!div class="mx-imgBorder"]
   > ![K zobrazení seznamu zařízení použijte příkazy synchronizovat a aktualizovat.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Vytvoření skupiny zařízení

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

### <a name="5-create-a-deployment-profile"></a>5. vytvoření profilu nasazení

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

### <a name="6-verify-the-esp-configuration"></a>6. Ověřte konfiguraci protokolu ESP.

Stránka stavu registrace (ESP) zobrazuje stav kompletního procesu konfigurace zařízení, který se spustí, když se uživatel spravovaný MDM poprvé přihlásí do zařízení. Ujistěte se, že se konfigurace protokolu ESP podobá následujícímu, a ověřte, že jsou přiřazení správná.  

> [!div class="mx-imgBorder"]
> ![Konfigurace ESP](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. ověřte stav profilu HoloLens zařízení

1. v centru pro správu Microsoft Endpoint Manager vyberte **zařízení**  >  **Windows**  >  **Windows registrace**  >  **zařízení**.

1. ověřte, že jsou v seznamu uvedená zařízení HoloLens a že jsou jejich stav profilu **přiřazený**.  

   > [!NOTE]  
   > Přiřazení profilu k zařízení může trvat několik minut.  

   > [!div class="mx-imgBorder"]
   > ![Přiřazení zařízení a profilu.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows autopilot pro HoloLens 2 – uživatelské prostředí

po dokončení výše uvedených pokynů se uživatelům HoloLens 2 při zřizování svých HoloLensch zařízení projdou tyto možnosti:  

1. Prostředí autopilotu vyžaduje přístup k Internetu. K poskytnutí přístupu k Internetu použijte prosím jednu z následujících možností:

    - Připojení zařízení do Wi-Fi sítě v OOBE a pak mu umožnit automatické rozpoznávání možností automatického pilotního nasazení. Toto je jediná doba, kterou budete potřebovat k interakci s OOBE, dokud se prostředí autopilotního projektu nedokončuje sami. všimněte si, že ve výchozím nastavení HoloLens 2 čeká 10 sekund na detekci automatického pilotního projektu po zjištění internetu. Pokud se během 10 sekund nezjistí žádný profil autopilotu, vytvoří se v počátečním souboru EULA. Pokud se setkáte s tímto scénářem, restartujte prosím zařízení, aby bylo možné zjistit automatický pilotní nasazení. Upozorňujeme také, že počáteční nastavení může pro TenantLockdown počkat na neomezenou dobu jenom v případě, že je na zařízení nastavené zásady.

    - Připojení zařízení pomocí sítě ethernet s použitím adaptérů USB-C do sítě ethernet pro drátové připojení k internetu a nechte HoloLens 2 dokončit automatické pilotní prostředí.

    - Připojení zařízení pomocí adaptérů USB-C do wi-fi pro bezdrátové připojení k internetu a nechte HoloLens 2 dokončit automatické pilotní prostředí.

        > [!IMPORTANT]  
       > zařízení, která se pokoušejí použít Wi-Fi sítě v OOBE pro autopiloter, musí být v [Windows holografická verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Pro zařízení, která používají adaptéry Ethernet, je nutné zařízení připojit k síti před spuštěním nástroje pro počáteční prostředí (OOBE). Zařízení určí, jestli se na první obrazovce OOBE zřídí jako zařízení s autopilotem. Pokud se zařízení nemůže připojit k síti nebo pokud se rozhodnete nezřídit zařízení jako zařízení autopilotu, nemůžete ho později změnit na autopilot. Místo toho byste museli spustit tento postup za účelem zřízení zařízení jako zařízení s autopilotem.

1. Zařízení by mělo automaticky spustit počáteční soubor. Nepoužívejte interakci s OOBE. Místo toho se nasaďte, vraťte se a uvolněte! umožněte HoloLens 2 detekci připojení k síti a umožněte automatickému dokončení souboru OOBE. Zařízení se může během POČÁTEČNÍho nastartu restartovat. Obrazovky OOBE by měly vypadat podobně jako následující.

   ![OOBE krok 1 ](./images/autopilot-welcome.jpg)
    ![ oobe krok 2 ](./images/autopilot-step-complete.jpg)
    ![ oobe krok 3](./images/autopilot-device-setup.jpg)

1. Na konci počátečního nastavení se můžete k zařízení přihlásit pomocí uživatelského jména a hesla.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP a autopilot

HoloLens 2 zařízení podporují zprostředkovatele CSP pro Windows holografickou verzi 20H2. Tento zprostředkovatel CSP udržuje zařízení v tenantovi organizace tím, že je zamkne do tohoto tenanta i přes resetování nebo reflash zařízení.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP umožňuje, aby HoloLens 2 byly vázané jenom na registraci MDM jenom pomocí autopilotu. jakmile se uzel RequireNetworkInOOBE poskytovatele TenantLockdown CSP nastaví na hodnotu true nebo false (zpočátku nastavená) na HoloLens 2, tato hodnota zůstane na zařízení i bez ohledu na to, jestli se jedná o opětovné spuštění, aktualizace operačního systému atd.

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
Hodnota OMA-URI by měla být ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s nastavením RequireNetworkInOOBE na hodnotu false přes OMA URI v Intune](images/hololens-tenant-lockdown-false.png)

1. Vytvořte skupinu a přiřaďte k této skupině zařízení konfigurační profil zařízení. 

1. Napřed HoloLens 2 člena skupiny vytvořené v předchozím kroku a aktivujte synchronizaci.

Na portálu Intune ověřte, že se konfigurace zařízení úspěšně použila. Jakmile se tato konfigurace zařízení úspěšně použije na zařízení HoloLens 2, účinky tenantaLockdown budou neaktivní.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co by se stalo při OOBE, pokud profil Autopilotu není přiřazený v HoloLens po nastavení tenantaLockdown na hodnotu true? 
OOBE bude čekat po neomezenou dobu, než se profil Autopilot stáhne, a zobrazí se následující dialogové okno. Aby bylo možné odebrat účinky tenantaLockdown, musí být zařízení zaregistrované v původním tenantovi jenom pomocí Autopilotu a RequireNetworkInOOBE musí být nenastavované, jak je popsáno v předchozím kroku, než se odeberou omezení zavedená poskytovatelem csP TenantLockdown.

![Zobrazení v zařízení, kdy se na zařízení vynucuje zásada](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Známé problémy a & omezení

- Zkoumáme problém, kdy instalace aplikace na základě kontextu zařízení nakonfigurovaná v MEM se nevztahuje na HoloLens. [Přečtěte si další informace o instalaci kontextu zařízení a kontextu uživatele.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Při nastavování Autopilotu přes Wi-Fi může dojít k instanci, kdy se profil Autopilotu při prvním vytvoření připojení k internetu nestáhne. V takovém případě se zobrazí licenční smlouva s koncovým uživatelem (EULA) a uživatel má možnost pokračovat v instalaci mimo Autopilot. Pokud chcete nastavení zopakovat pomocí Autopilotu, přestavte zařízení do režimu spánku, pak ho restartujte nebo restartujte a zkuste to znovu.
- Funkce "Převést všechna cílová zařízení na Autopilot" se v HoloLens nepodporuje.  

### <a name="troubleshooting"></a>Poradce při potížích

Následující články mohou být užitečným zdrojem dalších informací a řešení potíží s Autopilotem. Mějte ale na paměti, že tyto články jsou založené na Windows 10 Desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [Řešení Windows problémů s registrací zařízení Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Konflikty zásad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Zpětná vazba a podpora pro Autopilot

Pokud chcete poskytnout zpětnou vazbu nebo nahlásit problémy, použijte jednu z následujících metod:

- Pokud chcete podporu k registraci zařízení, obraťte se na prodejce nebo distributora.
- Pokud chcete obecné dotazy ohledně podpory Windows Autopilot nebo problémy, jako jsou přiřazení profilů, vytvoření skupin nebo ovládací prvky portálu MEM, obraťte se Microsoft Endpoint Manager [podpory.](/mem/get-support)  
- Pokud je vaše zařízení zaregistrované ve službě Autopilot a profil je přiřazený na portálu MEM, kontaktujte HoloLens [podpory](/hololens/) (viz karta Podpora). Otevřete lístek podpory, a pokud je to k dispozici, zahrřte snímky obrazovky a protokoly tím, že zachytáte [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnostické protokoly během spuštění zařízení.
- Pokud chcete nahlásit problém ze zařízení, použijte aplikaci Centrum Feedback ve vaší HoloLens. V Centrum Feedback vyberte **kategorii Enterprise Zařízení pro**  >  **správu.**
- Pokud chcete poskytnout obecnou zpětnou vazbu k Autopilotu pro HoloLens, můžete odeslat tento [průzkum.](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Možná už nebudete chtít používat zařízení pro Autopilot nebo registrovat zařízení do jiného tenanta. Pokud to chcete udělat, přečtěte si o odstranění zařízení[Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)