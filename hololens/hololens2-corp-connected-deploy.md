---
title: Průvodce nasazením – Příručky pro firemní HoloLens 2 s Dynamics 365 – nasazení
description: Zjistěte, jak nastavit nasazení zařízení HoloLens 2 přes podnikovou propojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, správa, firemní připojení, Průvodci Dynamics 365, AAD, Azure AD, MDM, Mobile Správa zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637060"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="3394a-104">Nasazení – Průvodce připojeným podnikem</span><span class="sxs-lookup"><span data-stu-id="3394a-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="3394a-105">Důležitou součástí každého nasazení je zajistit správné nastavení nasazení před tím, než ho sami otestujete, abyste zajistili bezproblémové prostředí pro koncového uživatele.</span><span class="sxs-lookup"><span data-stu-id="3394a-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="3394a-106">Vzhledem k tomu, že nasazujete certifikát Wi-Fi přes MDM, musíme nejprve nastavit HoloLens a zaregistrovat zařízení v otevřené síti Wi-Fi nebo v síti, která certifikát nevyžaduje.</span><span class="sxs-lookup"><span data-stu-id="3394a-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="3394a-107">Jakmile HoloLens oOBE a zaregistrovali, zařízení obdrží síťový certifikát a obchodní soubor nakonfigurovaný dříve a my budeme moct ověřit, že zařízení přijalo obojí.</span><span class="sxs-lookup"><span data-stu-id="3394a-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="3394a-108">Potom budete moct potvrdit, že můžete vytvořit a provozovat testovací příručku.</span><span class="sxs-lookup"><span data-stu-id="3394a-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="3394a-109">Ověření registrace</span><span class="sxs-lookup"><span data-stu-id="3394a-109">Enrollment Validation</span></span>

<span data-ttu-id="3394a-110">Teď, když je všechno správně nakonfigurované pro azure AD a registraci MDM, by teď mělo být všechno v pořádku.</span><span class="sxs-lookup"><span data-stu-id="3394a-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="3394a-111">Budete potřebovat připojení Wi-Fi a HoloLens zařízení a jeden z dříve nakonfigurovaných uživatelských účtů Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="3394a-112">Pokud zařízení aktuálně není ve stavu továrního nastavení, je teď vhodné ho [namítt.](/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="3394a-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="3394a-113">Jakmile bude zařízení v OOBE, budete muset začít pracovat a postupovat podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="3394a-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="3394a-114">Připojení k otevřené Wi-Fi, která nevyžaduje pro připojení k Wi-Fi certifikáty.</span><span class="sxs-lookup"><span data-stu-id="3394a-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="3394a-115">To umožní zařízení stáhnout certifikát, který se má po počátečním nastavení Wi-Fi v organizaci.</span><span class="sxs-lookup"><span data-stu-id="3394a-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="3394a-116">Kritická výzva se zobrazí, když se zobrazí **dotaz Kdo který tento HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="3394a-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="3394a-117">Vyberte **Můj pracovní nebo školní účet vlastní a** zadejte své přihlašovací údaje k účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="3394a-118">Po úspěšné registraci se zobrazí výzva k nastavení kódu PIN.</span><span class="sxs-lookup"><span data-stu-id="3394a-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="3394a-119">Tento PIN kód je pro tohoto uživatele jedinečný pro toto zařízení.</span><span class="sxs-lookup"><span data-stu-id="3394a-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="3394a-120">Budete také vyzváni k zadání nastavení kontroly Iris, hlasových dat a telemetrie a nakonec se dozvíte, jak otevřít nabídku Start a dokončit OOBE.</span><span class="sxs-lookup"><span data-stu-id="3394a-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="3394a-121">Jakmile se vrátíte na domovskou Mixed Reality, otevřete nabídka Start pomocí gesta **Start,** které jste se právě naučili.</span><span class="sxs-lookup"><span data-stu-id="3394a-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="3394a-122">Vyberte aplikaci **Nastavení** a vyberte **Systém.**</span><span class="sxs-lookup"><span data-stu-id="3394a-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="3394a-123">První informací, kterou uvidíte, je název vašeho zařízení, které pro vaše zařízení HoloLens 2 bude HOLOLENS– následované řetězcem se šesti &quot; &quot; znaky.</span><span class="sxs-lookup"><span data-stu-id="3394a-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="3394a-124">Poznamenejte si tento název.</span><span class="sxs-lookup"><span data-stu-id="3394a-124">Take note of this name.</span></span>

    ![HoloLens 2 Nastavení obrazovky](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="3394a-126">Ověřte, že je vaše zařízení úspěšně připojené k Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="3394a-127">Existují dva způsoby:</span><span class="sxs-lookup"><span data-stu-id="3394a-127">There are two ways;</span></span>

    1.  <span data-ttu-id="3394a-128">Aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="3394a-128">The Settings app.</span></span> <span data-ttu-id="3394a-129">V **Nastavení** vyberte Účty **Přístup** do práce nebo  ->  **do školy.**</span><span class="sxs-lookup"><span data-stu-id="3394a-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="3394a-130">Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k &quot;&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="3394a-131">Připojeno přes *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="3394a-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="3394a-132">Tím ověříte, že je vaše zařízení připojené k vaší organizaci&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="3394a-133">Na [Azure Portal](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="3394a-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="3394a-134">Přejděte na **Azure Active Directory** Zařízení Všechna zařízení a  ->    ->  vyhledejte název zařízení.</span><span class="sxs-lookup"><span data-stu-id="3394a-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="3394a-135">V části Typ spojení se zobrazí text Připojeno k Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="3394a-136">![Ověření typu připojení v Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="3394a-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="3394a-137">Ověřte, že je zařízení zaregistrované v MDM.</span><span class="sxs-lookup"><span data-stu-id="3394a-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="3394a-138">Existují dva způsoby:</span><span class="sxs-lookup"><span data-stu-id="3394a-138">There are two ways;</span></span>

    1. <span data-ttu-id="3394a-139">V **Nastavení** vyberte Účty **Přístup do** práce nebo do  ->  **školy.**</span><span class="sxs-lookup"><span data-stu-id="3394a-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="3394a-140">Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k &quot;&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="3394a-141">Připojeno přes *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="3394a-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="3394a-142">Z tohoto přístupového pracovního nebo školního účtu vyberte &quot; Připojeno k názvuAAD&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3394a-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="3394a-143">Připojeno yourusername@nameofAAD.onmicrosoft.com &quot; přes a vyberte **tlačítko** Informace.</span><span class="sxs-lookup"><span data-stu-id="3394a-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="3394a-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="3394a-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="3394a-145">Přihlaste se a **vyberte Zařízení a** pak Všechna **zařízení.**</span><span class="sxs-lookup"><span data-stu-id="3394a-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="3394a-146">Tady můžete prohledat název HoloLens&#39;zařízení.</span><span class="sxs-lookup"><span data-stu-id="3394a-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="3394a-147">Vaše aplikace by se měla zobrazit HoloLens v Intune.</span><span class="sxs-lookup"><span data-stu-id="3394a-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Ověření správy pomocí Intune v Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="3394a-149">Wi-Fi certifikátu</span><span class="sxs-lookup"><span data-stu-id="3394a-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="3394a-150">Zařízení by teď mělo mít přijatý Wi-Fi certifikát.</span><span class="sxs-lookup"><span data-stu-id="3394a-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="3394a-151">Nejjednodušším ověřením, které můžete provést, je pokus o připojení Wi-Fi, pro které jste&#39;obdrželi certifikát.</span><span class="sxs-lookup"><span data-stu-id="3394a-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="3394a-152">Otevřete aplikaci **Nastavení,** přejděte na **Síť &amp; Internet**  ->  **Wi-Fi** a vyberte připojení Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="3394a-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="3394a-153">Po připojení otevřete aplikaci Microsoft Edge a potvrďte, že můžete přejít na web.</span><span class="sxs-lookup"><span data-stu-id="3394a-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="3394a-154">Pokud chcete potvrdit, že jste certifikát obdrželi na zařízení, můžete použít [Správce certifikátů](/hololens/certificate-manager).</span><span class="sxs-lookup"><span data-stu-id="3394a-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="3394a-155">Ověření instalace obchodní aplikace</span><span class="sxs-lookup"><span data-stu-id="3394a-155">Validate LOB app install</span></span>

<span data-ttu-id="3394a-156">Pokud chcete zobrazit průběh instalace spravované aplikace, buď uvidíte, jestli je aplikace nainstalovaná, nebo zkontrolujte, jestli Nastavení.</span><span class="sxs-lookup"><span data-stu-id="3394a-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="3394a-157">Když obchodní aplikaci nakonfigurujete jako požadovanou instalaci pro naši skupinu, po registraci HoloLens s uživatelem v přiřazené skupině se aplikace automaticky stáhne do HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3394a-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="3394a-158">Otevřete nabídka Start a vyberte **Všechny aplikace**.</span><span class="sxs-lookup"><span data-stu-id="3394a-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="3394a-159">V závislosti na počtu aplikací možná budete muset  použít tlačítka pro zobrazení stránky nahoru nebo **dolů.**</span><span class="sxs-lookup"><span data-stu-id="3394a-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="3394a-160">Pokud chcete ověřit instalaci aplikace na zařízení, můžete to udělat přes přístup k účtům **Nastavení** do práce nebo do školy, vybrat účet, pak tlačítko Informace a posunout se dolů, abyste viděli různé konfigurace a aplikace použité pro zařízení z  ->    ->  MDM. </span><span class="sxs-lookup"><span data-stu-id="3394a-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="3394a-161">Pokud chcete ověřit instalaci z Intune, přejděte na stránku Stav instalace zařízení [MEM](https://endpoint.microsoft.com/#home)  ->  **Aplikace** -> Všechny   -> *aplikaceNázev_vašeho_zařízení_aplikace.*  ->  </span><span class="sxs-lookup"><span data-stu-id="3394a-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="3394a-162">Další informace: [Nasazení aplikací Intune pro HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="3394a-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="3394a-163">Ověření průvodců Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3394a-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="3394a-164">Existují režimy pro aplikaci Průvodci pro HoloLens, vytváření a provoz.</span><span class="sxs-lookup"><span data-stu-id="3394a-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="3394a-165">Před jeho provozováním budete muset dokončit průvodce vytvářením.</span><span class="sxs-lookup"><span data-stu-id="3394a-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="3394a-166">Vytváření příručky</span><span class="sxs-lookup"><span data-stu-id="3394a-166">Authoring the Guide</span></span>

<span data-ttu-id="3394a-167">Pro toto rychlé ověření toho moc dělat nemusíme.</span><span class="sxs-lookup"><span data-stu-id="3394a-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="3394a-168">Stačí vybrat průvodce, který jste připravili na svém počítači.</span><span class="sxs-lookup"><span data-stu-id="3394a-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="3394a-169">Kvůli rychlému ověření [budete muset](/dynamics365/mixed-reality/guides/hololens-app-anchor)průvodce ukotvit, abyste mohli použít holografické ukotvení.</span><span class="sxs-lookup"><span data-stu-id="3394a-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="3394a-170">Potom byste měli umístit [kroky a modely](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span><span class="sxs-lookup"><span data-stu-id="3394a-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="3394a-171">K přihlášení k **počítači a** vytváření na počítači budete potřebovat roli vytváření HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3394a-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="3394a-172">Role Operátor je jen pro čtení a nemá přístup k aplikaci pro počítače.</span><span class="sxs-lookup"><span data-stu-id="3394a-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="3394a-173">Použití příručky</span><span class="sxs-lookup"><span data-stu-id="3394a-173">Operating the Guide</span></span>

<span data-ttu-id="3394a-174">Jakmile jsou hologramy na místě, můžete otestovat provoz průvodce.</span><span class="sxs-lookup"><span data-stu-id="3394a-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="3394a-175">Výběr **režimu operátora**</span><span class="sxs-lookup"><span data-stu-id="3394a-175">Select **Operator mode**</span></span>
- <span data-ttu-id="3394a-176">Proklikejte se kroky průvodce.</span><span class="sxs-lookup"><span data-stu-id="3394a-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="3394a-177">Podrobnější pokyny k provozování průvodce najdete v těchto zdrojích informací:</span><span class="sxs-lookup"><span data-stu-id="3394a-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="3394a-178">Přehled provozu průvodce v příručkách Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3394a-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="3394a-179">Získejte orientaci na kartě Krok jako operátor v příručkách Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3394a-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="3394a-180">Další krok</span><span class="sxs-lookup"><span data-stu-id="3394a-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="3394a-181">Nasazení připojené k podnikové síti – údržba</span><span class="sxs-lookup"><span data-stu-id="3394a-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
