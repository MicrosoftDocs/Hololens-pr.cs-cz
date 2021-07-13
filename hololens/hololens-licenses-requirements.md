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
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640270"
---
# <a name="license-requirements"></a>Licenční požadavky

## <a name="hololens-2-device-managed"></a>zařízení HoloLens 2 (spravované)

[Účet Azure AD](/azure/active-directory/)

> [!IMPORTANT]
> službu Active Directory (AD) nelze použít ke správě HoloLensch zařízení.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) nebo jiné MDM.
- [Windows autopilot pro HoloLens 2](hololens2-autopilot.md)– usnadňuje zřizování správců IT i koncovým uživatelům. správci IT můžou předem nakonfigurovat zásady HoloLens 2 a při prvním spuštění budou zařízení nasazená ve stavu připraveném pro práci s nulovými interakcemi koncových uživatelů. 

  > [!NOTE]
  > Windows Pro automatický pilotní vývoj a nasazování zařízení s nízkou dotykovou instalací vyžaduje autopilotování [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) a [automatické registrace](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) . 

### <a name="business-use-case"></a>Případ použití firmy: 

- [Scénář nasazení a](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) – zkušební nasazení v konceptu nebo pilotní nasazení.

- [Scénář nasazení B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) – nasazení ve velkém měřítku.

## <a name="hololens-2-device-only-non-managed"></a>pouze zařízení HoloLens 2 (bez správy)

Při použití účtu Microsoft (MSA) nebo místního účtu se pro tyto účty nevyžadují žádné další licence.

[Místní účet](/windows/security/identity-protection/access-control/local-accounts)

- tento účet musí být [zřízen](hololens-provisioning.md#provisioning-package-hololens-wizard) před časem pomocí nástroje Windows Configuration Designer (WCD).

[Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> U zařízení s některým z těchto účtů se nepodporuje více uživatelů.

### <a name="business-use-case"></a>Případ použití firmy: 

- [Scénář nasazení C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -offline nebo zabezpečené nasazení.
 
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

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Připojení k síti

Pokud plánujete implementaci tohoto [scénáře mezi klienty](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), budete možná potřebovat licenci na informace o bariérách. V [tomto článku](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) zjistíte, jestli je nutná licence k informační bariérě.

### <a name="dynamics-365-guides"></a>Příručky k Dynamics 365 

#### <a name="admin"></a>správce

- Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)
- Předplatné produktu Dynamics 365 [vás předplatným nebo bezplatnou zkušební verzí](/dynamics365/mixed-reality/guides/setup-step-one)

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
