---
title: nastavení HoloLens 2
description: přečtěte si, jak nastavit HoloLens 2 při prvním používání Wi-Fi sítě pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636571"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="5a81f-104">nastavení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5a81f-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="5a81f-105">při prvním zapnutí HoloLens vás provedete nastavením zařízení, přihlášením pomocí uživatelského účtu a kalibrací HoloLens na oči.</span><span class="sxs-lookup"><span data-stu-id="5a81f-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="5a81f-106">v této části se seznámíte s úvodním prostředím HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a81f-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="5a81f-107">v další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy.</span><span class="sxs-lookup"><span data-stu-id="5a81f-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="5a81f-108">pokud chcete přejít k tomuto článku, přečtěte si téma [HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="5a81f-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5a81f-109">Než začnete</span><span class="sxs-lookup"><span data-stu-id="5a81f-109">Before you start</span></span>

<span data-ttu-id="5a81f-110">Než začnete, ujistěte se, že máte k dispozici následující:</span><span class="sxs-lookup"><span data-stu-id="5a81f-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="5a81f-111">**Připojení k síti**.</span><span class="sxs-lookup"><span data-stu-id="5a81f-111">**A network connection**.</span></span> <span data-ttu-id="5a81f-112">k jejímu nastavení budete muset připojit HoloLens k síti.</span><span class="sxs-lookup"><span data-stu-id="5a81f-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="5a81f-113">pomocí HoloLens 2 se můžete připojit pomocí Wi-Fi nebo přes síť ethernet (budete potřebovat adaptér USB-C-to-ethernet).</span><span class="sxs-lookup"><span data-stu-id="5a81f-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="5a81f-114">Při prvním připojení budete potřebovat otevřenou síť chráněnou heslem, která nevyžaduje navigaci na web nebo použití certifikátů k připojení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="5a81f-115">[přečtěte si další informace o webech, které HoloLens používá](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="5a81f-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="5a81f-116">**Účet Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5a81f-116">**A Microsoft account**.</span></span> <span data-ttu-id="5a81f-117">také se budete muset přihlásit k HoloLens pomocí účet Microsoft (nebo s pracovním účtem, pokud vaše organizace zařízení vlastní).</span><span class="sxs-lookup"><span data-stu-id="5a81f-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="5a81f-118">Pokud nemáte účet Microsoft, navštivte [account.Microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.</span><span class="sxs-lookup"><span data-stu-id="5a81f-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="5a81f-119">**Bezpečný a dobře osvětlený prostor bez Trip nebezpečí**.</span><span class="sxs-lookup"><span data-stu-id="5a81f-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="5a81f-120">[Stav a bezpečnostní údaje](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="5a81f-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="5a81f-121">**volitelná pomůcka pro pohodlí** , která byla dodávána s vaším HoloLens, aby vám pomohla lépe se přizpůsobit.</span><span class="sxs-lookup"><span data-stu-id="5a81f-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="5a81f-122">[Další informace o přizpůsobení a pohodlí](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="5a81f-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="5a81f-123">Instalace Windows</span><span class="sxs-lookup"><span data-stu-id="5a81f-123">Set up Windows</span></span>

<span data-ttu-id="5a81f-124">při prvním spuštění HoloLens 2 je prvním úkolem nastavit Windows holografický.</span><span class="sxs-lookup"><span data-stu-id="5a81f-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="5a81f-125">když začnete HoloLens, uslyšíte si hudbu a uvidíte logo Windows.</span><span class="sxs-lookup"><span data-stu-id="5a81f-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![První obrazovka při prvním spuštění](images/01-magic-moment.png)

<span data-ttu-id="5a81f-127">Zobrazí se Hummingbird kolem.</span><span class="sxs-lookup"><span data-stu-id="5a81f-127">You will see a hummingbird flying around.</span></span>

![Hummingbirdy plující za](images/hummingbird-1.png)

<span data-ttu-id="5a81f-129">Postupujte podle vašich rukou.</span><span class="sxs-lookup"><span data-stu-id="5a81f-129">Follow it with your hand.</span></span>

![Hummingbird s uzavřením](images/hummingbird-2.png)

<span data-ttu-id="5a81f-131">HoloLens 2 vás provede následujícími kroky:</span><span class="sxs-lookup"><span data-stu-id="5a81f-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="5a81f-132">Vyberte svůj jazyk.</span><span class="sxs-lookup"><span data-stu-id="5a81f-132">Select your language.</span></span>

    ![Vybrat jazyk](images/04-language.png)

1. <span data-ttu-id="5a81f-134">Vyberte oblast.</span><span class="sxs-lookup"><span data-stu-id="5a81f-134">Select your region.</span></span>

    ![Vybrat oblast](images/05-region.png)

1. <span data-ttu-id="5a81f-136">kalibrujte HoloLens své oči.</span><span class="sxs-lookup"><span data-stu-id="5a81f-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="5a81f-137">Pokud se rozhodnete přeskočit kalibraci, budete vyzváni k dalšímu přihlášení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="5a81f-138">Nejdřív upravíte své hypervisory.</span><span class="sxs-lookup"><span data-stu-id="5a81f-138">First, you'll adjust your visor.</span></span>
    
        ![Obrazovka pro výběr kalibrace](images/06-et-corners.png)

    2. <span data-ttu-id="5a81f-140">Kalibraci provedete tak, že se podíváte na sadu cílů (označovaných jako Gems).</span><span class="sxs-lookup"><span data-stu-id="5a81f-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="5a81f-141">Je to v pořádku, pokud během kalibrace bliká nebo blízko vaše oči, ale nemusíte je postarit na jiné objekty v místnosti nebo na fyzickém místě.</span><span class="sxs-lookup"><span data-stu-id="5a81f-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="5a81f-142">HoloLens tento proces využívá k tomu, abyste se dozvěděli o vaší poloze očí, aby mohl lépe vykreslovat svůj holografický svět.</span><span class="sxs-lookup"><span data-stu-id="5a81f-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Přizpůsobení pro oči](images/07-adjust-eyes.png)

        <span data-ttu-id="5a81f-144">Po kalibraci se hologramy zobrazí správně i v případě, že se hypervisory posunou na hlavu.</span><span class="sxs-lookup"><span data-stu-id="5a81f-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="5a81f-145">Informace o kalibraci jsou uloženy místně na zařízení a nejsou přidruženy k žádným informacím o účtu.</span><span class="sxs-lookup"><span data-stu-id="5a81f-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="5a81f-146">Další informace najdete v tématu [data kalibrace a zabezpečení](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="5a81f-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Kalibrace se dokončila.](images/calibration-complete.png)

1. <span data-ttu-id="5a81f-148">Připojení k internetu (vyberte Wi-Fi nebo připojení k síti ethernet).</span><span class="sxs-lookup"><span data-stu-id="5a81f-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="5a81f-149">HoloLens automaticky nastaví vaše časové pásmo na základě informací získaných z Wi-Fi sítě.</span><span class="sxs-lookup"><span data-stu-id="5a81f-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="5a81f-150">po dokončení instalace můžete časové pásmo změnit pomocí aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Připojení Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="5a81f-152">Pokud budete postupovat po Wi-Fim kroku a později potřebujete přepnout na jinou síť, ale stále v instalačním programu, můžete stisknutím tlačítka **hlasitosti dolů** a **napájení** přejít na tento krok, pokud používáte verzi operačního systému od října 2019 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="5a81f-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="5a81f-153">V případě starších verzí možná budete muset [zařízení resetovat](hololens-recovery.md) nebo restartovat v umístění, kde není dostupná síť Wi-Fi, aby se zabránilo automatickému připojení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="5a81f-154">všimněte si také, že během HoloLens nastavení je časový limit přihlašovacích údajů 2 minuty.</span><span class="sxs-lookup"><span data-stu-id="5a81f-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="5a81f-155">Uživatelské jméno nebo heslo je třeba zadat do dvou minut, jinak bude pole uživatelské jméno automaticky vymazáno.</span><span class="sxs-lookup"><span data-stu-id="5a81f-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="5a81f-156">pokud existuje HoloLens 2, bude vyhledávat a používat profil autopilotu.</span><span class="sxs-lookup"><span data-stu-id="5a81f-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="5a81f-157">Na této obrazovce není nutná žádná akce.</span><span class="sxs-lookup"><span data-stu-id="5a81f-157">No action is needed on this screen.</span></span>
 
    ![Hledání profilu autopilotu](images/autopilot-profile-search.png) 

1. <span data-ttu-id="5a81f-159">Na obrazovce licencování klikněte na **přijmout** .</span><span class="sxs-lookup"><span data-stu-id="5a81f-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows licenční smlouva](images/windows-license-agreement.png)

1. <span data-ttu-id="5a81f-161">Přihlaste se ke svému uživatelskému účtu.</span><span class="sxs-lookup"><span data-stu-id="5a81f-161">Sign in to your user account.</span></span> <span data-ttu-id="5a81f-162">Zvolíte si, že **se jedná o pracovní nebo školní vlastnictví** a **vlastní IT**.</span><span class="sxs-lookup"><span data-stu-id="5a81f-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![Nastavit uživatele](images/13-device-owner.png)
    - <span data-ttu-id="5a81f-164">Když zvolíte **Moje práce nebo škola**, přihlásíte se pomocí účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5a81f-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="5a81f-165">pokud vaše organizace používá Azure AD Premium a nakonfigurovali automatickou registraci MDM, HoloLens se automaticky zaregistrují v mdm.</span><span class="sxs-lookup"><span data-stu-id="5a81f-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="5a81f-166">pokud vaše organizace nepoužívá Azure AD Premium, automatický zápis MDM není k dispozici.</span><span class="sxs-lookup"><span data-stu-id="5a81f-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="5a81f-167">v takovém případě je třeba [ručně zaregistrovat HoloLens ve správě zařízení](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="5a81f-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="5a81f-168">Zadejte informace o účtu organizace.</span><span class="sxs-lookup"><span data-stu-id="5a81f-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="5a81f-169">Přijměte prohlášení o zásadách ochrany osobních údajů a licenční smlouvu s koncovým uživatelem.</span><span class="sxs-lookup"><span data-stu-id="5a81f-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="5a81f-170">Přihlaste se pomocí svých přihlašovacích údajů Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5a81f-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="5a81f-171">To se může přesměrovat na přihlašovací stránku vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="5a81f-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="5a81f-172">Pokračujte v nastavování zařízení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="5a81f-173">Když si vyberete **vlastní IT**, přihlásíte se účet Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a81f-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="5a81f-174">po dokončení instalace můžete [HoloLens ručně zaregistrovat do správy zařízení](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="5a81f-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="5a81f-175">Zadejte informace o účet Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a81f-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="5a81f-176">Zadejte svoje heslo.</span><span class="sxs-lookup"><span data-stu-id="5a81f-176">Enter your password.</span></span> <span data-ttu-id="5a81f-177">Pokud vaše účet Microsoft vyžaduje [dvoustupňové ověřování (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), dokončete proces ověření.</span><span class="sxs-lookup"><span data-stu-id="5a81f-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="5a81f-178">Nastavte přihlášení Iris výběrem možnosti **Další**.</span><span class="sxs-lookup"><span data-stu-id="5a81f-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="5a81f-179">Přes podobné prostředí se můžete setkat s kalibrací očí.</span><span class="sxs-lookup"><span data-stu-id="5a81f-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="5a81f-180">Až se kontrola dokončí, vyberte **Hotovo** .</span><span class="sxs-lookup"><span data-stu-id="5a81f-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="5a81f-181">Pokud chcete tento krok obejít, můžete taky vybrat **Přeskočit** .</span><span class="sxs-lookup"><span data-stu-id="5a81f-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="5a81f-182">![](images/setup-iris.png) ![ Dokončení instalačního programu Iris pro Iris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="5a81f-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="5a81f-183">Nastavíte PIN kód pro přihlášení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="5a81f-184">Tento kód PIN je specifický pro zařízení.</span><span class="sxs-lookup"><span data-stu-id="5a81f-184">This PIN is device specific.</span></span> 

    ![Instalační Windows Hello](images/setup-windows-hello.png)

    ![nastavit Windows Hello kód PIN](images/windows-hello-pin.png)

    ![Windows Hello Nastavení proběhlo úspěšně](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="5a81f-188">vyberte, jestli se má povolit rozpoznávání řeči na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a81f-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![Povolit Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="5a81f-190">vyberte, jestli se má povolit umístění na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a81f-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Povolit služby zjišťování polohy](images/setup-location-services.png)

1. <span data-ttu-id="5a81f-192">Vyberte úroveň telemetrie.</span><span class="sxs-lookup"><span data-stu-id="5a81f-192">Select your telemetry level.</span></span> <span data-ttu-id="5a81f-193">Pokud můžete, povolte prosím volitelnou telemetrii.</span><span class="sxs-lookup"><span data-stu-id="5a81f-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="5a81f-194">tyto informace skutečně pomáhají HoloLens technický tým.</span><span class="sxs-lookup"><span data-stu-id="5a81f-194">This information really helps the HoloLens engineering team.</span></span>

     ![Úroveň telemetrie](images/24-telemetry.png)

1. <span data-ttu-id="5a81f-196">naučte se používat počáteční gesto na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a81f-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Naučte se používat gesto Start, obrázek 1.](images/26-01-startmenu-learning.png)

     ![Naučte se používat gesto Start, obrázek 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="5a81f-199">Gratulujeme!</span><span class="sxs-lookup"><span data-stu-id="5a81f-199">Congratulations!</span></span>  <span data-ttu-id="5a81f-200">Instalace je hotová a Vy jste připraveni použít HoloLens!</span><span class="sxs-lookup"><span data-stu-id="5a81f-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a81f-201">Další kroky</span><span class="sxs-lookup"><span data-stu-id="5a81f-201">Next steps</span></span>

1. <span data-ttu-id="5a81f-202">Začněte ihned pracovat s Mixed Reality a procházením Windows 10 na HoloLens – podívejte se na aplikaci **Tipy,** ve které se můžete podívat na návody k interakcím pomocí rukou.</span><span class="sxs-lookup"><span data-stu-id="5a81f-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="5a81f-203">Pomocí gesta spuštění přejděte na Start nebo řekněte "Přejít na start" a vyberte Tipy.</span><span class="sxs-lookup"><span data-stu-id="5a81f-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="5a81f-204">Klikněte níže a pokračujte ve čtení o tom, jak se dostat HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5a81f-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5a81f-205">Práce s HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5a81f-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
