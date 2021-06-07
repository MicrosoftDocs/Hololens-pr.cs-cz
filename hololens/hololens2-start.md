---
title: Nastavení HoloLens 2
description: Zjistěte, jak poprvé nastavit HoloLens 2 v síti Wi-Fi pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379290"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="03c58-104">Nastavení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="03c58-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="03c58-105">Při prvním zapnutí HoloLens vás provede nastavením zařízení, přihlášením pomocí uživatelského účtu a zkalibrací HoloLensu do očí.</span><span class="sxs-lookup"><span data-stu-id="03c58-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="03c58-106">Tato část vás provede počátečním nastavením HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="03c58-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="03c58-107">V další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy.</span><span class="sxs-lookup"><span data-stu-id="03c58-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="03c58-108">Pokud chcete přeskočit na tento článek, podívejte se na článek [Začínáme s HoloLens 2.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="03c58-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="03c58-109">Než začnete</span><span class="sxs-lookup"><span data-stu-id="03c58-109">Before you start</span></span>

<span data-ttu-id="03c58-110">Než začnete, ujistěte se, že máte k dispozici následující:</span><span class="sxs-lookup"><span data-stu-id="03c58-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="03c58-111">**Síťové připojení**.</span><span class="sxs-lookup"><span data-stu-id="03c58-111">**A network connection**.</span></span> <span data-ttu-id="03c58-112">Abyste ho nastavili, budete muset holoLens připojit k síti.</span><span class="sxs-lookup"><span data-stu-id="03c58-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="03c58-113">S HoloLens 2 se můžete připojit k Wi-Fi nebo pomocí ethernetu (budete potřebovat adaptér USB-C-to-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="03c58-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="03c58-114">Při prvním připojení budete potřebovat otevřenou síť nebo síť chráněnou heslem, která nevyžaduje přechod na web ani používání certifikátů pro připojení.</span><span class="sxs-lookup"><span data-stu-id="03c58-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="03c58-115">[Přečtěte si další informace o webech, které HoloLens používá.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="03c58-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="03c58-116">**A účet Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="03c58-116">**A Microsoft account**.</span></span> <span data-ttu-id="03c58-117">Budete se také muset přihlásit k HoloLens pomocí účet Microsoft (nebo pomocí pracovního účtu, pokud vaše organizace vlastní zařízení).</span><span class="sxs-lookup"><span data-stu-id="03c58-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="03c58-118">Pokud nemáte vlastní účet Microsoft, přejděte na [account.microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.</span><span class="sxs-lookup"><span data-stu-id="03c58-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="03c58-119">**Bezpečný a dobře rozsvícený prostor bez nebezpečí při vyjetí.**</span><span class="sxs-lookup"><span data-stu-id="03c58-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="03c58-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="03c58-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="03c58-121">**Volitelné příslušenství pro komfort,** které se dodá s holoLens, vám pomůže s co nejpohodlnějším fitem.</span><span class="sxs-lookup"><span data-stu-id="03c58-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="03c58-122">[Další informace o fitu a komfortu.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="03c58-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="03c58-123">Instalace Windows</span><span class="sxs-lookup"><span data-stu-id="03c58-123">Set up Windows</span></span>

<span data-ttu-id="03c58-124">Při prvním spuštění HoloLens 2 je vaším prvním úkolem nastavit Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="03c58-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="03c58-125">Když spustíte HoloLens, uslyšíte hudbu a uvidíte logo Windows.</span><span class="sxs-lookup"><span data-stu-id="03c58-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![První obrazovka při prvním spuštění](images/01-magic-moment.png)

<span data-ttu-id="03c58-127">HoloLens 2 vás provede následujícími kroky:</span><span class="sxs-lookup"><span data-stu-id="03c58-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="03c58-128">Vyberte svůj jazyk.</span><span class="sxs-lookup"><span data-stu-id="03c58-128">Select your language.</span></span>

    ![Výběr jazyka](images/04-language.png)

1. <span data-ttu-id="03c58-130">Vyberte svou oblast.</span><span class="sxs-lookup"><span data-stu-id="03c58-130">Select your region.</span></span>

    ![Výběr oblasti](images/05-region.png)

1. <span data-ttu-id="03c58-132">Nakalibrovat HoloLens do očí.</span><span class="sxs-lookup"><span data-stu-id="03c58-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="03c58-133">Pokud se rozhodnete přeskočit přeskočení, při příštím přihlášení se zobrazí výzva.</span><span class="sxs-lookup"><span data-stu-id="03c58-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="03c58-134">Při nakalibrování se podíváte na sadu cílů (označované jako gemy).</span><span class="sxs-lookup"><span data-stu-id="03c58-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="03c58-135">Je v pořádku, když během chouly blikne nebo zavřete oči, ale snažte se nekoukat na jiné objekty v místnosti nebo fyzickém prostoru.</span><span class="sxs-lookup"><span data-stu-id="03c58-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="03c58-136">HoloLens tento proces používá k tomu, aby se dozvěděl o pozici oka, aby mohl lépe vykreslit holografický svět.</span><span class="sxs-lookup"><span data-stu-id="03c58-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="03c58-137">Po dokončení se hologramy zobrazí správně, i když se visor posune na vaší hlavy.</span><span class="sxs-lookup"><span data-stu-id="03c58-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="03c58-138">Informace o výuce se ukládají místně v zařízení a nejsou přidružené k žádným informacím o účtu.</span><span class="sxs-lookup"><span data-stu-id="03c58-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="03c58-139">Další informace najdete v tématu [o ochraně osobních údajů a zabezpečení.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="03c58-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Obrazovka pro výběr nahody](images/06-et-corners.png)

1. <span data-ttu-id="03c58-141">Připojte se k internetu (vyberte Wi-Fi nebo ethernetové připojení).</span><span class="sxs-lookup"><span data-stu-id="03c58-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="03c58-142">HoloLens nastaví časové pásmo automaticky na základě informací získaných z Wi-Fi sítě.</span><span class="sxs-lookup"><span data-stu-id="03c58-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="03c58-143">Po dokončení nastavení můžete časové pásmo změnit pomocí aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="03c58-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Připojení k Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="03c58-145">Pokud postupíte po kroku Wi-Fi a později budete muset přepnout na jinou síť, zatímco  jste stále v nastavení, můžete se k tomuto kroku vrátit stisknutím tlačítek Snížení objemu a napájení současně, pokud používáte verzi operačního systému z října 2019 nebo novější. </span><span class="sxs-lookup"><span data-stu-id="03c58-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="03c58-146">U starších verzí možná [](hololens-recovery.md) budete muset resetovat zařízení nebo ho restartovat v umístění, kde není dostupná síť Wi-Fi, aby se zabránilo jeho automatickému připojení.</span><span class="sxs-lookup"><span data-stu-id="03c58-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="03c58-147">Všimněte si také, že během instalace HoloLens došlo k časovému limitu přihlašovacích údajů dvou minut.</span><span class="sxs-lookup"><span data-stu-id="03c58-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="03c58-148">Uživatelské jméno a heslo je potřeba zadat do dvou minut, jinak se pole uživatelského jména automaticky vyškrtne.</span><span class="sxs-lookup"><span data-stu-id="03c58-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="03c58-149">Přihlaste se ke svému uživatelskému účtu.</span><span class="sxs-lookup"><span data-stu-id="03c58-149">Sign in to your user account.</span></span> <span data-ttu-id="03c58-150">Zvolíte si, jestli je můj **pracovní nebo** školní vlastnit a já **ho vlastním.**</span><span class="sxs-lookup"><span data-stu-id="03c58-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="03c58-151">Když zvolíte **Možnost Můj pracovní nebo školní účet** vlastní , přihlásíte se pomocí účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="03c58-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="03c58-152">Pokud vaše organizace používá Azure AD Premium a nakonfiguroval automatickou registraci MDM, HoloLens se do MDM automaticky zaregistruje.</span><span class="sxs-lookup"><span data-stu-id="03c58-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="03c58-153">Pokud vaše organizace tuto funkci Azure AD Premium, automatická registrace MDM není dostupná.</span><span class="sxs-lookup"><span data-stu-id="03c58-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="03c58-154">V takovém případě musíte [holoLens](hololens-enroll-mdm.md#different-ways-to-enroll)zaregistrovat ručně ve správě zařízení.</span><span class="sxs-lookup"><span data-stu-id="03c58-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="03c58-155">Zadejte informace o účtu organizace.</span><span class="sxs-lookup"><span data-stu-id="03c58-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="03c58-156">Přijměte prohlášení o zásadách ochrany osobních údajů a licenční smlouvu s koncovým uživatelem.</span><span class="sxs-lookup"><span data-stu-id="03c58-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="03c58-157">Přihlaste se pomocí svých přihlašovacích údajů azure AD.</span><span class="sxs-lookup"><span data-stu-id="03c58-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="03c58-158">To se může přesměrovat na přihlašovací stránku vaší organizace.</span><span class="sxs-lookup"><span data-stu-id="03c58-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="03c58-159">Pokračujte v nastavování zařízení.</span><span class="sxs-lookup"><span data-stu-id="03c58-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="03c58-160">Když zvolíte **Možnost vlastnit**, přihlásíte se pomocí účet Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03c58-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="03c58-161">Po dokončení instalace můžete [holoLens](hololens-enroll-mdm.md#different-ways-to-enroll)zaregistrovat do správy zařízení ručně.</span><span class="sxs-lookup"><span data-stu-id="03c58-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="03c58-162">Zadejte své účet Microsoft údaje.</span><span class="sxs-lookup"><span data-stu-id="03c58-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="03c58-163">Zadejte svoje heslo.</span><span class="sxs-lookup"><span data-stu-id="03c58-163">Enter your password.</span></span> <span data-ttu-id="03c58-164">Pokud váš účet Microsoft vyžaduje [dvoukrokové ověřování ,](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)dokončete proces ověřování.</span><span class="sxs-lookup"><span data-stu-id="03c58-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Nastavení uživatele](images/13-device-owner.png)

1. <span data-ttu-id="03c58-166">Vyberte, jestli se má na HoloLens 2 povolit řeč a jestli se má odesílat diagnostická telemetrie.</span><span class="sxs-lookup"><span data-stu-id="03c58-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Povolení Cortany](images/22-do-more-with-voice.png)

1. <span data-ttu-id="03c58-168">Vyberte úroveň telemetrie.</span><span class="sxs-lookup"><span data-stu-id="03c58-168">Select your telemetry level.</span></span> <span data-ttu-id="03c58-169">Pokud můžete, povolte úplnou telemetrii.</span><span class="sxs-lookup"><span data-stu-id="03c58-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="03c58-170">Tyto informace ve skutečnosti pomáhají technickém týmu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03c58-170">This information really helps the HoloLens engineering team.</span></span>

     ![Úroveň telemetrie](images/24-telemetry.png)

1. <span data-ttu-id="03c58-172">Naučte se používat gesto spuštění na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="03c58-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="03c58-173">![Naučte se používat gesto spuštění, obrázek 1 Naučte se používat gesto ](images/26-01-startmenu-learning.png) ![ spuštění, obrázek 2](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="03c58-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="03c58-174">Gratulujeme!</span><span class="sxs-lookup"><span data-stu-id="03c58-174">Congratulations!</span></span>  <span data-ttu-id="03c58-175">Nastavení je hotové a jste připraveni k použití HoloLens!</span><span class="sxs-lookup"><span data-stu-id="03c58-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="03c58-176">Další kroky</span><span class="sxs-lookup"><span data-stu-id="03c58-176">Next steps</span></span>

1. <span data-ttu-id="03c58-177">Začněte ihned pracovat s Mixed Reality a procházením Windows 10 holoLens – podívejte se  na aplikaci Tipy, ve které najdete návody k interakcím pomocí rukou.</span><span class="sxs-lookup"><span data-stu-id="03c58-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="03c58-178">Pomocí gesta spuštění přejděte na Start nebo řekněte "Přejít na start" a vyberte Tipy.</span><span class="sxs-lookup"><span data-stu-id="03c58-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="03c58-179">Klikněte níže a pokračujte ve čtení o použití HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="03c58-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="03c58-180">Začínáme s HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="03c58-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
