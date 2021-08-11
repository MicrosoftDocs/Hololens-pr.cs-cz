---
title: příprava certifikátů a profilů sítě pro HoloLens 2
description: naučte se konfigurovat, používat, nasazovat a řešit potíže s certifikáty pro síť na zařízeních HoloLens 2 mixed reality.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d9b752c820af8dbceb2b6b9f3c7a7be4df910805b5a5014bb3e3650551392ce8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664313"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>příprava certifikátů a profilů sítě pro HoloLens 2

ověřování založené na certifikátech je běžný požadavek pro zákazníky, kteří používají HoloLens 2. Možná budete vyžadovat, aby se certifikáty pro přístup k Wi-Fi připojovaly k řešením VPN nebo pro přístup k interním prostředkům ve vaší organizaci.

vzhledem k tomu, že zařízení HoloLens 2 jsou obvykle připojená k Azure Active Directory (Azure AD) a spravovaná službou intune nebo jiným poskytovatelem mdm, bude nutné tyto Simple Certificate Enrollment Protocol certifikáty nasadit pomocí infrastruktury certifikátů (SCEP) nebo klíče PKCS (Public Key Cryptography standard), která je integrovaná s vaším řešením mdm. 

>[!NOTE]
> pokud nemáte poskytovatele MDM, můžete i nadále nasazovat certifikáty prostřednictvím [zřizovacího balíčku](hololens-provisioning.md#steps-for-creating-provisioning-packages) v [nástroji Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) nebo prostřednictvím [správce certifikátů](certificate-manager.md) , a to tak, že na **Nastavení > Update & Security > certificate manager**.

## <a name="certificate-requirements"></a>Požadavky na certifikáty
K nasazení certifikátů prostřednictvím infrastruktury SCEP nebo PKCS se vyžadují kořenové certifikáty. další aplikace a služby ve vaší organizaci můžou vyžadovat, aby se kořenové certifikáty nasadily i na vaše zařízení HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Požadavky na připojení Wi-Fi
Pokud chcete, aby se zařízení automaticky poskytovalo s požadovanou konfigurací Wi-Fi pro vaši podnikovou síť, budete potřebovat konfigurační profil Wi-Fi. Pro nasazení těchto profilů do zařízení můžete nakonfigurovat Intune nebo jiného poskytovatele MDM. pokud zabezpečení vaší sítě vyžaduje, aby zařízení byla součástí místní domény, možná budete muset vyhodnotit Wi-Fi síťovou infrastrukturu, abyste měli jistotu, že je kompatibilní se zařízeními HoloLens 2 (zařízení HoloLens 2 jsou jenom připojená k Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Nasazení infrastruktury certifikátů
Pokud už žádná infrastruktura SCEP nebo PKCS neexistuje, budete ji muset připravit. Aby bylo možné podporovat používání certifikátů SCEP nebo PKCS pro ověřování, vyžaduje Intune použití [Certificate Connectoru](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Pokud používáte SCEP s certifikační autoritou Microsoftu, musíte taky nakonfigurovat [službu zápisu síťových zařízení (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes) .

Další informace najdete v tématu [Konfigurace profilu certifikátu pro vaše zařízení v Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Nasazení certifikátů a profilu sítě Wi-Fi/VPN
K nasazení certifikátů a profilů použijte následující postup:
1.  Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti nebudou nasazeny.**
1.  Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz [Vytvoření profilu certifikátu SCEP nebo vytvoření profilu certifikátu PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu dd/mm/rrrr. **Profily certifikátů bez data vypršení platnosti nebudou nasazeny.**

    > [!NOTE]
    > vzhledem k tomu, že HoloLens 2 se považuje za sdílené zařízení, více uživatelů na zařízení se doporučuje nasadit certifikáty zařízení místo uživatelských certifikátů pro ověřování Wi-Fi, pokud to jde.

3.  vytvořte profil pro každou podnikovou Wi-Fi síť (viz [nastavení Wi-Fi pro zařízení Windows 10 a novější](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Doporučuje se, aby byl profil Wi-Fi [přiřazen](/mem/intune/configuration/device-profile-assign) skupinám zařízení, nikoli skupinám uživatelů, pokud je to možné. 

    > [!TIP]
    > pracovní Wi-Fi profil můžete také exportovat ze Windows 10 počítače v podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. pak tento soubor importujte do intune a použijte ho jako profil Wi-Fi pro zařízení HoloLens 2. viz [nastavení exportu a importu Wi-Fi pro Windows zařízení.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  vytvořte si profil pro každou podnikovou síť VPN (další informace najdete v tématu [Windows 10 a Windows holografické zařízení pro přidání připojení k síti vpn pomocí intune](/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Řešení potíží s certifikáty

V případě, že potřebujete ověřit, jestli je certifikát nasazený správně, použijte prosím [Správce certifikátů](certificate-manager.md) na zařízení a ověřte, jestli je certifikát přítomný.  

>[!WARNING]
> I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nemůžete je odinstalovat ve Správci certifikátů. Musíte je odinstalovat přes MDM.


