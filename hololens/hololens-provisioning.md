---
title: konfigurace HoloLens pomocí zřizovacího balíčku (HoloLens)
description: Windows zřizování usnadňuje správcům it konfigurovat zařízení koncových uživatelů bez použití bitové kopie.
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
ms.openlocfilehash: d9a0901a916ec33c076eeae33b680406a45f7feefe82442da1f346e78bc9b383
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663571"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>konfigurace HoloLens pomocí zřizovacího balíčku

[Windows zřizování](/windows/configuration/provisioning-packages/provisioning-packages) usnadňuje správcům it konfigurovat zařízení koncových uživatelů bez použití bitové kopie. Windows Návrhář konfigurace je nástroj pro konfiguraci imagí a nastavení modulu runtime, která jsou pak integrovaná do zřizovacích balíčků.

některé konfigurace HoloLens, které můžete použít v zřizovacím balíčku, zahrnují následující:

- upgradovat na [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Nastavení místního účtu
- Nastavení Wi-Fiho připojení
- Použít certifikáty pro zařízení
- Povolit vývojářský režim
- Pomocí [podrobných pokynů](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)nakonfigurujte celoobrazovkový režim.

## <a name="provisioning-package-hololens-wizard"></a>průvodce zřizovacím balíčkem HoloLens

průvodce HoloLens vám pomůže nakonfigurovat následující nastavení v balíčku zřizování:

- Upgrade na edici Enterprise

    > [!NOTE]
    > ta by se měla používat jenom pro HoloLens 1. generace zařízení. Nastavení v zřizovacím balíčku se použijí jenom v případě, že zřizovací balíček zahrnuje licenci pro upgrade edice Windows Holographic for Business nebo jestli [je zařízení už upgradované na Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- nakonfigurovat první prostředí HoloLens (OOBE)
- Konfigurace Wi-Fi sítě
- registrace zařízení v Azure Active Directory nebo vytvoření místního účtu
- Přidat certifikáty
- Povolit vývojářský režim
- Pomocí [podrobných pokynů](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)nakonfigurujte celoobrazovkový režim.

> [!WARNING]
> pro konfiguraci Azure Active Directory registrace pomocí některého z průvodců je nutné spustit Windows návrháře konfigurace na Windows 10.

Zřizovací balíčky můžou zahrnovat pokyny a zásady správy, vlastní síťová připojení a zásady a další.

> [!TIP]
> Pomocí Průvodce plochou vytvořte balíček se společným nastavením a pak přepněte do rozšířeného editoru a přidejte další nastavení, aplikace, zásady atd.

## <a name="steps-for-creating-provisioning-packages"></a>Postup vytváření zřizovacích balíčků

1. **Možnost 1:** [z Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). to zahrnuje možnosti HoloLens 2.
2. **možnost 2:** [v sadě Windows Assessment and Deployment Kit (ADK) pro Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). pokud instalujete Windows configuration designeru z Windows ADK, vyberte **návrhář konfigurace** v dialogovém okně **vyberte funkce, které chcete nainstalovat** . tato možnost nezahrnuje možnosti HoloLens 2.

> [!NOTE]
> pokud víte, že budete používat počítač v režimu offline, který potřebuje přístup k nástroji Windows Configuration Designer, postupujte podle pokynů v tématu [instalace offline aplikace (hololens-recovery. md # downloaded-arc-bez použití-the-app-store) pro pokročilého průvodce obnovením. zpřístupněte Windows návrháře konfigurace. 

### <a name="2-create-the-provisioning-package"></a>2. vytvoření zřizovacího balíčku

k vytvoření zřizovacího balíčku použijte nástroj Windows Configuration Designer.

1. otevřete Windows configuration Designer (ve výchozím nastavení soubory%windir%\Program (x86) \ Windows Kits\10\Assessment a nasazení Kit\Imaging a Configuration Designer\x86\ICD.exe).

2. vyberte možnost **zřídit HoloLens zařízení**.

   ![Možnosti zahájení ICD](images/icd-create-options-1703.png)

3. Pojmenujte projekt a vyberte **Dokončit**.

4. Přečtěte si pokyny na stránce **Začínáme** a vyberte **Další**. Stránky pro zřizování desktopu vás provedou následujícími kroky.
  
> [!IMPORTANT]
> Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a do souboru zřizovacího balíčku (. ppkg). I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, když už je nepotřebujete.

### <a name="configure-settings"></a>Konfigurace nastavení

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>chcete-li upgradovat edici HoloLens, vyhledejte a vyberte licenční soubor enterprise.</br></br>Můžete také přepnout možnost <strong>Ano</strong> nebo <strong>ne</strong> a skrýt části prvního prostředí.</br></br>Pokud chcete zařízení nastavit bez nutnosti připojení k Wi-Fi síti, přepněte <strong>Nastavení přeskočit Wi-Fi nastavení</strong> na <strong>zapnuto</strong>.</br></br>Vyberte oblast a časové pásmo, ve kterém se bude zařízení používat. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>V této části můžete zadat podrobnosti o Wi-Fi bezdrátové sítě, ke které se má zařízení automaticky připojit. Provedete to tak, že vyberete <strong>zapnuto</strong>, zadáte identifikátor SSID, typ sítě (<strong>Open</strong> nebo <strong>WPA2-Personal</strong>) a (Pokud <strong>WPA2-osobní</strong>) heslo bezdrátové sítě.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>zařízení můžete zaregistrovat v Azure Active Directory nebo na zařízení vytvořit místní účet.</br></br>než použijete průvodce Windows Configuration Designer ke konfiguraci hromadné registrace azure ad, <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">nastavte v organizaci připojení k azure ad</a>. Nastavení <strong>maximální počet zařízení na uživatele</strong> v TENANTOVI Azure AD určuje, kolikrát se dá Hromadná token, který v průvodci dostanete, použít. Pokud chcete zařízení zaregistrovat v Azure AD, vyberte tuto možnost a zadejte popisný název hromadného tokenu, který budete používat v průvodci. Nastavte datum vypršení platnosti tokenu (maximálně 30 dní od data, kdy získáte token). Vyberte <strong>získat hromadnou token</strong>. V okně <strong>dovolit&#39;s přihlašováním</strong> zadejte účet, který má oprávnění k připojení zařízení ke službě Azure AD, a pak heslo. vyberte <strong>přijmout</strong> a poskytněte Windows Configuration designeru potřebná oprávnění. </br></br>Chcete-li vytvořit místní účet, vyberte tuto možnost a zadejte uživatelské jméno a heslo. </br></br><strong>Významná</strong> <br />(pouze pro Windows 10 verze 1607) pokud vytvoříte místní účet v zřizovacím balíčku, musíte změnit heslo pomocí aplikace <strong>Nastavení</strong> každých 42 dní. Pokud se heslo během této doby nezměnilo, může být účet uzamčen a nelze se přihlásit.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pokud chcete zařízení zřídit s certifikátem, klikněte na <strong>Přidat certifikát</strong>. Zadejte název certifikátu a pak vyhledejte a vyberte certifikát, který se má použít.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Přepínač <strong>Ano</strong> nebo <strong>ne</strong> pro povolení režimu vývojářů na HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Přečtěte si další informace o vývojářském režimu.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Nenastavujte heslo pro ochranu zřizovacího balíčku. pokud je zřizovací balíček chráněný heslem, zřizování zařízení HoloLens se nezdaří.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Až budete hotovi, vyberte **vytvořit**. Trvá to jenom několik sekund. Po sestavení balíčku se v dolní části stránky zobrazí umístění, kde je balíček uložený.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. vytvoření zřizovacího balíčku pro HoloLens s využitím pokročilého zřizování

> [!NOTE]
> zřizovací balíček, který vytvoříte v rámci **pokročilého zřizování** , nemusí zahrnovat licenci pro upgrade edice Windows Holographic for Business, aby se mohl úspěšně vztahovat na HoloLens (1. generace). [další informace najdete v Windows Holographic for Business HoloLens (1. generace)](hololens1-upgrade-enterprise.md).

1. na úvodní stránce Windowsho návrháře konfigurace vyberte **rozšířené zřizování**.
2. V okně **Zadejte podrobnosti projektu** zadejte název projektu a umístění projektu. Volitelně můžete zadat stručný popis pro popis projektu.

3. Vyberte **Další**.

4. v okně **zvolte, která nastavení se mají zobrazit a konfigurovat** vyberte **Windows 10 Holographic** a pak vyberte **další**.

5. Vyberte **Dokončit**.

6. Rozbalte položku **nastavení modulu runtime** a přizpůsobte balíček pomocí některého z nastavení [popsaných dále v tomto článku](#what-you-can-configure).

    > [!IMPORTANT]
    > (pouze pro Windows 10 verze 1607) pokud vytvoříte místní účet v zřizovacím balíčku, musíte změnit heslo pomocí aplikace **Nastavení** každých 42 dní. Pokud se heslo během této doby nezměnilo, může být účet uzamčen a nelze se přihlásit. Pokud je uživatelský účet uzamčený, je nutné [provést úplné obnovení zařízení](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery).

7. Vyberte   >  **Uložit** soubor.

8. Přečtěte si upozornění, že soubory projektu můžou obsahovat citlivé informace, a vyberte **OK**.

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a do souboru zřizovacího balíčku (. ppkg). I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, když už je nepotřebujete.
    
9. Vyberte **exportovat**  >  **zřizovací balíček**.

10. Změňte **vlastníka** na **správce IT**. Tím se nastaví priorita tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů. Vyberte **Další**.

11. Nastavte hodnotu pro **verzi balíčku**.

    > [!TIP]
    > Můžete provádět změny stávajících balíčků a změnit číslo verze na aktualizace dřív použitých balíčků.

12. V části **Vybrat podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další**.

    > [!WARNING]
    > pokud zašifrujete zřizovací balíček, zřizování zařízení HoloLens se nezdaří.  

13. Výběrem možnosti **Další** zadejte umístění výstupu, kde má zřizovací balíček přejít po sestavení. ve výchozím nastavení používá návrhář konfigurace Windows složku projektu jako umístění výstupu.

    Volitelně můžete vybrat Procházet **a** změnit výchozí umístění výstupu.

14. Vyberte **Další**.

15. Vyberte **Build (Sestavit)** a začněte vytvářet balíček. Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu označuje stav sestavení.

16. Po dokončení sestavení vyberte **Dokončit.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Použití zřizovacího balíčku pro HoloLens během instalace

HoloLens 2 zařízení na zařízeních Windows Holographic verze 2004 nebo [buildu 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) nebo novějším může ke zřízení balíčku použít USB flash disk. Jednoduše zkopírujte soubor .ppkg do kořenového adresáře jednotky USB. Zřizovací balíčky se použijí jenom v případě, že jsou v kořenovém adresáři JEDNOTKY USB. Několik přítomných zřizovacího balíčku se použije postupně.

HoloLens 2 zařízení na Windows Holographic verze [20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo novější mají novější funkce, které vám pomůžou zjednodušit a zjednodušit automatický proces. Projděte si následující části:

- [Automatické spuštění zřizování z USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatické potvrzení zřizovacího balíčku v OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatické zřizování bez použití uživatelského rozhraní](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Pomocí kabelu USB připojte zařízení k počítači (nebo k jednotce USB pro HoloLens 2, jak je uvedeno výše), a pak zařízení spusťte. Neposíít se přes **stránku Prvního interagovatelného okamžiku** prvního zařízení.   
    - V HoloLens (1. generace) obsahuje tato stránka modrý rámeček. 
    - Na HoloLens 2 obsahuje tato stránka balíček vousů.

2. Krátce stiskněte a **uvolněte tlačítka Pro snížení** hlasitosti a Napájení současně.  

3. HoloLens se zobrazí jako zařízení v Průzkumník souborů počítači.

4. V Průzkumník souborů přetáhněte zřizovací balíček (.ppkg) do úložiště zařízení.

5. Krátce znovu stiskněte a uvolněte tlačítka **Volume Down** (Snížení hlasitosti) a **Power (Napájení)** na stránce **Prvního** interakce při prvním zapnutí zařízení.

6. Zařízení se vás zeptá, jestli balíčku důvěřujete, a chcete ho použít. Ověřte, že balíčku důvěřujete.

7. Uvidíte, jestli se balíček úspěšně použil, nebo ne. Pokud se to nepovedlo, můžete balíček opravit a zkusit to znovu. Pokud byla úspěšná, pokračujte s OOBE.

> [!NOTE]
> Pokud bylo zařízení zakoupeno před srpnem 2016, budete se k zařízení muset přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a pak resetovat operační systém, abyste mohli použít zřizovací balíček.

### <a name="auto-launch-provisioning-from-usb"></a>Automatické spuštění zřizování z USB

- Automatizované procesy umožňující menší interakci uživatelů, když se během spuštění počítače používají jednotky USB se zřizovacími balíčky.

Před touto verzí museli uživatelé při zřizování pomocí kombinace tlačítek ručně spustit obrazovku zřizování během spuštění při spuštění počítače. Uživatelé teď mohou kombinaci tlačítek přeskočit pomocí zřizovacího balíčku na jednotce úložiště USB. 

1. Připojte jednotku USB se zřizovacím balíčkem během prvního interagovatelného okamžiku prvního ZOBE.
1. Až bude zařízení připravené ke zřízení, automaticky se otevře výzva se stránkou zřizování. 

Poznámka: Pokud je usb flash disk při spouštění zařízení připojený k napájení, OOBE provede výčet stávajícího paměťového zařízení USB a bude sledovat, jestli se neschytí další zařízení.

Přečtěte si informace [o použití zřizovacích balíčků během OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatické potvrzení zřizovacího balíčku v OOBE
- Automatizovaný proces, který umožňuje menší interakci uživatelů, a když se zobrazí stránka zřizovací balíček, automaticky použije všechny uvedené balíčky.

Když se zobrazí hlavní obrazovka zřizování, OOBE odpočítá 10 sekund, než automaticky začne používat všechny zřizovací balíčky. Do 10 sekund od ověření balíčků, které očekávali, mohou uživatelé stále potvrdit nebo zrušit.

### <a name="automatic-provisioning-without-using-ui"></a>Automatické zřizování bez použití uživatelského rozhraní
- Kombinované automatické procesy pro menší interakce zařízení pro zřizování. 

Kombinací automatického spuštění zřizování ze zařízení USB a automatického potvrzení zřizovacího balíčku může uživatel zřídit zařízení HoloLens 2 automaticky bez použití uživatelského rozhraní zařízení nebo dokonce s jeho používáním. Můžete dál používat stejnou jednotku USB a zřizovací balíček pro více zařízení. To je užitečné pro nasazení více zařízení najednou ve stejné oblasti. 

1. [Pomocí nástroje Windows](hololens-provisioning.md) [Configuration Designer vytvořte zřizovací balíček.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Zkopírujte balíček na jednotku úložiště USB.
1. [Flash váš HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) až [19041.1361 nebo novější build](https://aka.ms/hololens2previewdownload). 
1. Po [dokončení rozšířeného](https://www.microsoft.com/store/productId/9P74Z35SFRS8) průvodce obnovením zařízení odpojte kabel USB-C. 
1. Připojte jednotku USB k zařízení.
1. Když se HoloLens 2 spustí do OOBE, automaticky zjistí zřizovací balíček na USB disku a spustí stránku zřizování.
1. Po 10 sekundách zařízení automaticky použije zřizovací balíček. 

Vaše zařízení je teď nakonfigurované a zobrazí obrazovku Zřizování bylo úspěšné.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Použití nebo odebrání zřizovacího balíčku pro HoloLens po instalaci

> [!NOTE]
> Tento postup platí pro všechna zařízení HoloLens 2 a HoloLens (1. generace) na zařízeních Windows Holographic verze 1809 a vyšší.

Na počítači postupujte takto:
1. Vytvořte zřizovací balíček, jak je popsáno v tématu Vytvoření zřizovacího balíčku [pro HoloLens pomocí HoloLens.](hololens-provisioning.md)
2. Připojení HoloLens připojte zařízení k počítači pomocí kabelu USB. HoloLens se zobrazí jako zařízení v Průzkumník souborů počítači.
3. Přetáhněte zřizovací balíček do složky Dokumenty na HoloLens.

Na svém HoloLens postupujte takto:
1. Přejděte na **Nastavení**  >  **Přístup k**  >  **účtům do práce nebo do školy.** 
2. V **části Nastavení** vyberte **Přidat nebo odebrat zřizovací balíček.**
3. Na další stránce vyberte Přidat **balíček, aby** se spouštěl výběr souborů, a vyberte svůj zřizovací balíček. Pokud je složka prázdná, vyberte Toto **zařízení** a pak vyberte **Dokumenty.**

Po použití se balíček zobrazí v seznamu **Nainstalované balíčky**. Pokud chcete zobrazit podrobnosti balíčku nebo odebrat balíček ze zařízení, vyberte uvedený balíček.

## <a name="what-you-can-configure"></a>Co můžete konfigurovat

Zřizovací balíčky používají poskytovatele konfiguračních služeb (CSP). Pokud poskytovatele CSP ještě nevíte, podívejte se na úvod do poskytovatelů konfiguračních služeb [(CSP) pro IT profesionály.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

Když v Windows Configuration Designeru vytvoříte zřizovací balíček pro Windows Holographic, nastavení v části Dostupná přizpůsobení jsou založená na csP podporovaných v [Windows Holographic.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)  Následující tabulka popisuje nastavení, která můžete chtít nakonfigurovat pro HoloLens.

![Běžná nastavení modulu runtime pro HoloLens](images/icd-settings.png)

| Nastavení | Popis |
| --- | --- |
| **Certifikáty** | Nasaďte certifikát do HoloLens.  |
| **Profily připojení** | Nasaďte profil Wi-Fi do HoloLens.   |
| **Upgrade edice** | [Upgradujte na Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Zásady** | Povolte nebo zabraňte vývojářskému režimu HoloLens. [Zásady podporované Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalace aplikace prostřednictvím zřizovacího balíčku

Aplikace je možné nainstalovat prostřednictvím zřizovacího balíčku na HoloLens 2 zařízení. To umožňuje snadno znovu použitelný balíček, který můžete použít k distribuci aplikací. Přečtěte si úplné pokyny [pro nasazení aplikací prostřednictvím zřizovacího balíčku](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1. generace) má omezenou podporu instalace aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku. HoloLens (1. generace) podporují instalaci aplikace přes PPKG jenom během OOBE a jenom při instalaci kontextu uživatele.
