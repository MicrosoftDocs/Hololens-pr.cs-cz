---
title: Jak na straně načíst a nainstalovat aplikace přes instalační program aplikace pro HoloLens 2
description: Naučte se instalovat a řešit potíže s aplikacemi pomocí instalačního programu aplikace a na straně zátěže a instalovat aplikace přes uživatelské rozhraní.
keywords: Správa aplikací, aplikace, HoloLens, instalační program aplikace
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924124"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="e1f29-104">Instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace</span><span class="sxs-lookup"><span data-stu-id="e1f29-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="e1f29-105">Tato funkce byla dostupná ve [Windows holografickém systému, verze 20H2 – prosinec 2020 Update](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="e1f29-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="e1f29-106">Ujistěte se, že je vaše zařízení [aktualizované](hololens-update-hololens.md) , aby tuto funkci používalo.</span><span class="sxs-lookup"><span data-stu-id="e1f29-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="e1f29-107">Přidali jsme **novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** .</span><span class="sxs-lookup"><span data-stu-id="e1f29-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="e1f29-108">Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**.</span><span class="sxs-lookup"><span data-stu-id="e1f29-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="e1f29-109">Aby nedošlo k narušení podniků, instalační program aplikace nebude v tuto chvíli **k dispozici pro spravovaná zařízení** .</span><span class="sxs-lookup"><span data-stu-id="e1f29-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="e1f29-110">Zařízení se považuje za spravované, pokud platí **některá** z následujících podmínek:</span><span class="sxs-lookup"><span data-stu-id="e1f29-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="e1f29-111">[Zaregistrované](hololens-enroll-mdm.md) MDM</span><span class="sxs-lookup"><span data-stu-id="e1f29-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="e1f29-112">Nakonfigurováno pomocí [zřizovacího balíčku](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e1f29-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="e1f29-113">[Identita](hololens-identity.md) uživatele je Azure AD</span><span class="sxs-lookup"><span data-stu-id="e1f29-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="e1f29-114">Nyní je možné instalovat aplikace bez nutnosti povolit vývojářský režim ani používat portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="e1f29-115">Stáhněte si do svého zařízení (přes USB nebo přes Microsoft Edge) sadu appx a přejděte do sady appx v Průzkumníkovi souborů, kde se zobrazí výzva k ukončení instalace.</span><span class="sxs-lookup"><span data-stu-id="e1f29-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="e1f29-116">Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="e1f29-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="e1f29-117">Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem pomocí možnosti nasazení aplikace LOB pro správu mobilních aplikací, musí být aplikace digitálně podepsané pomocí [nástroje Signer](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a [certifikát použitý k podepsání musí být](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) před nasazením aplikace důvěryhodný pro zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e1f29-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1f29-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e1f29-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="e1f29-119">Pro vaše zařízení:</span><span class="sxs-lookup"><span data-stu-id="e1f29-119">For your devices:</span></span>

<span data-ttu-id="e1f29-120">Tato funkce je aktuálně dostupná ve Windows holografické 20H2 buildech pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e1f29-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="e1f29-121">Zajistěte, aby všechna zařízení používající tuto metodu byla [aktualizovaná](hololens-update-hololens.md).</span><span class="sxs-lookup"><span data-stu-id="e1f29-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="e1f29-122">Pro vaše aplikace:</span><span class="sxs-lookup"><span data-stu-id="e1f29-122">For your apps:</span></span>

<span data-ttu-id="e1f29-123">Konfigurace řešení vaší aplikace musí být buď **Hlavní** , nebo **verze** , protože instalační program aplikace bude používat závislosti ze Storu.</span><span class="sxs-lookup"><span data-stu-id="e1f29-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="e1f29-124">Přečtěte si další informace o [vytváření balíčků aplikací](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="e1f29-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="e1f29-125">Aplikace, které jsou nainstalované přes tuto metodu, musí být digitálně podepsané.</span><span class="sxs-lookup"><span data-stu-id="e1f29-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="e1f29-126">K podepsání aplikace budete muset použít certifikát.</span><span class="sxs-lookup"><span data-stu-id="e1f29-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="e1f29-127">Můžete buď získat certifikát ze [seznamu důvěryhodných certifikačních autorit MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). v takovém případě nebudete muset provádět žádnou další akci.</span><span class="sxs-lookup"><span data-stu-id="e1f29-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="e1f29-128">Případně můžete podepsat vlastní certifikát, ale tento certifikát bude nutné do zařízení vložit.</span><span class="sxs-lookup"><span data-stu-id="e1f29-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="e1f29-129">Jak podepisovat aplikace [pomocí nástroje Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="e1f29-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="e1f29-130">**Možnosti certifikátu:**</span><span class="sxs-lookup"><span data-stu-id="e1f29-130">**Certificate options:**</span></span>

- [<span data-ttu-id="e1f29-131">Seznam důvěryhodných certifikačních autorit MS</span><span class="sxs-lookup"><span data-stu-id="e1f29-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="e1f29-132">**Vyberte metodu nasazení certifikátu.**</span><span class="sxs-lookup"><span data-stu-id="e1f29-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="e1f29-133">[Balíčky zřizování](hololens-provisioning.md) se dají použít na místní zařízení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="e1f29-134">MDM se dá použít k [aplikování certifikátů s konfiguracemi zařízení](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="e1f29-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="e1f29-135">Použijte [Správce certifikátů](certificate-manager.md)zařízení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="e1f29-136">Metoda instalace</span><span class="sxs-lookup"><span data-stu-id="e1f29-136">Installation method</span></span>

1. <span data-ttu-id="e1f29-137">Ověřte, že se zařízení nepovažuje za spravované.</span><span class="sxs-lookup"><span data-stu-id="e1f29-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="e1f29-138">Ověřte, že je zařízení HoloLens 2 zapnuté a že jste přihlášení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="e1f29-139">Na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage\Downloads..</span><span class="sxs-lookup"><span data-stu-id="e1f29-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="e1f29-140">Po dokončení kopírování souboru můžete zařízení odpojit a instalaci dokončit později.</span><span class="sxs-lookup"><span data-stu-id="e1f29-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="e1f29-141">V zařízení HoloLens 2 Otevřete **nabídku Start**, vyberte **všechny aplikace** a spusťte aplikaci **Průzkumník souborů** .</span><span class="sxs-lookup"><span data-stu-id="e1f29-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="e1f29-142">Přejděte do složky Stažené soubory.</span><span class="sxs-lookup"><span data-stu-id="e1f29-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="e1f29-143">Možná budete muset na levém panelu aplikace vybrat **Toto zařízení** jako první a pak přejít na soubory ke stažení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="e1f29-144">Vyberte soubor yourapp. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="e1f29-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="e1f29-145">Spustí se instalační program aplikace.</span><span class="sxs-lookup"><span data-stu-id="e1f29-145">The App Installer will launch.</span></span> <span data-ttu-id="e1f29-146">Vyberte tlačítko **nainstalovat** a nainstalujte svou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e1f29-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="e1f29-147">Nainstalovaná aplikace se automaticky spustí po dokončení instalace.</span><span class="sxs-lookup"><span data-stu-id="e1f29-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="e1f29-149">Řešení potíží s instalací</span><span class="sxs-lookup"><span data-stu-id="e1f29-149">Troubleshooting Installs</span></span>

<span data-ttu-id="e1f29-150">Pokud se aplikaci nepovedlo nainstalovat, Projděte si následující problémy:</span><span class="sxs-lookup"><span data-stu-id="e1f29-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="e1f29-151">Vaše aplikace je buď hlavní Build, nebo sestavení pro vydání.</span><span class="sxs-lookup"><span data-stu-id="e1f29-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="e1f29-152">Vaše zařízení je aktualizováno na sestavení, ve kterém je tato funkce k dispozici.</span><span class="sxs-lookup"><span data-stu-id="e1f29-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="e1f29-153">Jste [připojení k Internetu](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="e1f29-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="e1f29-154">Vaše [koncové body pro Microsoft Store](hololens-offline.md) jsou správně nakonfigurované.</span><span class="sxs-lookup"><span data-stu-id="e1f29-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="e1f29-155">Webový instalační program</span><span class="sxs-lookup"><span data-stu-id="e1f29-155">Web Installer</span></span>

<span data-ttu-id="e1f29-156">Uživatelé můžou aplikaci nainstalovat přímo z webového serveru.</span><span class="sxs-lookup"><span data-stu-id="e1f29-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="e1f29-157">Tento tok využívá instalační program aplikace v kombinaci s snadnou metodou stažení a instalace pro distribuci.</span><span class="sxs-lookup"><span data-stu-id="e1f29-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="e1f29-158">Jak nastavit webovou instalaci:</span><span class="sxs-lookup"><span data-stu-id="e1f29-158">How to set up web install:</span></span>

1. <span data-ttu-id="e1f29-159">Ujistěte se, že je aplikace správně nakonfigurovaná pro instalaci.</span><span class="sxs-lookup"><span data-stu-id="e1f29-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="e1f29-160">Pomocí těchto [kroků Povolte instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="e1f29-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="e1f29-161">Činnost koncového uživatele:</span><span class="sxs-lookup"><span data-stu-id="e1f29-161">End user experience:</span></span>

1. <span data-ttu-id="e1f29-162">Uživatel obdrží certifikát do zařízení a nainstaluje ho pomocí metody výše zvolené výše.</span><span class="sxs-lookup"><span data-stu-id="e1f29-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="e1f29-163">Uživatel navštíví adresu URL vytvořenou z výše uvedeného kroku.</span><span class="sxs-lookup"><span data-stu-id="e1f29-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="e1f29-164">Aplikace se teď nainstaluje do zařízení.</span><span class="sxs-lookup"><span data-stu-id="e1f29-164">The app will now install to the device.</span></span> <span data-ttu-id="e1f29-165">Pokud chcete aplikaci najít, otevřete **nabídku Start** a vyberte tlačítko **všechny aplikace** a vyhledejte svou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e1f29-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="e1f29-166">Další pomoc při řešení potíží s metodou instalace instalačního programu aplikace najdete v tématu [řešení potíží s instalačním programem aplikace](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span><span class="sxs-lookup"><span data-stu-id="e1f29-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="e1f29-167">Uživatelské rozhraní není během procesu aktualizace podporováno.</span><span class="sxs-lookup"><span data-stu-id="e1f29-167">UI during the update process is not supported.</span></span> <span data-ttu-id="e1f29-168">Proto není možnost ShowPrompt na [této stránce](https://docs.microsoft.com/windows/msix/app-installer/update-settings) a související možnosti podporována.</span><span class="sxs-lookup"><span data-stu-id="e1f29-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="e1f29-169">Ukázkové aplikace</span><span class="sxs-lookup"><span data-stu-id="e1f29-169">Sample Apps</span></span>

<span data-ttu-id="e1f29-170">Vyzkoušejte si instalační program aplikace s některou z našich dostupných ukázkových aplikací.</span><span class="sxs-lookup"><span data-stu-id="e1f29-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="e1f29-171">Ukázkové aplikace</span><span class="sxs-lookup"><span data-stu-id="e1f29-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
