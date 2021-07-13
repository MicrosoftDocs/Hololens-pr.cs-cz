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
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640487"
---
# <a name="network-security"></a>Zabezpečení sítě

## <a name="network-protocols"></a>Síťové protokoly

Zastaralý systém NetBIOS (Network Basic Input/Output System) se v minulosti často používal ve scénářích LAN– často k poskytování překladu ip adres počítači a sdíleným složkám. V průběhu času se ale ukázalo, že rozhraní NetBIOS je náchylné k více útokům a jeho relevance se snižuje ve prospěch dalších bezpečnějších protokolů. Pokud chcete tento problém s ohrožením zabezpečení HoloLens 2, vyloučili jste z operačního systému kód související s rozhraním NetBIOS.

Protokoly TLS (Transport Layer Security) se neustále vyvíjejí. Aby bylo v souladu s různými zneužitími zabezpečení, které se v této oblasti objevilo, odstupňoval výpočetní odvětví novější a efektivnější verze. Vzhledem k době, kterou všechna nasazení serverů potřebují k přijetí nových verzí protokolu TLS, je možné implementovat záložní mechanismus, který umožňuje, aby klienti a servery s různými výchozími verzemi protokolu mohli během přechodného období stále komunikovat.

## <a name="secure-connectivity"></a>Zabezpečené připojení 

Brána Windows Defender Firewall poskytuje důležité funkce pro zabezpečení připojení zařízení. Při HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat.

Ochrana osobních údajů vzdáleného přístupu a připojení pro mobilní klienty je zajištěna prostřednictvím platformy [modulu plug-in VPN UPW.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Poskytovatelé sítě VPN třetích stran mohou vytvářet vlastní moduly plug-in pomocí rozhraní WinRT API, která povedou v sandboxu AppContainer, čímž eliminují složitost a problémy, které jsou často spojené s psaním ovladačů na úrovni systému.
