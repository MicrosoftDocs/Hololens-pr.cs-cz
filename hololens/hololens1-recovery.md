---
title: Restartování, resetování nebo obnovení HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Jak používat nástroj Windows Device Recovery Tool k flash flash disku obrázku do HoloLens 1. generace
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377608"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="96963-104">Restartování, resetování nebo obnovení HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="96963-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="96963-105">Pokud dochází k problémům s HoloLens, můžete zkusit restartovat nebo resetovat zařízení nebo dokonce pomocí obnovení zařízení odkazovat.</span><span class="sxs-lookup"><span data-stu-id="96963-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="96963-106">Tento článek vás provede doporučenými kroky obnovení v pořadí.</span><span class="sxs-lookup"><span data-stu-id="96963-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="96963-107">Pokud chcete obnovit HoloLens 2, podívejte se na obnovení [HoloLens 2,](https://docs.microsoft.com/hololens/hololens-recovery)protože se tento proces liší.</span><span class="sxs-lookup"><span data-stu-id="96963-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="96963-108">Tento článek se zaměřuje na zařízení a software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96963-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="96963-109">Pokud vaše hologramy vypadají správně, najdete informace o faktorech, které zlepšují kvalitu hologramů, v tématu Aspekty prostředí **[HoloLens.](hololens-environment-considerations.md)**</span><span class="sxs-lookup"><span data-stu-id="96963-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="96963-110">Restartovat</span><span class="sxs-lookup"><span data-stu-id="96963-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="96963-111">Bezpečné restartování pomocí Cortany</span><span class="sxs-lookup"><span data-stu-id="96963-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="96963-112">Nejbezpečnější způsob, jak restartovat HoloLens, je použití Cortany, což je obecně první věc, kterou byste si měli vyzkoušet, když nastane problém s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96963-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="96963-113">Cortana není dostupná na všech zařízeních.</span><span class="sxs-lookup"><span data-stu-id="96963-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="96963-114">Cortana je dostupná na všech zařízeních HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="96963-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="96963-115">Cortana je na zařízeních HoloLens 2 dostupná na buildech před aktualizací Windows Holograpic verze 2004.</span><span class="sxs-lookup"><span data-stu-id="96963-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="96963-116">Zapněte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96963-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="96963-117">Ujistěte se, že je uživatel přihlášený a že zařízení nečeká na odemknutí hesla.</span><span class="sxs-lookup"><span data-stu-id="96963-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="96963-118">Řekněte "Ahoj Cortana, restartování" nebo "Ahoj Cortana, restartujte".</span><span class="sxs-lookup"><span data-stu-id="96963-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="96963-119">Cortana odpoví a vyzve vás k potvrzení.</span><span class="sxs-lookup"><span data-stu-id="96963-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="96963-120">Počkejte, až se po otázce přehraje zvuk, a potom řekněte Ano.</span><span class="sxs-lookup"><span data-stu-id="96963-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="96963-121">Zařízení se restartuje.</span><span class="sxs-lookup"><span data-stu-id="96963-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="96963-122">Bezpečné restartování pomocí tlačítka napájení</span><span class="sxs-lookup"><span data-stu-id="96963-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="96963-123">Pokud stále nemůžete zařízení restartovat, zkuste ho restartovat pomocí tlačítka **napájení:**</span><span class="sxs-lookup"><span data-stu-id="96963-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="96963-124">Stiskněte a podržte **tlačítko napájení** po dobu 5 sekund.</span><span class="sxs-lookup"><span data-stu-id="96963-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="96963-125">Po 1 sekundě se všech pět LED diod rozzáří a pak postupně postupně jeden po druhém vypne zprava doleva.</span><span class="sxs-lookup"><span data-stu-id="96963-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="96963-126">Po 5 sekundách budou všechny LED diody vypnuté, což značí úspěšné vypnutí.</span><span class="sxs-lookup"><span data-stu-id="96963-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="96963-127">Okamžitě po vypnutí všech LED diod zastavte stisknutí tlačítka.</span><span class="sxs-lookup"><span data-stu-id="96963-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="96963-128">Počkejte 1 minutu, než se vypnutí dokončí.</span><span class="sxs-lookup"><span data-stu-id="96963-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="96963-129">Vypnutí může stále probíhají, i když jsou displeje vypnuté.</span><span class="sxs-lookup"><span data-stu-id="96963-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="96963-130">Znovu zapněte zařízení stisknutím a podržením tlačítka **napájení** na 1 sekundu.</span><span class="sxs-lookup"><span data-stu-id="96963-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="96963-131">Proveďte bezpečné restartování pomocí Portál zařízení s Windows</span><span class="sxs-lookup"><span data-stu-id="96963-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="96963-132">Pro tento proces je třeba HoloLens nakonfigurovat jako vývojářské zařízení.</span><span class="sxs-lookup"><span data-stu-id="96963-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="96963-133">Další informace najdete [na Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="96963-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="96963-134">Pokud předchozí postup nefunguje, zkuste zařízení restartovat pomocí příkazu [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="96963-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="96963-135">V pravém horním rohu vyhledejte možnost restartování nebo vypnutí zařízení.</span><span class="sxs-lookup"><span data-stu-id="96963-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="96963-136">Nebezpečné vynucené restartování</span><span class="sxs-lookup"><span data-stu-id="96963-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="96963-137">Pokud předchozí metody nerestartly HoloLens, vynutí restartování.</span><span class="sxs-lookup"><span data-stu-id="96963-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="96963-138">Tato metoda je ekvivalentní k odebrání a opětovné instalaci baterie.</span><span class="sxs-lookup"><span data-stu-id="96963-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="96963-139">Je to nebezpečné, protože by mohlo nechat zařízení v poškozeném stavu.</span><span class="sxs-lookup"><span data-stu-id="96963-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="96963-140">Pokud k tomu dojde, budete muset holoLens blikat.</span><span class="sxs-lookup"><span data-stu-id="96963-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="96963-141">Jedná se o potenciálně škodlivou metodu, která by se měla použít pouze v případě, že dříve citované metody nefungují.</span><span class="sxs-lookup"><span data-stu-id="96963-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="96963-142">Stiskněte a podržte **tlačítko** napájení alespoň 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="96963-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="96963-143">Tlačítko můžete podržet déle než 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="96963-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="96963-144">Každou aktivitu indikátoru LED můžete bezpečně ignorovat.</span><span class="sxs-lookup"><span data-stu-id="96963-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="96963-145">Uvolněte tlačítko a počkejte 2–3 sekundy.</span><span class="sxs-lookup"><span data-stu-id="96963-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="96963-146">Stiskněte a podržte **tlačítko** napájení po dobu 1 sekundy.</span><span class="sxs-lookup"><span data-stu-id="96963-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="96963-147">Pokud stále máte problémy,  stiskněte tlačítko napájení po dobu 4 sekund, dokud se všechny indikátory baterie neztlumí a obrazovka přestane zobrazovat hologramy.</span><span class="sxs-lookup"><span data-stu-id="96963-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="96963-148">Počkejte 1 minutu a pak znovu stiskněte **tlačítko** napájení, aby se zařízení zapne.</span><span class="sxs-lookup"><span data-stu-id="96963-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="96963-149">Obnovení továrního nastavení</span><span class="sxs-lookup"><span data-stu-id="96963-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="96963-150">Baterie potřebuje k resetování alespoň 40procentní poplatek.</span><span class="sxs-lookup"><span data-stu-id="96963-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="96963-151">Pokud má holoLens problém, zkuste ho resetovat do stavu továrního nastavení.</span><span class="sxs-lookup"><span data-stu-id="96963-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="96963-152">Tento krok zachová verzi softwaru Windows Holographic, který je v ní nainstalovaný, a vrátí všechno ostatní do továrního nastavení.</span><span class="sxs-lookup"><span data-stu-id="96963-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="96963-153">Pokud zařízení resetujete, vymažou se všechny vaše osobní údaje, aplikace a nastavení včetně informací o resetování čipu TPM.</span><span class="sxs-lookup"><span data-stu-id="96963-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="96963-154">Resetováním se nainstaluje jenom nejnovější nainstalovaná verze Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="96963-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="96963-155">Budete muset znovu provést všechny kroky inicializace (nakalibrovat, připojit se k Wi-Fi, vytvořit uživatelský účet, stáhnout aplikace atd.).</span><span class="sxs-lookup"><span data-stu-id="96963-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="96963-156">Otevřete aplikaci Nastavení a pak vyberte **Aktualizovat**  >  **obnovení.**</span><span class="sxs-lookup"><span data-stu-id="96963-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="96963-157">Vyberte možnost **Resetovat** zařízení a přečtěte si potvrzovací zprávu.</span><span class="sxs-lookup"><span data-stu-id="96963-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="96963-158">Potvrďte resetování.</span><span class="sxs-lookup"><span data-stu-id="96963-158">Confirm the reset.</span></span> <span data-ttu-id="96963-159">Zařízení se restartuje a zobrazí se sada rotujícího ozubeného kola a indikátor průběhu.</span><span class="sxs-lookup"><span data-stu-id="96963-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="96963-160">Počkejte asi 30 minut, než se tento proces dokončí.</span><span class="sxs-lookup"><span data-stu-id="96963-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="96963-161">Po dokončení se zařízení restartuje do prostředí, které je hotové.</span><span class="sxs-lookup"><span data-stu-id="96963-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="96963-162">Přeinstalujte operační systém.</span><span class="sxs-lookup"><span data-stu-id="96963-162">Reinstall the operating system</span></span>

<span data-ttu-id="96963-163">Pokud má zařízení problém i po restartování a resetování, můžete v počítači použít nástroj pro obnovení a znovu nainstalovat operační systém a firmware HoloLens.</span><span class="sxs-lookup"><span data-stu-id="96963-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="96963-164">Data, která HoloLens potřebuje k resetování, jsou zabalená v úplné aktualizaci Flash Update (FFU), která se podobá souboru .iso, .wim nebo .vhd.</span><span class="sxs-lookup"><span data-stu-id="96963-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="96963-165">Přečtěte si o formátech souborů obrázků FFU.</span><span class="sxs-lookup"><span data-stu-id="96963-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="96963-166">Nový operační systém můžete do HoloLens (1. generace) nainstalovat pomocí nástroje Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="96963-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="96963-167">Před použitím tohoto nástroje se podívejte, jestli restartování nebo resetování HoloLens tento problém vyřeší.</span><span class="sxs-lookup"><span data-stu-id="96963-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="96963-168">Proces obnovení může chvíli trvat.</span><span class="sxs-lookup"><span data-stu-id="96963-168">The recovery process may take a while.</span></span> <span data-ttu-id="96963-169">Až to bude hotové, nainstaluje se nejnovější verze softwaru Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="96963-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="96963-170">Pokud chcete nástroj používat, potřebujete počítač se systémem Windows 10 nebo novějším s alespoň 4 GB volného místa v úložišti.</span><span class="sxs-lookup"><span data-stu-id="96963-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="96963-171">Tento nástroj nelze spustit na virtuálním počítači.</span><span class="sxs-lookup"><span data-stu-id="96963-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="96963-172">Obnovení HoloLens</span><span class="sxs-lookup"><span data-stu-id="96963-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="96963-173">Stáhněte a nainstalujte do svého počítače nástroj Obnovení zařízení systému [Windows.](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)</span><span class="sxs-lookup"><span data-stu-id="96963-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="96963-174">Připojte HoloLens (1. generace) k počítači pomocí kabelu Micro USB, který jste dodáli s holoLens.</span><span class="sxs-lookup"><span data-stu-id="96963-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="96963-175">Otevřete nástroj Windows Device Recovery Tool a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="96963-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="96963-176">Pokud se holoLens (1. generace) nezjistí automaticky, vyberte **Moje zařízení se nezjistě.**</span><span class="sxs-lookup"><span data-stu-id="96963-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="96963-177">Pak postupujte podle pokynů a předejte zařízení do režimu obnovení.</span><span class="sxs-lookup"><span data-stu-id="96963-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="96963-178">Režim ručního blikajícího režimu</span><span class="sxs-lookup"><span data-stu-id="96963-178">Manual flashing mode</span></span>

<span data-ttu-id="96963-179">Pokud se vaše zařízení nezjme, postupujte podle těchto kroků a předejte ho do blikajícího režimu:</span><span class="sxs-lookup"><span data-stu-id="96963-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="96963-180">Odpojte zařízení od jakéhokoli zdroje napájení.</span><span class="sxs-lookup"><span data-stu-id="96963-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="96963-181">Pokud je zařízení vypnuté, podržte **stisknuté** tlačítko napájení, dokud se úplně nevypíná.</span><span class="sxs-lookup"><span data-stu-id="96963-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="96963-182">Podržte **tlačítko hlasitosti a** krátce klepněte na tlačítko **napájení.**</span><span class="sxs-lookup"><span data-stu-id="96963-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="96963-183">Zařízení by se mělo spustit a zobrazit pouze prostřední led diodu.</span><span class="sxs-lookup"><span data-stu-id="96963-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="96963-184">Připojte zařízení k počítači.</span><span class="sxs-lookup"><span data-stu-id="96963-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="96963-185">Otevřete Nástroj pro obnovení zařízení s Windows.</span><span class="sxs-lookup"><span data-stu-id="96963-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="96963-186">Vyberte **Moje zařízení se nezjtekuje** a pak **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="96963-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="96963-187">Podle pokynů obnovte zařízení.</span><span class="sxs-lookup"><span data-stu-id="96963-187">Follow the instructions to recover your device.</span></span>
