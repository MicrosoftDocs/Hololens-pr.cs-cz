---
title: Licenční požadavky
description: udržujte si aktuální informace o licenčních požadavcích a pokynech, které potřebujete ke správě mobilních zařízení, HoloLens a vzdálené pomoci.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: aae4e1dbbf28906c1f93ac7f29620260023f596bb96fc23a3ee78442e70585fa
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663290"
---
# <a name="license-requirements"></a>Licenční požadavky

## <a name="overview"></a>Přehled
tato stránka poskytuje podrobný přehled licencí a účtů potřebných k nasazení spravovaných i nespravovaných zařízení HoloLens 2 ve vaší organizaci. Obsahuje také informace o licencování pro [vzdálenou pomoc](#dynamics-365-remote-assist) a [příručky](#dynamics-365-guides)k Dynamics 365.

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 požadavky na licence a účet

 
|       &nbsp;      | Spravované HoloLens | Nespravované HoloLens |
|-------------------|-----------------|---------------------|
| **Případ použití firmy** | | |
| [Nasazení na zařízení připojená do cloudu – ověření konceptu nebo pilotního nasazení](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Nasazení ve velkém měřítku v rámci nasazení sítě vaší organizace](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Nasazení v zabezpečeném prostředí offline](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenses** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> nebo <sup>2</sup>) | ✔️  | |
| **Účty** |  | |
| Účet správce Azure AD | ✔️ |  |
| Uživatelský účet Azure AD | ✔️ | |
| [Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Místní účet](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [automatická registrace](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) při počátečním nastavení zařízení, které registruje a spojuje Azure Active Directory a umožňuje správu zařízení pomocí intune.
- <sup>2</sup> [Windows autopilot pro HoloLens 2](hololens2-autopilot.md) , usnadňuje zřizování správců IT i koncovým uživatelům. správci IT můžou předem nakonfigurovat zásady HoloLens 2 a při prvním spuštění budou zařízení nasazená ve stavu připraveném pro práci s nulovými interakcemi koncových uživatelů.
- <sup>3</sup> tento účet musí být [zřízen](hololens-provisioning.md#provisioning-package-hololens-wizard) před časem pomocí nástroje Windows Configuration Designer (WCD).

> [!IMPORTANT]
> službu Active Directory (AD) nelze použít ke správě HoloLensch zařízení.
 
> [!WARNING]
> Pro zařízení se nepodporují víc uživatelů pomocí účtu MSA nebo místního účtu.

## <a name="dynamics-365-licensing-and-requirements"></a>Licencování a požadavky Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Vzdálená pomoc pro Dynamics 365 

#### <a name="admin"></a>správce

- Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)
- [Předplatné vzdálené pomoci](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze vzdáleného asistence](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Uživatel funkce Remote Assist pro uživatele Dynamics 365

- Účet Azure AD

- Licence pro vzdálenou pomoc 

  > [!NOTE]
  > Microsoft Teams je součástí sady Remote Assist.

- Připojení k síti

#### <a name="microsoft-teams-user"></a>Microsoft Teams uživatel

- Účet Azure AD

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Připojení k síti

Pokud plánujete implementaci tohoto [scénáře mezi klienty](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), budete možná potřebovat licenci na informace o bariérách. V [tomto článku](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) zjistíte, jestli je nutná licence k informační bariérě.

### <a name="dynamics-365-guides"></a>Příručky k Dynamics 365 

#### <a name="admin"></a>správce

1. Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)
2. Předplatné produktu Dynamics 365 [vás předplatným nebo bezplatnou zkušební verzí](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Autoré vodítek

1. Účet Azure AD
1. [Licence pro Příručky k Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Příručka k aplikaci Dynamics 365, která je nainstalovaná na počítači nebo HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (slouží k zobrazení řídicího panelu analýzy)
1. Role autora (pro vytváření průvodců)
1. Připojení k síti

#### <a name="guides-user"></a>Průvodce uživatelem

1. Účet Azure AD
1. [Licence pro Příručky k Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikace vodítek pro Dynamics 365 je nainstalovaná na HoloLens
1. Role operátora (pro testování nebo použití průvodců)
1. Připojení k síti
