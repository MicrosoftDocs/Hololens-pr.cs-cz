---
title: odemčení funkcí Windows Holographic for Business
description: když upgradujete na Windows Holographic for Business, HoloLens poskytuje další funkce, které jsou navržené pro firmy.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635190"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="fc82b-103">odemčení funkcí Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="fc82b-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc82b-104">tato stránka se vztahuje pouze na HoloLens 1. generace.</span><span class="sxs-lookup"><span data-stu-id="fc82b-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="fc82b-105">Microsoft HoloLens je dostupná ve *verzi pro vývoj*, která se spouští Windows holografická (edice Windows 10, která je navržená pro HoloLens), a v [komerční sadě](hololens-commercial-features.md), která poskytuje další funkce navržené pro firmy.</span><span class="sxs-lookup"><span data-stu-id="fc82b-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="fc82b-106">po zakoupení komerční sady obdržíte licenci, která upgraduje Windows holografickou Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="fc82b-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="fc82b-107">Tuto licenci můžete na zařízení použít buď pomocí [poskytovatele správy mobilních zařízení (MDM)](#edition-upgrade-by-using-mdm) organizace, nebo [zřizovacího balíčku](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="fc82b-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="fc82b-108">v Windows 10 verze 1803 můžete kliknutím na **Nastavení** systém ověřit, že HoloLens upgradována na edici business edition  >  .</span><span class="sxs-lookup"><span data-stu-id="fc82b-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="fc82b-109">Upgrade edice pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="fc82b-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="fc82b-110">Licenci Enterprise může použít libovolný poskytovatel MDM, který podporuje [poskytovatele služby WindowsLicensing Configuration Service Provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc82b-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="fc82b-111">Nejnovější verze rozhraní Microsoft MDM API bude podporovat WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="fc82b-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="fc82b-112">podrobné pokyny pro upgrade HoloLens pomocí Microsoft Intune najdete v tématu [Upgrade zařízení s Windows holografickou na Windows Holographic for Business](/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="fc82b-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="fc82b-113">U jiných poskytovatelů MDM se můžou konkrétní kroky pro nastavení a nasazení zásad lišit.</span><span class="sxs-lookup"><span data-stu-id="fc82b-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="fc82b-114">Upgrade edice pomocí zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="fc82b-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="fc82b-115">zřizovací balíčky jsou soubory vytvořené nástrojem pro návrháře konfigurace Windows, které pro zařízení používají zadanou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="fc82b-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="fc82b-116">vytvoření zřizovacího balíčku, který upgraduje Windows holografické edice</span><span class="sxs-lookup"><span data-stu-id="fc82b-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="fc82b-117">Vytvořte zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fc82b-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="fc82b-118">Přejít na **nastavení modulu runtime**  >  **EditionUpgrade** a vyberte **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Vybraná možnost upgradovat edici s nastavením licence](images/icd1.png)

1. <span data-ttu-id="fc82b-120">Vyhledejte soubor s licencí XML, který jste zadali při nákupu komerční sady.</span><span class="sxs-lookup"><span data-stu-id="fc82b-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc82b-121">[Další nastavení můžete nakonfigurovat v balíčku zřizování](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="fc82b-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="fc82b-122">V nabídce **File** (Soubor) vyberte **Save** (Uložit).</span><span class="sxs-lookup"><span data-stu-id="fc82b-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="fc82b-123">Přečtěte si upozornění, že soubory projektu můžou obsahovat citlivé informace a klikněte na **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fc82b-124">Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a soubor zřizovacího balíčku (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="fc82b-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="fc82b-125">I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány.</span><span class="sxs-lookup"><span data-stu-id="fc82b-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="fc82b-126">Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, pokud už je nepotřebujete.</span><span class="sxs-lookup"><span data-stu-id="fc82b-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="fc82b-127">V nabídce **Export** vyberte **zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="fc82b-128">Změňte **vlastníka** na **správce IT**, který nastaví prioritu tohoto zřizovacího balíčku tak, aby byla vyšší než jiné použité pro toto zařízení z různých zdrojů, a pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="fc82b-129">Nastavte hodnotu pro **verzi balíčku**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fc82b-130">Můžete provádět změny stávajících balíčků a změnit číslo verze na aktualizace dřív použitých balíčků.</span><span class="sxs-lookup"><span data-stu-id="fc82b-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="fc82b-131">V **části vybrat podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="fc82b-132">Výběrem možnosti **Další** zadejte umístění výstupu, kde má zřizovací balíček přejít po sestavení.</span><span class="sxs-lookup"><span data-stu-id="fc82b-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="fc82b-133">ve výchozím nastavení používá Windows ICD jako výstupní umístění složku projektu.</span><span class="sxs-lookup"><span data-stu-id="fc82b-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="fc82b-134">Volitelně můžete vybrat možnost **Procházet** a změnit výchozí umístění výstupu.</span><span class="sxs-lookup"><span data-stu-id="fc82b-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="fc82b-135">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-135">Select **Next**.</span></span>

1. <span data-ttu-id="fc82b-136">Vyberte **sestavení** pro zahájení sestavování balíčku.</span><span class="sxs-lookup"><span data-stu-id="fc82b-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="fc82b-137">Na stránce Build (sestavení) se zobrazí informace o projektu a indikátor průběhu indikuje stav sestavení.</span><span class="sxs-lookup"><span data-stu-id="fc82b-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="fc82b-138">Po dokončení sestavení vyberte **Dokončit**.</span><span class="sxs-lookup"><span data-stu-id="fc82b-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="fc82b-139">Použití zřizovacího balíčku na HoloLens</span><span class="sxs-lookup"><span data-stu-id="fc82b-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="fc82b-140">Připojte zařízení k počítači pomocí kabelu USB.</span><span class="sxs-lookup"><span data-stu-id="fc82b-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="fc82b-141">Spusťte zařízení, ale nepokračujte za stránku **přizpůsobení** počátečního nastavení (první stránka s modrým polem).</span><span class="sxs-lookup"><span data-stu-id="fc82b-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="fc82b-142">v počítači se HoloLens v průzkumníkovi souborů zobrazí jako zařízení.</span><span class="sxs-lookup"><span data-stu-id="fc82b-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc82b-143">pokud HoloLens zařízení běží Windows 10 verze 1607 nebo starší, otevřete průzkumníka souborů tak, že na zařízení krátce **vypínáte** a uvolníte tlačítka hlasitosti a **napájení** .</span><span class="sxs-lookup"><span data-stu-id="fc82b-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="fc82b-144">V Průzkumníku souborů přetáhněte zřizovací balíček (. ppkg) do úložiště zařízení.</span><span class="sxs-lookup"><span data-stu-id="fc82b-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="fc82b-145">i když je HoloLens stále na stránce **přizpůsobit** , krátce potiskněte a uvolněte **i tlačítko pro vypnutí a vypnutí** **hlasitosti** .</span><span class="sxs-lookup"><span data-stu-id="fc82b-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="fc82b-146">HoloLens vás vyzve k tomu, kdybyste balíček důvěřovali a chtěli byste ho použít.</span><span class="sxs-lookup"><span data-stu-id="fc82b-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="fc82b-147">Potvrďte, že balíček důvěřujete.</span><span class="sxs-lookup"><span data-stu-id="fc82b-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="fc82b-148">Zobrazí se informace o tom, zda byl balíček úspěšně použit, nebo nikoli.</span><span class="sxs-lookup"><span data-stu-id="fc82b-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="fc82b-149">Pokud se nepovedlo úspěšně použít, můžete balíček opravit a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="fc82b-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="fc82b-150">V případě úspěchu pokračujte v nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="fc82b-150">If successful, proceed with device setup.</span></span>
