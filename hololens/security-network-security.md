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
# <a name="network-security"></a><span data-ttu-id="3f384-104">Zabezpečení sítě</span><span class="sxs-lookup"><span data-stu-id="3f384-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="3f384-105">Síťové protokoly</span><span class="sxs-lookup"><span data-stu-id="3f384-105">Network protocols</span></span>

<span data-ttu-id="3f384-106">Zastaralý systém NetBIOS (Network Basic Input/Output System) se v minulosti často používal ve scénářích LAN– často k poskytování překladu ip adres počítači a sdíleným složkám.</span><span class="sxs-lookup"><span data-stu-id="3f384-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="3f384-107">V průběhu času se ale ukázalo, že rozhraní NetBIOS je náchylné k více útokům a jeho relevance se snižuje ve prospěch dalších bezpečnějších protokolů.</span><span class="sxs-lookup"><span data-stu-id="3f384-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="3f384-108">Pokud chcete tento problém s ohrožením zabezpečení HoloLens 2, vyloučili jste z operačního systému kód související s rozhraním NetBIOS.</span><span class="sxs-lookup"><span data-stu-id="3f384-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="3f384-109">Protokoly TLS (Transport Layer Security) se neustále vyvíjejí.</span><span class="sxs-lookup"><span data-stu-id="3f384-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="3f384-110">Aby bylo v souladu s různými zneužitími zabezpečení, které se v této oblasti objevilo, odstupňoval výpočetní odvětví novější a efektivnější verze.</span><span class="sxs-lookup"><span data-stu-id="3f384-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="3f384-111">Vzhledem k době, kterou všechna nasazení serverů potřebují k přijetí nových verzí protokolu TLS, je možné implementovat záložní mechanismus, který umožňuje, aby klienti a servery s různými výchozími verzemi protokolu mohli během přechodného období stále komunikovat.</span><span class="sxs-lookup"><span data-stu-id="3f384-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="3f384-112">Zabezpečené připojení</span><span class="sxs-lookup"><span data-stu-id="3f384-112">Secure connectivity</span></span> 

<span data-ttu-id="3f384-113">Brána Windows Defender Firewall poskytuje důležité funkce pro zabezpečení připojení zařízení.</span><span class="sxs-lookup"><span data-stu-id="3f384-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="3f384-114">Při HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat.</span><span class="sxs-lookup"><span data-stu-id="3f384-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="3f384-115">Ochrana osobních údajů vzdáleného přístupu a připojení pro mobilní klienty je zajištěna prostřednictvím platformy [modulu plug-in VPN UPW.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="3f384-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="3f384-116">Poskytovatelé sítě VPN třetích stran mohou vytvářet vlastní moduly plug-in pomocí rozhraní WinRT API, která povedou v sandboxu AppContainer, čímž eliminují složitost a problémy, které jsou často spojené s psaním ovladačů na úrovni systému.</span><span class="sxs-lookup"><span data-stu-id="3f384-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
