---
title: Vyhledání, instalace a odinstalace aplikací
description: Tento Microsoft Store je vaším zdrojem pro aplikace a hry, které pracují s HoloLens.  Přečtěte si další informace o hledání, instalaci a odinstalaci holografických aplikací.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379211"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="c1198-105">Vyhledání, instalace a odinstalace aplikací z Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c1198-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="c1198-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c1198-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="c1198-107">Když na HoloLens půjdete do Storu, spustí se na ní všechny aplikace, které tam vidíte.</span><span class="sxs-lookup"><span data-stu-id="c1198-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="c1198-108">Aplikace na HoloLens používají 2D zobrazení nebo holografické zobrazení.</span><span class="sxs-lookup"><span data-stu-id="c1198-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="c1198-109">Aplikace, které používají 2D zobrazení, vypadají jako okna a můžete je umístit kolem sebe.</span><span class="sxs-lookup"><span data-stu-id="c1198-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="c1198-110">Aplikace, které používají holografické zobrazení, vás obklopují a stanou se jedinou aplikací, kterou vidíte.</span><span class="sxs-lookup"><span data-stu-id="c1198-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="c1198-111">HoloLens podporuje mnoho existujících aplikací z Microsoft Store a nové aplikace vytvořené speciálně pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c1198-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="c1198-112">Tento článek se zaměřuje na holografické aplikace z Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="c1198-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="c1198-113">Další informace o instalaci a spouštění vlastních aplikací najdete v tématu [Vlastní holografické aplikace.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="c1198-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="c1198-114">Hledání aplikací</span><span class="sxs-lookup"><span data-stu-id="c1198-114">Find apps</span></span>

<span data-ttu-id="c1198-115">Otevřete Microsoft Store z nabídky **Start.**</span><span class="sxs-lookup"><span data-stu-id="c1198-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="c1198-116">Pak vyhledejte aplikace a hry.</span><span class="sxs-lookup"><span data-stu-id="c1198-116">Then browse for apps and games.</span></span> <span data-ttu-id="c1198-117">Hlasové příkazy [můžete](hololens-cortana.md) použít k vyhledávání tak, že řeknete "Hledat", jakmile se otevře okno hledání, které řekne "Start dictating" (Začít diktovat) a po zobrazení výzvy začne hledaný výraz říkat.</span><span class="sxs-lookup"><span data-stu-id="c1198-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="c1198-118">Požadavky na systém pro zařízení HoloLens jsou založené na architektuře sestavení aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="c1198-119">Pokud nebylo sestavení aplikace pro HoloLens (1. generace) aktualizováno na novější UPW ve Storu, aby zahrnovalo balíček architektury ARM, nebude dostupné pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c1198-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="c1198-120">Podobně platí, že pokud aplikace HoloLens 2 neobsahuje balíček architektury x86, nebude k dispozici pro zařízení HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="c1198-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="c1198-121">Architektury zařízení HoloLens:</span><span class="sxs-lookup"><span data-stu-id="c1198-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="c1198-122">x86 = HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="c1198-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="c1198-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c1198-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="c1198-124">12. ledna 2021 se ke konci podpory na zařízeních HoloLens dostanou následující aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="c1198-125">Pokud chcete používat webovou verzi aplikace, doporučujeme na svém zařízení použít následující odkaz.</span><span class="sxs-lookup"><span data-stu-id="c1198-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="c1198-126">Aplikace</span><span class="sxs-lookup"><span data-stu-id="c1198-126">App</span></span>        | <span data-ttu-id="c1198-127">Odkaz</span><span class="sxs-lookup"><span data-stu-id="c1198-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="c1198-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="c1198-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="c1198-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="c1198-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="c1198-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="c1198-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="c1198-131">Instalace aplikací</span><span class="sxs-lookup"><span data-stu-id="c1198-131">Install apps</span></span>

<span data-ttu-id="c1198-132">Pokud si chcete stáhnout aplikace, musíte být přihlášeni pomocí účet Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1198-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="c1198-133">Některé aplikace jsou zdarma a můžete si je hned stáhnout.</span><span class="sxs-lookup"><span data-stu-id="c1198-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="c1198-134">U aplikací, které vyžadují nákup, musíte být přihlášeni ke Storu pomocí účet Microsoft a mít platný způsob platby.</span><span class="sxs-lookup"><span data-stu-id="c1198-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="c1198-135">Účet, který používáte Microsoft Store, nemusí být stejný jako účet, pod nímž jste přihlášení.</span><span class="sxs-lookup"><span data-stu-id="c1198-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="c1198-136">Pokud na holoLens používáte pracovní nebo školní účet, možná se budete muset přihlásit pomocí svého osobního účtu v aplikaci pro Store a provést nákup.</span><span class="sxs-lookup"><span data-stu-id="c1198-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="c1198-137">Pokud chcete nastavit způsob platby, přejděte do části [account.microsoft.com](https://account.microsoft.com/) vyberte **Payment & billing Payment**  >  **options**  >  **(Způsoby platby) Add a payment option**(Přidat způsob platby).</span><span class="sxs-lookup"><span data-stu-id="c1198-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="c1198-138">Pokud chcete otevřít [ **nabídku Start,**](holographic-home.md)proveďte [na](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) HoloLens (1. generace) gesto Start (Spustit gest) nebo [bloom](hololens1-basic-usage.md) (rozkvět).</span><span class="sxs-lookup"><span data-stu-id="c1198-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="c1198-139">Vyberte aplikaci Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="c1198-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="c1198-140">Po otevření aplikace pro Store:</span><span class="sxs-lookup"><span data-stu-id="c1198-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="c1198-141">Pomocí panelu hledání vyhledejte aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="c1198-142">Vyberte základní aplikace nebo aplikace speciálně pro HoloLens z jedné z kurátorovaných kategorií.</span><span class="sxs-lookup"><span data-stu-id="c1198-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="c1198-143">V pravém horním rohu aplikace pro Store vyberte **tlačítko "..."** a pak vyberte **Moje** knihovna. Zobrazí se všechny dříve zakoupené aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="c1198-144">Na  stránce **aplikace** vyberte Získat nebo Nainstalovat (může být nutné koupit).</span><span class="sxs-lookup"><span data-stu-id="c1198-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="c1198-145">Aktualizace aplikací</span><span class="sxs-lookup"><span data-stu-id="c1198-145">Update Apps</span></span>

<span data-ttu-id="c1198-146">Pokud chcete aktualizovat aplikaci, kterou jste nainstalovali z Microsoft Store, můžete ji aktualizovat z Microsoft Store aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="c1198-147">U aplikací nainstalovaných pro Microsoft Store pro firmy můžete tyto aplikace také aktualizovat z Microsoft Store pro firmy.</span><span class="sxs-lookup"><span data-stu-id="c1198-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="c1198-148">Pokud chcete otevřít [ **nabídku Start,**](holographic-home.md)proveďte [na](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) HoloLens (1. generace) gesto Start (Spustit gest) nebo [bloom](hololens1-basic-usage.md) (rozkvět).</span><span class="sxs-lookup"><span data-stu-id="c1198-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="c1198-149">Vyberte aplikaci pro Store.</span><span class="sxs-lookup"><span data-stu-id="c1198-149">Select the Store app.</span></span>

1. <span data-ttu-id="c1198-150">Podívejte se do pravého horního rohu aplikace Store.</span><span class="sxs-lookup"><span data-stu-id="c1198-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="c1198-151">Vyberte **tlačítko "..."** nebo "Zobrazit další".</span><span class="sxs-lookup"><span data-stu-id="c1198-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1198-152">![Microsoft Store snímku obrazovky aplikace](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="c1198-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="c1198-153">Vyberte **Položky ke stažení a aktualizace.**</span><span class="sxs-lookup"><span data-stu-id="c1198-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="c1198-154">Pokud zařízení dříve identifikovalo aktualizace, může se zobrazit šipka dolů a číslo, které představuje čekající aktualizace.</span><span class="sxs-lookup"><span data-stu-id="c1198-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="c1198-155">Vyberte **Získat aktualizace.**</span><span class="sxs-lookup"><span data-stu-id="c1198-155">Select **Get updates**.</span></span> <span data-ttu-id="c1198-156">Vaše zařízení teď bude hledat aktualizace a nastavovat je tak, aby se stáhly a instalují.</span><span class="sxs-lookup"><span data-stu-id="c1198-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c1198-157">![Microsoft Store snímku obrazovky aplikace se získáním aktualizací.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="c1198-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="c1198-158">Pokud vaše organizace distribuuje aplikace na vašem zařízení, můžete je aktualizovat stejnými komerčními metodami správy aplikací.</span><span class="sxs-lookup"><span data-stu-id="c1198-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="c1198-159">Pokud to platí pro vaši situaci, přečtěte si další informace v [přehledu nasazení komerčních aplikací.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1198-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="c1198-160">Pokud chcete aktualizovat vlastní aplikaci, která se nasadila bokem nebo bokem, budete muset použít stejnou metodu s aktualizovanou verzí aplikace.</span><span class="sxs-lookup"><span data-stu-id="c1198-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="c1198-161">Další informace o instalaci a spouštění vlastních aplikací najdete v tématu [o vlastních holografických aplikacích.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="c1198-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="c1198-162">Odinstalovat aplikace</span><span class="sxs-lookup"><span data-stu-id="c1198-162">Uninstall apps</span></span>

<span data-ttu-id="c1198-163">Existují tři způsoby odinstalace aplikací.</span><span class="sxs-lookup"><span data-stu-id="c1198-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="c1198-164">Aplikace můžete odinstalovat prostřednictvím Microsoft Store, nabídka Start nebo z Nastavení.</span><span class="sxs-lookup"><span data-stu-id="c1198-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="c1198-165">Systémovou aplikaci ani samotnou aplikaci Microsoft Store odinstalovat.</span><span class="sxs-lookup"><span data-stu-id="c1198-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1198-166">Pokud holoLens 2 obsahuje více uživatelů, musíte být přihlášeni jako uživatel, který aplikaci nainstaloval, abyste ji odinstaloval.</span><span class="sxs-lookup"><span data-stu-id="c1198-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="c1198-167">Odinstalace z Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c1198-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="c1198-168">V Microsoft Store Start otevřete **soubor a** vyhledejte aplikaci, kterou chcete odinstalovat.</span><span class="sxs-lookup"><span data-stu-id="c1198-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="c1198-169">Na stránce Store má každá nainstalovaná aplikace **tlačítko Odinstalovat.**</span><span class="sxs-lookup"><span data-stu-id="c1198-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="c1198-170">Odinstalace z nabídka Start</span><span class="sxs-lookup"><span data-stu-id="c1198-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="c1198-171">V **nabídce Start** nebo v **Všechny aplikace** přejděte k aplikaci.</span><span class="sxs-lookup"><span data-stu-id="c1198-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="c1198-172">Vyberte a podržte, dokud se nezobrazí nabídka, a pak vyberte **Odinstalovat.**</span><span class="sxs-lookup"><span data-stu-id="c1198-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="c1198-173">Odinstalace z nastavení</span><span class="sxs-lookup"><span data-stu-id="c1198-173">Uninstall from Settings</span></span>
<span data-ttu-id="c1198-174">V **nabídce Start** vyberte **Nastavení -> Aplikace.**</span><span class="sxs-lookup"><span data-stu-id="c1198-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="c1198-175">Vyhledejte aplikaci ze seznamu, vyberte ji a pak klikněte na **Odinstalovat.**</span><span class="sxs-lookup"><span data-stu-id="c1198-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="c1198-176">Pokud nemůžete odinstalovat aplikaci, zpětnou vazbu nahlaste [pomocí](https://docs.microsoft.com/hololens/hololens-feedback) Centrum Feedback.</span><span class="sxs-lookup"><span data-stu-id="c1198-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
