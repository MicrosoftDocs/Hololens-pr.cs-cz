---
title: Zabezpečení operačního systému bez oprávnění správce
description: Seznamte se s operačními systémy bez správy, vlastníky zařízení a zabezpečením na zařízeních hybridní reality HoloLens.
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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379237"
---
# <a name="admin-less-operating-system"></a>Operační systém bez oprávnění správce

HoloLens 2 minimalizuje prostor pro eskalaci oprávnění tím, že zakáže podporu pro skupinu Administrators a omezí veškerý kód aplikace UPW třetích stran tak, aby se s jeho pomocí s oprávněními soukal jenom v rámci sandboxu AppContainer. Tento kód má kromě prostředků, které jsou přístupné pro všechny kontejnery AppContainer, udělen přístup pouze k prostředkům chráněným funkcemi výslovně manifestovaným v aplikaci pro nepřipraveného uživatele.
Tyto možnosti aplikací mají i nadále třívrstvý klasifikační model:
  * Obecné
  * S omezeným přístupem
  * Windows

Komponenty Windows mohou také využívat sandbox AppContainer prostřednictvím systémových UWP. Další informace o Univerzální platforma Windows (UPW) najdete v dokumentaci [k UPW.](https://docs.microsoft.com/windows/uwp/) Kromě toho komponenty Windows s vyššími požadavky na snížení oprávnění (například stránky obsahu prohlížeče nebo analyzátory) používají sandbox Less Privileged AppContainer (LPAC), který ořízne přístup k sadě prostředků přístupných všem kontejnerům AppContainers.

## <a name="device-owner"></a>Vlastník zařízení

Provádění konkrétních operací v celém zařízení, jako je například připojení zařízení k tenantovi nebo správa uživatelů, je povolené pouze pro "vlastníky zařízení". Tuto skupinu naplní uživatelé na zařízení pomocí jednoho z následujících kroků:
  * První uživatel v zařízení je vždy určen jako vlastník. 
> [!IMPORTANT]
>Výjimkou z tohoto pravidla pro uživatele Azure AD je, že pokud je zařízení připojené ke službě Azure AD prostřednictvím Autopilotu nebo hromadná registrace služby Azure AD, která používá uživatele, který není skutečným uživatelem. V takovém případě nemusí být prvním uživatelem AAD, který se přihlásí k zařízení, automaticky nastaven jako vlastník zařízení, pokud nemá přiřazenou roli globálního správce nebo správce zařízení v Azure Portal. Další informace najdete v poznámce níže.  

  * Když je uživatel povýšen jako vlastník z uživatelského rozhraní Nastavení jiným vlastníkem na zařízení.
  * Pokud už vlastník zařízení není dostupný (opustí společnost) a zařízení je připojené k Azure AD, správce tenanta může změnit vlastníka zařízení na nového uživatele v Azure Portal. Globální správci a správci zařízení tenanta Azure AD jsou implicitně přihlášení jako vlastníci zařízení, aniž by to vyžadovalo některý z předchozích kroků.  

 Správci IT můžou spravovat, ke jakým aplikacím má přístup prostřednictvím [zásad ochrany osobních](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) údajů. 

> [!NOTE]
> Další informace o tom, kdo se stal vlastníkem zařízení připojeného k Azure AD, najdete v dokumentaci Přiřadit místního správce [(ale](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) přečtěte si o tom, že místní správce je vlastníkem zařízení, protože správce v HoloLens neexistuje).