---
title: Připojení k mobilní síti a 5G
description: Připojení k mobilním sítím ze zařízení s hybridní realitou HoloLens
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
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379199"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="861af-103">Připojení k mobilní síti a 5G</span><span class="sxs-lookup"><span data-stu-id="861af-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="861af-104">HoloLens 2 podporuje dvě metody připojení k mobilním sítím a sítím 5G:</span><span class="sxs-lookup"><span data-stu-id="861af-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="861af-105">Ad hoc síť Wi-Fi poskytovaná mobilním zařízením, která se běžně označuje jako hotspot</span><span class="sxs-lookup"><span data-stu-id="861af-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="861af-106">Omezená podpora pro zařízení připojená přes USB-C</span><span class="sxs-lookup"><span data-stu-id="861af-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="861af-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="861af-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="861af-108">Většinu potřeb mobilního připojení je možné splnit s hotspotem.</span><span class="sxs-lookup"><span data-stu-id="861af-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="861af-109">HoloLens 2 WiFi podporuje protokol 802.11ac, který může poskytovat požadavky na šířku pásma a latenci potřebné pro většinu běžných případů použití.</span><span class="sxs-lookup"><span data-stu-id="861af-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="861af-110">WiFi je také bez kabelu a nabízí kompatibilitu s největším počtem mobilních zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="861af-111">Připojení k hotspotu</span><span class="sxs-lookup"><span data-stu-id="861af-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="861af-112">Informace o tom, jak povolit režim hotspotu, najdete v příručce k vašemu zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="861af-113">Povolte režim hotspotu a zadejte název sítě a známé heslo.</span><span class="sxs-lookup"><span data-stu-id="861af-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="861af-114">V nastavení sítě HoloLens 2 vyhledejte síť WiFi vytvořenou v kroku 2 a připojte se k ní.</span><span class="sxs-lookup"><span data-stu-id="861af-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="861af-115">Připojení USB-C</span><span class="sxs-lookup"><span data-stu-id="861af-115">USB-C Tethering</span></span>

<span data-ttu-id="861af-116">Připojení USB-C může poskytovat nižší latenci pro pokročilé úlohy, které je potřebují.</span><span class="sxs-lookup"><span data-stu-id="861af-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="861af-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)například může těžit z tetheringu.</span><span class="sxs-lookup"><span data-stu-id="861af-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="861af-118">Upozorňujeme, že tethering vyžaduje kabel mezi mobilním zařízením a HoloLens a připojení je podporováno omezeným počtem zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="861af-119">Kompatibilita USB-C</span><span class="sxs-lookup"><span data-stu-id="861af-119">USB-C compatibility</span></span>

<span data-ttu-id="861af-120">S Windows Holographic verze 2004 a novější je možné použít omezený počet zařízení, která se prezentují jako ethernetový adaptér.</span><span class="sxs-lookup"><span data-stu-id="861af-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="861af-121">Zařízení, která se prezentují jako ethernetový adaptér, musí podporovat obecný ovladač Microsoft [RNDIS.](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-)</span><span class="sxs-lookup"><span data-stu-id="861af-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="861af-122">S HoloLensem 2 je ale kompatibilní jenom omezený počet těchto zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="861af-123">Podrobnosti o tom, jestli zařízení podporuje obecný ovladač Microsoft RNDIS, najdete u výrobce vašeho zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="861af-124">Zařízení, která nejsou kompatibilní s RNDIS nebo která vyžadují instalaci ovladače nebo aplikace, se nepodporují.</span><span class="sxs-lookup"><span data-stu-id="861af-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="861af-125">I když Microsoft neudržuje seznam kompatibilních zařízení, existuje komunitní diskuze o tomto [tématu.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="861af-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="861af-126">Připojení k připojenému zařízení</span><span class="sxs-lookup"><span data-stu-id="861af-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="861af-127">Informace o tom, jak povolit sdílení dat přes USB, najdete v příručce k vašemu zařízení.</span><span class="sxs-lookup"><span data-stu-id="861af-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="861af-128">Toto nastavení se často označuje jako "Připojení USB", "Sdílení dat" nebo "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="861af-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="861af-129">Povolte sdílení dat přes USB.</span><span class="sxs-lookup"><span data-stu-id="861af-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="861af-130">Připojte zařízení k portu USB-C HoloLens.</span><span class="sxs-lookup"><span data-stu-id="861af-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="861af-131">V nastavení sítě HoloLens 2 se zařízení automaticky zobrazí jako ethernetové připojení.</span><span class="sxs-lookup"><span data-stu-id="861af-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
