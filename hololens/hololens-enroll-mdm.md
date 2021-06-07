---
title: Registrace HoloLens v MDM
description: Zjistěte, jak zaregistrovat HoloLens ve správě mobilních zařízení (MDM), abyste usnadnili správu více zařízení.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377680"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="86a43-103">Registrace HoloLens v MDM</span><span class="sxs-lookup"><span data-stu-id="86a43-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="86a43-104">Pomocí řešení, jako je Microsoft HoloLens , můžete spravovat [více zařízení Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="86a43-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="86a43-105">Budete moct spravovat nastavení, vybrat aplikace pro instalaci a nastavení konfigurací zabezpečení přizpůsobených potřebám vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="86a43-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="86a43-106">Viz [Správa zařízení s Windows Holographic s Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), poskytovatelé konfiguračních služeb [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)podporovaní ve Windows Holographic a zásady podporované službou [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="86a43-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="86a43-107">Správa mobilních zařízení (MDM), včetně funkcí VPN, BitLockeru a bezobrazovkovém režimu, je dostupná jenom při upgradu na [Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="86a43-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="86a43-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="86a43-108">Requirements</span></span>

 <span data-ttu-id="86a43-109">Aby bylo možné spravovat zařízení HoloLens, musí mít vaše organizace nastavenou možnost Mobile Správa zařízení (MDM).</span><span class="sxs-lookup"><span data-stu-id="86a43-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="86a43-110">Váš poskytovatel MDM může být Microsoft Intune třetí strany, který používá rozhraní MICROSOFT MDM API.</span><span class="sxs-lookup"><span data-stu-id="86a43-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="86a43-111">Různé způsoby registrace</span><span class="sxs-lookup"><span data-stu-id="86a43-111">Different ways to enroll</span></span>

<span data-ttu-id="86a43-112">V závislosti na typu [identity zvolené](hololens-identity.md) při OOBE nebo po přihlášení existují různé metody registrace.</span><span class="sxs-lookup"><span data-stu-id="86a43-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="86a43-113">Pokud je Identita Azure AD, pak buď během doby hotového prostředí nebo nastavení Tlačítko Přístup do aplikace do práce  ->  **nebo Do**  ->  **školy.**</span><span class="sxs-lookup"><span data-stu-id="86a43-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="86a43-114">Automatická registrace [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) v Azure AD nastane jenom v případě, že je v Azure AD nakonfigurované adresy URL pro registraci.</span><span class="sxs-lookup"><span data-stu-id="86a43-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="86a43-115">Pokud je identita Azure AD a zařízení je předem zaregistrované na serveru MdM Intune s přiřazeným konkrétním konfiguračním profilem, pak během spuštění počítače dojde k azure AD-Join a automatické registraci [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)</span><span class="sxs-lookup"><span data-stu-id="86a43-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="86a43-116">Říká se jim [také tok Autopilot](hololens2-autopilot.md) dostupný ve [buildech verze 19041.1103 nebo více.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="86a43-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="86a43-117">Pokud je Identita MSA, pak pomocí tlačítka **Settings App**  ->  **Access Work nebo School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="86a43-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="86a43-118">Říká se mu také tok Přidat pracovní účet (AWA).</span><span class="sxs-lookup"><span data-stu-id="86a43-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="86a43-119">Pokud je Identita místní uživatel, pomocí odkazu Nastavení **Přístup do** aplikace do práce nebo Do školy  ->    ->  **se zaregistrujte jenom ve správě** zařízení.</span><span class="sxs-lookup"><span data-stu-id="86a43-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="86a43-120">Říká se jim také čistý tok registrace MDM.</span><span class="sxs-lookup"><span data-stu-id="86a43-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="86a43-121">Jakmile je zařízení zaregistrované na serveru MDM, aplikace Nastavení teď bude odrážet, že je zařízení zaregistrované ve správě zařízení.</span><span class="sxs-lookup"><span data-stu-id="86a43-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="86a43-122">Automatická registrace v MDM</span><span class="sxs-lookup"><span data-stu-id="86a43-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="86a43-123">Pokud má vaše organizace předplatné [Azure Premium](https://azure.microsoft.com/overview/), používá službu Azure Active Directory (Azure AD) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje pouze v Microsoft Intune a AirWatchu), může správce IT nakonfigurovat službu Azure AD tak, aby po přihlášení uživatele pomocí svého účtu Azure AD automaticky povoluje registraci MDM.</span><span class="sxs-lookup"><span data-stu-id="86a43-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="86a43-124">Zjistěte, jak nakonfigurovat registraci Azure AD.</span><span class="sxs-lookup"><span data-stu-id="86a43-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="86a43-125">Pokud je povolená automatická registrace, není potřeba žádná další ruční registrace.</span><span class="sxs-lookup"><span data-stu-id="86a43-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="86a43-126">Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se po dokončení prvního spuštění zapíše do MDM.</span><span class="sxs-lookup"><span data-stu-id="86a43-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="86a43-127">Pokud je zařízení připojené k Azure AD, může to mít vliv na to, kdo ho považuje [za vlastníka.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="86a43-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="86a43-128">Zrušení registrace HoloLens v Intune</span><span class="sxs-lookup"><span data-stu-id="86a43-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="86a43-129">V závislosti na metodě registrace nemusí být registrace zařízení dostupná.</span><span class="sxs-lookup"><span data-stu-id="86a43-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="86a43-130">Pokud bylo vaše zařízení zaregistrované pomocí účtu Azure AD nebo Autopilotu, není možné jeho registrace zrušit v Intune.</span><span class="sxs-lookup"><span data-stu-id="86a43-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="86a43-131">Pokud se chcete připojit k HoloLens z Azure AD nebo se k jinému tenantovi Azure AD připojit znovu, musíte zařízení resetovat [nebo odkazovat](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) na něj.</span><span class="sxs-lookup"><span data-stu-id="86a43-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="86a43-132">Pokud bylo vaše zařízení zaregistrované z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který se zaregistroval jenom ve správě zařízení, můžete registraci zařízení zrušit.</span><span class="sxs-lookup"><span data-stu-id="86a43-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="86a43-133">Otevřete okno nabídka Start pak vyberte Nastavení **Přístup k** aplikaci Do práce nebo Do školy  ->    ->  *VášÚčet*  ->  **Odpojit.**</span><span class="sxs-lookup"><span data-stu-id="86a43-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>