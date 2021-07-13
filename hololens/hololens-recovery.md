---
title: Restartování, resetování nebo obnovení HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: jak použít pokročilého průvodce obnovením k blikání obrázku na HoloLens 2.
keywords: postupy, restartování, resetování, obnovení, vynucené resetování, tiché resetování, cyklus napájení, HoloLens, vypnutí, oblouk, pokročilý průvodce obnovením
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
ms.openlocfilehash: 0124453ef9e3b21722acaf2c6b438ebdfbd65043
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635938"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="daed7-104">restartování, resetování nebo obnovení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="daed7-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="daed7-105">Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="daed7-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="daed7-106">[Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="daed7-107">použijte [nabíječku a kabel typu USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) , který byl dodán s HoloLens 2, jako je to nejlepší způsob, jak zařízení účtovat.</span><span class="sxs-lookup"><span data-stu-id="daed7-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="daed7-108">Nabíječka dodá 18W výkonu (9V v 2A).</span><span class="sxs-lookup"><span data-stu-id="daed7-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="daed7-109">když použijete dodanou nabíječku zdí, zařízení HoloLens 2 můžou baterii navýšit na plnou dobu během méně než 65 minut, když je zařízení v pohotovostním režimu.</span><span class="sxs-lookup"><span data-stu-id="daed7-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="daed7-110">Pokud tato příslušenství nejsou k dispozici, zajistěte, aby nabíječka, která je k dispozici, mohla podporovat aspoň 15W napájení.</span><span class="sxs-lookup"><span data-stu-id="daed7-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="daed7-111">Pokud je to možné, nepoužívejte počítač k navýšení kapacity zařízení přes USB, což je pomalé.</span><span class="sxs-lookup"><span data-stu-id="daed7-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="daed7-112">Pokud je zařízení správně spuštěno a běží, existují tři způsoby, jak ověřit úroveň nabití baterie:</span><span class="sxs-lookup"><span data-stu-id="daed7-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="daed7-113">z hlavní nabídky uživatelského rozhraní HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="daed7-114">Podívejte se, že indikátor LED blízko tlačítka napájení (pro poplatek 40 – Percent) by se měl zobrazit aspoň dva Solid diody LED.</span><span class="sxs-lookup"><span data-stu-id="daed7-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="daed7-115">Když se zařízení účtuje, indikátory baterie až do indikace aktuální úrovně zpoplatnění.</span><span class="sxs-lookup"><span data-stu-id="daed7-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="daed7-116">Poslední světlo zmizí a odznačí aktivní zpoplatnění.</span><span class="sxs-lookup"><span data-stu-id="daed7-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="daed7-117">když je vaše HoloLens zapnutá, indikátor baterie zobrazí úroveň baterie v pěti přírůstcích.</span><span class="sxs-lookup"><span data-stu-id="daed7-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="daed7-118">Pokud je zapnutá jenom jedna z pěti světel, úroveň baterie je nižší než 20 procent.</span><span class="sxs-lookup"><span data-stu-id="daed7-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="daed7-119">Pokud je úroveň baterie kriticky nízká a pokusíte se zařízení zapnout, bude se krátce rozsvítit v jednom světle a pak se vrátí.</span><span class="sxs-lookup"><span data-stu-id="daed7-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="daed7-120">na hostitelském počítači otevřete **průzkumníka souborů** a hledejte zařízení HoloLens 2 na levé straně **tohoto počítače**.</span><span class="sxs-lookup"><span data-stu-id="daed7-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="daed7-121">Pravým tlačítkem myši klikněte na zařízení a vyberte **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="daed7-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="daed7-122">V dialogovém okně se zobrazí úroveň nabití baterie.</span><span class="sxs-lookup"><span data-stu-id="daed7-122">A dialog box will show the battery charge level.</span></span>

   ![obrazovka vlastností HoloLens 2 zobrazuje úroveň změny baterie](images/ResetRecovery2.png)

<span data-ttu-id="daed7-124">Pokud se zařízení nedá spustit do nabídky po spuštění, poznamenejte si vzhled INDIKÁTORu a výčet zařízení na hostitelském počítači.</span><span class="sxs-lookup"><span data-stu-id="daed7-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="daed7-125">Pak postupujte podle pokynů [Průvodce odstraňováním potíží](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="daed7-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="daed7-126">Pokud se stav zařízení neshoduje s žádným ze stavů uvedených v Průvodci odstraňováním potíží, proveďte [postupnou operaci resetování](hololens-recovery.md#hard-reset-procedure) u zařízení připojeného k napájení, ne do hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="daed7-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="daed7-127">Počkejte alespoň jednu hodinu, než se zařízení doúčtuje.</span><span class="sxs-lookup"><span data-stu-id="daed7-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="daed7-128">Resetování zařízení</span><span class="sxs-lookup"><span data-stu-id="daed7-128">Reset the device</span></span>

<span data-ttu-id="daed7-129">Za určitých okolností může být nutné ručně resetovat zařízení bez použití uživatelského rozhraní softwaru.</span><span class="sxs-lookup"><span data-stu-id="daed7-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="daed7-130">Standardní postup</span><span class="sxs-lookup"><span data-stu-id="daed7-130">Standard procedure</span></span>

1. <span data-ttu-id="daed7-131">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="daed7-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="daed7-132">Stiskněte a držte tlačítko **napájení** po dobu 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="daed7-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="daed7-133">Všechny diody LED by měly být vypnuté.</span><span class="sxs-lookup"><span data-stu-id="daed7-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="daed7-134">Počkejte 2-3 sekund a potom stiskněte tlačítko **napájení** .</span><span class="sxs-lookup"><span data-stu-id="daed7-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="daed7-135">Indikátory LED, které se blíží tlačítku napájení, se budou rozsvítit a zařízení se začne spouštět.</span><span class="sxs-lookup"><span data-stu-id="daed7-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="daed7-136">Připojení zařízení na hostitelském počítači a pak otevřete Správce zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="daed7-137">(pro Windows 10 stiskněte klávesu **Windows** a pak klíč **X** a potom vyberte **Správce zařízení**.) ujistěte se, že se zařízení správně zobrazuje tak, jak *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="daed7-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![MicrosoftHoloLensRecovery 2 devive manager HoloLens](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="daed7-139">Postup pevného resetu</span><span class="sxs-lookup"><span data-stu-id="daed7-139">Hard-reset procedure</span></span>

<span data-ttu-id="daed7-140">Pokud standardní procedura resetování nefungovala, použijte postup pevného resetování:</span><span class="sxs-lookup"><span data-stu-id="daed7-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="daed7-141">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="daed7-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="daed7-142">U 15 sekund podržíte tlačítka **hlasitosti dolů**  +   .</span><span class="sxs-lookup"><span data-stu-id="daed7-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="daed7-143">Zařízení se automaticky restartuje.</span><span class="sxs-lookup"><span data-stu-id="daed7-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="daed7-144">Připojení zařízení na hostitelský počítač.</span><span class="sxs-lookup"><span data-stu-id="daed7-144">Connect the device to the host PC.</span></span>


5. <span data-ttu-id="daed7-145">otevřete Správce zařízení (pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a potom vyberte **Správce zařízení**).</span><span class="sxs-lookup"><span data-stu-id="daed7-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="daed7-146">ujistěte se, že se zařízení správně zobrazuje tak, jak *Microsoft HoloLens* , jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="daed7-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery zařízení správce 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="daed7-148">Vyčistit a znovu zablikat zařízení</span><span class="sxs-lookup"><span data-stu-id="daed7-148">Clean-reflash the device</span></span>

<span data-ttu-id="daed7-149">v mimořádných situacích možná budete muset "vyčistit-bliknutí" HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="daed7-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="daed7-150">Upozorňujeme, že příkaz vyčistit-reflash se neočekává vlivem na následující problémy:</span><span class="sxs-lookup"><span data-stu-id="daed7-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="daed7-151">Zobrazit sjednocení barev</span><span class="sxs-lookup"><span data-stu-id="daed7-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="daed7-152">Spouštění se zvukem, ale bez zobrazení výstupu</span><span class="sxs-lookup"><span data-stu-id="daed7-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="daed7-153">vzor LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="daed7-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="daed7-154">Přehřívání</span><span class="sxs-lookup"><span data-stu-id="daed7-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="daed7-155">Selhání operačního systému (které se liší od selhání aplikace)</span><span class="sxs-lookup"><span data-stu-id="daed7-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="daed7-156">Existují dva způsoby, jak zařízení znovu zablikat.</span><span class="sxs-lookup"><span data-stu-id="daed7-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="daed7-157">pro obojí musíte nejdřív [nainstalovat rozšířeného průvodce obnovením z Windows storu](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="daed7-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="daed7-158">Pokud vaše zařízení budete znovu zablikat, budou smazána všechna vaše osobní data, aplikace a nastavení, včetně informací o resetování čipu TPM.</span><span class="sxs-lookup"><span data-stu-id="daed7-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="daed7-159">Ve výchozím nastavení je průvodce pokročilým obnovením nastaven na stažení nejnovějšího buildu pro vydání funkce. Přečtěte si zde [poznámky k verzi](hololens-release-notes.md#) , kde najdete další informace o nejnovější verzi funkce.</span><span class="sxs-lookup"><span data-stu-id="daed7-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="daed7-160">pokud chcete získat nejnovější HoloLens 2 úplný balíček Flash Update (FFU), abyste mohli svoje zařízení znovu zablikat prostřednictvím pokročilého průvodce obnovením, [klikněte sem a stáhněte si nejnovější měsíční obrázek HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="daed7-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="daed7-161">Tato verze je nejnovější všeobecně dostupná sestavení.</span><span class="sxs-lookup"><span data-stu-id="daed7-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="daed7-162">než začnete s postupem přeblesku, ujistěte se, že je aplikace nainstalovaná a spuštěná na počítači s Windows 10 a připravená k detekci zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="daed7-163">také se ujistěte, že se HoloLens účtuje minimálně 40%.</span><span class="sxs-lookup"><span data-stu-id="daed7-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![snímek obrazovky HoloLens 2 pro vyčištění paměti](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="daed7-165">Běžný postup</span><span class="sxs-lookup"><span data-stu-id="daed7-165">Normal procedure</span></span>

1. <span data-ttu-id="daed7-166">když je zařízení HoloLens spuštěné, připojte ho k počítači Windows 10, kde jste předtím otevřeli rozšířenou aplikaci pro obnovení.</span><span class="sxs-lookup"><span data-stu-id="daed7-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="daed7-167">Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:</span><span class="sxs-lookup"><span data-stu-id="daed7-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![úvodní obrazovka HoloLens 2 pro vyčištění](images/ARC2.png)

3. <span data-ttu-id="daed7-169">vyberte zařízení HoloLens 2 v rozšířeném uživatelském rozhraní aplikace Companion pro obnovení a podle pokynů dokončete znovu blesk.</span><span class="sxs-lookup"><span data-stu-id="daed7-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="daed7-170">Ruční procedura</span><span class="sxs-lookup"><span data-stu-id="daed7-170">Manual procedure</span></span>

<span data-ttu-id="daed7-171">pokud se HoloLens 2 nespustila správně nebo pokud průvodce pokročilým obnovením nemůže zařízení rozpoznat, bude pravděpodobně nutné toto zařízení umístit do režimu obnovení:</span><span class="sxs-lookup"><span data-stu-id="daed7-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="daed7-172">Odpojte kabel Type-C a odpojte zařízení od zdroje napájení nebo hostitelského počítače.</span><span class="sxs-lookup"><span data-stu-id="daed7-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="daed7-173">Stiskněte a držte tlačítko **napájení** po dobu 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="daed7-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="daed7-174">Všechny diody LED by se měly vypnout.</span><span class="sxs-lookup"><span data-stu-id="daed7-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="daed7-175">Při stisknutí tlačítka **hlasitosti** stiskněte a uvolněte tlačítko **napájení** a spusťte zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="daed7-176">Počkejte 15 sekund a pak uvolněte tlačítko **hlasitosti** .</span><span class="sxs-lookup"><span data-stu-id="daed7-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="daed7-177">Rozsvítí se jenom střední LED z pěti diod LED.</span><span class="sxs-lookup"><span data-stu-id="daed7-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="daed7-178">Připojení zařízení na hostitelský počítač a otevřete Správce zařízení.</span><span class="sxs-lookup"><span data-stu-id="daed7-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="daed7-179">(pro Windows 10 stiskněte klávesu **Windows** a pak stiskněte klávesu **X** a potom vyberte **Správce zařízení**.) ujistěte se, že se zařízení správně zobrazuje tak, jak Microsoft HoloLens, jak je znázorněno na následujícím obrázku:</span><span class="sxs-lookup"><span data-stu-id="daed7-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="daed7-181">Zařízení se automaticky rozpozná a v uživatelském rozhraní Průvodce pokročilé aplikace pro obnovení se spustí proces aktualizace:</span><span class="sxs-lookup"><span data-stu-id="daed7-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 – vyčistit obrazovku](images/ARC2.png)

6. <span data-ttu-id="daed7-183">vyberte zařízení HoloLens 2 v uživatelském rozhraní pomocníka pro zotavení po obnovení a podle pokynů dokončete znovu blesk.</span><span class="sxs-lookup"><span data-stu-id="daed7-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="daed7-184">Poradce při potížích s pokročilým obnovením</span><span class="sxs-lookup"><span data-stu-id="daed7-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="daed7-185">Před pokusem o spuštění aplikace Flash se ujistěte, že se na zařízení účtuje 40% nebo víc.</span><span class="sxs-lookup"><span data-stu-id="daed7-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="daed7-186">Ověřte, že je zařízení odemknuté.</span><span class="sxs-lookup"><span data-stu-id="daed7-186">Check your device is unlocked.</span></span>

1. <span data-ttu-id="daed7-187">Ověřte, že je zařízení zapojené přímo do hostitelského počítače, ne z rozbočovače.</span><span class="sxs-lookup"><span data-stu-id="daed7-187">Check your device is plugged directly into the host PC, not a hub.</span></span>

1. <span data-ttu-id="daed7-188">pokud se zařízení nezobrazuje jako zařízení pro obnovení HoloLens/HoloLens v části ovladače Universal Serial Bus, zaškrtněte:</span><span class="sxs-lookup"><span data-stu-id="daed7-188">If your device is not showing as a HoloLens/HoloLens Recovery device under Universal Serial Bus Drivers, check:</span></span>
    1. <span data-ttu-id="daed7-189">**Porty** jako zařízení s rozhraním Qualcomm HS – USB</span><span class="sxs-lookup"><span data-stu-id="daed7-189">**Ports**, as a Qualcomm HS-USB device</span></span>
    1.   <span data-ttu-id="daed7-190">**Jiná zařízení**, jako QUSB_BULK zařízení – v hostitelském počítači chybí ovladače potřebné k detekci HoloLens.</span><span class="sxs-lookup"><span data-stu-id="daed7-190">**Other Devices**, as a QUSB_BULK device - your host PC is missing the necessary drivers to detect your HoloLens.</span></span> <span data-ttu-id="daed7-191">klikněte pravým tlačítkem a vyberte aktualizovat ovladač a vyhledejte ovladače online nebo [zaškrtněte volitelné aktualizace v nastaveních web Windows Update](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span><span class="sxs-lookup"><span data-stu-id="daed7-191">Right click and select Update Driver and search for drivers online or [check Optional Updates in your Windows Update settings](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674).</span></span> <span data-ttu-id="daed7-192">Po stažení ovladače by měl být oblouk schopný ho detekovat.</span><span class="sxs-lookup"><span data-stu-id="daed7-192">After the driver is downloaded, ARC should be able to detect it.</span></span>
 
1. <span data-ttu-id="daed7-193">Pokud ARC zařízení nerozpozná, ujistěte se, že se k němu můžete připojit pomocí Průzkumníka souborů na svém počítači.</span><span class="sxs-lookup"><span data-stu-id="daed7-193">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="daed7-194">Pokud nemůžete;</span><span class="sxs-lookup"><span data-stu-id="daed7-194">If you cannot;</span></span>

    1.  <span data-ttu-id="daed7-195">Je možné, že vaše zařízení může mít zásady USB, které toto připojení zakáže.</span><span class="sxs-lookup"><span data-stu-id="daed7-195">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="daed7-196">V takovém případě zkuste použít [režim ručního blikání](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="daed7-196">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="daed7-197">Pokud neexistují žádné zásady, zkuste použít jiný kabel USB.</span><span class="sxs-lookup"><span data-stu-id="daed7-197">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="daed7-198">Ověřte, že zařízení nezobrazuje [vzorek LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="daed7-198">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="daed7-199">Stáhnout oblouk bez použití App Storu</span><span class="sxs-lookup"><span data-stu-id="daed7-199">Download ARC without using the app store</span></span>

<span data-ttu-id="daed7-200">pokud it prostředí zabraňuje použití aplikace Windows storu nebo omezuje přístup k prodejnímu obchodu, může správce IT tuto aplikaci zpřístupnit prostřednictvím cesty nasazení offline.</span><span class="sxs-lookup"><span data-stu-id="daed7-200">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="daed7-201">Správci IT můžou tuto aplikaci také distribuovat prostřednictvím System Center Configuration Manager (SCCM) nebo Intune.</span><span class="sxs-lookup"><span data-stu-id="daed7-201">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="daed7-202">Tato příručka se zaměřuje na Advanced Recovery Companion, ale tento proces je možné použít i pro jiné "offline" aplikace.</span><span class="sxs-lookup"><span data-stu-id="daed7-202">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="daed7-203">Pokud chcete povolit cestu nasazení, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="daed7-203">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="daed7-204">Přejděte na [Microsoft Store pro firmy](https://businessstore.microsoft.com) a přihlaste se pomocí Azure Active Directory identity.</span><span class="sxs-lookup"><span data-stu-id="daed7-204">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="daed7-205">Přejděte na **Spravovat – Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="daed7-205">Go to **Manage – Settings**.</span></span> <span data-ttu-id="daed7-206">V části **Nákupní prostředí zapněte Zobrazit offline** **aplikace.**</span><span class="sxs-lookup"><span data-stu-id="daed7-206">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="daed7-207">Přejděte do **obchodu pro moji skupinu a** vyhledejte Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="daed7-207">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="daed7-208">Změňte **Typ licence na** **_offline_ a vyberte *_* Spravovat.**</span><span class="sxs-lookup"><span data-stu-id="daed7-208">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="daed7-209">V **části Stáhnout balíček pro offline použití** vyberte druhé modré **tlačítko** Stáhnout.</span><span class="sxs-lookup"><span data-stu-id="daed7-209">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="daed7-210">Ujistěte se, že je přípona *souboru .appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="daed7-210">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="daed7-211">Pokud má stolní počítač v této fázi přístup k internetu, poklikejte na balíček a nainstalujte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="daed7-211">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="daed7-212">Pokud cílový počítač nemá připojení k internetu, postupujte následovně:</span><span class="sxs-lookup"><span data-stu-id="daed7-212">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="daed7-213">Vyberte nekódované licence a pak vyberte **Vygenerovat licenci.**</span><span class="sxs-lookup"><span data-stu-id="daed7-213">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="daed7-214">V **části Požadované architektury** vyberte **Stáhnout.**</span><span class="sxs-lookup"><span data-stu-id="daed7-214">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="daed7-215">Pomocí nástroje DISM použijte balíček se závislostí a licencí.</span><span class="sxs-lookup"><span data-stu-id="daed7-215">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="daed7-216">Z příkazového řádku správce spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="daed7-216">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="daed7-217">Číslo verze v tomto příkladu kódu nemusí odpovídat aktuálně dostupné verzi.</span><span class="sxs-lookup"><span data-stu-id="daed7-217">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="daed7-218">Možná jste také zvolili jiné umístění pro stahování než v tomto příkladu.</span><span class="sxs-lookup"><span data-stu-id="daed7-218">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="daed7-219">Proveďte všechny změny příkazu podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="daed7-219">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="daed7-220">Pokud máte v plánu použít Advanced Recovery Companion k offline instalaci FFU, může být užitečné stáhnout si flash image.</span><span class="sxs-lookup"><span data-stu-id="daed7-220">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="daed7-221">[**Stáhněte si aktuální image pro HoloLens 2.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="daed7-221">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="daed7-222">Další zdroje informací:</span><span class="sxs-lookup"><span data-stu-id="daed7-222">Other resources:</span></span>
- [<span data-ttu-id="daed7-223">Distribuce offline aplikací</span><span class="sxs-lookup"><span data-stu-id="daed7-223">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="daed7-224">Možnosti příkazového řádku pro údržbu balíčku aplikace DISM (.appx nebo .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="daed7-224">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
