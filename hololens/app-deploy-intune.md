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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635496"
---
# <a name="intune--company-portal"></a><span data-ttu-id="5cd29-104">Intune & Portál společnosti</span><span class="sxs-lookup"><span data-stu-id="5cd29-104">Intune & Company Portal</span></span>

<span data-ttu-id="5cd29-105">S Mobile Správa zařízení (MDM) můžete použít vlastní aplikace prostřednictvím [služby Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) a nasadit je přímo do vašich HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="5cd29-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="5cd29-106">Microsoft Intune je cloudová služba, která se zaměřuje na správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM).</span><span class="sxs-lookup"><span data-stu-id="5cd29-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="5cd29-107">Intune je součástí sady [Microsoftu Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)a umožňuje uživatelům být produktivní a současně chránit data vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="5cd29-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="5cd29-108">Další informace o Intune najdete v co [je Intune.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="5cd29-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="5cd29-109">Nastavení</span><span class="sxs-lookup"><span data-stu-id="5cd29-109">Setup</span></span>

1. <span data-ttu-id="5cd29-110">Upload aplikaci do obchodního podniku nebo nahrát vlastní aplikaci do tenanta Intune.</span><span class="sxs-lookup"><span data-stu-id="5cd29-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="5cd29-111">Viz také: [Enterprise správy aplikací.](/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="5cd29-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="5cd29-112">[Přiřaďte aplikaci ke skupině](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="5cd29-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="5cd29-113">Na základě typu přiřazení, který zvolíte, můžete aplikaci doručit automaticky nebo ji můžete snadno načíst, pokud máte vybrané aplikace.</span><span class="sxs-lookup"><span data-stu-id="5cd29-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="5cd29-114">Při vytváření sady appx nezapomeňte zohlednit zahrnutí architektury pro zařízení, na která nasazujete.</span><span class="sxs-lookup"><span data-stu-id="5cd29-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="5cd29-115">HoloLens 2 je ARM64 a HoloLens (1. generace) je x86.</span><span class="sxs-lookup"><span data-stu-id="5cd29-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="5cd29-116">Pokud plánujete mít prostředí se smíšenými zařízeními, můžete obojí zahrnout do jedné sady appx.</span><span class="sxs-lookup"><span data-stu-id="5cd29-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="5cd29-117">Typy přiřazení</span><span class="sxs-lookup"><span data-stu-id="5cd29-117">Assignment types</span></span>

<span data-ttu-id="5cd29-118">Pokud chcete, aby se vaše aplikace po registraci  automaticky nainstalovala na zařízení, měli byste pro tuto skupinu nebo skupiny vybrat Povinné.</span><span class="sxs-lookup"><span data-stu-id="5cd29-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="5cd29-119">Pokud chcete aplikaci stáhnout do zařízení zaregistrovaná prostřednictvím portálu společnosti, vyberte **Dostupná pro zaregistrovaná zařízení.**</span><span class="sxs-lookup"><span data-stu-id="5cd29-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="5cd29-120">End-User prostředí</span><span class="sxs-lookup"><span data-stu-id="5cd29-120">End-User Experience</span></span>

<span data-ttu-id="5cd29-121">Po nastavení konfigurace v Intune jste připraveni koncovým uživatelům přijímat vybrané aplikace.</span><span class="sxs-lookup"><span data-stu-id="5cd29-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="5cd29-122">Pokud chcete automaticky získat aplikace, postupujte podle těchto kroků:</span><span class="sxs-lookup"><span data-stu-id="5cd29-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="5cd29-123">Zaregistrujte své zařízení v tenantovi.</span><span class="sxs-lookup"><span data-stu-id="5cd29-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="5cd29-124">Po dokončení registrace zařízení byste měli aplikaci obdržet na svém zařízení.</span><span class="sxs-lookup"><span data-stu-id="5cd29-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="5cd29-125">Pokud aplikaci nevidíte okamžitě, přejděte do části Nastavení Accounts Work or School your account Info **(Pracovní** nebo školní informace o účtu) a posuňte se dolů, kde se zobrazí informace o  >    >    >   stavu nainstalované aplikace.</span><span class="sxs-lookup"><span data-stu-id="5cd29-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="5cd29-126">Jak se dostat k aplikacím prostřednictvím Portál společnosti:</span><span class="sxs-lookup"><span data-stu-id="5cd29-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="5cd29-127">Otevřete **nabídku Start a** vyberte **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="5cd29-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="5cd29-128">Vyhledejte **Portál společnosti** a stáhněte si aplikaci.</span><span class="sxs-lookup"><span data-stu-id="5cd29-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="5cd29-129">Přihlaste se ke svému účtu.</span><span class="sxs-lookup"><span data-stu-id="5cd29-129">Sign into your account.</span></span>
4. <span data-ttu-id="5cd29-130">Vyberte aplikaci, kterou chcete obdržet, a stáhněte si ji.</span><span class="sxs-lookup"><span data-stu-id="5cd29-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="5cd29-131">Přečtěte si [další informace o automatické instalaci Portál společnosti](/mem/intune/apps/company-portal-app) a nasazení a správě aplikací v [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="5cd29-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
