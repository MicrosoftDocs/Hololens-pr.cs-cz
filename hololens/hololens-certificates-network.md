---
title: Příprava certifikátů a síťových profilů pro HoloLens 2
description: Naučte se konfigurovat, používat, nasazovat a řešit potíže s certifikáty pro síť na zařízeních s hybridní realitou HoloLens 2.
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
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379198"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Příprava certifikátů a síťových profilů pro HoloLens 2

Ověřování pomocí certifikátů je běžným požadavkem pro zákazníky, kteří používají HoloLens 2. Pro přístup k Wi-Fi, připojení k řešením VPN nebo pro přístup k interním prostředkům ve vaší organizaci můžete vyžadovat certifikáty.

Vzhledem k tomu, že zařízení HoloLens 2 jsou obvykle připojená k službě Azure Active Directory (Azure AD) a spravuje je Intune nebo jiný poskytovatel MDM, budete muset tyto certifikáty nasadit pomocí infrastruktury certifikátů Simple Certificate Enrollment Protocol (SCEP) nebo PKCS (Public Key Cryptography Standard), která je integrovaná s řešením MDM. 

>[!NOTE]
> Pokud poskytovatele MDM nemáte, můžete i nadále nasazovat certifikáty prostřednictvím zřizovacího balíčku v nástroji [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) nebo prostřednictvím Správce certifikátů tak, že v nastavení **> Update & Security > Certificate Manageru**. [](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) [](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="certificate-requirements"></a>Požadavky na certifikáty
Kořenové certifikáty jsou nutné k nasazení certifikátů prostřednictvím infrastruktury SCEP nebo PKCS. Další aplikace a služby ve vaší organizaci můžou vyžadovat také nasazení kořenových certifikátů do zařízení HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi připojení
Pokud chcete, aby zařízení bylo automaticky poskytnuto s požadovanou Wi-Fi pro podnikovou síť, budete potřebovat Wi-Fi konfigurační profil. Intune nebo jiného poskytovatele MDM můžete nakonfigurovat tak, aby tyto profily nasadil do vašich zařízení. Pokud zabezpečení sítě vyžaduje, aby zařízení byla součástí místní domény, možná budete také muset vyhodnotit síťovou infrastrukturu Wi-Fi, abyste se ujistili, že je kompatibilní se zařízeními HoloLens 2 (zařízení HoloLens 2 jsou připojená jenom k Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Nasazení infrastruktury certifikátů
Pokud ještě neexistuje žádná infrastruktura SCEP ani PKCS, budete si ji muset připravit. Pro podporu použití certifikátů SCEP nebo PKCS k ověřování vyžaduje Intune použití Certificate [Connectoru.](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Pokud používáte SCEP s certifikační autoritou Microsoftu, musíte také nakonfigurovat Služba zápisu síťových zařízení [(NDES).](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Další informace najdete v tématu [Konfigurace profilu certifikátu pro zařízení v Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Nasazení certifikátů a profilu Sítě Wi-Fi/VPN
Certifikáty a profily nasadíte takto:
1.  Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů).)](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**
1.  Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz Vytvoření profilu certifikátu SCEP nebo Vytvoření profilu certifikátu [PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**

    > [!NOTE]
    > Vzhledem k tomu, že zařízení HoloLens 2 je považováno za sdílené zařízení, více uživatelů na zařízení, doporučujeme místo uživatelských certifikátů nasadit certifikáty zařízení, pokud je Wi-Fi možné.

3.  Vytvořte profil pro každou podnikovou síť Wi-Fi sítě (viz [Nastavení Wi-Fi pro Windows 10 a novější zařízení).](https://docs.microsoft.com/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Pokud je to možné, doporučujeme [](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) Wi-Fi zařízení přiřadit skupinám zařízení, a ne skupinám uživatelů. 

    > [!TIP]
    > Můžete také exportovat pracovní profil Wi-Fi z Windows 10 počítače ve vaší podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. Pak tento soubor naimportujte do Intune a použijte ho jako Wi-Fi pro zařízení HoloLens 2. Viz [Export a import Wi-Fi nastavení pro zařízení s Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Vytvořte profil pro každou podnikovou síť VPN (informace o přidání připojení VPN pomocí Intune najdete v Windows 10 a nastavení zařízení [s Windows Holographic).](https://docs.microsoft.com/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Řešení potíží s certifikáty

V případě, že potřebujete ověřit, že je certifikát [](certificate-manager.md) správně nasazený, použijte správce certifikátů v zařízení a ověřte, že je váš certifikát k dispozici.  

>[!WARNING]
> I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nemůžete je odinstalovat ve Správci certifikátů. Je nutné je odinstalovat prostřednictvím MDM.


