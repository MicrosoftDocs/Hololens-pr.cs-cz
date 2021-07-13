---
title: Připojení mobilní a 5G
description: připojení k mobilním sítím z HoloLens zařízení se smíšenými realitami.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635836"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="b68c0-103">Připojení mobilní a 5G</span><span class="sxs-lookup"><span data-stu-id="b68c0-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="b68c0-104">HoloLens 2 podporuje dvě metody pro připojení k mobilním a 5G sítím:</span><span class="sxs-lookup"><span data-stu-id="b68c0-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="b68c0-105">Ad hoc síť Wi-Fi poskytovaná mobilním zařízením, které se běžně označuje jako "hotspot".</span><span class="sxs-lookup"><span data-stu-id="b68c0-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="b68c0-106">Omezená podpora pro připojená zařízení USB-C</span><span class="sxs-lookup"><span data-stu-id="b68c0-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="b68c0-107">HotSpot (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="b68c0-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="b68c0-108">Většinu potřeb mobilního připojení je možné splnit pomocí hotspotu.</span><span class="sxs-lookup"><span data-stu-id="b68c0-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="b68c0-109">HoloLens 2 wi-fi podporuje standard 802.11 ac, který může poskytovat požadavky na šířku pásma a latenci, které jsou nezbytné pro nejběžnější případy použití.</span><span class="sxs-lookup"><span data-stu-id="b68c0-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="b68c0-110">Wi-Fi je také bez kabelů a nabízí kompatibilitu s největším počtem mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="b68c0-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="b68c0-111">Připojení k hotspotu</span><span class="sxs-lookup"><span data-stu-id="b68c0-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="b68c0-112">Projděte si příručku zařízení, jak povolit režim hotspotu.</span><span class="sxs-lookup"><span data-stu-id="b68c0-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="b68c0-113">Povolte režim hotspotu, zadejte název sítě a také známé heslo.</span><span class="sxs-lookup"><span data-stu-id="b68c0-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="b68c0-114">v nastavení HoloLens 2 sítě vyhledejte síť wi-fi vytvořenou v kroku 2 a připojte se k ní.</span><span class="sxs-lookup"><span data-stu-id="b68c0-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="b68c0-115">Sdílení přes USB-C</span><span class="sxs-lookup"><span data-stu-id="b68c0-115">USB-C Tethering</span></span>

<span data-ttu-id="b68c0-116">Sdílení přes USB-C může poskytovat nižší latenci pro pokročilé úlohy, které ji potřebují.</span><span class="sxs-lookup"><span data-stu-id="b68c0-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="b68c0-117">[Vzdálené vykreslování Azure](https://azure.microsoft.com/services/remote-rendering)může například využít výhod internetového připojení.</span><span class="sxs-lookup"><span data-stu-id="b68c0-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="b68c0-118">poznámka: sdílení internetového připojení vyžaduje kabel mezi mobilním zařízením a HoloLens a sdílení internetového připojení je podporované omezeným počtem zařízení.</span><span class="sxs-lookup"><span data-stu-id="b68c0-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="b68c0-119">Kompatibilita USB-C</span><span class="sxs-lookup"><span data-stu-id="b68c0-119">USB-C compatibility</span></span>

<span data-ttu-id="b68c0-120">s Windows holografickou verzí 2004 a novějším je možné použít omezený počet zařízení, která jsou přítomná jako adaptér ethernet.</span><span class="sxs-lookup"><span data-stu-id="b68c0-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="b68c0-121">Zařízení, která nejsou přítomná jako adaptér sítě Ethernet, musí podporovat obecný ovladač Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) .</span><span class="sxs-lookup"><span data-stu-id="b68c0-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="b68c0-122">ale jenom omezený počet těchto zařízení je kompatibilní s HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b68c0-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="b68c0-123">Podrobnosti o tom, jestli podporuje obecný ovladač Microsoft RNDIS, najdete v výrobci zařízení.</span><span class="sxs-lookup"><span data-stu-id="b68c0-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="b68c0-124">Zařízení, která nejsou kompatibilní s RNDIS nebo vyžadují instalaci ovladače nebo aplikace, nejsou podporována.</span><span class="sxs-lookup"><span data-stu-id="b68c0-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="b68c0-125">V případě, že společnost Microsoft neudržuje seznam kompatibilních zařízení, v [tomto tématu najdete](https://aka.ms/HLCommunityCell)diskusi komunity.</span><span class="sxs-lookup"><span data-stu-id="b68c0-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="b68c0-126">Připojení k připojenému zařízení</span><span class="sxs-lookup"><span data-stu-id="b68c0-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="b68c0-127">Pokud chcete povolit sdílení dat přes USB, Projděte si příručku svého zařízení.</span><span class="sxs-lookup"><span data-stu-id="b68c0-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="b68c0-128">Toto nastavení se často označuje jako "sdílení obsahu USB", "sdílení dat" nebo "modem USB".</span><span class="sxs-lookup"><span data-stu-id="b68c0-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="b68c0-129">Povolí sdílení dat přes USB.</span><span class="sxs-lookup"><span data-stu-id="b68c0-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="b68c0-130">Připojení zařízení na port HoloLens USB-C.</span><span class="sxs-lookup"><span data-stu-id="b68c0-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="b68c0-131">v nastavení sítě HoloLens 2 se zařízení automaticky zobrazí jako připojení k síti Ethernet.</span><span class="sxs-lookup"><span data-stu-id="b68c0-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
