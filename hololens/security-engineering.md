---
title: Engineering zabezpečení
description: Engineering zabezpečení
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Security, engineering
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1c043b721590e8245f694b3e4f6e5b6ce57f1ecf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639348"
---
# <a name="security-engineering"></a><span data-ttu-id="823f4-104">Engineering zabezpečení</span><span class="sxs-lookup"><span data-stu-id="823f4-104">Security engineering</span></span>

<span data-ttu-id="823f4-105">Microsoft má několik zdrojů a týmů, které se věnují optimalizaci technických protokolů společnosti, řešení dodržování předpisů a zajištění důvěry zákazníků.</span><span class="sxs-lookup"><span data-stu-id="823f4-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="823f4-106">Další informace o postupech vývoje bezpečnostního inženýrství od Microsoftu najdete v tématu [Security Development Lifecycle (SDL).](https://www.microsoft.com/securityengineering/sdl)</span><span class="sxs-lookup"><span data-stu-id="823f4-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="823f4-107">Microsoft a tedy HoloLens 2 umožňují zákazníkům rozhodovat se, jak a proč se data shromažďují a používají, což je možné dále prozkoumat v zásadách ochrany osobních [údajů společnosti Microsoft.](https://privacy.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="823f4-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="823f4-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) je součástí komunity defenderu a poskytuje efektivní prostředí pro hlášení ohrožení zabezpečení a efektivní kategorizaci a reakci na chyby zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="823f4-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="823f4-109">Aktualizace a opravy</span><span class="sxs-lookup"><span data-stu-id="823f4-109">Updates and patches</span></span>

<span data-ttu-id="823f4-110">Aktualizace a opravy zabezpečení se vydaná druhé úterý v každém měsíci.</span><span class="sxs-lookup"><span data-stu-id="823f4-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="823f4-111">Pokud chcete porozumět kritériím, pomocí kterých Microsoft vyhodnocuje další kroky nahlášené chyby zabezpečení, Microsoft Security Response Center stránce [Kritéria údržby zabezpečení.](https://www.microsoft.com/msrc/windows-security-servicing-criteria)</span><span class="sxs-lookup"><span data-stu-id="823f4-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="823f4-112">Pokyny ke správě aktualizací HoloLens 2 prostřednictvím MDM najdete v tématu [Správa HoloLens aktualizací.](hololens-updates.md)</span><span class="sxs-lookup"><span data-stu-id="823f4-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](hololens-updates.md).</span></span> <span data-ttu-id="823f4-113">Frekvence aktualizací operačního systému HoloLens 2 odpovídá Windows 10; Existují dvě aktualizace za rok, jedna probíhá ve Springu a druhá na Fallu.</span><span class="sxs-lookup"><span data-stu-id="823f4-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="823f4-114">Další informace o tom, jak jsou zařízení zabezpečená během aktualizací operačního systému, najdete v tématu [Oddělení stavu](security-state-separation-isolation.md)a izolace .</span><span class="sxs-lookup"><span data-stu-id="823f4-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="823f4-115">Správci IT mohou další informace o zásadách aktualizace na [stránce Policy CSP – Update](/windows/client-management/mdm/policy-csp-update).</span><span class="sxs-lookup"><span data-stu-id="823f4-115">IT admins can learn more about update policy at [Policy CSP - Update](/windows/client-management/mdm/policy-csp-update).</span></span> 
