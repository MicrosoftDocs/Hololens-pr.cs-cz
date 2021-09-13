---
title: Průvodce nasazením – Průvodci podnikovými HoloLens 2 s Dynamics 365 – konfigurace
description: Zjistěte, jak nastavit konfigurace pro nasazení HoloLens 2 přes podnikovou připojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, správa, firemní připojení, Průvodci Dynamics 365, AAD, Azure AD, MDM, Mobile Správa zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032315"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurace – Průvodce připojeným podnikem

## <a name="azure-users-and-groups"></a>Uživatelé a skupiny Azure

Azure a Intune tímto rozšířením používají uživatele a skupiny k přiřazení konfigurací a licencí. Kvůli ověření tohoto toku nasazení a kontrole, jestli můžete vytvořit a provozovat průvodce,&#39;potřebovat uživatelský účet.

Můžeme vytvořit jednu skupinu uživatelů speciálně pro přiřazování licencí.

Pokud ještě&#39;přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít . Tady jsou úvodní příručky pro:

- [Jak vytvořit uživatele](/mem/intune/fundamentals/quickstart-create-user)
- [Jak vytvořit skupinu](/mem/intune/fundamentals/quickstart-create-group)
- [Přidání uživatelů do skupiny](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Přidání vytvořených uživatelů pro vytvoření skupiny
- [Konfigurace Azure AD tak, aby skupině uživatelů umožnila připojovat](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) se k zařízením – Ujistěte se, že nová skupina uživatelů má oprávnění k registraci zařízení do Azure AD.

## <a name="auto-enrollment-on-hololens-2"></a>Automatická registrace na HoloLens 2

Pokud chcete mít bezproblémové a bezproblémové prostředí, můžete použít nastavení AADJ (Azure Active Directory Join) a automatické registrace do Intune pro zařízení HoloLens 2. To umožňuje uživatelům zadat přihlašovací údaje organizace během OOBE a automaticky se zaregistrovat ve službě Azure AD a zaregistrovat zařízení do MDM.

Pomocí [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a procházet několik stránek, dokud nebude možné vybrat Získat zkušební Premium verzi. Můžete si všimnout, že Azure Active Directory Premium 1 a 2 – pro automatickou registraci P1 je dostačující. Můžeme vybrat Intune, vybrat obor uživatele pro automatickou registraci a vybrat skupinu, která byla vytvořena dříve.

Úplné podrobnosti a kroky najdete v průvodci [povolením automatické registrace pro Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Připojení Wi-Fi podnikové sítě

Firemní Wi-Fi připojení budou často vyžadovat ověřování pomocí certifikátů pro zákazníky, kteří používají HoloLens 2. Tyto certifikáty budete muset nasadit pomocí infrastruktury certifikátů Simple Certificate Enrollment Protocol (SCEP) nebo PKCS (Public Key Cryptography Standard), která je integrovaná s řešením MDM. Použití Intune k nasazení Wi-Fi profilů, certifikátů a nastavení proxy serveru vytváří bezproblémové prostředí pro koncové uživatele.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Nasazení certifikátů a Wi-Fi profilů

Pokud chcete nasadit certifikáty a profily prostřednictvím Microsoft Endpoint Manager, postupujte takto:

1. Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR.

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti se nenasadí.**

2. Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz Vytvoření profilu certifikátu SCEP nebo Vytvoření profilu certifikátu [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR.

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti se nenasadí.**

    > [!Note]
    > Vzhledem k tomu, že HoloLens 2 se považuje za sdílené zařízení, t.j. více uživatelů na zařízení, doporučujeme místo uživatelských certifikátů nasadit certifikáty zařízení, pokud je Wi-Fi možné.

3. Vytvořte profil pro podnikovou síť Wi-Fi sítě (viz [Nastavení Wi-Fi pro Windows 10 a novější zařízení).](/intune/wi-fi-settings-windows) V rámci Wi-Fi profilu můžete použít nastavení proxy serveru v rámci vaší organizace.

    Možnosti:
    - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
    - **Ruční konfigurace:** Zadejte **IP adresu proxy serveru a** číslo **portu**.
    - **Automaticky nakonfigurovat:** Zadejte adresu URL odkazující na skript pac (auto configuration) proxy serveru. Zadejte například *http://proxy.contoso.com/proxy.pac* .

    Další informace o souborech PAC najdete v tématu [Soubor PAC (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (otevře web od jiných společností než Microsoft).
 
    > [!Note]
    > Pokud je to možné, Wi-Fi profil zařízení přiřaděl skupinám zařízení, a ne skupinám uživatelů.
     
    > [!Tip]
    > Můžete také exportovat pracovní profil Wi-Fi z Windows 10 počítače ve vaší podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. Pak tento soubor naimportujte do Intune a použijte ho jako profil Wi-Fi pro zařízení s HoloLens 2. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Přiřaďte](/mem/intune/configuration/device-profile-assign) profily zařízení ke skupině HoloLens zařízení.

2.  [Monitorujte](/mem/intune/configuration/device-profile-monitor) profily zařízení v Intune.

Pokud máte problémy s profily Wi-Fi, najdete je v tématu Řešení Wi-Fi [potíží s konfiguračními profily zařízení v Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Řešení potíží s externím přístupem k internetu při připojení Corp
Když se služby nepokusí projít nastaveným proxy serverem, mohou se pokusit připojit přes bránu firewall. Pokud chcete tyto problémy vyřešit, můžete do pravidel brány firewall přidat seznam specifik koncových bodů.

Pokud jste zablokovaní na portech brány firewall, povolte některé běžné [koncové](/hololens/hololens-offline) body pro HoloLens.

Můžete také povolit porty specifické pro příručky: adresy URL přístupné z internetu [vyžadované pro připojení k Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Nasazení aplikací

Nasazení obchodní aplikace přes MDM je metoda, která je snadno škálovatelná a lze ji automaticky nasadit do zařízení při registraci ve vytvořené skupině.

Pokud své aplikace stále vyvíjíte nebo ještě žádné nemáte, můžete použít ukázkovou aplikaci z centra příkladů MRTK. Tato ukázková aplikace je připravená k použití a nevyžaduje použití Unity ani Visual Studio. [Stáhněte si ukázkovou aplikaci MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Pokud byste chtěli raději používat vlastní aplikaci nebo byste chtěli vývoj aplikací pro Mixed Reality, můžete si prohlédněte naši dokumentaci Mixed Reality [pro vývojáře.](/windows/mixed-reality/design/design)

> [!NOTE]
> Požadavky na systém HoloLens zařízení jsou založené na architektuře sestavení aplikace. HoloLens 2 používají architekturu ARM. Při sestavování aplikací v Visual Studio ujistěte se, že jste pro zařízení vybrali správnou architekturu a že zahrnuje všechny potřebné závislosti.

> [!IMPORTANT]
> Při nasazování obchodních aplikací je důležité nahrát certifikát do Intune a přiřadit ho stejné skupině, která má aplikaci používat, jinak se správně nenainstaluje.

### <a name="upload-and-assign-the-app"></a>Upload a přiřazení aplikace

1. Přejděte do [Centra pro správu MEM.](https://endpoint.microsoft.com/#home)

2. Vyberte **Aplikace**  ->  **Všechny aplikace** a vyberte **tlačítko +** Přidat.

3. V části Jiné **vyberte Obchodní aplikace.** Klikněte **na vybrat**.

4. Vyberte soubor balíčku aplikace, to je váš soubor APPXBUNDLE, nebo v našem příkladu je aplikace _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Budete upozorněni na chybějící závislosti. V tomto případě musíme nahrát _Microsoft.VCLibs.ARM.14.00.appx_. Vyhledejte ho v **části Vyberte soubor**.

6. Vyberte OK.

7. Na další obrazovce se automaticky vyplní požadovaná pole. Vyberte **Další**.

8. V části Povinné přidejte dříve vytvořenou skupinu, aby se tato aplikace pro skupinu vyžadovala. To způsobí, že se aplikace automaticky stáhne na zaregistrovaná zařízení ve skupině. Vyberte **Další**.

9. Vyberte **Vytvořit**.

Další informace: [Přiřazení aplikací do skupin v Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Průvodci nastavením: Licence aplikací, dataverse a vytváření

Abyste mohli používat příručky Dynamics 365, budete muset provést nějakou přípravu. Existují tři oblasti, ve kterých se budeme muset připravit. uživatele, dataverse a samotné příručky.

### <a name="users-and-application-licenses"></a>Uživatelé a licence aplikací

Aby mohl někdo používat příručky, bude muset použít účet Azure AD, který jsme si nastavili v předchozí příručce.

Také budete muset přiřadit licenci průvodců Dynamics 365 vytvořenému uživateli. Budete to dělat z [Centrum pro správu Microsoftu 365](https://admin.microsoft.com/AdminPortal/Home). Také přiřaďte licenci k primárnímu účtu Azure.

Podrobné [pokyny k](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) použití licencí aplikací najdete v tomto krátkém průvodci obrázky.

### <a name="set-up-the-dataverse"></a>Nastavení dataverse

Abyste mohli [nastavit produkční prostředí,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) budete muset splnit dva požadavky. Musíte mít roli Správce  [**systému**](/power-platform/admin/database-security) [**a**](/power-platform/admin/signup-question-and-answer) musíte mít Power Apps licenci (nebo licenci průvodců [**Dynamics 365,**](/dynamics365/mixed-reality/guides/setup-step-one) která zahrnuje Power Apps licence). Pokud jste podle této příručky vytvořili Azure AD, splňujete požadavky role pro správce systému. V předchozím kroku jsme také přiřadili licenci guides.

V tomto průvodci [vytvoříte prostředí Microsoft Dataverse:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Začněte použitím [centrum pro správu Power Platform](https://admin.powerplatform.microsoft.com/environments) a vytvořením nového prostředí.
2. Při vytváření **nového prostředí** jako Typ **vyberete**&#39;produkční **prostředí**.
3. Je důležité přepnout na **Vytvořit databázi pro toto prostředí?**  na **Ano.**
4. V dialogovém  **okně Přidat**  databázi nastavte možnost Povolit aplikace  **Dynamics 365**  na  **Ano.**

Maximální velikost souboru položek v datovém zdroji byste měli zvětšit. Zvýšení maximální velikosti souboru vám umožní nahrát větší 3D modely nebo videosoubory, které použijete později v průvodcích. Pokud chcete změnit maximální [velikost nahrání souboru, postupujte podle krátké příručky.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Nakonec budete muset řešení nainstalovat [a nakonfigurovat.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) V [centrum pro správu Power Platform](https://admin.powerplatform.microsoft.com/environments)vyberte Prostředky  \& gt;  **Aplikace Dynamics 365,** v seznamu vyberte **Příručky Dynamics 365** a pak vyberte **Nainstalovat.**  

Abyste [mohli aplikace používat,](/dynamics365/mixed-reality/guides/assign-role) musíte přidat roli zabezpečení Příručky.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Vytvoření testovací příručky na počítači prostřednictvím vytváření

Při vytváření průvodců vždy začnete na svém počítači. Vytvoření kroků, výběr modelů a ukotvení průvodce Za tímto krokem umístíte obsah pro průvodce později v režimu vytváření obsahu na HoloLens zařízení. Pro účely tohoto průvodce doporučujeme, abyste si krátkého testovacího průvodce s minimálními kroky a modely.

Pokud se chcete začít učit o vytváření průvodců, začněte tady s [přehledem vytváření.](/dynamics365/mixed-reality/guides/authoring-overview) Nebo pokud chcete získat rychlý přehled, podívejte se na toto krátké video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Volitelné: Bezobrazovový režim

Bezobrazovový režim je režim, který umožňuje správci IT nakonfigurovat uživatelské rozhraní nabídky Start tak, aby se v ní zobrazují jenom jedna aplikace nebo výběr aplikací. Beziosk se také může použít pro konkrétní uživatele, skupiny nebo na úrovni zařízení. a v některých případech některé uživatele vylučte z veřejného terminálů, aby jim stále povoloval přístup k běžné nabídce Start.

Bezobrazovový režim má mnoho různých proměnných, a to jak v rozsahu, tak v konfiguracích, které je možné nastavit, a také metody nasazení veřejného terminálu do HoloLens. Vzhledem ke všem těmto proměnným je  režim Veřejného terminálu pro tohoto průvodce volitelný a nebude se k tomu vracet. Pokud se domníváte, že máte obchodní potřebu omezit dostupné aplikace na uživatele nebo chcete získat další informace, přečtěte si, jak nastavit HoloLens jako [beziosk](/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Volitelné: WDAC

WdAC umožňuje správci IT nakonfigurovat svá zařízení tak, aby blokují spouštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je například režim veřejného terminála, kde se uživateli zobrazí uživatelské rozhraní, které skryje aplikace v zařízení, ale přesto je můžete spustit. I když je nástroj WDAC implementován, aplikace se stále zobrazí v seznamu Všechny aplikace, ale nástroj WDAC zastaví spuštění těchto aplikací a procesů uživatelem zařízení.

Další informace najdete v referenčních informacích: Použití wdac a Windows PowerShell k povolení nebo blokování aplikací na [HoloLens 2 s Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Řízení aplikací – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Nasazení připojené k podnikové síti – nasazení](hololens2-corp-connected-deploy.md)