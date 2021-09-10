---
title: Příprava certifikátů a síťových profilů pro HoloLens 2
description: Naučte se konfigurovat, používat, nasazovat a řešit potíže s certifikáty pro síť na HoloLens 2 zařízeních hybridní reality.
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
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427036"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Příprava certifikátů a síťových profilů pro HoloLens 2

Ověřování pomocí certifikátů je běžným požadavkem pro zákazníky, kteří používají HoloLens 2. Pro přístup k Wi-Fi, připojení k řešením VPN nebo pro přístup k interním prostředkům ve vaší organizaci můžete vyžadovat certifikáty.

Vzhledem k tomu, že zařízení HoloLens 2 jsou obvykle připojená k službě Azure Active Directory (Azure AD) a spravuje je Intune nebo jiný poskytovatel MDM, budete muset tyto certifikáty nasadit pomocí infrastruktury certifikátů Simple Certificate Enrollment Protocol (SCEP) nebo PKCS (Public Key Cryptography Standard), která je integrovaná s vaším řešením MDM. 

>[!NOTE]
> Pokud poskytovatele MDM nemáte, můžete certifikáty nasadit prostřednictvím [](hololens-provisioning.md#steps-for-creating-provisioning-packages) zřizovacího balíčku v nástroji [](certificate-manager.md) [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) nebo prostřednictvím Správce certifikátů tak, že Nastavení > Update & Security **> Certificate Manager**.

## <a name="certificate-requirements"></a>Požadavky na certifikáty
Kořenové certifikáty jsou nutné k nasazení certifikátů prostřednictvím infrastruktury SCEP nebo PKCS. Jiné aplikace a služby ve vaší organizaci můžou vyžadovat nasazení kořenových certifikátů HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi připojení
Pokud chcete, aby zařízení bylo automaticky poskytnuto s požadovanou konfigurací Wi-Fi pro podnikovou síť, budete potřebovat Wi-Fi konfigurace. Intune nebo jiného poskytovatele MDM můžete nakonfigurovat tak, aby tyto profily nasadil do vašich zařízení. Pokud zabezpečení sítě vyžaduje, aby zařízení byla součástí místní domény, možná budete také muset vyhodnotit síťovou infrastrukturu Wi-Fi, abyste se ujistili, že jsou kompatibilní se zařízeními HoloLens 2 (zařízení HoloLens 2 jsou připojená jenom ke službě Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Nasazení infrastruktury certifikátů
Pokud ještě neexistuje žádná infrastruktura SCEP ani PKCS, budete si ji muset připravit. Pro podporu použití certifikátů SCEP nebo PKCS k ověřování vyžaduje Intune použití Certificate [Connectoru.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Pokud používáte SCEP s certifikační autoritou Microsoftu, musíte také nakonfigurovat Služba zápisu síťových zařízení [(NDES).](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Další informace najdete v tématu [Konfigurace profilu certifikátu pro zařízení v Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Nasazení certifikátů a profilu Sítě Wi-Fi/VPN
Certifikáty a profily nasadíte takto:
1.  Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů).)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**
1.  Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz Vytvoření profilu certifikátu SCEP nebo Vytvoření profilu certifikátu [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**

    > [!NOTE]
    > Vzhledem k tomu, že HoloLens 2 se považuje za sdílené zařízení, více uživatelů na zařízení, doporučujeme místo uživatelských certifikátů nasadit certifikáty zařízení pro ověřování Wi-Fi, pokud je to možné.

3.  Vytvořte profil pro každou podnikovou síť Wi-Fi sítě (viz [Nastavení Wi-Fi pro Windows 10 a novější zařízení).](/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Pokud je to možné, doporučujeme [](/mem/intune/configuration/device-profile-assign) Wi-Fi zařízení přiřadit ke skupinám zařízení, a ne skupinám uživatelů. 

    > [!TIP]
    > Můžete také exportovat pracovní profil Wi-Fi z Windows 10 počítače ve vaší podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. Pak tento soubor naimportujte do Intune a použijte ho jako profil Wi-Fi pro zařízení s HoloLens 2. Viz [Export a import Wi-Fi nastavení pro Windows zařízení.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Vytvořte profil pro každou podnikovou síť VPN (informace o přidání připojení VPN pomocí Intune Windows 10 a [Windows holografického](/intune/vpn-settings-windows-10)zařízení).

## <a name="troubleshooting-certificates"></a>Řešení potíží s certifikáty

V případě, že potřebujete ověřit, že je certifikát [](certificate-manager.md) správně nasazený, použijte správce certifikátů v zařízení a ověřte, že je váš certifikát k dispozici.  

>[!WARNING]
> I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nemůžete je odinstalovat ve Správci certifikátů. Musíte je odinstalovat prostřednictvím MDM.


