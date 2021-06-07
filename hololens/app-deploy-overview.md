---
title: Přehled – Správa aplikací
description: Začínáme s přehledem správy aplikací hybridní reality pomocí správy mobilních zařízení, Microsoft Storu pro firmy a zřizovacích balíčků
keywords: HoloLens, user, account, app, application management,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377580"
---
# <a name="app-management-overview"></a>Správa aplikací: Přehled

Aplikace můžete nasadit do čtyř různých cest: **Mobile Správa zařízení (MDM),** **Microsoft Store pro firmy,** **Microsoft Store** nebo jejich instalací prostřednictvím **zřizování**.

## <a name="mobile-device-management-mdm"></a>Správa mobilního zařízení (MDM)

Řešení pro správu mobilních zařízení umožňuje správcům a správcům IT soukromě automaticky instalovat (nabízeně) své vlastní obchodní aplikace nebo nakupovat aplikace prostřednictvím Storu pro skupinu uživatelů. Zařízení HoloLens fungují nejlépe se službou Microsoft Endpoint Manager (Intune) pro [správu aplikací.](app-deploy-intune.md) Intune také nabízí uživatelům přesnější kontrolu nad aplikacemi spravovanými IT prostřednictvím Portál společnosti ke stažení.

> [!NOTE]
> Následující pokyny jsou pro uživatele, kteří chtějí spravovat své aplikace pomocí Intune. Microsoft doporučuje ke správě aplikací a zařízení používat Intune.

Mobilní Správa zařízení (MDM) se vztahuje na:

* Nasazená a Portál společnosti MDM
* Obchodní aplikace (ne veřejné)
* Ruční instalace dostupných aplikací prostřednictvím Portál společnosti
* Nabízení správy prostřednictvím zásad MDM
* Automatická aktualizace prostřednictvím MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store pro firmy

The [Microsoft Store pro firmy](app-deploy-store-business.md) poskytuje it decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps. Správci IT můžou Microsoft Store aplikace a privátní obchodní aplikace v jednom inventáři a podle potřeby přiřazovat a opakovaně používat licence. Další informace najdete v tématu [Požadavky pro použití nástroje Microsoft Store pro firmy](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Tento Microsoft Store pro firmy platí pro:

* Veřejné nebo obchodní aplikace
* Automatická instalace požadovaných aplikací prostřednictvím přidružení MDM
* Uživatel stáhne aplikace ručně.
* Automatická aktualizace

## <a name="microsoft-store-apps"></a>Aplikace pro Microsoft Store

Tento Microsoft Store poskytuje správcům a správcům IT ve firmách vyhledávání, získávání, správu a distribuci veřejných aplikací.

Tato Microsoft Store platí pro:

* Jenom veřejné aplikace
* Uživatel stáhne aplikace ručně.
* Automatická aktualizace při připojení k internetu

Další informace najdete na webu [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Instalace prostřednictvím zřizovací balíčky

[Zřizovací](app-deploy-provisioning-package.md) balíčky umožňují instalovat vlastní nebo obchodní aplikace, což IT profesionálům a správcům umožňuje rychle instalovat aplikace na místní zařízení přes USB. Tuto instalaci je možné provést bez připojení k internetu a libovolného typu identity.

Instalace prostřednictvím zřizovací balíčky se vztahuje na:

* Obchodní / samoobslužné (ne veřejné) aplikace
* Veřejné aplikace (pokud je k dispozici offline instalační program)
* Jenom načítání bokem přes USB
* Žádná automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím zřizovacího balíčku)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací

Uživatelé s [Instalační program aplikací](app-deploy-app-installer.md) mohou mít prostředí, které je jednoduché pro instalaci aplikací na místní zařízení nebo sdílení aplikace s někým jiným, kdo nemá zkušenosti s jinými metodami instalace aplikací na HoloLens. Můžete to udělat bez nutnosti povolit vývojářský režim nebo použít Portál zařízení. Jedná se o jednoduchou metodu distribuce plně sestavené aplikace. Bez ohledu na to, jestli chcete aplikaci jednoduše degradovat na jiného uživatele pomocí HoloLens, nebo chcete aplikaci nasadit, tato metoda funguje snadno.

Instalace prostřednictvím Instalační program aplikací se vztahuje na:

* Obchodní / samoobslužné (ne veřejné) aplikace
* Pouze zkušební načtení
* Nevyžaduje vývojářský režim ani portál zařízení.
* Snadná instalace pro koncového uživatele
