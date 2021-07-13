---
title: Zabezpečení operačního systému bez oprávnění správce
description: Seznamte se s operačními systémy bez správy, vlastníky zařízení a zabezpečením na HoloLens hybridní realitě.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639399"
---
# <a name="admin-less-operating-system"></a>Operační systém bez oprávnění správce

HoloLens 2 minimalizuje prostor pro eskalaci oprávnění tím, že zakáže podporu pro skupinu Administrators a omezí veškerý kód aplikace UPW třetích stran tak, aby se v sandboxu AppContainer s jeho spouštěním mohl provádět jenom jako standardní uživatelé. Tento kód má kromě prostředků, které jsou přístupné pro všechny kontejnery AppContainer, udělen přístup pouze k prostředkům chráněným funkcemi výslovně manifestovaným v aplikaci pro nepřipraveného uživatele.
Tyto možnosti aplikací mají i nadále třívrstvý klasifikační model:
  * Obecné
  * S omezeným přístupem
  * Windows

Windows můžete také využít sandbox AppContainer prostřednictvím systémových UWP. Další informace o univerzální platformě Windows platformě (UPW) najdete v dokumentaci [k UPW.](/windows/uwp/) Kromě toho Windows komponenty s vyššími požadavky na snížení oprávnění (například stránky obsahu prohlížeče nebo analyzátory) používají sandbox Less Privileged AppContainer (LPAC), který ořízne přístup k sadě prostředků přístupných všem kontejnerům AppContainer.

## <a name="device-owner"></a>Vlastník zařízení

Provádění konkrétních operací v celém zařízení, jako je například připojení zařízení k tenantovi nebo správa uživatelů, je povolené pouze pro "vlastníky zařízení". Tuto skupinu naplní uživatelé na zařízení pomocí jednoho z následujících kroků:
  * První uživatel v zařízení je vždy určen jako vlastník. 
> [!IMPORTANT]
>Výjimkou z tohoto pravidla pro uživatele Azure AD je, že pokud je zařízení připojené ke službě Azure AD prostřednictvím Autopilotu nebo hromadná registrace služby Azure AD, která používá uživatele, který není skutečným uživatelem. V takovém případě nemusí být prvním uživatelem AAD, který se přihlásí k zařízení, automaticky nastaven jako vlastník zařízení, pokud nemá přiřazenou roli globálního správce nebo správce zařízení v Azure Portal. Další informace najdete v poznámce níže.  

  * Když je uživatel povýšen na vlastníka z uživatelského Nastavení uživatelského rozhraní jiného vlastníka na zařízení.
  * Pokud už vlastník zařízení není dostupný (opustí společnost) a zařízení je připojené k Azure AD, správce tenanta může změnit vlastníka zařízení na nového uživatele v Azure Portal. Globální správci a správci zařízení tenanta Azure AD jsou implicitně přihlášení jako vlastníci zařízení, aniž by to vyžadovalo některý z předchozích kroků.  

 Správci IT můžou spravovat, k jakým aplikacím má přístup prostřednictvím [zásad ochrany osobních](/windows/client-management/mdm/policy-csp-privacy) údajů. 

> [!NOTE]
> Pokud chcete lépe porozumět tomu, kdo je vlastníkem zařízení připojeného k Azure AD, přečtěte si dokumentaci Přiřadit místního správce [(ale](/azure/active-directory/devices/assign-local-admin) přečtěte si o tom, že místní správce je vlastníkem zařízení, protože správce na zařízení HoloLens).