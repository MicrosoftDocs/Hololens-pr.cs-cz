---
title: Připojení k Bluetooth a zařízením USB-C
description: Začínáme s připojením k zařízením Bluetooth a USB-C a příslušenstvím ze zařízení hybridní reality HoloLens
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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924175"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="b3f2e-103">Připojení k Bluetooth a zařízením USB-C</span><span class="sxs-lookup"><span data-stu-id="b3f2e-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="b3f2e-104">Spárování zařízení Bluetooth</span><span class="sxs-lookup"><span data-stu-id="b3f2e-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="b3f2e-105">HoloLens 2 podporuje následující třídy zařízení Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="b3f2e-106">[HID:](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="b3f2e-107">Myš</span><span class="sxs-lookup"><span data-stu-id="b3f2e-107">Mouse</span></span>
    - <span data-ttu-id="b3f2e-108">Klávesnice</span><span class="sxs-lookup"><span data-stu-id="b3f2e-108">Keyboard</span></span>
- <span data-ttu-id="b3f2e-109">Výstupní zvuková zařízení (A2DP)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="b3f2e-110">HoloLens 2 podporuje následující rozhraní API Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="b3f2e-111">Server [a klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) [POS](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="b3f2e-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="b3f2e-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="b3f2e-113">Možná budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné skutečně používat zařízení HID a</span><span class="sxs-lookup"><span data-stu-id="b3f2e-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="b3f2e-114">HoloLens (1. generace) podporuje následující třídy zařízení Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="b3f2e-115">Myš</span><span class="sxs-lookup"><span data-stu-id="b3f2e-115">Mouse</span></span>
- <span data-ttu-id="b3f2e-116">Klávesnice</span><span class="sxs-lookup"><span data-stu-id="b3f2e-116">Keyboard</span></span>
- [<span data-ttu-id="b3f2e-117">HoloLens (1. generace) clicker</span><span class="sxs-lookup"><span data-stu-id="b3f2e-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="b3f2e-118">Další typy zařízení Bluetooth, jako jsou mluvčí, náhlavní soupravy, smartphony a herní pady, mohou být uvedené jako dostupné v nastavení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="b3f2e-119">Tato zařízení ale nejsou v HoloLens (1. generace) podporovaná.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="b3f2e-120">Další informace najdete v článku [HoloLens Settings (Nastavení HoloLens)](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)uvádí zařízení jako dostupná, ale zařízení nefungují.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="b3f2e-121">Spárování klávesnice nebo myši Bluetooth</span><span class="sxs-lookup"><span data-stu-id="b3f2e-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="b3f2e-122">Zapněte klávesnici nebo myš a zajistěte, aby byla zjistitelná.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="b3f2e-123">Pokud chcete zjistit, jak zajistit, aby bylo zařízení zjistitelné, vyhledejte informace o zařízení (nebo jeho dokumentaci) nebo navštivte web výrobce.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="b3f2e-124">Pomocí gesta bloom (HoloLens (1. generace) nebo gesta spuštění (HoloLens 2) přejděte na **Start** a pak vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="b3f2e-125">Vyberte **Zařízení** a ujistěte se, že je zapnuté Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="b3f2e-126">Až se zobrazí název zařízení, vyberte **Spárovat** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="b3f2e-127">Zakázání Bluetooth</span><span class="sxs-lookup"><span data-stu-id="b3f2e-127">Disable Bluetooth</span></span>

<span data-ttu-id="b3f2e-128">Tento postup vypne komponenty RF rádia Bluetooth a zakáže všechny funkce Bluetooth na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="b3f2e-129">Pomocí gesta bloom (HoloLens (1. generace)) nebo gesta spuštění (HoloLens 2) přejděte na **Start** a pak vyberte **Nastavení**  >  **Zařízení.**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="b3f2e-130">Přesuňte posuvník  pro Bluetooth **do** pozice Vypnuto.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="b3f2e-131">HoloLens 2: Připojení zařízení USB-C</span><span class="sxs-lookup"><span data-stu-id="b3f2e-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="b3f2e-132">HoloLens 2 podporuje následující třídy zařízení USB-C:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="b3f2e-133">Velkokapamová úložná zařízení (například kryptografický disk)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="b3f2e-134">Ethernetové adaptéry (včetně ethernetového a zpoplatnění)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="b3f2e-135">Digitální zvukové adaptéry USB-C-to-3,5mm</span><span class="sxs-lookup"><span data-stu-id="b3f2e-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="b3f2e-136">Digitální zvukové náhlavní soupravy USB-C (včetně adaptérů náhlavní soupravy a zpoplatnění)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="b3f2e-137">Externí mikrofony USB-C ([Windows Holographic, verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a novější)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="b3f2e-138">Drátová myš</span><span class="sxs-lookup"><span data-stu-id="b3f2e-138">Wired mouse</span></span>
- <span data-ttu-id="b3f2e-139">Drátová klávesnice</span><span class="sxs-lookup"><span data-stu-id="b3f2e-139">Wired keyboard</span></span>
- <span data-ttu-id="b3f2e-140">Kombinované rozbočovače PD (USB A a PD)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="b3f2e-141">V reakci na zpětnou vazbu od zákazníků jsme povolili omezenou podporu mobilního připojení, které je připojeno přímo k HoloLens přes USB-C.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="b3f2e-142">Další informace najdete v tématu Připojení k mobilní síti a [5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="b3f2e-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="b3f2e-143">Podpora externího mikrofonu USB-C</span><span class="sxs-lookup"><span data-stu-id="b3f2e-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3f2e-144">Když zapojíte mikrofon USB, nenastaví **se automaticky jako vstupní zařízení.**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="b3f2e-145">Při zapojení do sady konektorů USB-C uživatelé sledují, že zvuk této kabeláže se automaticky přesměruje na konektory, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad libovolným jiným vstupním zařízením.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="b3f2e-146">**Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="b3f2e-147">Externí mikrofony není možné používat v buildech před [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) nebo vyšší.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="b3f2e-148">Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí panelu **nastavení** Zvuk.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="b3f2e-149">Mikrofony USB-C je možné použít k volání, nahrávání atd.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="b3f2e-150">Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Nastavení zvuku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="b3f2e-152">Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="b3f2e-153">Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="b3f2e-154">Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="b3f2e-155">Volba Výchozí **komunikace** znamená, že externí mikrofon se použije ve vzdáleném asistenci a dalších komunikačních aplikacích, ale pole Mikrofon HoloLens se může používat i pro jiné úlohy.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavení výchozího nastavení mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="b3f2e-158">A co podpora mikrofonu Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="b3f2e-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="b3f2e-159">Na HoloLens 2 se bohužel stále nepodporují mikrofony Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="b3f2e-160">Rozbočovače USB-C</span><span class="sxs-lookup"><span data-stu-id="b3f2e-160">USB-C Hubs</span></span>

<span data-ttu-id="b3f2e-161">Někteří uživatelé možná budou muset připojit více zařízení najednou.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="b3f2e-162">Pro uživatele, kteří chtějí používat mikrofon [USB-C](#usb-c-external-microphone-support) společně s jiným připojeným zařízením, mohou být rozbočovače USB-C vhodné pro potřeby zákazníka.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="b3f2e-163">Microsoft tato zařízení netestoval, ani nemůžeme doporučit konkrétní značky.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="b3f2e-164">**Požadavky na rozbočovač USB-C a připojená zařízení:**</span><span class="sxs-lookup"><span data-stu-id="b3f2e-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="b3f2e-165">Připojená zařízení nesmí vyžadovat instalaci ovladače.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="b3f2e-166">Celkový příkon všech připojených zařízení musí být nižší než 4,5 W.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="b3f2e-167">Připojení k Miracastu</span><span class="sxs-lookup"><span data-stu-id="b3f2e-167">Connect to Miracast</span></span>

<span data-ttu-id="b3f2e-168">Pokud chcete použít Miracast, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="b3f2e-169">Proveďte některou z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="b3f2e-169">Do one of the following:</span></span>  

   - <span data-ttu-id="b3f2e-170">Otevřete **nabídku Start** a vyberte **ikonu** Zobrazit.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="b3f2e-171">Při pohledu na nabídku **Start** řekněte "Připojit".</span><span class="sxs-lookup"><span data-stu-id="b3f2e-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="b3f2e-172">V seznamu zařízení, která se zobrazí, vyberte dostupné zařízení.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="b3f2e-173">Dokončete párování a zahajte projektování.</span><span class="sxs-lookup"><span data-stu-id="b3f2e-173">Complete the pairing to begin projecting.</span></span>
