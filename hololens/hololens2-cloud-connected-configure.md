---
title: průvodce nasazením – Cloud připojený HoloLens 2 ke škálování pomocí programu vzdálená pomoc – konfigurace
description: naučte se, jak nastavit konfigurace pro registraci HoloLens zařízení přes cloudovou síť připojenou ke škálování pomocí funkce vzdálená pomoc.
keywords: HoloLens, správa, připojení k cloudu, vzdálená pomoc, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635139"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="9d338-104">Konfigurace – Průvodce připojením k cloudu</span><span class="sxs-lookup"><span data-stu-id="9d338-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="9d338-105">V této části příručky&#39;vše, jak nastavit automatický zápis pro vašeho tenanta a jak používat licence pro Intune i vzdálenou pomoc.</span><span class="sxs-lookup"><span data-stu-id="9d338-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="9d338-106">Uživatelé a skupiny Azure</span><span class="sxs-lookup"><span data-stu-id="9d338-106">Azure Users and Groups</span></span>

<span data-ttu-id="9d338-107">Azure a Intune pomocí tohoto rozšíření využívají uživatele a skupiny, které vám pomůžou přiřadit konfigurace a licence.</span><span class="sxs-lookup"><span data-stu-id="9d338-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="9d338-108">Pro účely ověření tohoto toku nasazení a umožnění vzdáleného volání pomoci od jednoho uživatele k jinému&#39;potřebujete, aby byly dva uživatelské účty.</span><span class="sxs-lookup"><span data-stu-id="9d338-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="9d338-109">Pro účely přiřazování licencí můžeme vytvořit jednu skupinu uživatelů.</span><span class="sxs-lookup"><span data-stu-id="9d338-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="9d338-110">Oba uživatele můžeme připojit ke stejné skupině a použít licenci pro Intune a vzdálenou pomoc k této skupině.</span><span class="sxs-lookup"><span data-stu-id="9d338-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="9d338-111">Pokud nemáte&#39;t už máte přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít. Tady jsou Úvodní příručky pro:</span><span class="sxs-lookup"><span data-stu-id="9d338-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="9d338-112">Postup vytvoření uživatele</span><span class="sxs-lookup"><span data-stu-id="9d338-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="9d338-113">Vytvoření skupiny</span><span class="sxs-lookup"><span data-stu-id="9d338-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="9d338-114">[Přidat uživatele do skupiny](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – přidat vytvořené uživatele k vytvoření skupiny</span><span class="sxs-lookup"><span data-stu-id="9d338-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="9d338-115">[Konfigurace služby Azure AD tak, aby povolovala skupině uživatelů připojení zařízení](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – zajistěte, aby nová skupina uživatelů měla oprávnění k registraci zařízení do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d338-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="9d338-116">automatický zápis na HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9d338-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="9d338-117">aby bylo možné zajistit hladké a bezproblémové prostředí, nastavení Azure Active Directory Join (AADJ) a automatický zápis do intune pro HoloLens 2 zařízení je možné přejít.</span><span class="sxs-lookup"><span data-stu-id="9d338-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="9d338-118">Uživatelé tak budou moct během spuštění OOBE zadat přihlašovací údaje pro své organizace a automaticky se zaregistrovat ve službě Azure AD a zaregistrovat zařízení do MDM.</span><span class="sxs-lookup"><span data-stu-id="9d338-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="9d338-119">pomocí [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a přejít na několik stránek, dokud si nebudeme moct vybrat získat Premium zkušební verzi.</span><span class="sxs-lookup"><span data-stu-id="9d338-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="9d338-120">můžete si všimnout, že je k dispozici Azure Active Directory Premium 1 a 2, pokud je automatický zápis P1 dostačující.</span><span class="sxs-lookup"><span data-stu-id="9d338-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="9d338-121">Můžeme vybrat Intune a vybrat obor uživatele pro automatický zápis a vybrat skupinu, která byla dřív vytvořená.</span><span class="sxs-lookup"><span data-stu-id="9d338-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="9d338-122">Úplné podrobnosti a kroky najdete v průvodci, [Jak povolit automatický zápis pro Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span><span class="sxs-lookup"><span data-stu-id="9d338-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="9d338-123">Licence k aplikacím</span><span class="sxs-lookup"><span data-stu-id="9d338-123">Application Licenses</span></span>

<span data-ttu-id="9d338-124">Licence aplikace umožňuje uživateli instalovat aplikace zakoupené firmou nebo upgradovat z bezplatné zkušební verze na plnou verzi aplikace.</span><span class="sxs-lookup"><span data-stu-id="9d338-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="9d338-125">Licence k aplikacím lze použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.</span><span class="sxs-lookup"><span data-stu-id="9d338-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="9d338-126">Pro uživatele ve vaší organizaci, kteří používají vzdálenou pomoc, je&#39;nutné licence pro vzdálenou pomoc.</span><span class="sxs-lookup"><span data-stu-id="9d338-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="9d338-127">Pro účely tohoto průvodce přiřadíte licence Remote Assist ke skupině uživatelů, kterou jsme vytvořili výše v [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="9d338-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="9d338-128">Požadavky na licence se můžou lišit v závislosti na tom, jestli bude uživatel provádět volání vzdálené pomoci ze zařízení, nebo se může jednat o vzdáleného spolupracovníka z Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9d338-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="9d338-129">ve výchozím nastavení jsou zaškrtávací políčka vzdálená pomoc a Teams označena jako.</span><span class="sxs-lookup"><span data-stu-id="9d338-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="9d338-130">Pro účely tohoto průvodce doporučujeme ponechat zaškrtnutá výchozí políčka.</span><span class="sxs-lookup"><span data-stu-id="9d338-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="9d338-131">Přečtěte si další informace o různých [licencích a požadavcích na produkt na roli](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span><span class="sxs-lookup"><span data-stu-id="9d338-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="9d338-132">Existuje několik různých typů licencí na vzdálenou pomoc, takže si nezapomeňte získat správné požadavky.</span><span class="sxs-lookup"><span data-stu-id="9d338-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="9d338-133">Musíte&#39;[získat licenci](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span><span class="sxs-lookup"><span data-stu-id="9d338-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="9d338-134">[Použijte své licence](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) na skupinu.</span><span class="sxs-lookup"><span data-stu-id="9d338-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="9d338-135">Další krok</span><span class="sxs-lookup"><span data-stu-id="9d338-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9d338-136">Nasazení propojené s cloudem – nasazení</span><span class="sxs-lookup"><span data-stu-id="9d338-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)