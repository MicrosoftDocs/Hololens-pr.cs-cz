---
title: HoloLens BitLocker Encryption
description: Zjistěte, jak povolit šifrování zařízení nástrojem BitLocker za účelem ochrany souborů uložených na zařízeních hybridní reality HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377526"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="8f4c7-103">HoloLens (1. generace) Šifrování nástrojem BitLocker</span><span class="sxs-lookup"><span data-stu-id="8f4c7-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="8f4c7-104">HoloLens (1. generace) i HoloLens 2 podporují šifrování zařízení pomocí BitLockeru, ale BitLocker je na HoloLens 2 vždycky povolený.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="8f4c7-105">Tento článek vám pomůže povolit a spravovat BitLocker na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="8f4c7-106">V HoloLens (1. generace) můžete šifrování zařízení nástrojem BitLocker povolit ručně nebo pomocí správy mobilních zařízení (MDM).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="8f4c7-107">Podle těchto pokynů povolte [šifrování zařízení nástrojem BitLocker,](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) abyste ochránili soubory a informace uložené v HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="8f4c7-108">Šifrování zařízení pomáhá chránit vaše data pomocí metody šifrování AES-CBC 128, která je ekvivalentní metodě [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) v poskytovateli konfigurační služby BitLockeru (CSP).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="8f4c7-109">Pracovníci, kteří mají správný šifrovací klíč (například heslo), ho mohou dešifrovat nebo provést obnovení dat.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="8f4c7-110">Povolení šifrování zařízení pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="8f4c7-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="8f4c7-111">Pomocí zprostředkovatele Mobile Správa zařízení (MDM) můžete použít zásadu, která vyžaduje šifrování zařízení.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="8f4c7-112">Zásadou, která se má použít, je nastavení [Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) v CSP zásad.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="8f4c7-113">Přečtěte si pokyny k povolení šifrování zařízení pomocí Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="8f4c7-114">Pokyny k dalším nástrojům MDM najdete v dokumentaci k poskytovateli MDM.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="8f4c7-115">Pokud váš poskytovatel MDM vyžaduje vlastní identifikátor URI pro šifrování zařízení, použijte následující konfiguraci:</span><span class="sxs-lookup"><span data-stu-id="8f4c7-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="8f4c7-116">**Name**(Název): Název podle vašeho výběru.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="8f4c7-117">**Popis:** volitelné</span><span class="sxs-lookup"><span data-stu-id="8f4c7-117">**Description**: optional</span></span>
- <span data-ttu-id="8f4c7-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="8f4c7-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="8f4c7-119">**Datový typ:** celé číslo</span><span class="sxs-lookup"><span data-stu-id="8f4c7-119">**Data type**: integer</span></span>
- <span data-ttu-id="8f4c7-120">**Hodnota:**`1`</span><span class="sxs-lookup"><span data-stu-id="8f4c7-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="8f4c7-121">Povolení šifrování zařízení pomocí zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="8f4c7-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="8f4c7-122">Zřizovací balíčky jsou soubory vytvořené nástrojem Windows Configuration Designer, který pro zařízení použije zadanou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="8f4c7-123">Vytvoření zřizovacího balíčku, který upgraduuje edici Windows Holographic a povolí šifrování</span><span class="sxs-lookup"><span data-stu-id="8f4c7-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="8f4c7-124">Vytvořte zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="8f4c7-125">Přejděte na **Nastavení modulu runtime**  >  **Zabezpečení**  >  **zásad** a vyberte **VyžadovatDeviceEncryption.**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Vyžadovat nastavení šifrování zařízení nakonfigurované na Ano](images/device-encryption.png)

1. <span data-ttu-id="8f4c7-127">Vyhledejte licenční soubor XML, který jste poskytli při nákupu komerční sady.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="8f4c7-128">Přejděte na soubor s licencí XML, který jste poskytli při nákupu komerční sady, a vyberte ho.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8f4c7-129">Další nastavení [můžete nakonfigurovat v zřizovacím balíčku](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="8f4c7-130">V nabídce **File** (Soubor) klikněte na **Save** (Uložit).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="8f4c7-131">Přečtěte si upozornění s vysvětlením, že soubory projektu mohou obsahovat citlivé informace, a klikněte na **OK.**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8f4c7-132">Při vytváření zřizovacího balíčku můžete do souborů projektu a souboru zřizovacího balíčku (.ppkg) zahrnout citlivé informace.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="8f4c7-133">I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou šifrovány.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="8f4c7-134">Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, pokud už je nepotřebujete.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="8f4c7-135">V nabídce **Export** klikněte na **Zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="8f4c7-136">Změňte **možnost Vlastník** na Správce **IT,** která nastaví prioritu tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů, a pak vyberte **Další.**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="8f4c7-137">Nastavte hodnotu pro **Package Version (Verze balíčku).**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f4c7-138">Můžete provádět změny existujících balíčků a změnit číslo verze tak, aby se dříve použité balíčky aktualizují.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="8f4c7-139">V části **Vyberte podrobnosti zabezpečení pro zřizovací balíček** klikněte na **Další.**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="8f4c7-140">Klikněte **na** Další a zadejte výstupní umístění, kam má zřizovací balíček po jeho vytváření přejít.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="8f4c7-141">Windows ICD ve výchozím nastavení používá jako výstupní umístění složku projektu.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="8f4c7-142">Volitelně můžete kliknutím na Procházet změnit výchozí umístění výstupu.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="8f4c7-143">Klikněte na **Next** (Další).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-143">Click **Next**.</span></span>
1. <span data-ttu-id="8f4c7-144">Kliknutím **na** Build (Sestavit) začněte vytvářet balíček.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="8f4c7-145">Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu označuje stav sestavení.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="8f4c7-146">Po dokončení sestavení klikněte na **Dokončit.**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="8f4c7-147">Použití zřizovacího balíčku pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="8f4c7-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="8f4c7-148">Připojte zařízení přes USB k počítači a spusťte ho,  ale neposíjte ho dál za stránku přizpůsobení prostředí počátečního nastavení (první stránka s modrým rámečem).</span><span class="sxs-lookup"><span data-stu-id="8f4c7-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="8f4c7-149">Krátce stiskněte a **uvolněte tlačítka Pro snížení hlasitosti** a Napájení současně. </span><span class="sxs-lookup"><span data-stu-id="8f4c7-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="8f4c7-150">HoloLens se zobrazí jako zařízení v Průzkumník souborů počítači.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="8f4c7-151">V Průzkumník souborů přetáhněte zřizovací balíček (.ppkg) do úložiště zařízení.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="8f4c7-152">Krátce stiskněte a **uvolněte tlačítka Pro** snížení hlasitosti a Napájení současně na **stránce** Přizpůsobit. </span><span class="sxs-lookup"><span data-stu-id="8f4c7-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="8f4c7-153">Zařízení se vás zeptá, jestli balíčku důvěřujete, a chcete ho použít.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="8f4c7-154">Ověřte, že balíčku důvěřujete.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="8f4c7-155">Uvidíte, jestli se balíček úspěšně použil, nebo ne.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="8f4c7-156">Pokud se to nepovedlo, můžete balíček opravit a zkusit to znovu.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="8f4c7-157">Pokud byla úspěšná, pokračujte v nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="8f4c7-158">Pokud bylo zařízení zakoupené před srpnem 2016, budete se k zařízení muset přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a pak resetovat operační systém, abyste mohli použít zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="8f4c7-159">Ověření šifrování zařízení</span><span class="sxs-lookup"><span data-stu-id="8f4c7-159">Verify device encryption</span></span>

<span data-ttu-id="8f4c7-160">Šifrování je na HoloLens tiché.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="8f4c7-161">Ověření stavu šifrování zařízení:</span><span class="sxs-lookup"><span data-stu-id="8f4c7-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="8f4c7-162">V HoloLens přejděte na **Settings System**  >  About (Systém nastavení **o**  >  **aplikaci).**</span><span class="sxs-lookup"><span data-stu-id="8f4c7-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="8f4c7-163">**BitLocker** je **povolený,** pokud je zařízení zašifrované.</span><span class="sxs-lookup"><span data-stu-id="8f4c7-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Obrazovka s povoleným BitLockerem](images/about-encryption.png)
