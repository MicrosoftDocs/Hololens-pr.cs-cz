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
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635887"
---
# <a name="license-requirements"></a>Licenční požadavky

## <a name="hololens-2-device-managed"></a>HoloLens 2 Zařízení (spravované)

[Účet Azure AD](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> Službu Active Directory (AD) nelze použít ke správě HoloLens zařízení.

[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) nebo jiný MDM.
- [Windows Autopilot pro HoloLens 2](hololens2-autopilot.md)– zjednodušuje zřizování pro správce IT i koncové uživatele. Správci IT mohou předem HoloLens 2 zásady a při prvním spuštění se zařízení nasadí ve stavu připraveném pro firmy s nulovou interakcí koncových uživatelů. 

  > [!NOTE]
  > Windows Autopilot vyžaduje, aby [](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) [se azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) a automatická registrace nakonfigurovali jako první pro tok Autopilotu a nasazení zařízení s nízkými funkcemi. 

### <a name="business-use-case"></a>Případ obchodního použití: 

- [Scénář nasazení A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – potvrzení konceptu nebo pilotní nasazení.

- [Scénář nasazení B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – nasazení ve velkém měřítku

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Pouze zařízení (nespravovaná)

Při použití účtu Microsoft (MSA) nebo místního účtu nejsou pro tyto účty vyžadovány žádné další licence.

[Místní účet](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- Tento účet je nutné [zřídit](hololens-provisioning.md#provisioning-package-hololens-wizard) předem pomocí Windows Configuration Designer (WCD).

[Účet Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Pro zařízení používající některý z těchto účtů není podporováno více uživatelů.

### <a name="business-use-case"></a>Případ obchodního použití: 

- [Scénář nasazení C –](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) offline nebo zabezpečené nasazení.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Licencování a požadavky Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>správce

- Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
- [Předplatné Remote Assistu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Uživatel Dynamics 365 Remote Assistu

- Účet Azure AD

- Licence Remote Assistu 

  > [!NOTE]
  > Microsoft Teams je součástí Remote Assistu.

- Připojení k síti

#### <a name="microsoft-teams-user"></a>Microsoft Teams uživatele

- Účet Azure AD

- Microsoft Teams nebo [Teams Freemium.](https://products.office.com/microsoft-teams/free)

- Připojení k síti

Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers. Informace [o tom,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) jestli se vyžaduje licence Information Barrier, najdete v tomto článku.

### <a name="dynamics-365-guides"></a>Průvodci Dynamics 365 

#### <a name="admin"></a>správce

- Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
- Předplatné průvodců Dynamics 365 [nebo bezplatná zkušební verze](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)

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
