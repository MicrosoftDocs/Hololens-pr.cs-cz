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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379273"
---
# <a name="license-requirements"></a>Licenční požadavky

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Pokyny Správa zařízení k licencím pro Mobile Správa zařízení (MDM)

Pokud máte v plánu spravovat zařízení HoloLens, budete potřebovat Azure AD a MDM. Active Director (AD) není možné použít ke správě zařízení HoloLens.
Pokud plánujete používat jiný MDM než Intune, vyžaduje [se Azure Active Directory licence.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
Pokud máte v plánu používat Intune jako MDM, přečtěte si seznam sad, [které](https://docs.microsoft.com/intune/fundamentals/licenses) obsahují licence Intune. **Upozorňujeme, že služba Azure AD je součástí většiny těchto sad.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>Identifikace licencí potřebných pro váš scénář a produkty

### <a name="hololens-1st-gen-licenses-requirements"></a>HoloLens (1. generace) – požadavky na licence

Možná budete muset upgradovat zařízení HoloLens (1. generace) na Windows Holographic for Business. (Pokud chcete zjistit, jestli potřebujete upgradovat, podívejte se na komerční funkce [HoloLens.](holoLens-commercial-features.md#feature-comparison-between-editions)

 Pokud ano, budete muset provést následující:

- Získání souboru XML s licencí HoloLens Enterprise
- Použijte soubor XML na HoloLens. Můžete to provést prostřednictvím [zřizovacího balíčku nebo](hololens-provisioning.md) přes [Mobile Správce zařízení](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Licenční požadavky pro Remote Assist

Ujistěte se, že máte požadované licence a zařízení, které můžete zkontrolovat v [dokumentaci k požadavkům.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)

1. [Licence Remote Assistu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Nebo zkuste zkušební [verzi vzdálené pomoci.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) License](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Pokud plánujete implementaci tohoto **[scénáře napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** možná budete potřebovat licenci Information Barriers. Pokud chcete [zjistit, jestli](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) se vyžaduje licence Information Barrier, přečtěte si tento článek.

### <a name="guides-license-requirements"></a>Průvodci licenčními požadavky

Podívejte se na [aktualizované licenční požadavky a požadavky na zařízení.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Azure Active Directory (Azure AD) License](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Příručky](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
