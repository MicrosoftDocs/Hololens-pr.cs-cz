---
title: Pokyny k infrastruktuře HoloLens
description: Seznamte se s pokyny pro infrastrukturu HoloLens zařízení, včetně podpory bezdrátové sítě, vzdálené pomoci a správy mobilních zařízení.
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639280"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="880c1-103">Konfigurace sítě pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="880c1-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="880c1-104">Tato část dokumentu bude vyžadovat následující osoby:</span><span class="sxs-lookup"><span data-stu-id="880c1-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="880c1-105">Správce sítě s oprávněními k provedení změn proxy serveru nebo brány firewall</span><span class="sxs-lookup"><span data-stu-id="880c1-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="880c1-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="880c1-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="880c1-107">Správce mobilních Správce zařízení</span><span class="sxs-lookup"><span data-stu-id="880c1-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="880c1-108">Požadavky na infrastrukturu</span><span class="sxs-lookup"><span data-stu-id="880c1-108">Infrastructure Requirements</span></span>

<span data-ttu-id="880c1-109">HoloLens jádrem je mobilní zařízení Windows integrované s Azure.</span><span class="sxs-lookup"><span data-stu-id="880c1-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="880c1-110">Funguje nejlépe v komerčních prostředích s dostupností bezdrátové sítě (Wi-Fi) a přístupem k služby Microsoft.</span><span class="sxs-lookup"><span data-stu-id="880c1-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="880c1-111">Mezi důležité cloudové služby patří:</span><span class="sxs-lookup"><span data-stu-id="880c1-111">Critical cloud services include:</span></span>

- <span data-ttu-id="880c1-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="880c1-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="880c1-113">Windows Aktualizace (WU)</span><span class="sxs-lookup"><span data-stu-id="880c1-113">Windows Update (WU)</span></span>

<span data-ttu-id="880c1-114">Komerční zákazníci budou potřebovat infrastrukturu správy podnikové mobility (EMM) nebo správy mobilních zařízení (MDM), aby HoloLens zařízení ve velkém měřítku.</span><span class="sxs-lookup"><span data-stu-id="880c1-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="880c1-115">V této příručce [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) příklad, i když každý poskytovatel s plnou podporou služby Microsoft Policy může HoloLens.</span><span class="sxs-lookup"><span data-stu-id="880c1-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="880c1-116">Zeptejte se poskytovatele správy mobilních zařízení, jestli podporuje HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="880c1-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="880c1-117">HoloLens podporuje omezenou sadu prostředí odpojených od cloudu.</span><span class="sxs-lookup"><span data-stu-id="880c1-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="880c1-118">Podpora protokolu EAP bezdrátové sítě</span><span class="sxs-lookup"><span data-stu-id="880c1-118">Wireless network EAP support</span></span>

- <span data-ttu-id="880c1-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="880c1-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="880c1-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="880c1-120">PEAP-TLS</span></span>
- <span data-ttu-id="880c1-121">TLS</span><span class="sxs-lookup"><span data-stu-id="880c1-121">TLS</span></span>
- <span data-ttu-id="880c1-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="880c1-122">TTLS-CHAP</span></span>
- <span data-ttu-id="880c1-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="880c1-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="880c1-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="880c1-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="880c1-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="880c1-125">TTLS-PAP</span></span>
- <span data-ttu-id="880c1-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="880c1-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="880c1-127">HoloLens Specifické požadavky na síť</span><span class="sxs-lookup"><span data-stu-id="880c1-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="880c1-128">Ujistěte se, [že je v](hololens-offline.md) síťové bráně firewall povolený tento seznam koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="880c1-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="880c1-129">To umožní, HoloLens správně fungovat.</span><span class="sxs-lookup"><span data-stu-id="880c1-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="880c1-130">Požadavky na síť specifické pro Remote Assist</span><span class="sxs-lookup"><span data-stu-id="880c1-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="880c1-131">Doporučená šířka pásma pro optimální výkon nástroje Remote Assist je 1,5 Mb/s.</span><span class="sxs-lookup"><span data-stu-id="880c1-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="880c1-132">Další informace [najdete v podrobných požadavcích](/MicrosoftTeams/prepare-network) na síť.</span><span class="sxs-lookup"><span data-stu-id="880c1-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="880c1-133">**(Upozorňujeme, že pokud nemáte síť s rychlostí alespoň 1,5 Mb/s, remote assist bude i nadále fungovat. Může ale utrpět kvalita.**</span><span class="sxs-lookup"><span data-stu-id="880c1-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="880c1-134">Ujistěte se, že tyto porty a adresy URL jsou ve vaší síťové bráně firewall povolené, aby Microsoft Teams fungovaly.</span><span class="sxs-lookup"><span data-stu-id="880c1-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="880c1-135">Nejnovější seznam portů [vám bude aktuální.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="880c1-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="880c1-136">Další informace o konkrétních požadavcích [na síť pro remote assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="880c1-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="880c1-137">Další informace o přípravě [sítě organizace na Microsoft Teams](/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="880c1-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="880c1-138">Průvodci konkrétními požadavky na síť</span><span class="sxs-lookup"><span data-stu-id="880c1-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="880c1-139">Průvodci ke stažení a používání aplikace vyžadují jenom síťový přístup.</span><span class="sxs-lookup"><span data-stu-id="880c1-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="880c1-140">Azure Active Directory Pokyny</span><span class="sxs-lookup"><span data-stu-id="880c1-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="880c1-141">Tento krok je nezbytný pouze v případě, že vaše společnost plánuje spravovat HoloLens.</span><span class="sxs-lookup"><span data-stu-id="880c1-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="880c1-142">Ujistěte se, že máte licenci Azure AD.</span><span class="sxs-lookup"><span data-stu-id="880c1-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="880c1-143">Další [HoloLens v požadavcích](hololens-licenses-requirements.md) na licence.</span><span class="sxs-lookup"><span data-stu-id="880c1-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="880c1-144">Pokud plánujete používat automatickou registraci, budete muset [nakonfigurovat registraci Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="880c1-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="880c1-145">Ujistěte se, že jsou uživatelé vaší společnosti ve službě Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="880c1-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="880c1-146">Pokud chcete přidat [uživatele, přečtěte](/azure/active-directory/fundamentals/add-users-azure-active-directory) si následující pokyny.</span><span class="sxs-lookup"><span data-stu-id="880c1-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="880c1-147">Doporučujeme, aby uživatelé, kteří potřebují podobné licence, byli přidáni do stejné skupiny.</span><span class="sxs-lookup"><span data-stu-id="880c1-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="880c1-148">Vytvoření skupiny</span><span class="sxs-lookup"><span data-stu-id="880c1-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="880c1-149">Přidání uživatelů do skupin</span><span class="sxs-lookup"><span data-stu-id="880c1-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="880c1-150">Zajistěte, aby uživatelům (nebo skupině uživatelů) vaší společnosti byly přiřazeny potřebné licence.</span><span class="sxs-lookup"><span data-stu-id="880c1-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="880c1-151">Pokud potřebujete přiřadit licence, postupujte podle [těchto pokynů.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="880c1-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="880c1-152">Tento krok proveďte jenom v případě, že se od uživatelů očekává, že si do vás zaregistrují zařízení HoloLens/Mobile (Existují tři možnosti). Tyto kroky zajistí, aby uživatelé vaší společnosti (nebo skupina uživatelů) mohli přidat zařízení.</span><span class="sxs-lookup"><span data-stu-id="880c1-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="880c1-153">**Možnost 1:** Udejte všem uživatelům oprávnění k připojení zařízení k Azure AD.</span><span class="sxs-lookup"><span data-stu-id="880c1-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="880c1-154">**Přihlaste se k Azure Portal jako správce.**  >  **Azure Active Directory**  >  **Zařízení**  >  **Device Nastavení**  >
 **Nastavte možnost Uživatelé smí připojovat zařízení k Azure AD na *Vše.***</span><span class="sxs-lookup"><span data-stu-id="880c1-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="880c1-155">**Možnost 2:** Udělit vybraným uživatelům nebo skupinám oprávnění pro připojení zařízení k Azure AD Přihlásit se k **Azure Portal** jako správce  >  **Azure Active Directory** Devices Device Nastavení Set Users may join devices to Azure AD to Selected Image that shows Configuration of Azure AD Joined Devices  >    >  **(Konfigurace**  >
 \*\*\*\* 
 zařízení připojených ke službě ![ Azure AD)](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="880c1-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="880c1-156">**Možnost 3:** Všem uživatelům můžete zablokovat připojení svých zařízení k doméně.</span><span class="sxs-lookup"><span data-stu-id="880c1-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="880c1-157">To znamená, že všechna zařízení budou muset být ručně zaregistrovaná.</span><span class="sxs-lookup"><span data-stu-id="880c1-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="880c1-158">Pokyny Správce zařízení mobilních aplikacích</span><span class="sxs-lookup"><span data-stu-id="880c1-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="880c1-159">Průběžná správa zařízení</span><span class="sxs-lookup"><span data-stu-id="880c1-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="880c1-160">Tento krok je nezbytný pouze v případě, že vaše společnost plánuje spravovat HoloLens.</span><span class="sxs-lookup"><span data-stu-id="880c1-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="880c1-161">Průběžná správa zařízení bude záviset na infrastruktuře správy mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="880c1-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="880c1-162">Většina má stejné obecné funkce, ale uživatelské rozhraní se může výrazně lišit.</span><span class="sxs-lookup"><span data-stu-id="880c1-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="880c1-163">[Poskytovatelé konfiguračních služeb (CSP)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umožňují vytvářet a nasazovat nastavení správy pro zařízení ve vaší síti.</span><span class="sxs-lookup"><span data-stu-id="880c1-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="880c1-164">Referenční informace [najdete v HoloLens csP.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)</span><span class="sxs-lookup"><span data-stu-id="880c1-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="880c1-165">[Zásady dodržování](/intune/device-compliance-get-started) předpisů jsou pravidla a nastavení, která zařízení musí splňovat, aby splňovala předpisy ve vaší podnikové infrastruktuře.</span><span class="sxs-lookup"><span data-stu-id="880c1-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="880c1-166">Pomocí těchto zásad s podmíněným přístupem můžete blokovat přístup k prostředkům společnosti pro zařízení, která nedodržují předpisy.</span><span class="sxs-lookup"><span data-stu-id="880c1-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="880c1-167">Můžete třeba vytvořit zásadu, která vyžaduje zapnutý Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="880c1-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="880c1-168">[Vytvořte zásady dodržování předpisů.](/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="880c1-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="880c1-169">Podmíněný přístup umožňuje nebo odmítá mobilním zařízením a mobilním aplikacím přístup k prostředkům společnosti.</span><span class="sxs-lookup"><span data-stu-id="880c1-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="880c1-170">K dispozici jsou dva užitečné dokumenty: [Plánování nasazení certifikační autority a](/azure/active-directory/conditional-access/plan-conditional-access) osvědčené [postupy.](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="880c1-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="880c1-171">[Tento článek](/intune/fundamentals/windows-holographic-for-business) popisuje nástroje pro správu Intune pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="880c1-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="880c1-172">Vytvoření profilu zařízení</span><span class="sxs-lookup"><span data-stu-id="880c1-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="880c1-173">Správa aktualizací</span><span class="sxs-lookup"><span data-stu-id="880c1-173">Manage updates</span></span>

<span data-ttu-id="880c1-174">Intune obsahuje funkci s názvem Aktualizační okruhy pro Windows 10 zařízení, včetně HoloLens 2 a HoloLens v1 (s Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="880c1-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="880c1-175">Aktualizační okruhy obsahují skupinu nastavení, která určují, jak a kdy se mají aktualizace instalovat.</span><span class="sxs-lookup"><span data-stu-id="880c1-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="880c1-176">Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat.</span><span class="sxs-lookup"><span data-stu-id="880c1-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="880c1-177">Můžete se také rozhodnout pozastavit aktualizace po neomezenou dobu, dokud nebude aktualizace připravená.</span><span class="sxs-lookup"><span data-stu-id="880c1-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="880c1-178">Přečtěte si další [informace o konfiguraci aktualizačních okruhů pomocí Intune.](/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="880c1-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="880c1-179">Správa aplikací</span><span class="sxs-lookup"><span data-stu-id="880c1-179">Application management</span></span>

<span data-ttu-id="880c1-180">Správa HoloLens aplikací prostřednictvím:</span><span class="sxs-lookup"><span data-stu-id="880c1-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="880c1-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="880c1-181">Microsoft Store</span></span>  
  <span data-ttu-id="880c1-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span><span class="sxs-lookup"><span data-stu-id="880c1-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="880c1-183">K dispozici je skvělá sada základních aplikací HoloLens jsou už ve Storu k dispozici, nebo můžete [publikovat vlastní](/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="880c1-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="880c1-184">Všechny aplikace ve Storu jsou veřejně dostupné všem, ale pokud to není přijatelné, Microsoft Store pro firmy.</span><span class="sxs-lookup"><span data-stu-id="880c1-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="880c1-185">Microsoft Store pro firmy</span><span class="sxs-lookup"><span data-stu-id="880c1-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="880c1-186">Microsoft Store pro firmy a Education je vlastní obchod pro vaše podnikové prostředí.</span><span class="sxs-lookup"><span data-stu-id="880c1-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="880c1-187">Umožňuje používat integrované Microsoft Store a Windows 10 HoloLens k vyhledání, získání, distribuci a správě aplikací pro vaši organizaci.</span><span class="sxs-lookup"><span data-stu-id="880c1-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="880c1-188">Umožňuje také nasazovat aplikace, které jsou specifické pro vaše komerční prostředí, ale ne pro celý svět.</span><span class="sxs-lookup"><span data-stu-id="880c1-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="880c1-189">Nasazení a správa aplikací přes Intune nebo jiné řešení pro správu mobilních zařízení</span><span class="sxs-lookup"><span data-stu-id="880c1-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="880c1-190">Většina řešení pro správu mobilních zařízení, včetně Intune, poskytuje způsob, jak nasadit obchodní aplikace přímo do sady zaregistrovaných zařízení.</span><span class="sxs-lookup"><span data-stu-id="880c1-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="880c1-191">Informace o instalaci aplikací [Intune najdete v tomto článku.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="880c1-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="880c1-192">_nedoporučuje se_ Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="880c1-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="880c1-193">Aplikace se také instalují do HoloLens přímo pomocí Windows Portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="880c1-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="880c1-194">To se nedoporučuje, protože pro používání portálu zařízení musí být povolený vývojářský režim.</span><span class="sxs-lookup"><span data-stu-id="880c1-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="880c1-195">Přečtěte si další [informace o instalaci aplikací na HoloLens](hololens-install-apps.md).</span><span class="sxs-lookup"><span data-stu-id="880c1-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="880c1-196">Certifikáty</span><span class="sxs-lookup"><span data-stu-id="880c1-196">Certificates</span></span>

<span data-ttu-id="880c1-197">Certifikáty můžete distribuovat prostřednictvím poskytovatele MDM.</span><span class="sxs-lookup"><span data-stu-id="880c1-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="880c1-198">Pokud vaše společnost vyžaduje certifikáty, Intune podporuje PKCS, PFX a SCEP.</span><span class="sxs-lookup"><span data-stu-id="880c1-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="880c1-199">Je důležité pochopit, který certifikát je pro vaši společnost správný.</span><span class="sxs-lookup"><span data-stu-id="880c1-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="880c1-200">Pokud chcete [zjistit, který](/intune/protect/certificates-configure) certifikát je pro vás nejlepší, projděte si dokumentaci ke konfiguracím certifikátů.</span><span class="sxs-lookup"><span data-stu-id="880c1-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="880c1-201">Pokud plánujete používat certifikáty pro ověřování HoloLens, pfx nebo SCEP může být pro vás to pravé.</span><span class="sxs-lookup"><span data-stu-id="880c1-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="880c1-202">Informace o používání [scep najdete v následujících krocích.](/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="880c1-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="880c1-203">Postup upgradu na Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="880c1-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="880c1-204">Windows Holographics for Business (komerční sada) je určená jenom HoloLens 1. generace.</span><span class="sxs-lookup"><span data-stu-id="880c1-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="880c1-205">Profil se nebude aplikovat na HoloLens 2 zařízení.</span><span class="sxs-lookup"><span data-stu-id="880c1-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="880c1-206">Pokyny k upgradu na komerční sadu najdete v dokumentaci [k holografickému](/intune/configuration/holographic-upgrade) upgradu.</span><span class="sxs-lookup"><span data-stu-id="880c1-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="880c1-207">Konfigurace bezobrazovkového režimu pomocí Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="880c1-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="880c1-208">Synchronizace Microsoft Store s Intune (viz následující [pokyny).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="880c1-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="880c1-209">Kontrola nastavení aplikace</span><span class="sxs-lookup"><span data-stu-id="880c1-209">Check your app settings</span></span>
    1. <span data-ttu-id="880c1-210">Přihlaste se ke svému Microsoft Store Business.</span><span class="sxs-lookup"><span data-stu-id="880c1-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="880c1-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span><span class="sxs-lookup"><span data-stu-id="880c1-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="880c1-212">Pokud nevidíte aplikaci, kterou chcete, budete ji muset "získat" vyhledáním aplikace v obchodě.</span><span class="sxs-lookup"><span data-stu-id="880c1-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="880c1-213">Klikněte na panel Hledat v pravém horním rohu > zadejte název aplikace > klikněte na aplikaci > **vyberte Získat.**</span><span class="sxs-lookup"><span data-stu-id="880c1-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="880c1-214">Pokud aplikace v Intune > **Client Apps > Apps** nevidíte, možná budete muset aplikace [znovu](/intune/apps/windows-store-for-business#synchronize-apps) synchronizovat.</span><span class="sxs-lookup"><span data-stu-id="880c1-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="880c1-215">Vytvoření profilu zařízení pro beznaioskový režim</span><span class="sxs-lookup"><span data-stu-id="880c1-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="880c1-216">Různé uživatele můžete nakonfigurovat tak, aby měli různá prostředí v bezobrazovkovém režimu. Jako typ přihlášení uživatele můžete použít Azure AD.</span><span class="sxs-lookup"><span data-stu-id="880c1-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="880c1-217">Tato možnost je ale dostupná jenom v bezobrazovkovém režimu s více aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="880c1-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="880c1-218">Bezobrazovový režim s více aplikacemi bude fungovat jenom s jednou aplikací a několika aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="880c1-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Obrázek znázorňuje konfiguraci bezobrazovkového režimu v Intune](images/aad-kioskmode.png)

<span data-ttu-id="880c1-220">Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli.</span><span class="sxs-lookup"><span data-stu-id="880c1-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="880c1-221">Pokud k nastavení [veřejného HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) MDM potřebujete vlastní nastavení a úplnou konfiguraci XML, přečtěte si pokyny k beznaiosku.</span><span class="sxs-lookup"><span data-stu-id="880c1-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="880c1-222">Certifikáty a ověřování</span><span class="sxs-lookup"><span data-stu-id="880c1-222">Certificates and Authentication</span></span>

<span data-ttu-id="880c1-223">Certifikáty je možné nasadit prostřednictvím MDM (viz "certifikáty" v části [MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="880c1-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="880c1-224">Certifikáty je také možné nasadit do HoloLens prostřednictvím zřizování balíčků.</span><span class="sxs-lookup"><span data-stu-id="880c1-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="880c1-225">Další [informace HoloLens v tématu o](hololens-provisioning.md) zřizování prostředků.</span><span class="sxs-lookup"><span data-stu-id="880c1-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="880c1-226">Další rychlé odkazy pro Intune</span><span class="sxs-lookup"><span data-stu-id="880c1-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="880c1-227">[Vytvoření profilů:](/intune/configuration/device-profile-create) Profily umožňují přidávat a konfigurovat nastavení, která se budou předát do zařízení ve vaší organizaci.</span><span class="sxs-lookup"><span data-stu-id="880c1-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

