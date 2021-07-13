---
title: Pokyny k infrastruktuře HoloLens
description: Seznamte se s pokyny pro infrastrukturu HoloLens zařízení, včetně podpory bezdrátové sítě, vzdálené pomoci a správy mobilních zařízení.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639280"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurace sítě pro HoloLens

Tato část dokumentu bude vyžadovat následující osoby:

1. Správce sítě s oprávněními k provedení změn proxy serveru nebo brány firewall
2. Azure Active Directory Admin
3. Správce mobilních Správce zařízení

## <a name="infrastructure-requirements"></a>Požadavky na infrastrukturu

HoloLens jádrem je mobilní zařízení Windows integrované s Azure.  Funguje nejlépe v komerčních prostředích s dostupností bezdrátové sítě (Wi-Fi) a přístupem k služby Microsoft.

Mezi důležité cloudové služby patří:

- Azure active directory (Azure AD)
- Windows Aktualizace (WU)

Komerční zákazníci budou potřebovat infrastrukturu správy podnikové mobility (EMM) nebo správy mobilních zařízení (MDM), aby HoloLens zařízení ve velkém měřítku.  V této příručce [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) příklad, i když každý poskytovatel s plnou podporou služby Microsoft Policy může HoloLens.  Zeptejte se poskytovatele správy mobilních zařízení, jestli podporuje HoloLens 2.

HoloLens podporuje omezenou sadu prostředí odpojených od cloudu.

### <a name="wireless-network-eap-support"></a>Podpora protokolu EAP bezdrátové sítě

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Specifické požadavky na síť

Ujistěte se, [že je v](hololens-offline.md) síťové bráně firewall povolený tento seznam koncových bodů. To umožní, HoloLens správně fungovat.

### <a name="remote-assist-specific-network-requirements"></a>Požadavky na síť specifické pro Remote Assist

1. Doporučená šířka pásma pro optimální výkon nástroje Remote Assist je 1,5 Mb/s. Další informace [najdete v podrobných požadavcích](/MicrosoftTeams/prepare-network) na síť.
**(Upozorňujeme, že pokud nemáte síť s rychlostí alespoň 1,5 Mb/s, remote assist bude i nadále fungovat. Může ale utrpět kvalita.**
1. Ujistěte se, že tyto porty a adresy URL jsou ve vaší síťové bráně firewall povolené, aby Microsoft Teams fungovaly. Nejnovější seznam portů [vám bude aktuální.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Další informace o konkrétních požadavcích [na síť pro remote assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Další informace o přípravě [sítě organizace na Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Průvodci konkrétními požadavky na síť

Průvodci ke stažení a používání aplikace vyžadují jenom síťový přístup.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Pokyny

> [!NOTE]
> Tento krok je nezbytný pouze v případě, že vaše společnost plánuje spravovat HoloLens.

1. Ujistěte se, že máte licenci Azure AD.
Další [HoloLens v požadavcích](hololens-licenses-requirements.md) na licence.

1. Pokud plánujete používat automatickou registraci, budete muset [nakonfigurovat registraci Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Ujistěte se, že jsou uživatelé vaší společnosti ve službě Azure Active Directory (Azure AD).
Pokud chcete přidat [uživatele, přečtěte](/azure/active-directory/fundamentals/add-users-azure-active-directory) si následující pokyny.

1. Doporučujeme, aby uživatelé, kteří potřebují podobné licence, byli přidáni do stejné skupiny.
    1. [Vytvoření skupiny](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Přidání uživatelů do skupin](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Zajistěte, aby uživatelům (nebo skupině uživatelů) vaší společnosti byly přiřazeny potřebné licence.
Pokud potřebujete přiřadit licence, postupujte podle [těchto pokynů.](/azure/active-directory/fundamentals/license-users-groups)

1. Tento krok proveďte jenom v případě, že se od uživatelů očekává, že si do vás zaregistrují zařízení HoloLens/Mobile (Existují tři možnosti). Tyto kroky zajistí, aby uživatelé vaší společnosti (nebo skupina uživatelů) mohli přidat zařízení.
    1. **Možnost 1:** Udejte všem uživatelům oprávnění k připojení zařízení k Azure AD.
**Přihlaste se k Azure Portal jako správce.**  >  **Azure Active Directory**  >  **Zařízení**  >  **Device Nastavení**  >
 **Nastavte možnost Uživatelé smí připojovat zařízení k Azure AD na *Vše.***

    1. **Možnost 2:** Udělit vybraným uživatelům nebo skupinám oprávnění pro připojení zařízení k Azure AD Přihlásit se k **Azure Portal** jako správce  >  **Azure Active Directory** Devices Device Nastavení Set Users may join devices to Azure AD to Selected Image that shows Configuration of Azure AD Joined Devices  >    >  **(Konfigurace**  >
 **** 
 zařízení připojených ke službě ![ Azure AD)](images/azure-ad-image.png)

    1. **Možnost 3:** Všem uživatelům můžete zablokovat připojení svých zařízení k doméně. To znamená, že všechna zařízení budou muset být ručně zaregistrovaná.

## <a name="mobile-device-manager-guidance"></a>Pokyny Správce zařízení mobilních aplikacích

### <a name="ongoing-device-management"></a>Průběžná správa zařízení

> [!NOTE]
> Tento krok je nezbytný pouze v případě, že vaše společnost plánuje spravovat HoloLens.

Průběžná správa zařízení bude záviset na infrastruktuře správy mobilních zařízení.  Většina má stejné obecné funkce, ale uživatelské rozhraní se může výrazně lišit.

1. [Poskytovatelé konfiguračních služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umožňují vytvářet a nasazovat nastavení správy pro zařízení ve vaší síti. Referenční informace [najdete v HoloLens csP.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)

1. [Zásady dodržování](/intune/device-compliance-get-started) předpisů jsou pravidla a nastavení, která zařízení musí splňovat, aby splňovala předpisy ve vaší podnikové infrastruktuře. Pomocí těchto zásad s podmíněným přístupem můžete blokovat přístup k prostředkům společnosti pro zařízení, která nedodržují předpisy. Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.

1. [Vytvořte zásady dodržování předpisů.](/intune/protect/compliance-policy-create-windows)

1. Podmíněný přístup umožňuje nebo odmítá mobilním zařízením a mobilním aplikacím přístup k prostředkům společnosti. K dispozici jsou dva užitečné dokumenty: [Plánování nasazení certifikační autority a](/azure/active-directory/conditional-access/plan-conditional-access) osvědčené [postupy.](/azure/active-directory/conditional-access/best-practices)

1. [Tento článek](/intune/fundamentals/windows-holographic-for-business) popisuje nástroje pro správu Intune pro HoloLens.

1. [Vytvoření profilu zařízení](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Správa aktualizací

Intune obsahuje funkci s názvem Aktualizační okruhy pro Windows 10 zařízení, včetně HoloLens 2 a HoloLens v1 (s Holographic for Business). Aktualizační okruhy obsahují skupinu nastavení, která určují, jak a kdy se mají aktualizace instalovat.

Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat.  Můžete se také rozhodnout pozastavit aktualizace po neomezenou dobu, dokud nebude aktualizace připravená.

Přečtěte si další [informace o konfiguraci aktualizačních okruhů pomocí Intune.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Správa aplikací

Správa HoloLens aplikací prostřednictvím:

1. Microsoft Store  
  The Microsoft Store is the best way to distribute and consume applications on HoloLens.  K dispozici je skvělá sada základních aplikací HoloLens jsou už ve Storu k dispozici, nebo můžete [publikovat vlastní](/windows/uwp/publish/).  
  Všechny aplikace ve Storu jsou veřejně dostupné všem, ale pokud to není přijatelné, Microsoft Store pro firmy.  

1. [Microsoft Store pro firmy](/microsoft-store/)  
  Microsoft Store pro firmy a Education je vlastní obchod pro vaše podnikové prostředí.  Umožňuje používat integrované Microsoft Store a Windows 10 HoloLens k vyhledání, získání, distribuci a správě aplikací pro vaši organizaci.  Umožňuje také nasazovat aplikace, které jsou specifické pro vaše komerční prostředí, ale ne pro celý svět.

1. Nasazení a správa aplikací přes Intune nebo jiné řešení pro správu mobilních zařízení  
  Většina řešení pro správu mobilních zařízení, včetně Intune, poskytuje způsob, jak nasadit obchodní aplikace přímo do sady zaregistrovaných zařízení.  Informace o instalaci aplikací [Intune najdete v tomto článku.](/intune/apps-deploy)

1. _nedoporučuje se_ Portál zařízení  
  Aplikace se také instalují do HoloLens přímo pomocí Windows Portál zařízení.  To se nedoporučuje, protože pro používání portálu zařízení musí být povolený vývojářský režim.

Přečtěte si další [informace o instalaci aplikací na HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certifikáty

Certifikáty můžete distribuovat prostřednictvím poskytovatele MDM. Pokud vaše společnost vyžaduje certifikáty, Intune podporuje PKCS, PFX a SCEP. Je důležité pochopit, který certifikát je pro vaši společnost správný. Pokud chcete [zjistit, který](/intune/protect/certificates-configure) certifikát je pro vás nejlepší, projděte si dokumentaci ke konfiguracím certifikátů. Pokud plánujete používat certifikáty pro ověřování HoloLens, pfx nebo SCEP může být pro vás to pravé.

Informace o používání [scep najdete v následujících krocích.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Postup upgradu na Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (komerční sada) je určená jenom HoloLens 1. generace. Profil se nebude aplikovat na HoloLens 2 zařízení.

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

Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení [veřejného HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) MDM potřebujete vlastní nastavení a úplnou konfiguraci XML, přečtěte si pokyny k beznaiosku.

## <a name="certificates-and-authentication"></a>Certifikáty a ověřování

Certifikáty je možné nasadit prostřednictvím MDM (viz "certifikáty" v části [MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Certifikáty je také možné nasadit do HoloLens prostřednictvím zřizování balíčků. Další [informace HoloLens v tématu o](hololens-provisioning.md) zřizování prostředků.

### <a name="additional-intune-quick-links"></a>Další rychlé odkazy pro Intune

1. [Vytvoření profilů:](/intune/configuration/device-profile-create) Profily umožňují přidávat a konfigurovat nastavení, která se budou předát do zařízení ve vaší organizaci.

