---
title: Pokyny pro infrastrukturu HoloLens
description: Přečtěte si o pravidlech infrastruktury pro zařízení HoloLens, včetně podpory bezdrátové sítě, vzdálené pomoci a správy mobilních zařízení.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379197"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurace sítě pro HoloLens

Tato část dokumentu bude vyžadovat následující uživatele:

1. Správce sítě s oprávněními k provedení změn na proxy serveru nebo bráně firewall
2. Správce Azure Active Directory
3. Správce mobilních Správce zařízení

## <a name="infrastructure-requirements"></a>Požadavky na infrastrukturu

HoloLens je ve svém jádru mobilní zařízení s Windows, které je integrované s Azure.  Funguje nejlépe v komerčních prostředích s dostupností bezdrátové sítě (Wi-Fi) a přístup ke službám Microsoftu.

Mezi důležité cloudové služby patří:

- Azure Active Directory (Azure AD)
- Web Windows Update (WU)

Komerční zákazníci budou potřebovat infrastrukturu pro správu mobilních zařízení (EMM) nebo správu mobilních zařízení (MDM), aby mohli spravovat zařízení HoloLens ve velkém měřítku.  Tato příručka používá [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako příklad, i když libovolný poskytovatel s plnou podporou pro zásady Microsoftu podporuje HoloLens.  Zeptejte se poskytovatele správy mobilních zařízení, pokud podporují HoloLens 2.

HoloLens podporuje omezené sady prostředí odpojených do cloudu.

### <a name="wireless-network-eap-support"></a>Podpora protokolu EAP bezdrátové sítě

- Protokol PEAP-MS-CHAPv2
- PROTOKOL PEAP-TLS
- TLS
- TTLS – CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS – TLS

### <a name="hololens-specific-network-requirements"></a>Požadavky na síť specifické pro HoloLens

Ujistěte se, že se [Tento seznam](hololens-offline.md) koncových bodů povoluje v bráně firewall vaší sítě. To umožní funkci HoloLens správně fungovat.

### <a name="remote-assist-specific-network-requirements"></a>Požadavky na určitou síť pro vzdálenou pomoc

1. Doporučená šířka pásma pro optimální výkon funkce Remote Assist je 1,5 MB/s. Další informace najdete v [podrobnostech o požadavcích na síť](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .
**(Pokud v síti nemáte síťové rychlosti minimálně 1,5 MB/s, bude Vzdálená pomoc pořád fungovat. Kvalita ale může mít zhoršený vliv.**
1. Ujistěte se, že tyto porty a adresy URL jsou povolené v bráně firewall sítě, aby mohly Microsoft Teams fungovat. [Seznamte se s nejnovějšími porty](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)v aktuálním stavu.

- Přečtěte si další informace o konkrétních [požadavcích na síť pro vzdálenou pomoc](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Další informace o tom, jak [připravit síť vaší organizace pro Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Konkrétní požadavky na síť pro příručky

Příručky vyžadují přístup k síti pouze ke stažení a používání aplikace.

## <a name="azure-active-directory-guidance"></a>Pokyny pro Azure Active Directory

> [!NOTE]
> Tento krok je nezbytný pouze v případě, že vaše společnost plánuje správu HoloLens.

1. Ujistěte se, že máte licenci Azure AD.
Další informace najdete v [požadavcích na licence HoloLens](hololens-licenses-requirements.md) .

1. Pokud plánujete použití automatického zápisu, budete muset [nakonfigurovat registraci Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Ujistěte se, že jsou uživatelé vaší společnosti v Azure Active Directory (Azure AD).
Pokud chcete přidat uživatele, přečtěte si následující [pokyny](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) .

1. Doporučujeme, aby uživatelé, kteří potřebují podobné licence, přidali do stejné skupiny.
    1. [Vytvoření skupiny](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Přidat uživatele do skupin](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Ujistěte se, že uživatelé (nebo skupiny uživatelů) vaší společnosti mají přidělené potřebné licence.
Pokud potřebujete přiřadit licence, postupujte podle těchto [pokynů](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Tento krok proveďte jenom v případě, že se uživatelé chtějí zaregistrovat svoje zařízení HoloLens nebo mobilní zařízení (Existují tři možnosti) tyto kroky zajistí, že uživatelé společnosti (nebo skupiny uživatelů) můžou přidat zařízení.
    1. **Možnost 1:** Poskytněte všem uživatelům oprávnění k připojení zařízení ke službě Azure AD.
**Přihlaste se k Azure Portal jako správce**  >  . **Azure Active Directory**  >  **Zařízení**  >  **Nastavení zařízení**  >
 **Nastavení uživatelé můžou připojovat zařízení ke službě Azure AD *všem***

    1. **Možnost 2:** Udělení oprávnění vybraným uživatelům nebo skupinám k připojení zařízení k Azure AD **přihlášení k Azure Portal jako správce**  >  **Azure Active Directory**  >  **zařízení**  >  **nastavení zařízení**  >
 **Uživatelé můžou ke *zvolené* imagi připojit zařízení do Azure AD a** 
 ![ zobrazit tak konfiguraci zařízení připojených k Azure AD.](images/azure-ad-image.png)

    1. **Možnost 3:** Můžete zablokovat všem uživatelům připojení svých zařízení k doméně. To znamená, že všechna zařízení bude nutné zaregistrovat ručně.

## <a name="mobile-device-manager-guidance"></a>Doprovodné materiály pro Mobile Správce zařízení

### <a name="ongoing-device-management"></a>Probíhající Správa zařízení

> [!NOTE]
> Tento krok je nezbytný pouze v případě, že vaše společnost plánuje správu HoloLens.

Probíhající Správa zařízení bude záviset na infrastruktuře správy mobilních zařízení.  Většina má stejné obecné funkce, ale uživatelské rozhraní se může výrazně lišit.

1. [CSP (poskytovatelé konfigurační služby)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umožňují vytvářet a nasazovat nastavení správy pro zařízení ve vaší síti. Podívejte se na [seznam zprostředkovatelů HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) pro účely reference.

1. [Zásady dodržování předpisů](https://docs.microsoft.com/intune/device-compliance-get-started) jsou pravidla a nastavení, která musí zařízení splňovat, aby splňovala předpisy vaší podnikové infrastruktury. Pomocí těchto zásad s podmíněným přístupem Zablokujte přístup k prostředkům společnosti pro zařízení, která nedodržují předpisy. Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.

1. [Vytvořte zásady dodržování předpisů](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. Podmíněný přístup povoluje nebo zakazuje mobilním zařízením a mobilním aplikacím přístup k prostředkům společnosti. Užitečné dva dokumenty vám pomohou při [Plánování nasazení certifikační autority](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) a [osvědčených postupů](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [Tento článek](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) pojednává o nástrojích pro správu Intune pro HoloLens.

1. [Vytvoření profilu zařízení](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Správa aktualizací

Intune zahrnuje funkci nazvanou aktualizační kanály pro zařízení s Windows 10, včetně HoloLens 2 a HoloLens V1 (s holografickým pro firmy). Aktualizační kanály zahrnují skupinu nastavení, která určují, jak a kdy se mají aktualizace instalovat.

Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat.  Můžete se také rozhodnout pozastavit aktualizace po neomezenou dobu, dokud nebudete připraveni na aktualizaci.

Přečtěte si další informace o [konfiguraci aktualizačních kanálů s Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Správa aplikací

Spravovat aplikace HoloLens prostřednictvím:

1. Microsoft Store  
  Microsoft Store je nejlepším způsobem, jak distribuovat a využívat aplikace na HoloLens.  Ve Storu už je k dispozici skvělá sada základních aplikací HoloLens nebo můžete [publikovat vlastní](https://docs.microsoft.com/windows/uwp/publish/).  
  Všechny aplikace v obchodě jsou veřejně dostupné všem, ale pokud to není přijatelné, rezervujte Microsoft Store pro firmy.  

1. [Microsoft Store pro firmy](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store pro firmy a vzdělávání je vlastní úložiště pro vaše podnikové prostředí.  Umožňuje použít Microsoft Store integrovaný do Windows 10 a HoloLens k hledání, získávání, distribuci a správě aplikací pro vaši organizaci.  Umožňuje taky nasazovat aplikace, které jsou specifické pro vaše komerční prostředí, ale ne pro celý svět.

1. Nasazení a Správa aplikací přes Intune nebo jiné řešení pro správu mobilních zařízení  
  Většina řešení pro správu mobilních zařízení, včetně Intune, nabízí způsob, jak nasazovat obchodní aplikace přímo do sady zaregistrovaných zařízení.  Viz tento článek [instalace aplikace Intune](https://docs.microsoft.com/intune/apps-deploy).

1. _nedoporučuje se_ Portál zařízení  
  Aplikace můžete nainstalovat také přímo na HoloLens pomocí portálu zařízení Windows.  Tato možnost se nedoporučuje, protože je nutné povolit režim vývojářů, aby bylo možné používat portál zařízení.

Přečtěte si další informace o [instalaci aplikací na HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### <a name="certificates"></a>Certifikáty

Certifikáty můžete distribuovat prostřednictvím poskytovatele MDM. Pokud vaše společnost vyžaduje certifikáty, podporuje Intune PKCS, PFX a SCEP. Je důležité pochopit, který certifikát je pro vaši společnost nejvhodnější. Navštivte prosím dokumentaci [Konfigurace certifikátů](https://docs.microsoft.com/intune/protect/certificates-configure) a určete, který certifikát je pro vás nejvhodnější. Pokud máte v plánu používat certifikáty pro ověřování HoloLens, PFX nebo SCEP může být pro vás to pravé.

Informace o používání [scep najdete v následujících krocích.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Postup upgradu na Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (komerční sada) je určená jenom pro zařízení HoloLens 1. generace. Profil se nebude aplikovat na zařízení HoloLens 2.

Pokyny k upgradu na komerční sadu najdete v dokumentaci [k holografickému](https://docs.microsoft.com/intune/configuration/holographic-upgrade) upgradu.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Konfigurace bezobrazovkového režimu pomocí Microsoft Intune

1. Synchronizace Microsoft Store s Intune (viz následující [pokyny).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Kontrola nastavení aplikace
    1. Přihlaste se ke svému Microsoft Store Business.
    1. **Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**
        >[!NOTE]
        >Pokud nevidíte aplikaci, kterou chcete, budete ji muset "získat" vyhledáním aplikace v obchodě. Klikněte na panel Hledat v pravém horním rohu > zadejte název aplikace > klikněte na aplikaci **> vyberte Získat.**
    1. Pokud aplikace v Intune > **Client Apps > Apps** nevidíte, možná budete muset aplikace [znovu](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) synchronizovat.

1. [Vytvoření profilu zařízení pro beznaioskový režim](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Různé uživatele můžete nakonfigurovat tak, aby měli různá prostředí v bezobrazovkovém režimu. Jako typ přihlášení uživatele můžete použít Azure AD. Tato možnost je ale dostupná jenom v bezobrazovkovém režimu s více aplikacemi. Bezobrazovový režim s více aplikacemi bude fungovat jenom s jednou aplikací a několika aplikacemi.

![Obrázek znázorňuje konfiguraci bezobrazovkového režimu v Intune](images/aad-kioskmode.png)

Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud potřebujete k nastavení veřejného terminálu ve službě MDM použít vlastní nastavení a úplnou konfiguraci XML, přečtěte si pokyny k beznaiosku [HoloLens.](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

## <a name="certificates-and-authentication"></a>Certifikáty a ověřování

Certifikáty je možné nasadit prostřednictvím MDM (viz "certifikáty" v části [MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Certifikáty je také možné nasadit do HoloLens prostřednictvím zřizování balíčků. Další informace [najdete v tématu Zřizování HoloLens.](hololens-provisioning.md)

### <a name="additional-intune-quick-links"></a>Další rychlé odkazy pro Intune

1. [Vytvoření profilů:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profily umožňují přidávat a konfigurovat nastavení, která se budou předát do zařízení ve vaší organizaci.

