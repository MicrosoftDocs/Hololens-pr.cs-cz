---
title: HoloLens Šifrování BitLockeru
description: naučte se, jak povolit šifrování zařízení pomocí nástroje BitLocker k ochraně souborů uložených ve vašich zařízeních HoloLens hybridní realitu.
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
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635241"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="6eba6-103">šifrování bitlockeru HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="6eba6-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="6eba6-104">HoloLens (1. generace) a HoloLens 2 podporují šifrování zařízení pomocí nástroje bitlocker, ale nástroj bitlocker je vždy povolený v HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6eba6-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="6eba6-105">tento článek vám pomůže s povolením a správou nástroje BitLocker na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="6eba6-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="6eba6-106">v HoloLens (1. generace) můžete povolit šifrování zařízení pomocí nástroje BitLocker ručně nebo pomocí správy mobilních zařízení (MDM).</span><span class="sxs-lookup"><span data-stu-id="6eba6-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="6eba6-107">Pomocí těchto pokynů povolte [šifrování zařízení s nástrojem BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) k ochraně souborů a informací uložených v HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6eba6-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="6eba6-108">Šifrování zařízení pomáhá chránit vaše data pomocí metody šifrování AES-CBC 128, která je ekvivalentní [EncryptionMethodByDriveType metodě 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ve zprostředkovateli kryptografických služeb (CSP) nástroje BitLocker.</span><span class="sxs-lookup"><span data-stu-id="6eba6-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="6eba6-109">Pracovníci, kteří mají správný šifrovací klíč (například heslo), ho můžou dešifrovat nebo obnovení dat provést.</span><span class="sxs-lookup"><span data-stu-id="6eba6-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="6eba6-110">Povolení šifrování zařízení pomocí MDM</span><span class="sxs-lookup"><span data-stu-id="6eba6-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="6eba6-111">Pomocí poskytovatele správy mobilních zařízení (MDM) můžete použít zásadu, která vyžaduje šifrování zařízení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="6eba6-112">Zásady, které se mají použít, jsou [nastavení zabezpečení/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) ve zprostředkovateli kryptografických služeb v zásadách.</span><span class="sxs-lookup"><span data-stu-id="6eba6-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="6eba6-113">Přečtěte si pokyny pro povolení šifrování zařízení pomocí Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6eba6-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="6eba6-114">Další informace o dalších nástrojích MDM najdete v dokumentaci poskytovatele MDM.</span><span class="sxs-lookup"><span data-stu-id="6eba6-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="6eba6-115">Pokud poskytovatel MDM vyžaduje pro šifrování zařízení vlastní identifikátor URI, použijte následující konfiguraci:</span><span class="sxs-lookup"><span data-stu-id="6eba6-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="6eba6-116">**Název**: název dle vašeho výběru.</span><span class="sxs-lookup"><span data-stu-id="6eba6-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="6eba6-117">**Popis**: volitelné</span><span class="sxs-lookup"><span data-stu-id="6eba6-117">**Description**: optional</span></span>
- <span data-ttu-id="6eba6-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="6eba6-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="6eba6-119">**Datový typ**: celé číslo</span><span class="sxs-lookup"><span data-stu-id="6eba6-119">**Data type**: integer</span></span>
- <span data-ttu-id="6eba6-120">**Hodnota**: `1`</span><span class="sxs-lookup"><span data-stu-id="6eba6-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="6eba6-121">Povolení šifrování zařízení pomocí zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="6eba6-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="6eba6-122">zřizovací balíčky jsou soubory vytvořené nástrojem pro návrháře konfigurace Windows, které pro zařízení používají zadanou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="6eba6-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="6eba6-123">vytvoření zřizovacího balíčku, který upgraduje Windows holografickou edici a povoluje šifrování</span><span class="sxs-lookup"><span data-stu-id="6eba6-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="6eba6-124">Vytvořte zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6eba6-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="6eba6-125">Přejít na **nastavení modulu runtime**  >  **zásady**  >  **zabezpečení** a vyberte **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Vyžadovat nastavení šifrování zařízení nakonfigurované na Ano](images/device-encryption.png)

1. <span data-ttu-id="6eba6-127">Vyhledejte soubor s licencí XML, který jste zadali při nákupu komerční sady.</span><span class="sxs-lookup"><span data-stu-id="6eba6-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="6eba6-128">Vyhledejte a vyberte soubor s licencí XML, který jste zadali při nákupu komerční sady.</span><span class="sxs-lookup"><span data-stu-id="6eba6-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="6eba6-129">[Další nastavení můžete nakonfigurovat v balíčku zřizování](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="6eba6-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="6eba6-130">V nabídce **File** (Soubor) klikněte na **Save** (Uložit).</span><span class="sxs-lookup"><span data-stu-id="6eba6-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="6eba6-131">Přečtěte si upozornění, které vysvětluje, že soubory projektu můžou obsahovat citlivé informace a klikněte na **OK**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6eba6-132">Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a soubor zřizovacího balíčku (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="6eba6-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="6eba6-133">I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány.</span><span class="sxs-lookup"><span data-stu-id="6eba6-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="6eba6-134">Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, pokud už je nepotřebujete.</span><span class="sxs-lookup"><span data-stu-id="6eba6-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="6eba6-135">V nabídce **exportovat** klikněte na **zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="6eba6-136">Změňte **vlastníka** na **správce IT**, který nastaví prioritu tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů a pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="6eba6-137">Nastavte hodnotu pro **verzi balíčku**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6eba6-138">Můžete provádět změny stávajících balíčků a změnit číslo verze na aktualizace dřív použitých balíčků.</span><span class="sxs-lookup"><span data-stu-id="6eba6-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="6eba6-139">V části **Vybrat podrobnosti zabezpečení pro zřizovací balíček** klikněte na **Další**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="6eba6-140">Klikněte na tlačítko **Další** a zadejte umístění výstupu, kde má zřizovací balíček přejít po sestavení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="6eba6-141">ve výchozím nastavení používá Windows ICD jako výstupní umístění složku projektu.</span><span class="sxs-lookup"><span data-stu-id="6eba6-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="6eba6-142">Případně můžete kliknout na tlačítko Procházet a změnit výchozí umístění výstupu.</span><span class="sxs-lookup"><span data-stu-id="6eba6-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="6eba6-143">Klikněte na **Next** (Další).</span><span class="sxs-lookup"><span data-stu-id="6eba6-143">Click **Next**.</span></span>
1. <span data-ttu-id="6eba6-144">Kliknutím na **sestavit** zahajte sestavování balíčku.</span><span class="sxs-lookup"><span data-stu-id="6eba6-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="6eba6-145">Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu indikuje stav sestavení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="6eba6-146">Po dokončení sestavení klikněte na **Dokončit**.</span><span class="sxs-lookup"><span data-stu-id="6eba6-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="6eba6-147">Použití zřizovacího balíčku na HoloLens</span><span class="sxs-lookup"><span data-stu-id="6eba6-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="6eba6-148">Připojení zařízení přes USB do počítače a spusťte zařízení, ale nepokračujte za stránku **přizpůsobit** úvodním nastavením (první stránka s modrým polem).</span><span class="sxs-lookup"><span data-stu-id="6eba6-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="6eba6-149">Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** současně.</span><span class="sxs-lookup"><span data-stu-id="6eba6-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="6eba6-150">HoloLens se v průzkumníku souborů na počítači zobrazí jako zařízení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="6eba6-151">V Průzkumníku souborů přetáhněte zřizovací balíček (. ppkg) do úložiště zařízení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="6eba6-152">Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** na stránce **přizpůsobit** .</span><span class="sxs-lookup"><span data-stu-id="6eba6-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="6eba6-153">Zařízení vás vyzve, pokud zadáte důvěryhodný balíček a chcete ho použít.</span><span class="sxs-lookup"><span data-stu-id="6eba6-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="6eba6-154">Potvrďte, že balíček důvěřujete.</span><span class="sxs-lookup"><span data-stu-id="6eba6-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="6eba6-155">Zobrazí se informace o tom, zda byl balíček úspěšně použit, nebo nikoli.</span><span class="sxs-lookup"><span data-stu-id="6eba6-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="6eba6-156">Pokud se nezdařila, můžete balíček opravit a akci opakujte.</span><span class="sxs-lookup"><span data-stu-id="6eba6-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="6eba6-157">V případě úspěchu pokračujte v nastavení zařízení.</span><span class="sxs-lookup"><span data-stu-id="6eba6-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="6eba6-158">Pokud se zařízení nakoupilo před 2016. srpna, budete se muset k zařízení přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a potom obnovit operační systém, aby se zřizovací balíček mohl použít.</span><span class="sxs-lookup"><span data-stu-id="6eba6-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="6eba6-159">Ověření šifrování zařízení</span><span class="sxs-lookup"><span data-stu-id="6eba6-159">Verify device encryption</span></span>

<span data-ttu-id="6eba6-160">Šifrování je v HoloLens tiché.</span><span class="sxs-lookup"><span data-stu-id="6eba6-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="6eba6-161">Ověření stavu šifrování zařízení:</span><span class="sxs-lookup"><span data-stu-id="6eba6-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="6eba6-162">v HoloLens se o systému **Nastavení**  >  **systém**  >  .</span><span class="sxs-lookup"><span data-stu-id="6eba6-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="6eba6-163">**BitLocker** je **povolený** , pokud je zařízení zašifrované.</span><span class="sxs-lookup"><span data-stu-id="6eba6-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![O obrazovce s povoleným nástrojem BitLocker](images/about-encryption.png)
