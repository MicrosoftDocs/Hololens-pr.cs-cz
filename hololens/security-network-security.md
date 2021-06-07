---
title: Zabezpečení sítě
description: zabezpečení sítě
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, network, network security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379231"
---
# <a name="network-security"></a>Zabezpečení sítě

## <a name="network-protocols"></a>Síťové protokoly

Zastaralý systém NetBIOS (Network Basic Input/Output System) se v minulosti často používal ve scénářích LAN– často k poskytování překladu názvů na počítač a sdílené složky. V průběhu času se ale ukázalo, že rozhraní NetBIOS je náchylné k více útokům a jeho relevance se snížila ve prospěch dalších bezpečnějších protokolů. K odebrání tohoto problému s ohrožením zabezpečení vyloučil HoloLens 2 kód související s rozhraním NetBIOS z operačního systému.

Protokoly TLS (Transport Layer Security) se neustále vyvíjejí. Aby bylo v souladu s různými zneužitími zabezpečení, které se v této oblasti objevilo, odstupňoval výpočetní odvětví novější a efektivnější verze. Vzhledem k době, kterou všechna nasazení serverů potřebují k přijetí nových verzí protokolu TLS, je možné implementovat záložní mechanismus, který umožňuje, aby klienti a servery s různými výchozími verzemi protokolu mohli během přechodného období stále komunikovat.

## <a name="secure-connectivity"></a>Zabezpečené připojení 

Tato Firewall v programu Windows Defender poskytuje důležité funkce pro zabezpečení připojení zařízení. U HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat.

Vzdálený přístup a ochrana osobních údajů připojení pro mobilní klienty lze získat prostřednictvím platformy [modulu plug-in VPN UPW.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Poskytovatelé sítě VPN třetích stran mohou vytvářet vlastní moduly plug-in pomocí rozhraní WinRT API, která povedou v sandboxu AppContainer, čímž eliminují složitost a problémy, které jsou často spojené s psaním ovladačů na úrovni systému.
