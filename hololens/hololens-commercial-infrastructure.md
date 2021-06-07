---
title: Pokyny pro infrastrukturu HoloLens
description: Přečtěte si o pravidlech infrastruktury pro zařízení HoloLens, včetně podpory bezdrátové sítě, vzdálené pomoci a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379197"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="e346a-103">Konfigurace sítě pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="e346a-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="e346a-104">Tato část dokumentu bude vyžadovat následující uživatele:</span><span class="sxs-lookup"><span data-stu-id="e346a-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="e346a-105">Správce sítě s oprávněními k provedení změn na proxy serveru nebo bráně firewall</span><span class="sxs-lookup"><span data-stu-id="e346a-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="e346a-106">Správce Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e346a-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="e346a-107">Správce mobilních Správce zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="e346a-108">Požadavky na infrastrukturu</span><span class="sxs-lookup"><span data-stu-id="e346a-108">Infrastructure Requirements</span></span>

<span data-ttu-id="e346a-109">HoloLens je ve svém jádru mobilní zařízení s Windows, které je integrované s Azure.</span><span class="sxs-lookup"><span data-stu-id="e346a-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="e346a-110">Funguje nejlépe v komerčních prostředích s dostupností bezdrátové sítě (Wi-Fi) a přístup ke službám Microsoftu.</span><span class="sxs-lookup"><span data-stu-id="e346a-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="e346a-111">Mezi důležité cloudové služby patří:</span><span class="sxs-lookup"><span data-stu-id="e346a-111">Critical cloud services include:</span></span>

- <span data-ttu-id="e346a-112">Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e346a-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="e346a-113">Web Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="e346a-113">Windows Update (WU)</span></span>

<span data-ttu-id="e346a-114">Komerční zákazníci budou potřebovat infrastrukturu pro správu mobilních zařízení (EMM) nebo správu mobilních zařízení (MDM), aby mohli spravovat zařízení HoloLens ve velkém měřítku.</span><span class="sxs-lookup"><span data-stu-id="e346a-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="e346a-115">Tato příručka používá [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako příklad, i když libovolný poskytovatel s plnou podporou pro zásady Microsoftu podporuje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e346a-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="e346a-116">Zeptejte se poskytovatele správy mobilních zařízení, pokud podporují HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e346a-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="e346a-117">HoloLens podporuje omezené sady prostředí odpojených do cloudu.</span><span class="sxs-lookup"><span data-stu-id="e346a-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="e346a-118">Podpora protokolu EAP bezdrátové sítě</span><span class="sxs-lookup"><span data-stu-id="e346a-118">Wireless network EAP support</span></span>

- <span data-ttu-id="e346a-119">Protokol PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e346a-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="e346a-120">PROTOKOL PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="e346a-120">PEAP-TLS</span></span>
- <span data-ttu-id="e346a-121">TLS</span><span class="sxs-lookup"><span data-stu-id="e346a-121">TLS</span></span>
- <span data-ttu-id="e346a-122">TTLS – CHAP</span><span class="sxs-lookup"><span data-stu-id="e346a-122">TTLS-CHAP</span></span>
- <span data-ttu-id="e346a-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e346a-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="e346a-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="e346a-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="e346a-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="e346a-125">TTLS-PAP</span></span>
- <span data-ttu-id="e346a-126">TTLS – TLS</span><span class="sxs-lookup"><span data-stu-id="e346a-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="e346a-127">Požadavky na síť specifické pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="e346a-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="e346a-128">Ujistěte se, že se [Tento seznam](hololens-offline.md) koncových bodů povoluje v bráně firewall vaší sítě.</span><span class="sxs-lookup"><span data-stu-id="e346a-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="e346a-129">To umožní funkci HoloLens správně fungovat.</span><span class="sxs-lookup"><span data-stu-id="e346a-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="e346a-130">Požadavky na určitou síť pro vzdálenou pomoc</span><span class="sxs-lookup"><span data-stu-id="e346a-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="e346a-131">Doporučená šířka pásma pro optimální výkon funkce Remote Assist je 1,5 MB/s.</span><span class="sxs-lookup"><span data-stu-id="e346a-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="e346a-132">Další informace najdete v [podrobnostech o požadavcích na síť](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .</span><span class="sxs-lookup"><span data-stu-id="e346a-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="e346a-133">**(Pokud v síti nemáte síťové rychlosti minimálně 1,5 MB/s, bude Vzdálená pomoc pořád fungovat. Kvalita ale může mít zhoršený vliv.**</span><span class="sxs-lookup"><span data-stu-id="e346a-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="e346a-134">Ujistěte se, že tyto porty a adresy URL jsou povolené v bráně firewall sítě, aby mohly Microsoft Teams fungovat.</span><span class="sxs-lookup"><span data-stu-id="e346a-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="e346a-135">[Seznamte se s nejnovějšími porty](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)v aktuálním stavu.</span><span class="sxs-lookup"><span data-stu-id="e346a-135">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="e346a-136">Přečtěte si další informace o konkrétních [požadavcích na síť pro vzdálenou pomoc](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="e346a-136">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="e346a-137">Další informace o tom, jak [připravit síť vaší organizace pro Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="e346a-137">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="e346a-138">Konkrétní požadavky na síť pro příručky</span><span class="sxs-lookup"><span data-stu-id="e346a-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="e346a-139">Příručky vyžadují přístup k síti pouze ke stažení a používání aplikace.</span><span class="sxs-lookup"><span data-stu-id="e346a-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="e346a-140">Pokyny pro Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e346a-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="e346a-141">Tento krok je nezbytný pouze v případě, že vaše společnost plánuje správu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e346a-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="e346a-142">Ujistěte se, že máte licenci Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e346a-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="e346a-143">Další informace najdete v [požadavcích na licence HoloLens](hololens-licenses-requirements.md) .</span><span class="sxs-lookup"><span data-stu-id="e346a-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="e346a-144">Pokud plánujete použití automatického zápisu, budete muset [nakonfigurovat registraci Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="e346a-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="e346a-145">Ujistěte se, že jsou uživatelé vaší společnosti v Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e346a-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="e346a-146">Pokud chcete přidat uživatele, přečtěte si následující [pokyny](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) .</span><span class="sxs-lookup"><span data-stu-id="e346a-146">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="e346a-147">Doporučujeme, aby uživatelé, kteří potřebují podobné licence, přidali do stejné skupiny.</span><span class="sxs-lookup"><span data-stu-id="e346a-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="e346a-148">Vytvoření skupiny</span><span class="sxs-lookup"><span data-stu-id="e346a-148">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="e346a-149">Přidat uživatele do skupin</span><span class="sxs-lookup"><span data-stu-id="e346a-149">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="e346a-150">Ujistěte se, že uživatelé (nebo skupiny uživatelů) vaší společnosti mají přidělené potřebné licence.</span><span class="sxs-lookup"><span data-stu-id="e346a-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="e346a-151">Pokud potřebujete přiřadit licence, postupujte podle těchto [pokynů](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="e346a-151">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="e346a-152">Tento krok proveďte jenom v případě, že se uživatelé chtějí zaregistrovat svoje zařízení HoloLens nebo mobilní zařízení (Existují tři možnosti) tyto kroky zajistí, že uživatelé společnosti (nebo skupiny uživatelů) můžou přidat zařízení.</span><span class="sxs-lookup"><span data-stu-id="e346a-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="e346a-153">**Možnost 1:** Poskytněte všem uživatelům oprávnění k připojení zařízení ke službě Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e346a-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="e346a-154">**Přihlaste se k Azure Portal jako správce**  >  . **Azure Active Directory**  >  **Zařízení**  >  **Nastavení zařízení**  >
 **Nastavení uživatelé můžou připojovat zařízení ke službě Azure AD *všem***</span><span class="sxs-lookup"><span data-stu-id="e346a-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="e346a-155">**Možnost 2:** Udělení oprávnění vybraným uživatelům nebo skupinám k připojení zařízení k Azure AD **přihlášení k Azure Portal jako správce**  >  **Azure Active Directory**  >  **zařízení**  >  **nastavení zařízení**  >
 **Uživatelé můžou ke *zvolené* imagi připojit zařízení do Azure AD a** 
 ![ zobrazit tak konfiguraci zařízení připojených k Azure AD.](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="e346a-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="e346a-156">**Možnost 3:** Můžete zablokovat všem uživatelům připojení svých zařízení k doméně.</span><span class="sxs-lookup"><span data-stu-id="e346a-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="e346a-157">To znamená, že všechna zařízení bude nutné zaregistrovat ručně.</span><span class="sxs-lookup"><span data-stu-id="e346a-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="e346a-158">Doprovodné materiály pro Mobile Správce zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="e346a-159">Probíhající Správa zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="e346a-160">Tento krok je nezbytný pouze v případě, že vaše společnost plánuje správu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e346a-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="e346a-161">Probíhající Správa zařízení bude záviset na infrastruktuře správy mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="e346a-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="e346a-162">Většina má stejné obecné funkce, ale uživatelské rozhraní se může výrazně lišit.</span><span class="sxs-lookup"><span data-stu-id="e346a-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="e346a-163">[CSP (poskytovatelé konfigurační služby)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umožňují vytvářet a nasazovat nastavení správy pro zařízení ve vaší síti.</span><span class="sxs-lookup"><span data-stu-id="e346a-163">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="e346a-164">Podívejte se na [seznam zprostředkovatelů HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) pro účely reference.</span><span class="sxs-lookup"><span data-stu-id="e346a-164">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="e346a-165">[Zásady dodržování předpisů](https://docs.microsoft.com/intune/device-compliance-get-started) jsou pravidla a nastavení, která musí zařízení splňovat, aby splňovala předpisy vaší podnikové infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="e346a-165">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="e346a-166">Pomocí těchto zásad s podmíněným přístupem Zablokujte přístup k prostředkům společnosti pro zařízení, která nedodržují předpisy.</span><span class="sxs-lookup"><span data-stu-id="e346a-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="e346a-167">Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="e346a-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="e346a-168">[Vytvořte zásady dodržování předpisů](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="e346a-168">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="e346a-169">Podmíněný přístup povoluje nebo zakazuje mobilním zařízením a mobilním aplikacím přístup k prostředkům společnosti.</span><span class="sxs-lookup"><span data-stu-id="e346a-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="e346a-170">Užitečné dva dokumenty vám pomohou při [Plánování nasazení certifikační autority](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) a [osvědčených postupů](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span><span class="sxs-lookup"><span data-stu-id="e346a-170">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="e346a-171">[Tento článek](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) pojednává o nástrojích pro správu Intune pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e346a-171">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="e346a-172">Vytvoření profilu zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-172">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="e346a-173">Správa aktualizací</span><span class="sxs-lookup"><span data-stu-id="e346a-173">Manage updates</span></span>

<span data-ttu-id="e346a-174">Intune zahrnuje funkci nazvanou aktualizační kanály pro zařízení s Windows 10, včetně HoloLens 2 a HoloLens V1 (s holografickým pro firmy).</span><span class="sxs-lookup"><span data-stu-id="e346a-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="e346a-175">Aktualizační kanály zahrnují skupinu nastavení, která určují, jak a kdy se mají aktualizace instalovat.</span><span class="sxs-lookup"><span data-stu-id="e346a-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="e346a-176">Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat.</span><span class="sxs-lookup"><span data-stu-id="e346a-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="e346a-177">Můžete se také rozhodnout pozastavit aktualizace po neomezenou dobu, dokud nebudete připraveni na aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="e346a-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="e346a-178">Přečtěte si další informace o [konfiguraci aktualizačních kanálů s Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="e346a-178">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="e346a-179">Správa aplikací</span><span class="sxs-lookup"><span data-stu-id="e346a-179">Application management</span></span>

<span data-ttu-id="e346a-180">Spravovat aplikace HoloLens prostřednictvím:</span><span class="sxs-lookup"><span data-stu-id="e346a-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="e346a-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e346a-181">Microsoft Store</span></span>  
  <span data-ttu-id="e346a-182">Microsoft Store je nejlepším způsobem, jak distribuovat a využívat aplikace na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e346a-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="e346a-183">Ve Storu už je k dispozici skvělá sada základních aplikací HoloLens nebo můžete [publikovat vlastní](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="e346a-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="e346a-184">Všechny aplikace v obchodě jsou veřejně dostupné všem, ale pokud to není přijatelné, rezervujte Microsoft Store pro firmy.</span><span class="sxs-lookup"><span data-stu-id="e346a-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="e346a-185">Microsoft Store pro firmy</span><span class="sxs-lookup"><span data-stu-id="e346a-185">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="e346a-186">Microsoft Store pro firmy a vzdělávání je vlastní úložiště pro vaše podnikové prostředí.</span><span class="sxs-lookup"><span data-stu-id="e346a-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="e346a-187">Umožňuje použít Microsoft Store integrovaný do Windows 10 a HoloLens k hledání, získávání, distribuci a správě aplikací pro vaši organizaci.</span><span class="sxs-lookup"><span data-stu-id="e346a-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="e346a-188">Umožňuje taky nasazovat aplikace, které jsou specifické pro vaše komerční prostředí, ale ne pro celý svět.</span><span class="sxs-lookup"><span data-stu-id="e346a-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="e346a-189">Nasazení a Správa aplikací přes Intune nebo jiné řešení pro správu mobilních zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="e346a-190">Většina řešení pro správu mobilních zařízení, včetně Intune, nabízí způsob, jak nasazovat obchodní aplikace přímo do sady zaregistrovaných zařízení.</span><span class="sxs-lookup"><span data-stu-id="e346a-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="e346a-191">Viz tento článek [instalace aplikace Intune](https://docs.microsoft.com/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="e346a-191">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="e346a-192">_nedoporučuje se_ Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="e346a-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="e346a-193">Aplikace můžete nainstalovat také přímo na HoloLens pomocí portálu zařízení Windows.</span><span class="sxs-lookup"><span data-stu-id="e346a-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="e346a-194">Tato možnost se nedoporučuje, protože je nutné povolit režim vývojářů, aby bylo možné používat portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="e346a-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="e346a-195">Přečtěte si další informace o [instalaci aplikací na HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="e346a-195">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <a name="certificates"></a><span data-ttu-id="e346a-196">Certifikáty</span><span class="sxs-lookup"><span data-stu-id="e346a-196">Certificates</span></span>

<span data-ttu-id="e346a-197">Certifikáty můžete distribuovat prostřednictvím poskytovatele MDM.</span><span class="sxs-lookup"><span data-stu-id="e346a-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="e346a-198">Pokud vaše společnost vyžaduje certifikáty, podporuje Intune PKCS, PFX a SCEP.</span><span class="sxs-lookup"><span data-stu-id="e346a-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="e346a-199">Je důležité pochopit, který certifikát je pro vaši společnost nejvhodnější.</span><span class="sxs-lookup"><span data-stu-id="e346a-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="e346a-200">Navštivte prosím dokumentaci [Konfigurace certifikátů](https://docs.microsoft.com/intune/protect/certificates-configure) a určete, který certifikát je pro vás nejvhodnější.</span><span class="sxs-lookup"><span data-stu-id="e346a-200">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="e346a-201">Pokud máte v plánu používat certifikáty pro ověřování HoloLens, PFX nebo SCEP může být pro vás to pravé.</span><span class="sxs-lookup"><span data-stu-id="e346a-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="e346a-202">Informace o používání [scep najdete v následujících krocích.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="e346a-202">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="e346a-203">Postup upgradu na Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="e346a-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="e346a-204">Windows Holographics for Business (komerční sada) je určená jenom pro zařízení HoloLens 1. generace.</span><span class="sxs-lookup"><span data-stu-id="e346a-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="e346a-205">Profil se nebude aplikovat na zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e346a-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="e346a-206">Pokyny k upgradu na komerční sadu najdete v dokumentaci [k holografickému](https://docs.microsoft.com/intune/configuration/holographic-upgrade) upgradu.</span><span class="sxs-lookup"><span data-stu-id="e346a-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="e346a-207">Konfigurace bezobrazovkového režimu pomocí Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e346a-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="e346a-208">Synchronizace Microsoft Store s Intune (viz následující [pokyny).](https://docs.microsoft.com/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="e346a-208">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="e346a-209">Kontrola nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="e346a-209">Check your app settings</span></span>
    1. <span data-ttu-id="e346a-210">Přihlaste se ke svému Microsoft Store Business.</span><span class="sxs-lookup"><span data-stu-id="e346a-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="e346a-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span><span class="sxs-lookup"><span data-stu-id="e346a-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="e346a-212">Pokud nevidíte aplikaci, kterou chcete, budete ji muset "získat" vyhledáním aplikace v obchodě.</span><span class="sxs-lookup"><span data-stu-id="e346a-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="e346a-213">Klikněte na panel Hledat v pravém horním rohu > zadejte název aplikace > klikněte na aplikaci **> vyberte Získat.**</span><span class="sxs-lookup"><span data-stu-id="e346a-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="e346a-214">Pokud aplikace v Intune > **Client Apps > Apps** nevidíte, možná budete muset aplikace [znovu](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) synchronizovat.</span><span class="sxs-lookup"><span data-stu-id="e346a-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="e346a-215">Vytvoření profilu zařízení pro beznaioskový režim</span><span class="sxs-lookup"><span data-stu-id="e346a-215">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="e346a-216">Různé uživatele můžete nakonfigurovat tak, aby měli různá prostředí v bezobrazovkovém režimu. Jako typ přihlášení uživatele můžete použít Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e346a-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="e346a-217">Tato možnost je ale dostupná jenom v bezobrazovkovém režimu s více aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="e346a-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="e346a-218">Bezobrazovový režim s více aplikacemi bude fungovat jenom s jednou aplikací a několika aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="e346a-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Obrázek znázorňuje konfiguraci bezobrazovkového režimu v Intune](images/aad-kioskmode.png)

<span data-ttu-id="e346a-220">Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli.</span><span class="sxs-lookup"><span data-stu-id="e346a-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="e346a-221">Pokud potřebujete k nastavení veřejného terminálu ve službě MDM použít vlastní nastavení a úplnou konfiguraci XML, přečtěte si pokyny k beznaiosku [HoloLens.](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="e346a-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="e346a-222">Certifikáty a ověřování</span><span class="sxs-lookup"><span data-stu-id="e346a-222">Certificates and Authentication</span></span>

<span data-ttu-id="e346a-223">Certifikáty je možné nasadit prostřednictvím MDM (viz "certifikáty" v části [MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="e346a-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="e346a-224">Certifikáty je také možné nasadit do HoloLens prostřednictvím zřizování balíčků.</span><span class="sxs-lookup"><span data-stu-id="e346a-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="e346a-225">Další informace [najdete v tématu Zřizování HoloLens.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e346a-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="e346a-226">Další rychlé odkazy pro Intune</span><span class="sxs-lookup"><span data-stu-id="e346a-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="e346a-227">[Vytvoření profilů:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profily umožňují přidávat a konfigurovat nastavení, která se budou předát do zařízení ve vaší organizaci.</span><span class="sxs-lookup"><span data-stu-id="e346a-227">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

