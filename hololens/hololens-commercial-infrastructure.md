---
title: Pokyny pro infrastrukturu pro HoloLens
description: přečtěte si o pokynech infrastruktury pro HoloLens zařízení, včetně podpory bezdrátové sítě, vzdálené pomoci a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035839"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurace sítě pro HoloLens

Tato část dokumentu bude vyžadovat následující uživatele:

1. Správce sítě s oprávněními k provedení změn na proxy serveru nebo bráně firewall
2. Azure Active Directory Správ
3. Správce mobilních Správce zařízení

## <a name="infrastructure-requirements"></a>Požadavky na infrastrukturu

HoloLens je v jádru Windows mobilní zařízení integrované s Azure.  funguje nejlépe v komerčních prostředích s dostupností bezdrátové sítě (wi-fi) a přístup k služby Microsoft.

Mezi důležité cloudové služby patří:

- Azure Active Directory (Azure AD)
- Windows Aktualizace (WU)

komerční zákazníci budou potřebovat infrastrukturu pro správu podnikových zařízení (EMM) nebo správu mobilních zařízení (MDM) pro správu HoloLensch zařízení ve velkém měřítku.  tato příručka používá [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako příklad, i když kterýkoli poskytovatel s plnou podporou pro zásady microsoftu může HoloLens podporovat.  zeptejte se poskytovatele správy mobilních zařízení, pokud podporuje HoloLens 2.

HoloLens podporuje omezené množství prostředí odpojených do cloudu.

### <a name="wireless-network-eap-support"></a>Podpora protokolu EAP bezdrátové sítě

- Protokol PEAP-MS-CHAPv2
- PROTOKOL PEAP-TLS
- TLS
- TTLS – CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS – TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Specifické požadavky na síť

Ujistěte se, že se [Tento seznam](hololens-offline.md) koncových bodů povoluje v bráně firewall vaší sítě. to umožní, aby HoloLens správně fungovalo.

### <a name="remote-assist-specific-network-requirements"></a>Požadavky na určitou síť pro vzdálenou pomoc

1. Doporučená šířka pásma pro optimální výkon funkce Remote Assist je 1,5 MB/s. Další informace najdete v [podrobnostech o požadavcích na síť](/MicrosoftTeams/prepare-network) .
**(Pokud v síti nemáte síťové rychlosti minimálně 1,5 MB/s, bude Vzdálená pomoc pořád fungovat. Kvalita ale může mít zhoršený vliv.**
1. ujistěte se, že tyto porty a adresy url jsou povoleny v bráně firewall sítě, aby bylo možné povolit funkci Microsoft Teams. [Seznamte se s nejnovějšími porty](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)v aktuálním stavu.

- Přečtěte si další informace o konkrétních [požadavcích na síť pro vzdálenou pomoc](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Přečtěte si další informace o tom, jak [připravit síť vaší organizace pro Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Konkrétní požadavky na síť pro příručky

Příručky vyžadují přístup k síti pouze ke stažení a používání aplikace.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Směrné

> [!NOTE]
> Tento krok je nezbytný pouze v případě, že vaše společnost plánuje správu HoloLens.

1. Ujistěte se, že máte licenci Azure AD.
další informace prosím [HoloLens požadavky na licence](hololens-licenses-requirements.md) .

1. Pokud plánujete použití automatického zápisu, budete muset [nakonfigurovat registraci Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Ujistěte se, že jsou uživatelé vaší společnosti v Azure Active Directory (Azure AD).
Pokud chcete přidat uživatele, přečtěte si následující [pokyny](/azure/active-directory/fundamentals/add-users-azure-active-directory) .

1. Doporučujeme, aby uživatelé, kteří potřebují podobné licence, přidali do stejné skupiny.
    1. [Vytvoření skupiny](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Přidat uživatele do skupin](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Ujistěte se, že uživatelé (nebo skupiny uživatelů) vaší společnosti mají přidělené potřebné licence.
Pokud potřebujete přiřadit licence, postupujte podle těchto [pokynů](/azure/active-directory/fundamentals/license-users-groups).

1. tento krok proveďte jenom v případě, že se uživatelům očekává, aby si do sebe zaregistrovali své HoloLens zařízení/Mobile (existují tři možnosti) tyto kroky zajistí, že uživatelé společnosti (nebo skupina uživatelů) můžou přidat zařízení.
    1. **Možnost 1:** Poskytněte všem uživatelům oprávnění k připojení zařízení ke službě Azure AD.
**Přihlaste se k Azure Portal jako správce**  >  . **Azure Active Directory**  >  **Zařízení**  >  **Nastavení zařízení**  >
 **Nastavení uživatelé můžou připojovat zařízení ke službě Azure AD *všem***

    1. **Možnost 2:** udělit vybraným uživatelům nebo skupinám oprávnění k připojení zařízení ke službě Azure AD **přihlášení k Azure Portal jako správce**  >  **Azure Active Directory**  >  **zařízení**  >  **Nastavení**  >
 **nastavení uživatelé můžou ke *zvolené* imagi připojovat zařízení do azure ad** 
 ![ , které zobrazuje konfiguraci zařízení připojených k azure ad.](images/azure-ad-image.png)

    1. **Možnost 3:** Můžete zablokovat všem uživatelům připojení svých zařízení k doméně. To znamená, že všechna zařízení bude nutné zaregistrovat ručně.

## <a name="mobile-device-manager-guidance"></a>Doprovodné materiály pro Mobile Správce zařízení

### <a name="ongoing-device-management"></a>Probíhající Správa zařízení

> [!NOTE]
> Tento krok je nutný jenom v případě, že vaše společnost plánuje správu HoloLens.

Probíhající Správa zařízení bude záviset na infrastruktuře správy mobilních zařízení.  Většina má stejné obecné funkce, ale uživatelské rozhraní se může výrazně lišit.

1. [CSP (poskytovatelé konfigurační služby)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umožňují vytvářet a nasazovat nastavení správy pro zařízení ve vaší síti. podívejte se na [seznam HoloLens csp](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) pro referenci.

1. [Zásady dodržování předpisů](/intune/device-compliance-get-started) jsou pravidla a nastavení, která musí zařízení splňovat, aby splňovala předpisy vaší podnikové infrastruktury. Pomocí těchto zásad s podmíněným přístupem Zablokujte přístup k prostředkům společnosti pro zařízení, která nedodržují předpisy. Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.

1. [Vytvořte zásady dodržování předpisů](/intune/protect/compliance-policy-create-windows).

1. Podmíněný přístup povoluje nebo zakazuje mobilním zařízením a mobilním aplikacím přístup k prostředkům společnosti. Užitečné dva dokumenty vám pomohou při [Plánování nasazení certifikační autority](/azure/active-directory/conditional-access/plan-conditional-access) a [osvědčených postupů](/azure/active-directory/conditional-access/best-practices).

1. [Tento článek](/intune/fundamentals/windows-holographic-for-business) pojednává o nástrojích pro správu Intune pro HoloLens.

1. [Vytvoření profilu zařízení](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Správa aktualizací

intune zahrnuje funkci nazvanou aktualizační kanály pro Windows 10 zařízení, včetně HoloLens 2 a HoloLens v1 (s holografickým pro firmy). Aktualizační kanály zahrnují skupinu nastavení, která určují, jak a kdy se mají aktualizace instalovat.

Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat.  Můžete se také rozhodnout pozastavit aktualizace po neomezenou dobu, dokud nebudete připraveni na aktualizaci.

Přečtěte si další informace o [konfiguraci aktualizačních kanálů s Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Správa aplikací

spravovat HoloLens aplikací prostřednictvím:

1. Microsoft Store  
  Microsoft Store je nejlepším způsobem, jak distribuovat a využívat aplikace v HoloLens.  ve storu je k dispozici skvělou sadu základních HoloLens aplikací, které jsou již k dispozici, nebo můžete [publikovat vlastní](/windows/uwp/publish/).  
  všechny aplikace v úložišti jsou veřejně dostupné všem, ale pokud to není přijatelné, rezervujte Microsoft Store pro firmy.  

1. [Microsoft Store pro firmy](/microsoft-store/)  
  Microsoft Store pro firmy a vzdělávání je vlastní úložiště pro vaše podnikové prostředí.  umožňuje použít Microsoft Store integrovaný do Windows 10 a HoloLens k hledání, získávání, distribuci a správě aplikací pro vaši organizaci.  Umožňuje taky nasazovat aplikace, které jsou specifické pro vaše komerční prostředí, ale ne pro celý svět.

1. Nasazení a Správa aplikací přes Intune nebo jiné řešení pro správu mobilních zařízení  
  Většina řešení pro správu mobilních zařízení, včetně Intune, nabízí způsob, jak nasazovat obchodní aplikace přímo do sady zaregistrovaných zařízení.  Viz tento článek [instalace aplikace Intune](/intune/apps-deploy).

1. _nedoporučuje se_ Portál zařízení  
  aplikace lze také nainstalovat do HoloLens přímo pomocí portálu Windows zařízení.  Tato možnost se nedoporučuje, protože je nutné povolit režim vývojářů, aby bylo možné používat portál zařízení.

Přečtěte si další informace o [instalaci aplikací na HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certifikáty

Certifikáty můžete distribuovat prostřednictvím poskytovatele MDM. Pokud vaše společnost vyžaduje certifikáty, podporuje Intune PKCS, PFX a SCEP. Je důležité pochopit, který certifikát je pro vaši společnost nejvhodnější. Navštivte prosím dokumentaci [Konfigurace certifikátů](/intune/protect/certificates-configure) a určete, který certifikát je pro vás nejvhodnější. Pokud máte v plánu používat certifikáty pro HoloLens ověřování, pfx nebo SCEP může být pro vás to pravé.

Informace o používání [scep najdete v následujících krocích.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Postup upgradu na Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (komerční sada) je určená pouze HoloLens 1. generace. Profil se nebude aplikovat na HoloLens 2 zařízení.

Pokyny k upgradu na komerční sadu najdete v dokumentaci [k holografickému](/intune/configuration/holographic-upgrade) upgradu.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Konfigurace bezobrazovkového režimu pomocí Microsoft Intune

1. Synchronizace Microsoft Store s Intune (viz následující [pokyny).](/intune/apps/windows-store-for-business)

1. Kontrola nastavení aplikace
    1. Přihlaste se ke svému Microsoft Store Business.
    1. **Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**
        >[!NOTE]
        >Pokud nevidíte aplikaci, kterou chcete, budete ji muset "získat" vyhledáním aplikace v obchodě. Klikněte na panel Hledat v pravém horním rohu > zadejte název aplikace > klikněte na aplikaci > **vyberte Získat.**
    1. Pokud aplikace v Intune > **Client Apps > Apps** nevidíte, možná budete muset aplikace [znovu](/intune/apps/windows-store-for-business#synchronize-apps) synchronizovat.

1. [Vytvoření profilu zařízení pro beznaioskový režim](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Různé uživatele můžete nakonfigurovat tak, aby měli různá prostředí v bezobrazovkovém režimu. Jako typ přihlášení uživatele můžete použít Azure AD. Tato možnost je ale dostupná jenom v bezobrazovkovém režimu s více aplikacemi. Bezobrazovový režim s více aplikacemi bude fungovat jenom s jednou aplikací a několika aplikacemi.

![Obrázek znázorňuje konfiguraci bezobrazovkového režimu v Intune](images/aad-kioskmode.png)

Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení [veřejného HoloLens](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) MDM potřebujete použít vlastní nastavení a úplnou konfiguraci XML, přečtěte si pokyny k beznaiosku.

## <a name="certificates-and-authentication"></a>Certifikáty a ověřování

Certifikáty je možné nasadit prostřednictvím MDM (viz "certifikáty" v části [MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Certifikáty je také možné nasadit do služby HoloLens prostřednictvím zřizování balíčků. Další [informace HoloLens v tématu o](hololens-provisioning.md) zřizování prostředků.

### <a name="additional-intune-quick-links"></a>Další rychlé odkazy pro Intune

1. [Vytvoření profilů:](/intune/configuration/device-profile-create) Profily umožňují přidávat a konfigurovat nastavení, která se budou předá do zařízení ve vaší organizaci.

