---
title: Odemknutí Windows Holographic for Business funkcí
description: Při upgradu na Windows Holographic for Business holoLens poskytuje další funkce, které jsou navržené pro firmy.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377630"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="1bef0-103">Odemknutí Windows Holographic for Business funkcí</span><span class="sxs-lookup"><span data-stu-id="1bef0-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bef0-104">Tato stránka se týká pouze HoloLens 1. generace.</span><span class="sxs-lookup"><span data-stu-id="1bef0-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="1bef0-105">Microsoft HoloLens je k dispozici v edici *Development Edition* s Windows Holographic (edice Windows 10, která je určená pro HoloLens), a v komerční edici [,](hololens-commercial-features.md)která poskytuje další funkce určené pro firmy.</span><span class="sxs-lookup"><span data-stu-id="1bef0-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="1bef0-106">Když si koupíte komerční sadu, obdržíte licenci, která upgradují Windows Holographic na Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="1bef0-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="1bef0-107">Tuto licenci můžete na zařízení použít buď pomocí poskytovatele správy mobilních zařízení [(MDM)](#edition-upgrade-by-using-mdm) organizace, nebo zřizovacího [balíčku](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="1bef0-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="1bef0-108">V Windows 10 verze 1803 můžete výběrem možnosti **Settings** System (Systém nastavení) zkontrolovat, jestli byl HoloLens upgradován na obchodní  >  **edici.**</span><span class="sxs-lookup"><span data-stu-id="1bef0-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="1bef0-109">Upgrade edice pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="1bef0-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="1bef0-110">Podnikovou licenci může použít jakýkoli poskytovatel MDM, který podporuje poskytovatele konfiguračních služeb [WindowsLicensing (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="1bef0-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="1bef0-111">Nejnovější verze rozhraní MICROSOFT MDM API bude podporovat WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="1bef0-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="1bef0-112">Podrobné pokyny k upgradu HoloLens pomocí nástroje Microsoft Intune v tématu Upgrade zařízení s [Windows Holographic na Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="1bef0-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="1bef0-113">U jiných poskytovatelů MDM se konkrétní kroky pro nastavení a nasazení zásad můžou lišit.</span><span class="sxs-lookup"><span data-stu-id="1bef0-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="1bef0-114">Upgrade edice pomocí zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="1bef0-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="1bef0-115">Zřizovací balíčky jsou soubory vytvořené nástrojem Windows Configuration Designer, který pro zařízení použije zadanou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="1bef0-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="1bef0-116">Vytvoření zřizovacího balíčku, který upgraduuje edici Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="1bef0-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="1bef0-117">Vytvořte zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bef0-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="1bef0-118">Přejděte na **Nastavení modulu runtime**  >  **EditionUpgrade** a vyberte **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="1bef0-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Upgrade edice s vybraným nastavením licence](images/icd1.png)

1. <span data-ttu-id="1bef0-120">Vyhledejte licenční soubor XML, který jste poskytli při nákupu komerční sady.</span><span class="sxs-lookup"><span data-stu-id="1bef0-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1bef0-121">V [zřizovacího balíčku můžete nakonfigurovat další nastavení.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="1bef0-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="1bef0-122">V nabídce **File** (Soubor) vyberte **Save** (Uložit).</span><span class="sxs-lookup"><span data-stu-id="1bef0-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="1bef0-123">Přečtěte si upozornění, že soubory projektu mohou obsahovat citlivé informace, a klikněte na **OK.**</span><span class="sxs-lookup"><span data-stu-id="1bef0-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1bef0-124">Při vytváření zřizovacího balíčku můžete do souborů projektu a souboru zřizovacího balíčku (.ppkg) zahrnout citlivé informace.</span><span class="sxs-lookup"><span data-stu-id="1bef0-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="1bef0-125">I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou zašifrované.</span><span class="sxs-lookup"><span data-stu-id="1bef0-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="1bef0-126">Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, pokud už je nepotřebujete.</span><span class="sxs-lookup"><span data-stu-id="1bef0-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="1bef0-127">V **nabídce Export** vyberte **Zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="1bef0-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="1bef0-128">Změňte **možnost Vlastník** na Správce **IT,** která nastaví prioritu tohoto zřizovacího balíčku tak, aby byla vyšší než jiná nastavení použitá na toto zařízení z různých zdrojů, a pak vyberte **Další.**</span><span class="sxs-lookup"><span data-stu-id="1bef0-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="1bef0-129">Nastavte hodnotu pro **Package Version (Verze balíčku).**</span><span class="sxs-lookup"><span data-stu-id="1bef0-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1bef0-130">Můžete provádět změny existujících balíčků a změnit číslo verze tak, aby se dříve použité balíčky aktualizují.</span><span class="sxs-lookup"><span data-stu-id="1bef0-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="1bef0-131">V **části Vybrat podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další.**</span><span class="sxs-lookup"><span data-stu-id="1bef0-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="1bef0-132">Vyberte **Další** a zadejte výstupní umístění, kam má zřizovací balíček po jeho vytváření přejít.</span><span class="sxs-lookup"><span data-stu-id="1bef0-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="1bef0-133">Windows ICD ve výchozím nastavení používá jako výstupní umístění složku projektu.</span><span class="sxs-lookup"><span data-stu-id="1bef0-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="1bef0-134">Volitelně můžete vybrat Procházet **a** změnit výchozí umístění výstupu.</span><span class="sxs-lookup"><span data-stu-id="1bef0-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="1bef0-135">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="1bef0-135">Select **Next**.</span></span>

1. <span data-ttu-id="1bef0-136">Vyberte **Build (Sestavit)** a začněte vytvářet balíček.</span><span class="sxs-lookup"><span data-stu-id="1bef0-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="1bef0-137">Na stránce sestavení se zobrazí informace o projektu a indikátor průběhu uvádí stav sestavení.</span><span class="sxs-lookup"><span data-stu-id="1bef0-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="1bef0-138">Po dokončení sestavení vyberte **Dokončit.**</span><span class="sxs-lookup"><span data-stu-id="1bef0-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="1bef0-139">Použití zřizovacího balíčku pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="1bef0-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="1bef0-140">Pomocí kabelu USB připojte zařízení k počítači.</span><span class="sxs-lookup"><span data-stu-id="1bef0-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="1bef0-141">Spusťte zařízení, ale neposířte ho za stránku přizpůsobení prostředí počátečního nastavení (první stránka s modrým rámečem). </span><span class="sxs-lookup"><span data-stu-id="1bef0-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="1bef0-142">Na počítači se HoloLens zobrazí jako zařízení v Průzkumník souborů.</span><span class="sxs-lookup"><span data-stu-id="1bef0-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1bef0-143">Pokud zařízení HoloLens používá Windows 10 verze 1607 nebo starší, otevřete Průzkumník souborů tak, že na  zařízení  krátce stisknete a uvolníte tlačítka Pro vypnutí a Napájení.</span><span class="sxs-lookup"><span data-stu-id="1bef0-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="1bef0-144">V Průzkumník souborů přetáhněte zřizovací balíček (.ppkg) do úložiště zařízení.</span><span class="sxs-lookup"><span data-stu-id="1bef0-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="1bef0-145">Zatímco HoloLens je stále na **fitové** stránce, krátce  znovu stiskněte a uvolněte tlačítka **Pro** snížení hlasitosti a Napájení.</span><span class="sxs-lookup"><span data-stu-id="1bef0-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="1bef0-146">HoloLens se vás zeptá, jestli balíčku důvěřujete, a chcete ho použít.</span><span class="sxs-lookup"><span data-stu-id="1bef0-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="1bef0-147">Ověřte, že balíčku důvěřujete.</span><span class="sxs-lookup"><span data-stu-id="1bef0-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="1bef0-148">Uvidíte, jestli se balíček úspěšně použil, nebo ne.</span><span class="sxs-lookup"><span data-stu-id="1bef0-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="1bef0-149">Pokud se nepoupravil úspěšně, můžete balíček opravit a zkusit to znovu.</span><span class="sxs-lookup"><span data-stu-id="1bef0-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="1bef0-150">V případě úspěchu pokračujte v nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="1bef0-150">If successful, proceed with device setup.</span></span>
