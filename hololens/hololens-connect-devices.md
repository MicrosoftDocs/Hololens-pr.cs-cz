---
title: Připojení k zařízením Bluetooth a USB-C
description: Začněte s připojením k zařízením Bluetooth a USB-C a příslušenstvím ze zařízení s technologií HoloLens hybridních realit.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379283"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="61b62-103">Připojení k zařízením Bluetooth a USB-C</span><span class="sxs-lookup"><span data-stu-id="61b62-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="61b62-104">Párování zařízení Bluetooth</span><span class="sxs-lookup"><span data-stu-id="61b62-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="61b62-105">HoloLens 2 podporuje následující třídy zařízení Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="61b62-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="61b62-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="61b62-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="61b62-107">Myš</span><span class="sxs-lookup"><span data-stu-id="61b62-107">Mouse</span></span>
    - <span data-ttu-id="61b62-108">Klávesnice</span><span class="sxs-lookup"><span data-stu-id="61b62-108">Keyboard</span></span>
- <span data-ttu-id="61b62-109">Výstupní zvukové zařízení (A2DP)</span><span class="sxs-lookup"><span data-stu-id="61b62-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="61b62-110">HoloLens 2 podporuje následující rozhraní API Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="61b62-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="61b62-111">[Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) a [klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) GATT</span><span class="sxs-lookup"><span data-stu-id="61b62-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="61b62-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="61b62-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="61b62-113">Možná budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store ke skutečnému používání zařízení se standardem HID a GATT.</span><span class="sxs-lookup"><span data-stu-id="61b62-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="61b62-114">HoloLens (1. generace) podporuje následující třídy zařízení Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="61b62-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="61b62-115">Myš</span><span class="sxs-lookup"><span data-stu-id="61b62-115">Mouse</span></span>
- <span data-ttu-id="61b62-116">Klávesnice</span><span class="sxs-lookup"><span data-stu-id="61b62-116">Keyboard</span></span>
- [<span data-ttu-id="61b62-117">HoloLens (1. generace) – kliknutí</span><span class="sxs-lookup"><span data-stu-id="61b62-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="61b62-118">Další typy zařízení Bluetooth, jako jsou například reproduktory, sluchátka s mikrofony, smartphony a Game pad, mohou být v nastaveních HoloLens uvedeny jako dostupné.</span><span class="sxs-lookup"><span data-stu-id="61b62-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="61b62-119">Tato zařízení ale nejsou podporovaná na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="61b62-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="61b62-120">Další informace najdete v tématu [Nastavení HoloLens seznam zařízení, která jsou k dispozici, ale zařízení nefungují](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="61b62-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="61b62-121">Párování klávesnice nebo myši Bluetooth</span><span class="sxs-lookup"><span data-stu-id="61b62-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="61b62-122">Zapněte klávesnici nebo myš a nastavte ji jako zjistitelnou.</span><span class="sxs-lookup"><span data-stu-id="61b62-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="61b62-123">Pokud se chcete dozvědět, jak zařízení zjistit, vyhledejte informace na zařízení (nebo jeho dokumentaci) nebo navštivte web výrobce.</span><span class="sxs-lookup"><span data-stu-id="61b62-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="61b62-124">Použijte gesto Bloom (HoloLens (1. gen)) nebo gesto Start (HoloLens 2), abyste mohli přejít na **Start** a pak vybrat **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="61b62-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="61b62-125">Vyberte **zařízení** a ujistěte se, že je Bluetooth zapnuté.</span><span class="sxs-lookup"><span data-stu-id="61b62-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="61b62-126">Když se zobrazí název zařízení, vyberte **spárovat** a pak postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="61b62-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="61b62-127">Zakázat Bluetooth</span><span class="sxs-lookup"><span data-stu-id="61b62-127">Disable Bluetooth</span></span>

<span data-ttu-id="61b62-128">Tento postup vypne součásti RF v přepínači Bluetooth a zakáže všechny funkce Bluetooth na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61b62-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="61b62-129">Použijte gesto Bloom (HoloLens (1. generace)) nebo gesto Start (HoloLens 2), abyste mohli přejít na **Start** a pak vybrat **Nastavení**  >  **zařízení**.</span><span class="sxs-lookup"><span data-stu-id="61b62-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="61b62-130">Přesuňte přepínač posuvníku pro **Bluetooth** do **vypnuté** polohy.</span><span class="sxs-lookup"><span data-stu-id="61b62-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="61b62-131">HoloLens 2: připojení zařízení USB-C</span><span class="sxs-lookup"><span data-stu-id="61b62-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="61b62-132">HoloLens 2 podporuje následující třídy zařízení USB-C:</span><span class="sxs-lookup"><span data-stu-id="61b62-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="61b62-133">Velkokapacitní úložná zařízení (například jednotky s palec)</span><span class="sxs-lookup"><span data-stu-id="61b62-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="61b62-134">Adaptéry sítě Ethernet (včetně zpoplatnění Ethernet Plus)</span><span class="sxs-lookup"><span data-stu-id="61b62-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="61b62-135">Digitální zvukové adaptéry USB-C-do-3.5 mm</span><span class="sxs-lookup"><span data-stu-id="61b62-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="61b62-136">Sluchátka s digitálním zvukem USB-C (včetně adaptérů sluchátek a zpoplatnění)</span><span class="sxs-lookup"><span data-stu-id="61b62-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="61b62-137">Externí mikrotelefony USB-C ([Windows holografick, verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší)</span><span class="sxs-lookup"><span data-stu-id="61b62-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="61b62-138">Kabelová myš</span><span class="sxs-lookup"><span data-stu-id="61b62-138">Wired mouse</span></span>
- <span data-ttu-id="61b62-139">Drátová klávesnice</span><span class="sxs-lookup"><span data-stu-id="61b62-139">Wired keyboard</span></span>
- <span data-ttu-id="61b62-140">Kombinovaná centra PD (USB A Plus PD zpoplatněná)</span><span class="sxs-lookup"><span data-stu-id="61b62-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="61b62-141">V reakci na zpětnou vazbu od zákazníků jsme povolili omezené podpory pro mobilní připojení, které jsou připojené přímo k HoloLens přes USB-C.</span><span class="sxs-lookup"><span data-stu-id="61b62-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="61b62-142">Další informace najdete v tématu [připojení k mobilním a 5g](hololens-cellular.md) .</span><span class="sxs-lookup"><span data-stu-id="61b62-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="61b62-143">Podpora externích mikrofonů USB-C</span><span class="sxs-lookup"><span data-stu-id="61b62-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61b62-144">Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**.</span><span class="sxs-lookup"><span data-stu-id="61b62-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="61b62-145">Při zapojení do sady sluchátek USB-C se uživatelům zobrazí, že se zvuk z sluchátka automaticky přesměruje na sluchátka, ale operační systém HoloLens nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení.</span><span class="sxs-lookup"><span data-stu-id="61b62-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="61b62-146">**Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**</span><span class="sxs-lookup"><span data-stu-id="61b62-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="61b62-147">Externí mikrotelefony nejde v buildech použít před [Windows holografickou verzí 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší.</span><span class="sxs-lookup"><span data-stu-id="61b62-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="61b62-148">Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C.</span><span class="sxs-lookup"><span data-stu-id="61b62-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="61b62-149">Mikrofony USB-C lze použít pro volání, záznam atd.</span><span class="sxs-lookup"><span data-stu-id="61b62-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="61b62-150">Otevřete aplikaci **Nastavení** a vyberte **systémové**  >  **zvuky**.</span><span class="sxs-lookup"><span data-stu-id="61b62-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Nastavení zvuku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="61b62-152">Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.</span><span class="sxs-lookup"><span data-stu-id="61b62-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="61b62-153">Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.**</span><span class="sxs-lookup"><span data-stu-id="61b62-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="61b62-154">Volba **výchozí** znamená, že se externí mikrofon bude používat všude.</span><span class="sxs-lookup"><span data-stu-id="61b62-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="61b62-155">Zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a v dalších komunikačních aplikacích, ale pro jiné úkoly se může používat i pole mikrofonu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61b62-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavit výchozí mikrofon](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="61b62-158">Co je podpora mikrofonu Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="61b62-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="61b62-159">Technologie HoloLens 2 bohužel v současné době nepodporuje mikrofony Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="61b62-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="61b62-160">Řešení potíží s mikrofony USB-C</span><span class="sxs-lookup"><span data-stu-id="61b62-160">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="61b62-161">Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí.</span><span class="sxs-lookup"><span data-stu-id="61b62-161">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="61b62-162">Jedná se o problém s mikrofonem a ne s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="61b62-162">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="61b62-163">Při zapojení jednoho z těchto mikrofonů do HoloLens může dojít ke ztrátě zvuku.</span><span class="sxs-lookup"><span data-stu-id="61b62-163">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="61b62-164">Naštěstí je jednoduchá oprava.</span><span class="sxs-lookup"><span data-stu-id="61b62-164">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="61b62-165">V **Nastavení**  ->    ->  **zvuk** systému explicitně nastavte Vestavěné reproduktory **(zvukový ovladač analogové funkce)** jako **výchozí zařízení**.</span><span class="sxs-lookup"><span data-stu-id="61b62-165">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="61b62-166">HoloLens by si mělo pamatovat toto nastavení i v případě, že mikrofon odeberete a znovu připojíte později.</span><span class="sxs-lookup"><span data-stu-id="61b62-166">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a><span data-ttu-id="61b62-168">Rozbočovače USB-C</span><span class="sxs-lookup"><span data-stu-id="61b62-168">USB-C Hubs</span></span>

<span data-ttu-id="61b62-169">Někteří uživatelé možná potřebují připojit více zařízení najednou.</span><span class="sxs-lookup"><span data-stu-id="61b62-169">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="61b62-170">Pro uživatele, kteří chtějí používat [mikrofon USB-c](#usb-c-external-microphone-support) spolu s jiným připojeným zařízením, můžou rozbočovače USB-c odpovídat potřebám zákazníka.</span><span class="sxs-lookup"><span data-stu-id="61b62-170">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="61b62-171">Společnost Microsoft tato zařízení netestovala, a proto nemůžeme doporučit žádné konkrétní značky.</span><span class="sxs-lookup"><span data-stu-id="61b62-171">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="61b62-172">**Požadavky na rozbočovač USB-C a připojená zařízení:**</span><span class="sxs-lookup"><span data-stu-id="61b62-172">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="61b62-173">Připojená zařízení nesmí vyžadovat instalaci ovladače.</span><span class="sxs-lookup"><span data-stu-id="61b62-173">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="61b62-174">Celkový výkon vykreslování všech připojených zařízení musí být nižší než 4,5 wattů.</span><span class="sxs-lookup"><span data-stu-id="61b62-174">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="61b62-175">Připojení k Miracast</span><span class="sxs-lookup"><span data-stu-id="61b62-175">Connect to Miracast</span></span>

<span data-ttu-id="61b62-176">Chcete-li použít Miracast, postupujte podle následujících kroků:</span><span class="sxs-lookup"><span data-stu-id="61b62-176">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="61b62-177">Proveďte některou z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="61b62-177">Do one of the following:</span></span>  

   - <span data-ttu-id="61b62-178">Otevřete nabídku **Start** a vyberte ikonu **Zobrazit** .</span><span class="sxs-lookup"><span data-stu-id="61b62-178">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="61b62-179">Řekněme, že při pohledui v nabídce **Start** Vydáte "připojit".</span><span class="sxs-lookup"><span data-stu-id="61b62-179">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="61b62-180">V seznamu zařízení, která se zobrazí, vyberte dostupné zařízení.</span><span class="sxs-lookup"><span data-stu-id="61b62-180">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="61b62-181">Zahajte párování pro zahájení projekce.</span><span class="sxs-lookup"><span data-stu-id="61b62-181">Complete the pairing to begin projecting.</span></span>
