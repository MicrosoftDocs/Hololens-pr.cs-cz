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
# <a name="network-security"></a><span data-ttu-id="b9e05-104">Zabezpečení sítě</span><span class="sxs-lookup"><span data-stu-id="b9e05-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="b9e05-105">Síťové protokoly</span><span class="sxs-lookup"><span data-stu-id="b9e05-105">Network protocols</span></span>

<span data-ttu-id="b9e05-106">Zastaralý systém NetBIOS (Network Basic Input/Output System) se v minulosti často používal ve scénářích LAN– často k poskytování překladu názvů na počítač a sdílené složky.</span><span class="sxs-lookup"><span data-stu-id="b9e05-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="b9e05-107">V průběhu času se ale ukázalo, že rozhraní NetBIOS je náchylné k více útokům a jeho relevance se snížila ve prospěch dalších bezpečnějších protokolů.</span><span class="sxs-lookup"><span data-stu-id="b9e05-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="b9e05-108">K odebrání tohoto problému s ohrožením zabezpečení vyloučil HoloLens 2 kód související s rozhraním NetBIOS z operačního systému.</span><span class="sxs-lookup"><span data-stu-id="b9e05-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="b9e05-109">Protokoly TLS (Transport Layer Security) se neustále vyvíjejí.</span><span class="sxs-lookup"><span data-stu-id="b9e05-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="b9e05-110">Aby bylo v souladu s různými zneužitími zabezpečení, které se v této oblasti objevilo, odstupňoval výpočetní odvětví novější a efektivnější verze.</span><span class="sxs-lookup"><span data-stu-id="b9e05-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="b9e05-111">Vzhledem k době, kterou všechna nasazení serverů potřebují k přijetí nových verzí protokolu TLS, je možné implementovat záložní mechanismus, který umožňuje, aby klienti a servery s různými výchozími verzemi protokolu mohli během přechodného období stále komunikovat.</span><span class="sxs-lookup"><span data-stu-id="b9e05-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="b9e05-112">Zabezpečené připojení</span><span class="sxs-lookup"><span data-stu-id="b9e05-112">Secure connectivity</span></span> 

<span data-ttu-id="b9e05-113">Tato Firewall v programu Windows Defender poskytuje důležité funkce pro zabezpečení připojení zařízení.</span><span class="sxs-lookup"><span data-stu-id="b9e05-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="b9e05-114">U HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat.</span><span class="sxs-lookup"><span data-stu-id="b9e05-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="b9e05-115">Vzdálený přístup a ochrana osobních údajů připojení pro mobilní klienty lze získat prostřednictvím platformy [modulu plug-in VPN UPW.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="b9e05-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="b9e05-116">Poskytovatelé sítě VPN třetích stran mohou vytvářet vlastní moduly plug-in pomocí rozhraní WinRT API, která povedou v sandboxu AppContainer, čímž eliminují složitost a problémy, které jsou často spojené s psaním ovladačů na úrovni systému.</span><span class="sxs-lookup"><span data-stu-id="b9e05-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
