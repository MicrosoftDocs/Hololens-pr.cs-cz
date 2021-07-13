---
title: Správa vlastních aplikací pro HoloLens (1. generace)
description: Naučte se instalovat, odinstalovat a načítat vlastní holografické aplikace na HoloLens zařízení pomocí Portál zařízení a Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635904"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="db7d3-104">Správa vlastních aplikací pro HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="db7d3-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="db7d3-105">HoloLens podporuje mnoho existujících aplikací z Microsoft Store a také nové aplikace vytvořené speciálně pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="db7d3-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="db7d3-106">Tento článek se zaměřuje na vlastní holografické aplikace.</span><span class="sxs-lookup"><span data-stu-id="db7d3-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="db7d3-107">Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="db7d3-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db7d3-108">Následující informace byly vytvořeny pro HoloLens (1. generace) také nazývané HoloLens Developer Edition.</span><span class="sxs-lookup"><span data-stu-id="db7d3-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="db7d3-109">Jako takové bylo běžné instalovat aplikace bokem přes portál zařízení a Visual Studio přes zařízení.</span><span class="sxs-lookup"><span data-stu-id="db7d3-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="db7d3-110">U podnikových nasazení nedoporučujeme povolovat vývojářský režim, který obě tyto metody používají.</span><span class="sxs-lookup"><span data-stu-id="db7d3-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="db7d3-111">Pokud vás zajímá metoda zabezpečeného nasazení aplikací, projděte si naši správu [aplikací: Přehled.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="db7d3-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="db7d3-112">Pokud hledáte některou z metod instalace aplikací pro vývojáře HoloLens 2, přečtěte si:</span><span class="sxs-lookup"><span data-stu-id="db7d3-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="db7d3-113">Portál zařízení: Instalace aplikace</span><span class="sxs-lookup"><span data-stu-id="db7d3-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="db7d3-114">Použití Visual Studio k nasazení a ladění aplikací</span><span class="sxs-lookup"><span data-stu-id="db7d3-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="db7d3-115">Instalace vlastních aplikací</span><span class="sxs-lookup"><span data-stu-id="db7d3-115">Install custom apps</span></span>

<span data-ttu-id="db7d3-116">Vlastní aplikace můžete na HoloLens nainstalovat buď pomocí Portál zařízení, nebo nasazením aplikací z Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db7d3-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="db7d3-117">Instalace balíčku aplikace pomocí Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="db7d3-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="db7d3-118">Navázání připojení [z Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal) k cílovému HoloLens.</span><span class="sxs-lookup"><span data-stu-id="db7d3-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="db7d3-119">V levém navigačním panelu přejděte na **stránku** Aplikace.</span><span class="sxs-lookup"><span data-stu-id="db7d3-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="db7d3-120">V **části Balíček aplikace** přejděte k souboru .appx, který je přidružený k vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="db7d3-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="db7d3-121">Nezapomeňte odkazovat na všechny přidružené soubory závislostí a certifikátů.</span><span class="sxs-lookup"><span data-stu-id="db7d3-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="db7d3-122">Vyberte **Přejít.**</span><span class="sxs-lookup"><span data-stu-id="db7d3-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="db7d3-123">![Instalace formuláře aplikace v Windows Portál zařízení na Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="db7d3-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="db7d3-124">Nasazení z Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="db7d3-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="db7d3-125">Otevřete řešení pro Visual Studio aplikace (soubor .sln).</span><span class="sxs-lookup"><span data-stu-id="db7d3-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="db7d3-126">Otevřete vlastnosti **projektu**.</span><span class="sxs-lookup"><span data-stu-id="db7d3-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="db7d3-127">Vyberte následující konfiguraci sestavení: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="db7d3-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="db7d3-128">Když vyberete **Vzdálený počítač:**</span><span class="sxs-lookup"><span data-stu-id="db7d3-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="db7d3-129">Ujistěte se, že adresa odkazuje na Wi-Fi IP adresu vašeho HoloLens.</span><span class="sxs-lookup"><span data-stu-id="db7d3-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="db7d3-130">Nastavte ověřování **na Univerzální (nešifrovaný protokol).**</span><span class="sxs-lookup"><span data-stu-id="db7d3-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="db7d3-131">Sestavte své řešení.</span><span class="sxs-lookup"><span data-stu-id="db7d3-131">Build your solution.</span></span>

1. <span data-ttu-id="db7d3-132">Pokud chcete nasadit aplikaci z vývojového počítače do HoloLens vyberte **Vzdálený počítač**.</span><span class="sxs-lookup"><span data-stu-id="db7d3-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="db7d3-133">Pokud již máte existující sestavení na HoloLens, vyberte **Ano** a nainstalujte tuto novější verzi.</span><span class="sxs-lookup"><span data-stu-id="db7d3-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Nasazení vzdáleného počítače pro aplikace Microsoft HoloLens v Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="db7d3-135">Aplikace se na váš počítač nainstaluje a automaticky HoloLens.</span><span class="sxs-lookup"><span data-stu-id="db7d3-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="db7d3-136">Po instalaci aplikace ji najdete v seznamu Všechny aplikace  (**Start**  >  **Všechny aplikace**).</span><span class="sxs-lookup"><span data-stu-id="db7d3-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
