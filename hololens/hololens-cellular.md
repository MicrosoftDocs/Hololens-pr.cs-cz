---
title: Připojení na Mobilní a 5G
description: Připojení k mobilním sítím z HoloLens zařízení hybridní reality
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427226"
---
# <a name="connect-to-cellular-and-5g"></a>Připojení na Mobilní a 5G

HoloLens 2 podporuje dvě metody připojení k mobilním sítím a sítím 5G:

- Ad hoc síť Wi-Fi poskytovaná mobilním zařízením, která se běžně označuje jako hotspot
- Omezená podpora pro zařízení připojená přes USB-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

Většinu potřeb mobilního připojení je možné splnit s hotspotem. HoloLens 2 WiFi podporuje protokol 802.11ac, který může poskytovat požadavky na šířku pásma a latenci potřebné pro většinu běžných případů použití. WiFi je také bez kabelu a nabízí kompatibilitu s největším počtem mobilních zařízení.

### <a name="connecting-to-a-hotspot"></a>Připojení k hotspotu

1. Informace o tom, jak povolit režim hotspotu, najdete v příručce k vašemu zařízení.
1. Povolte režim hotspotu a zadejte název sítě a známé heslo.
1. V HoloLens 2 Nastavení sítě vyhledejte síť WiFi vytvořenou v kroku 2 a připojte se k ní.

## <a name="usb-c-tethering"></a>Připojení USB-C

Připojení USB-C může poskytovat nižší latenci pro pokročilé úlohy, které je potřebují. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)například může těžit z tetheringu. Upozorňujeme, že tethering vyžaduje kabel mezi mobilním zařízením a HoloLens a připojení je podporováno omezeným počtem zařízení.

### <a name="usb-c-compatibility"></a>Kompatibilita USB-C

S verzí 2004 a novější je možné použít omezený počet zařízení, která se prezentují jako ethernetový Windows.

Zařízení, která se prezentují jako ethernetový adaptér, musí podporovat obecný ovladač Microsoft [RNDIS.](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Ale jenom omezený počet těchto zařízení je kompatibilní s HoloLens 2. Podrobnosti o tom, jestli zařízení podporuje obecný ovladač Microsoft RNDIS, najdete u výrobce vašeho zařízení.

Zařízení, která nejsou kompatibilní s RNDIS nebo která vyžadují instalaci ovladače nebo aplikace, se nepodporují.

I když Microsoft neudržuje seznam kompatibilních zařízení, existuje komunitní diskuze k tématu, které [najdete tady.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Připojení k připojenému zařízení

1. Informace o tom, jak povolit sdílení dat přes USB, najdete v příručce k vašemu zařízení. Toto nastavení se často označuje jako "Připojení USB", "Sdílení dat" nebo "Modem USB".
1. Povolte sdílení dat přes USB.
1. Připojení zařízení na HoloLens USB-C.
1. V HoloLens 2 Nastavení sítě se zařízení automaticky zobrazí jako ethernetové připojení.
