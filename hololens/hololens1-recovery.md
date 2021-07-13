---
title: restartování, resetování nebo obnovení HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: jak použít nástroj pro obnovení zařízení Windows k zablikání obrázku HoloLens 1. generace
keywords: postupy, restartování, resetování, obnovení, vynucené resetování, obnovitelné resetování, cyklus napájení, HoloLens, vypnutí, wdrt, nástroj pro obnovení zařízení systému windows
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635224"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="e38a4-104">restartování, resetování nebo obnovení HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="e38a4-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="e38a4-105">pokud máte problémy s HoloLens, můžete zkusit restartovat nebo resetovat nebo dokonce zařízení znovu zablikat pomocí obnovení zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="e38a4-106">Tento článek vás provede doporučenými kroky obnovení v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="e38a4-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="e38a4-107">pokud hledáte HoloLens 2, přečtěte si téma obnovení [HoloLens 2](hololens-recovery.md), protože se tento proces liší.</span><span class="sxs-lookup"><span data-stu-id="e38a4-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="e38a4-108">tento článek se zaměřuje na HoloLens zařízení a software.</span><span class="sxs-lookup"><span data-stu-id="e38a4-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="e38a4-109">pokud vaše hologramy nevypadají správně, přečtěte si téma **[aspekty HoloLens prostředí](hololens-environment-considerations.md)** , kde najdete informace o faktorech, které zlepšují kvalitu hologramů.</span><span class="sxs-lookup"><span data-stu-id="e38a4-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="e38a4-110">Restartovat</span><span class="sxs-lookup"><span data-stu-id="e38a4-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="e38a4-111">Bezpečné restartování pomocí Cortana</span><span class="sxs-lookup"><span data-stu-id="e38a4-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="e38a4-112">nejbezpečnější způsob, jak restartovat HoloLens, je použití Cortana, což je obecně první věc, kterou můžete vyzkoušet v případě potíží s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e38a4-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="e38a4-113">Cortana není k dispozici na všech zařízeních.</span><span class="sxs-lookup"><span data-stu-id="e38a4-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="e38a4-114">Cortana je k dispozici na všech HoloLensch (1. Gen) zařízeních.</span><span class="sxs-lookup"><span data-stu-id="e38a4-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="e38a4-115">Cortana je k dispozici na zařízeních HoloLens 2 v sestavách před Windows Holograpic verze 2004 aktualizace.</span><span class="sxs-lookup"><span data-stu-id="e38a4-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="e38a4-116">Zapněte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e38a4-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="e38a4-117">Ujistěte se, že je uživatel přihlášený a že zařízení nečeká na jeho odemknutí heslem.</span><span class="sxs-lookup"><span data-stu-id="e38a4-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="e38a4-118">vyslovte "hey Cortana, restart" nebo "Hey Cortana, restarter."</span><span class="sxs-lookup"><span data-stu-id="e38a4-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="e38a4-119">Cortana odpoví a zobrazí se výzva k potvrzení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="e38a4-120">Počkejte, až se zvuk dohraje, a pak řekněte "Ano".</span><span class="sxs-lookup"><span data-stu-id="e38a4-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="e38a4-121">Zařízení se restartuje.</span><span class="sxs-lookup"><span data-stu-id="e38a4-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="e38a4-122">K bezpečnému restartování použijte tlačítko napájení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="e38a4-123">Pokud stále nemůžete restartovat vaše zařízení, zkuste ho restartovat pomocí tlačítka **napájení** :</span><span class="sxs-lookup"><span data-stu-id="e38a4-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="e38a4-124">Stiskněte a držte tlačítko **napájení** po dobu 5 sekund.</span><span class="sxs-lookup"><span data-stu-id="e38a4-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="e38a4-125">Po 1 sekundách se všechna pět diod LED rozsvítí a pak pomalu vypnou od sebe od zprava doleva.</span><span class="sxs-lookup"><span data-stu-id="e38a4-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="e38a4-126">Po 5 sekundách dojde k vypnutí všech diod LED, což znamená úspěšné vypnutí.</span><span class="sxs-lookup"><span data-stu-id="e38a4-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="e38a4-127">Zastaví stisknutí tlačítka ihned po vypnutí všech diod LED.</span><span class="sxs-lookup"><span data-stu-id="e38a4-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="e38a4-128">Počkejte 1 minutu na dokončení vypnutí.</span><span class="sxs-lookup"><span data-stu-id="e38a4-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="e38a4-129">Vypnutí může stále probíhat i po vypnutí displeje.</span><span class="sxs-lookup"><span data-stu-id="e38a4-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="e38a4-130">Znovu zapněte zařízení stisknutím a podržením tlačítka **napájení** po dobu 1 sekundy.</span><span class="sxs-lookup"><span data-stu-id="e38a4-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="e38a4-131">bezpečné restartování pomocí Windows portálu zařízení</span><span class="sxs-lookup"><span data-stu-id="e38a4-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="e38a4-132">pro tento proces musí být HoloLens nakonfigurovaný jako vývojářské zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="e38a4-133">další informace najdete na [Windows portálu zařízení](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="e38a4-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="e38a4-134">pokud předchozí postup nefunguje, zkuste zařízení restartovat pomocí [portálu Windows zařízení](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="e38a4-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="e38a4-135">V pravém horním rohu Najděte možnost pro restartování nebo vypnutí zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="e38a4-136">Provedení nebezpečného vynuceného restartování</span><span class="sxs-lookup"><span data-stu-id="e38a4-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="e38a4-137">pokud předchozí metody nerestartoval váš HoloLens, vynuťte restart.</span><span class="sxs-lookup"><span data-stu-id="e38a4-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="e38a4-138">Tato metoda je ekvivalentní k odebrání a přeinstalaci baterie.</span><span class="sxs-lookup"><span data-stu-id="e38a4-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="e38a4-139">Je nebezpečný, protože může opustit vaše zařízení v poškozeném stavu.</span><span class="sxs-lookup"><span data-stu-id="e38a4-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="e38a4-140">Pokud k tomu dojde, budete muset svůj HoloLens Flash.</span><span class="sxs-lookup"><span data-stu-id="e38a4-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="e38a4-141">Toto je potenciálně škodlivá metoda a měla by se používat jenom v případě, že dříve citované metody nefungovaly.</span><span class="sxs-lookup"><span data-stu-id="e38a4-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="e38a4-142">Stiskněte a držte tlačítko **napájení** alespoň 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="e38a4-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="e38a4-143">Tlačítko je v pořádku po dobu delší než 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="e38a4-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="e38a4-144">Je bezpečné ignorovat aktivitu LED.</span><span class="sxs-lookup"><span data-stu-id="e38a4-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="e38a4-145">Uvolněte tlačítko a počkejte na 2-3 sekund.</span><span class="sxs-lookup"><span data-stu-id="e38a4-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="e38a4-146">Stiskněte a držte tlačítko **napájení** po dobu 1 sekundy.</span><span class="sxs-lookup"><span data-stu-id="e38a4-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="e38a4-147">Pokud stále máte problémy, stiskněte tlačítko **napájení** po dobu 4 sekund, dokud se všechny indikátory baterie nezobrazují, a obrazovka přestane zobrazovat hologramy.</span><span class="sxs-lookup"><span data-stu-id="e38a4-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="e38a4-148">Počkejte 1 minutu a potom znovu stiskněte tlačítko **napájení** a zapněte zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="e38a4-149">přejít zpět na předchozí verzi HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="e38a4-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="e38a4-150">v některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru.</span><span class="sxs-lookup"><span data-stu-id="e38a4-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="e38a4-151">to můžete provést pomocí nástroje pro obnovení Windows zařízení a resetovat HoloLens na předchozí verzi.</span><span class="sxs-lookup"><span data-stu-id="e38a4-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="e38a4-152">Když se vrátíte k předchozí verzi, odstraní se vaše osobní soubory a nastavení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="e38a4-153">chcete-li se vrátit k předchozí verzi HoloLens 1, postupujte podle následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="e38a4-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="e38a4-154">ujistěte se, že nemáte k počítači připojené žádné telefony ani zařízení Windows.</span><span class="sxs-lookup"><span data-stu-id="e38a4-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="e38a4-155">na počítači stáhněte [nástroj Windows pro obnovení zařízení (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="e38a4-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="e38a4-156">stáhněte si [balíček pro obnovení aktualizace pro HoloLens výročí](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="e38a4-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="e38a4-157">Po dokončení stahování otevřete **Průzkumníka souborů**  >  .</span><span class="sxs-lookup"><span data-stu-id="e38a4-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="e38a4-158">Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.</span><span class="sxs-lookup"><span data-stu-id="e38a4-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="e38a4-159">Připojení své HoloLens k počítači pomocí kabelu mikrosběrnice USB, na který byl dodán.</span><span class="sxs-lookup"><span data-stu-id="e38a4-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="e38a4-160">(i když používáte k připojení HoloLens jiné kabely, tato funkce funguje nejlépe.)</span><span class="sxs-lookup"><span data-stu-id="e38a4-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="e38a4-161">WDRT automaticky detekuje vaše HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e38a4-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="e38a4-162">vyberte dlaždici **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="e38a4-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="e38a4-163">Na další obrazovce vyberte ruční výběr balíčku a zvolte instalační soubor obsažený ve složce, kterou jste **rozbalíte** v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="e38a4-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="e38a4-164">(Vyhledejte soubor s příponou. FFU.)</span><span class="sxs-lookup"><span data-stu-id="e38a4-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="e38a4-165">Vyberte **instalovat software** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="e38a4-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="e38a4-166">pokud WDRT nezjistí váš HoloLens, zkuste restartovat počítač.</span><span class="sxs-lookup"><span data-stu-id="e38a4-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="e38a4-167">pokud to nepomůže, vyberte **moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="e38a4-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="e38a4-168">Resetovat do továrního nastavení</span><span class="sxs-lookup"><span data-stu-id="e38a4-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="e38a4-169">Pro resetování baterie musí být vyplněna minimální sazba 40 až procent.</span><span class="sxs-lookup"><span data-stu-id="e38a4-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="e38a4-170">pokud má HoloLens stále problém, zkuste ho obnovit do stavu tovární nastavení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="e38a4-171">v tomto kroku se zachová verze Windows holografického softwaru, který je na něm nainstalovaný, a vrátí všechno ostatní k továrnímu nastavení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="e38a4-172">Pokud resetujete zařízení, budou smazána všechna vaše osobní data, aplikace a nastavení, včetně informací o resetování čipu TPM.</span><span class="sxs-lookup"><span data-stu-id="e38a4-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="e38a4-173">při obnovení se nainstaluje jenom nejnovější nainstalovaná verze Windows holografické.</span><span class="sxs-lookup"><span data-stu-id="e38a4-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="e38a4-174">Budete muset znovu provést všechny kroky inicializace (kalibraci, připojit se k Wi-Fi, vytvořit uživatelský účet, stáhnout aplikace atd.).</span><span class="sxs-lookup"><span data-stu-id="e38a4-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="e38a4-175">otevřete aplikaci Nastavení a pak vyberte **aktualizovat**  >  **obnovení**.</span><span class="sxs-lookup"><span data-stu-id="e38a4-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="e38a4-176">Vyberte možnost **resetovat zařízení** a přečtěte si potvrzovací zprávu.</span><span class="sxs-lookup"><span data-stu-id="e38a4-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="e38a4-177">Potvrďte resetování.</span><span class="sxs-lookup"><span data-stu-id="e38a4-177">Confirm the reset.</span></span> <span data-ttu-id="e38a4-178">Zařízení se restartuje a zobrazí se sada rotujících ozubených kolečk a indikátor průběhu.</span><span class="sxs-lookup"><span data-stu-id="e38a4-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="e38a4-179">Počkejte přibližně 30 minut, než se tento proces dokončí.</span><span class="sxs-lookup"><span data-stu-id="e38a4-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="e38a4-180">Až se zařízení dokončí, zařízení se restartuje do předpřipraveného prostředí.</span><span class="sxs-lookup"><span data-stu-id="e38a4-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="e38a4-181">Opětovná instalace operačního systému</span><span class="sxs-lookup"><span data-stu-id="e38a4-181">Reinstall the operating system</span></span>

<span data-ttu-id="e38a4-182">pokud má zařízení stále problém po restartování a obnovení, můžete použít nástroj pro obnovení na počítači k přeinstalování HoloLens operační systém a firmware.</span><span class="sxs-lookup"><span data-stu-id="e38a4-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="e38a4-183">data, která HoloLens potřebuje pro obnovení, se zabalí do úplné aktualizace Flash (FFU), která je podobná souboru. iso,. wim nebo. vhd.</span><span class="sxs-lookup"><span data-stu-id="e38a4-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="e38a4-184">Přečtěte si o formátech souborů obrázků FFU.</span><span class="sxs-lookup"><span data-stu-id="e38a4-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="e38a4-185">nový operační systém můžete nainstalovat do HoloLens (1. generace) pomocí nástroje Windows pro obnovení zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="e38a4-186">než tento nástroj použijete, přečtěte si článek o restartování nebo resetování HoloLens problém vyřeší.</span><span class="sxs-lookup"><span data-stu-id="e38a4-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="e38a4-187">Proces obnovení může chvíli trvat.</span><span class="sxs-lookup"><span data-stu-id="e38a4-187">The recovery process may take a while.</span></span> <span data-ttu-id="e38a4-188">až to bude hotové, nainstaluje se nejnovější verze Windows holografického softwaru.</span><span class="sxs-lookup"><span data-stu-id="e38a4-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="e38a4-189">chcete-li použít nástroj, potřebujete počítač se systémem Windows 10 nebo novějším s alespoň 4 GB volného místa v úložišti.</span><span class="sxs-lookup"><span data-stu-id="e38a4-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="e38a4-190">Tento nástroj nemůžete spustit na virtuálním počítači.</span><span class="sxs-lookup"><span data-stu-id="e38a4-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="e38a4-191">Obnovení HoloLens</span><span class="sxs-lookup"><span data-stu-id="e38a4-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="e38a4-192">stáhněte a nainstalujte [nástroj Windows recovery zařízení](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) do počítače.</span><span class="sxs-lookup"><span data-stu-id="e38a4-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="e38a4-193">Připojení HoloLens (1. generace) do vašeho počítače pomocí kabelu mikrosběrnice USB, který byl dodán s vaším HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e38a4-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="e38a4-194">otevřete nástroj Windows recovery zařízení a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="e38a4-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="e38a4-195">pokud se nezjistí automaticky HoloLens (1. generace), vyberte **moje zařízení se nezjistilo**.</span><span class="sxs-lookup"><span data-stu-id="e38a4-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="e38a4-196">Pak postupujte podle pokynů a vložte zařízení do režimu obnovení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="e38a4-197">Režim ručního blikání</span><span class="sxs-lookup"><span data-stu-id="e38a4-197">Manual flashing mode</span></span>

<span data-ttu-id="e38a4-198">Pokud zařízení není zjištěné, postupujte podle těchto kroků a přepněte do režimu blikání:</span><span class="sxs-lookup"><span data-stu-id="e38a4-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="e38a4-199">Odpojte zařízení od libovolného zdroje napájení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="e38a4-200">Pokud je zařízení zapnuté, stiskněte tlačítko **napájení** , dokud se úplně nevypne.</span><span class="sxs-lookup"><span data-stu-id="e38a4-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="e38a4-201">Podržte **tlačítko pro** zvýšení hlasitosti a krátce klepněte na tlačítko **napájení.**</span><span class="sxs-lookup"><span data-stu-id="e38a4-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="e38a4-202">Zařízení by se mělo spustit a zobrazit pouze prostřední led diodu.</span><span class="sxs-lookup"><span data-stu-id="e38a4-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="e38a4-203">Připojte zařízení k počítači.</span><span class="sxs-lookup"><span data-stu-id="e38a4-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="e38a4-204">Otevřete nástroj Windows Device Recovery.</span><span class="sxs-lookup"><span data-stu-id="e38a4-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="e38a4-205">Vyberte **Moje zařízení se nezjme a** potom **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="e38a4-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="e38a4-206">Podle pokynů obnovte zařízení.</span><span class="sxs-lookup"><span data-stu-id="e38a4-206">Follow the instructions to recover your device.</span></span>
