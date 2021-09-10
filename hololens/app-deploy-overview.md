---
title: Přehled – Správa aplikací
description: Seznamte se s přehledem hybridních aplikací realit pomocí správy mobilních zařízení, Microsoft Storu pro firmy a zřizovacích balíčků.
keywords: HoloLens, uživatel, účet, aplikace, správa aplikací,
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428479"
---
# <a name="app-management-overview"></a>Správa aplikací: Přehled

aplikace můžete nasadit na čtyři různé cesty: **správu mobilních zařízení (MDM)**, **Microsoft Store pro firmy**, **Microsoft Store** nebo jejich instalací prostřednictvím **zřizování**.

## <a name="mobile-device-management-mdm"></a>Správa mobilního zařízení (MDM)

Řešení pro správu mobilních zařízení umožňuje IT tvůrcům a správcům IT nastavovat soukromou automatickou automatickou instalaci (nabízené) podnikové aplikace nebo si koupit aplikace v obchodě pro skupinu uživatelů. HoloLens zařízení fungují nejlépe s Microsoft Endpoint Manager (intune) pro [správu aplikací](app-deploy-intune.md). intune také nabízí uživatelům citlivější kontrolu nad IT aplikacemi spravovanými prostřednictvím prostředí pro stažení Portál společnosti.

> [!NOTE]
> Následující pokyny jsou pro uživatele, kteří chtějí spravovat své aplikace v Intune. Microsoft doporučuje používat Intune ke správě aplikací a zařízení.

Správa mobilních zařízení (MDM) platí pro:

* nasazené MDM + Portál společnosti
* Obchodní aplikace (ne veřejné)
* ruční instalace dostupných aplikací prostřednictvím Portál společnosti
* Nabízená oznámení správce prostřednictvím zásad MDM
* Automatické aktualizace prostřednictvím MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store pro firmy

[Microsoft Store pro firmy](app-deploy-store-business.md) poskytuje organizacím pro rozhodování a správcům IT v podnicích, aby našli, načítat, spravují a distribuují bezplatné a placené aplikace. správci IT můžou spravovat aplikace Microsoft Store a soukromé obchodní aplikace v jednom inventáři a navíc jim přiřadit a znovu používat licence podle potřeby. další informace najdete [v části požadavky pro použití Microsoft Store pro firmy](/microsoft-store/prerequisites-microsoft-store-for-business).

Microsoft Store pro firmy platí pro:

* Veřejné nebo obchodní aplikace
* Automatická instalace požadovaných aplikací prostřednictvím přidružení MDM
* Uživatel ručně stáhne aplikace
* Automatická aktualizace

## <a name="microsoft-store-apps"></a>Aplikace pro Microsoft Store

Microsoft Store poskytuje organizacím pro rozhodování a správcům IT v podnicích, aby našli, načítat, spravují a distribuují veřejné aplikace.

tato Microsoft Store platí pro:

* Pouze veřejné aplikace
* Uživatel ručně stáhne aplikace
* Automatická aktualizace, pokud je připojená k Internetu

Další informace najdete na webu [aplikace na holografickém obchodu](/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Instalace prostřednictvím zřizovacích balíčků

[Zřizovací balíčky](app-deploy-provisioning-package.md) umožňují nainstalovat vlastní nebo obchodní aplikace a umožní IT profesionálům a správcům rychle instalovat aplikace na místní zařízení přes USB. Tuto instalaci můžete provést bez připojení k Internetu a pro libovolný typ identity.

Instalace prostřednictvím zřizovacích balíčků je platná pro:

* Obchodní/samostatně vyvinuté aplikace (ne veřejné)
* Veřejné aplikace (Pokud je k dispozici offline instalátor)
* Jenom USB – načítání
* Bez automatické aktualizace (vyžaduje ruční aktualizace prostřednictvím zřizovacího balíčku)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace

Používání uživatelů v [instalačním programu aplikace](app-deploy-app-installer.md) může mít prostředí, které je jednoduché pro instalaci aplikací na místní zařízení nebo sdílení aplikace s někým jiným, kdo není obeznámen s jinými metodami instalace aplikací na HoloLens. To se dá udělat, aniž byste museli povolit vývojářský režim ani používat portál zařízení. Toto je jednoduchá metoda distribuce zcela sestavené aplikace. bez ohledu na to, jestli chcete aplikaci jednoduše vyzkoušet na jiného uživatele pomocí HoloLens nebo když chcete aplikaci nasadit, tato metoda funguje snadno.

Instalace prostřednictvím instalačního programu aplikace je platná pro:

* Obchodní/samoobslužné aplikace (ne veřejné)
* Jenom po straně
* Nevyžaduje vývojářský režim ani portál zařízení
* Snadné instalace pro koncové uživatele
