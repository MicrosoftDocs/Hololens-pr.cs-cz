---
title: Aktualizovat HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377637"
---
# <a name="update-hololens"></a><span data-ttu-id="a7428-104">Aktualizovat HoloLens</span><span class="sxs-lookup"><span data-stu-id="a7428-104">Update HoloLens</span></span>

<span data-ttu-id="a7428-105">HoloLens používá web Windows Update stejně jako jiná zařízení s Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a7428-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="a7428-106">Vaše HoloLens automaticky stáhne a nainstaluje aktualizace systému, kdykoli se připojí k Internetu, a to i v případě, že je v pohotovostním režimu.</span><span class="sxs-lookup"><span data-stu-id="a7428-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="a7428-107">Tento článek vás provede nástroji HoloLens pro:</span><span class="sxs-lookup"><span data-stu-id="a7428-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="a7428-108">zobrazení aktuální verze operačního systému (číslo sestavení)</span><span class="sxs-lookup"><span data-stu-id="a7428-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="a7428-109">hledají se aktualizace.</span><span class="sxs-lookup"><span data-stu-id="a7428-109">checking for updates</span></span>
- <span data-ttu-id="a7428-110">Ruční aktualizace HoloLens</span><span class="sxs-lookup"><span data-stu-id="a7428-110">manually updating HoloLens</span></span>
- <span data-ttu-id="a7428-111">vrácení zpět se starší aktualizací</span><span class="sxs-lookup"><span data-stu-id="a7428-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="a7428-112">Ověřit verzi operačního systému (číslo sestavení)</span><span class="sxs-lookup"><span data-stu-id="a7428-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="a7428-113">Číslo verze systému (číslo sestavení) můžete ověřit tak, že otevřete aplikaci nastavení a vyberete **systém**  >  .</span><span class="sxs-lookup"><span data-stu-id="a7428-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="a7428-114">Vyhledat aktualizace a ručně aktualizovat</span><span class="sxs-lookup"><span data-stu-id="a7428-114">Check for updates and manually update</span></span>

<span data-ttu-id="a7428-115">Aktualizace můžete vyhledat kdykoli v nastavení.</span><span class="sxs-lookup"><span data-stu-id="a7428-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="a7428-116">Chcete-li zobrazit dostupné aktualizace a vyhledat nové aktualizace:</span><span class="sxs-lookup"><span data-stu-id="a7428-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="a7428-117">Otevřete aplikaci **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="a7428-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="a7428-118">Přejděte k **aktualizaci web Windows Update zabezpečení &**  >  .</span><span class="sxs-lookup"><span data-stu-id="a7428-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="a7428-119">Vyberte **Vyhledat aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="a7428-119">Select **Check for updates**.</span></span>

<span data-ttu-id="a7428-120">Pokud je k dispozici aktualizace, začne se stahovat nová verze.</span><span class="sxs-lookup"><span data-stu-id="a7428-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="a7428-121">Po dokončení stahování spusťte instalaci kliknutím na tlačítko **restartovat** .</span><span class="sxs-lookup"><span data-stu-id="a7428-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="a7428-122">Pokud je vaše zařízení pod 40% a není napájené z elektrické sítě, při restartování se nespustí instalace aktualizace.</span><span class="sxs-lookup"><span data-stu-id="a7428-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="a7428-123">I když váš HoloLens instaluje aktualizaci, zobrazí se ozubené kolečka a indikátor průběhu.</span><span class="sxs-lookup"><span data-stu-id="a7428-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="a7428-124">Během této doby nepínejte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7428-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="a7428-125">Po dokončení instalace se automaticky restartuje.</span><span class="sxs-lookup"><span data-stu-id="a7428-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="a7428-126">HoloLens používá vždy jednu aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="a7428-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="a7428-127">Pokud máte více než jednu verzi, kterou máte v poslední době, možná budete muset projít proces aktualizace několikrát, abyste ho mohli plně aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="a7428-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="a7428-128">Přejít zpět na předchozí verzi – HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a7428-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="a7428-129">V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7428-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="a7428-130">To můžete provést pomocí Průvodce pokročilým obnovením a resetovat svoji HoloLens na předchozí verzi.</span><span class="sxs-lookup"><span data-stu-id="a7428-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="a7428-131">Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.</span><span class="sxs-lookup"><span data-stu-id="a7428-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="a7428-132">Chcete-li se vrátit k předchozí verzi HoloLens 2, postupujte podle následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="a7428-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="a7428-133">Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.</span><span class="sxs-lookup"><span data-stu-id="a7428-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="a7428-134">V počítači si stáhněte z Microsoft Store [Průvodce rozšířeným obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) .</span><span class="sxs-lookup"><span data-stu-id="a7428-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="a7428-135">Stáhněte si nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="a7428-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="a7428-136">Po dokončení těchto souborů ke stažení otevřete **Průzkumníka souborů**  >  .</span><span class="sxs-lookup"><span data-stu-id="a7428-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="a7428-137">Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.</span><span class="sxs-lookup"><span data-stu-id="a7428-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="a7428-138">Připojte HoloLens k počítači pomocí USB-A k kabelu USB-C.</span><span class="sxs-lookup"><span data-stu-id="a7428-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="a7428-139">(I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)</span><span class="sxs-lookup"><span data-stu-id="a7428-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="a7428-140">Průvodce pokročilým obnovením automaticky detekuje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7428-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="a7428-141">Vyberte dlaždici **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="a7428-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="a7428-142">Na další obrazovce vyberte ruční výběr balíčku a potom vyberte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="a7428-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="a7428-143">(Vyhledejte soubor s příponou. FFU.)</span><span class="sxs-lookup"><span data-stu-id="a7428-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="a7428-144">Vyberte **instalovat software** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="a7428-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="a7428-145">Přejít zpět na předchozí verzi – HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="a7428-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="a7428-146">V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7428-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="a7428-147">To můžete provést pomocí nástroje pro obnovení zařízení systému Windows a resetovat svoji HoloLens na předchozí verzi.</span><span class="sxs-lookup"><span data-stu-id="a7428-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="a7428-148">Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.</span><span class="sxs-lookup"><span data-stu-id="a7428-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="a7428-149">Chcete-li se vrátit k předchozí verzi HoloLens 1, postupujte podle následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="a7428-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="a7428-150">Ujistěte se, že k počítači nemáte připojené žádné telefony ani zařízení s Windows.</span><span class="sxs-lookup"><span data-stu-id="a7428-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="a7428-151">Na počítači stáhněte [Nástroj Windows Device Recovery (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="a7428-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="a7428-152">Stáhněte si [balíček pro obnovení aktualizace HoloLens výročí](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="a7428-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="a7428-153">Po dokončení stahování otevřete **Průzkumníka souborů**  >  .</span><span class="sxs-lookup"><span data-stu-id="a7428-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="a7428-154">Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.</span><span class="sxs-lookup"><span data-stu-id="a7428-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="a7428-155">Připojte HoloLens k počítači pomocí kabelu mikrosběrnice USB, ke kterému byl dodán.</span><span class="sxs-lookup"><span data-stu-id="a7428-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="a7428-156">(I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)</span><span class="sxs-lookup"><span data-stu-id="a7428-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="a7428-157">WDRT automaticky detekuje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a7428-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="a7428-158">Vyberte dlaždici **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="a7428-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="a7428-159">Na další obrazovce vyberte ruční výběr balíčku a zvolte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="a7428-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="a7428-160">(Vyhledejte soubor s příponou. FFU.)</span><span class="sxs-lookup"><span data-stu-id="a7428-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="a7428-161">Vyberte **instalovat software** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="a7428-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="a7428-162">Pokud WDRT nerozpozná váš HoloLens, zkuste restartovat počítač.</span><span class="sxs-lookup"><span data-stu-id="a7428-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="a7428-163">Pokud to nepomůže, vyberte **Moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="a7428-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="a7428-164">Program Windows Insider na HoloLens</span><span class="sxs-lookup"><span data-stu-id="a7428-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="a7428-165">Chcete zobrazit nejnovější funkce v HoloLens?</span><span class="sxs-lookup"><span data-stu-id="a7428-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="a7428-166">Pokud ano, připojte se k programu Windows Insider. získáte přístup k buildům Preview pro aktualizace softwaru HoloLens předtím, než budou k dispozici všeobecně veřejnosti.</span><span class="sxs-lookup"><span data-stu-id="a7428-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="a7428-167">[Získejte Windows Insider Preview pro Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="a7428-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
