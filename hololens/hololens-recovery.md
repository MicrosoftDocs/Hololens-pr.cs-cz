---
title: Restartování, resetování nebo obnovení HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Jak použít pokročilého Průvodce obnovením k blikání image na HoloLens 2.
keywords: postupy, restart, reset, obnovení, vynucené resetování, měkké resetování, cyklus napájení, HoloLens, vypnutí, oblouk, pokročilý Průvodce obnovením
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923631"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="8a7b8-104">Restartování, resetování nebo obnovení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8a7b8-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="8a7b8-105">Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="8a7b8-106">[Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="8a7b8-107">Použijte [nabíječku a kabel typu USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) , který byl dodán s HoloLens 2, protože to je nejlepší způsob, jak zařízení účtovat.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="8a7b8-108">Nabíječka dodá 18W výkonu (9V v 2A).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="8a7b8-109">Pomocí dodaných nabíječk zdí můžou zařízení s HoloLens 2 po dobu, kdy je zařízení v pohotovostním režimu, navýšit baterie na plnou dobu během méně než 65 minut.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="8a7b8-110">Pokud tato příslušenství nejsou k dispozici, zajistěte, aby nabíječka, která je k dispozici, mohla podporovat aspoň 15W napájení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="8a7b8-111">Pokud je to možné, nepoužívejte počítač k navýšení kapacity zařízení přes USB, což je pomalé.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="8a7b8-112">Pokud je zařízení správně spuštěno a běží, existují tři způsoby, jak ověřit úroveň nabití baterie:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="8a7b8-113">Z hlavní nabídky uživatelského rozhraní zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="8a7b8-114">Podívejte se, že indikátor LED blízko tlačítka napájení (pro poplatek 40 – Percent) by se měl zobrazit aspoň dva Solid diody LED.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="8a7b8-115">Když se zařízení účtuje, indikátory baterie až do indikace aktuální úrovně zpoplatnění.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="8a7b8-116">Poslední světlo zmizí a odznačí aktivní zpoplatnění.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="8a7b8-117">Když je zapnutý HoloLens, indikátor baterie zobrazí úroveň baterie v pěti přírůstcích.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="8a7b8-118">Pokud je zapnutá jenom jedna z pěti světel, úroveň baterie je nižší než 20 procent.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="8a7b8-119">Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, bude se krátce rozsvítit v jednom světle a pak se vrátí.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="8a7b8-120">Na hostitelském počítači otevřete **Průzkumníka souborů** a hledejte zařízení HoloLens 2 na levé straně **tohoto počítače**.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="8a7b8-121">Pravým tlačítkem myši klikněte na zařízení a vyberte **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="8a7b8-122">V dialogovém okně se zobrazí úroveň nabití baterie.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-122">A dialog box will show the battery charge level.</span></span>

   ![Obrazovka vlastností HoloLens 2 zobrazuje úroveň změny baterie](images/ResetRecovery2.png)

<span data-ttu-id="8a7b8-124">Pokud se zařízení nedá spustit do nabídky po spuštění, poznamenejte si vzhled INDIKÁTORu a výčet zařízení na hostitelském počítači.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="8a7b8-125">Pak postupujte podle pokynů [Průvodce odstraňováním potíží](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="8a7b8-126">Pokud se stav zařízení neshoduje s žádným ze stavů uvedených v Průvodci odstraňováním potíží, proveďte [postupnou operaci resetování](hololens-recovery.md#hard-reset-procedure) u zařízení připojeného k napájení, ne do hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="8a7b8-127">Počkejte alespoň jednu hodinu, než se zařízení doúčtuje.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="8a7b8-128">Resetování zařízení</span><span class="sxs-lookup"><span data-stu-id="8a7b8-128">Reset the device</span></span>

<span data-ttu-id="8a7b8-129">Za určitých okolností může být nutné ručně resetovat zařízení bez použití uživatelského rozhraní softwaru.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="8a7b8-130">Standardní postup</span><span class="sxs-lookup"><span data-stu-id="8a7b8-130">Standard procedure</span></span>

1. <span data-ttu-id="8a7b8-131">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8a7b8-132">Stiskněte a držte tlačítko **napájení** po dobu 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="8a7b8-133">Všechny diody LED by měly být vypnuté.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="8a7b8-134">Počkejte 2-3 sekund a potom stiskněte tlačítko **napájení** .</span><span class="sxs-lookup"><span data-stu-id="8a7b8-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="8a7b8-135">Indikátory LED, které se blíží tlačítku napájení, se budou rozsvítit a zařízení se začne spouštět.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="8a7b8-136">Připojte zařízení k hostitelskému počítači a otevřete Správce zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="8a7b8-137">(Pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a pak vyberte **Správce zařízení**.) Ujistěte se, že se zařízení správně vyčísluje jako *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery Devive Manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="8a7b8-139">Postup pevného resetu</span><span class="sxs-lookup"><span data-stu-id="8a7b8-139">Hard-reset procedure</span></span>

<span data-ttu-id="8a7b8-140">Pokud standardní procedura resetování nefungovala, použijte postup pevného resetování:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="8a7b8-141">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8a7b8-142">U 15 sekund podržíte tlačítka **hlasitosti dolů**  +   .</span><span class="sxs-lookup"><span data-stu-id="8a7b8-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="8a7b8-143">Zařízení se automaticky restartuje.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="8a7b8-144">Připojte zařízení k hostitelskému počítači.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="8a7b8-145">Otevřete Správce zařízení (pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a pak vyberte **Správce zařízení**).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="8a7b8-146">Ujistěte se, že se zařízení správně vyčísluje jako *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery zařízení správce 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="8a7b8-148">Vyčistit a znovu zablikat zařízení</span><span class="sxs-lookup"><span data-stu-id="8a7b8-148">Clean-reflash the device</span></span>

<span data-ttu-id="8a7b8-149">V mimořádných situacích možná budete muset "vyčistit-bliknutí" na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="8a7b8-150">Upozorňujeme, že příkaz vyčistit-reflash se neočekává vlivem na následující problémy:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="8a7b8-151">Zobrazit sjednocení barev</span><span class="sxs-lookup"><span data-stu-id="8a7b8-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="8a7b8-152">Spouštění se zvukem, ale bez zobrazení výstupu</span><span class="sxs-lookup"><span data-stu-id="8a7b8-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="8a7b8-153">vzor LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="8a7b8-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="8a7b8-154">Přehřívání</span><span class="sxs-lookup"><span data-stu-id="8a7b8-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="8a7b8-155">Selhání operačního systému (které se liší od selhání aplikace)</span><span class="sxs-lookup"><span data-stu-id="8a7b8-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="8a7b8-156">Existují dva způsoby, jak zařízení znovu zablikat.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="8a7b8-157">V obou případech je potřeba nejdřív [nainstalovat rozšířeného Průvodce obnovením z Windows Storu](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="8a7b8-158">Pokud vaše zařízení budete znovu zablikat, budou smazána všechna vaše osobní data, aplikace a nastavení, včetně informací o resetování čipu TPM.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="8a7b8-159">Ve výchozím nastavení je průvodce pokročilým obnovením nastaven na stažení nejnovějšího buildu pro vydání funkce. Přečtěte si zde [poznámky k verzi](hololens-release-notes.md#) , kde najdete další informace o nejnovější verzi funkce.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="8a7b8-160">Pokud chcete získat nejnovější balíček s úplným FFUm pro HoloLens 2, abyste mohli svoje zařízení znovu zablikat prostřednictvím pokročilého Průvodce obnovením, [klikněte sem a Stáhněte si nejnovější měsíční image HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="8a7b8-161">Tato verze je nejnovější všeobecně dostupná sestavení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="8a7b8-162">Než začnete s postupem přeblesku, ujistěte se, že je aplikace nainstalovaná a spuštěná na počítači s Windows 10 a je připravená k detekci zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="8a7b8-163">Také se ujistěte, že je váš HoloLens účtován minimálně 40%.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Snímek HoloLens 2 – vyčištění obrazovky čistého formátu](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="8a7b8-165">Běžný postup</span><span class="sxs-lookup"><span data-stu-id="8a7b8-165">Normal procedure</span></span>

1. <span data-ttu-id="8a7b8-166">Když je zařízení HoloLens spuštěné, připojte ho k počítači s Windows 10, kde jste předtím otevřeli rozšířenou aplikaci pro obnovení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="8a7b8-167">Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Úvodní obrazovka k vyčištění paměti HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="8a7b8-169">Vyberte zařízení HoloLens 2 v uživatelském rozhraní doprovodné aplikace pro pokročilé obnovení a podle pokynů dokončete znovu blesk.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="8a7b8-170">Ruční procedura</span><span class="sxs-lookup"><span data-stu-id="8a7b8-170">Manual procedure</span></span>

<span data-ttu-id="8a7b8-171">Pokud se zařízení HoloLens 2 nespustilo správně nebo pokud průvodce pokročilým obnovením nemůže zařízení rozpoznat, bude pravděpodobně nutné toto zařízení umístit do režimu obnovení:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="8a7b8-172">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="8a7b8-173">Stiskněte a držte tlačítko **napájení** po dobu 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="8a7b8-174">Všechny diody LED by se měly vypnout.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="8a7b8-175">Při stisknutí tlačítka **hlasitosti** stiskněte a uvolněte tlačítko **napájení** a spusťte zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="8a7b8-176">Počkejte 15 sekund a pak uvolněte tlačítko **hlasitosti** .</span><span class="sxs-lookup"><span data-stu-id="8a7b8-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="8a7b8-177">Rozsvítí se jenom střední LED z pěti diod LED.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="8a7b8-178">Připojte zařízení k hostitelskému počítači a otevřete Správce zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="8a7b8-179">(Pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a pak vyberte **Správce zařízení**.) Ujistěte se, že se zařízení správně vyčísluje jako Microsoft HoloLens, jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="8a7b8-181">Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Obrazovka pro vyčištění paměti HoloLens 2 – vyčistit](images/ARC2.png)

6. <span data-ttu-id="8a7b8-183">Vyberte zařízení HoloLens 2 v uživatelském rozhraní doprovodné aplikace pro pokročilé obnovení a podle pokynů dokončete znovu blesk.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="8a7b8-184">Poradce při potížích s pokročilým obnovením</span><span class="sxs-lookup"><span data-stu-id="8a7b8-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="8a7b8-185">Před pokusem o spuštění aplikace Flash se ujistěte, že se na zařízení účtuje 40% nebo víc.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="8a7b8-186">Ověřte, že je zařízení odemknuté.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="8a7b8-187">Pokud ARC zařízení nerozpozná, ujistěte se, že se k němu můžete připojit pomocí Průzkumníka souborů na svém počítači.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="8a7b8-188">Pokud nemůžete;</span><span class="sxs-lookup"><span data-stu-id="8a7b8-188">If you cannot;</span></span>

    1.  <span data-ttu-id="8a7b8-189">Je možné, že vaše zařízení může mít zásady USB, které toto připojení zakáže.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="8a7b8-190">V takovém případě zkuste použít [režim ručního blikání](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="8a7b8-191">Pokud neexistují žádné zásady, zkuste použít jiný kabel USB.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="8a7b8-192">Ověřte, že zařízení nezobrazuje [vzorek LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="8a7b8-193">Stáhnout oblouk bez použití App Storu</span><span class="sxs-lookup"><span data-stu-id="8a7b8-193">Download ARC without using the app store</span></span>

<span data-ttu-id="8a7b8-194">Pokud IT prostředí zabraňuje použití aplikace pro Windows Store nebo omezuje přístup k prodejnímu obchodu, může správce IT tuto aplikaci zpřístupnit prostřednictvím cesty nasazení offline.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="8a7b8-195">Správci IT mohou tuto aplikaci také distribuovat prostřednictvím System Center Configuration Manager (SCCM) nebo Intune.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="8a7b8-196">Tato příručka se zaměřuje na pokročilého Průvodce obnovením, ale tento postup je možné použít i pro jiné aplikace v režimu offline.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="8a7b8-197">Pokud chcete povolit cestu nasazení, postupujte podle těchto kroků:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="8a7b8-198">Přejít na [Microsoft Store pro firmy](https://businessstore.microsoft.com) a přihlaste se pomocí Azure Active Directory identity.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="8a7b8-199">Přejít na **Správa – nastavení**.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="8a7b8-200">Zapnutí možnosti **Zobrazit offline aplikace** v rámci **nakupování**</span><span class="sxs-lookup"><span data-stu-id="8a7b8-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="8a7b8-201">Přejděte do **obchodu pro moji skupinu a** vyhledejte Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="8a7b8-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="8a7b8-202">Změňte **Typ licence na** **_offline_ a vyberte *_* Spravovat.**</span><span class="sxs-lookup"><span data-stu-id="8a7b8-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="8a7b8-203">V **části Stáhnout balíček pro offline použití** vyberte druhé modré **tlačítko** Stáhnout.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="8a7b8-204">Ujistěte se, že je přípona *souboru .appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="8a7b8-205">Pokud má stolní počítač v této fázi přístup k internetu, poklikejte na balíček a nainstalujte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="8a7b8-206">Pokud cílový počítač nemá připojení k internetu, postupujte následovně:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="8a7b8-207">Vyberte nekódované licence a pak vyberte **Vygenerovat licenci.**</span><span class="sxs-lookup"><span data-stu-id="8a7b8-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="8a7b8-208">V **části Požadované architektury** vyberte **Stáhnout.**</span><span class="sxs-lookup"><span data-stu-id="8a7b8-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="8a7b8-209">Pomocí nástroje DISM použijte balíček se závislostí a licencí.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="8a7b8-210">Z příkazového řádku správce spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="8a7b8-211">Číslo verze v tomto příkladu kódu nemusí odpovídat aktuálně dostupné verzi.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="8a7b8-212">Možná jste také zvolili jiné umístění pro stahování než v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="8a7b8-213">Proveďte všechny změny příkazu podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="8a7b8-214">Když plánujete použít Advanced Recovery Companion k offline instalaci FFU, může být užitečné stáhnout si image flash.</span><span class="sxs-lookup"><span data-stu-id="8a7b8-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="8a7b8-215">[**Stáhněte si aktuální image pro HoloLens 2.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="8a7b8-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="8a7b8-216">Další zdroje informací:</span><span class="sxs-lookup"><span data-stu-id="8a7b8-216">Other resources:</span></span>
- [<span data-ttu-id="8a7b8-217">Distribuce offline aplikací</span><span class="sxs-lookup"><span data-stu-id="8a7b8-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="8a7b8-218">Možnosti příkazového řádku pro údržbu balíčku aplikace DISM (.appx nebo .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="8a7b8-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
