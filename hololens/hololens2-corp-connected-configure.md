---
title: Průvodce nasazením – Průvodci pro HoloLens 2 připojené k podnikové síti s Dynamics 365 – konfigurace
description: Zjistěte, jak nastavit konfigurace pro nasazení zařízení HoloLens 2 přes podnikovou připojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377534"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurace – Průvodce připojeným podnikem

## <a name="azure-users-and-groups"></a>Uživatelé a skupiny Azure

Azure a Intune tímto rozšířením používají uživatele a skupiny k přiřazení konfigurací a licencí. Kvůli ověření tohoto toku nasazení a kontrole, jestli můžete vytvořit a provozovat průvodce,&#39;potřebovat uživatelský účet.

Můžeme vytvořit jednu skupinu uživatelů speciálně pro přiřazování licencí.

Pokud ještě&#39;přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít . Tady jsou úvodní příručky pro:

- [Jak vytvořit uživatele](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Jak vytvořit skupinu](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Přidání uživatelů do skupiny](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Přidání vytvořených uživatelů pro vytvoření skupiny
- [Konfigurace Azure AD tak, aby umožnila skupině](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) uživatelů připojovat se k zařízením – Ujistěte se, že nová skupina uživatelů má oprávnění k registraci zařízení do Azure AD.

## <a name="auto-enrollment-on-hololens-2"></a>Automatická registrace na HoloLens 2

Pokud chcete mít bezproblémové a bezproblémové prostředí, můžete použít nastavení AADJ (Azure Active Directory Join) a automatické registrace do Intune pro zařízení HoloLens 2. To umožňuje uživatelům zadat přihlašovací údaje organizace během OOBE a automaticky se zaregistrovat ve službě Azure AD a zaregistrovat zařízení do MDM.

Pomocí microsoft [Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a procházet několik stránek, dokud nevybereme Získat zkušební verzi Premium. Můžete si všimnout, že Azure Active Directory Premium 1 a 2 – pro automatickou registraci P1 je dostačující. Můžeme vybrat Intune, vybrat obor uživatele pro automatickou registraci a vybrat skupinu, která byla vytvořena dříve.

Úplné podrobnosti a kroky najdete v průvodci [povolením automatické registrace pro Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Připojení Wi-Fi podnikové sítě

Firemní Wi-Fi připojení budou často vyžadovat ověřování na základě certifikátů pro zákazníky, kteří používají HoloLens 2. Tyto certifikáty budete muset nasadit pomocí infrastruktury certifikátů Simple Certificate Enrollment Protocol (SCEP) nebo PKCS (Public Key Cryptography Standard), která je integrovaná s řešením MDM. Použití Intune k nasazení Wi-Fi profilů, certifikátů a nastavení proxy serveru vytváří bezproblémové prostředí pro koncové uživatele.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Nasazení certifikátů a Wi-Fi profilů

Pokud chcete nasadit certifikáty a profily prostřednictvím služby Microsoft Endpoint Manager, postupujte následovně:

1. Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. 

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti se nenasadí.**

2.  Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz Vytvoření profilu certifikátu SCEP nebo Vytvoření profilu certifikátu [PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. 

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti se nenasadí.**

    > [!Note]
    > Vzhledem k tomu, že zařízení HoloLens 2 je považováno za sdílené zařízení, tj. více uživatelů na zařízení, doporučujeme místo uživatelských certifikátů nasadit certifikáty zařízení, pokud je Wi-Fi možné.

3.  Vytvořte profil pro podnikovou síť Wi-Fi sítě (viz [Nastavení Wi-Fi pro Windows 10 a novější zařízení).](https://docs.microsoft.com/intune/wi-fi-settings-windows) V rámci Wi-Fi můžete v rámci své organizace použít nastavení proxy serveru.
 
    Možnosti:
    - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
    - **Ruční konfigurace:** Zadejte **IP adresu proxy serveru a** číslo **portu**.
    - **Automaticky nakonfigurovat:** Zadejte adresu URL odkazující na skript pac (auto configuration) proxy serveru. Zadejte například *http://proxy.contoso.com/proxy.pac* .

    Další informace o souborech PAC najdete v tématu [Soubor PAC (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (otevře web od jiných společností než Microsoft).
 
    > [!Note]
    > Pokud je to možné, doporučujeme profil Wi-Fi přiřadit skupinám zařízení, a ne skupinám uživatelů.
     
    > [!Tip]
    > Můžete také exportovat pracovní profil Wi-Fi z Windows 10 počítače ve vaší podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. Pak tento soubor naimportujte do Intune a použijte ho jako Wi-Fi pro zařízení HoloLens 2. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Přiřaďte](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) profily zařízení ke skupině zařízení HoloLens.

2.  [Monitorujte](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) profily zařízení v Intune.

Pokud máte problémy s profily Wi-Fi, najdete je v tématu Řešení [potíží Wi-Fi profilů konfigurace zařízení v Intune.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Řešení potíží s externím přístupem k internetu při připojení společnosti
Když se služby nepokusí projít nastaveným proxy serverem, mohou se pokusit připojit přes bránu firewall. Pokud chcete tyto problémy vyřešit, můžete do pravidel brány firewall přidat seznam specifik koncových bodů.

Pokud jste zablokovaní na portech brány firewall, povolte některé běžné [koncové](https://docs.microsoft.com/hololens/hololens-offline) body pro HoloLens.

Můžete také povolit porty specifické pro příručky: adresy URL přístupné z internetu, které [jsou potřeba pro připojení k Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Nasazení aplikací

Nasazení obchodní aplikace přes MDM je metoda, která je snadno škálovatelná a lze ji automaticky nasadit do zařízení při registraci ve vytvořené skupině.

Pokud své aplikace stále vyvíjíte nebo ještě žádné nemáte, můžete použít ukázkovou aplikaci z centra příkladů MRTK. Tato ukázková aplikace je připravená k použití a nevyžaduje použití Unity ani Visual Studio. [Stáhněte si ukázkovou aplikaci MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Pokud byste chtěli raději používat vlastní aplikaci nebo byste chtěli vývoj aplikací pro Mixed Reality, můžete si prohlédněte naši dokumentaci [Mixed Reality pro vývojáře.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> Požadavky na systém pro zařízení HoloLens jsou založené na architektuře sestavení aplikace. Zařízení HoloLens 2 používají architekturu ARM. Při sestavování aplikací v Visual Studio ujistěte se, že jste pro zařízení vybrali správnou architekturu a že zahrnuje všechny potřebné závislosti.

> [!IMPORTANT]
> Při nasazování obchodních aplikací je důležité nahrát certifikát do Intune a přiřadit ho stejné skupině, která má aplikaci používat, jinak se správně nenainstaluje.

### <a name="upload-and-assign-the-app"></a>Nahrání a přiřazení aplikace

1. Přejděte do [Centra pro správu MEM.](https://endpoint.microsoft.com/#home)

2. Vyberte **Aplikace**  ->  **Všechny aplikace** a vyberte **tlačítko +** Přidat.

3. V části Jiné **vyberte Obchodní aplikace.** Klikněte **na vybrat**.

4. Vyberte soubor balíčku aplikace, toto je váš soubor APPXBUNDLE, nebo v našem příkladu je aplikace _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_.

5. Budete upozorněni na chybějící závislosti. V tomto případě musíme nahrát _Microsoft.VCLibs.ARM.14.00.appx_. Vyhledejte ho v **části Vyberte soubor**.

6. Vyberte OK.

7. Na další obrazovce se automaticky vyplní požadovaná pole. Vyberte **Další**.

8. V části Povinné přidejte dříve vytvořenou skupinu, aby se tato aplikace pro skupinu vyžadovala. To způsobí, že se aplikace automaticky stáhne na zaregistrovaná zařízení ve skupině. Vyberte **Další**.

9. Vyberte **Vytvořit**.

Další informace: [Přiřazení aplikací do skupin v Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Průvodci nastavením: Licence aplikací, dataverse a vytváření

Abyste mohli používat příručky Dynamics 365, budete muset provést nějakou přípravu. Existují tři oblasti, ve kterých se budeme muset připravit. uživatele, dataverse a samotné příručky.

### <a name="users-and-application-licenses"></a>Uživatelé a licence aplikací

Aby mohl někdo používat příručky, bude muset použít účet Azure AD, který jsme si nastavili v předchozí příručce.

Také budete muset přiřadit licenci průvodců Dynamics 365 vytvořenému uživateli. Budete to dělat z [Centrum pro správu Microsoftu 365](https://admin.microsoft.com/AdminPortal/Home). Také přiřaďte licenci k primárnímu účtu Azure.

Podrobné [pokyny k](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) použití licencí aplikací najdete v tomto krátkém průvodci obrázky.

### <a name="set-up-the-dataverse"></a>Nastavení dataverse

Abyste mohli [nastavit produkční prostředí,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) musíte splnit dva požadavky. Musíte mít roli Správce  [**systému**](https://docs.microsoft.com/power-platform/admin/database-security) a musíte mít licenci [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (nebo licenci průvodců [**Dynamics 365,**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) která zahrnuje Power Apps licence). Pokud jste podle této příručky vytvořili Azure AD, splňujete požadavky role pro správce systému. V předchozím kroku jsme také přiřadili licenci guides.

V tomto průvodci [vytvoříte prostředí Microsoft Dataverse:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Začněte použitím příkazu [centrum pro správu Power Platform](https://admin.powerplatform.microsoft.com/environments) a vytvořením nového prostředí.
2. Při vytváření **nového prostředí** jako Typ **vyberete**&#39;produkční **prostředí**.
3. Je důležité zapnout možnost **Vytvořit databázi pro toto prostředí?**  na **Ano.**
4. V dialogovém  **okně Přidat**  databázi nastavte možnost Povolit aplikace  **Dynamics 365**  na  **Ano.**

Budete chtít zvětšit maximální velikost souborů v DataItem. Zvýšení maximální velikosti souboru vám umožní nahrávat větší 3D modely nebo videosoubory, které budete používat později v průvodcích. Použijte krátký průvodce [pro změnu maximální velikosti souboru pro nahrání](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size).

Nakonec budete muset [řešení nainstalovat a nakonfigurovat](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). V [centru pro správu Power Platform](https://admin.powerplatform.microsoft.com/environments)vyberte **prostředky** \& gt;  **Aplikace dynamics 365**, v seznamu vyberte **Průvodce Dynamics 365** a pak vyberte **nainstalovat**.  

Než budete moct aplikace používat, musíte [Přidat roli zabezpečení Průvodce](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) .

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Vytvoření průvodce testováním na počítači pomocí vytváření obsahu

Při vytváření vodítek se vždycky zahájíte na svém počítači. Vytvoření kroků, výběr modelů a postup při ukotvení průvodce. Tato akce bude následovat po umístění obsahu pro vaši příručku později v části v režimu vytváření na zařízení HoloLens. Pro účely tohoto průvodce doporučujeme vytvořit krátký průvodce testováním s minimálními kroky a modely.

Pokud se chcete seznámit s vytvářením obsahu pro příručky, začněte tady s [přehledem vytváření](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview). Pokud chcete získat přehled o rychlém sledování, podívejte se na toto krátké video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Volitelné: celoobrazovkový režim

Celoobrazovkový režim je režim, který umožňuje správci IT nakonfigurovat uživatelské rozhraní nabídky Start tak, aby zobrazovalo jenom jednu aplikaci nebo výběr aplikací. Veřejný terminál se dá použít taky pro konkrétní uživatele, skupiny nebo na úrovni zařízení. a v některých případech vyloučí některé uživatele z veřejného terminálu a zároveň jim umožní přístup k běžné nabídce Start.

Celoobrazovkový režim má mnoho různých proměnných, v oboru i konfiguracích, které lze nastavit, a také metody nasazení veřejného terminálu na HoloLens. Z důvodu všech těchto proměnných je celoobrazovkový režim ponechán jako _volitelný_ pro tento průvodce a nebude znovu navštěvovat. Pokud se domníváte, že máte potřebnou firmu omezit dostupné aplikace na uživatele nebo chcete získat další informace, můžete si být jisti, jak [nastavit HoloLens jako veřejný terminál](https://docs.microsoft.com/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Volitelné: WDAC

WDAC umožňuje správci IT nakonfigurovat zařízení tak, aby blokovala spuštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je například celoobrazovkový režim, kde se uživatel zobrazuje s uživatelským ROZHRANÍm, které skrývá aplikace na zařízení, ale je možné ho přesto spustit. I když je implementováno WDAC, aplikace jsou stále viditelné v seznamu všechny aplikace, ale WDAC zastaví aplikace a procesy, aby je mohl uživatel zařízení spustit.

Další informace najdete v příručce [použití WDAC a prostředí Windows PowerShell k povolení nebo blokování aplikací na zařízeních HoloLens 2 pomocí Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Řízení aplikací v programu Windows Defender – WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Firemní připojené nasazení – nasazení](hololens2-corp-connected-deploy.md)