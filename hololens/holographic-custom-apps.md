---
title: Správa vlastních aplikací pro HoloLens (1. generace)
description: Naučte se instalovat, odinstalovat a načítat vlastní holografické aplikace na zařízeníChoLens pomocí Portál zařízení a Visual Studio.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377587"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="458fb-104">Správa vlastních aplikací pro HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="458fb-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="458fb-105">HoloLens podporuje mnoho existujících aplikací z Microsoft Store a také nové aplikace vytvořené speciálně pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="458fb-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="458fb-106">Tento článek se zaměřuje na vlastní holografické aplikace.</span><span class="sxs-lookup"><span data-stu-id="458fb-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="458fb-107">Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="458fb-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="458fb-108">Následující informace byly vytvořeny pro HoloLens (1. generace), které se v tu dobu také nazývaly HoloLens Developer Edition.</span><span class="sxs-lookup"><span data-stu-id="458fb-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="458fb-109">Jako takové bylo běžné instalovat aplikace bokem přes portál zařízení a Visual Studio přes zařízení.</span><span class="sxs-lookup"><span data-stu-id="458fb-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="458fb-110">U podnikových nasazení nedoporučujeme povolovat vývojářský režim, který obě tyto metody používají.</span><span class="sxs-lookup"><span data-stu-id="458fb-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="458fb-111">Pokud vás zajímá metoda zabezpečeného nasazení aplikací, projděte si naši správu [aplikací: Přehled.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="458fb-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="458fb-112">Pokud hledáte některou z metod instalace aplikací pro zařízení HoloLens 2 pro vývojáře, projděte si:</span><span class="sxs-lookup"><span data-stu-id="458fb-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="458fb-113">Portál zařízení: Instalace aplikace</span><span class="sxs-lookup"><span data-stu-id="458fb-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="458fb-114">Použití Visual Studio k nasazení a ladění aplikací</span><span class="sxs-lookup"><span data-stu-id="458fb-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="458fb-115">Instalace vlastních aplikací</span><span class="sxs-lookup"><span data-stu-id="458fb-115">Install custom apps</span></span>

<span data-ttu-id="458fb-116">Vlastní aplikace můžete na HoloLens nainstalovat buď pomocí Portál zařízení, nebo nasazením aplikací z Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="458fb-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="458fb-117">Instalace balíčku aplikace pomocí Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="458fb-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="458fb-118">Navázání připojení [z Portál zařízení](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) k cílovému Zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="458fb-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="458fb-119">V levém navigačním panelu přejděte na **stránku** Aplikace.</span><span class="sxs-lookup"><span data-stu-id="458fb-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="458fb-120">V **části Balíček aplikace** přejděte k souboru .appx, který je přidružený k vaší aplikaci.</span><span class="sxs-lookup"><span data-stu-id="458fb-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="458fb-121">Nezapomeňte odkazovat na všechny přidružené soubory závislostí a certifikátů.</span><span class="sxs-lookup"><span data-stu-id="458fb-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="458fb-122">Vyberte **Přejít.**</span><span class="sxs-lookup"><span data-stu-id="458fb-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="458fb-123">![Instalace formuláře aplikace v Portál zařízení s Windows na Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="458fb-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="458fb-124">Nasazení z Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="458fb-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="458fb-125">Otevřete řešení pro Visual Studio aplikace (soubor .sln).</span><span class="sxs-lookup"><span data-stu-id="458fb-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="458fb-126">Otevřete vlastnosti **projektu**.</span><span class="sxs-lookup"><span data-stu-id="458fb-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="458fb-127">Vyberte následující konfiguraci sestavení: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="458fb-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="458fb-128">Když vyberete **Vzdálený počítač:**</span><span class="sxs-lookup"><span data-stu-id="458fb-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="458fb-129">Ujistěte se, že adresa odkazuje Wi-Fi IP adresu vaší společnosti HoloLens.</span><span class="sxs-lookup"><span data-stu-id="458fb-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="458fb-130">Nastavte ověřování **na Univerzální (nešifrovaný protokol).**</span><span class="sxs-lookup"><span data-stu-id="458fb-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="458fb-131">Sestavte své řešení.</span><span class="sxs-lookup"><span data-stu-id="458fb-131">Build your solution.</span></span>

1. <span data-ttu-id="458fb-132">Pokud chcete aplikaci nasadit z vývojového počítače do HoloLens, vyberte **Vzdálený počítač.**</span><span class="sxs-lookup"><span data-stu-id="458fb-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="458fb-133">Pokud už máte na HoloLens existující build, vyberte **Ano** a nainstalujte tuto novější verzi.</span><span class="sxs-lookup"><span data-stu-id="458fb-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Nasazení vzdáleného počítače pro aplikace Microsoft HoloLens v Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="458fb-135">Aplikace se na HoloLens nainstaluje a automaticky spustí.</span><span class="sxs-lookup"><span data-stu-id="458fb-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="458fb-136">Po instalaci aplikace ji najdete v seznamu Všechny aplikace  (**Start**  >  **Všechny aplikace**).</span><span class="sxs-lookup"><span data-stu-id="458fb-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
