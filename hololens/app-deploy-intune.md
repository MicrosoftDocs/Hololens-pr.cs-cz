---
title: Intune a Portál společnosti
description: Zjistěte, jak nastavit, přiřadit a vytvořit pohodlné uživatelské prostředí pro Intune, správu mobilních zařízení a portál společnosti.
keywords: intune, app management, app, company portal, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377683"
---
# <a name="intune--company-portal"></a><span data-ttu-id="40d46-104">Intune & Portál společnosti</span><span class="sxs-lookup"><span data-stu-id="40d46-104">Intune & Company Portal</span></span>

<span data-ttu-id="40d46-105">S Mobile Správa zařízení (MDM) můžete použít vlastní aplikace prostřednictvím [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) a nasadit je přímo do zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="40d46-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="40d46-106">Microsoft Intune je cloudová služba, která se zaměřuje na správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM).</span><span class="sxs-lookup"><span data-stu-id="40d46-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="40d46-107">Intune je součástí sady [microsoftových Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)a umožňuje uživatelům být produktivní a současně chránit data vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="40d46-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="40d46-108">Další informace o Intune najdete v co [je Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="40d46-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="40d46-109">Nastavení</span><span class="sxs-lookup"><span data-stu-id="40d46-109">Setup</span></span>

1. <span data-ttu-id="40d46-110">Nahrajte aplikaci do obchodního podniku nebo nahrajte vlastní aplikaci do tenanta Intune.</span><span class="sxs-lookup"><span data-stu-id="40d46-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="40d46-111">Viz také: [Správa podnikových aplikací.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="40d46-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="40d46-112">[Přiřaďte aplikaci ke skupině](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="40d46-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="40d46-113">Na základě typu přiřazení, který zvolíte, můžete aplikaci doručit automaticky nebo ji můžete snadno načíst, pokud máte vybrané aplikace.</span><span class="sxs-lookup"><span data-stu-id="40d46-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="40d46-114">Při vytváření sady appx nezapomeňte zohlednit zahrnutí architektury pro zařízení, na která nasazujete.</span><span class="sxs-lookup"><span data-stu-id="40d46-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="40d46-115">HoloLens 2 je ARM64 a HoloLens (1. generace) je x86.</span><span class="sxs-lookup"><span data-stu-id="40d46-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="40d46-116">Pokud plánujete mít prostředí se smíšenými zařízeními, můžete obojí zahrnout do jedné sady appx.</span><span class="sxs-lookup"><span data-stu-id="40d46-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="40d46-117">Typy přiřazení</span><span class="sxs-lookup"><span data-stu-id="40d46-117">Assignment types</span></span>

<span data-ttu-id="40d46-118">Pokud chcete, aby se vaše aplikace po registraci  automaticky nainstalovala na zařízení, měli byste pro tuto skupinu nebo skupiny vybrat Povinné.</span><span class="sxs-lookup"><span data-stu-id="40d46-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="40d46-119">Pokud chcete aplikaci stáhnout do zařízení zaregistrovaná prostřednictvím portálu společnosti, vyberte **Dostupná pro zaregistrovaná zařízení.**</span><span class="sxs-lookup"><span data-stu-id="40d46-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="40d46-120">End-User prostředí</span><span class="sxs-lookup"><span data-stu-id="40d46-120">End-User Experience</span></span>

<span data-ttu-id="40d46-121">Po nastavení konfigurace v Intune jste připraveni koncovým uživatelům přijímat vybrané aplikace.</span><span class="sxs-lookup"><span data-stu-id="40d46-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="40d46-122">Pokud chcete automaticky získat aplikace, postupujte podle těchto kroků:</span><span class="sxs-lookup"><span data-stu-id="40d46-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="40d46-123">Zaregistrujte své zařízení v tenantovi.</span><span class="sxs-lookup"><span data-stu-id="40d46-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="40d46-124">Po dokončení registrace zařízení byste měli aplikaci obdržet na svém zařízení.</span><span class="sxs-lookup"><span data-stu-id="40d46-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="40d46-125">Pokud aplikaci nevidíte okamžitě, přejděte na Nastavení Účty Pracovní nebo Školní informace o vašem účtu a posuňte se dolů, abyste viděli informace o  >    >    >   stavu nainstalované aplikace.</span><span class="sxs-lookup"><span data-stu-id="40d46-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="40d46-126">Jak se dostat k aplikacím prostřednictvím Portál společnosti:</span><span class="sxs-lookup"><span data-stu-id="40d46-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="40d46-127">Otevřete **nabídku Start a** vyberte **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="40d46-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="40d46-128">Vyhledejte **Portál společnosti** a stáhněte si aplikaci.</span><span class="sxs-lookup"><span data-stu-id="40d46-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="40d46-129">Přihlaste se ke svému účtu.</span><span class="sxs-lookup"><span data-stu-id="40d46-129">Sign into your account.</span></span>
4. <span data-ttu-id="40d46-130">Vyberte aplikaci, kterou chcete obdržet, a stáhněte si ji.</span><span class="sxs-lookup"><span data-stu-id="40d46-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="40d46-131">Přečtěte si [další informace o automatické instalaci Portál společnosti](https://docs.microsoft.com/mem/intune/apps/company-portal-app) a nasazení a správě aplikací v [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="40d46-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
