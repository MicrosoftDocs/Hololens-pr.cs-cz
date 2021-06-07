---
title: Průvodce nasazením – nasazení HoloLens 2 připojené ke cloudu ve velkém měřítku s remote assist – konfigurace
description: Zjistěte, jak nastavit konfigurace pro registraci zařízení HoloLens přes síť připojenou ke cloudu ve velkém měřítku pomocí remote assistu.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377600"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="5c7ef-104">Konfigurace – Průvodce připojeným ke cloudu</span><span class="sxs-lookup"><span data-stu-id="5c7ef-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="5c7ef-105">V této části příručky si&#39;, jak pro vašeho tenanta nastavit automatickou registraci a jak používat licence pro Intune i Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="5c7ef-106">Uživatelé a skupiny Azure</span><span class="sxs-lookup"><span data-stu-id="5c7ef-106">Azure Users and Groups</span></span>

<span data-ttu-id="5c7ef-107">Azure a Intune tímto rozšířením používají uživatele a skupiny k přiřazení konfigurací a licencí.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="5c7ef-108">Pro ověření tohoto toku nasazení a možnost volání vzdálené pomoci od jednoho uživatele k druhému budete potřebovat&#39;uživatelské účty.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="5c7ef-109">Pro účely přiřazování licencí můžeme vytvořit jednu skupinu uživatelů.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="5c7ef-110">Oba uživatele můžeme připojit ke stejné skupině a pro tuto skupinu použít licenci pro Intune a Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="5c7ef-111">Pokud ještě&#39;přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít . Tady jsou úvodní příručky pro:</span><span class="sxs-lookup"><span data-stu-id="5c7ef-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="5c7ef-112">Jak vytvořit uživatele</span><span class="sxs-lookup"><span data-stu-id="5c7ef-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="5c7ef-113">Jak vytvořit skupinu</span><span class="sxs-lookup"><span data-stu-id="5c7ef-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="5c7ef-114">[Přidání uživatelů do skupiny](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Přidání vytvořených uživatelů k vytvoření skupiny</span><span class="sxs-lookup"><span data-stu-id="5c7ef-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="5c7ef-115">[Konfigurace Azure AD tak, aby umožnila skupině](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) uživatelů připojovat se k zařízením – Ujistěte se, že nová skupina uživatelů má oprávnění k registraci zařízení do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="5c7ef-116">Automatická registrace na HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5c7ef-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="5c7ef-117">Pokud chcete mít bezproblémové a bezproblémové prostředí, můžete použít nastavení AADJ (Azure Active Directory Join) a automatické registrace do Intune pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="5c7ef-118">To uživatelům umožní zadat přihlašovací údaje organizace během spuštění počítače a automaticky se zaregistrovat v Azure AD a zaregistrovat zařízení do MDM.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="5c7ef-119">Pomocí microsoft [Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a procházet několik stránek, dokud nevybereme Získat zkušební verzi Premium.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="5c7ef-120">Můžete si všimnout, že Azure Active Directory Premium 1 a 2, protože automatická registrace P1 je dostačující.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="5c7ef-121">Můžeme vybrat Intune, vybrat obor uživatele pro automatickou registraci a vybrat skupinu, která byla vytvořena dříve.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="5c7ef-122">Úplné podrobnosti a kroky najdete v průvodci [povolením automatické registrace pro Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="5c7ef-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="5c7ef-123">Licence aplikací</span><span class="sxs-lookup"><span data-stu-id="5c7ef-123">Application Licenses</span></span>

<span data-ttu-id="5c7ef-124">Licence aplikace umožňuje uživateli buď nainstalovat zakoupené aplikace společnosti, nebo upgradovat z bezplatné zkušební verze na plnou verzi aplikace.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="5c7ef-125">Licence aplikací je možné použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="5c7ef-126">K&#39;remote assist budete potřebovat licence remote assistu pro uživatele ve vaší organizaci.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="5c7ef-127">Pro účely této příručky přiřadíme licence Remote Assistu ke skupině uživatelů, kterou jsme vytvořili výše v části Uživatelé a [skupiny Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="5c7ef-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="5c7ef-128">Požadavky na licence se mohou lišit v závislosti na tom, jestli uživatel bude volat vzdálenou pomoc ze zařízení nebo bude vzdáleným spolupracovníkem z Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="5c7ef-129">Ve výchozím nastavení jsou obě políčka Remote Assist a Teams označená.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="5c7ef-130">Pro účely tohoto průvodce doporučujeme nechat zaškrtnutá výchozí políčka.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="5c7ef-131">Další informace o různých [licenčních a produktových požadavcích na roli.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="5c7ef-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="5c7ef-132">Existuje několik různých typů licencí Remote Assistu, takže se ujistěte, že máte ty správné pro vaše potřeby.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="5c7ef-133">Musíte&#39;licenci [.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="5c7ef-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="5c7ef-134">[Použijte své licence](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) na skupinu.</span><span class="sxs-lookup"><span data-stu-id="5c7ef-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c7ef-135">Další krok</span><span class="sxs-lookup"><span data-stu-id="5c7ef-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5c7ef-136">Nasazení připojené ke cloudu – nasazení</span><span class="sxs-lookup"><span data-stu-id="5c7ef-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)