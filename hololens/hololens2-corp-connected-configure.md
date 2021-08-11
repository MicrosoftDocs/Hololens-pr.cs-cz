---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – konfigurace
description: naučte se, jak nastavit konfigurace pro nasazení HoloLens 2 zařízení přes podnikovou síť s příručkami k Dynamics 365.
keywords: HoloLens, správa, připojení k podnikové síti, příručky k Dynamics 365, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.openlocfilehash: 2b855f5891dfa4ca695e4ae3b2a2e82510c5b626f08b434643169be239b48291
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660183"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurace – příručka propojená s podnikem

## <a name="azure-users-and-groups"></a>Uživatelé a skupiny Azure

Azure a Intune pomocí tohoto rozšíření využívají uživatele a skupiny, které vám pomůžou přiřadit konfigurace a licence. Pro účely ověření tohoto toku nasazení a možnost kontrolovat, zda můžete vytvořit a pracovat s průvodcem,&#39;potřebný uživatelský účet.

Můžete vytvořit jednu skupinu uživatelů specifickou pro přiřazení licencí.

Pokud nemáte&#39;t už máte přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít. Tady jsou Úvodní příručky pro:

- [Postup vytvoření uživatele](/mem/intune/fundamentals/quickstart-create-user)
- [Vytvoření skupiny](/mem/intune/fundamentals/quickstart-create-group)
- [Přidat uživatele do skupiny](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – přidat vytvořené uživatele k vytvoření skupiny
- [Konfigurace služby Azure AD tak, aby povolovala skupině uživatelů připojení zařízení](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – zajistěte, aby nová skupina uživatelů měla oprávnění k registraci zařízení do Azure AD.

## <a name="auto-enrollment-on-hololens-2"></a>automatický zápis na HoloLens 2

aby bylo možné zajistit hladké a bezproblémové prostředí, nastavení Azure Active Directory Join (AADJ) a automatický zápis do intune pro HoloLens 2 zařízení je možné přejít. Díky tomu můžou uživatelé během spuštění OOBE zadat přihlašovací údaje pro své organizace a automaticky se zaregistrovat ve službě Azure AD a zaregistrovat zařízení do MDM.

pomocí [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a přejít na několik stránek, dokud si nebudeme moct vybrat získat Premium zkušební verzi. můžete si všimnout, že existuje Azure Active Directory Premium 1 a 2 – pro automatický zápis P1 je dostačující. Můžeme vybrat Intune a vybrat obor uživatele pro automatický zápis a vybrat skupinu, která byla dřív vytvořená.

Úplné podrobnosti a kroky najdete v průvodci, [Jak povolit automatický zápis pro Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Připojení k podnikovému Wi-Fi

podniková Wi-Fiová připojení budou běžně vyžadovat ověřování na základě certifikátů pro zákazníky, kteří používají HoloLens 2. Tyto certifikáty budete muset nasadit pomocí Simple Certificate Enrollment Protocol (SCEP) nebo infrastruktury certifikátu PKCS (Public Key Cryptography Standard), která je integrovaná s vaším řešením pro správu mobilních zařízení (MDM). Použití Intune k nasazení profilů Wi-Fi, certifikátů a nastavení proxy serveru vytvoří bezproblémové prostředí pro koncové uživatele.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Nasazení certifikátů a profilů Wi-Fi

k nasazení certifikátů a profilů prostřednictvím Microsoft Endpoint Manager použijte následující postup:

1. Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR.

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti nebudou nasazeny**.

2. Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz [Vytvoření profilu certifikátu SCEP nebo vytvoření profilu certifikátu PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu dd/mm/rrrr.

    > [!CAUTION]
    > **Profily certifikátů bez data vypršení platnosti nebudou nasazeny.**

    > [!Note]
    > vzhledem k tomu, že HoloLens 2 se považuje za sdílené zařízení, tj. více uživatelů na každé zařízení, doporučuje se místo uživatelských certifikátů nasadit certifikáty zařízení, a to v případě potřeby Wi-Fi ověřování.

3. vytvořte profil pro vaši podnikovou Wi-Fi síť (viz [nastavení Wi-Fi pro zařízení Windows 10 a novější](/intune/wi-fi-settings-windows)). V rámci vašeho profilu Wi-Fi můžete zvolit, že se má používat nastavení proxy serveru v rámci vaší organizace.

    Možnosti:
    - **Žádné:** nenakonfiguruje se žádné nastavení proxy.
    - **Ručně konfigurovat**: zadejte **IP adresu proxy serveru** a **číslo portu**.
    - **Automaticky konfigurovat**: zadejte adresu URL odkazující na skript automatické konfigurace proxy serveru (PAC). Zadejte například *http://proxy.contoso.com/proxy.pac* .

    Další informace o souborech PAC najdete v tématu [soubor automatické konfigurace proxy serveru](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (otevře se na webu, který není Microsoft).
 
    > [!Note]
    > Doporučuje se, aby byl profil Wi-Fi přiřazen skupinám zařízení, nikoli skupinám uživatelů, pokud je to možné.
     
    > [!Tip]
    > pracovní Wi-Fi profil můžete také exportovat ze Windows 10 počítače v podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. pak tento soubor importujte do intune a použijte ho jako profil Wi-Fi pro zařízení HoloLens 2. Viz [Import nastavení Wi-Fi pro zařízení s Windows 8.1 a novější verzí v Microsoft Intune](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [přiřaďte](/mem/intune/configuration/device-profile-assign) profily zařízení k HoloLens skupině zařízení.

2.  [Monitorujte](/mem/intune/configuration/device-profile-monitor) profily zařízení v Intune.

Pokud dojde k problémům s profilem Wi-Fi, [vyřešte potíže Wi-Fi konfiguračních profilů zařízení v Intune](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Řešení potíží s externím přístupem k Internetu při připojení Corp
Pokud se služba pokusí neprojít serverem proxy, může se pokusit připojit přes bránu firewall. Pro řešení těchto problémů můžete přidat seznam specifických koncových bodů k pravidlům brány firewall.

Pokud jste blokováni na portech brány firewall, povolte některé běžné [koncové body](/hololens/hololens-offline) pro HoloLens.

Můžete také povolit porty specifické pro příručky: [internetové adresy URL, které jsou vyžadovány pro připojení k Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Nasazení aplikací

Nasazení obchodní aplikace přes MDM je metoda, kterou je možné snadno škálovat a která se dá automaticky nasadit do vašich zařízení při registraci v vytvořené skupině.

Pokud stále vyvíjíte aplikace nebo ještě nemáte, můžete použít ukázkovou aplikaci centra příkladů MRTK. Tato ukázková aplikace je připravená k použití, a nevyžaduje použití ani Visual Studio Unity. [Stáhněte si ukázkovou aplikaci s příklady pro MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Pokud dáváte přednost používání vlastní aplikace nebo zajímáte vývoj aplikací pro hybridní realitu, můžete si klidně přečíst naši dokumentaci pro [vývojáře hybridní reality](/windows/mixed-reality/design/design).

> [!NOTE]
> požadavky na systém pro HoloLens zařízení jsou založené na architektuře buildu aplikace. zařízení HoloLens 2 používají architekturu ARM. při sestavování aplikací v Visual Studio ujistěte se, že jste vybrali správnou architekturu pro zařízení a zadáte všechny potřebné závislosti.

> [!IMPORTANT]
> Při nasazování obchodních aplikací je důležité také odeslat certifikát do Intune a přiřadit ho ke stejné skupině, která je určena k používání aplikace, nebo nebude správně nainstalována.

### <a name="upload-and-assign-the-app"></a>Upload a přiřazení aplikace

1. Přejděte do [centra pro správu nástroje mem](https://endpoint.microsoft.com/#home).

2. Vyberte **aplikace**  ->  **všechny aplikace** a klikněte na tlačítko **+ Přidat** .

3. Pod položkou jiné vyberte **obchodní aplikaci**. Klikněte na **Vybrat**.

4. Vyberte soubor balíčku aplikace, jedná se o soubor APPXBUNDLE, nebo v našem případě v tomto příkladu je aplikace _MRTK Examples hub \_ 2.4.2.0 \_ ARM \_ Master. appxbundle_.

5. Zobrazí se oznámení o chybějících závislostech. V takovém případě musíme nahrát _Microsoft. VCLibs. ARM. 14.00. appx_. Vyhledejte ho v části **Vybrat soubor**.

6. Vyberte OK.

7. Na další obrazovce budou požadovaná pole automaticky vyplněna. Vyberte **Další**.

8. V části požadováno přidejte naši dříve vytvořenou skupinu, aby tato aplikace byla pro skupinu požadovaná. Tato akce způsobí, že se aplikace automaticky stáhne do zaregistrovaných zařízení ve skupině. Vyberte **Další**.

9. Vyberte **Vytvořit**.

Další informace: [přiřazování aplikací do skupin v Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Průvodce nastavením: licence k aplikacím, datatext a vytváření obsahu

Aby bylo možné používat Příručky k Dynamics 365, je nutné provést určitou přípravu. Existují tři oblasti, ve kterých budeme muset připravit. Uživatelé, datatext a vlastní příručky.

### <a name="users-and-application-licenses"></a>Licence uživatelů a aplikací

Aby někdo mohl používat příručky, musí použít účet Azure AD, který jsme v této příručce nastavili dřív.

Pro uživatele, kterého jste vytvořili, budete také muset přiřadit licenci pro Příručky k Dynamics 365. provedete to z [Centrum pro správu Microsoftu 365](https://admin.microsoft.com/AdminPortal/Home). Také přiřaďte licenci k primárnímu účtu Azure.

Podrobné pokyny k instalaci licencí k aplikacím najdete v [tomto krátkém průvodci](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) s obrázky.

### <a name="set-up-the-dataverse"></a>Nastavení datatext

Aby bylo možné [nastavit produkční prostředí](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) , budete muset splnit dva požadavky. musíte mít roli [**správce systému**](/power-platform/admin/database-security) **a** musíte mít licenci [**Power Apps**](/power-platform/admin/signup-question-and-answer) (nebo [**licenci k Dynamics 365**](/dynamics365/mixed-reality/guides/setup-step-one) , která zahrnuje licenci Power Apps). Pokud se vám v tomto průvodci vytvořila služba Azure AD, budete splňovat požadavky role pro správce systému. V předchozím kroku jsme také přiřadili licenci na příručky.

V této příručce [vytvoříte prostředí Microsoft](/dynamics365/mixed-reality/guides/setup-step-two)datatext:

1. Začněte pomocí centra pro [správu Power Platform](https://admin.powerplatform.microsoft.com/environments) a vytvořte nové prostředí.
2. Když vytváříte **nové prostředí**, pro **typ** , který&#39;te, se vybere **produkce**.
3. Je důležité, abyste **pro toto prostředí přepnuli vytvořit databázi?**  možnost  **Ano**.
4. V dialogovém okně  **Přidat databázi**  nastavte možnost  **povolit aplikace Dynamics 365**  na  **Ano.**

Maximální velikost souboru položek v datovém zdroji byste měli zvětšit. Zvýšení maximální velikosti souboru vám umožní nahrát větší 3D modely nebo videosoubory, které použijete později v průvodcích. Pokud chcete změnit maximální [velikost nahrání souboru, postupujte podle krátké příručky.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Nakonec budete muset řešení nainstalovat [a nakonfigurovat.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) V [centrum pro správu Power Platform](https://admin.powerplatform.microsoft.com/environments)vyberte Prostředky  \& gt;  **Aplikace Dynamics 365,** v seznamu vyberte **Příručky Dynamics 365** a pak vyberte **Nainstalovat.**  

Abyste [mohli aplikace používat,](/dynamics365/mixed-reality/guides/assign-role) musíte přidat roli zabezpečení Příručky.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Vytvoření testovací příručky na počítači prostřednictvím vytváření

Při vytváření průvodců vždy začnete na svém počítači. Vytvoření kroků, výběr modelů a ukotvení průvodce Za tímto krokem umístíte obsah pro průvodce později v režimu vytváření obsahu na HoloLens zařízení. Pro účely tohoto průvodce doporučujeme, abyste si krátkého testovacího průvodce s minimálními kroky a modely.

Pokud se chcete začít učit o vytváření průvodců, začněte tady s [přehledem vytváření.](/dynamics365/mixed-reality/guides/authoring-overview) Nebo pokud chcete získat rychlý přehled, podívejte se na toto krátké video.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Volitelné: Bezobrazovový režim

Bezobrazovový režim je režim, který umožňuje správci IT nakonfigurovat uživatelské rozhraní nabídky Start tak, aby se v ní zobrazují jenom jedna aplikace nebo výběr aplikací. Bezobrazovk se také může použít u konkrétních uživatelů, skupin nebo na úrovni zařízení. a v některých případech některé uživatele z veřejného terminálů vylučte, aby jim stále povoloval přístup k běžné nabídce Start.

Bezobrazovový režim má mnoho různých proměnných, a to jak v rozsahu, tak v konfiguracích, které je možné nastavit, a také metody nasazení veřejného terminálu do HoloLens. Vzhledem ke všem těmto proměnným je  režim Veřejného terminálu pro tohoto průvodce volitelný a nebude se k tomuto průvodci znovu vracet. Pokud se domníváte, že máte obchodní potřebu omezit dostupné aplikace na uživatele nebo chcete získat další informace, přečtěte si, jak nastavit HoloLens jako [beziosk](/hololens/hololens-kiosk).

## <a name="optional-wdac"></a>Volitelné: WDAC

WdAC umožňuje správci IT nakonfigurovat svá zařízení tak, aby blokují spouštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je například bezobrazovový režim, kde se uživateli zobrazí uživatelské rozhraní, které skryje aplikace v zařízení, ale přesto je můžete spustit. Přestože je nástroj WDAC implementován, aplikace se stále zobrazí v seznamu Všechny aplikace, ale nástroj WDAC zastaví spuštění těchto aplikací a procesů uživatelem zařízení.

Další informace najdete v referenčních informacích: Použití wdac a Windows PowerShell k povolení nebo blokování aplikací na [zařízeních HoloLens 2 s Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Řízení aplikací – WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Nasazení připojené k podnikové síti – nasazení](hololens2-corp-connected-deploy.md)