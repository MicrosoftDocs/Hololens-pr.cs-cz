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
# <a name="admin-less-operating-system"></a><span data-ttu-id="c1df6-104">Operační systém bez oprávnění správce</span><span class="sxs-lookup"><span data-stu-id="c1df6-104">Admin-less operating system</span></span>

<span data-ttu-id="c1df6-105">HoloLens 2 minimalizuje prostor pro eskalaci oprávnění tím, že zakáže podporu pro skupinu Administrators a omezí veškerý kód aplikace UPW třetích stran tak, aby se s jeho pomocí s oprávněními soukal jenom v rámci sandboxu AppContainer.</span><span class="sxs-lookup"><span data-stu-id="c1df6-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="c1df6-106">Tento kód má kromě prostředků, které jsou přístupné pro všechny kontejnery AppContainer, udělen přístup pouze k prostředkům chráněným funkcemi výslovně manifestovaným v aplikaci pro nepřipraveného uživatele.</span><span class="sxs-lookup"><span data-stu-id="c1df6-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="c1df6-107">Tyto možnosti aplikací mají i nadále třívrstvý klasifikační model:</span><span class="sxs-lookup"><span data-stu-id="c1df6-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="c1df6-108">Obecné</span><span class="sxs-lookup"><span data-stu-id="c1df6-108">General</span></span>
  * <span data-ttu-id="c1df6-109">S omezeným přístupem</span><span class="sxs-lookup"><span data-stu-id="c1df6-109">Restricted</span></span>
  * <span data-ttu-id="c1df6-110">Windows</span><span class="sxs-lookup"><span data-stu-id="c1df6-110">Windows</span></span>

<span data-ttu-id="c1df6-111">Komponenty Windows mohou také využívat sandbox AppContainer prostřednictvím systémových UWP.</span><span class="sxs-lookup"><span data-stu-id="c1df6-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="c1df6-112">Další informace o Univerzální platforma Windows (UPW) najdete v dokumentaci [k UPW.](https://docs.microsoft.com/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="c1df6-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="c1df6-113">Kromě toho komponenty Windows s vyššími požadavky na snížení oprávnění (například stránky obsahu prohlížeče nebo analyzátory) používají sandbox Less Privileged AppContainer (LPAC), který ořízne přístup k sadě prostředků přístupných všem kontejnerům AppContainers.</span><span class="sxs-lookup"><span data-stu-id="c1df6-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="c1df6-114">Vlastník zařízení</span><span class="sxs-lookup"><span data-stu-id="c1df6-114">Device owner</span></span>

<span data-ttu-id="c1df6-115">Provádění konkrétních operací v celém zařízení, jako je například připojení zařízení k tenantovi nebo správa uživatelů, je povolené pouze pro "vlastníky zařízení".</span><span class="sxs-lookup"><span data-stu-id="c1df6-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="c1df6-116">Tuto skupinu naplní uživatelé na zařízení pomocí jednoho z následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="c1df6-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="c1df6-117">První uživatel v zařízení je vždy určen jako vlastník.</span><span class="sxs-lookup"><span data-stu-id="c1df6-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="c1df6-118">Výjimkou z tohoto pravidla pro uživatele Azure AD je, že pokud je zařízení připojené ke službě Azure AD prostřednictvím Autopilotu nebo hromadná registrace služby Azure AD, která používá uživatele, který není skutečným uživatelem.</span><span class="sxs-lookup"><span data-stu-id="c1df6-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="c1df6-119">V takovém případě nemusí být prvním uživatelem AAD, který se přihlásí k zařízení, automaticky nastaven jako vlastník zařízení, pokud nemá přiřazenou roli globálního správce nebo správce zařízení v Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="c1df6-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="c1df6-120">Další informace najdete v poznámce níže.</span><span class="sxs-lookup"><span data-stu-id="c1df6-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="c1df6-121">Když je uživatel povýšen jako vlastník z uživatelského rozhraní Nastavení jiným vlastníkem na zařízení.</span><span class="sxs-lookup"><span data-stu-id="c1df6-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="c1df6-122">Pokud už vlastník zařízení není dostupný (opustí společnost) a zařízení je připojené k Azure AD, správce tenanta může změnit vlastníka zařízení na nového uživatele v Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="c1df6-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="c1df6-123">Globální správci a správci zařízení tenanta Azure AD jsou implicitně přihlášení jako vlastníci zařízení, aniž by to vyžadovalo některý z předchozích kroků.</span><span class="sxs-lookup"><span data-stu-id="c1df6-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="c1df6-124">Správci IT můžou spravovat, ke jakým aplikacím má přístup prostřednictvím [zásad ochrany osobních](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) údajů.</span><span class="sxs-lookup"><span data-stu-id="c1df6-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1df6-125">Další informace o tom, kdo se stal vlastníkem zařízení připojeného k Azure AD, najdete v dokumentaci Přiřadit místního správce [(ale](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) přečtěte si o tom, že místní správce je vlastníkem zařízení, protože správce v HoloLens neexistuje).</span><span class="sxs-lookup"><span data-stu-id="c1df6-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>