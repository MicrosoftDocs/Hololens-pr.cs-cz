---
title: Zabezpečení sítě
description: zabezpečení sítě
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpečení, HoloLens, síť, zabezpečení sítě
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c5ac42ee272becfd404a1f00931fa05237e31993288fee16d79d73f79aade646
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665382"
---
# <a name="network-security"></a>Zabezpečení sítě

## <a name="network-protocols"></a>Síťové protokoly

Zastaralý systém NetBIOS (Network Basic Input/Output System) se v minulosti používal v dřívějších scénářích sítě LAN – často pro poskytování překladu adres IP počítačům a sdíleným složkám. V průběhu času se však rozhraní NetBIOS ukázalo jako náchylné k více útokům a jeho závažnost se snížila ve prospěch dalších bezpečnějších protokolů. kvůli odebrání tohoto problému s chybou zabezpečení HoloLens 2 vyloučil kód týkající se rozhraní NetBIOS z operačního systému.

Protokoly TLS (Transport Layer Security) se neustále vyvíjí. Aby se zajistilo, že se v této oblasti zjistí různé zneužití, výpočetní prostředí se na novějších a efektivnějších verzích dokončí. Vzhledem k času nutnému, aby všechna nasazení serveru přijímala nové verze protokolu TLS, je možné implementovat záložní mechanismus, který umožňuje klientovi a serverům v různých výchozích verzích protokolů, aby během přechodného období nadále komunikovaly.

## <a name="secure-connectivity"></a>Zabezpečené připojení 

brána Windows Defender Firewall přináší důležité funkce pro zabezpečení připojení zařízení. u HoloLens 2 je brána firewall vždycky zapnutá a neexistuje žádný způsob, jak ho deaktivovat programově nebo prostřednictvím uživatelského rozhraní.

Vzdálený přístup a ochrana osobních údajů pro mobilní klienty lze zajistit prostřednictvím [technologie Plug-in sítě VPN UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Poskytovatelé sítě VPN třetích stran můžou vytvářet vlastní moduly plug-in pomocí rozhraní API WinRT, která se spustí v izolovaném prostoru kontejneru AppContainer, což eliminuje složitost a problémy často spojené s psaním ovladačů na úrovni systému.
