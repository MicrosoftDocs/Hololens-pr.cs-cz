---
title: Zabezpečení operačního systému bez oprávnění správce
description: Seznamte se s operačními systémy bez správy, vlastníky zařízení a zabezpečením na HoloLens hybridní realitě.
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
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639399"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="88319-104">Operační systém bez oprávnění správce</span><span class="sxs-lookup"><span data-stu-id="88319-104">Admin-less operating system</span></span>

<span data-ttu-id="88319-105">HoloLens 2 minimalizuje prostor pro eskalaci oprávnění tím, že zakáže podporu pro skupinu Administrators a omezí veškerý kód aplikace UPW třetích stran tak, aby se v sandboxu AppContainer s jeho spouštěním mohl provádět jenom jako standardní uživatelé.</span><span class="sxs-lookup"><span data-stu-id="88319-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="88319-106">Tento kód má kromě prostředků, které jsou přístupné pro všechny kontejnery AppContainer, udělen přístup pouze k prostředkům chráněným funkcemi výslovně manifestovaným v aplikaci pro nepřipraveného uživatele.</span><span class="sxs-lookup"><span data-stu-id="88319-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="88319-107">Tyto možnosti aplikací mají i nadále třívrstvý klasifikační model:</span><span class="sxs-lookup"><span data-stu-id="88319-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="88319-108">Obecné</span><span class="sxs-lookup"><span data-stu-id="88319-108">General</span></span>
  * <span data-ttu-id="88319-109">S omezeným přístupem</span><span class="sxs-lookup"><span data-stu-id="88319-109">Restricted</span></span>
  * <span data-ttu-id="88319-110">Windows</span><span class="sxs-lookup"><span data-stu-id="88319-110">Windows</span></span>

<span data-ttu-id="88319-111">Windows můžete také využít sandbox AppContainer prostřednictvím systémových UWP.</span><span class="sxs-lookup"><span data-stu-id="88319-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="88319-112">Další informace o univerzální platformě Windows platformě (UPW) najdete v dokumentaci [k UPW.](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="88319-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="88319-113">Kromě toho Windows komponenty s vyššími požadavky na snížení oprávnění (například stránky obsahu prohlížeče nebo analyzátory) používají sandbox Less Privileged AppContainer (LPAC), který ořízne přístup k sadě prostředků přístupných všem kontejnerům AppContainer.</span><span class="sxs-lookup"><span data-stu-id="88319-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="88319-114">Vlastník zařízení</span><span class="sxs-lookup"><span data-stu-id="88319-114">Device owner</span></span>

<span data-ttu-id="88319-115">Provádění konkrétních operací v celém zařízení, jako je například připojení zařízení k tenantovi nebo správa uživatelů, je povolené pouze pro "vlastníky zařízení".</span><span class="sxs-lookup"><span data-stu-id="88319-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="88319-116">Tuto skupinu naplní uživatelé na zařízení pomocí jednoho z následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="88319-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="88319-117">První uživatel v zařízení je vždy určen jako vlastník.</span><span class="sxs-lookup"><span data-stu-id="88319-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="88319-118">Výjimkou z tohoto pravidla pro uživatele Azure AD je, že pokud je zařízení připojené ke službě Azure AD prostřednictvím Autopilotu nebo hromadná registrace služby Azure AD, která používá uživatele, který není skutečným uživatelem.</span><span class="sxs-lookup"><span data-stu-id="88319-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="88319-119">V takovém případě nemusí být prvním uživatelem AAD, který se přihlásí k zařízení, automaticky nastaven jako vlastník zařízení, pokud nemá přiřazenou roli globálního správce nebo správce zařízení v Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="88319-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="88319-120">Další informace najdete v poznámce níže.</span><span class="sxs-lookup"><span data-stu-id="88319-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="88319-121">Když je uživatel povýšen na vlastníka z uživatelského Nastavení uživatelského rozhraní jiného vlastníka na zařízení.</span><span class="sxs-lookup"><span data-stu-id="88319-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="88319-122">Pokud už vlastník zařízení není dostupný (opustí společnost) a zařízení je připojené k Azure AD, správce tenanta může změnit vlastníka zařízení na nového uživatele v Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="88319-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="88319-123">Globální správci a správci zařízení tenanta Azure AD jsou implicitně přihlášení jako vlastníci zařízení, aniž by to vyžadovalo některý z předchozích kroků.</span><span class="sxs-lookup"><span data-stu-id="88319-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="88319-124">Správci IT můžou spravovat, k jakým aplikacím má přístup prostřednictvím [zásad ochrany osobních](/windows/client-management/mdm/policy-csp-privacy) údajů.</span><span class="sxs-lookup"><span data-stu-id="88319-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="88319-125">Pokud chcete lépe porozumět tomu, kdo je vlastníkem zařízení připojeného k Azure AD, přečtěte si dokumentaci Přiřadit místního správce [(ale](/azure/active-directory/devices/assign-local-admin) přečtěte si o tom, že místní správce je vlastníkem zařízení, protože správce na zařízení HoloLens).</span><span class="sxs-lookup"><span data-stu-id="88319-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>