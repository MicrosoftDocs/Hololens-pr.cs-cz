---
title: Aktualizace HoloLens 2
description: Naučte se kontrolovat číslo sestavení HoloLens, udržovat aktuální informace o aktualizacích zařízení, zapojit se do programu Insiders a vracet aktualizace.
keywords: postupy, aktualizace, vrácení zpět, HoloLens, ověření sestavení, číslo sestavení
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924107"
---
# <a name="update-hololens-2"></a><span data-ttu-id="8ccb3-104">Aktualizace HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8ccb3-104">Update HoloLens 2</span></span>

<span data-ttu-id="8ccb3-105">HoloLens používá web Windows Update stejně jako jiná zařízení s Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="8ccb3-106">Vaše HoloLens automaticky stáhne a nainstaluje aktualizace systému, kdykoli se připojí k Internetu, a to i v případě, že je v pohotovostním režimu.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="8ccb3-107">Tento článek vás provede nástroji HoloLens pro:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="8ccb3-108">zobrazení aktuální verze operačního systému (číslo sestavení)</span><span class="sxs-lookup"><span data-stu-id="8ccb3-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="8ccb3-109">hledají se aktualizace.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-109">checking for updates</span></span>
- <span data-ttu-id="8ccb3-110">Ruční aktualizace HoloLens</span><span class="sxs-lookup"><span data-stu-id="8ccb3-110">manually updating HoloLens</span></span>
- <span data-ttu-id="8ccb3-111">vrácení zpět se starší aktualizací</span><span class="sxs-lookup"><span data-stu-id="8ccb3-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="8ccb3-112">Ověřit verzi operačního systému (číslo sestavení)</span><span class="sxs-lookup"><span data-stu-id="8ccb3-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="8ccb3-113">Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete aplikaci nastavení a vyberete **systém**  >  .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="8ccb3-114">Vyhledat aktualizace a ručně aktualizovat</span><span class="sxs-lookup"><span data-stu-id="8ccb3-114">Check for updates and manually update</span></span>

<span data-ttu-id="8ccb3-115">Aktualizace můžete vyhledat kdykoli v nastavení.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="8ccb3-116">Chcete-li zobrazit dostupné aktualizace a vyhledat nové aktualizace:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="8ccb3-117">Otevřete aplikaci **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="8ccb3-118">Přejděte k **aktualizaci web Windows Update zabezpečení &**  >  .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="8ccb3-119">Vyberte **Vyhledat aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-119">Select **Check for updates**.</span></span>

<span data-ttu-id="8ccb3-120">Pokud je k dispozici aktualizace, začne se stahovat nová verze.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="8ccb3-121">Po dokončení stahování spusťte instalaci kliknutím na tlačítko **restartovat** .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="8ccb3-122">Pokud je vaše zařízení pod 40% a není napájené z elektrické sítě, při restartování se nespustí instalace aktualizace.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="8ccb3-123">I když váš HoloLens instaluje aktualizaci, zobrazí se ozubené kolečka a indikátor průběhu.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="8ccb3-124">Během této doby nepínejte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="8ccb3-125">Po dokončení instalace se automaticky restartuje.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="8ccb3-126">HoloLens používá vždy jednu aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="8ccb3-127">Pokud máte více než jednu verzi, kterou máte v poslední době, možná budete muset projít proces aktualizace několikrát, abyste ho mohli plně aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="8ccb3-128">Přejít zpět na předchozí verzi</span><span class="sxs-lookup"><span data-stu-id="8ccb3-128">Go back to a previous version</span></span>

<span data-ttu-id="8ccb3-129">V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8ccb3-130">Doporučené kroky jsou tyto:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-130">The recommended steps are:</span></span>

1. <span data-ttu-id="8ccb3-131">Pokud chcete zjistit, jestli můžou problém vyřešit, obraťte se na podporu.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="8ccb3-132">Zajistěte, aby byla povolená **volitelná** nebo **plná** telemetrie – díky tomu je vaše chyba více užitečná a snazší pro inženýry diagnostikovat.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="8ccb3-133">[Zpětná vazba](hololens-feedback.md) je co nejsrozumitelnější.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="8ccb3-134">Poznamenejte si název nebo použijte funkci sdílení, abyste mohli svoji chybu sdílet s podporou.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="8ccb3-135">Obraťte se na [podporu](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="8ccb3-136">Pokud je váš problém takový, který je potřeba vyřešit vrácením do předchozí verze, může vám dodávat FFU k tomu, aby vaše zařízení bylo možné zablikat.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="8ccb3-137">Pokud to nefunguje, [resetujte nebo znovu zablikají svůj HoloLens 2 s pokročilým pomocníkem pro obnovení](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="8ccb3-138">V počítači si stáhněte z Microsoft Store [Průvodce rozšířeným obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="8ccb3-139">Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="8ccb3-140">Vyberte verzi, kterou chcete zablikat:</span><span class="sxs-lookup"><span data-stu-id="8ccb3-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="8ccb3-141">Můžete si stáhnout nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="8ccb3-142">Můžete použít výchozí sestavení, které jsou hostiteli ARC.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="8ccb3-143">(Pokud zvolíte tuto možnost, přejděte k dalšímu kroku.)</span><span class="sxs-lookup"><span data-stu-id="8ccb3-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="8ccb3-144">Můžete použít podporu sestavení, která vám poskytne.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="8ccb3-145">Po dokončení těchto souborů ke stažení otevřete **Průzkumníka souborů**  >  .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="8ccb3-146">Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="8ccb3-147">Připojte HoloLens k počítači pomocí USB-A k kabelu USB-C.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="8ccb3-148">(I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)</span><span class="sxs-lookup"><span data-stu-id="8ccb3-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="8ccb3-149">Průvodce pokročilým obnovením automaticky detekuje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="8ccb3-150">Vyberte dlaždici **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="8ccb3-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="8ccb3-151">Na další obrazovce vyberte ruční výběr balíčku a potom vyberte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="8ccb3-152">(Vyhledejte soubor s příponou. FFU.)</span><span class="sxs-lookup"><span data-stu-id="8ccb3-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="8ccb3-153">Vyberte **instalovat software** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="8ccb3-154">Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8ccb3-155">Pokud budete chtít zůstat v aktuálně nainstalované verzi, můžete také ručně [pozastavit aktualizace](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="8ccb3-156">To poskytne technickému týmu čas k vyřešení problému.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="8ccb3-157">Program Windows Insider na HoloLens</span><span class="sxs-lookup"><span data-stu-id="8ccb3-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="8ccb3-158">Chcete zobrazit nejnovější funkce v HoloLens?</span><span class="sxs-lookup"><span data-stu-id="8ccb3-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="8ccb3-159">Pokud ano, připojte se k programu Windows Insider. získáte přístup k buildům Preview pro aktualizace softwaru HoloLens předtím, než budou k dispozici všeobecně veřejnosti.</span><span class="sxs-lookup"><span data-stu-id="8ccb3-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="8ccb3-160">[Získejte Windows Insider Preview pro Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="8ccb3-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
