---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – příprava
description: přečtěte si, jak připravit registraci HoloLens 2 zařízení přes podnikovou síť s příručkami k Dynamics 365.
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427442"
---
# <a name="prepare---corporate-connected-guide"></a>Příprava – Průvodce připojenou k podnikové síti
## <a name="infrastructure-essentials"></a>Základy infrastruktury
pro scénáře osobního i podnikového nasazení je systém správy mobilních zařízení (MDM) základní infrastrukturou, která je nutná k nasazení a správě Windows 10ch zařízení, obzvláště HoloLens 2. jako zprostředkovatel identity se doporučuje [předplatné Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium) a **vyžaduje** se pro podporu určitých možností.

> [!NOTE]
> i když je HoloLens 2 nasazené a spravované jako mobilní zařízení, obvykle se používá jako sdílené zařízení mezi mnoha uživateli.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD je cloudová adresářová služba, která poskytuje správu identit a přístupů. organizace, které používají Microsoft Office 365 nebo intune, už používají Azure AD, které mají tři edice: Free, Premium P1 a Premium P2 (viz [edice Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). všechny edice podporují registraci zařízení Azure AD, ale Premium P1 se vyžaduje k povolení automatického zápisu MDM, který v této příručce použijeme později.
> [!Important]
> je nutné mít službu Azure AD jako HoloLens zařízení nepodporují místní službu AD join. Pokud ještě nemáte nastavenou službu Azure AD, začněte podle pokynů a [vytvořte nového tenanta v Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Správa identit
V této příručce bude použitá [Identita](/hololens/hololens-identity) účty Azure AD. Účty Azure AD mají několik výhod, například:

- zaměstnanci používají svůj účet Azure ad k registraci zařízení v Azure ad a můžou ho automaticky zaregistrovat v řešení MDM organizace (Azure AD + MDM – vyžaduje [předplatné Azure AD Premium](/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- účty Azure AD mají další [možnosti ověřování](/hololens/hololens-identity) prostřednictvím [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Kromě přihlášení Iris se uživatelé můžou přihlašovat z jiného zařízení nebo používat bezpečnostní klíče FIDO.

> [!WARNING] 
> Zaměstnanci můžou použít jenom jeden účet k inicializaci zařízení, aby **bylo naprosto nezbytné, aby vaše organizace měla kontrolu nad tím, který účet je povolený jako první**. Vybraný účet určí, kdo bude řídit zařízení a ovlivňuje možnosti správy.

## <a name="mobile-device-management"></a>Správa mobilních zařízení
Microsoft Intune, součást Enterprise Mobility + Security, je cloudový systém MDM, který spravuje zařízení připojená k vašemu tenantovi. podobně jako Office 365 intune používá službu Azure AD pro správu identit, takže zaměstnanci používají stejné přihlašovací údaje k registraci zařízení v intune, které používají pro přihlášení k Office 365. Intune také podporuje zařízení s jinými operačními systémy, jako jsou iOS a Android, a poskytuje tak kompletní řešení MDM. pro účely tohoto průvodce se zaměříme na použití intune pro povolení nasazení do interní sítě pomocí HoloLens 2.
> [!Important] 
> Je nutné mít správu mobilních zařízení. Pokud ho ještě nemáte nastavené, postupujte podle pokynů v této příručce a začněte s Intune.

> [!Important]
> Aby bylo možné používat Průvodce, je třeba zadat účet služby Azure AD.

> [!Note] 
> víc systémů MDM podporuje Windows 10 a podporuje i většinu scénářů nasazení osobních i podnikových zařízení. mezi poskytovatele MDM podporující Windows 10 Holographic patří: MobileIron a další. Většina špičkových dodavatelů MDM už podporuje integraci s Azure AD. Nejaktuálnější seznam dodavatelů MDM, kteří podporují Azure AD, najdete v [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Přístup k síti 
Příručky k Dynamics 365 jsou cloudové aplikace. Pokud správce sítě obsahuje seznam schválení, může být nutné přidat IP adresy nebo koncové body, které jsou vyžadovány pro připojení k serverům Dynamics 365. [Přečtěte si další informace o odblokování IP adres a adres URL](/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Certifikáty
Certifikáty zlepšují zabezpečení tím, že poskytují ověřování účtu, Wi-Fi ověřování, šifrování sítě VPN a šifrování SSL webového obsahu. I když správci můžou certifikáty na zařízeních spravovat ručně prostřednictvím zřizovacích balíčků, je osvědčeným postupem použití systému MDM ke správě certifikátů v celém celém životním cyklu – od registrace po obnovení a odvolání. 

Systém MDM může tyto certifikáty po registraci automaticky nasadit do úložišť certifikátů zařízení (Pokud váš systém MDM podporuje **Simple Certificate Enrollment Protocol (SCEP)** nebo **veřejného klíče kryptografie #12 (PKCS # 12)**). [Seznamte se s typy a profily certifikátů, které používáte s Microsoft Intune](/mem/intune/protect/certificates-configure). MDM taky může dotazovat a odstraňovat zaregistrované klientské certifikáty nebo aktivovat novou žádost o registraci před vypršením platnosti aktuálního certifikátu.

pokud jsou vaše systémy MDM už pro certifikáty nakonfigurované, [příprava certifikátů a profilů sítě pro HoloLens 2](/hololens/hololens-certificates-network) vám umožní začít nasazovat certifikáty a profily pro zařízení HoloLens 2.

## <a name="scep"></a>SCEP

Pro nasazení SCEP se vyžadují následující služby s výjimkou proxy serveru webových aplikací.

- [Certifikační autorita](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Role serveru NDES](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Připojovací](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Také je nutné publikovat adresu URL služby NDES externě pro vaši podnikovou síť pomocí [proxy aplikací služby Azure AD nebo Web Access proxy serveru](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application). Můžete také použít jiný reverzní proxy server, který si vyberete.

![Tok dat SCEP.](./images/hololens2-scep-info-flow.png)

Pokud vaše síť ještě nepodporuje SCEP, nebo si nejste jistí, jestli je vaše síť správně nastavená pro SCEP s Intune, referenční informace  [ke konfiguraci infrastruktury pro podporu protokolu SCEP s Intune](/mem/intune/protect/certificates-scep-configure).

pokud už vaše infrastruktura podporuje SCEP, budete muset [vytvořit](/mem/intune/protect/certificates-profile-scep) [profil](/mem/configmgr/protect/deploy-use/create-certificate-profiles) pro každý certifikát SCEP, který bude používat HoloLens 2. Pokud máte problémy s protokolem SCEP, pomocí [Poradce při potížích s používáním profilů certifikátů SCEP zřiďte certifikáty s Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Intune také podporuje použití privátních certifikátů a certifikátů PKCS (Public Key párové). referenční informace k [použití privátních a veřejných klíčů najdete v Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) .

## <a name="proxy"></a>Proxy server
Většina podnikových intranetových sítí využívá proxy server ke správě externích přenosů. pomocí HoloLens 2 můžete nakonfigurovat proxy server připojení k síti ethernet, Wi-Fi a VPN.

Existuje několik různých typů proxy serverů a způsobů konfigurace proxy serveru. Pro účely tohoto průvodce jsme se rozhodli zvolit **proxy Wi-Fi, nastavit přes adresu URL PAC a nasadit přes MDM**. To přináší výhody, které se nasazují prostřednictvím MDM automaticky, takže je možné soubor PAC aktualizovat místo použití serveru: Konfigurace portů a nakonec pomocí Wi-Fi proxy nakonfigurovat, aby se proxy server používal jenom pro jedno připojení Wi-Fi umožňující, aby se zařízení pořád používala v případě připojení k jinému umístění.

další podrobnosti o nastaveních proxy serveru pro Windows 10 najdete v tématu [vytvoření profilu Wi-Fi pro zařízení v Microsoft Intune – Azure](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Obchodní aplikace 
přestože je možné nainstalovat několik aplikací prostřednictvím Microsoft Store, je pravděpodobně vaše vlastní aplikace, kterou jste vytvořili speciálně pro použití ve smíšené realitě. Tyto vlastní aplikace distribuované v celé organizaci pro vaši firmu se nazývají obchodní aplikace (LOB).
  
existuje několik způsobů, jak nasadit aplikace do zařízení HoloLens 2. aplikace se dají nasadit přímo přes MDM, Microsoft Store pro firmy (MSfB) nebo zkušebně načtené prostřednictvím zřizovacího balíčku. Pro účely tohoto průvodce budeme nasazovat aplikace přes MDM prostřednictvím použití požadované instalace aplikace. to umožní, aby se vaše obchodní aplikace po registraci automaticky stáhly do zařízení HoloLens.

Pro ty, které nemají vlastní objekt LOB, vám poskytneme ukázkovou aplikaci pro otestování tohoto toku nasazení. Tato aplikace bude MRTK s [Příklady](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) aplikace a už je předem sestavená a zabalená pro testování konceptu.

Další podrobnosti týkající se nasazení aplikace najdete v článku [Správa aplikací: Přehled](/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 podporuje pouze spouštění aplikací ARM64 pro UWP.

## <a name="guides-playbook"></a>PlayBook vodítek
Příručky používají prostředí Microsoft datatext jako úložiště dat pro aplikace průvodců. Je důležité porozumět většímu přehledu o tom, jak vaše datavzhledové prostředí komunikuje s vašimi aplikacemi a vaším klientem. V této příručce se nebudeme řídit, jak spravovat váš datatext, ale Přečtěte si [základní koncepty pro nasazení příruček dynamics 365 – dynamics 365 Mixed reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Firemní připojené nasazení – konfigurace](hololens2-corp-connected-configure.md)