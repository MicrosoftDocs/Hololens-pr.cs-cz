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
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: cf9e14ffbda01bb1fd9e788385f7b85884d1dc8c
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351613"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Příprava certifikátů a síťových profilů pro HoloLens 2

Ověřování pomocí certifikátů je běžným požadavkem pro zákazníky, kteří používají HoloLens 2. Pro přístup k Wi-Fi, připojení k řešením VPN nebo pro přístup k interním prostředkům ve vaší organizaci můžete vyžadovat certifikáty.

Vzhledem k tomu, že zařízení HoloLens 2 jsou obvykle připojená k službě Azure Active Directory (Azure AD) a spravuje je Intune nebo jiný poskytovatel MDM, budete muset tyto certifikáty nasadit pomocí infrastruktury certifikátů Simple Certificate Enrollment Protocol (SCEP) nebo PKCS (Public Key Cryptography Standard), která je integrovaná s řešením MDM. 

>[!NOTE]
> Pokud poskytovatele MDM nemáte, můžete certifikáty nasazovat prostřednictvím zřizovacího balíčku v [](certificate-manager.md) nástroji [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) nebo prostřednictvím Správce certifikátů tak, že budete Nastavení > Update & Security > **Certificate Manager.** [](hololens-provisioning.md#create-the-provisioning-package)

## <a name="certificate-requirements"></a>Požadavky na certifikáty
Kořenové certifikáty jsou nutné k nasazení certifikátů prostřednictvím infrastruktury SCEP nebo PKCS. Jiné aplikace a služby ve vaší organizaci můžou vyžadovat nasazení kořenových certifikátů do HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi připojení
Pokud chcete, aby zařízení bylo automaticky poskytnuto s požadovanou konfigurací Wi-Fi pro podnikovou síť, budete potřebovat Wi-Fi konfigurace. Intune nebo jiného poskytovatele MDM můžete nakonfigurovat tak, aby tyto profily nasadil do vašich zařízení. Pokud zabezpečení sítě vyžaduje, aby zařízení byla součástí místní domény, možná budete také muset vyhodnotit síťovou infrastrukturu Wi-Fi, abyste se ujistili, že jsou kompatibilní se zařízeními HoloLens 2 (zařízení HoloLens 2 jsou připojená jenom ke službě Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Nasazení infrastruktury certifikátů
Pokud ještě neexistuje žádná infrastruktura SCEP ani PKCS, budete si ji muset připravit. Pro podporu použití certifikátů SCEP nebo PKCS k ověřování vyžaduje Intune použití Certificate [Connectoru.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Pokud používáte SCEP s certifikační autoritou Microsoftu, musíte také nakonfigurovat [Služba zápisu síťových zařízení (NDES).](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Další informace najdete v tématu [Konfigurace profilu certifikátu pro zařízení v Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Nasazení certifikátů a profilu Sítě Wi-Fi/VPN
Certifikáty a profily nasadíte takto:

1.  Vytvořte profil pro každý kořenový a zprostředkující certifikát (viz [Vytvoření profilů důvěryhodných certifikátů).)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**

2.  Vytvořte profil pro každý certifikát SCEP nebo PKCS (viz Vytvoření profilu certifikátu SCEP nebo Vytvoření profilu certifikátu [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Každý z těchto profilů musí mít popis, který obsahuje datum vypršení platnosti ve formátu DD/MM/RRRR. **Profily certifikátů bez data vypršení platnosti se nenasadí.**

    > [!NOTE]
    > Vzhledem k tomu, že HoloLens 2 je považováno za sdílené zařízení, více uživatelů na zařízení, doporučujeme místo uživatelských certifikátů nasadit certifikáty zařízení pro ověřování Wi-Fi zařízení, pokud je to možné.

3.  Vytvořte profil pro každou podnikovou síť Wi-Fi sítě (viz [Nastavení Wi-Fi pro Windows 10 a novější zařízení).](/intune/wi-fi-settings-windows) 

    > [!NOTE]
    > Pokud je to možné, Wi-Fi profil zařízení [přiřaděl](/mem/intune/configuration/device-profile-assign) skupinám zařízení, a ne skupinám uživatelů. 

    > [!TIP]
    > Můžete také exportovat pracovní profil Wi-Fi z Windows 10 počítače ve vaší podnikové síti. Tento export vytvoří soubor XML se všemi aktuálními nastaveními. Pak tento soubor naimportujte do Intune a použijte ho jako profil Wi-Fi pro vaše zařízení HoloLens 2. Viz [Export a import Wi-Fi nastavení pro Windows zařízení.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Vytvořte profil pro každou podnikovou síť VPN (informace o přidání připojení VPN pomocí Intune najdete Windows 10 a [Windows holografického](/intune/vpn-settings-windows-10)zařízení).

## <a name="troubleshooting"></a>Řešení potíží

### <a name="issue---unable-to-connect-with-network-using-certificate-based-authentication"></a>Problém – Nelze se připojit k síti pomocí ověřování na základě certifikátů ###

**Příznaky**

Zařízení se nepovede navázat síťové připojení s ověřováním pomocí certifikátů.

**Postup při řešení potíží**

1. V případě, že potřebujete ověřit, že je certifikát [](certificate-manager.md) správně nasazený, použijte správce certifikátů v zařízení a ověřte, že je váš certifikát k dispozici.  

    >[!WARNING]
    > I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nelze je odinstalovat ve Správci certifikátů. Je nutné je odinstalovat prostřednictvím MDM.

2. Pokud se k nasazování certifikátů používá Simple Certificate Enrollment Protocol (SCEP), ujistěte se, že je ze zařízení přístupná adresa URL serveru Služba zápisu síťových zařízení (NDES). [Informace související s nastavením najdete v tématu Certifikáty SCEP](/mem/intune/protect/certificates-profile-scep) v Intune. Pokud se pro server NDES místo plně kvalifikované domény používá CNAME, zadáním této adresy URL ve webovém prohlížeči na zařízení se ujistěte, že se problém vyřešil.
