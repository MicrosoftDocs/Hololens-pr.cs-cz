---
title: Windows Defender Řízení aplikací – WDAC
description: přehled o tom, co Windows Defender Application Control je a jak ho používat ke správě HoloLens zařízení se smíšeným realitou.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639926"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="e8a75-103">Windows Defender Řízení aplikací – WDAC</span><span class="sxs-lookup"><span data-stu-id="e8a75-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="e8a75-104">WDAC umožňuje správci IT nakonfigurovat zařízení tak, aby blokovala spuštění aplikací na zařízeních.</span><span class="sxs-lookup"><span data-stu-id="e8a75-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="e8a75-105">To se liší od metod omezení zařízení, jako je celoobrazovkový režim, kde se uživatel zobrazuje s uživatelským ROZHRANÍm, které skrývá aplikace na zařízení, ale je možné ho přesto spustit.</span><span class="sxs-lookup"><span data-stu-id="e8a75-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="e8a75-106">I když je implementováno WDAC, aplikace jsou stále viditelné v seznamu všechny aplikace, ale WDAC zastaví aplikace a procesy, aby je mohli spustit uživatel zařízení.</span><span class="sxs-lookup"><span data-stu-id="e8a75-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="e8a75-107">Zařízení může mít přiřazeno více než jednu zásadu WDAC.</span><span class="sxs-lookup"><span data-stu-id="e8a75-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="e8a75-108">Pokud je v systému nastaveno více zásad WDAC, většina omezujících se projeví.</span><span class="sxs-lookup"><span data-stu-id="e8a75-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="e8a75-109">když se koncoví uživatelé pokusí spustit aplikaci, která je blokovaná službou WDAC HoloLens, neobdrží oznámení o tom, že tuto aplikaci nepůjde spustit.</span><span class="sxs-lookup"><span data-stu-id="e8a75-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="e8a75-110">následuje průvodce pro uživatele, kteří se naučí [používat WDAC a Windows PowerShell k povolení nebo blokování aplikací na zařízeních HoloLens 2 s Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="e8a75-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="e8a75-111">když uživatelé hledají aplikace nainstalované na svém Windows 10 počítači pomocí prvního ukázkového kroku, může být potřeba provést několik pokusů o zúžení výsledků.</span><span class="sxs-lookup"><span data-stu-id="e8a75-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="e8a75-112">Pokud neznáte úplný název balíčku, možná několikrát spustíte rutinu Get-AppxPackage-name \* YourBestGuess \* .</span><span class="sxs-lookup"><span data-stu-id="e8a75-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="e8a75-113">Po zadání názvu spusťte ' $package 1 = Get-AppxPackage-Name skutečnost. název balíčku '</span><span class="sxs-lookup"><span data-stu-id="e8a75-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="e8a75-114">například když Microsoft Edge spustíte následující příkaz, vrátí se více výsledků, ale z tohoto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="e8a75-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="e8a75-115">Názvy rodin balíčků pro aplikace v HoloLens</span><span class="sxs-lookup"><span data-stu-id="e8a75-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="e8a75-116">v průvodci výše můžete ručně upravit newPolicy.xml a přidat pravidla pro aplikace, které jsou nainstalovány pouze v HoloLens s názvy jejich rodin balíčků.</span><span class="sxs-lookup"><span data-stu-id="e8a75-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="e8a75-117">Někdy existují aplikace, které můžete použít k použití, které nejsou na stolním počítači, které chcete přidat do zásad.</span><span class="sxs-lookup"><span data-stu-id="e8a75-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="e8a75-118">tady je seznam běžně používaných a In-Box aplikací pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e8a75-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="e8a75-119">Název aplikace</span><span class="sxs-lookup"><span data-stu-id="e8a75-119">App Name</span></span>                   | <span data-ttu-id="e8a75-120">Název rodiny balíčků</span><span class="sxs-lookup"><span data-stu-id="e8a75-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="e8a75-121">Prohlížeč 3D</span><span class="sxs-lookup"><span data-stu-id="e8a75-121">3D Viewer</span></span>                  | <span data-ttu-id="e8a75-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e8a75-123">Instalační program aplikace</span><span class="sxs-lookup"><span data-stu-id="e8a75-123">App Installer</span></span>              | <span data-ttu-id="e8a75-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e8a75-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="e8a75-125">Kalendář</span><span class="sxs-lookup"><span data-stu-id="e8a75-125">Calendar</span></span>                   | <span data-ttu-id="e8a75-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e8a75-127">Camera</span><span class="sxs-lookup"><span data-stu-id="e8a75-127">Camera</span></span>                     | <span data-ttu-id="e8a75-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e8a75-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="e8a75-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="e8a75-129">Cortana</span></span>                    | <span data-ttu-id="e8a75-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="e8a75-131">Příručky k Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e8a75-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="e8a75-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e8a75-133">Vzdálená pomoc pro Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e8a75-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="e8a75-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="e8a75-135">Centrum Feedback</span><span class="sxs-lookup"><span data-stu-id="e8a75-135">Feedback Hub</span></span>               | <span data-ttu-id="e8a75-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="e8a75-137">Průzkumník souborů</span><span class="sxs-lookup"><span data-stu-id="e8a75-137">File Explorer</span></span>              | <span data-ttu-id="e8a75-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e8a75-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="e8a75-139">Poštovní</span><span class="sxs-lookup"><span data-stu-id="e8a75-139">Mail</span></span>                       | <span data-ttu-id="e8a75-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="e8a75-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e8a75-141">Microsoft Store</span></span>            | <span data-ttu-id="e8a75-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="e8a75-143">Filmy & televizor</span><span class="sxs-lookup"><span data-stu-id="e8a75-143">Movies & TV</span></span>                | <span data-ttu-id="e8a75-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="e8a75-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="e8a75-145">OneDrive</span></span>                   | <span data-ttu-id="e8a75-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="e8a75-147">Fotky</span><span class="sxs-lookup"><span data-stu-id="e8a75-147">Photos</span></span>                     | <span data-ttu-id="e8a75-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="e8a75-149">Nastavení</span><span class="sxs-lookup"><span data-stu-id="e8a75-149">Settings</span></span>                   | <span data-ttu-id="e8a75-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="e8a75-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="e8a75-151">Tipy</span><span class="sxs-lookup"><span data-stu-id="e8a75-151">Tips</span></span>                       | <span data-ttu-id="e8a75-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="e8a75-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="e8a75-153">1. blokování instalačního programu aplikace zablokuje jenom aplikaci instalátor aplikace a ne aplikace nainstalované z jiných zdrojů, jako je Microsoft Store nebo z řešení MDM.</span><span class="sxs-lookup"><span data-stu-id="e8a75-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="e8a75-154">Jak najít název řady balíčků</span><span class="sxs-lookup"><span data-stu-id="e8a75-154">How to find a Package Family Name</span></span>

<span data-ttu-id="e8a75-155">pokud aplikace není na tomto seznamu, pak uživatel může použít portál zařízení, který je připojený k HoloLens 2, která má nainstalovanou aplikaci, kterou chcete zablokovat, abyste zjistili, jak PackageRelativeID, tak PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="e8a75-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="e8a75-156">nainstalujte aplikaci na zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e8a75-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="e8a75-157">otevřete Nastavení-> aktualizace & zabezpečení > pro vývojáře a povolte **vývojářský režim** a potom **portál zařízení**.</span><span class="sxs-lookup"><span data-stu-id="e8a75-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="e8a75-158">Další podrobnosti najdete [v tématu o nastavení a používání portálu pro zařízení tady](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="e8a75-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="e8a75-159">Jakmile je portál zařízení připojený, přejděte do **zobrazení** a pak na **aplikace**.</span><span class="sxs-lookup"><span data-stu-id="e8a75-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="e8a75-160">V panelu nainstalované aplikace vyberte pomocí rozevírací nabídky nainstalovanou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e8a75-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="e8a75-161">Vyhledejte PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="e8a75-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="e8a75-162">Kopírovat znaky aplikace před!. tyto znaky budou vaší PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="e8a75-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


