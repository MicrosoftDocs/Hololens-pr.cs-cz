---
title: Průvodce nasazením – Firemní zařízení HoloLens 2 s průvodci Dynamics 365 – příprava
description: Zjistěte, jak se připravit na registraci zařízení HoloLens 2 přes podnikovou připojenou síť pomocí průvodců Dynamics 365.
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377632"
---
# <a name="prepare---corporate-connected-guide"></a>Příprava – Průvodce podnikovým propojením
## <a name="infrastructure-essentials"></a>Základy infrastruktury
Pro osobní i firemní nasazení je systém Mobile Správa zařízení (MDM) základní infrastrukturou, která se vyžaduje k nasazení a správě zařízení Windows 10, zejména HoloLens 2. Jako [Azure AD Premium identity](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) se doporučuje předplatné, které je potřeba **k** podpoře určitých funkcí.

> [!NOTE]
> I když je HoloLens 2 nasazený a spravovaný jako mobilní zařízení, obvykle se používá jako sdílené zařízení mezi mnoha uživateli.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD je cloudová adresářová služba, která poskytuje správu identit a přístupu. Organizace, které používají systém Microsoft Office 365 nebo Intune, už používají Azure AD, která má tři edice: Free, Premium P1 a Premium P2 (viz edice [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Všechny edice podporují registraci zařízení v Azure AD, ale k povolení automatické registrace MDM, kterou budeme později používat v této příručce, se vyžaduje Premium P1.
> [!Important]
> Je nezbytné mít Službu Azure AD, protože zařízení HoloLens nepodporují připojení k místní službě AD. Pokud ještě nemáte nastavenou službu Azure AD, postupujte podle pokynů k zahájení práce a vytvoření nového [tenanta](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)v Azure Active Directory .

## <a name="identity-management"></a>Správa identit
V tomto průvodci budou [použitou](https://docs.microsoft.com/hololens/hololens-identity) identitou účty Azure AD. Účty Azure AD mají několik výhod, například:
- Zaměstnanci používají svůj účet Azure AD k registraci zařízení v Azure AD a mohou ho automaticky zaregistrovat v řešení MDM organizace (Azure AD + MDM – vyžaduje předplatné [Azure AD Premium předplatného).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Účty Azure AD mají další [možnosti ověřování](https://docs.microsoft.com/hololens/hololens-identity) prostřednictvím [Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Kromě přihlášení Iris se uživatelé mohou přihlašovat z jiného zařízení nebo používat klíče zabezpečení FIDO.

> [!WARNING] 
> Zaměstnanci mohou k inicializaci zařízení použít jenom jeden účet, takže je nezbytné, aby vaše organizace nejdřív **povolila, který účet je povolený.** Zvolený účet určí, kdo zařízení řídí, a ovlivní možnosti správy.

## <a name="mobile-device-management"></a>Správa mobilních zařízení
Microsoft Intune, který je Enterprise Mobility + Security, je cloudový systém MDM, který spravuje zařízení připojená k vašemu tenantovi. Stejně jako Office 365 používá Intune ke správě identit Azure AD, takže zaměstnanci používají stejné přihlašovací údaje k registraci zařízení v Intune, která používají pro přihlášení k Office 365. Intune také podporuje zařízení s jinými operačními systémy, jako je iOS a Android, a poskytuje tak kompletní řešení MDM. Pro účely této příručky se zaměříme na použití Intune k povolení nasazení do interní sítě pomocí HoloLens 2.
> [!Important] 
> Je nezbytné mít Mobile Správa zařízení. Pokud ho ještě nemáte nastavený, postupujte podle této příručky a pokynů Začínáme s Intune.

> [!Important]
> Abyste mohli používat příručky, vyžaduje se účet Azure AD.

> [!Note] 
> Několik systémů MDM podporuje Windows 10 většina podporuje scénáře nasazení osobních a firemních zařízení. Mezi poskytovatele MDM, kteří Windows 10 Holographic, patří: AirWatch, MobileIron a další. Většina špičkových dodavatelů MDM už integraci s Azure AD podporuje. Aktuální seznam dodavatelů MDM, kteří podporují Azure AD, najdete v Azure Marketplace [.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Přístup k síti 
Příručky Dynamics 365 jsou cloudové aplikace. Pokud má správce sítě seznam schválení, může potřebovat přidat IP adresy nebo koncové body potřebné pro připojení k serverům Dynamics 365. [Přečtěte si další informace o odblokování IP adres a adres URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certifikáty
Certifikáty pomáhají zlepšit zabezpečení tím, že poskytují ověřování účtu, Wi-Fi ověřování, šifrování sítě VPN a šifrování SSL webového obsahu. I když správci můžou spravovat certifikáty na zařízeních ručně prostřednictvím zřizování balíčků, je osvědčeným postupem používat systém MDM ke správě těchto certifikátů v průběhu celého jejich životního cyklu – od registrace až po obnovení a odvolání. 

Systém MDM může tyto certifikáty automaticky nasadit do úložišť certifikátů zařízení po jejich registraci (pokud systém MDM podporuje **standardy Simple Certificate Enrollment Protocol (SCEP)** nebo **PKCS#12**( Public Key Cryptography Standards #12). [Seznamte se s typy certifikátů a profily, které používáte s Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). MDM může také dotazovat a odstraňovat zaregistrované klientské certifikáty nebo aktivovat novou žádost o registraci před vypršením platnosti aktuálního certifikátu.
 
Pokud už máte systémy MDM nakonfigurované pro certifikáty, začněte nasazovat certifikáty a profily pro zařízení HoloLens 2 v tématu Příprava certifikátů a síťových profilů pro [HoloLens](https://docs.microsoft.com/hololens/hololens-certificates-network) 2.

## <a name="scep"></a>SCEP

Pro nasazení SCEP jsou vyžadovány následující služby s výjimkou webového proxy aplikací Serveru.
- [Certifikační autorita](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Role serveru NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Connector](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Musíte také publikovat adresu URL NDES mimo vaši podnikovou síť pomocí proxy aplikací [služby Azure AD nebo Web Access proxy serveru.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Můžete také použít jiný reverzní proxy server podle vašeho výběru.

![Tok dat SCEP](./images/hololens2-scep-info-flow.png)

Pokud vaše síť ještě SCEP nepodporuje nebo si nejste jistí, jestli je vaše síť správně nastavená pro SCEP s Intune, najdete informace v tématu Konfigurace infrastruktury pro podporu SCEP s [Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Pokud vaše infrastruktura už SCEP podporuje, [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) budete muset vytvořit profil pro každý certifikát SCEP, který bude HoloLens 2 používat. [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) Pokud máte problémy s SCEP, použijte řešení potíží s používáním profilů [certifikátů SCEP](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)ke zřízení certifikátů s Microsoft Intune .

## <a name="pkcs"></a>PKCS
Intune také podporuje použití certifikátů PKCS (private and public key pair). Další informace najdete v části Použití certifikátů [privátních Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) veřejných klíčů v nástroji .

## <a name="proxy"></a>Proxy server
Většina podnikových intranetových sítí ke správě externích přenosů využívá proxy server. Pomocí HoloLens 2 můžete nakonfigurovat síť proxy server připojení k síti ethernet, Wi-Fi sítě a VPN.

Existuje několik různých typů proxy serveru a způsobů konfigurace proxy serveru. Pro účely této příručky volíme **proxy wi-fi,** nastavíme adresu URL PAC a nasadíme ji přes MDM. To má tu výhodu, že se nasazovat automaticky přes MDM, protože je možné aktualizovat soubor PAC místo konfigurace server:port a nakonec pomocí proxy serveru Wi-Fi nakonfigurovat proxy server tak, aby se používal jenom pro jedno připojení Wi-Fi, což umožňuje, aby se zařízení i nadále používala, pokud jsou připojená v jiném umístění. 


Další podrobnosti o nastavení proxy serveru pro Windows 10 najdete v tématu Vytvoření profilu Wi-Fi pro zařízení v [Microsoft Intune – Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Obchodní aplikace 
I když je možné několik aplikací nainstalovat prostřednictvím Microsoft Store, je pravděpodobné, že máte vlastní aplikaci, kterou jste vytvořili speciálně pro použití v hybridní realitě. Tyto vlastní aplikace distribuované ve vaší organizaci pro vaši firmu se nazývají obchodní aplikace.
  
Existuje několik způsobů, jak nasadit aplikace na zařízení HoloLens 2. Aplikace je možné nasadit přímo prostřednictvím MDM, Microsoft Store pro firmy (MSfB) nebo předinstalovat prostřednictvím zřizovacího balíčku. Pro potřeby této příručky budeme nasazovat aplikace přes MDM pomocí požadované instalace aplikace. To umožní, aby se vaše obchodní aplikace po dokončení registrace automaticky stáhly do zařízení HoloLens.

Pro ty z vás, kteří nemají vlastní obchodní objekt, poskytneme ukázkovou aplikaci pro testování tohoto toku nasazení. Tato aplikace bude [ukázková aplikace MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) a už je předem sestavená a zabalená pro testování konceptu.
 
Další podrobnosti týkající se nasazení aplikací najdete v tématu [Správa aplikací: Přehled](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 podporuje spouštění jenom aplikací UPW ARM64.

## <a name="guides-playbook"></a>Playbook průvodců
Příručky používají prostředí Microsoft Dataverse jako úložiště dat pro vaše aplikace guides. Je důležité pochopit širší obrázek toho, jak vaše prostředí Dataverse komunikuje s vašimi aplikacemi Guides a vaším tenantem. V této příručce nebudeme prohazovat, jak spravovat dataverse, ale projděte si základní koncepty nasazení průvodců [Dynamics 365 – Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Nasazení připojené k podnikové síti – Konfigurace](hololens2-corp-connected-configure.md)