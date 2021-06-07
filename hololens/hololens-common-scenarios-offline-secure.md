---
title: Běžné scénáře – HoloLens 2 v režimu offline
description: Zjistěte, jak nastavit scénář offline zabezpečeného nasazení a nasazení aplikací se zřizováním pro zařízení HoloLens.
keywords: HoloLens, správa, offline, offline zabezpečení
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377539"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="a9b55-104">Běžné scénáře – HoloLens 2 v režimu offline</span><span class="sxs-lookup"><span data-stu-id="a9b55-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="a9b55-105">Přehled</span><span class="sxs-lookup"><span data-stu-id="a9b55-105">Overview</span></span>

<span data-ttu-id="a9b55-106">Tato příručka obsahuje pokyny pro použití ukázkového zřizovacího balíčku, který uzamkne HoloLens 2 pro použití v zabezpečených prostředích s následujícími omezeními:</span><span class="sxs-lookup"><span data-stu-id="a9b55-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="a9b55-107">Zakažte WiFi.</span><span class="sxs-lookup"><span data-stu-id="a9b55-107">Disable WiFi.</span></span>
-   <span data-ttu-id="a9b55-108">Zakažte BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="a9b55-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="a9b55-109">Zakažte Mikrofony.</span><span class="sxs-lookup"><span data-stu-id="a9b55-109">Disable Microphones.</span></span>
-   <span data-ttu-id="a9b55-110">Zabraňuje přidávání nebo odebírání zřizovacích balíčků.</span><span class="sxs-lookup"><span data-stu-id="a9b55-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="a9b55-111">Žádný uživatel nemůže povolit žádnou z výše uvedených omezených komponent.</span><span class="sxs-lookup"><span data-stu-id="a9b55-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="a9b55-112">[![Scénář zabezpečení offline ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a9b55-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="a9b55-113">Příprava</span><span class="sxs-lookup"><span data-stu-id="a9b55-113">Prepare</span></span>

<span data-ttu-id="a9b55-114">Windows 10 počítače</span><span class="sxs-lookup"><span data-stu-id="a9b55-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="a9b55-115">[Stáhněte si nejnovější soubor operačního systému HoloLens 2](https://aka.ms/hololens2download) přímo do počítače.</span><span class="sxs-lookup"><span data-stu-id="a9b55-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="a9b55-116">Podpora této konfigurace je součástí buildu 19041.1117 a vyššího.</span><span class="sxs-lookup"><span data-stu-id="a9b55-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="a9b55-117">Stažení nebo instalace nástroje Advanced Recovery Companion(ARC) [z Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) do počítače</span><span class="sxs-lookup"><span data-stu-id="a9b55-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="a9b55-118">Stáhněte si nebo nainstalujte [nejnovější nástroj Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) z Microsoft Store do počítače.</span><span class="sxs-lookup"><span data-stu-id="a9b55-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="a9b55-119">[Stáhněte složku OfflineSecureHL2_Sample se soubory projektu a](https://aka.ms/HoloLensDocs-SecureOfflineSample) sestavte PPKG.</span><span class="sxs-lookup"><span data-stu-id="a9b55-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="a9b55-120">Připravte offline [obchodní aplikaci na nasazení PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="a9b55-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="a9b55-121">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="a9b55-121">Configure</span></span>

<span data-ttu-id="a9b55-122">Vytvoření zřizovacího balíčku zabezpečené konfigurace</span><span class="sxs-lookup"><span data-stu-id="a9b55-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="a9b55-123">Na počítači spusťte nástroj WCD.</span><span class="sxs-lookup"><span data-stu-id="a9b55-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="a9b55-124">Vyberte **Soubor -> Otevřít projekt.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="a9b55-125">Přejděte do umístění dříve uložené OfflineSecureHL2_Sample složky a vyberte: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="a9b55-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="a9b55-126">Projekt by se měl otevřít a teď byste měli mít seznam dostupných přizpůsobení:</span><span class="sxs-lookup"><span data-stu-id="a9b55-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b55-127">![Snímek obrazovky s konfiguračním balíčkem otevřeným ve WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="a9b55-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="a9b55-128">Konfigurace nastavené v tomto zřizovacím balíčku:</span><span class="sxs-lookup"><span data-stu-id="a9b55-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="a9b55-129">Položka</span><span class="sxs-lookup"><span data-stu-id="a9b55-129">Item</span></span>                                                |     <span data-ttu-id="a9b55-130">Nastavení</span><span class="sxs-lookup"><span data-stu-id="a9b55-130">Setting</span></span>                       |     <span data-ttu-id="a9b55-131">Popis</span><span class="sxs-lookup"><span data-stu-id="a9b55-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="a9b55-132">Účty a uživatelé</span><span class="sxs-lookup"><span data-stu-id="a9b55-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="a9b55-133">Místní uživatelské jméno & heslo</span><span class="sxs-lookup"><span data-stu-id="a9b55-133">Local User Name & Password</span></span>    |     <span data-ttu-id="a9b55-134">U těchto offline zařízení musí všichni uživatelé zařízení nastavit a sdílet jedno uživatelské jméno a heslo.</span><span class="sxs-lookup"><span data-stu-id="a9b55-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="a9b55-135">První prostředí / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="a9b55-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="a9b55-136">Ano</span><span class="sxs-lookup"><span data-stu-id="a9b55-136">True</span></span>                          |     <span data-ttu-id="a9b55-137">Přeskočí jen počáteční nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="a9b55-138">První zkušenosti / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="a9b55-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="a9b55-139">Ano</span><span class="sxs-lookup"><span data-stu-id="a9b55-139">True</span></span>                          |     <span data-ttu-id="a9b55-140">Přeskočí trénování zařízení během počátečního nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="a9b55-141">První prostředí / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="a9b55-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="a9b55-142">Ano</span><span class="sxs-lookup"><span data-stu-id="a9b55-142">True</span></span>                          |     <span data-ttu-id="a9b55-143">Přeskočí Wi-Fi konfigurace během počátečního nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="a9b55-144">Zásady/Připojení/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="a9b55-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="a9b55-145">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-145">No</span></span>                            |     <span data-ttu-id="a9b55-146">Zakáže Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="a9b55-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="a9b55-147">Zásady/Prostředí/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="a9b55-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="a9b55-148">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-148">No</span></span>                            |     <span data-ttu-id="a9b55-149">Zakáže Cortanu (aby se eliminly potenciální problémy, protože mikrofony jsou zakázané)</span><span class="sxs-lookup"><span data-stu-id="a9b55-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="a9b55-150">Zásady/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="a9b55-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="a9b55-151">Yes</span><span class="sxs-lookup"><span data-stu-id="a9b55-151">Yes</span></span>                           |     <span data-ttu-id="a9b55-152">Zakáže mikrofon.</span><span class="sxs-lookup"><span data-stu-id="a9b55-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="a9b55-153">Zásady/Ochrana osobních údajů/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="a9b55-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="a9b55-154">Vynutit odepření</span><span class="sxs-lookup"><span data-stu-id="a9b55-154">Force deny</span></span>                    |     <span data-ttu-id="a9b55-155">Brání aplikacím v pokusu o přístup k datům o poloze (aby se eliminly potenciální problémy, protože sledování polohy je zakázané).</span><span class="sxs-lookup"><span data-stu-id="a9b55-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="a9b55-156">Zásady/Ochrana osobních údajů/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="a9b55-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="a9b55-157">Vynutit odepření</span><span class="sxs-lookup"><span data-stu-id="a9b55-157">Force deny</span></span>                    |     <span data-ttu-id="a9b55-158">Brání aplikacím v pokusu o přístup k mikrofonům (aby se eliminly potenciální problémy, protože mikrofony jsou zakázané).</span><span class="sxs-lookup"><span data-stu-id="a9b55-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="a9b55-159">Zásady/Zabezpečení/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="a9b55-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="a9b55-160">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-160">No</span></span>                            |     <span data-ttu-id="a9b55-161">Zabrání komukoli v přidávání zřizovacích balíčků, které se můžou pokoušet přepsat zásady uzamčení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="a9b55-162">Zásady/Zabezpečení/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="a9b55-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="a9b55-163">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-163">No</span></span>                            |     <span data-ttu-id="a9b55-164">Zabrání komukoli v odebrání tohoto uzamčeného zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="a9b55-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="a9b55-165">Zásady/Systém/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="a9b55-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="a9b55-166">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-166">No</span></span>                            |     <span data-ttu-id="a9b55-167">Zabrání zařízení v pokusu o sledování dat o poloze.</span><span class="sxs-lookup"><span data-stu-id="a9b55-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="a9b55-168">Zásady/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="a9b55-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="a9b55-169">No</span><span class="sxs-lookup"><span data-stu-id="a9b55-169">No</span></span>                            |     <span data-ttu-id="a9b55-170">Zakáže Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a9b55-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="a9b55-171">V části Nastavení modulu runtime vyberte **Účty / Uživatelé / Uživatelské jméno: Holo / Heslo.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="a9b55-172">Poznamenejte si heslo a v případě potřeby resetujte.</span><span class="sxs-lookup"><span data-stu-id="a9b55-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="a9b55-173">Přejděte na UniversalAppInstall / UserContextApp a nakonfigurujte [obchodní aplikaci,](app-deploy-provisioning-package.md) kterou nasazujete do těchto zařízení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b55-174">![Snímek obrazovky s přidáním aplikace do WCD](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="a9b55-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="a9b55-175">Po dokončení vyberte tlačítko Exportovat a postupujte podle všech výtek, dokud se nevytycí zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="a9b55-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b55-176">![Snímek obrazovky s tlačítkem Exportovat pro tento balíček v WCD](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="a9b55-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="a9b55-177">Nasadit</span><span class="sxs-lookup"><span data-stu-id="a9b55-177">Deploy</span></span>

1. <span data-ttu-id="a9b55-178">Připojte HL2 k počítači Windows 10 pomocí kabelu USB.</span><span class="sxs-lookup"><span data-stu-id="a9b55-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="a9b55-179">Spusťte nástroj ARC a vyberte **HoloLens 2.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Počáteční obrazovka čistého zpětného lomítka HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="a9b55-181">Na další obrazovce vyberte **Ruční výběr balíčku.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-181">On the next screen select **Manual package selection**.</span></span>

   ![Informační obrazovka HoloLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="a9b55-183">Přejděte na dříve stažený soubor .ffu a vyberte **Otevřít.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="a9b55-184">Na stránce Upozornění vyberte **Pokračovat.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-184">At the Warning page select **Continue**.</span></span>

   ![Obrazovka upozornění HoloLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="a9b55-186">Počkejte, až nástroj ARC dokončí instalaci operačního systému HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a9b55-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="a9b55-187">Jakmile zařízení dokončí instalaci a spustí se znovu, přejděte z počítače na Průzkumník souborů a zkopírujte dříve uložený soubor PPKG do složky zařízení.</span><span class="sxs-lookup"><span data-stu-id="a9b55-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9b55-188">![Soubor PPKG na počítači v Průzkumník souborů okně.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="a9b55-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="a9b55-189">Na holoLens 2 stiskněte následující kombinaci tlačítek, aby se spouštěl zřizovací balíček: **Klepněte** současně na Snížení objemu a tlačítko napájení. </span><span class="sxs-lookup"><span data-stu-id="a9b55-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="a9b55-190">Zobrazí se výzva k použití zřizovacího balíčku a vyberte **Potvrdit.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="a9b55-191">Po dokončení zřizovacího balíčku vyberte **OK.**</span><span class="sxs-lookup"><span data-stu-id="a9b55-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="a9b55-192">Pak byste měli být vyzváni k přihlášení k zařízení pomocí sdíleného místního účtu a hesla.</span><span class="sxs-lookup"><span data-stu-id="a9b55-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="a9b55-193">Údržba</span><span class="sxs-lookup"><span data-stu-id="a9b55-193">Maintain</span></span>

<span data-ttu-id="a9b55-194">S touto konfigurací se doporučuje restartovat výše uvedený proces a zařízení znovu zobrazit v nástroji ARC a použít nový PPKG k provádění aktualizací operačního systému nebo aplikací.</span><span class="sxs-lookup"><span data-stu-id="a9b55-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
