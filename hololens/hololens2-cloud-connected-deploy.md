---
title: Průvodce nasazením – nasazení HoloLens 2 připojené ke cloudu ve velkém měřítku pomocí nástroje Remote Assist – nasazení
description: Zjistěte, jak ověřit registraci a vzdálenou pomoc pro zařízení HoloLens přes síť připojenou ke cloudu.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377696"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="49f0e-104">Nasazení – Průvodce připojeným ke cloudu</span><span class="sxs-lookup"><span data-stu-id="49f0e-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="49f0e-105">Teď, když máte všechno nakonfigurované, byste měli být připravení distribuovat zařízení.</span><span class="sxs-lookup"><span data-stu-id="49f0e-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="49f0e-106">Teď byste ale měli nastavení nejdřív ověřit.</span><span class="sxs-lookup"><span data-stu-id="49f0e-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="49f0e-107">Nejprve by se měl ověřit proces připojení k Azure AD a registrace MDM a pak ověřit, že je možné provést volání vzdálené pomoci.</span><span class="sxs-lookup"><span data-stu-id="49f0e-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="49f0e-108">Ověření registrace</span><span class="sxs-lookup"><span data-stu-id="49f0e-108">Enrollment Validation</span></span>

<span data-ttu-id="49f0e-109">Teď, když je všechno správně nakonfigurované pro azure AD a registraci MDM, by teď mělo být všechno v pořádku.</span><span class="sxs-lookup"><span data-stu-id="49f0e-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="49f0e-110">Budete&#39;připojení Wi-Fi zařízení HoloLens a také jeden z dříve nakonfigurovaných uživatelských účtů AAD.</span><span class="sxs-lookup"><span data-stu-id="49f0e-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="49f0e-111">Pokud zařízení není&#39;ve stavu továrního nastavení, je teď vhodné zařízení [namítt.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="49f0e-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="49f0e-112">Jakmile je zařízení v OOBE,&#39;začít pracovat a podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="49f0e-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="49f0e-113">Kritická výzva se zobrazí, když se zobrazí dotaz **Kdo je vlastnit tuto holoLens?**</span><span class="sxs-lookup"><span data-stu-id="49f0e-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="49f0e-114">Vyberte **Můj pracovní nebo školní účet vlastní a** zadejte své přihlašovací údaje k účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49f0e-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="49f0e-115">Po úspěšné registraci se&#39;výzva k nastavení kódu PIN.</span><span class="sxs-lookup"><span data-stu-id="49f0e-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="49f0e-116">Tento PIN kód je pro tohoto uživatele jedinečný pro toto zařízení.</span><span class="sxs-lookup"><span data-stu-id="49f0e-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="49f0e-117">Budete také vyzváni k zadání nastavení kontroly Iris, hlasových dat a telemetrie a nakonec&#39;se dozvíte, jak otevřít nabídku Start a dokončit OOBE.</span><span class="sxs-lookup"><span data-stu-id="49f0e-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="49f0e-118">Jakmile se vrátíte do Mixed Reality domovská stránka, otevřete nabídka Start pomocí gesta **Start,** které jste se právě naučili.</span><span class="sxs-lookup"><span data-stu-id="49f0e-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="49f0e-119">Vyberte aplikaci **Nastavení** a vyberte **Systém.**</span><span class="sxs-lookup"><span data-stu-id="49f0e-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="49f0e-120">První informace, kterou&#39;, je název vašeho zařízení, který pro zařízení HoloLens 2 bude HOLOLENS následovaný řetězcem se šesti &quot; &quot; znaky.</span><span class="sxs-lookup"><span data-stu-id="49f0e-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="49f0e-121">Poznamenejte si tento název.</span><span class="sxs-lookup"><span data-stu-id="49f0e-121">Take note of this name.</span></span>

![Nastavení HoloLens 2 – informace](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="49f0e-123">Můžete ověřit, že je vaše zařízení úspěšně zaregistrované v Azure AD v aplikaci Nastavení.</span><span class="sxs-lookup"><span data-stu-id="49f0e-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="49f0e-124">V **Nastavení vyberte** Účty **Přístup** do práce nebo do  ->  **školy.**</span><span class="sxs-lookup"><span data-stu-id="49f0e-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="49f0e-125">Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k názvu&#39;&quot; Azure AD. </span><span class="sxs-lookup"><span data-stu-id="49f0e-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="49f0e-126">Připojeno _pomocí vašeho_ @ _uživatelského jménanázevAAD_.onmicrosoft.com &quot; .</span><span class="sxs-lookup"><span data-stu-id="49f0e-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="49f0e-127">Abychom ověřili, že zařízení je připojené k Azure [](https://portal.azure.com/#home)AD, můžeme zkontrolovat Azure Active Directory v Azure Portal Azure Active Directory Zařízení Všechna zařízení a vyhledat  ->    ->    ->  název zařízení.</span><span class="sxs-lookup"><span data-stu-id="49f0e-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="49f0e-128">Můžete&#39;vidět, že zařízení je součástí Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49f0e-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory – zařízení](./images/aad-enrollment.png)

<span data-ttu-id="49f0e-130">Dále se&#39;přihlásit k Centru pro správu [Microsoftu Endpoint Manager správce.](https://endpoint.microsoft.com/#home)</span><span class="sxs-lookup"><span data-stu-id="49f0e-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="49f0e-131">Přihlaste se a **vyberte Zařízení a** pak Všechna **zařízení.**</span><span class="sxs-lookup"><span data-stu-id="49f0e-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="49f0e-132">Tady můžete vyhledat název zařízení HoloLens&#39;názvu.</span><span class="sxs-lookup"><span data-stu-id="49f0e-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="49f0e-133">Měli byste vidět holoLens uvedený v Intune.</span><span class="sxs-lookup"><span data-stu-id="49f0e-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune – zařízení](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="49f0e-135">Ověření volání vzdálené pomoci</span><span class="sxs-lookup"><span data-stu-id="49f0e-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="49f0e-136">Jakmile&#39;, že je zařízení zaregistrované v AAD i MDM, je&#39;k otestování volání vzdálené pomoci.</span><span class="sxs-lookup"><span data-stu-id="49f0e-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="49f0e-137">K tomuto ověření&#39;zařízení HoloLens a počítač Windows 10 a druhý uživatelský účet Azure AD pro počítač.</span><span class="sxs-lookup"><span data-stu-id="49f0e-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="49f0e-138">V tomto kroku ověření se předpokládá, že jste už dokončili poslední krok ověření a vaše zařízení je zaregistrované a uživatel Azure AD je na zařízení.</span><span class="sxs-lookup"><span data-stu-id="49f0e-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="49f0e-139">Pokud ještě nemáte na počítači nainstalovaný Microsoft Teams, můžete [Teams stáhnout tady.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)</span><span class="sxs-lookup"><span data-stu-id="49f0e-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="49f0e-140">Přihlaste se k Teams pomocí druhého uživatelského účtu Azure AD, který je aktuálně přihlášený k HoloLens.</span><span class="sxs-lookup"><span data-stu-id="49f0e-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="49f0e-141">Po přihlášení do počítače budete připraveni přijmout volání.</span><span class="sxs-lookup"><span data-stu-id="49f0e-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="49f0e-142">Odemkněte HoloLens a přihlaste se.</span><span class="sxs-lookup"><span data-stu-id="49f0e-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="49f0e-143">Aplikaci Remote Assist spustíte tak, že **otevřete nabídku Start** a vyberete **Vzdálená pomoc.**</span><span class="sxs-lookup"><span data-stu-id="49f0e-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="49f0e-144">Remote Assist je součástí nejen aplikace doručené pošty, ale také připnuté k holoLens 2&#39;nabídce Start.</span><span class="sxs-lookup"><span data-stu-id="49f0e-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="49f0e-145">V případě, že&#39;připnutá k nabídka Start, otevřete seznam Všechny aplikace **a** vyhledejte ho.</span><span class="sxs-lookup"><span data-stu-id="49f0e-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="49f0e-146">Jakmile remote assist spustí, měl by identifikovat uživatele zařízení prostřednictvím [jednotného přihlašování](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) a přihlásit se k aplikaci.</span><span class="sxs-lookup"><span data-stu-id="49f0e-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="49f0e-147">V aplikaci vyberte **Hledat** a vyhledejte druhého uživatele na počítači.</span><span class="sxs-lookup"><span data-stu-id="49f0e-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="49f0e-148">Výběrem uživatele zahájíte volání.</span><span class="sxs-lookup"><span data-stu-id="49f0e-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="49f0e-149">V počítači odpovězte na volání.</span><span class="sxs-lookup"><span data-stu-id="49f0e-149">From your PC, answer the call.</span></span>

<span data-ttu-id="49f0e-150">Blahopřejeme,&#39;jste se úspěšně připojili a jste na vzdáleném volání pomoci.</span><span class="sxs-lookup"><span data-stu-id="49f0e-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="49f0e-151">Nezapomeňte vyzkoušet konkrétní funkce vzdálené pomoci, například pomocí:</span><span class="sxs-lookup"><span data-stu-id="49f0e-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="49f0e-152">Inkování poznámek</span><span class="sxs-lookup"><span data-stu-id="49f0e-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="49f0e-153">Sdílení souboru a zobrazení ve smíšené realitě</span><span class="sxs-lookup"><span data-stu-id="49f0e-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="49f0e-154">Získání nápovědy v jiné aplikaci HoloLens</span><span class="sxs-lookup"><span data-stu-id="49f0e-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="49f0e-155">Další krok</span><span class="sxs-lookup"><span data-stu-id="49f0e-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="49f0e-156">Nasazení připojené ke cloudu – údržba</span><span class="sxs-lookup"><span data-stu-id="49f0e-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)