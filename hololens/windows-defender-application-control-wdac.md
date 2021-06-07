---
title: Windows Defender řízení aplikací – WDAC
description: Přehled toho, Windows Defender řízení aplikací je a jak ho používat ke správě zařízení hybridní reality HoloLens
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377611"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="bc05e-103">Windows Defender řízení aplikací – WDAC</span><span class="sxs-lookup"><span data-stu-id="bc05e-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="bc05e-104">WdAC umožňuje správci IT nakonfigurovat svá zařízení tak, aby blokují spouštění aplikací na zařízeních.</span><span class="sxs-lookup"><span data-stu-id="bc05e-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="bc05e-105">To se liší od metod omezení zařízení, jako je třeba režim veřejného terminála, kde se uživateli zobrazí uživatelské rozhraní, které skryje aplikace v zařízení, ale přesto je možné je spustit.</span><span class="sxs-lookup"><span data-stu-id="bc05e-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="bc05e-106">I když je nástroj WDAC implementován, aplikace se stále zobrazí v seznamu Všechny aplikace, ale nástroj WDAC zastaví spuštění těchto aplikací a procesů uživatelem zařízení.</span><span class="sxs-lookup"><span data-stu-id="bc05e-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="bc05e-107">Zařízení může mít přiřazeno více než jednu zásadu WDAC.</span><span class="sxs-lookup"><span data-stu-id="bc05e-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="bc05e-108">Pokud je v systému nastaveno více zásad WDAC, projeví se většina omezujících zásad.</span><span class="sxs-lookup"><span data-stu-id="bc05e-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="bc05e-109">Když se koncoví uživatelé pokusí spustit aplikaci, která je blokovaná wdac, na HoloLens neobdrží oznámení o tom, že ji není možné spustit.</span><span class="sxs-lookup"><span data-stu-id="bc05e-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="bc05e-110">Následuje průvodce, který uživatelům pomůže naučit se používat funkce WDAC a Windows PowerShell k povolení nebo blokování aplikací na [zařízeních HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)s Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="bc05e-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="bc05e-111">Když uživatelé vyhledájí aplikace nainstalované na svém počítači Windows 10 počítači pomocí prvního příkladu, možná budou muset provést několik pokusů o zúžení výsledků.</span><span class="sxs-lookup"><span data-stu-id="bc05e-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="bc05e-112">Pokud nevíte úplný název balíčku, možná budete muset několikrát spustit příkaz Get-AppxPackage -name \* YourBestGuess, abyste ho \* našli.</span><span class="sxs-lookup"><span data-stu-id="bc05e-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="bc05e-113">Jakmile budete mít název, spusťte $package 1 = Get-AppxPackage -name Actual.PackageName.</span><span class="sxs-lookup"><span data-stu-id="bc05e-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="bc05e-114">Například spuštění následujícího kódu pro Microsoft Edge vrátí více než jeden výsledek, ale v tomto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="bc05e-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="bc05e-115">Názvy rodin balíčků pro aplikace na HoloLens</span><span class="sxs-lookup"><span data-stu-id="bc05e-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="bc05e-116">V průvodci propojeném výše můžete ručně upravit newPolicy.xml a přidat pravidla pro aplikace, které jsou nainstalované jenom na HoloLens s názvy jejich skupin balíčků.</span><span class="sxs-lookup"><span data-stu-id="bc05e-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="bc05e-117">Někdy můžete použít aplikace, které nejsou na vašem stolním počítači a které chcete přidat do zásad.</span><span class="sxs-lookup"><span data-stu-id="bc05e-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="bc05e-118">Tady je seznam běžně používaných a In-Box pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bc05e-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="bc05e-119">Název aplikace</span><span class="sxs-lookup"><span data-stu-id="bc05e-119">App Name</span></span>                   | <span data-ttu-id="bc05e-120">Název rodiny balíčků</span><span class="sxs-lookup"><span data-stu-id="bc05e-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="bc05e-121">3D prohlížeč</span><span class="sxs-lookup"><span data-stu-id="bc05e-121">3D Viewer</span></span>                  | <span data-ttu-id="bc05e-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="bc05e-123">Instalační program aplikací</span><span class="sxs-lookup"><span data-stu-id="bc05e-123">App Installer</span></span>              | <span data-ttu-id="bc05e-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bc05e-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="bc05e-125">Kalendář</span><span class="sxs-lookup"><span data-stu-id="bc05e-125">Calendar</span></span>                   | <span data-ttu-id="bc05e-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="bc05e-127">Camera</span><span class="sxs-lookup"><span data-stu-id="bc05e-127">Camera</span></span>                     | <span data-ttu-id="bc05e-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bc05e-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="bc05e-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="bc05e-129">Cortana</span></span>                    | <span data-ttu-id="bc05e-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="bc05e-131">Průvodci Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bc05e-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="bc05e-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="bc05e-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bc05e-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="bc05e-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="bc05e-135">Centrum Feedback</span><span class="sxs-lookup"><span data-stu-id="bc05e-135">Feedback Hub</span></span>               | <span data-ttu-id="bc05e-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="bc05e-137">Průzkumník souborů</span><span class="sxs-lookup"><span data-stu-id="bc05e-137">File Explorer</span></span>              | <span data-ttu-id="bc05e-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bc05e-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="bc05e-139">Poštovní</span><span class="sxs-lookup"><span data-stu-id="bc05e-139">Mail</span></span>                       | <span data-ttu-id="bc05e-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="bc05e-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bc05e-141">Microsoft Store</span></span>            | <span data-ttu-id="bc05e-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="bc05e-143">Movies & TV</span><span class="sxs-lookup"><span data-stu-id="bc05e-143">Movies & TV</span></span>                | <span data-ttu-id="bc05e-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="bc05e-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bc05e-145">OneDrive</span></span>                   | <span data-ttu-id="bc05e-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="bc05e-147">Fotky</span><span class="sxs-lookup"><span data-stu-id="bc05e-147">Photos</span></span>                     | <span data-ttu-id="bc05e-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="bc05e-149">Nastavení</span><span class="sxs-lookup"><span data-stu-id="bc05e-149">Settings</span></span>                   | <span data-ttu-id="bc05e-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bc05e-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="bc05e-151">Tipy</span><span class="sxs-lookup"><span data-stu-id="bc05e-151">Tips</span></span>                       | <span data-ttu-id="bc05e-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bc05e-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="bc05e-153">1 – Blokování Instalační program aplikací zablokuje jenom aplikaci Instalační program aplikací, a ne aplikace nainstalované z jiných zdrojů, jako je Microsoft Store nebo z vašeho řešení MDM.</span><span class="sxs-lookup"><span data-stu-id="bc05e-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="bc05e-154">Jak najít rodinu balíčků</span><span class="sxs-lookup"><span data-stu-id="bc05e-154">How to find a Package Family Name</span></span>

<span data-ttu-id="bc05e-155">Pokud aplikace není v tomto seznamu, může uživatel použít Portál zařízení připojený k HoloLens 2, který má nainstalovanou aplikaci, kterou chcete blokovat, k určení PackageRelativeID a odtud získat PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="bc05e-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="bc05e-156">Nainstalujte aplikaci na zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bc05e-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="bc05e-157">Otevřete Nastavení -> Aktualizace & Zabezpečení -> Pro vývojáře a povolte Vývojářský **režim** a potom **Portál zařízení.**</span><span class="sxs-lookup"><span data-stu-id="bc05e-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="bc05e-158">Další podrobnosti najdete v tématu další informace o [nastavení a používání portálu zařízení.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bc05e-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="bc05e-159">Po Portál zařízení připojení přejděte na **Zobrazení a** pak na **Aplikace.**</span><span class="sxs-lookup"><span data-stu-id="bc05e-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="bc05e-160">Na panelu Nainstalované aplikace vyberte pomocí rozevíracího seznamu nainstalovanou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="bc05e-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="bc05e-161">Vyhledejte PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="bc05e-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="bc05e-162">Zkopírujte znaky aplikace před znakem !, tyto znaky budou vaše PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="bc05e-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


