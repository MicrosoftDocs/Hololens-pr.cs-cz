---
title: Boční načtení a instalace aplikací přes HoloLens 2 Instalační program aplikací
description: Naučte se instalovat a řešit potíže s aplikacemi pomocí instalačního programu aplikací a instalace aplikací bokem a pomocí uživatelského rozhraní.
keywords: app management, app, hololens, app installer
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377577"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="42492-104">Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací</span><span class="sxs-lookup"><span data-stu-id="42492-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="42492-105">Tato funkce byla dostupná ve [Windows Holographic verze 20H2 –prosinec 2020 Update.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="42492-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="42492-106">Ujistěte se, že je [zařízení aktualizované](hololens-update-hololens.md) tak, aby tuto funkci bylo možné používat.</span><span class="sxs-lookup"><span data-stu-id="42492-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="42492-107">Přidali **jsme novou funkci (Instalační program aplikací),** která umožňuje hladce instalovat aplikace na zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42492-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="42492-108">Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.**</span><span class="sxs-lookup"><span data-stu-id="42492-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="42492-109">Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.</span><span class="sxs-lookup"><span data-stu-id="42492-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="42492-110">Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:</span><span class="sxs-lookup"><span data-stu-id="42492-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="42492-111">Zaregistrované [](hololens-enroll-mdm.md) MDM</span><span class="sxs-lookup"><span data-stu-id="42492-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="42492-112">Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="42492-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="42492-113">Identita [uživatele](hololens-identity.md) je Azure AD</span><span class="sxs-lookup"><span data-stu-id="42492-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="42492-114">Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="42492-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="42492-115">Stáhněte si do zařízení (přes USB nebo přes Microsoft Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.</span><span class="sxs-lookup"><span data-stu-id="42492-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="42492-116">Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="42492-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="42492-117">Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) aplikace MDM, musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens důvěryhodný, aby bylo možné aplikaci nasadit. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)</span><span class="sxs-lookup"><span data-stu-id="42492-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="42492-118">Požadavky</span><span class="sxs-lookup"><span data-stu-id="42492-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="42492-119">Pro vaše zařízení:</span><span class="sxs-lookup"><span data-stu-id="42492-119">For your devices:</span></span>

<span data-ttu-id="42492-120">Tato funkce je aktuálně dostupná v buildech Windows Holographic 20H2 pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42492-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="42492-121">Ujistěte se, že jsou aktualizovaná všechna zařízení používající tuto [metodu.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="42492-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="42492-122">Pro vaše aplikace:</span><span class="sxs-lookup"><span data-stu-id="42492-122">For your apps:</span></span>

<span data-ttu-id="42492-123">Konfigurace řešení vaší aplikace musí  být  buď hlavní, nebo vy vydání, protože Instalační program aplikací bude používat závislosti z obchodu.</span><span class="sxs-lookup"><span data-stu-id="42492-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="42492-124">Další informace o [vytváření balíčků aplikací najdete v tématu](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="42492-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="42492-125">Aplikace nainstalované touto metodou musí být digitálně podepsané.</span><span class="sxs-lookup"><span data-stu-id="42492-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="42492-126">K podepsání aplikace budete muset použít certifikát.</span><span class="sxs-lookup"><span data-stu-id="42492-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="42492-127">Můžete buď získat certifikát ze seznamu důvěryhodných certifikačních autority [ms,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)v takovém případě nebudete muset provést žádnou další akci.</span><span class="sxs-lookup"><span data-stu-id="42492-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="42492-128">Nebo můžete podepsat vlastní certifikát, ale tento certifikát se bude muset do zařízení nasučit.</span><span class="sxs-lookup"><span data-stu-id="42492-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="42492-129">Jak podepisovat [aplikace pomocí nástroje pro podpis](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="42492-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="42492-130">**Možnosti certifikátu:**</span><span class="sxs-lookup"><span data-stu-id="42492-130">**Certificate options:**</span></span>

- [<span data-ttu-id="42492-131">Seznam důvěryhodných certifikačních autorit ms</span><span class="sxs-lookup"><span data-stu-id="42492-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="42492-132">**Vyberte metodu nasazení certifikátu.**</span><span class="sxs-lookup"><span data-stu-id="42492-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="42492-133">[Zřizovací balíčky](hololens-provisioning.md) je možné použít na místní zařízení.</span><span class="sxs-lookup"><span data-stu-id="42492-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="42492-134">MDM lze použít k [použití certifikátů s konfiguracemi zařízení.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="42492-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="42492-135">Použijte ve Správci [certifikátů zařízení](certificate-manager.md).</span><span class="sxs-lookup"><span data-stu-id="42492-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="42492-136">Metoda instalace</span><span class="sxs-lookup"><span data-stu-id="42492-136">Installation method</span></span>

1. <span data-ttu-id="42492-137">Zkontrolujte, že se vaše zařízení nepovažuje za spravované.</span><span class="sxs-lookup"><span data-stu-id="42492-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="42492-138">Zkontrolujte, že je zařízení HoloLens 2 zapnuté a že jste přihlášeni.</span><span class="sxs-lookup"><span data-stu-id="42492-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="42492-139">Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní úložiště\Soubory ke stažení.</span><span class="sxs-lookup"><span data-stu-id="42492-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="42492-140">Po zkopírování souboru můžete zařízení odpojit a instalaci dokončit později.</span><span class="sxs-lookup"><span data-stu-id="42492-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="42492-141">Na zařízení HoloLens 2 otevřete **nabídku Start,** vyberte **Všechny aplikace** a spusťte **Průzkumník souborů** aplikaci.</span><span class="sxs-lookup"><span data-stu-id="42492-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="42492-142">Přejděte do složky Stažené soubory.</span><span class="sxs-lookup"><span data-stu-id="42492-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="42492-143">Možná budete muset na levém panelu aplikace nejprve vybrat **Toto zařízení** a pak přejít na Položky ke stažení.</span><span class="sxs-lookup"><span data-stu-id="42492-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="42492-144">Vyberte soubor yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="42492-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="42492-145">Spustí Instalační program aplikací.</span><span class="sxs-lookup"><span data-stu-id="42492-145">The App Installer will launch.</span></span> <span data-ttu-id="42492-146">Vyberte **tlačítko Install** (Nainstalovat) a nainstalujte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="42492-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="42492-147">Nainstalovaná aplikace se automaticky spustí po dokončení instalace.</span><span class="sxs-lookup"><span data-stu-id="42492-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="42492-149">Řešení potíží s instalacemi</span><span class="sxs-lookup"><span data-stu-id="42492-149">Troubleshooting Installs</span></span>

<span data-ttu-id="42492-150">Pokud se vaší aplikaci nepodařilo nainstalovat, při řešení potíží zkontrolujte následující:</span><span class="sxs-lookup"><span data-stu-id="42492-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="42492-151">Vaše aplikace je buď sestavení hlavní verze, nebo sestavení verze.</span><span class="sxs-lookup"><span data-stu-id="42492-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="42492-152">Vaše zařízení se aktualizuje na sestavení, na kterém je tato funkce dostupná.</span><span class="sxs-lookup"><span data-stu-id="42492-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="42492-153">Jste [připojení k internetu.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="42492-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="42492-154">Vaše [koncové body pro Microsoft Store](hololens-offline.md) jsou správně nakonfigurované.</span><span class="sxs-lookup"><span data-stu-id="42492-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="42492-155">Webový instalační program</span><span class="sxs-lookup"><span data-stu-id="42492-155">Web Installer</span></span>

<span data-ttu-id="42492-156">Uživatelé instalují aplikaci přímo z webového serveru.</span><span class="sxs-lookup"><span data-stu-id="42492-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="42492-157">Tento tok využívá metodu Instalační program aplikací v kombinaci se snadnou metodou distribuce stahování a instalace.</span><span class="sxs-lookup"><span data-stu-id="42492-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="42492-158">Jak nastavit webovou instalaci:</span><span class="sxs-lookup"><span data-stu-id="42492-158">How to set up web install:</span></span>

1. <span data-ttu-id="42492-159">Ujistěte se, že je aplikace správně nakonfigurovaná k instalaci.</span><span class="sxs-lookup"><span data-stu-id="42492-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="42492-160">Pokud chcete [povolit instalaci z webové stránky, postupujte podle těchto kroků.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="42492-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="42492-161">Prostředí koncového uživatele:</span><span class="sxs-lookup"><span data-stu-id="42492-161">End user experience:</span></span>

1. <span data-ttu-id="42492-162">Uživatel obdrží a nainstaluje certifikát do zařízení pomocí metody dříve zvolené výše.</span><span class="sxs-lookup"><span data-stu-id="42492-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="42492-163">Uživatel navštíví adresu URL vytvořenou v kroku výše.</span><span class="sxs-lookup"><span data-stu-id="42492-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="42492-164">Aplikace se teď nainstaluje do zařízení.</span><span class="sxs-lookup"><span data-stu-id="42492-164">The app will now install to the device.</span></span> <span data-ttu-id="42492-165">Aplikaci najdete tak, že otevřete **nabídka Start** a výběrem tlačítka **Všechny aplikace** aplikaci najdete.</span><span class="sxs-lookup"><span data-stu-id="42492-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="42492-166">Další pomoc s řešením potíží s metodou instalace instalačního programu aplikace najdete v tématu Řešení [potíží s instalačním programem aplikací.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="42492-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="42492-167">Uživatelské rozhraní během procesu aktualizace se nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="42492-167">UI during the update process is not supported.</span></span> <span data-ttu-id="42492-168">Možnost ShowPrompt na [této stránce](https://docs.microsoft.com/windows/msix/app-installer/update-settings) a související možnosti se proto nepodporují.</span><span class="sxs-lookup"><span data-stu-id="42492-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="42492-169">Ukázkové aplikace</span><span class="sxs-lookup"><span data-stu-id="42492-169">Sample Apps</span></span>

<span data-ttu-id="42492-170">Pokud si chcete Instalační program aplikací ukázkové aplikace, podívejte se na některé z našich dostupných ukázek:</span><span class="sxs-lookup"><span data-stu-id="42492-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="42492-171">MRTK Examples Hub</span><span class="sxs-lookup"><span data-stu-id="42492-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="42492-172">Povrchy</span><span class="sxs-lookup"><span data-stu-id="42492-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="42492-173">Ukázkové aplikace pro UPW, které je možné použít k testování</span><span class="sxs-lookup"><span data-stu-id="42492-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
