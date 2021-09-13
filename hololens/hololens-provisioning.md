---
title: Konfigurace HoloLens pomocí zřizovacího balíčku (HoloLens)
description: Windows zřizování usnadňuje správcům IT konfiguraci zařízení koncových uživatelů bez vytváření bitové kopie.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032404"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Konfigurace HoloLens pomocí zřizovacího balíčku

[Windows zřizování usnadňuje](/windows/configuration/provisioning-packages/provisioning-packages) správcům IT konfiguraci zařízení koncových uživatelů bez vytváření bitové kopie. Windows Configuration Designer je nástroj pro konfiguraci imagí a nastavení modulu runtime, které se pak zabudují do zřizovacích balíčků.

Mezi konfigurace HoloLens, které můžete použít ve zřizovacím balíčku, patří:

- Upgrade na [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Nastavení místního účtu
- Nastavení Wi-Fi připojení
- Použití certifikátů na zařízení
- Povolení vývojářského režimu
- Ke konfiguraci bezobrazovkového režimu postupujte [podle podrobných pokynů.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Průvodce vytvořením HoloLens balíčku

Průvodce HoloLens vám pomůže nakonfigurovat následující nastavení ve zřizovacího balíčku:

- Upgrade na edici Enterprise

    > [!NOTE]
    > Tento způsob by se měl používat HoloLens zařízení 1. generace. Nastavení zřizovacího balíčku se použijí jenom v případě, že zřizovací balíček obsahuje licenci na upgrade edice na Windows Holographic for Business nebo pokud už je zařízení [upgradované na Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Konfigurace prvního HoloLens (OOBE)
- Konfigurace Wi-Fi sítě
- Registrace zařízení v Azure Active Directory nebo vytvoření místního účtu
- Přidání certifikátů
- Povolení vývojářského režimu
- Ke konfiguraci bezobrazovkového režimu postupujte [podle podrobných pokynů.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

> [!WARNING]
> Ke konfiguraci Windows pomocí Windows 10 musíte spustit Azure Active Directory Configuration Designer.

Zřizovací balíčky mohou zahrnovat pokyny a zásady pro správu, vlastní síťová připojení a zásady a další.

> [!TIP]
> Pomocí průvodce desktopem vytvořte balíček se společným nastavením a pak přepněte do rozšířeného editoru a přidejte další nastavení, aplikace, zásady atd.

## <a name="steps-for-creating-provisioning-packages"></a>Postup vytváření zřizovacích balíčků

1. **Možnost 1: Z** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). To zahrnuje HoloLens 2 možnosti.
2. **Možnost 2:** [Ze sady ADK (Windows Assessment and Deployment Kit) pro Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Pokud instalujete Windows Configuration Designer z Windows ADK,  v dialogovém okně Vyberte funkce, **které chcete** nainstalovat vyberte Návrhář konfigurace. Tato možnost nezahrnuje HoloLens 2.

> [!NOTE]
> Pokud víte, že budete používat offline počítač, který potřebuje přístup k nástroji Windows Configuration Designer, postupujte podle pokynů [offline app install(hololens-recovery.md#downloading-arc-without-using-the-app-store) pro Advanced Recovery Companion. Proveďte Windows Configuration Designer podle svého výběru. 

### <a name="2-create-the-provisioning-package"></a>2. Vytvoření zřizovacího balíčku

Pomocí nástroje Windows Configuration Designer vytvořte zřizovací balíček.

1. Otevřete Windows Configuration Designer (ve výchozím nastavení%windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Vyberte **Zřídit HoloLens zařízení.**

   ![Možnosti spuštění ICD.](images/icd-create-options-1703.png)

3. Zadejte název projektu a vyberte **Dokončit.**

4. Přečtěte si pokyny na **stránce Začínáme a** vyberte **Další.** Stránky pro zřizování desktopových aplikací vás projde následujícími kroky.
  
> [!IMPORTANT]
> Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a do souboru zřizovacího balíčku (.ppkg). I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, když už je nepotřebujete.

### <a name="configure-settings"></a>Konfigurace nastavení

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Přejděte na a vyberte soubor podnikové licence a upgradujte HoloLens edici.</br></br>Pokud chcete skrýt <strong>části</strong> prvního prostředí, můžete také přepnout ano nebo ne. <strong></strong></br></br>Pokud chcete nastavit zařízení bez nutnosti připojovat se k Wi-Fi síti, přepněte Přeskočit nastavení <strong>Wi-Fi</strong> na <strong>Zapnout.</strong></br></br>Vyberte oblast a časové pásmo, ve kterém se zařízení použije. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>V této části můžete zadat podrobnosti o bezdrátové síti Wi-Fi, ke které by se zařízení mělo automaticky připojit. Chcete-li to provést, vyberte V <strong>systému</strong>, zadejte SSID, typ sítě (<strong>Open</strong> nebo <strong>WPA2-Personal</strong>) a (pokud <strong>WPA2-Personal)</strong>heslo bezdrátové sítě.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Zařízení můžete zaregistrovat v Azure Active Directory nebo na zařízení vytvořit místní účet.</br></br>Než použijete průvodce Windows Konfigurace konfigurace ke konfiguraci hromadné registrace Azure AD, nastavte připojení ke službě <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD ve vaší organizaci.</a> Maximální <strong>počet zařízení na uživatelské</strong> nastavení v tenantovi Azure AD určuje, kolikrát se může hromadný token, který získáte v průvodci, použít. Pokud chcete zaregistrovat zařízení ve službě Azure AD, vyberte tuto možnost a zadejte popisný název hromadného tokenu, který získáte pomocí průvodce. Nastavte datum vypršení platnosti tokenu (maximálně 30 dnů od data, kdy token získáte). Vyberte <strong>Získat hromadný token</strong>. V <strong>okně&#39;přihlášení</strong> zadejte účet, který má oprávnění k připojení zařízení ke službě Azure AD, a pak heslo. Vyberte <strong>Přijmout,</strong> abyste Windows Configuration Designeru potřebná oprávnění. </br></br>Pokud chcete vytvořit místní účet, vyberte tuto možnost a zadejte uživatelské jméno a heslo. </br></br><strong>Důležité:</strong> <br />(Pouze Windows 10 verze 1607) Pokud v zřizovacím balíčku vytvoříte místní účet, musíte každých 42 dnů změnit heslo pomocí <strong>Nastavení</strong> aplikace. Pokud během tohoto období heslo nezměníte, může být účet uzamčený a nebude se možné přihlásit.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pokud chcete pro zařízení zřídit certifikát, klikněte <strong>na Přidat certifikát.</strong> Zadejte název certifikátu, přejděte na adresu a vyberte certifikát, který se má použít.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Přepnutím <strong>ano</strong> nebo <strong>ne</strong> povolte vývojářský režim na HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Přečtěte si další informace o režimu pro vývojáře.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Nenastavovat heslo pro ochranu zřizovacího balíčku. Pokud je zřizovací balíček chráněný heslem, zřízení HoloLens zařízení selže.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Až budete hotovi, vyberte **Vytvořit.** Trvá to jenom pár sekund. Při sestavě balíčku se umístění, kde je balíček uložený, zobrazí jako hypertextový odkaz v dolní části stránky.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Vytvoření zřizovacího balíčku pro HoloLens pomocí pokročilého zřizování

> [!NOTE]
> Zřizovací balíček,  který vytvoříte v rozšířeném zřizování, nemusí zahrnovat licenci na upgrade edice na Windows Holographic for Business, aby se úspěšně aplikuje na HoloLens (1. generace). [Další informace o Windows Holographic for Business najdete HoloLens (1. generace).](hololens1-upgrade-enterprise.md)

1. Na úvodní Windows Návrháře konfigurace vyberte **Rozšířené zřizování.**
2. V **okně Zadejte podrobnosti** projektu zadejte název projektu a umístění projektu. Volitelně můžete zadat stručný popis projektu.

3. Vyberte **Další**.

4. V okně Zvolte nastavení k zobrazení a **konfiguraci** vyberte **Windows 10 Holographic** a pak vyberte **Další.**

5. Vyberte **Dokončit**.

6. Rozbalte **položku Nastavení** modulu runtime a přizpůsobte balíček pomocí libovolného nastavení [popsaného dále v tomto článku.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Pouze Windows 10 verze 1607) Pokud v zřizovacím balíčku vytvoříte místní účet, musíte každých 42 dnů změnit heslo pomocí **Nastavení** aplikace. Pokud během tohoto období heslo nezměníte, může být účet uzamčený a nebude se možné přihlásit. Pokud je uživatelský účet uzamčený, musíte [provést úplné obnovení zařízení.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Vyberte **Soubor**  >  **Uložit.**

8. Přečtěte si upozornění, že soubory projektu mohou obsahovat citlivé informace, a vyberte **OK.**

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a do souboru zřizovacího balíčku (.ppkg). I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, když už je nepotřebujete.

9. Vyberte **Exportovat**  >  **zřizovací balíček.**

10. Změňte **Vlastníka** na **Správce IT.** Tím se nastaví priorita tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů. Vyberte **Další**.

11. Nastavte hodnotu pro **Package Version (Verze balíčku).**

    > [!TIP]
    > Můžete provádět změny existujících balíčků a změnit číslo verze tak, aby se dříve použité balíčky aktualizují.

12. V části **Vyberte podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další.**

    > [!WARNING]
    > Pokud zašifrujete zřizovací balíček, zřízení HoloLens zařízení selže.  

13. Vyberte **Další** a zadejte výstupní umístění, kam má zřizovací balíček po jeho vytváření přejít. Ve výchozím nastavení Windows Configuration Designer používá složku projektu jako výstupní umístění.

    Volitelně můžete vybrat možnost **Procházet** a změnit výchozí umístění výstupu.

14. Vyberte **Další**.

15. Vyberte **sestavení** pro zahájení sestavování balíčku. Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu indikuje stav sestavení.

16. Po dokončení sestavení vyberte **Dokončit**.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>použití zřizovacího balíčku pro HoloLens během instalace

zařízení HoloLens 2 Windows holografická verze 2004 nebo build [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) nebo novější může použít jednotku USB k použití zřizovacího balíčku. Jednoduše zkopírujte soubor. ppkg do kořenového adresáře jednotky USB. Zřizovací balíčky se použijí jenom v případě, že jsou v kořenu jednotky USB. K dispozici je více zřizovacích balíčků postupně.

HoloLens 2 zařízení [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo novější mají novější funkce, které vám pomůžou tento proces automaticky zjednodušit a zjednodušit. Přečtěte si prosím následující oddíly:

- [Automatické spuštění zřizování z USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatické potvrzení zřizovacích balíčků v OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatické zřizování bez použití uživatelského rozhraní](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. pomocí kabelu USB připojte zařízení k počítači (nebo k jednotce USB pro HoloLens 2, jak je uvedeno výše), a pak zařízení spusťte. Nepokračujte za první možné nefungující **momentně** na stránce OOBE.
    - na HoloLens (1. generace) tato stránka obsahuje modrý rámeček.
    - na HoloLens 2 tato stránka obsahuje hummingbird.

2. Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** současně.

3. HoloLens se v průzkumníku souborů na počítači zobrazí jako zařízení.

4. V Průzkumníku souborů přetáhněte zřizovací balíček (. ppkg) do úložiště zařízení.

5. Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** , a to na první funkční stránce počátečního **momentu** pro počáteční práci.

6. Zařízení vás vyzve k tomu, kdybyste balíček důvěřovali a chtěli byste ho použít. Potvrďte, že balíček důvěřujete.

7. Zobrazí se informace o tom, zda byl balíček úspěšně použit, nebo nikoli. Pokud se nezdařila, můžete balíček opravit a akci opakujte. Pokud bylo úspěšné, pokračujte v operaci OOBE.

> [!NOTE]
> Pokud se zařízení zakoupilo před 2016. srpna, budete se muset k zařízení přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a potom obnovit operační systém, aby se balíček pro zřizování použil.

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňují menší interakci s uživatelem, když se při počátečním spuštění počítače použijí jednotky USB s Zřizovacími balíčky.

Předtím, než uživatelé této verze museli při zřizování pomocí kombinace tlačítek znovu spustit zřizování obrazovky během vytváření POČÁTEČNÍch hodnot. Uživatelé teď můžou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na USB paměťové jednotce.

1. Připojte se k jednotce USB pomocí zřizovacího balíčku během prvního prozatím Provisioning OOBE
1. Když je zařízení připravené k zřízení, automaticky se otevře výzva se stránkou zřizování.

Poznámka: Pokud se jednotka USB v době, kdy se zařízení spouští, dokončí, vytvoří OOBE výčet existujícího úložného zařízení USB a sledujte další zařízení, která jsou zapojená do sítě.

Přečtěte si o [použití zřizovacích balíčků během OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacích balíčků v OOBE
- Automatizovaný proces – při zobrazení stránky zřizovacího balíčku se automaticky použije všechny uvedené balíčky.

Když se objeví hlavní obrazovka zřizování, počáteční čas se bude počítat 10 sekund, než se automaticky začnou používat všechny zřizovací balíčky. Po ověření balíčků, které se očekávají, můžou uživatelé tuto dobu 10 sekund potvrdit i zrušit.

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní
- Kombinované automatické procesy pro zajištění omezeného počtu interakcí zařízení pro zřizování. 

díky kombinaci automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovacích balíčků může uživatel zřídit zařízení HoloLens 2 automaticky bez použití uživatelského rozhraní zařízení nebo dokonce zařízení. Můžete nadále používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení několika zařízení najednou ve stejné oblasti. 

1. [vytvořte zřizovací balíček](hololens-provisioning.md) pomocí [návrháře konfigurace Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Flash HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) až [19041,1361 nebo novější sestavení](https://aka.ms/hololens2previewdownload). 
1. Až [Průvodce pokročilým obnovením](https://www.microsoft.com/store/productId/9P74Z35SFRS8) dokončí blikání vašeho zařízení, odpojte kabel USB-C. 
1. Připojte jednotku USB k zařízení.
1. když se zařízení HoloLens 2 spustí do režimu OOBE, automaticky rozpozná zřizovací balíček na jednotce USB a spustí stránku zřizování.
1. Po 10 sekundách bude zařízení automaticky používat zřizovací balíček. 

Vaše zařízení je teď nakonfigurované a zobrazí se úspěšná obrazovka zřizování.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>použít nebo odebrat zřizovací balíček pro HoloLens po instalaci

> [!NOTE]
> tyto kroky se vztahují na všechna zařízení HoloLens 2 a HoloLens (1. generace) na Windows holografické verzi 1809 a vyšší.

V počítači použijte následující postup:
1. vytvořte zřizovací balíček, jak je popsáno v tématu [vytvoření zřizovacího balíčku pro HoloLens pomocí průvodce HoloLens](hololens-provisioning.md).
2. Připojení HoloLens zařízení k počítači pomocí kabelu USB. HoloLens se v průzkumníku souborů na počítači zobrazí jako zařízení.
3. Přetáhněte zřizovací balíček do složky Dokumenty na HoloLens.

v HoloLens postupujte podle následujících kroků:
1. přejděte na **Nastavení**  >  **účty**  >  **přístup do práce nebo do školy**. 
2. v **seznamu související Nastavení** vyberte **přidat nebo odebrat zřizovací balíček**.
3. Na další stránce vyberte **Přidat balíček** a spusťte tak výběr souboru a vyberte balíček zřizování. Pokud je složka prázdná, ujistěte se, že jste vybrali **Toto zařízení** a vyberete **dokumenty**.

Po použití balíčku se zobrazí v seznamu **nainstalovaných balíčků**. Pokud chcete zobrazit podrobnosti balíčku nebo odebrat balíček ze zařízení, vyberte uvedený balíček.

## <a name="what-you-can-configure"></a>Co můžete konfigurovat

Zřizovací balíčky využívají poskytovatele konfiguračních služeb (CSP). Pokud nejste obeznámeni s CSP, přečtěte si téma [Úvod do poskytovatele konfiguračních služeb (CSP) pro odborníky v oblasti IT](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

v návrháři konfigurace Windows při vytváření zřizovacího balíčku pro Windows holografickou jsou nastavení v **dostupných úpravách** založená na [csp, které jsou podporovány v Windows holografickém](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). Následující tabulka popisuje nastavení, která můžete chtít nakonfigurovat pro HoloLens.

![Běžné nastavení modulu runtime pro HoloLens.](images/icd-settings.png)

| Nastavení | Popis |
| --- | --- |
| **Certifikáty** | Nasaďte certifikát pro HoloLens.  |
| **ConnectivityProfiles** | Nasaďte profil Wi-Fi pro HoloLens.   |
| **Upgrade edice** | [Upgradujte na Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Zásady** | Povolí nebo zakáže vývojářský režim na HoloLens. [Zásady podporované Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalace aplikace prostřednictvím zřizovacího balíčku

aplikace se dají instalovat prostřednictvím zřizovacích balíčků na zařízeních HoloLens 2. Díky tomu je možné snadno opakovaně použitelný balíček, který vám pomůže distribuovat aplikace. Přečtěte si kompletní pokyny pro [nasazení aplikací prostřednictvím zřizovacích balíčků](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1. generace) má omezené podpory pro instalaci aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku. zařízení HoloLens (1. generace) podporují jenom instalaci aplikace přes PPKG jenom během spuštění OOBE a jenom s instalací kontextu uživatele.
