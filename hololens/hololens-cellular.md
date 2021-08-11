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
ms.openlocfilehash: 0a31ff0af0af5b60fc0a44ef8fc5a85b5b50e766201d5441d508fd23dd0369e4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664481"
---
# <a name="connect-to-cellular-and-5g"></a>Připojení mobilní a 5G

HoloLens 2 podporuje dvě metody pro připojení k mobilním a 5G sítím:

- Ad hoc síť Wi-Fi poskytovaná mobilním zařízením, které se běžně označuje jako "hotspot".
- Omezená podpora pro připojená zařízení USB-C

## <a name="hotspot-wifi"></a>HotSpot (Wi-Fi)

Většinu potřeb mobilního připojení je možné splnit pomocí hotspotu. HoloLens 2 wi-fi podporuje standard 802.11 ac, který může poskytovat požadavky na šířku pásma a latenci, které jsou nezbytné pro nejběžnější případy použití. Wi-Fi je také bez kabelů a nabízí kompatibilitu s největším počtem mobilních zařízení.

### <a name="connecting-to-a-hotspot"></a>Připojení k hotspotu

1. Projděte si příručku zařízení, jak povolit režim hotspotu.
1. Povolte režim hotspotu, zadejte název sítě a také známé heslo.
1. v nastavení HoloLens 2 sítě vyhledejte síť wi-fi vytvořenou v kroku 2 a připojte se k ní.

## <a name="usb-c-tethering"></a>Sdílení přes USB-C

Sdílení přes USB-C může poskytovat nižší latenci pro pokročilé úlohy, které ji potřebují. [Vzdálené vykreslování Azure](https://azure.microsoft.com/services/remote-rendering)může například využít výhod internetového připojení. poznámka: sdílení internetového připojení vyžaduje kabel mezi mobilním zařízením a HoloLens a sdílení internetového připojení je podporované omezeným počtem zařízení.

### <a name="usb-c-compatibility"></a>Kompatibilita USB-C

s Windows holografickou verzí 2004 a novějším je možné použít omezený počet zařízení, která jsou přítomná jako adaptér ethernet.

Zařízení, která nejsou přítomná jako adaptér sítě Ethernet, musí podporovat obecný ovladač Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) . ale jenom omezený počet těchto zařízení je kompatibilní s HoloLens 2. Podrobnosti o tom, jestli podporuje obecný ovladač Microsoft RNDIS, najdete v výrobci zařízení.

Zařízení, která nejsou kompatibilní s RNDIS nebo vyžadují instalaci ovladače nebo aplikace, nejsou podporována.

V případě, že společnost Microsoft neudržuje seznam kompatibilních zařízení, v [tomto tématu najdete](https://aka.ms/HLCommunityCell)diskusi komunity.

### <a name="connecting-to-a-tethered-device"></a>Připojení k připojenému zařízení

1. Pokud chcete povolit sdílení dat přes USB, Projděte si příručku svého zařízení. Toto nastavení se často označuje jako "sdílení obsahu USB", "sdílení dat" nebo "modem USB".
1. Povolí sdílení dat přes USB.
1. Připojení zařízení na port HoloLens USB-C.
1. v nastavení sítě HoloLens 2 se zařízení automaticky zobrazí jako připojení k síti Ethernet.
