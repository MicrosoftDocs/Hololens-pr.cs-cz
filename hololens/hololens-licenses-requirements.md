---
title: Licenční požadavky
description: Udržujte si aktuální všechny licenční požadavky a pokyny, které potřebujete pro správu mobilních zařízení, HoloLens a Remote Assist.
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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: bd55edcc855e20d6709c7e535573f43785155d41
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2021
ms.locfileid: "114661708"
---
# <a name="license-requirements"></a>Licenční požadavky

## <a name="overview"></a>Přehled
Tato stránka poskytuje základní přehled licencí a účtů potřebných k nasazení spravovaných i nespravovaných zařízení HoloLens 2 ve vaší organizaci. Obsahuje také informace o licencování Dynamics 365 [Remote Assistu](#dynamics-365-remote-assist) a [příručky](#dynamics-365-guides).

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 licence a požadavky na účet

 
|       &nbsp;      | Spravované HoloLens | Nespravované HoloLens |
|-------------------|-----------------|---------------------|
| **Případ obchodního použití** | | |
| [Nasazení do zařízení připojených ke cloudu – doklad o konceptu nebo pilotní nasazení](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Nasazení v síti vaší organizace – nasazení ve velkém měřítku](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Nasazení v zabezpečeném offline prostředí](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenses** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> nebo <sup>2)</sup> | ✔️  | |
| **Účty** |  | |
| Účet správce Azure AD | ✔️ |  |
| Uživatelský účet Azure AD | ✔️ | |
| [Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Místní účet](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Automatická registrace](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) během počátečního nastavení zařízení, která registruje a připojuje Azure Active Directory a umožňuje správu zařízení pomocí Intune.
- <sup>2</sup> [Windows Autopilot pro HoloLens 2](hololens2-autopilot.md) zjednodušuje zřizování pro správce IT i koncové uživatele. Správci IT mohou předem HoloLens 2 zásady a při prvním spuštění se zařízení nasadí ve stavu připraveném pro firmy s nulovou interakcí koncových uživatelů.
- <sup>3</sup> Tento účet je nutné [zřídit](hololens-provisioning.md#provisioning-package-hololens-wizard) předem pomocí Windows Configuration Designer (WCD).

> [!IMPORTANT]
> Službu Active Directory (AD) nelze použít ke správě HoloLens zařízení.
 
> [!WARNING]
> Více uživatelů není podporováno pro zařízení pomocí účtu MSA nebo místního účtu.

## <a name="dynamics-365-licensing-and-requirements"></a>Licencování a požadavky Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>správce

- Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
- [Předplatné Remote Assistu](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Uživatel Dynamics 365 Remote Assistu

- Účet Azure AD

- Licence Remote Assistu 

  > [!NOTE]
  > Microsoft Teams je součástí Remote Assistu.

- Připojení k síti

#### <a name="microsoft-teams-user"></a>Microsoft Teams uživatele

- Účet Azure AD

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Připojení k síti

Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers. Informace [o tom,](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) jestli se vyžaduje licence Information Barrier, najdete v tomto článku.

### <a name="dynamics-365-guides"></a>Průvodci Dynamics 365 

#### <a name="admin"></a>správce

1. Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
2. Předplatné průvodců Dynamics 365 [nebo bezplatná zkušební verze](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Autor příručky

1. Účet Azure AD
1. [Licence průvodců Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikace Průvodci Dynamics 365 nainstalovanou na počítači nebo HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (slouží k zobrazení řídicího panelu Analýza)
1. Role autora (pro vytváření průvodců)
1. Připojení k síti

#### <a name="guides-user"></a>Návody – uživatel

1. Účet Azure AD
1. [Licence průvodců Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikace Průvodci Dynamics 365 nainstalovaná na HoloLens
1. Role operátora (pro testování nebo používání průvodců)
1. Připojení k síti
