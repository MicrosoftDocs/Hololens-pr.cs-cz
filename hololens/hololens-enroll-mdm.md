---
title: registrace HoloLens v MDM
description: naučte se, jak zaregistrovat HoloLens ve správě mobilních zařízení (MDM) pro snazší správu více zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640402"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="821b2-103">registrace HoloLens v MDM</span><span class="sxs-lookup"><span data-stu-id="821b2-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="821b2-104">pomocí řešení jako [Microsoft Intune](/intune/windows-holographic-for-business)můžete spravovat více Microsoft HoloLens zařízení současně.</span><span class="sxs-lookup"><span data-stu-id="821b2-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="821b2-105">Budete moct spravovat nastavení, vybrat aplikace, které chcete nainstalovat, a nastavit konfigurace zabezpečení přizpůsobené potřebám vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="821b2-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="821b2-106">přečtěte si téma [správa zařízení se systémem Windows holografická s Microsoft Intune](/intune/windows-holographic-for-business), [poskytovateli konfiguračních služeb (csp), které jsou podporovány v Windowsových holografickích](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), a [zásady podporované Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="821b2-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="821b2-107">Správa mobilních zařízení (MDM), včetně funkcí sítě VPN, BitLocker a celoobrazovkového režimu, je k dispozici pouze při [upgradu na Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="821b2-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="821b2-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="821b2-108">Requirements</span></span>

 <span data-ttu-id="821b2-109">aby bylo možné spravovat HoloLens zařízení, bude nutné, aby vaše organizace měla nastavenou správu mobilních zařízení (MDM).</span><span class="sxs-lookup"><span data-stu-id="821b2-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="821b2-110">váš poskytovatel MDM může být Microsoft Intune nebo poskytovatel třetí strany, který používá rozhraní Microsoft MDM api.</span><span class="sxs-lookup"><span data-stu-id="821b2-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="821b2-111">Různé způsoby registrace</span><span class="sxs-lookup"><span data-stu-id="821b2-111">Different ways to enroll</span></span>

<span data-ttu-id="821b2-112">V závislosti na typu [identity](hololens-identity.md) , který jste zvolili při počátečním spuštění nebo po přihlášení, existují různé metody registrace.</span><span class="sxs-lookup"><span data-stu-id="821b2-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="821b2-113">pokud se jedná o službu Azure AD, pak buď během počátečního nastavení, nebo v aplikaci **Nastavení**  ->  **accessového nebo školním**  ->  tlačítku **Připojení** .</span><span class="sxs-lookup"><span data-stu-id="821b2-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="821b2-114">V případě Azure AD dojde k [automatické registraci MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) jenom v případě, že je služba Azure AD nakonfigurovaná s adresami URL pro zápis.</span><span class="sxs-lookup"><span data-stu-id="821b2-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="821b2-115">Pokud je identita Azure AD a u zařízení se systémem Intune MDM, ke kterému je přiřazený určitý nakonfigurovaný profil, používá předregistrovaná identita, pak při spuštění služby Azure AD-Join a [automatické registraci MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) dojde k zápisu v rámci služby OOBE.</span><span class="sxs-lookup"><span data-stu-id="821b2-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="821b2-116">Také označovaný jako [autopilot Flow](hololens2-autopilot.md) dostupný v [sestaveních 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="821b2-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="821b2-117">pokud je identita MSAá, použijte   ->  tlačítko pro **přístup k práci nebo škole**  ->  **Připojení** aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="821b2-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="821b2-118">Také se nazývá AWA (Přidat pracovní účet).</span><span class="sxs-lookup"><span data-stu-id="821b2-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="821b2-119">pokud je identita místní uživatel, pak pomocí aplikace **Nastavení**  ->  **přístup k aplikaci v pracovním nebo školním**  ->  **zápisu jenom v odkazu správa zařízení** .</span><span class="sxs-lookup"><span data-stu-id="821b2-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="821b2-120">Označuje se taky jako čistý tok zápisu MDM.</span><span class="sxs-lookup"><span data-stu-id="821b2-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="821b2-121">jakmile je zařízení zaregistrované ve vašem serveru MDM, Nastavení aplikace teď odrážejí, že je zařízení zaregistrované ve správě zařízení.</span><span class="sxs-lookup"><span data-stu-id="821b2-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="821b2-122">Automatické registrace v MDM</span><span class="sxs-lookup"><span data-stu-id="821b2-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="821b2-123">pokud má vaše organizace [předplatné azure Premium](https://azure.microsoft.com/overview/), používá Azure Active Directory (Azure ad) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje jenom v Microsoft Intune a sledování), může správce IT nakonfigurovat službu Azure ad tak, aby po přihlášení uživatele k účtu azure ad automaticky povolovala registraci MDM.</span><span class="sxs-lookup"><span data-stu-id="821b2-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="821b2-124">Přečtěte si, jak nakonfigurovat registraci Azure AD.</span><span class="sxs-lookup"><span data-stu-id="821b2-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="821b2-125">Pokud je povolená Automatická registrace, nevyžaduje se žádná další ruční registrace.</span><span class="sxs-lookup"><span data-stu-id="821b2-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="821b2-126">Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se zaregistruje do MDM po dokončení prvního spuštění prostředí.</span><span class="sxs-lookup"><span data-stu-id="821b2-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="821b2-127">Když je zařízení připojené k Azure AD, může to mít vliv na to, kdo posuzuje [vlastníka zařízení](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="821b2-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="821b2-128">zrušit registraci HoloLens v intune</span><span class="sxs-lookup"><span data-stu-id="821b2-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="821b2-129">V závislosti na metodě registrace možná nebude k dispozici zrušení registrace zařízení.</span><span class="sxs-lookup"><span data-stu-id="821b2-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="821b2-130">Pokud je vaše zařízení zaregistrované s účtem služby Azure AD nebo s automatickým pilotním, nedá se zrušit jeho registrace v Intune.</span><span class="sxs-lookup"><span data-stu-id="821b2-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="821b2-131">pokud chcete zrušit připojení HoloLens z Azure ad nebo ho znovu připojit k jinému klientovi Azure ad, musíte zařízení [resetovat nebo znovu zablikat](hololens-recovery.md#reset-the-device) .</span><span class="sxs-lookup"><span data-stu-id="821b2-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="821b2-132">Pokud bylo zařízení zaregistrováno z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který byl zaregistrován pouze ve správě zařízení, můžete zrušit registraci zařízení.</span><span class="sxs-lookup"><span data-stu-id="821b2-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="821b2-133">otevřete nabídka Start a pak klikněte na tlačítko přístup k **aplikaci Nastavení**  ->  **Work nebo School**  ->  *YourAccount*  ->  **disconnect** .</span><span class="sxs-lookup"><span data-stu-id="821b2-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>